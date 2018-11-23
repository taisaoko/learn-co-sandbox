Hi! 👋h

You've opened the IDE Sandbox. 🎉

The Sandbox is an environment that you can access on "readme" and "code-along" lessons in Learn. It's a great place to experiment with code when you're not working on a "lab" (labs open the IDE In Browser).

The work you do in the Sandbox will be saved from lesson to lesson, and is automatically saved on your behalf to a repository in your GitHub account called `learn-co-sandbox`.

Please DO NOT touch this repository in GitHub, as it will affect your Sandbox experience, and potentially cause your work to be out of sync.

To learn more about the Sandbox, please visit http://help.learn.co/ide-in-browser#sandbox.
 def self.scrape_sinclair
    doc = Nokogiri::HTML(open("http://sinclair.edu/academics/online/"))
    program_list = []
    
    doc.css(".col-xl-8.col-12 ul li").children.each do |children|
      program_list << children.text
    end
    program_list
    
    # program_list = []
    
    #   doc.css("div.row").children.css("div.row ul li a").children.each do |children|
    #     program_list << children.text
    #   end
    
    #   doc.css("ul").children.each.with_index do |children, i|
    #     index_list = [111, 113, 117, 119, 121, 123]
    #     if index_list.include?(i)
    #     program_list << children.text
    #     end
    #   end
    # program_list
    
    #doc.css("div.c-4.nr.nt ul:nth-child(8) li").text
    
  end
  
  def print_program(program)
    puts ""
    puts "----------- #{program.name} - #{program.degree_type} -----------"
    puts ""
    puts "Division:            #{program.division}"
    puts "Department:          #{program.department}"
    puts "Contact:             #{program.contact}"
    puts "Website:             #{program.url}"
    puts "---------------Outcomes--------------" 
    puts ""
    puts "#{program.outcomes}"
    puts ""
    puts "--------Career Opportunities---------"
    puts ""
    puts "#{program.career_opportunity}"
    puts ""
    puts "---------------Description--------------"
    puts ""
    puts "#{program.description}"
    puts ""
  end