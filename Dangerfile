if github.branch_for_base == "master"
  if !git.modified_files.include?("README.md")
    warn "Please add a new entry to the `README.md` file before merging to master."
  end

  if !git.modified_files.include?("index.md")
    warn "Please add a new entry to the `index.md` file before merging to master."
  end
end

markdown_files = (git.modified_files + git.added_files).select do |line|
  line.end_with?(".md")
end

ignored_words = []

File.open('.spelling').each_line do |line|
  line.chomp!
  next if line.empty? || line.start_with?('#')
  ignored_words.push(line)
end

prose.ignored_words = ignored_words
prose.ignore_numbers = true
prose.ignore_acronyms = true
prose.language = "en-us"
prose.lint_files markdown_files
prose.check_spelling markdown_files
