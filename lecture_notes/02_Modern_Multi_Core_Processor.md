### Example Porgram 
> **Aims**: Compute sin(x) using Taylor expansion for each element of an array of N floating-point numbers
> **Taylor expansion**: sin(x) = x - x^3/3! + x^5/5! - ...
```C
void sinx(int N, int terms, float* x, float* result)
{
   for (int i=0; i<N; i++)
   {
      float value = x[i];
      float numer = x[i] * x[i] * x[i]; intdenom=6; //3!
      int sign = -1;
      for (int j=1; j<=terms; j++)
      {
         value += sign * numer / denom;
         numer *= x[i] * x[i];
         denom *= (2*j+2) * (2*j+3);
         sign *= -1;
      }
      result[i] = value;
   }
}
```

- **Compile the program**
  - input: textfile
  - output: binary code
 
- **Execute program**
  - Simple Processor: executes one instruction per clock

    <img width="266" alt="Screenshot 2024-01-30 at 3 07 40 PM" src="https://github.com/LuminaScript/CMU-15-418-618/assets/98562104/a2335025-5f0a-40a9-a3a8-242555f6d32a">
    <img width="304" alt="Screenshot 2024-01-30 at 3 12 38 PM" src="https://github.com/LuminaScript/CMU-15-418-618/assets/98562104/13f2205e-f325-4d55-a09d-17d301980b88">

    - Fetch/Decode: Decode the instructions
    - ALU (Execute): Execute the code
    - Execitoon Context : Update the register state
   
  - Superscalar Processor: ILP (instruction level parallelism) (decode & execute two instrutcions per clock)
    - we don't have _independent insrtuctions_

  - Proessor:
     - pre multi-core era: majority of chip transistors used to perform operation that help _a single instruction_ stream **run faster**
       - More transistors = larger cache, smarter out-of-order logic, smarter branch predictor, etc. (Also: more transistors → smaller transistors → higher clock frequencies)
       <img width="630" alt="Screenshot 2024-01-30 at 3 14 25 PM" src="https://github.com/LuminaScript/CMU-15-418-618/assets/98562104/5343733a-695b-4b25-9e5f-fbaea3e281ad">
      - two cores: compute 2 elements in parallel:
      - Four cores: compute four elements in parallel
      - Sixteen cores: compute sixteen elements in parallel

      - for all loop: Data-parallel expression
           1. Loop iterations declared by the programmer to be independent
           2. SIMD processing: single instruction & multiple data (SIMD processing) same instruction broadcast to all ALUs, executed in parallel on all ALUs
         ```cpp
         void sinx(int N, int terms, float* x, float* result)
         {
            // declare independent loop iterations
            forall (int i from 0 to N-1)
            {
         float value = x[i];
         float numer = x[i] * x[i] * x[i]; intdenom=6; //3!
         int sign = -1;
               for (int j=1; j<=terms; j++)
               {
                  value += sign * numer / denom;
                  numer *= x[i] * x[i];
                  denom *= (2*j+2) * (2*j+3);
                  sign *= -1;
         }
               result[i] = value;
            }
         }
        ```
         - 16 SIMD cores : 168 parallels 






  
