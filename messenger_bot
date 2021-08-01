
from fbchat import Client, log
from fbchat.models import *

email = "EMAIL"
password = "PASSWORD"
message_to_trigger = "message"
message_to_reply = "reply"


class reply(Client):
    def onMessage(
            self,
            author_id=None,
            message_object=None,
            thread_id=None,
            thread_type=ThreadType.USER,
            **kwargs
    ):
        self.markAsRead(author_id)
        log.info(f"{message_object} from {thread_id} in {thread_type}")

        message = message_object.text
        if message_to_trigger in message.lower():
            if author_id != self.uid:
                self.send(Message(text=message_to_reply), thread_id=thread_id, thread_type=thread_type)


object = reply(email, password)

object.listen()
