# -*- ruby -*-
require "rake"
require "rake/clean"

########################################
# Edit to suit your needs

# LaTeX binary to use. LuaLaTeX strongly recommended.
LATEX = "lualatex"

########################################

CLEAN.include("src/*.aux", "src/*.lof", "src/*.lot", "src/*.log", "src/*.out", "src/*.toc")
CLOBBER.include("src/*.pdf")

begin
  `#{LATEX} --help`
rescue Errno::ENOENT
  abort "#{LATEX} not found."
end

desc "Compiles the document 4 times in a row."
task :compile do
  4.times do
    cd "src" do
      sh "#{LATEX} main.tex"
    end
  end
end

desc "Compiles the document once."
task :compile_once do
  cd "src" do
    sh "#{LATEX} main.tex"
  end
end
