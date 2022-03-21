### stats 220
*meme creation*

## why did I create this meme?
1. for the assignment 
2. I watched 5 episodes of Jane the Virgin on Netflix which led me to procrastinate 


# my GitHub!
https://github.com/jlok459/stats220


### my meme
https://github.com/jlok459/stats220/blob/main/my%20meme.png


# R code for meme

library(magick)

#section one 
first_photo <- image_read("https://i.imgflip.com/4/t7px7.jpg") %>%
  image_scale(500)

#section two
second_photo <- image_read("https://i.pinimg.com/originals/03/18/37/0318370bfcfe64ee2f9b5ed4081c00e9.jpg") %>% 
  image_scale(500)

#section three 
lecture_text <- image_blank(width = 500, 
                           height = 500, 
                           color = "#000000") %>% 
  image_annotate(text = "Watching a one hour lecture", 
                 color = "#FFFFFF", 
                 size = 40, 
                 gravity = "center")

#section four
netflix_text <- image_blank(width = 500, 
                            height = 500, 
                            color = "#000000") %>% 
              image_annotate(text = "watching 5 hours of Netflix", 
                             color = "#FFFFFF", 
                             size = 40, 
                             gravity = "center")
  
#combining section one and three
top_row <- image_append(c(first_photo, lecture_text))

#combining section two and four
bottom_row <- image_append(c(second_photo, netflix_text))

c(top_row, bottom_row) %>%
  image_append(stack = TRUE)
