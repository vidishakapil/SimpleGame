# SimpleGame
package vidisha;

public class Main {

	public static void main(String[] args) {
		player1 player = new player1("vidisha","sword",100);
	//	System.out.println(player.getHealth());
	player.damagaByGun1();
	player.damagaByGun1();
    player.damageByGun2();
	player.heal();
		
		
	}

}
package vidisha;

public class player1 {
private String name;
private String weapon;
private  int health;

public player1(String name,String weapon,int health) {
	this.name=name;
	this.weapon=weapon;
	if(health<0||health>100) {
		this.health=100;
	}else {
	this.health=health;
	}
}

public void damagaByGun1() {
	this.health -=30;
	if(this.health<=0) {
		this.health=0;
	}
	System.out.println("Got hit by gun1.Health is reduced by 30 "+".New health is"+this.health);
	if(this.health==0) {
		System.out.println(getName()+" is dead");
	}
}
public void damageByGun2() {
	this.health -=50;
	if(this.health<=0) {
		this.health=0;
	}
	System.out.println("Got hit by gun1.Health is reduced by 50"
			 +".New health is"+this.health);
	if(this.health==0) {
		System.out.println(getName() +" is dead");
}
}
public void heal() {
	if(this.health<=0) {
		System.out.println("Player is dead.Heal not possible.");
	}else {
		this.health=100;
		System.out.println("Health is"+this.health);
	}
}

public String getName() {
	return name;
}

public void setName(String name) {
	this.name = name;
}

public String getWeapon() {
	return weapon;
}

public void setWeapon(String weapon) {
	this.weapon = weapon;
}

public int getHealth() {
	return health;
}

public void setHealth(int health) {
	this.health = health;
}

}
package vidisha;

public class player2 extends player1 {
	private int health;
	private boolean armour;

	
public player2(String name, String weapon, int health,boolean armour) {
		super(name, weapon, health);
		this.health = health;
		this.armour = armour;
	}


@Override
public void damagaByGun1() {
	if(armour) {
		this.health -=20;
		if(this.health <=0) this.health =0;
		System.out.println("Armour is on.Got hit by gun 1.Health is reduced by 20"+
		"New health is"+ this.health);
	}
	if(!armour) {
		this.health -=30;
		if(this.health <=0) this.health =0;
		System.out.println("Armour is off.Got hit by gun 1.Health is reduced by 30"+
		"New health is"+ this.health);
	}
	if(this.health==0) {
		System.out.println(getName()+"is dead");
	}
}


@Override
public void damageByGun2() {
	if(armour) {
		this.health -=40;
		if(this.health <=0) this.health =0;
		System.out.println("Armour is on.Got hit by gun 1.Health is reduced by 40"+
		"New health is"+ this.health);
	}
	if(!armour) {
		this.health -=50;
		if(this.health <=0) this.health =0;
		System.out.println("Armour is off.Got hit by gun 1.Health is reduced by 50"+
		"New health is"+ this.health);
	}
	if(this.health==0) {
		System.out.println(getName()+"is dead");
	}
}


@Override
public void heal() {
	// TODO Auto-generated method stub
	super.heal();
}

}
