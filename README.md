//COMBATE
SubProceso Batalla_Terminada <- Combate ( Nombre Por Referencia,Mini_enemigos Por Referencia, nivel Por Referencia, vida_Guerrero Por Referencia , XP Por Referencia)
	
	Definir danio_Guerrero Como Entero;
	
FinSubProceso




//ENEMIGO PEQUEÑO ALEATORIO (No hay Jefes)
SubProceso Enemigo <- Aleatorio_Enemigo_mini(enemigo_aleatorio Por Valor,Mini_enemigos Por Referencia,indice_enemigo Por Referencia  )
	
	//Enemigos con su vida y daño (Aun no tienen puesto la vida y el daño)
	Definir goblins Como Caracter; 				 Definir vida_goblins Como Entero;
	Definir esqueleto_caballero Como Caracter;	 Definir vida_esqueleto_caballero Como Entero;
	Definir esqueleto_arquero Como Caracter; 	 Definir vida_esqueleto_arquero Como Entero;
	Definir orcos Como Caracter; 				 Definir vida_orcos Como Entero;
	Definir slime Como Caracter; 				 Definir vida_slime Como Entero;
	Definir gremlin Como Caracter; 				 Definir vida_gremlin Como Entero;
	Definir caballero_zombi Como Caracter; 		 Definir vida_caballero_zombi Como Entero;
	Definir zombi_mutado Como Caracter; 			 Definir vida_zombi_mutado Como Entero;
	Definir gigante_bebe Como Caracter; 			 Definir vida_gigante_bebe Como Entero;
	Definir golem_bebe Como Caracter; 			 Definir vida_golem_bebe Como Entero;
	Definir bruja Como Caracter; 				 Definir vida_bruja Como Entero;
	Definir bandidos Como Caracter; 				 Definir vida_bandidos Como Entero;
	
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
			//Que salgan 1-3 gremlins
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
			11:
			
			
		
	FinSegun
	
	
FinSubProceso




//JEFE ALEATORIO
//SubProceso BOSS <- Aleatorio_Enemigo_BOSS()
	
	
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
	
	
	// Llamar al Subproceso de los cofres:   Objeto_para_mochila <- Cofre (indice, mochila, arma_aleatoria);
FinSubProceso





Proceso Slayer_WHAT
	//---Combate---
	definir Batalla_Terminada Como Entero;
	
	// ---Opciones del Jugador---
	Definir opciones_jugador Como Caracter;
	
	// ---Guerrero---
	Definir Objeto_para_mochila Como Entero; //Subproceso de cofres
	Dimensionar mochila[10];
	Definir Huecos Como Entero; //Huecos de la mochila
	Huecos <- 1;
	Definir mochila Como Caracter;
	Definir Nombre Como Caracter;
	Definir nivel Como Entero; //Subirle el daño en +2 y la vida en +5
	Definir XP Como Entero; //100xp de maximo, Subirle nivel +1 cuando llegue al maximo
	Definir danio_Guerrero Como Entero;
	Definir vida_Guerrero Como Entero;
	
	// ---Armas---
	Definir Punios Como Entero;
	Punios <- 2;
	Definir espada, espada_rota, espada_madera,espada_diamante Como Entero; //Espadas
	espada <- 10;
	espada_rota <- 3;
	espada_madera <- 5;
	espada_diamante <- 25;
	Definir arco_madera, arco_metal,arco_roto Como Entero; //Arcos
	arco_madera <- 5;
	arco_metal <- 17;
	arco_roto <- 2;
	Definir arma_aleatoria Como Entero; //Cofre
	
	// ---Enemigos---
	// ---Mini Enemigos---
	Dimensionar Mini_enemigos[50];
	Definir indice_enemigo Como Entero;
	indice_enemigo <- 0;
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
	vida_Guerrero <-100;
	Escribir "       -- BIENVENIDO A --SLAYER_WHAT--";
	Escribir " -- Demomento el juego esta en desarrollo pero espero que disfrutes del poco contenido que tiene uWu --";
	Escribir "";
	Escribir "";
	Escribir " Antes de empezar tu aventura lo PRIMERO DE TODO y LO MAS IMPORTANTE ES:";
	Escribir "";
	Escribir " El nombre de tu personaje porsupuesto";
	Leer Nombre;
	
	Escribir " BIENVENIDO ", Nombre , " ha esta nueva aventura.";
	Escribir " Te ire diciendo lo que puedes hace y lo que no VALE??? --- Si ya sabes jugar escribe --VeteranPlayer--";
	Leer opciones_jugador;
	
	// ----TUTORIAL----
	//Si dice que NO es nuevo se salta el tutorial
	si opciones_jugador <> "VeteranPlayer" Entonces
		si opciones_jugador = "si" o opciones_jugador = "Si" o opciones_jugador = "VALLE" o opciones_jugador = "Vale" o opciones_jugador = "vale" o opciones_jugador = "Entendido" o opciones_jugador = "entendido" o opciones_jugador = "Enefecto" Entonces
			Escribir "";
			Escribir " GUUD BOYYYY, ahora empezare dandote una breve introduccion sobre lo que vas a jugar";
			Escribir " No vas a tener que leer mucho DONT WORRY";
			Escribir " Este juego va sobre ERECCIONES";
			Escribir " My Bad, MY BAD";
			Escribir " Quise decir ELECCIONES :v     Simple verdad?";
			Escribir " En el camino encontraras: cofres, enemigos, rutas nuevas, ETC... ";
			Escribir " Y pues eso es todo, nada mas que explicarte, ya lo veras por ti mismo lo que tiene este juego, BUENA SUERTE  <; ";
			Escribir "";
			
		SiNo
			Escribir " TU VES GRACIOSO DECIRME ",opciones_jugador, " EN VEZ DE -- SI JEFE -- ES GRACIOSO??";
			Escribir " PUES AHORA TE LO VOY A PONER EN MODO DIFICIL, JODETE";
			Escribir "";
			Escribir " Es fake, no te pongas a llorar";
			Escribir " Ahora empezare dandote una breve introduccion sobre lo que vas a jugar";
			Escribir " No vas a tener que leer mucho DONT WORRY";
			Escribir " Este juego va sobre ERECCIONES";
			Escribir " My Bad, MY BAD";
			Escribir " Quise decir ELECCIONES :v     Simple verdad?";
			Escribir " En el camino encontraras: cofres, enemigos, rutas nuevas, ETC... ";
			Escribir " Y pues eso es todo, nada mas que explicarte, ya lo veras por ti mismo lo que tiene este juego, BUENA SUERTE  <; ";
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
	Escribir " Estas en un prado muy llano lleno de hierva muy alta y mientras caminabas te encontraste un cofre con bastante mala pinta";
	Escribir " Quieres abrir el cofre? si o no";
	
	// ----RUTA 1: PRADO----
	Leer opciones_jugador;
	si opciones_jugador = "si" o opciones_jugador = "Si" Entonces
		
		Escribir "";
		Escribir " Veamos que primera arma te toco: (La casi todo este juego es gacha)";
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
	Enemigo <- Aleatorio_Enemigo_mini (enemigo_aleatorio,Mini_enemigos,indice_enemigo);
	
	Escribir "";
	Escribir "=====================================================";
	Escribir "=                                                  =";
	Escribir "=      ¡¡ ¡HA APARECIDO UN NUEVO ENEMIGO! !!       =";
	Escribir "=                                                  =";
	Escribir "=               ",Mayusculas(Mini_enemigos[indice_enemigo -1]), "                =";
	Escribir "=                                                  =";
	Escribir "=====================================================";
	Escribir "";
	Escribir "     Presiona una tecla para comenzar el combate...";
	Esperar Tecla;
	
	Batalla_Terminada <- Combate (Nombre,Mini_enemigos, nivel, vida_Guerrero , XP);
	
	//Hacer un subproceso que restaure la vida de los enemigos
	//Ponerle la vida, daño y probabilidad de esquivar a los enemigos/Jugador para continuar.
	//-------------------------------------------------------------------------------------------
	
	
	
FinProceso
