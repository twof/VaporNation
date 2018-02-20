if github.branch_for_base == "master"
  if !git.modified_files.include?("README.md")
    warn "Please add a new entry to `README.md` file before merging to master."
  end

  if !git.modified_files.include?("index.md")
    warn "Please add a new entry to `index.md` file before merging to master."
  end
end
