# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: svanmarc <@student.42perpignan.fr>         +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2024/03/04 11:22:58 by svanmarc          #+#    #+#              #
#    Updated: 2024/03/04 11:24:18 by svanmarc         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME = ex00

CC = c++

CFLAGS = -Wall -Wextra -Werror -std=c++98 -Wshadow

SRC = main.cpp Animal.cpp Dog.cpp Cat.cpp

OBJ = $(SRC:.cpp=.o)

all: $(NAME)

$(NAME): $(OBJ)
	$(CC) $(CFLAGS) -o $(NAME) $(OBJ)

%.o: %.cpp
	$(CC) $(CFLAGS) -o $@ -c $<

clean:
	rm -rf $(OBJ)

fclean: clean
	rm -rf $(NAME)

re: fclean all

.PHONY: all clean fclean re