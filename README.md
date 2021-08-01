# messenger_chat_bot

####Package required
pip install fbchat

#### Change 
fbchat _state.py line 190 : revision = int(r.text.split('"client_revision":', 1)[1].split(",", 1)[0]) -> revision = 1

_state.py FB_DTSG_REGEX = re.compile(r'name="fb_dtsg" value="(.*?)"') -> FB_DTSG_REGEX = re.compile(r'"fb_dtsg" value="(.*?)"')
