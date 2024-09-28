# mySQL
create table somativa2.vinicola(
codvinicola bigint primary key not null,
nome_vinicola varchar(100) not null,
descricao_vinicola  text,
fone_vinicola varchar(15),
email_vinicola varchar(15),
codregiao bigint,
foreign key (codregiao) references somativa2.regiao(codregiao) 
);

create table somativa2.regiao(
codregiao bigint primary key not null,
nome_regiao varchar(100) not null,
descircao_regiao text
);

create table somativa2.vinho(
codvinho bigint primary key not null,
nome_vinho varchar(50) not null,
tipo_vinho varchar(30) not null,
ano_vinho int not null,
descricao_vinho text,
codvinicola bigint,
foreign key (codvinicola) references somativa2.vinicola(codvinicola)
);

insert into somativa2.regiao values
('0001','cambare','umida'
);

insert into somativa2.regiao values
('0002','rio açu','muito umida'
);

insert into somativa2.regiao values
('0003','matinhos','montanhosa'
);

insert into somativa2.regiao values
('0004','paris','elegante'
);

insert into somativa2.regiao values
('0005','umuarama','pantanosa'
);


insert into somativa2.vinho values
('01','campo largo','tinto','2005','ruim','001'
);

insert into somativa2.vinho values
('02','bordou','suave','2008','elegante','002'
);

insert into somativa2.vinho values
('03','hidromel','tinto','1020','açucarado','003'
);

insert into somativa2.vinho values
('04','divvino','tinto','2024','so para nobres','004'
);

insert into somativa2.vinho values
('05','celeste','suave','2009','bom e barato','005'
);
insert into somativa2.vinicola values
('001','região de cambare','umida','5598673423','cambare@gmail','0001'
);

insert into somativa2.vinicola values
('002','região do rio açu','umida','7898676754','rioaçu@gmail','0002'
);

insert into somativa2.vinicola values
('003','região de matinhos','montanhosa','4195553423','matinhos@gmail','0003'
);

insert into somativa2.vinicola values
('004','região de paris','elegante','5798333423','paris@gmail','0004'
);

insert into somativa2.vinicola values
('005','região de umuarama','pantanosa','0998673423','umuarama@gmail','0005'
);
select * from somativa2.regiao;
select * from somativa2.vinicola;
select * from somativa2.vinho;

SELECT t1.nome_vinho, t1.ano_vinho, t2.nome_vinicola, t2.descricao_vinicola
FROM somativa2.vinho AS t1
JOIN somativa2.vinicola AS t2
ON t1.codvinho = t2.codvinicola;
