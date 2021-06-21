#include <iostream>
#include <ctime>

int main()
{
	srand(time(NULL));
	const int matrixSize = 5;

	int matrixA[matrixSize][matrixSize];
	int matrixB[matrixSize][matrixSize];

	int matrixDiagonalSum = 0;
	int matrixTopSum = 0;

	int matrixTopCounter = 0;

	std::cout << "Source matrix A : " << std::endl;


	for (int i = 0; i < matrixSize; i++)
	{
		for (int j = 0; j < matrixSize; j++)
		{
			matrixA[i][j] = rand() % 10;

			if (i == j)
				matrixDiagonalSum += matrixA[i][j];

			if (j > i)
			{
				matrixTopSum += matrixA[i][j];
				matrixTopCounter++;
			}

			std::cout << matrixA[i][j] << ' ';
		}
		std::cout << std::endl;
	}

	float matrixTopRatio = matrixTopSum / matrixTopCounter;
	float matrixDiagonalRatio = matrixDiagonalSum / matrixSize;
	float matrixRatio = matrixTopRatio / matrixDiagonalRatio;

	std::cout << "Aswer 1 : " << matrixRatio << std::endl;


	for (int i = 0; i < matrixSize; i++)
	{
		for (int j = 0; j < matrixSize; j++)
		{
			matrixB[i][j] = matrixA[matrixSize - 1 - i][matrixSize - 1 - j];
			std::cout << matrixB[i][j] << " ";
		}
		std::cout << std::endl;
	}

}
