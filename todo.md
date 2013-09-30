- in the json, we store a boolean indicating whether or not message is encrypted

- a button says "decrypt feed with this password."  tries that password on each (encrypted) post in the feed. if sjcl says "no," just leave that post as it is. otherwise, print decrypted message to the js console


-------------------

- store the decrypted message somehow in the post, so we can't see the encrypted version that's stored persistently 