
git config --global user.name "Your Name"	             Set your Git username/name
git config --global user.name	                         Check your Git name
git config --global user.email "you@email.com"	       Set your Git email
git config --global user.email	                       Check your Git email
git config --global core.editor "code --wait"	         Set VS Code as Git editor
git config --global core.autocrlf "input"	             Handle line-ending differences




git inctallation

U - untracked
A - added or staged
C - Commited

commands you need to know 
git status -s => to know about staged and unstages file
git log --oneline => know the corrent ststus of save points

managing your own projects
making a git avalible in one project
making a ckeck point and save point
   adding files
   staging them
   commiting them
going back to the some previous save point
  logging everything
  reverting back to the previous saved point  (git reset --hard HEAD~1)  


**Git Conflict** = Jab **2 changes same line/code ko different tarike se change karte hain**, Git decide nahi kar pata ki **kaunsa change rakhe**.

Git conflict hone par generally 3 options milte hain:

Accept Current Change → Tumhara current/local change rakho.
Accept Incoming Change → Dusre branch/person ka change rakho.
Accept Both Changes → Dono changes rakho.

👉 Easy: Current = mera, Incoming = uska, Both = dono.

rm -rf .git → Project ke andar .git folder delete karta hai, yani us project ka Git repository connection/history remove ho jata hai.

-----------------------------------------------

git branch feature/navbar → ek new branch create karta hai jiska naam feature/navbar hai. 🌿

👉 Important: Ye branch create hoti hai, but tum automatically us branch par switch nahi hote.

Switch karne ke liye:   git switch feature/navbar


IMP => MARGED KAR NAI KAI LIYE MAIN BRACH PAR RAHANA JARURI HAI

git merge feature/navbar




git log --oneline --graph → Git ki commit history ko short form me aur branch ka visual graph ke saath dikhata hai.

---------------------------
Three-way merge → Jab Git 2 branches ko merge karte time 3 versions compare karta hai: Current branch + Other branch + Common Ancestor (old common commit).

👉 Easy yaad rakho: “2 branches + 1 common parent = Three-way merge.”
-----------------------------

Fast-forward merge → Jab current branch me koi extra commit nahi hota, Git simply branch pointer ko aage move kar deta hai—new merge commit nahi banta.

👉 Easy yaad rakho: “No separate work → pointer forward → Fast-forward.”

------------------------------------

git branch -d feature/navbar → feature/navbar branch ko delete karta hai. 🗑️

👉 Easy yaad rakho:
-d = delete branch

-------------------------------------------

git switch -C feature/add-footer

git switch -C feature/add-footer → feature/add-footer naam ki branch create karta hai aur turant us branch par switch karta hai.

👉 Easy yaad rakho:
-C = Create + Switch (aur agar branch already hai to reset/overwrite kar sakta hai)

-------------------------------------------------

git stash → Tumhare current uncommitted changes ko temporarily save karke working directory clean kar deta hai.

👉 Easy yaad rakho: “Kaam save karo, abhi side me rakho.” 📦

----------------------------------------------

git stash apply → Jo changes tumne git stash se temporarily save kiye the, unhe wapas working directory me laata hai.

👉 Easy yaad rakho:

git stash = changes side me rakho 📦
git stash apply = changes wapas lao 🔄

⚠️ apply ke baad stash delete nahi hota.

---------------------------------------------------

git stash clear → Saare saved/stashed changes ko permanently delete karta hai. 🗑️

👉 Easy yaad rakho:
stash = save aside 📦
stash clear = all stash delete ❌

-----------------------------------------------------
----------
****************  IMPORTENT NOTE ************************
----------
-----------------------------------------------------

Agar tum:

 > git stash apply

karne ke baad:

> git stash clear

chalate ho, to working directory me jo changes apply ho chuke hain woh delete nahi honge. ✅

git stash clear sirf stash ke andar saved copies ko delete karta hai.

-----------------------------------------------------------------------------------------

