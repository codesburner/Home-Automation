#!/usr/bin/env ruby

require "rexml/document"

puts "started desu~"

# Running mean.
sample_power_total = 0
sample_power_count = 0
sample_tmpr_total = 0
sample_tmpr_count = 0

# Best way to read stdin?
ARGF.each do |line|
#  puts "line: #{line}"
  if line.strip.length > 0
    # I have no idea why I need two [0]. 
    watts = Integer(line.scan(/<ch1><watts>[0]*([^<]*)</)[0][0])
    tmpr = Float(line.scan(/<tmpr>([^<]*)</)[0][0])
   
    sample_power_total += watts
    sample_power_count += 1
    mean_power = sample_power_total / ( sample_power_count > 0 ? sample_power_count : 1 )
     
    sample_tmpr_total += tmpr
    sample_tmpr_count += 1
    mean_tmpr = sample_tmpr_total / ( sample_tmpr_count > 0 ? sample_tmpr_count : 1 )
    
    puts "watts: #{watts} ( #{mean_power} ) | tmpr: #{tmpr} ( #{mean_tmpr} )"
  end
end

