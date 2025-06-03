# setup.R — Template for a Reproducible R Environment
# ---------------------------------------------------------------
# This script sets up a reproducible environment for a new study or project.
# It uses {renv} to manage package versions and dependencies,
# {here} to manage file paths, and {quarto} for reproducible reporting.
# ---------------------------------------------------------------

# Project environment management
install.packages("renv", repos = "https://cloud.r-project.org")
library(renv)
renv::init(bare = TRUE)  # creates a new renv environment
# For existing projects with renv.lock file, use renv::restore() to recreate the environment

# Essential packages {here} and {quarto}, add all other packages you need
packages <- c("here", "quarto", "labelled", "stringr", "tidyverse", "ggplot2")

# 3. Install missing packages and load packages
for (pkg in packages) {
  if (!requireNamespace(pkg, quietly = TRUE)) {
    message("Installing missing package: ", pkg)
    install.packages(pkg, repos = "https://cloud.r-project.org")
  }
  suppressPackageStartupMessages(library(pkg, character.only = TRUE))
}

renv::snapshot(prompt = FALSE) # Save the current state of the environment (rerun after installing additional packages)

# Quarto installation and version
if (!is.null(quarto::quarto_path())) {
  message("Quarto is installed! Version: ", quarto::quarto_version())
} else {
  warning(
    "Quarto is not installed on this system.\n",
    "Please install Quarto from https://quarto.org before rendering documents."
  )
}

# Generate plain-text citations for essential packages
generate_package_citations <- function(packages, outfile = "package_citations.txt") {
  message("Generating plain-text citations for project packages...")
  sink(outfile)
  for (pkg in packages) {
    tryCatch({
      cat("------------------------------------------------------------\n")
      cat("Package:", pkg, "\n\n")
      print(citation(pkg), style = "text")
      cat("\n\n")
    }, error = function(e) {
      warning(sprintf("Could not generate citation for package '%s': %s", pkg, e$message))
    })
  }
  sink()
  message("Plain-text citations saved to: ", outfile)
}

generate_package_citations(packages, "package_citations.txt")

message("Project setup complete")