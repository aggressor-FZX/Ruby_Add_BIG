# Ruby_Add_BIG
#Adds a giant unstorable integer as string for practice sake
# number 2 must be the larger of the two numbers
# follows the same algorithm that we use for adding on paper

def addBig(num1, num2)
  a = num1.to_s
  b = num2.to_s
  a_split = a.chars
  b_split = b.chars
  index = 0
  carry = 0
  new_char = []
  
  for each in b_split.reverse do
  
    puts "TOTAL - #{new_char.join()}"
    sum = each.to_i + a.reverse[index].to_i + carry
    puts "#{sum} = #{each.to_i} + #{a.reverse[index].to_i} + #{carry}"
    index += 1
    puts "sum #{sum}"
    
    if sum >= 10
      newval = sum%10
      new_char.unshift(newval)
      puts "storing #{newval}"
      carry = 1
      puts "Carry the #{carry}"
    
    else
      carry = 0
      new_char.unshift(sum)
      puts "storing #{sum}"
    end
  
  end

  while carry == 1
    index += 1
    sum = b.reverse[index].to_i + carry
    puts " Finally is #{b.reverse[index].to_i} + #{carry} = #{sum}"
    if sum >= 10
      newval = sum%10
      puts "remainder =  #{newval}"
      new_char.unshift(newval)
      puts "storing #{newval}"

    else
      new_char.unshift(sum)
      puts "carry is set to 0, storing #{sum} "
      carry = 0
    end
  
  end
  strings_end = b.length - index
  
  final = new_char.join() 
  return final.to_s.strip
end
