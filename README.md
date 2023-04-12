# Video_processing
# processing through audio
# Load the video file
video = VideoFileClip(input_file)
audio = video.audio
clips = [audio]*50
# Combine the clips using the CompositeAudioClip class
final_clip = CompositeAudioClip(clips)
# Create a new video clip with the extracted audio
new_video = ImageClip(image_file).set_duration(video.duration*50)
new_video = new_video.set_audio(final_clip)
