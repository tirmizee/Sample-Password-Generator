# Sample-Password-Generator
	
	@author pratya yeekhaday
	
	public class PasswordGenerator {

		private static final String DIGITS = "0123456789";
		private static final String UPCASE_CHARACTERS = "ABCDEFGHJKMNPQRSTUVWXYZ";
		private static final String LOCASE_CHARACTERS = UPCASE_CHARACTERS.toLowerCase();
		private static final Random RANDOM = new Random();


		public static String generate(int length){
			final StringBuilder password = new StringBuilder(length);
			for (int i = 0; i < length; i++) {
				switch(RANDOM.nextInt(3)){
					case 0 : password.append(randomDigit()); break;
					case 1 : password.append(randomLowerCharacter()); break;
					case 2 : password.append(randomUpperCharacter()); break;
				}
			}
			return password.toString();
		}

		private static int randomIndex(int bound){
			return RANDOM.nextInt(bound);
		}

		private static char randomDigit(){
			return DIGITS.charAt(randomIndex(DIGITS.length()));
		}

		private static char randomLowerCharacter(){
			return LOCASE_CHARACTERS.charAt(randomIndex(UPCASE_CHARACTERS.length()));
		}

		private static char randomUpperCharacter(){
			return UPCASE_CHARACTERS.charAt(randomIndex(LOCASE_CHARACTERS.length()));
		}

		public static void main(String[] args) {
			for (int i = 0; i < 5; i++) {
				System.out.println(generate(10));
			}
		}
	
	}
## Output

WRnqJw7C8n

ddzzx3d73G

XGbC0J7QcH

6MwqCY1hxT

fY9Eq7m1Cg
