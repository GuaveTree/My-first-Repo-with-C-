
#include <iostream>
#include <filesystem>


template <typename T> void print(T x, bool wantSpace = true) {
	
	if (!wantSpace) {
		std::cout << x << "  ";
	}
	else {
		std::cout << x << "\n";
	}
}

int main() {
	while (true) {
	std::string targetPath;
		print("Enter Your Path");

	std::getline(std::cin >> std::ws, targetPath);
	
		if (std::filesystem::exists(targetPath)) {
			std::filesystem::path ThePath = targetPath;
			if (std::filesystem::is_regular_file(targetPath)) {
				print("");
				print("=======================================");
				print("The file Was found!");
			}
			else if (std::filesystem::is_directory(targetPath)) {
				print("The Folder Was found!");

				print("The Children");
				print("===================================");

				for (const auto& file : std::filesystem::directory_iterator(targetPath)) {
					std::filesystem::path filPath = file;
					print("|__", false); print("The Name:", false); print(filPath.filename(), false); print("The Extension: ", false); print(filPath.extension());
				}
				print("===================================");
				
			}
				print("The Size is:", false);
				print(std::filesystem::file_size(targetPath));
	
				print("The Name: ", false);
				print(ThePath.filename());

				print("The Extension", false);
				print(ThePath.extension());
				print("=======================================");
				print("");
		}
		else {
			print("The Target not found");
		}
	}
	
	return 0;
}
