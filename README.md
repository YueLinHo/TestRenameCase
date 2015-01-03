TestRenameCase
==============

### Create a repo which has both Abc.txt and abc.txt files ###

first commit

![](/Image/01_Commit1_abc.png)

```git config core.ignorecase false```

![](/Image/02_set_ignorecase_false.png)

Rename via explorer contexn meanu (not TortoiseGit)

![](/Image/03_Rename_Case.png)

Commit it (NOTE: Only one item in list)

![](/Image/04_Commit2_Abc.png)

Check log (NOTE: status of Abc.txt is ```Added```, not rename)

![](/Image/05_Log2.png)

Create test branch and checkout it

![](/Image/06_Create_Branch_+_Switch.png)

*Problem here:* file is not checkout, the status is ```Deleted```, so Revert it.

Then, abc.txt in working tree:

![](/Image/07_After_Revert.png)

Modified the abc.txt, and commit it.

![](/Image/08_test_branch_commit1.png)

Check log:

![](/Image/09_Log3.png)

Checkout master, but failed. (in Windows)

![](/Image/10_Switch_to_master_failed.png)

So, delete abc.txt file.

![](/Image/11_delete_abc.png)

Then, checkout master again. the result:

![](/Image/12_only_abc_is_checkout_and_no_Abc.png)

Merge.

![](/Image/13_Merge.png)

Merge is ok.

![](/Image/14_Merge_OK.png)

![](/Image/15_Log_Merged.png)

But the result(the following 2 screeshots) is not wanted.

The frist, the working tree is not clean.

![](/Image/16_Working_dir_changes.png)

Try to revert it, but show abc.txt is modified this time.

![](/Image/17_Revert_Abc.png)

*Suppose the core.ignorecase shlould be not set to false.*

### Back to... ###

Reset hard master

![](/Image/18_Reset_hard.png)

Confirm with browser repository

![](/Image/19_Browser_repository.png)

### In Windows, core.ignorecase = true by default ###

set back

```git config core.ignorecase true```

![](/Image/20_set_ignorecase_true.png)

Delete the file and the log

![](/Image/21_Delete_and_Log.png)

Reset hard again

*Problem here:* abc.txt is checkout, not Abc.txt.

![](/Image/22_Reset_hard.png)

Delete the file again.

![](/Image/23_Delete_again.png)

Rvert Abc.txt

![](/Image/24_Revert.png)

The Result: (wait a minute)

![](/Image/25_After_Revert.png)

Press F5 to refresh:

![](/Image/26_After_Refresh.png)

Delete the file again. (The 3rd times)

![](/Image/27_Delete_again.png)

Open Commit dialog

Uncheck wanted item and commit

![](/Image/28_Uncheck_wanted_item.png)

Revert wanted item

![](/Image/29_Revert_wanted_item.png)

Revert result

![](/Image/30_After_Revert.png)

Try mrege again

![](/Image/31_Merge.png)

Oops! conflict.

![](/Image/32_Merge_conflict.png)

Abort Merge. (Tried some resolve method, but failed.)

![](/Image/33_Abort_Merge.png)

Checkout test branch

![](/Image/34_Checkout_test.png)

Using TortoiseGit's Rename

![](/Image/35_Rename_Abc.png)

Commit

![](/Image/36_commit.png)

Now, checkout master and do merge again.

![](/Image/37_Merge.png)

Merge OK.

![](/Image/38_Merge_OK.png)

![](/Image/39_Merge_result.png)




