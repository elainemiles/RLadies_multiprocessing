cat("Welcome to the multiprocessing demo project.\n")

# Load useful libraries
check.packages <- function(pkg) {
  new.pkg <- pkg[!(pkg %in% utils::installed.packages()[, "Package"])]
  if (length(new.pkg)) 
    utils::install.packages(new.pkg, dependencies = T, quiet = T)
  sapply(pkg, require, character.only = T, warn.conflicts = F, quietly = T)
}

.libPaths(c(.libPaths(), getwd()))

packages <- c("tidyverse", 
              "lubridate", 
              "microbenchmark",
              "logging",
              "zoo", 
              "tidyquant", 
              "foreach",
              "parallel",
              "doParallel"
              )

cat("Loading and installing required libraries.\n")
cat(paste(packages, collapse = ', ' ))
cat("\n")
check.packages(packages)

# Options
options(stringsAsFactors = FALSE)

# Setup knitr
knitr::opts_chunk$set(fig.width = 12,
                      fig.height = 8,
                      dpi = 96,
                      include = TRUE,
                      warning = FALSE,
                      message = FALSE,
                      echo = TRUE)

# Setup ggplot2
theme_set(theme_bw(base_size = 22))

# Setup logger
# Default 20: INFO and above.  
# See loglevels for more info
logging::basicConfig()

# Setup directory spaces
logging::loginfo("Creating directories:")
base_dir <- getwd()
log_dir <- file.path(base_dir, "logs")
setup_dirs <- c(base_dir, log_dir)
purrr::walk(setup_dirs, dir.create, showWarnings = F)
logging::loginfo(paste(setup_dirs, collapse = ', ' ))

# Suppress warnings
options(warn = -1)

# Start working
logging::loginfo("Environment setup, now time to work!")

# EOF
