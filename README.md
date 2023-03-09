# Doc-Spring-Boot
Bonnes pratiques Spring Boot de A à Z

## Bien démarre un projet Spring boot :

1. *Installation de l'environnement de développement :* Vous devez installer un IDE (Integrated Development Environment) pour développer votre projet. Vous pouvez utiliser des IDEs populaires tels qu'Eclipse, IntelliJ IDEA ou Visual Studio Code pour développer des projets Spring Boot.

2. *Création du projet :* Pour créer un nouveau projet Spring Boot, vous pouvez utiliser l'outil de création de projet Spring Initializr. Il permet de générer rapidement une structure de projet de base pour Spring Boot avec des dépendances courantes telles que Spring MVC, Spring Data, etc.

3. *Configuration des dépendances :* Dans le fichier **pom.xml** (si vous utilisez Maven) ou **build.gradle** (si vous utilisez Gradle) de votre projet, vous pouvez ajouter les dépendances requises pour votre projet. Par exemple, si vous souhaitez utiliser une base de données MySQL, vous devez ajouter la dépendance correspondante dans votre fichier de configuration.

4. *Écriture du code :* Vous pouvez maintenant écrire votre code en utilisant les annotations Spring Boot. Par exemple, si vous souhaitez créer un endpoint REST, vous pouvez utiliser l'annotation **@RestController** pour indiquer que votre classe est un contrôleur REST.

5. *Exécution du projet :* Pour exécuter votre projet, vous pouvez utiliser les fonctionnalités de votre IDE ou exécuter la commande **mvn spring-boot:run** ou **./gradlew bootRun** dans votre terminal.

6. *Tests :* Il est important de tester votre projet pour vous assurer que tout fonctionne correctement. Vous pouvez écrire des tests unitaires et d'intégration en utilisant des bibliothèques de test populaires telles que JUnit et Mockito.

7. *Déploiement :* Une fois que vous avez terminé de développer et tester votre projet, vous pouvez le déployer sur un serveur d'application tel que Tomcat ou Jetty. Vous pouvez également déployer votre projet sur des plates-formes cloud telles que AWS, Heroku ou Azure.

## Créer son premier projet Spring Boot

1. Ouvrez votre navigateur web et allez sur le site web de Spring Initializr à l'adresse suivante : [https://start.spring.io/](https://start.spring.io/).

2. Configurez les détails de votre projet en choisissant le langage de programmation (Java, Kotlin, Groovy), la version de Spring Boot, le nom de votre projet et les dépendances dont vous avez besoin pour votre projet. Vous pouvez sélectionner des dépendances courantes telles que **Spring Web** (pour la création d'API REST), **Spring Data JPA** (pour la gestion des bases de données), et **Thymeleaf** (pour la création de pages web dynamiques).

3. Cliquez sur le bouton **Generate** pour générer votre projet. Cela va télécharger un fichier ZIP contenant la structure de projet de base.

4. Extrayez le fichier ZIP sur votre ordinateur et ouvrez votre projet dans votre IDE préféré (par exemple, IntelliJ IDEA, Eclipse).

5. Écrivez votre code en utilisant les annotations Spring Boot. Par exemple, si vous souhaitez créer un endpoint REST, vous pouvez ajouter la classe **@RestController** pour indiquer que votre classe est un contrôleur REST et ajouter une méthode avec l'annotation **@GetMapping** pour indiquer le point de terminaison et la méthode HTTP utilisée.

6. Exécutez votre application en utilisant la fonctionnalité de votre IDE ou en exécutant la commande **mvn spring-boot:run** ou **./gradlew bootRun** dans votre terminal.

7. Testez votre application en utilisant des outils de test comme Postman pour tester vos endpoints REST ou JUnit pour tester vos services et classes de données.

## Importer un projet Spring Boot sur Eclipse

1.  Ouvrez Eclipse IDE et sélectionnez **"File"** dans la barre de menus, puis cliquez sur **"Import"**.
2. Dans la boîte de dialogue **"Import"**, sélectionnez **"Existing Maven Projects"** et cliquez sur **"Next"**.
3.  Dans la boîte de dialogue **"Import Maven Projects"**, cliquez sur **"Browse"** et sélectionnez le répertoire racine de votre projet Spring Boot.
4.  Une fois que vous avez sélectionné le répertoire, cliquez sur **"Finish"**. Eclipse devrait maintenant importer le projet Maven dans votre espace de travail.
5.  Pour exécuter le projet, ouvrez le fichier principal de l'application Spring Boot (généralement nommé **"Application.java"** ou similaire) et exécutez-le en tant qu'application Java.

> Remarque: Assurez-vous d'avoir installé le plugin Maven dans Eclipse avant d'importer le projet. Si vous ne l'avez pas déjà installé, vous pouvez le faire en suivant les instructions dans le chapitre suivant.

## Configurer Eclipse pour Maven et Spring Boot

1.  Assurez-vous que vous avez installé Eclipse IDE pour Java EE Developers, car cela inclut les plugins nécessaires pour travailler avec Maven et Spring Boot.
    
2.  Dans Eclipse, ouvrez le menu **"Window"** dans la barre de menus, sélectionnez **"Preferences"**, puis recherchez **"Maven"** dans la barre de recherche.
    
3.  Sélectionnez **"Installations Maven"** et ajoutez une installation Maven si elle n'est pas déjà présente. Vous pouvez télécharger la dernière version de Maven à partir de son site officiel et l'ajouter en tant qu'installation Maven dans Eclipse.
    
4.  Dans la section **"User Settings"**, configurez le fichier **"settings.xml"** de Maven pour inclure les informations d'authentification et les configurations de proxy si nécessaire. Vous pouvez également ajouter des référentiels Maven supplémentaires dans cette section.
    
5.  Pour travailler avec Spring Boot dans Eclipse, vous pouvez ajouter le plugin Spring Tools Suite (STS) à Eclipse. Pour ce faire, allez dans le menu **"Help"** dans la barre de menus, sélectionnez **"Eclipse Marketplace"**, recherchez **"Spring Tools"**, puis sélectionnez "Spring Tools 4 (aka Spring Tool Suite 4)" pour l'installer.
    
> Une fois que vous avez installé STS, vous pouvez créer des projets Spring Boot en utilisant les modèles fournis dans le menu "File" > "New" > "Spring Starter Project". Vous pouvez également utiliser la vue "Spring Explorer" pour accéder aux fonctionnalités de Spring Boot, telles que la configuration des propriétés d'application et la gestion des dépendances.
    
6.  Pour exécuter des applications Spring Boot dans Eclipse, vous pouvez utiliser la fonctionnalité **"Run as Spring Boot App"**. Cela lancera l'application dans un conteneur embarqué Tomcat ou Jetty, selon la configuration de l'application.

## Créer une API Spring Boot

1.  Commencez par créer un nouveau projet Spring Boot en utilisant l'outil de votre choix (par exemple, Spring Initializr).

2.  Ajoutez les dépendances nécessaires pour la création d'une API RESTful, telles que *Spring Web*, *Spring Data JPA*, et éventuellement *Spring Security*.

3.  Créez une classe de contrôleur qui contiendra les méthodes pour répondre aux requêtes HTTP.

4.  Définissez les endpoints de votre API en utilisant les annotations **@RequestMapping**, **@GetMapping**, **@PostMapping**, **@PutMapping**, ou **@DeleteMapping** en fonction des opérations que vous souhaitez exposer.

5.  Implémentez la logique métier de votre API en utilisant les services et les repositories appropriés.

6.  Testez votre API en utilisant un outil tel que Postman pour vous assurer que les endpoints fonctionnent correctement.

7.  Déployez votre API sur un serveur pour qu'elle soit accessible à partir de clients externes.

## Ordre de développement d'une API Spring Boot

1.  *Modélisation des données :* Définissez les entités et les relations nécessaires pour votre API en utilisant des annotations JPA, et configurez votre base de données en utilisant Spring Data JPA.
    
2.  *Création d'une classe de service :* Écrivez une classe de service qui contient la logique métier de votre API, comme la création, la mise à jour et la suppression des entités. Les services peuvent utiliser des repositories pour accéder à la base de données.
    
3.  *Création d'une classe de contrôleur :* Écrivez une classe de contrôleur qui définit les endpoints de votre API en utilisant les annotations de Spring MVC. Les méthodes dans la classe de contrôleur peuvent appeler les méthodes dans la classe de service pour effectuer les opérations CRUD.
    
4.  *Test de l'API :* Utilisez des outils comme Postman pour tester l'API en appelant les endpoints et en vérifiant que les réponses sont correctes.
    
5.  *Sécurité :* Ajoutez une couche de sécurité à votre API en utilisant Spring Security pour gérer l'authentification et l'autorisation.
    
6.  *Validation :* Ajoutez des validations pour les requêtes entrantes pour garantir que les données sont conformes aux attentes et éviter les erreurs de traitement.
    
7.  *Documentation :* Documentez votre API en utilisant des outils comme Swagger pour générer automatiquement la documentation de l'API.
    
8.  *Déploiement :* Déployez votre API sur un serveur de production en utilisant des outils comme Docker pour faciliter la mise en production et la gestion des mises à jour.

## Modélisation des données d'une API Spring Boot Java

Pour modéliser les données d'une API Spring Boot Java, vous pouvez utiliser des classes Java qui représentent les entités de votre application. Les classes Java sont utilisées pour créer des objets qui représentent des données dans votre application.

Voici un exemple de classe Java pour modéliser une entité "Utilisateur" :

    @Entity
	@Table(name = "users")
	public class User {
 
	    @Id
	    @GeneratedValue(strategy = GenerationType.IDENTITY)
	    private Long id;
	 
	    @Column(name = "username", unique = true)
	    private String username;
	 
	    @Column(name = "password")
	    private String password;
	 
	    @Column(name = "enabled")
	    private boolean enabled;
	 
	    @ManyToMany(fetch = FetchType.LAZY)
	    @JoinTable(name = "user_roles",
	            joinColumns = @JoinColumn(name = "user_id"),
	            inverseJoinColumns = @JoinColumn(name = "role_id"))
	    private Set<Role> roles = new HashSet<>();
	 
	    // getters and setters
	}

Dans cet exemple, la classe User est annotée avec `@Entity` et `@Table(name = "users")` pour indiquer qu'elle est une entité et qu'elle doit être mappée à une table de base de données nommée "users". Les champs de la classe sont annotés avec `@Column` pour indiquer comment ils doivent être mappés à des colonnes dans la table de la base de données.

Le champ `id` est annoté avec `@Id` pour indiquer que c'est la clé primaire de l'entité. La stratégie de génération de la clé primaire est spécifiée avec `@GeneratedValue(strategy = GenerationType.IDENTITY)`.

Le champ `roles` est annoté avec `@ManyToMany` pour indiquer qu'il y a une relation many-to-many entre les utilisateurs et les rôles. La configuration de cette relation est spécifiée avec `@JoinTable` et les champs `joinColumns` et `inverseJoinColumns`.

En utilisant des classes Java pour modéliser les entités de votre application, vous pouvez facilement les utiliser dans votre code pour interagir avec la base de données via une couche d'accès aux données, comme JPA.

## Création de notre interface Repository

Voici un exemple de l'interface `UserRepository` utilisant Spring Data JPA pour effectuer des opérations CRUD (Create, Read, Update, Delete) sur une entité `User` :

    @Repository
	public interface UserRepository extends JpaRepository<User, Long> {
	 
	    User findByUsername(String username);
	 
	    List<User> findAllByOrderByUsernameAsc();
	 
	    List<User> findByUsernameContainingIgnoreCaseOrderByUsernameAsc(String username);
	}

Explications :

-   `@Repository` est une annotation Spring qui indique que cette interface est un composant qui gère l'accès aux données, et permet notamment l'injection de dépendances à travers `@Autowired`.
-   `User` est l'entité sur laquelle la classe `UserRepository` va effectuer des opérations CRUD. `Long` est le type de l'identifiant de l'entité.
-   `JpaRepository` est une interface fournie par Spring Data JPA qui définit les méthodes de base pour effectuer des opérations CRUD sur une entité. Ici, on étend `JpaRepository<User, Long>` pour définir un repository pour l'entité `User`.
-   `findByUsername` est une méthode définie dans l'interface `UserRepository` qui permet de rechercher un utilisateur par son nom d'utilisateur. Cette méthode est basée sur une convention de nommage de Spring Data JPA qui génère automatiquement la requête SQL correspondante à partir du nom de la méthode.
-   `findAllByOrderByUsernameAsc` est une méthode définie dans l'interface `UserRepository` qui permet de récupérer tous les utilisateurs triés par ordre alphabétique croissant sur le nom d'utilisateur.
-   `findByUsernameContainingIgnoreCaseOrderByUsernameAsc` est une méthode définie dans l'interface `UserRepository` qui permet de récupérer tous les utilisateurs dont le nom d'utilisateur contient une chaîne de caractères donnée, sans tenir compte de la casse, triés par ordre alphabétique croissant sur le nom d'utilisateur.

## Création d'un service Spring Boot

Créez une classe Java dans votre projet Spring Boot avec le nom de votre choix. Dans votre classe de service, injectez une instance de l'interface `UserRepository` pour effectuer des opérations sur la base de données. Implémentez des méthodes pour effectuer des opérations sur les utilisateurs en utilisant l'instance `userRepository` injectée.

    @Service
	public class UserService {
 
	    @Autowired
	    private UserRepository userRepository;
 
	    public User save(User user) {
	        return userRepository.save(user);
	    }
	 
	    public User findById(Long id) {
	        return userRepository.findById(id).orElse(null);
	    }
	 
	    public User findByUsername(String username) {
	        return userRepository.findByUsername(username);
	    }
	}

