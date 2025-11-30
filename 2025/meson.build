# Project metadata
project('aoc2025', 'cpp', default_options: ['cpp_std=c++17'], version: '2025')

# Imports
fs = import('fs')

# Directories
# incdir = include_directories('include')

# Dependencies
gtest = dependency('gtest', required: true)
gtest_main = dependency('gtest_main', required: true)
test_args = ['--gtest_color=yes']

# Tests for each problem
foreach ith_problem : range(1, 26)
  if not fs.exists('problem_' + ith_problem.to_string() + '.cpp')
    continue
  endif
  problem = executable(
    'problem_' + ith_problem.to_string(),
    'problem_' + ith_problem.to_string() + '.cpp',
    dependencies: [gtest, gtest_main],
    install: false,
  )
  test(
    'AOC-2025',
    problem,
    args: test_args,
    suite: 'tests_aoc_2025',
  )
endforeach


