# _HashPassword(ushort const *,uchar *,unsigned __int64)

- ea: `0x18000b094`
- end: `0x18000b1da`
- name: `?_HashPassword@@YAJPEBGPEAE_K@Z`
- size: `326`
- prototype: `__int64 __fastcall(BYTE *pbData, BYTE *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006f80`

## callees

- `0x1800092b8`
- `0x18000a67c`
- `0x18000b094`

## import_xrefs

- `CRYPTSP!CryptReleaseContext` at `0x18000b1c7`
- `CRYPTSP!CryptReleaseContext` at `0x18000b1c7`
- `CRYPTSP!CryptDestroyHash` at `0x18000b1bb`
- `CRYPTSP!CryptDestroyHash` at `0x18000b1bb`
- `CRYPTSP!CryptHashData` at `0x18000b161`
- `CRYPTSP!CryptHashData` at `0x18000b161`
- `CRYPTSP!CryptAcquireContextW` at `0x18000b0e1`
- `CRYPTSP!CryptAcquireContextW` at `0x18000b0e1`
- `CRYPTSP!CryptCreateHash` at `0x18000b116`
- `CRYPTSP!CryptCreateHash` at `0x18000b116`
- `CRYPTSP!CryptGetHashParam` at `0x18000b1a1`
- `CRYPTSP!CryptGetHashParam` at `0x18000b1a1`

## pseudocode

```c
__int64 __fastcall _HashPassword(BYTE *pbData, BYTE *a2, __int64 a3)
{
  __int64 v5; // r8
  BYTE *v6; // rax
  int Error; // ebx
  __int64 v8; // rcx
  int v9; // ecx
  HCRYPTHASH phHash; // [rsp+68h] [rbp+38h] BYREF
  __int64 dwDataLen; // [rsp+70h] [rbp+40h] BYREF
  HCRYPTPROV phProv; // [rsp+78h] [rbp+48h] BYREF

  dwDataLen = a3;
  v5 = 32;
  v6 = a2;
  do
  {
    *v6++ = 0;
    --v5;
  }
  while ( v5 );
  phProv = 0;
  if ( CryptAcquireContextW(&phProv, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000000)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    phHash = 0;
    if ( CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      LODWORD(dwDataLen) = 0;
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&pbData[2 * v8] );
      Error = ULongLongToULong(2 * v8, (unsigned int *)&dwDataLen);
      if ( Error >= 0 )
      {
        if ( CryptHashData(phHash, pbData, dwDataLen, 0) || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          LODWORD(dwDataLen) = 0;
          Error = ULongLongToULong(0x20u, (unsigned int *)&dwDataLen);
          if ( Error >= 0 )
          {
            if ( CryptGetHashParam(phHash, v9 - 30, a2, (DWORD *)&dwDataLen, 0) )
              Error = 0;
            else
              Error = ResultFromKnownLastError();
          }
        }
      }
      CryptDestroyHash(phHash);
    }
    CryptReleaseContext(phProv, 0);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000b094  mov     [rsp-28h+dwDataLen], r8
0x18000b099  push    rbp
0x18000b09a  push    rbx
0x18000b09b  push    rsi
0x18000b09c  push    rdi
0x18000b09d  push    r14
0x18000b09f  mov     rbp, rsp
0x18000b0a2  sub     rsp, 30h
0x18000b0a6  mov     rsi, rdx
0x18000b0a9  mov     rdi, rcx
0x18000b0ac  mov     r8d, 20h ; ' '
0x18000b0b2  mov     rax, rdx
0x18000b0b5  xor     r14d, r14d
0x18000b0b8  mov     [rax], r14b
0x18000b0bb  inc     rax
0x18000b0be  sub     r8, 1
0x18000b0c2  jnz     short loc_18000B0B8
0x18000b0c4  lea     r9d, [r8+18h]; dwProvType
0x18000b0c8  mov     [rbp+phProv], r14
0x18000b0cc  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18000b0d3  mov     [rsp+30h+dwFlags], 0F0000000h; dwFlags
0x18000b0db  xor     edx, edx; szContainer
0x18000b0dd  lea     rcx, [rbp+phProv]; phProv
0x18000b0e1  call    cs:__imp_CryptAcquireContextW
0x18000b0e7  test    eax, eax
0x18000b0e9  jnz     short loc_18000B0FA
0x18000b0eb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000b0f0  mov     ebx, eax
0x18000b0f2  test    eax, eax
0x18000b0f4  js      loc_18000B1CD
0x18000b0fa  mov     rcx, [rbp+phProv]; hProv
0x18000b0fe  lea     rax, [rbp+phHash]
0x18000b102  xor     r9d, r9d; dwFlags
0x18000b105  mov     qword ptr [rsp+30h+dwFlags], rax; phHash
0x18000b10a  xor     r8d, r8d; hKey
0x18000b10d  mov     [rbp+phHash], r14
0x18000b111  mov     edx, 800Ch; Algid
0x18000b116  call    cs:__imp_CryptCreateHash
0x18000b11c  test    eax, eax
0x18000b11e  jnz     short loc_18000B12F
0x18000b120  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000b125  mov     ebx, eax
0x18000b127  test    eax, eax
0x18000b129  js      loc_18000B1C1
0x18000b12f  mov     dword ptr [rbp+dwDataLen], r14d
0x18000b133  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000b137  inc     rcx
0x18000b13a  cmp     [rdi+rcx*2], r14w
0x18000b13f  jnz     short loc_18000B137
0x18000b141  add     rcx, rcx; unsigned __int64
0x18000b144  lea     rdx, [rbp+dwDataLen]; unsigned int *
0x18000b148  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000b14d  mov     ebx, eax
0x18000b14f  test    eax, eax
0x18000b151  js      short loc_18000B1B7
0x18000b153  mov     r8d, dword ptr [rbp+dwDataLen]; dwDataLen
0x18000b157  xor     r9d, r9d; dwFlags
0x18000b15a  mov     rcx, [rbp+phHash]; hHash
0x18000b15e  mov     rdx, rdi; pbData
0x18000b161  call    cs:__imp_CryptHashData
0x18000b167  test    eax, eax
0x18000b169  jnz     short loc_18000B176
0x18000b16b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000b170  mov     ebx, eax
0x18000b172  test    eax, eax
0x18000b174  js      short loc_18000B1B7
0x18000b176  lea     rdx, [rbp+dwDataLen]; unsigned int *
0x18000b17a  mov     dword ptr [rbp+dwDataLen], r14d
0x18000b17e  mov     ecx, 20h ; ' '; unsigned __int64
0x18000b183  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000b188  mov     ebx, eax
0x18000b18a  test    eax, eax
0x18000b18c  js      short loc_18000B1B7
0x18000b18e  lea     edx, [rcx-1Eh]; dwParam
0x18000b191  mov     [rsp+30h+dwFlags], r14d; dwFlags
0x18000b196  mov     rcx, [rbp+phHash]; hHash
0x18000b19a  lea     r9, [rbp+dwDataLen]; pdwDataLen
0x18000b19e  mov     r8, rsi; pbData
0x18000b1a1  call    cs:__imp_CryptGetHashParam
0x18000b1a7  test    eax, eax
0x18000b1a9  jz      short loc_18000B1B0
0x18000b1ab  mov     ebx, r14d
0x18000b1ae  jmp     short loc_18000B1B7
0x18000b1b0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000b1b5  mov     ebx, eax
0x18000b1b7  mov     rcx, [rbp+phHash]; hHash
0x18000b1bb  call    cs:__imp_CryptDestroyHash
0x18000b1c1  mov     rcx, [rbp+phProv]; hProv
0x18000b1c5  xor     edx, edx; dwFlags
0x18000b1c7  call    cs:__imp_CryptReleaseContext
0x18000b1cd  mov     eax, ebx
0x18000b1cf  add     rsp, 30h
0x18000b1d3  pop     r14
0x18000b1d5  pop     rdi
0x18000b1d6  pop     rsi
0x18000b1d7  pop     rbx
0x18000b1d8  pop     rbp
0x18000b1d9  retn
```
