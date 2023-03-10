task :default do
  types = Dir['*/*tally*.lst'].map{|f| File.readlines(f).map{|l| l.split(',').first}}.join("\n").split(/\s+/).map(&:strip).uniq.sort
  types = types.reject{|t| t.match?(/^ء/) || t.match?(/^آ+$/)}.map{|t| t.gsub(/^آ[أا]+/,'آ')}.map{|t| t.gsub(/آ+/,'آ')}.uniq.sort
  File.write('types.lst', types.join("\n"))
end
