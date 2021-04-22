**Pour crée un évènement :**
- on doit tout d'abord crée la fonction : 
- pour cette exemple il s'agit d'un évènement ou l'ont ne peut pas copier un texte
```Javascript
noCopy = () => {
//on met le nom que l'ont veut
	alert('merci de ne pas copier')
//on active la methode
}
````
- ensuite on ajoute l'évènement dans la balise ou l'ont souhaite l'activer : 
```Javascript
<p onCopy={this.noCopy}>TEXT A NE PAS COPIER</p>
//this car nous somme dans une class 
//onCopy est le nom de l'évènement
}
````
==SI NOUS ETIONS DANS UNE FUNCTION ON NE DEVRAIT PAS METTRE LE THIS==
**Type d'évènement**
## onCopy :
-  pour ne pas copier et lancer un alert :
```Javascript
noCopy = () => {
	alert('merci de ne pas copier')
}
````
## onMousseOver : 
- pour pouvoir donner un style lorqu'ont passe la souris sur quelque chose : 
- on a rajouter dans l'index.css la classe a la balise qu'ont veut modifier : 
```Css
	 h1.styled{
		color: red;
		text-transform: uppercase;
	}
````
- on a mit une condition pour que lorsque on passe la souris dessus la condition ce met quand la class se rajoute
```Javascript
addStyle = (e) => {
	if (e.target.classList.contains('styled')) {
//e.target = la valeur
//classList.contains = pour trouver la class ('//')
		e.target.classList.remove('styled')
//.remove = pour supprimer la classe ('//')
	}else{
		e.target.classList.add('styled')
//.add = pour ajouter la classe ('//')
	}
}
`````
## onClick : 
- c'est un évènement au click :
- il y'a deux manière de le faire via une fonction ou via un paramètre 
//fonction
```Javascript
//state ou se trouve le titre qu'ont veut modifier
state = {
titreVoiture :  'Mon catalogue Voiture'
}
//fonction flechée
changeTitle = (e) => {
	// console.log(e.target)
//obliger de mettre setState quand on veut recuperer un objet qui est dans un state
	this.setState({
		titreVoiture :  'Mon nouveau titre'
	})
}

<button  onClick={this.changeTitle}>Changer le titre</button>
````
//via un paramètre :
```Javascript
changeTitleViaParam = (titre) => {
//ici on passe un paramètre qu'ont va faire appel dans le setState qui vaut la valeur du state modifier avec celle de la fonction
	this.setState({
		titreVoiture :  titre
	})
}

<button  onClick={() =>  this.changeTitleViaParam('Titre via un paramètre')}>modifier avec parametre</button>
````
## onChange :
- c'est un évènement ou l'ont peut changer/modifier un élément 
- je prend  ci-dessous comme exemple un input :
```Javascript
changeTitleInput = (e) => {
console.log(e.target.value)
	this.setState({
		titreVoiture :  e.target.value
//on prend le state titreVoiture et on lui assigne ca propre value qui serra afficher dans la valeur de l'input 
//grace a la methode onChange, la valeur de l'input changera le state(le titre, h1)
	})
}
````



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY1NTYyNjUwMl19
-->