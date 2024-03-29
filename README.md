
# Doc-Spring-Boot
Bonnes pratiques Spring Boot de A à Z

# Sommaire
## Démarrage
- [Bien démarrer un projet Spring Boot](#bien-démarrer-un-projet-spring-boot)
- [Créer son premier projet Spring Boot](#créer-son-premier-projet-spring-boot)
- [Importer un projet Spring Boot sur Eclipse](#importer-un-projet-spring-boot-sur-eclipse)
- [Configurer Eclipse pour Maven et Spring Boot](#configurer-eclipse-pour-maven-et-spring-boot)
## Création
- [Créer une API Spring Boot](#créer-une-api-spring-boot)
- [Ordre de développement d'une API Spring Boot](#ordre-de-développement-dune-api-spring-boot)
- [Modélisation des données d'une API Spring Boot Java](#modélisation-des-données-dune-api-spring-boot-java)
- [Création de notre interface Repository](#création-de-notre-interface-repository)
- [Création d'un service Spring Boot](#création-dun-service-spring-boot)
- [Création d'un controller Spring Boot](#création-dun-controller-spring-boot)
- [Mise en place d'un système d'authentification](#mise-en-place-dun-système-dauthentification)
## Test
- [Mise en place de l'environnement de test Eclipse](#mise-en-place-de-lenvironnement-de-test-eclipse)
- [Installer Mockito dans un projet Spring Boot](#installer-mockito-dans-un-projet-spring-boot)
- [Tester une entité modèle Spring Boot](#tester-une-entité-modèle-spring-boot)
- [Tester une interface "Repository" Spring Boot](#tester-une-interface-repository-spring-boot)
- [Tester un service Spring Boot](#tester-un-service-spring-boot)
- [Tester un controller Spring Boot](#tester-un-controller-spring-boot)
- [Tester son authentification Spring Boot](#tester-son-authentification-spring-boot)
## Documentation
- [Mise en place du Swagger de l'API Spring Boot](#mise-en-place-du-swagger-de-lapi-spring-boot)
- [Bien commenter son code](#bien-commenter-son-code)
- [Mettre en place un système de Logging](#mettre-en-place-un-système-de-logging)

## Bien démarrer un projet Spring Boot

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

## Création d'un controller Spring Boot

Pour créer un controller Spring Boot pour les utilisateurs, vous pouvez suivre les étapes suivantes :

1.  Créez une classe UserController avec l'annotation **@RestController**.

	    @RestController
		public class UserController {

		}


2. Injectez le service d'utilisateur dans le contrôleur en utilisant l'annotation **@Autowired**.

		@RestController
		public class UserController {

		    @Autowired
		    private UserService userService;
		    
		}


3.  Créez une méthode pour récupérer tous les utilisateurs. Utilisez l'annotation **@GetMapping** avec le chemin de l'API pour cette méthode.

	    @RestController
		public class UserController {

		    @Autowired
		    private UserService userService;

		    @GetMapping("/users")
		    public List<User> getUsers() {
		        return userService.getUsers();
		    }
		}


4.  Créez une méthode pour récupérer un utilisateur par ID. Utilisez l'annotation **@GetMapping** avec le chemin de l'API et l'ID de l'utilisateur pour cette méthode.

	    @RestController
		public class UserController {

		    @Autowired
		    private UserService userService;

		    @GetMapping("/users/{userId}")
		    public User getUserById(@PathVariable Long userId) {
		        return userService.getUserById(userId);
		    }
		}


5.  Créez une méthode pour ajouter un nouvel utilisateur. Utilisez l'annotation **@PostMapping** avec le chemin de l'API pour cette méthode.

	    @RestController
		public class UserController {

		    @Autowired
		    private UserService userService;

		    @PostMapping("/users")
		    public User addUser(@RequestBody User user) {
		        return userService.addUser(user);
		    }
		}


6.  Créez une méthode pour mettre à jour un utilisateur existant. Utilisez l'annotation **@PutMapping** avec le chemin de l'API et l'ID de l'utilisateur pour cette méthode.

		@RestController
		public class UserController {

		    @Autowired
		    private UserService userService;

		    @PutMapping("/users/{userId}")
		    public User updateUser(@PathVariable Long userId, @RequestBody User user) {
		        return userService.updateUser(userId, user);
		    }
		}


7.  Créez une méthode pour supprimer un utilisateur existant. Utilisez l'annotation **@DeleteMapping** avec le chemin de l'API et l'ID de l'utilisateur pour cette méthode.

	    @RestController
		public class UserController {

		    @Autowired
		    private UserService userService;

		    @DeleteMapping("/users/{userId}")
		    public void deleteUser(@PathVariable Long userId) {
		        userService.deleteUser(userId);
		    }
		}


Ces méthodes appellent les méthodes correspondantes du service d'utilisateur pour récupérer, ajouter, mettre à jour ou supprimer les utilisateurs. Vous pouvez adapter ces méthodes pour répondre à vos besoins spécifiques.

## Mise en place d'un système d'authentification

1.  Créez un projet Spring Boot et ajoutez les dépendances nécessaires dans votre fichier pom.xml :

	    <dependency>
		   <groupId>org.springframework.boot</groupId>
		   <artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		<dependency>
		   <groupId>io.jsonwebtoken</groupId>
		   <artifactId>jjwt</artifactId>
		   <version>0.9.1</version>
		</dependency>

2.  Dans votre classe User pensez à ajouter les champs nécessaires pour stocker les informations d'identification, telles que l'adresse e-mail et le mot de passe.
3. Créez un contrôleur pour gérer les demandes d'authentification et de création de jetons. Dans ce contrôleur, créez une méthode pour générer un jeton JWT en utilisant la bibliothèque jjwt.

	    @RestController
		public class AuthController {
		   
		   @PostMapping("/login")
		   public String login(@RequestBody User user) {
		       // Vérifier si l'utilisateur existe dans la base de données
		       // Vérifier si le mot de passe est correct
		       
		       // Si l'utilisateur est authentifié, générer un jeton JWT et le retourner
		       String token = Jwts.builder()
		               .setSubject(user.getEmail())
		               .signWith(SignatureAlgorithm.HS256, "secret".getBytes())
		               .compact();
		       return token;
		   }
		}

4.  Ajoutez une annotation @EnableWebSecurity à votre classe principale pour activer la sécurité Web de Spring.

	    @SpringBootApplication
		@EnableWebSecurity
		public class MyApp {
		   public static void main(String[] args) {
		       SpringApplication.run(MyApp.class, args);
		   }
		}
5.  Créez une classe de configuration de sécurité qui définit les règles d'accès aux points de terminaison de l'API. Dans cette classe, créez une méthode pour authentifier les utilisateurs en utilisant le jeton JWT.

	    @Configuration
		@EnableWebSecurity
		public class SecurityConfig extends WebSecurityConfigurerAdapter {
		   
		   @Override
		   protected void configure(HttpSecurity http) throws Exception {
		       http.csrf().disable()
		               .authorizeRequests()
		               .antMatchers("/login").permitAll() // Tout le monde peut accéder à la page de login
		               .anyRequest().authenticated() // Les utilisateurs doivent être authentifiés pour accéder à toutes les autres pages
		               .and()
		               .sessionManagement().sessionCreationPolicy(SessionCreationPolicy.STATELESS);
		   }
		   
		   @Override
		   protected void configure(AuthenticationManagerBuilder auth) throws Exception {
		       auth.inMemoryAuthentication()
		               .withUser("admin")
		               .password("{noop}password") // Le mot de passe est "password"
		               .roles("ADMIN");
		   }
		}


## Mise en place de l'environnement de test Eclipse

Pour installer JUnit sur Eclipse, vous pouvez suivre les étapes suivantes:

1.  Ouvrez Eclipse.
2.  Cliquez sur le menu "Help".
3.  Sélectionnez "Eclipse Marketplace".
4.  Dans la barre de recherche, tapez "JUnit".
5.  Sélectionnez "JUnit" dans les résultats de la recherche.
6.  Cliquez sur le bouton "Install" pour lancer l'installation.
7.  Suivez les instructions à l'écran pour compléter l'installation.
8.  Une fois l'installation terminée, redémarrez Eclipse.

Après l'installation, vous pouvez commencer à utiliser JUnit pour écrire et exécuter des tests unitaires dans vos projets Eclipse.

## Installer Mockito dans un projet Spring Boot

Ajoutez la dépendance Mockito à votre fichier pom.xml. Si vous utilisez Gradle, ajoutez la dépendance à votre build.gradle.

		<!-- Pour Maven -->
		<dependency>
		   <groupId>org.mockito</groupId>
		   <artifactId>mockito-core</artifactId>
		   <scope>test</scope>
		</dependency>

## Tester une entité modèle Spring Boot

Pour tester une classe modèle Java Spring Boot, vous pouvez utiliser l'un des frameworks de test disponibles pour Spring Boot, tels que JUnit ou Mockito. Voici un exemple de test unitaire qui teste une classe modèle simple :

Supposons que nous avons une classe modèle simple nommée "User" avec des propriétés telles que "id", "nom" et "email". Nous pouvons écrire un test unitaire pour cette classe en utilisant JUnit et Mockito comme suit :

    import static org.junit.jupiter.api.Assertions.assertEquals;
	import org.junit.jupiter.api.Test;
	import org.mockito.InjectMocks;
	import org.mockito.junit.jupiter.MockitoExtension;

	@ExtendWith(MockitoExtension.class)
	public class UserTest {

	    @InjectMocks
	    private User user;

	    @Test
	    public void testUser() {
	        user.setId(1);
	        user.setName("John");
	        user.setEmail("john@gmail.com");

	        assertEquals(1, user.getId());
	        assertEquals("John", user.getName());
	        assertEquals("john@gmail.com", user.getEmail());
	    }
	}

Dans ce test unitaire, nous avons injecté la classe "User" en utilisant l'annotation "@InjectMocks" et nous avons écrit des assertions pour vérifier que les valeurs des propriétés sont correctement initialisées. En exécutant ce test, nous pouvons nous assurer que la classe modèle "User" fonctionne correctement.

Il est important de noter que cela ne teste que la logique de la classe modèle en elle-même, et pas nécessairement comment elle est utilisée dans le reste de l'application. Pour tester l'application dans son ensemble, il est recommandé d'utiliser des tests d'intégration et des tests fonctionnels qui testent la communication entre les différentes parties de l'application.

## Tester une interface "Repository" Spring Boot

1.  Créez une classe de test pour votre interface Repository. Vous pouvez utiliser JUnit pour écrire vos tests.
    
2.  Injectez l'interface Repository dans votre classe de test en utilisant l'annotation @Autowired.
    
3.  Écrivez un test pour vérifier que vous pouvez enregistrer un objet dans la base de données en utilisant la méthode save() de l'interface Repository. Pour cela, vous pouvez créer un objet de test, l'enregistrer dans la base de données en utilisant la méthode save(), puis vérifier que l'objet a bien été enregistré en le récupérant à partir de la base de données.
    
4.  Écrivez un test pour vérifier que vous pouvez récupérer un objet de la base de données en utilisant la méthode findById() de l'interface Repository. Pour cela, vous pouvez enregistrer un objet de test dans la base de données en utilisant la méthode save(), puis récupérer l'objet en utilisant la méthode findById() et vérifier que les propriétés de l'objet récupéré correspondent aux propriétés de l'objet de test.
    
5.  Écrivez des tests supplémentaires pour tester les autres méthodes de l'interface Repository que vous utilisez dans votre application.
    

Voici un exemple de classe de test pour une interface Repository :

    @RunWith(SpringRunner.class)
@SpringBootTest
public class UserRepositoryTest {

    @Autowired
    private UserRepository userRepository;

	    @Test
	    public void testSave() {
	        User user = new User("John", "Doe");
	        userRepository.save(user);
	        User savedUser = userRepository.findById(user.getId()).orElse(null);
	        assertNotNull(savedUser);
	        assertEquals(user.getFirstName(), savedUser.getFirstName());
	        assertEquals(user.getLastName(), savedUser.getLastName());
	    }

	    @Test
	    public void testFindById() {
	        User user = new User("John", "Doe");
	        userRepository.save(user);
	        User foundUser = userRepository.findById(user.getId()).orElse(null);
	        assertNotNull(foundUser);
	        assertEquals(user.getId(), foundUser.getId());
	        assertEquals(user.getFirstName(), foundUser.getFirstName());
	        assertEquals(user.getLastName(), foundUser.getLastName());
	    }
	}
Dans cet exemple, nous avons créé deux tests : testSave() et testFindById(). Le premier test vérifie que nous pouvons enregistrer un utilisateur dans la base de données en utilisant la méthode save(), et le deuxième test vérifie que nous pouvons récupérer un utilisateur à partir de la base de données en utilisant la méthode findById().

## Tester un service Spring Boot

Voici un exemple simple de test d'un service Spring Boot avec Mockito et JUnit :

    @RunWith(MockitoJUnitRunner.class)
	public class UserServiceTest {

	    @Mock
	    private UserRepository userRepository;

	    @InjectMocks
	    private UserService userService;

	    @Test
	    public void testGetUserById() {
	        // Créer un utilisateur simulé
	        User user = new User();
	        user.setId(1L);
	        user.setName("John Doe");
	        user.setEmail("johndoe@example.com");

	        // Simuler le comportement de UserRepository.findById()
	        when(userRepository.findById(1L)).thenReturn(Optional.of(user));

	        // Appeler la méthode getUserById() de UserService
	        User result = userService.getUserById(1L);

	        // Vérifier que la méthode UserRepository.findById() a été appelée
	        verify(userRepository, times(1)).findById(1L);

	        // Vérifier que la réponse renvoyée est correcte
	        assertEquals(user, result);
	    }
	}

Dans cet exemple, nous avons simulé le comportement de la méthode *UserRepository.findById()* en utilisant la fonction Mockito **"when"** et **"thenReturn"**. Nous avons ensuite appelé la méthode *getUserById()* de *UserService* et vérifié que *UserRepository.findById()* a été appelée une fois en utilisant la fonction Mockito **"verify"**. Enfin, nous avons vérifié que la réponse renvoyée est correcte en utilisant la fonction JUnit **"assertEquals"**.

## Tester un controller Spring Boot

Voici un exemple de test de la classe UserController en utilisant JUnit et Mockito :

    @RunWith(MockitoJUnitRunner.class)
	public class UserControllerTest {

	    @InjectMocks
	    private UserController userController;

	    @Mock
	    private UserService userService;

	    private MockMvc mockMvc;

	    @Before
	    public void setup() {
	        mockMvc = MockMvcBuilders.standaloneSetup(userController).build();
	    }

	    @Test
	    public void testGetUserById() throws Exception {
	        Long userId = 1L;
	        User user = new User(userId, "John", "Doe");

	        Mockito.when(userService.getUserById(userId)).thenReturn(user);

	        mockMvc.perform(get("/users/{id}", userId))
	                .andExpect(status().isOk())
	                .andExpect(jsonPath("$.id", is(userId.intValue())))
	                .andExpect(jsonPath("$.firstName", is(user.getFirstName())))
	                .andExpect(jsonPath("$.lastName", is(user.getLastName())));

	        Mockito.verify(userService, Mockito.times(1)).getUserById(userId);
	    }
	}

Dans cet exemple, nous avons utilisé Mockito pour simuler le comportement de la couche de service et nous avons utilisé MockMvc pour tester l'API REST. Nous avons créé un utilisateur simulé et avons simulé l'appel à la méthode `getUserById` du service en utilisant `Mockito.when`. Ensuite, nous avons appelé l'API REST en utilisant MockMvc et avons vérifié si la réponse contient les bonnes informations d'utilisateur en utilisant `andExpect`. Enfin, nous avons vérifié que la méthode `getUserById` du service a été appelée une fois en utilisant `Mockito.verify`.

## Tester son authentification Spring Boot

1.  Créez une classe de test et ajoutez les annotations nécessaires :

	    @RunWith(SpringRunner.class)
		@SpringBootTest(webEnvironment = WebEnvironment.RANDOM_PORT)
		@AutoConfigureMockMvc
		public class AuthControllerTest {
		   
		   @Autowired
		   private MockMvc mockMvc;
		   
		   //...
		}


2. Créez une méthode pour tester l'authentification avec des informations d'identification valides :

	    @Test
		public void testLoginWithValidCredentials() throws Exception {
		   User user = new User();
		   user.setEmail("john@example.com");
		   user.setPassword("password");
		   
		   mockMvc.perform(post("/login")
		           .contentType(MediaType.APPLICATION_JSON)
		           .content(new ObjectMapper().writeValueAsString(user)))
		           .andExpect(status().isOk())
		           .andExpect(jsonPath("$").isString());
		}
3.  Créez une méthode pour tester l'authentification avec des informations d'identification invalides :

	    @Test
		public void testLoginWithInvalidCredentials() throws Exception {
		   User user = new User();
		   user.setEmail("john@example.com");
		   user.setPassword("wrong_password");
		   
		   mockMvc.perform(post("/login")
		           .contentType(MediaType.APPLICATION_JSON)
		           .content(new ObjectMapper().writeValueAsString(user)))
		           .andExpect(status().isUnauthorized());
		}
4.  Ajoutez une méthode pour tester l'accès à un point de terminaison sécurisé avec un jeton JWT valide :

	    @Test
		public void testAccessSecureEndpointWithValidToken() throws Exception {
		   User user = new User();
		   user.setEmail("john@example.com");
		   user.setPassword("password");
		   
		   MvcResult result = mockMvc.perform(post("/login")
		           .contentType(MediaType.APPLICATION_JSON)
		           .content(new ObjectMapper().writeValueAsString(user)))
		           .andReturn();
		   
		   String token = result.getResponse().getContentAsString();
		   
		   mockMvc.perform(get("/secure")
		           .header("Authorization", "Bearer " + token))
		           .andExpect(status().isOk());
		}
5.  Ajoutez une méthode pour tester l'accès à un point de terminaison sécurisé sans jeton JWT :

	    @Test
		public void testAccessSecureEndpointWithoutToken() throws Exception {
		   mockMvc.perform(get("/secure"))
		           .andExpect(status().isUnauthorized());
		}
6.  Ajoutez une méthode pour tester l'accès à un point de terminaison sécurisé avec un jeton JWT invalide :

	    @Test
		public void testAccessSecureEndpointWithInvalidToken() throws Exception {
		   mockMvc.perform(get("/secure")
		           .header("Authorization", "Bearer invalid_token"))
		           .andExpect(status().isUnauthorized());
		}

Ces tests permettent de vérifier que le système d'authentification avec JWT fonctionne correctement en vérifiant la validité des informations d'identification et la protection des points de terminaison sécurisés.

## Mise en place du Swagger de l'API Spring Boot

our générer une documentation Swagger pour une application Spring Boot, vous pouvez suivre les étapes suivantes :

1.  Ajouter les dépendances Swagger à votre fichier pom.xml :

		 <dependency>
		    <groupId>io.springfox</groupId>
		    <artifactId>springfox-swagger2</artifactId>
		    <version>2.9.2</version>
		</dependency>
		<dependency>
		    <groupId>io.springfox</groupId>
		    <artifactId>springfox-swagger-ui</artifactId>
		    <version>2.9.2</version>
		</dependency>

2.  Ajouter l'annotation `@EnableSwagger2` à votre classe principale :

	    @SpringBootApplication
		@EnableSwagger2
		public class MyApp {
		    // ...
		}

3.  Configurer Swagger dans votre application. Vous pouvez créer une classe de configuration Swagger comme suit :

	    @Configuration
		@EnableSwagger2
		public class SwaggerConfig {
		    @Bean
		    public Docket api() {
		        return new Docket(DocumentationType.SWAGGER_2)
		                .select()
		                .apis(RequestHandlerSelectors.any())
		                .paths(PathSelectors.any())
		                .build();
		    }
		}

Dans cet exemple, nous avons configuré Swagger pour documenter toutes les API exposées par l'application.

4.  Exécuter votre application et accéder à l'interface Swagger UI en accédant à l'URL [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html). Vous devriez voir une interface utilisateur Swagger qui affiche la documentation de vos API.

Ces étapes devraient vous permettre de générer une documentation Swagger pour votre application Spring Boot. Vous pouvez également personnaliser la configuration Swagger pour répondre à vos besoins spécifiques en matière de documentation.

## Bien commenter son code

Voici un exemple de commentaire de méthode Java pour une application Spring Boot :

    /**
	 * Récupère tous les utilisateurs de l'application.
	 *
	 * @return la liste des utilisateurs
	 */
	@GetMapping("/users")
	public List<User> getAllUsers() {
	    return userService.getAllUsers();
	}

Dans cet exemple, nous avons commenté une méthode qui récupère tous les utilisateurs de l'application. Le commentaire commence par une description de la méthode, qui indique ce que fait la méthode (récupérer tous les utilisateurs).

Ensuite, nous avons précisé que la méthode renvoie une liste d'utilisateurs. Cela est utile pour les développeurs qui utilisent cette méthode, car ils peuvent voir immédiatement quel est le type de retour de la méthode.

Enfin, nous n'avons pas mentionné les détails d'implémentation de la méthode car cela n'est pas nécessaire dans ce commentaire. Cependant, il est toujours bon de commenter le code avec des informations utiles pour les développeurs qui pourraient utiliser la méthode.

## Mettre en place un système de Logging

1.  Ajoutez la dépendance SLF4J dans le fichier pom.xml de votre projet :

	    <dependency>
		    <groupId>org.slf4j</groupId>
		    <artifactId>slf4j-api</artifactId>
		    <version>1.7.25</version>
		</dependency>

2.  Ajoutez une implémentation de SLF4J, par exemple Logback, en ajoutant la dépendance dans votre fichier pom.xml :

	    <dependency>
		    <groupId>ch.qos.logback</groupId>
		    <artifactId>logback-classic</artifactId>
		    <version>1.2.3</version>
		</dependency>

3.  Créez un fichier de configuration pour Logback, par exemple "logback.xml" :

	    <configuration>
		    <appender name="FILE" class="ch.qos.logback.core.FileAppender">
		        <file>logs/myapp.log</file>
		        <encoder>
		            <pattern>%d %p [%c] - %m%n</pattern>
		        </encoder>
		    </appender>
		    <root level="INFO">
		        <appender-ref ref="FILE" />
		    </root>
		</configuration>

Dans cet exemple, le fichier de log sera créé dans le dossier "logs" à la racine du projet avec le nom "myapp.log". Le pattern spécifie le format de la ligne de log, qui inclut la date, le niveau de log, le nom de la classe et le message.

4.  Dans votre application, utilisez le logging SLF4J avec la classe LoggerFactory pour créer des objets de logger :

		import org.slf4j.Logger;
		import org.slf4j.LoggerFactory;

		public class MyApp {
		    private static final Logger logger = LoggerFactory.getLogger(MyApp.class);

		    public static void main(String[] args) {
		        logger.info("Hello, world!");
		    }
		}

Dans cet exemple, nous avons créé un objet de logger en appelant la méthode getLogger de la classe LoggerFactory en utilisant la classe MyApp comme argument. Nous avons ensuite utilisé l'objet de logger pour enregistrer un message d'information. Ce message sera écrit dans le fichier logs/myapp.log avec le format spécifié dans le fichier de configuration.
