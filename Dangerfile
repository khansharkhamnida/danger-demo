warning_count = 0

# Check 1: PR Description
if github.pr_body.empty?
  warn("Add a description")
  warning_count += 1
end

# Check 2: PR Title

if github.pr_title.length < 10
  warning_count += 1
  warn("Title too short") 
end

# Check 3: PR Labels
if git.lines_of_code > 500
  warn("PR is too large") 
  warning_count += 1
end

# Check 4: PR Size
if git.lines_of_code > 500
  warn("PR is too large")
  warning_count += 1
end

# Check 5: Documentation

if git.modified_files.any? { |f| f.start_with?("src/") } && !git.modified_files.include?("README.md")
  warn("Update README")
  warning_count += 1
end

# Confirmation
if warning_count == 0
  message("No warnings found. All checks have passed.")
end
