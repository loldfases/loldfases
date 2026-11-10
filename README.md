
//FUTURAS MEJORAS;
// Poder cambiar el arma en mitad de un combate, pero en ese turno te pega el enemigo mientras la cambias
//Opcion de Esquivar, aumenta un 10+ en esquivar un ataque
// Poner la opcion de avanzar 



//Bolsa con pociones para curarte
Subproceso Bolsa_con_pociones ( Bolsa_pociones Por Referencia, pociones Por Referencia) 
	
FinSubProceso

//COMBATE SubProceso Batalla_Terminada <- Combate ( Nombre Por Referencia,Mini_enemigos Por Referencia, nivel Por Referencia, vida_Guerrero Por Referencia , XP Por Referencia)

//Definir danio_Guerrero Como Entero;
//Ponerle primero la vida a los enemigos y las Stats del personaje antes de hacer Esto.
//FinSubProceso

//ENEMIGO PEQUEÑO ALEATORIO (No hay Jefes) 
SubProceso Enemigo <- Aleatorio_Enemigo_mini(enemigo_aleatorio Por Valor,Mini_enemigos Por Referencia,indice_enemigo Por Referencia,vida_enemigo Por Referencia,indice_vida_enemigo Por Referencia)

	//Enemigos con su vida y daño (Aun no tienen puesto la vida y el daño)
	//BIOMA LLANURA;
Definir goblins Como Caracter; 				 Definir vida_goblins Como Entero; vida_goblins <- 30;
Definir esqueleto_caballero Como Caracter;	 Definir vida_esqueleto_caballero Como Entero; vida_esqueleto_caballero <- 20; //Pero tiene mucho daño
Definir esqueleto_arquero Como Caracter; 	 Definir vida_esqueleto_arquero Como Entero; vida_esqueleto_arquero <- 35; //Tiene mas probabilidad de esquivar por ser a distancia 
Definir orcos Como Caracter; 				 Definir vida_orcos Como Entero; vida_orcos <- 40;  
Definir slime Como Caracter; 				 Definir vida_slime Como Entero; vida_slime <- 20;
Definir gremlin Como Caracter; 				 Definir vida_gremlin Como Entero; vida_gremlin <- 20; //Van minimo 2 gremlins juntos
Definir caballero_zombi Como Caracter; 		 Definir vida_caballero_zombi Como Entero; vida_caballero_zombi <- 50;
Definir zombi_mutado Como Caracter; 			 Definir vida_zombi_mutado Como Entero; 
Definir gigante_bebe Como Caracter; 			 Definir vida_gigante_bebe Como Entero;
Definir golem_bebe Como Caracter; 			 Definir vida_golem_bebe Como Entero;
Definir bruja Como Caracter; 				 Definir vida_bruja Como Entero;
Definir bandidos Como Caracter; 				 Definir vida_bandidos Como Entero;

//BIOMA ----




//Para invocar un enemigo aleatorio.
//  enemigo_aleatorio <- azar(10) + 1;

goblins <- "goblins";
esqueleto_caballero <- "esqueleto caballero";
esqueleto_arquero <- "esqueleto arquero";
orcos <- "orco";
slime <- "slime";
gremlin <- "gremlin";
caballero_zombi <- "caballero zombi";
zombi_mutado <- "zombi mutado";
gigante_bebe <- "gigante bebe";
golem_bebe <- "golem bebe";
bruja <- "bruja";
bandidos <- "bandidos";
Escribir "";
Escribir " TE APARECIÓ: ";

Segun enemigo_aleatorio Hacer
	
	1:
		Escribir " ------------------------------";
		Escribir " -------esqueleto caballero----"; 
		Escribir " ------------------------------";
		Mini_enemigos[indice_enemigo] <-esqueleto_caballero;
		indice_enemigo <- indice_enemigo +1;
	2:
		Escribir " ---------------------";
		Escribir " -----gigante bebe----"; 
		Escribir " ---------------------";
		Mini_enemigos[indice_enemigo] <- gigante_bebe;
		indice_enemigo <- indice_enemigo +1;
	3:
		//Este zombi mutado significa que al morir explota haciendo daño
		Escribir " --------------------";
		Escribir " ----zombi mutado----"; 
		Escribir " --------------------";
		Mini_enemigos[indice_enemigo] <- zombi_mutado;
		indice_enemigo <- indice_enemigo +1;
	4:
		Escribir " -------------------------";
		Escribir " ----esqueleto arquero----"; 
		Escribir " -------------------------";
		Mini_enemigos[indice_enemigo] <- esqueleto_arquero;
		indice_enemigo <- indice_enemigo +1;
	5:
		//Ponerle que tenga probabilidad de envenenar/echizar de alguna manera
		Escribir " --------------";
		Escribir " -----bruja----"; 
		Escribir " --------------";
		Mini_enemigos[indice_enemigo] <- bruja;
		indice_enemigo <- indice_enemigo +1;
	6:
		//Ponerle que pueden salir entre 1-3 bandidos
		Escribir " ----------------";
		Escribir " ----bandidos----"; 
		Escribir " ----------------";
		Mini_enemigos[indice_enemigo] <- bandidos;
		indice_enemigo <- indice_enemigo +1;
	7:
		Escribir " -------------------------";
		Escribir " ------caballero_zombi----"; 
		Escribir " -------------------------";
		Mini_enemigos[indice_enemigo] <- caballero_zombi;
		indice_enemigo <- indice_enemigo +1;
	8:
		//Que salgan 2-3 gremlins
		Escribir " ----------------";
		Escribir " -----gremlin----"; 
		Escribir " ----------------";
		Mini_enemigos[indice_enemigo] <- gremlin;
		indice_enemigo <- indice_enemigo +1;
	9:
		Escribir " ----------------";
		Escribir " -----goblins----"; 
		Escribir " ----------------";
		Mini_enemigos[indice_enemigo] <- goblins;
		indice_enemigo <- indice_enemigo +1;
		
	10:
		Escribir " --------------------";
		Escribir " ------golem_bebe----"; 
		Escribir " --------------------";
		Mini_enemigos[indice_enemigo] <- golem_bebe;
		indice_enemigo <- indice_enemigo +1;
		
		
		
FinSegun
FinSubProceso

//JEFE ALEATORIO //SubProceso BOSS <- Aleatorio_Enemigo_BOSS()

//FinSubProceso

//COFRES 
SubProceso Objeto_para_mochila <- Cofre (Huecos Por referencia, mochila Por Referencia, arma_aleatoria Por Valor)

// ---Armas---
Definir espada, espada_rota, espada_madera,espada_diamante Como caracter; //Espadas
Definir arco_madera, arco_metal,arco_roto Como caracter; //Arcos
espada <- "espada";
espada_rota <- "espada rota";
espada_madera <- "espada de madera";
espada_diamante <- "espada de diamante";
arco_madera <- "arco de madera";
arco_metal <- "arco de metal";
arco_roto <- "arco roto";
//Para ver el conteenido de la mochila solamente.
Definir indice_mochila Como Entero;
Definir Huecos_max Como Entero;
Definir opciones_jugador Como Caracter;
Escribir "";
Escribir " BUENA SUERTE UwU";
Escribir "";
si Huecos <= 10 Entonces
	Segun  arma_aleatoria Hacer
		1:
			Escribir " ---------------------";
			Escribir " ----espada de madera----"; 
			Escribir " ---------------------";
			mochila[Huecos] <- espada_madera;
			Escribir " Se guardo en tu mochila un --espada_madera--  normalito";
			Huecos <- Huecos +1;
		2:
			Escribir " ---------------------";
			Escribir " ------arco de madera------"; 
			Escribir " ---------------------";
			mochila[Huecos] <- arco_madera;
			Escribir " Se guardo en tu mochila un --arco_madera--  normalito";
			Huecos <- Huecos +1;
		3:
			Escribir " --------------";
			Escribir " ----espada----"; 
			Escribir " --------------";
			mochila[Huecos] <- espada;
			Escribir " Se guardo en tu mochila un --espada--  Una espada normal y corriente... literal";
			Huecos <- Huecos +1;
		4:
			Escribir " Wow, NADA";
		5:
			Escribir " ---------------------";
			Escribir " ----espada rota------"; 
			Escribir " ---------------------";
			mochila[Huecos] <- espada_rota;
			Escribir " Se guardo en tu mochila un --espada_rota-- Sigue con esa suerte y no duraras mucho!!";
			Huecos <- Huecos +1;
		6:
			Escribir " Wow, NADA";
		7:
			Escribir " -----------------";
			Escribir " ----arco roto----"; 
			Escribir " -----------------";
			mochila[Huecos] <- arco_roto;
			Escribir " Se guardo en tu mochila un --arco_roto--  Increible suerte!! GL"; 
			Huecos <- Huecos +1;
		8:
			Escribir " --------------------------";
			Escribir " -----espada de diamante------"; 
			Escribir " --------------------------";
			mochila[Huecos] <- espada_diamante;
			Escribir " Se guardo en tu mochila un --espada_diamante--  La mejor espada disponible!! ¿que flor en el culo tienes?";
			Huecos <- Huecos +1;
		9:
			//Aqui que te quite vida
			
		10:
			Escribir " ------------------";
			Escribir " ----arco de metal----"; 
			Escribir " ------------------";
			mochila[Huecos] <- arco_metal;
			Escribir " Se guardo en tu mochila un --arco_metal--  El mejor arco disponible!!";
			Huecos <- Huecos +1;
			
			//Aniadir futuras armas y cosas!!!!
			
		11:
			Escribir " Wow, NADA";
			
		12:
			//Aqui que te quite vida
			
			
	FinSegun
SiNo
	Escribir " No tienes mas espacio My G";
FinSi
Escribir "";
Escribir "";

Escribir " Quieres ver tu mochila? Escribe"," si ", "para ver";
Leer opciones_jugador;
si opciones_jugador = "si" o opciones_jugador = "Si" Entonces
	
	
	Escribir "";
	Escribir "   --- CONTENIDO DE LA MOCHILA ---";
	
	
	// Para mostrar el contenido:
	Para indice_mochila <- 1 Hasta Huecos - 1 Con Paso 1 Hacer
		Escribir "Hueco ", indice_mochila, " -> ", mochila[indice_mochila];
	FinPara
FinSi
Esperar 200 Milisegundos;

// Llamar al Subproceso de los cofres:   Objeto_para_mochila <- Cofre (indice, mochila, arma_aleatoria);
FinSubProceso


//Para hacer el efecto al texto
SubProceso Efecto_texto ( Mensaje Por Valor)
	//  Efecto_texto(  );
	
	Definir  indice_mensaje Como Entero;
	
	Para indice_mensaje <- 0 Hasta Longitud(mensaje)-1 Hacer
		Escribir Sin Saltar Subcadena(Mensaje, indice_mensaje,indice_mensaje);
		Esperar 40 Milisegundos;
		
	FinPara
	
	Escribir "";
FinSubProceso

















Proceso Slayer_WHAT //---Combate--- definir Batalla_Terminada Como Entero;
	
	// ---Opciones del Jugador---
	Definir opciones_jugador Como Caracter;
	Definir mensaje Como Caracter;
	
	// ---Guerrero---
	Dimensionar mochila[10];
	Definir Huecos Como Entero; Huecos <- 1; //Huecos de la mochila
	Definir mochila Como Caracter;
	Definir Objeto_para_mochila Como Entero; //Subproceso de cofres
	
	dimension Bolsa_pociones[10];
	Definir Bolsa_pociones como Entero;
	Definir pociones Como Entero; pociones <- 1; 
	
	Definir Nombre Como Caracter;
	Definir vidaMax Como Entero; vidaMax <- 100;
	Definir nivel Como Entero; Nivel <- 1; //Subirle el daño en +2 y la vida en +5
	Definir XP Como Entero; xp <- 0;//100xp de maximo, Subirle nivel +1 cuando llegue al maximo
	Definir vida_Guerrero Como Entero; vida_Guerrero <-100;
	
	// ---Armas---
	Definir Punios Como Entero;
	Punios <- 2;
	Definir espada, espada_rota, espada_madera,espada_diamante Como Entero; //Espadas
	espada <- 10;
	espada_rota <- 5;
	espada_madera <- 8;
	espada_diamante <- 30;
	Definir arco_madera, arco_metal,arco_roto Como Entero; //Arcos
	arco_madera <- 10;
	arco_metal <- 22;
	arco_roto <- 4;
	Definir arma_aleatoria Como Entero; //Cofre
	
	// ---Enemigos---
	// --Mini Enemigos--
	Dimension Mini_enemigos[60];
	Dimension vida_enemigo[60];
	Definir vida_enemigo Como Entero;
	Definir indice_vida_enemigo Como Entero;
	Definir indice_enemigo Como Entero; indice_enemigo <- 0; 
	
	Definir Mini_enemigos como Caracter;
	Definir Enemigo Como Caracter; // Enemigo aleatorio del SubProceso 
	Definir enemigo_aleatorio Como Entero;
	Definir goblins,vida_goblins Como Entero;
	Definir esqueleto_caballero,vida_esqueleto_caballero Como Entero;
	Definir esqueleto_arquero,vida_esqueleto_arquero Como Entero;
	
	// ---JEFES---
	Dimensionar Jefes[50];
	Definir boss_aleatorio Como Entero;
	definir Minotauro, vida_Minotauro Como Entero;
	
	
	
	//Empieza partida
	
	Efecto_texto("                -- BIENVENIDO A SLAYER_WHAT ---");
	Escribir "";
	Esperar 400 Milisegundos;
	Efecto_texto( " -- Demomento el juego esta en desarrollo pero espero que disfrutes del poco contenido que tiene uWu --" ) ;
	Esperar 400 Milisegundos;
	
	Escribir "";
	Escribir "";
	Efecto_texto(" Antes de empezar tu aventura lo PRIMERO DE TODO y LO MAS IMPORTANTE ES:"  );
	Esperar 300 Milisegundos;
	Escribir "";
	Efecto_texto(" El nombre de tu personaje porsupuesto");
	Leer Nombre;
	Escribir "";
	
	Escribir " BIENVENIDO ", Nombre , " ha esta nueva aventura.";
	Efecto_texto( " Te ire diciendo lo que puedes hace y lo que no VALE??? --- Si ya sabes jugar escribe --VeteranPlayer--");
	Leer opciones_jugador;
	
	// ----TUTORIAL----
	//Si dice que NO es nuevo se salta el tutorial
	si opciones_jugador <> "VeteranPlayer" Entonces
		si opciones_jugador = "si" o opciones_jugador = "Si" o opciones_jugador = "VALLE" o opciones_jugador = "Vale" o opciones_jugador = "vale" o opciones_jugador = "Entendido" o opciones_jugador = "entendido" o opciones_jugador = "Enefecto" Entonces
			Escribir "";
			Efecto_texto(" GUUD BOYYYY, ahora empezaré dandote una breve introducción sobre lo que vas a jugar");
			Efecto_texto(" No vas a tener que leer mucho DONT WORRY");
			Efecto_texto(" Este juego va sobre ERECCIONES");
			Efecto_texto(" My Bad, MY BAD");
			Efecto_texto(" Quise decir ELECCIONES :v     Simple verdad?");
			Efecto_texto(" En el camino encontraras: cofres, enemigos, rutas nuevas, ETC... ");
			Efecto_texto(" Y pues eso es todo, nada mas que explicarte, ya lo veras por ti mismo lo que tiene este juego, BUENA SUERTE  <; ");
			Escribir "";
			
		SiNo
			Escribir "TU VES GRACIOSO DECIRME ",opciones_jugador, " EN VEZ DE -- SI JEFE -- ES GRACIOSO??";
			Efecto_texto(" PUES AHORA TE LO VOY A PONER EN MODO DIFICIL, JODETE");
			Escribir "";
			Efecto_texto(" Es fake, no te pongas a llorar");
			Efecto_texto(" Ahora empezaré dandote una breve introducción sobre lo que vas a jugar");
			Efecto_texto(" No vas a tener que leer mucho DONT WORRY");
			Efecto_texto(" Este juego va sobre ERECCIONES");
			Efecto_texto(" My Bad, MY BAD");
			Efecto_texto(" Quise decir ELECCIONES :v     Simple verdad?");
			Efecto_texto(" En el camino encontraras: cofres, enemigos, rutas nuevas, ETC... ");
			Efecto_texto(" Y pues eso es todo, nada mas que explicarte, ya lo veras por ti mismo lo que tiene este juego, BUENA SUERTE  <; ");
			Escribir "";
			
		FinSi
		
	FinSi
	
	// ----INICIO DEL JUEGO----
	Escribir " ----START GAME---- "; 
	Escribir "";
	Escribir "";
	Escribir " ---------------------";
	Escribir " ----RUTA 1: PRADO----"; 
	Escribir " ---------------------";
	Escribir "";
	Escribir " Estás en un prado muy llano, lleno de hierva muy alta y mientras caminabas te encontraste un cofre con bastante mala pinta";
	Escribir " Quieres abrir el cofre? si o no ";
	
	// ----RUTA 1: PRADO----
	Leer opciones_jugador;
	si opciones_jugador = "si" o opciones_jugador = "Si" Entonces
		
		Escribir "";
		Escribir " Veamos que te toco: (casi todo este juego es gacha)";
		arma_aleatoria <- Azar(10) + 1;
		Objeto_para_mochila <- Cofre (Huecos, mochila, arma_aleatoria);
		Escribir "";
		
	SiNo
		Escribir " Bueno, pues te quedas sin saber que habia en el cofre";
		Escribir " Ahora te toca ir a punio limpio campeon  -_- ";
	FinSi
	
	Escribir " Continuemos con la aventura,";
	Escribir " A ESPERA, que no te dije cual es tu objetivo en esta aventura";
	Escribir " Es muy simple";
	Escribir " Sobrevivir a esta locura de mundo";
	Escribir " Si, como lo estas leyendo, ese es tu objeivo porque te puede pasar CUALQUIER cosa que no te esperes en CUALQUIER MOMENTO";
	Escribir " Eso es todo, sigamos";
	Escribir "   Presiona una tecla para continuar ...";
	Esperar Tecla;
	
	Escribir "";
	Escribir " Avanzas mas adelante del prado y como no ves nada te chocas con algo inusual,";
	Escribir " Algo que no parece ser un cofre";
	Escribir " ES TU PRIMER ENEMIGO";
	
	Escribir "";
	Escribir "========================================================";
	Escribir "                   ? SLAYER_WHAT ?                      ";
	Escribir "		     		               A PELEAR                     ";
	Escribir "========================================================";
	Escribir "";
	Escribir "   Presiona una tecla para continuar ...";
	Esperar Tecla;
	Limpiar Pantalla;
	
	//Enemigo aleatorio
	enemigo_aleatorio <- azar(10) + 1;
	Enemigo <- Aleatorio_Enemigo_mini (enemigo_aleatorio,Mini_enemigos,indice_enemigo,vida_enemigo,indice_vida_enemigo);
	
	Escribir "";
	Escribir "=====================================================";
	Escribir "=                                                  =";
	Escribir "=      ¡¡ ¡HA APARECIDO UN NUEVO ENEMIGO! !!       =";
	Escribir "=                                                  =";
	Escribir "=                   ",   Mayusculas(Mini_enemigos[indice_enemigo -1 ]), "                     =";
	Escribir "=                                                  =";
	Escribir "=====================================================";
	Escribir "";
	Escribir "";
	Escribir "";
	Escribir "";
	
	//Poner alado del ESTADO DEL HERO el HESTADO DEL ENEMIGO
	//-------------------------------------------------------
	Escribir "";
    Escribir "=================================="; 
    Escribir "          ESTADO DEL HEROE";
    Escribir "==================================";
    Escribir " NIVEL: ",nivel;
    Escribir " VIDA: ",vida_Guerrero,"/",vidaMax;
    Escribir " EXPERIENCIA: ",xp,"/100";
    Escribir " DANIO: ",10;
    Escribir " POCIONES: ",pociones;
    Escribir "==================================";
	Escribir "     Presiona una tecla para comenzar el combate...";
	Esperar Tecla;
	
	//Batalla_Terminada <- Combate (Nombre,Mini_enemigos, nivel, vida_Guerrero , XP);
	
	//Hacer un subproceso que restaure la vida de los enemigos
	//Ponerle la vida, daño y probabilidad de esquivar a los enemigos/Jugador para continuar.
	//-------------------------------------------------------------------------------------------
FinProceso
