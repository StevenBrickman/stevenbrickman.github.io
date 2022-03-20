---
layout: post
title: "Homework 1-6 Inventory Tracker"
date: 2022-03-19
categories: jekyll update
---
```

```file = ARGV.first



def check_inventory(file)
  if !File.exist?(file)
    return 0
  end
    f = File.open(file)    
    read = File.read(f)
    return read.to_i
end

def add_to_inventory
     file = ARGV.first
     line1 = $stdin.gets.chomp.to_i + check_inventory(file)
     target = File.open(file, 'w')
     target.write(line1)
     target.close
end

def remove_from_inventory
     file = ARGV.first
     num = $stdin.gets.chomp.to_i - check_inventory(file)
     target = File.open(file, 'w')
     target.write(num)
     target.close
end    

puts "The last time you checked in you had #{check_inventory(file)} pounds of potatoes."
puts "How many pounds of potatoes did you harvest since then? *enter 0 or RETURN in none. "
add_to_inventory
puts "How many potatoes did you sell since then? *enter 0 or just RETURN if none."
remove_from_inventory
puts "now have #{check_inventory(file)} pounds of potatoes."


