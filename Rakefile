require "rake"

task default: %w[deploy]

task :deploy, [:comment] do |t, args|
    # Build to _site
    `jekyll build`
    # Commit code in _site and push to github
    timestamp = Time.new.strftime("%Y-%m-%d %H:%M:%S").to_s
    args.with_defaults(comment: "auto build #{timestamp} HK")
    puts "deploy start"
    `cd _site; git add . --all; git commit -m "#{args[:comment]}"; git push`
end

