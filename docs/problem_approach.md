## How I approached this problem:

I knew there was a pattern that I was manually checking for across multiple files.
Whenever you notice a manual action that you are taking more than once, your first
thought should be: "Can I automate this?" Sometimes the answer is "yes, but the time
it would take is not worth the time it would save". But if you think you can save time/hassle,
identify the actions that are taking place. It's helpful, since we are talking about automation,
to think in pseudocode.

BEGIN
For each video file in a known directory/set of directories,
  If the video file has a yell (audio spike) in it
    Add that video file to the montage
END

The next question is "do I have access to tools that can perform these actions?"
I don't know how to automatically add the video to the montage, but I should at
least be able to get the list of files and when the audio spike ocurred for each.

So now, identify the script (again, using pseudocode):

BEGIN
For each video file in a directory
  for each audio spike lasting longer than 1 second in the file
    add the spike beginning and end time to list of known spikes

output list of known spikes to user
END

It is by no means required to document this thought process. When you have experience
in the problem domain, often this whole conversation ocurrs internally in a matter of seconds,
and you know whether or not you will move forward with scripting.
