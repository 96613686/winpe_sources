# I_MinCryptFindIssuerCertificateByName

- ea: `0x180016c14`
- end: `0x180016d05`
- name: `I_MinCryptFindIssuerCertificateByName`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016f2c`
- `0x18001805c`

## callees

- `0x180016c14`
- `0x180016e48`
- `0x180018404`

## import_xrefs

- `securekernel!RtlCompareMemory` at `0x180016c75`
- `securekernel!RtlCompareMemory` at `0x180016c75`

## pseudocode

```c
__int64 __fastcall I_MinCryptFindIssuerCertificateByName(
        unsigned int *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  SIZE_T v5; // r15
  const void *v9; // r9
  unsigned int v10; // edi
  __int64 v11; // rsi
  const void *v13; // [rsp+20h] [rbp-38h]
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF

  v5 = *a1;
  if ( (_DWORD)v5 )
  {
    v9 = (const void *)*((_QWORD *)a1 + 1);
    v10 = 0;
    v13 = v9;
    while ( v10 < a2 )
    {
      v11 = a3 + 240LL * v10;
      if ( (_DWORD)v5 == *(_DWORD *)(v11 + 160) )
      {
        if ( RtlCompareMemory(v9, *(const void **)(v11 + 168), v5) == v5 )
        {
          if ( !a4 )
            return a3 + 240LL * v10;
          if ( !a5 )
            return a3 + 240LL * v10;
          if ( (*(_DWORD *)(a4 + 4) & 1) == 0 )
            return a3 + 240LL * v10;
          v14 = 50;
          if ( (int)I_MinCryptGetCertificateEKUs(v11 + 224, &v14, a5) >= 0 )
          {
            if ( (unsigned __int8)I_MinCryptCheckEKURequirements(v14, a5, a4) )
              return a3 + 240LL * v10;
          }
        }
        v9 = v13;
      }
      ++v10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016c14  mov     [rsp+arg_8], rbx
0x180016c19  mov     [rsp+arg_10], rbp
0x180016c1e  push    rsi
0x180016c1f  push    rdi
0x180016c20  push    r12
0x180016c22  push    r13
0x180016c24  push    r15
0x180016c26  sub     rsp, 30h
0x180016c2a  mov     r15d, [rcx]
0x180016c2d  mov     rbp, r9
0x180016c30  mov     r13, r8
0x180016c33  mov     r12d, edx
0x180016c36  test    r15d, r15d
0x180016c39  jz      loc_180016CEB
0x180016c3f  mov     r9, [rcx+8]
0x180016c43  xor     edi, edi
0x180016c45  mov     [rsp+58h+var_38], r9
0x180016c4a  cmp     edi, r12d
0x180016c4d  jnb     loc_180016CEB
0x180016c53  mov     eax, edi
0x180016c55  imul    rsi, rax, 0F0h
0x180016c5c  add     rsi, r13
0x180016c5f  cmp     r15d, [rsi+0A0h]
0x180016c66  jnz     short loc_180016CDF
0x180016c68  mov     rdx, [rsi+0A8h]; Source2
0x180016c6f  mov     r8, r15; Length
0x180016c72  mov     rcx, r9; Source1
0x180016c75  call    cs:__imp_RtlCompareMemory
0x180016c7c  nop     dword ptr [rax+rax+00h]
0x180016c81  cmp     rax, r15
0x180016c84  jnz     short loc_180016CDA
0x180016c86  test    rbp, rbp
0x180016c89  jz      short loc_180016CE6
0x180016c8b  cmp     [rsp+58h+arg_20], 0
0x180016c94  jz      short loc_180016CE6
0x180016c96  mov     eax, [rbp+4]
0x180016c99  test    al, 1
0x180016c9b  jz      short loc_180016CE6
0x180016c9d  mov     r8, [rsp+58h+arg_20]
0x180016ca5  lea     rcx, [rsi+0E0h]
0x180016cac  lea     rdx, [rsp+58h+arg_0]
0x180016cb1  mov     [rsp+58h+arg_0], 32h ; '2'
0x180016cb9  call    I_MinCryptGetCertificateEKUs
0x180016cbe  test    eax, eax
0x180016cc0  js      short loc_180016CDA
0x180016cc2  mov     rdx, [rsp+58h+arg_20]
0x180016cca  mov     r8, rbp
0x180016ccd  mov     ecx, [rsp+58h+arg_0]
0x180016cd1  call    I_MinCryptCheckEKURequirements
0x180016cd6  test    al, al
0x180016cd8  jnz     short loc_180016CE6
0x180016cda  mov     r9, [rsp+58h+var_38]
0x180016cdf  inc     edi
0x180016ce1  jmp     loc_180016C4A
0x180016ce6  mov     rax, rsi
0x180016ce9  jmp     short loc_180016CED
0x180016ceb  xor     eax, eax
0x180016ced  mov     rbx, [rsp+58h+arg_8]
0x180016cf2  mov     rbp, [rsp+58h+arg_10]
0x180016cf7  add     rsp, 30h
0x180016cfb  pop     r15
0x180016cfd  pop     r13
0x180016cff  pop     r12
0x180016d01  pop     rdi
0x180016d02  pop     rsi
0x180016d03  retn
```
