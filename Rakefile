# -*- ruby -*-
require "rake"
require "rake/clean"

########################################
# Edit to suit your needs

# LaTeX binary to use. LuaLaTeX strongly recommended.
LATEX = "lualatex"

########################################

CLEAN.include("*aux", "*.lof", "*.lot", "*.log", "*.out", "*.toc")
CLOBBER.include("*.pdf")

begin
  `#{LATEX} --help`
rescue Errno::ENOENT
  abort "#{LATEX} not found."
end

desc "Compiles the document 4 times in a row."
task :compile do
  4.times do
    sh "#{LATEX} main.tex"
  end
end

desc "Compiles the document once."
task :compile_once do
  sh "#{LATEX} main.tex"
end
