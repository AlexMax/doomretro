#
#========================================================================
#
#  DOOM RETRO
#  The classic, refined DOOM source port. For Windows PC.
#  Copyright (C) 2013-2014 by Brad Harding. All rights reserved.
#
#  DOOM RETRO is a fork of CHOCOLATE DOOM by Simon Howard.
#
#  For a complete list of credits, see the accompanying AUTHORS file.
#
#  This file is part of DOOM RETRO.
#
#  DOOM RETRO is free software: you can redistribute it and/or modify
#  it under the terms of the GNU General Public License as published by
#  the Free Software Foundation, either version 3 of the License, or
#  (at your option) any later version.
#
#  DOOM RETRO is distributed in the hope that it will be useful, but
#  WITHOUT ANY WARRANTY; without even the implied warranty of
#  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
#  GNU General Public License for more details.
#
#  You should have received a copy of the GNU General Public License
#  along with DOOM RETRO. If not, see <http://www.gnu.org/licenses/>.
#
#========================================================================
#

CFLAGS = -m32 -O2 -g `sdl-config --cflags ` $(INCLUDES)
LDFLAGS = -g `sdl-config --libs` -lSDL_mixer

SRCS := $(shell find . -name '*.c')

OBJS = $(patsubst %.c,%.o,$(SRCS))

doomretro : $(OBJS)
	$(CC) $(CFLAGS) $(LDFLAGS) $^ $(LIBS) -o $@

%.o : %.c
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	rm -f $(OBJS) doomretro
