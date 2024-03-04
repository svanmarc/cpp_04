# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: svanmarc <@student.42perpignan.fr>         +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2024/03/04 11:22:58 by svanmarc          #+#    #+#              #
#    Updated: 2024/03/04 11:49:37 by svanmarc         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

name = ex00

SRC_DIR = srcs
SRCS = $(wildcard $(SRC_DIR)/*.cpp)

OBJS_DIR = objs
OBJS = $(patsubst $(SRC_DIR)/%.cpp, $(OBJS_DIR)/%.o, $(SRCS))

INCLUDES = -I./includes

CC = g++
CFLAGS = -Wall -Wextra -Werror -g -std=c++98 -Wshadow $(INCLUDES)

RM = rm -rf

DEP_FILE = .depend

all: $(name)

$(name): $(OBJS)
	@$(CC) $(CFLAGS) $(OBJS) -o $@ 
	@echo "\033[32mCompilation done !\033[0m"

$(OBJS_DIR):
	@mkdir -p $(OBJS_DIR)

$(OBJS_DIR)/%.o: $(SRC_DIR)/%.cpp | $(OBJS_DIR)
	@$(CC) $(CFLAGS) $(INCLUDES) -c $< -o $@
	@echo "\033[32mCompilation of $< done !\033[0m"

clean:
	$(RM) $(OBJS_DIR) $(DEP_FILE)
	@echo "\033[31mObjects deleted !\033[0m"

fclean: clean
	$(RM) $(name)
	@echo "\033[31m$(name) deleted !\033[0m"

re: fclean all

$(DEP_FILE): $(SRCS) $(INCLUDES)
	@$(CC) -MM $(SRCS) > $(DEP_FILE)

-include $(DEP_FILE)

