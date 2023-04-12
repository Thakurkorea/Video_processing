new_video.write_videofile(output_file,fps=24,verbose=False, remove_temp=True,
    codec="libx264",
    audio_codec='libmp3lame',preset='medium')
