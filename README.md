import os
from moviepy.editor import *
directory = os.getcwd()

# Get the list of image file names
fls = sorted([f for f in os.listdir(directory) if f.endswith('.mp4')],reverse=False)
fls
# set input and output file names
input_file = fls
output_file='replicated_video.mp4'
image_file = '/content/TD1.JPG'
# Create a list of three copies of the video

videos = [VideoFileClip(x) for x in input_file]

# videos = [original_video] * 50

# Concatenate the videos to create a new video clip
new_video = concatenate_videoclips(videos)

# load the static image file
image = ImageClip(image_file).set_duration(new_video.duration)

# combine the video clip and image clip
final_clip = CompositeVideoClip([new_video, image])

final_clip.write_videofile(output_file,fps=24,verbose=False, remove_temp=True, codec="libx264", audio_codec='libmp3lame',preset='medium')




#new_video.write_videofile(output_file,fps=24,verbose=False, remove_temp=True,
 #   codec="libx264",
  #  audio_codec='libmp3lame',preset='medium')


  ##############################################################
  ################# Video editin ################
import os
from moviepy.editor import *
# Get the current working directory
current_directory = os.getcwd()

# List files in the current directory ending with .mp4
fls = [file for file in os.listdir(current_directory) if file.endswith('.mp4')]

# set input and output file names
input_file = fls
output_file='replicated_video.mp4'
image_file = 'TD1.JPG'
# Create a list of three copies of the video

videos = [VideoFileClip(x) for x in input_file]

# videos = [original_video] * 50

# Concatenate the videos to create a new video clip
new_video = concatenate_videoclips(videos)

# load the static image file
image = ImageClip(image_file).set_duration(new_video.duration).on_color((1280, 720), color=(0,0,0), pos='center')
image
# # combine the video clip and image clip
# final_clip = CompositeVideoClip([new_video, image])
final_clip = CompositeVideoClip([new_video, image])
final_clip.write_videofile(output_file,fps=24,verbose=False, remove_temp=True, codec="libx264", audio_codec='libmp3lame',preset='medium')
