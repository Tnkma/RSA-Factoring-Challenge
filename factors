#include <stdio.h>
#include <math.h>
#include <string.h>
#include <stdlib.h>
/**
 * get_factor - gets the factor of the number
 * @num: the number to get
 *
 * Return: the factor
 */

int get_factor(long long int num)
{
	long long int m;
	long long int squ;

	squ = sqrt(num);
	for (m = 2; m <= squ; m++)
	{
		if (num % m == 0)
		{
			return (m);
		}
	}
	return (-1);
}
/**
 * main -  a program that factorize as many numbers as possible
 * into a product of two smaller numbers.
 *
 * @argc: the argument count
 * @argv: the command line argument
 *
 * Return: Always 0 for success
 */

int main(int argc, char **argv)
{
	FILE *open_file = NULL;
	char *line = NULL;
	size_t len = 0;
	ssize_t gread;
	long long int get_num = 0, fac = 0;
	long long int num;

	if (argc != 2)
	{
		fprintf(stderr, "please include the file name\n");
		exit(EXIT_FAILURE);
	}
	/* open the file */
	open_file = fopen(argv[1], "r");
	if (!open_file)
	{
		fprintf(stderr, "can't open file %s\n", argv[1]);
		exit(EXIT_FAILURE);
	}
	while ((gread = getline(&line, &len, open_file)) != -1)
	{
		num = atoll(line);
		get_num = get_factor(num);
		if (get_num != -1)
		{
			fac = num / get_num;
			printf("%lld=%lld*%lld\n", num, fac, get_num);
		}
		else
		{
			printf("No factor found for the %lld\n", num);
		}
	}
	gread = getline(&line, &len, open_file);

	fclose(open_file);
	free(line);
	return (0);
}
