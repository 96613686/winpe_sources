# TSGenRandom(ulong,uchar *)

- ea: `0x180018f38`
- end: `0x180018fa9`
- name: `?TSGenRandom@@YAJKPEAE@Z`
- size: `113`
- prototype: `int(unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006650`

## callees

- `0x180018f38`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x180018f87`
- `bcrypt!BCryptGenRandom` at `0x180018f87`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180018f96`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180018f96`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180018f6c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180018f6c`

## pseudocode

```c
__int64 __fastcall TSGenRandom(__int64 a1, unsigned __int8 *a2)
{
  NTSTATUS v3; // ebx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp+18h] BYREF

  phAlgorithm = 0;
  if ( a2 )
  {
    v3 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", 0, 0);
    if ( v3 >= 0 )
    {
      v3 = BCryptGenRandom(phAlgorithm, a2, 0x20u, 0);
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180018f38  mov     [rsp+arg_0], rbx
0x180018f3d  push    rdi
0x180018f3e  sub     rsp, 20h
0x180018f42  mov     [rsp+28h+phAlgorithm], 0
0x180018f4b  mov     rdi, rdx
0x180018f4e  test    rdx, rdx
0x180018f51  jnz     short loc_180018F5A
0x180018f53  mov     ebx, 0C000000Dh
0x180018f58  jmp     short loc_180018F9C
0x180018f5a  xor     r9d, r9d; dwFlags
0x180018f5d  lea     rdx, aRng; "RNG"
0x180018f64  xor     r8d, r8d; pszImplementation
0x180018f67  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x180018f6c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180018f72  mov     ebx, eax
0x180018f74  test    eax, eax
0x180018f76  js      short loc_180018F9C
0x180018f78  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x180018f7d  xor     r9d, r9d; dwFlags
0x180018f80  mov     rdx, rdi; pbBuffer
0x180018f83  lea     r8d, [r9+20h]; cbBuffer
0x180018f87  call    cs:__imp_BCryptGenRandom
0x180018f8d  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x180018f92  xor     edx, edx; dwFlags
0x180018f94  mov     ebx, eax
0x180018f96  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180018f9c  mov     eax, ebx
0x180018f9e  mov     rbx, [rsp+28h+arg_0]
0x180018fa3  add     rsp, 20h
0x180018fa7  pop     rdi
0x180018fa8  retn
```
