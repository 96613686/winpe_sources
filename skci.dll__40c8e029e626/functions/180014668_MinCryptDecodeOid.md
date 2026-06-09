# MinCryptDecodeOid

- ea: `0x180014668`
- end: `0x1800146ce`
- name: `MinCryptDecodeOid`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014614`
- `0x1800146d4`

## callees

- `0x180014668`

## import_xrefs

- `securekernel!RtlCompareMemory` at `0x1800146a1`
- `securekernel!RtlCompareMemory` at `0x1800146a1`

## pseudocode

```c
__int64 __fastcall MinCryptDecodeOid(__int64 a1, unsigned int a2, unsigned int *a3)
{
  SIZE_T v3; // r14
  const void *v5; // r12
  __int64 i; // rdi

  v3 = *a3;
  v5 = (const void *)*((_QWORD *)a3 + 1);
  for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
  {
    if ( (_DWORD)v3 == *(_DWORD *)(a1 + 24 * i) && RtlCompareMemory(v5, *(const void **)(a1 + 24 * i + 8), v3) == v3 )
      return *(unsigned int *)(a1 + 24 * i + 16);
  }
  return 0;
}

```

## disassembly

```asm
0x180014668  push    rbx
0x18001466a  push    rbp
0x18001466b  push    rsi
0x18001466c  push    rdi
0x18001466d  push    r12
0x18001466f  push    r14
0x180014671  push    r15
0x180014673  sub     rsp, 20h
0x180014677  mov     r14d, [r8]
0x18001467a  mov     r15d, edx
0x18001467d  mov     r12, [r8+8]
0x180014681  mov     rbp, rcx
0x180014684  xor     edi, edi
0x180014686  cmp     edi, r15d
0x180014689  jnb     short loc_1800146BC
0x18001468b  lea     rsi, [rdi+rdi*2]
0x18001468f  cmp     r14d, [rbp+rsi*8+0]
0x180014694  jnz     short loc_1800146B2
0x180014696  mov     rdx, [rbp+rsi*8+8]; Source2
0x18001469b  mov     r8, r14; Length
0x18001469e  mov     rcx, r12; Source1
0x1800146a1  call    cs:__imp_RtlCompareMemory
0x1800146a8  nop     dword ptr [rax+rax+00h]
0x1800146ad  cmp     rax, r14
0x1800146b0  jz      short loc_1800146B6
0x1800146b2  inc     edi
0x1800146b4  jmp     short loc_180014686
0x1800146b6  mov     eax, [rbp+rsi*8+10h]
0x1800146ba  jmp     short loc_1800146BE
0x1800146bc  xor     eax, eax
0x1800146be  add     rsp, 20h
0x1800146c2  pop     r15
0x1800146c4  pop     r14
0x1800146c6  pop     r12
0x1800146c8  pop     rdi
0x1800146c9  pop     rsi
0x1800146ca  pop     rbp
0x1800146cb  pop     rbx
0x1800146cc  retn
```
