# RngGetBytes(uchar *,uint)

- ea: `0x140021884`
- end: `0x140021911`
- name: `?RngGetBytes@@YAJPEAEI@Z`
- size: `141`
- prototype: `__int64 __fastcall(PUCHAR pbBuffer, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002015c`

## callees

- `0x140021884`

## import_xrefs

- `cng!BCryptGenRandom` at `0x1400218dd`
- `cng!BCryptGenRandom` at `0x1400218dd`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400218f7`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400218f7`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400218bc`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400218bc`

## pseudocode

```c
__int64 __fastcall RngGetBytes(PUCHAR pbBuffer)
{
  NTSTATUS v2; // ebx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp+18h] BYREF

  phAlgorithm = 0;
  if ( pbBuffer )
  {
    v2 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", L"Microsoft Primitive Provider", 0);
    if ( v2 >= 0 )
      v2 = BCryptGenRandom(phAlgorithm, pbBuffer, 0x14u, 0);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140021884  mov     [rsp+arg_0], rbx
0x140021889  push    rdi
0x14002188a  sub     rsp, 20h
0x14002188e  mov     [rsp+28h+phAlgorithm], 0
0x140021897  mov     rdi, rcx
0x14002189a  test    rcx, rcx
0x14002189d  jnz     short loc_1400218A6
0x14002189f  mov     ebx, 0C000000Dh
0x1400218a4  jmp     short loc_140021903
0x1400218a6  xor     r9d, r9d; dwFlags
0x1400218a9  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1400218b0  lea     rdx, pszAlgId; "RNG"
0x1400218b7  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x1400218bc  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400218c3  nop     dword ptr [rax+rax+00h]
0x1400218c8  mov     ebx, eax
0x1400218ca  test    eax, eax
0x1400218cc  js      short loc_1400218EB
0x1400218ce  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x1400218d3  xor     r9d, r9d; dwFlags
0x1400218d6  mov     rdx, rdi; pbBuffer
0x1400218d9  lea     r8d, [r9+14h]; cbBuffer
0x1400218dd  call    cs:__imp_BCryptGenRandom
0x1400218e4  nop     dword ptr [rax+rax+00h]
0x1400218e9  mov     ebx, eax
0x1400218eb  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x1400218f0  test    rcx, rcx
0x1400218f3  jz      short loc_140021903
0x1400218f5  xor     edx, edx; dwFlags
0x1400218f7  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400218fe  nop     dword ptr [rax+rax+00h]
0x140021903  mov     eax, ebx
0x140021905  mov     rbx, [rsp+28h+arg_0]
0x14002190a  add     rsp, 20h
0x14002190e  pop     rdi
0x14002190f  retn
```
