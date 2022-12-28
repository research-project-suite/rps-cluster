# ansible-role-purge_hard_disks

This role PURGES your HARDDISKS. Do not

It only runs if you set `REALLY_PURGE_HARDDISKS_WHICH_WILL_DESTROY_EVERYTHING_ON_YOUR_HARDDISKS_I_KNOW_WHAT_I_AM_DOING` to true. Do not set it fixed in your code but use vars_prompt in your playbook to let the user confirm the usage

```
  vars_prompt:
    - name: REALLY_PURGE_HARDDISKS_WHICH_WILL_DESTROY_EVERYTHING_ON_YOUR_HARDDISKS_I_KNOW_WHAT_I_AM_DOING
      prompt: |
        You are about to PURGE your HARDDISKS which will DESTROY EVERYTHING on your HARDDISKS!!!
        All your FILESYSTEMS, PARTITION TABLES, SOFTWARE RAID, LOGICAL VOLUME GROUPS are going to be erased!
        All Data on you BLOCK DEVICES is going to get overwritten! 

        This will affect the targeted hosts:

        {{ansible_play_hosts| join("
        ")}}

        Do you REALLY want to PURGE your HARDDISKS which will DESTROY EVERYTHING on your HARDDISKS? Do you know what you are doing?
      private: no
```

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
