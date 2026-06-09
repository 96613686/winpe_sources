# I_MinCryptFindSignerCertificateByIssuerAndSerialNumber

- ea: `0x180014cc4`
- end: `0x180014d6c`
- name: `I_MinCryptFindSignerCertificateByIssuerAndSerialNumber`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800150c0`
- `0x180015624`

## callees

- `0x180014cc4`

## import_xrefs

- `securekernel!RtlCompareMemory` at `0x180014d1e`
- `securekernel!RtlCompareMemory` at `0x180014d39`
- `securekernel!RtlCompareMemory` at `0x180014d1e`
- `securekernel!RtlCompareMemory` at `0x180014d39`

## pseudocode

```c
__int64 __fastcall I_MinCryptFindSignerCertificateByIssuerAndSerialNumber(
        unsigned int *a1,
        unsigned int *a2,
        unsigned int a3,
        __int64 a4)
{
  SIZE_T v4; // r14
  SIZE_T v7; // rbp
  const void *v8; // r9
  unsigned int v9; // esi
  const void *v10; // r13
  __int64 v11; // rdi
  const void *v13; // [rsp+70h] [rbp+8h]

  v4 = *a1;
  if ( (_DWORD)v4 )
  {
    v7 = *a2;
    if ( (_DWORD)v7 )
    {
      v8 = (const void *)*((_QWORD *)a2 + 1);
      v9 = 0;
      v10 = (const void *)*((_QWORD *)a1 + 1);
      v13 = v8;
      while ( v9 < a3 )
      {
        v11 = a4 + 240LL * v9;
        if ( (_DWORD)v4 == *(_DWORD *)(v11 + 112) && (_DWORD)v7 == *(_DWORD *)(v11 + 96) )
        {
          if ( RtlCompareMemory(v8, *(const void **)(v11 + 104), v7) == v7
            && RtlCompareMemory(v10, *(const void **)(v11 + 120), v4) == v4 )
          {
            return a4 + 240LL * v9;
          }
          v8 = v13;
        }
        ++v9;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180014cc4  push    rbx
0x180014cc6  push    rbp
0x180014cc7  push    rsi
0x180014cc8  push    rdi
0x180014cc9  push    r12
0x180014ccb  push    r13
0x180014ccd  push    r14
0x180014ccf  push    r15
0x180014cd1  sub     rsp, 28h
0x180014cd5  mov     r14d, [rcx]
0x180014cd8  mov     r12, r9
0x180014cdb  mov     r15d, r8d
0x180014cde  test    r14d, r14d
0x180014ce1  jz      short loc_180014D58
0x180014ce3  mov     ebp, [rdx]
0x180014ce5  test    ebp, ebp
0x180014ce7  jz      short loc_180014D58
0x180014ce9  mov     r9, [rdx+8]
0x180014ced  xor     esi, esi
0x180014cef  mov     r13, [rcx+8]
0x180014cf3  mov     [rsp+68h+arg_0], r9
0x180014cf8  cmp     esi, r15d
0x180014cfb  jnb     short loc_180014D58
0x180014cfd  mov     eax, esi
0x180014cff  imul    rdi, rax, 0F0h
0x180014d06  add     rdi, r12
0x180014d09  cmp     r14d, [rdi+70h]
0x180014d0d  jnz     short loc_180014D4F
0x180014d0f  cmp     ebp, [rdi+60h]
0x180014d12  jnz     short loc_180014D4F
0x180014d14  mov     rdx, [rdi+68h]; Source2
0x180014d18  mov     r8, rbp; Length
0x180014d1b  mov     rcx, r9; Source1
0x180014d1e  call    cs:__imp_RtlCompareMemory
0x180014d25  nop     dword ptr [rax+rax+00h]
0x180014d2a  cmp     rax, rbp
0x180014d2d  jnz     short loc_180014D4A
0x180014d2f  mov     rdx, [rdi+78h]; Source2
0x180014d33  mov     r8, r14; Length
0x180014d36  mov     rcx, r13; Source1
0x180014d39  call    cs:__imp_RtlCompareMemory
0x180014d40  nop     dword ptr [rax+rax+00h]
0x180014d45  cmp     rax, r14
0x180014d48  jz      short loc_180014D53
0x180014d4a  mov     r9, [rsp+68h+arg_0]
0x180014d4f  inc     esi
0x180014d51  jmp     short loc_180014CF8
0x180014d53  mov     rax, rdi
0x180014d56  jmp     short loc_180014D5A
0x180014d58  xor     eax, eax
0x180014d5a  add     rsp, 28h
0x180014d5e  pop     r15
0x180014d60  pop     r14
0x180014d62  pop     r13
0x180014d64  pop     r12
0x180014d66  pop     rdi
0x180014d67  pop     rsi
0x180014d68  pop     rbp
0x180014d69  pop     rbx
0x180014d6a  retn
```
