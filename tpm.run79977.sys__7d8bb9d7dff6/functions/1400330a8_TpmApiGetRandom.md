# TpmApiGetRandom

- ea: `0x1400330a8`
- end: `0x14003314c`
- name: `TpmApiGetRandom`
- size: `164`
- prototype: `__int64 __fastcall(ULONG cbBuffer, PUCHAR pbBuffer)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140032970`
- `0x140034664`

## callees

- `0x140033080`
- `0x1400330a8`

## import_xrefs

- `cng!BCryptGenRandom` at `0x14003310c`
- `cng!BCryptGenRandom` at `0x14003310c`
- `cng!BCryptCloseAlgorithmProvider` at `0x14003312d`
- `cng!BCryptCloseAlgorithmProvider` at `0x14003312d`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400330e5`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400330e5`

## pseudocode

```c
__int64 __fastcall TpmApiGetRandom(ULONG cbBuffer, PUCHAR pbBuffer)
{
  int v2; // ebx
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  phAlgorithm = 0;
  if ( cbBuffer )
  {
    if ( pbBuffer )
    {
      v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", 0, 0);
      v2 = FromNtStatus(v5);
      if ( v2 >= 0 )
      {
        v6 = BCryptGenRandom(phAlgorithm, pbBuffer, cbBuffer, 0);
        v2 = FromNtStatus(v6);
      }
      if ( phAlgorithm )
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    }
    else
    {
      return (unsigned int)-2144796413;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400330a8  mov     [rsp+arg_0], rbx
0x1400330ad  mov     [rsp+arg_8], rsi
0x1400330b2  push    rdi
0x1400330b3  sub     rsp, 20h
0x1400330b7  xor     ebx, ebx
0x1400330b9  mov     rdi, rdx
0x1400330bc  mov     [rsp+28h+phAlgorithm], rbx
0x1400330c1  mov     esi, ecx
0x1400330c3  test    ecx, ecx
0x1400330c5  jz      short loc_140033139
0x1400330c7  test    rdx, rdx
0x1400330ca  jnz     short loc_1400330D3
0x1400330cc  mov     ebx, 80290103h
0x1400330d1  jmp     short loc_140033139
0x1400330d3  xor     r9d, r9d; dwFlags
0x1400330d6  lea     rdx, pszAlgId; "RNG"
0x1400330dd  xor     r8d, r8d; pszImplementation
0x1400330e0  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x1400330e5  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400330ec  nop     dword ptr [rax+rax+00h]
0x1400330f1  mov     ecx, eax; int
0x1400330f3  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1400330f8  mov     ebx, eax
0x1400330fa  test    eax, eax
0x1400330fc  js      short loc_140033121
0x1400330fe  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x140033103  xor     r9d, r9d; dwFlags
0x140033106  mov     r8d, esi; cbBuffer
0x140033109  mov     rdx, rdi; pbBuffer
0x14003310c  call    cs:__imp_BCryptGenRandom
0x140033113  nop     dword ptr [rax+rax+00h]
0x140033118  mov     ecx, eax; int
0x14003311a  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x14003311f  mov     ebx, eax
0x140033121  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x140033126  test    rcx, rcx
0x140033129  jz      short loc_140033139
0x14003312b  xor     edx, edx; dwFlags
0x14003312d  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140033134  nop     dword ptr [rax+rax+00h]
0x140033139  mov     rsi, [rsp+28h+arg_8]
0x14003313e  mov     eax, ebx
0x140033140  mov     rbx, [rsp+28h+arg_0]
0x140033145  add     rsp, 20h
0x140033149  pop     rdi
0x14003314a  retn
```
