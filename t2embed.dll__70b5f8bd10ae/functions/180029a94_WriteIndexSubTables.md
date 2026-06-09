# WriteIndexSubTables

- ea: `0x180029a94`
- end: `0x180029d35`
- name: `WriteIndexSubTables`
- size: `673`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012a18`

## callees

- `0x18000edd4`
- `0x180010ae4`
- `0x180011640`
- `0x18001c9ec`
- `0x180029a94`

## pseudocode

```c
__int16 __fastcall WriteIndexSubTables(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        unsigned int a5,
        unsigned int a6,
        _DWORD *a7)
{
  unsigned int v7; // ebx
  __int64 v9; // rdi
  unsigned __int16 v10; // r15
  unsigned int v12; // r13d
  unsigned int v13; // edx
  _WORD *v14; // rdi
  __int16 result; // ax
  __int16 v16; // si
  char *v17; // r8
  int v18; // edx
  __int64 v19; // rdx
  __int16 v20; // [rsp+30h] [rbp-20h]
  _WORD v21[2]; // [rsp+40h] [rbp-10h] BYREF
  _DWORD v22[3]; // [rsp+44h] [rbp-Ch] BYREF
  unsigned __int16 v24; // [rsp+A8h] [rbp+58h]

  v24 = a4;
  v7 = a5;
  v9 = a3;
  v21[0] = 0;
  v10 = 0;
  v22[0] = 0;
  v12 = a5;
  while ( v10 < a4 )
  {
    v13 = a6;
    if ( *(_DWORD *)(a2 + 8LL * v10 + 4) < a6 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v13 = a6;
    }
    v14 = (_WORD *)(*(unsigned int *)(a2 + 8LL * v10 + 4) - (unsigned __int64)v13 + v9);
    *(_DWORD *)(a2 + 8LL * v10 + 4) = v13 + v7 - v12;
    if ( *v14 == 1 )
    {
      v16 = *(_WORD *)(a2 + 8LL * v10 + 2) - *(_WORD *)(a2 + 8LL * v10) + 2;
      result = WriteGeneric(a1, (__int64)v14, 8u, (unsigned __int8 *)&INDEXSUBTABLE1_CONTROL, v7, v21);
      if ( result )
        return result;
      v20 = 4;
      v17 = LONG_CONTROL;
    }
    else
    {
      if ( *v14 == 2 )
      {
        result = WriteGeneric(a1, (__int64)v14, 0x14u, (unsigned __int8 *)INDEXSUBTABLE2_CONTROL, v7, v21);
        if ( result )
          return result;
        v18 = v21[0];
        goto LABEL_23;
      }
      if ( *v14 != 3 )
      {
        if ( *v14 == 4 )
        {
          result = WriteGeneric(a1, (__int64)v14, 0xCu, (unsigned __int8 *)&INDEXSUBTABLE4_CONTROL, v7, v21);
          if ( result )
            return result;
          v7 += v21[0];
          result = WriteGenericRepeat(
                     a1,
                     (int)v14 + 12,
                     (unsigned int)CODEOFFSETPAIR_CONTROL,
                     v7,
                     (__int64)v22,
                     v14[4] + 1,
                     4);
        }
        else
        {
          if ( *v14 != 5 )
            return 1086;
          result = WriteGeneric(a1, (__int64)v14, 0x18u, (unsigned __int8 *)INDEXSUBTABLE5_CONTROL, v7, v21);
          if ( result )
            return result;
          v7 += v21[0];
          result = WriteGenericRepeat(a1, (int)v14 + 24, (unsigned int)WORD_CONTROL, v7, (__int64)v22, v14[10], 2);
        }
        goto LABEL_21;
      }
      v16 = *(_WORD *)(a2 + 8LL * v10 + 2) - *(_WORD *)(a2 + 8LL * v10) + 2;
      result = WriteGeneric(a1, (__int64)v14, 8u, (unsigned __int8 *)INDEXSUBTABLE3_CONTROL, v7, v21);
      if ( result )
        return result;
      v20 = 2;
      v17 = WORD_CONTROL;
    }
    v7 += v21[0];
    result = WriteGenericRepeat(a1, (int)v14 + 8, (_DWORD)v17, v7, (__int64)v22, v16, v20);
LABEL_21:
    if ( result )
      return result;
    v18 = v22[0];
LABEL_23:
    v19 = v7 + v18;
    a5 = v19;
    result = ZeroLongWordAlign(a1, v19, &a5);
    if ( result )
      return result;
    v7 = a5;
    ++v10;
    a4 = v24;
    v9 = a3;
  }
  *a7 = v7 - v12;
  return 0;
}

```

## disassembly

```asm
0x180029a94  mov     [rsp-38h+arg_0], rbx
0x180029a99  mov     [rsp-38h+arg_18], r9w
0x180029a9f  mov     [rsp-38h+arg_10], r8
0x180029aa4  push    rbp
0x180029aa5  push    rsi
0x180029aa6  push    rdi
0x180029aa7  push    r12
0x180029aa9  push    r13
0x180029aab  push    r14
0x180029aad  push    r15
0x180029aaf  mov     rbp, rsp
0x180029ab2  sub     rsp, 50h
0x180029ab6  mov     ebx, [rbp+arg_20]
0x180029ab9  mov     r14, rcx
0x180029abc  xor     ecx, ecx
0x180029abe  mov     rdi, r8
0x180029ac1  mov     [rbp+var_10], cx
0x180029ac5  mov     r15d, ecx
0x180029ac8  mov     [rbp+var_C], ecx
0x180029acb  mov     r12, rdx
0x180029ace  mov     r13d, ebx
0x180029ad1  mov     r8d, 2
0x180029ad7  cmp     r15w, r9w
0x180029adb  jnb     loc_180029D12
0x180029ae1  mov     edx, [rbp+arg_28]
0x180029ae4  movzx   esi, r15w
0x180029ae8  cmp     [r12+rsi*8+4], edx
0x180029aed  jnb     short loc_180029AFD
0x180029aef  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180029af4  mov     edx, [rbp+arg_28]
0x180029af7  mov     r8d, 2
0x180029afd  mov     ecx, [r12+rsi*8+4]
0x180029b02  mov     eax, edx
0x180029b04  sub     rcx, rax
0x180029b07  mov     eax, ebx
0x180029b09  sub     eax, r13d
0x180029b0c  add     rdi, rcx
0x180029b0f  add     eax, edx
0x180029b11  mov     [r12+rsi*8+4], eax
0x180029b16  movzx   ecx, word ptr [rdi]
0x180029b19  sub     ecx, 1
0x180029b1c  jz      loc_180029C6C
0x180029b22  sub     ecx, 1
0x180029b25  jz      loc_180029C38
0x180029b2b  sub     ecx, 1
0x180029b2e  jz      loc_180029BEB
0x180029b34  sub     ecx, 1
0x180029b37  jz      short loc_180029B94
0x180029b39  cmp     ecx, 1
0x180029b3c  jnz     loc_180029D0B
0x180029b42  lea     rax, [rbp+var_10]
0x180029b46  mov     rdx, rdi
0x180029b49  lea     r8d, [rcx+17h]
0x180029b4d  mov     [rsp+50h+var_28], rax
0x180029b52  lea     r9, INDEXSUBTABLE5_CONTROL
0x180029b59  mov     dword ptr [rsp+50h+var_30], ebx
0x180029b5d  mov     rcx, r14
0x180029b60  call    WriteGeneric
0x180029b65  test    ax, ax
0x180029b68  jnz     loc_180029D1D
0x180029b6e  movzx   eax, [rbp+var_10]
0x180029b72  lea     rdx, [rdi+18h]
0x180029b76  add     ebx, eax
0x180029b78  mov     [rsp+50h+var_20], 2
0x180029b7f  movzx   eax, word ptr [rdi+14h]
0x180029b83  lea     r8, WORD_CONTROL
0x180029b8a  mov     word ptr [rsp+50h+var_28], ax
0x180029b8f  jmp     loc_180029CC2
0x180029b94  lea     rax, [rbp+var_10]
0x180029b98  mov     r8d, 0Ch
0x180029b9e  mov     [rsp+50h+var_28], rax
0x180029ba3  lea     r9, INDEXSUBTABLE4_CONTROL
0x180029baa  mov     rdx, rdi
0x180029bad  mov     dword ptr [rsp+50h+var_30], ebx
0x180029bb1  mov     rcx, r14
0x180029bb4  call    WriteGeneric
0x180029bb9  test    ax, ax
0x180029bbc  jnz     loc_180029D1D
0x180029bc2  movzx   eax, [rbp+var_10]
0x180029bc6  lea     rdx, [rdi+0Ch]
0x180029bca  add     ebx, eax
0x180029bcc  mov     [rsp+50h+var_20], 4
0x180029bd3  movzx   eax, word ptr [rdi+8]
0x180029bd7  lea     r8, CODEOFFSETPAIR_CONTROL
0x180029bde  inc     ax
0x180029be1  mov     word ptr [rsp+50h+var_28], ax
0x180029be6  jmp     loc_180029CC2
0x180029beb  movzx   eax, word ptr [r12+rsi*8+2]
0x180029bf1  lea     r9, INDEXSUBTABLE3_CONTROL
0x180029bf8  sub     ax, [r12+rsi*8]
0x180029bfd  mov     rdx, rdi
0x180029c00  mov     rcx, r14
0x180029c03  lea     esi, [r8+rax]
0x180029c07  mov     r8d, 8
0x180029c0d  lea     rax, [rbp+var_10]
0x180029c11  mov     [rsp+50h+var_28], rax
0x180029c16  mov     dword ptr [rsp+50h+var_30], ebx
0x180029c1a  call    WriteGeneric
0x180029c1f  test    ax, ax
0x180029c22  jnz     loc_180029D1D
0x180029c28  mov     [rsp+50h+var_20], 2
0x180029c2f  lea     r8, WORD_CONTROL
0x180029c36  jmp     short loc_180029CB3
0x180029c38  lea     rax, [rbp+var_10]
0x180029c3c  mov     r8d, 14h
0x180029c42  mov     [rsp+50h+var_28], rax
0x180029c47  lea     r9, INDEXSUBTABLE2_CONTROL
0x180029c4e  mov     rdx, rdi
0x180029c51  mov     dword ptr [rsp+50h+var_30], ebx
0x180029c55  mov     rcx, r14
0x180029c58  call    WriteGeneric
0x180029c5d  test    ax, ax
0x180029c60  jnz     loc_180029D1D
0x180029c66  movzx   edx, [rbp+var_10]
0x180029c6a  jmp     short loc_180029CDE
0x180029c6c  movzx   eax, word ptr [r12+rsi*8+2]
0x180029c72  lea     r9, INDEXSUBTABLE1_CONTROL
0x180029c79  sub     ax, [r12+rsi*8]
0x180029c7e  mov     rdx, rdi
0x180029c81  mov     rcx, r14
0x180029c84  lea     esi, [r8+rax]
0x180029c88  mov     r8d, 8
0x180029c8e  lea     rax, [rbp+var_10]
0x180029c92  mov     [rsp+50h+var_28], rax
0x180029c97  mov     dword ptr [rsp+50h+var_30], ebx
0x180029c9b  call    WriteGeneric
0x180029ca0  test    ax, ax
0x180029ca3  jnz     short loc_180029D1D
0x180029ca5  mov     [rsp+50h+var_20], 4
0x180029cac  lea     r8, LONG_CONTROL
0x180029cb3  movzx   eax, [rbp+var_10]
0x180029cb7  lea     rdx, [rdi+8]
0x180029cbb  add     ebx, eax
0x180029cbd  mov     word ptr [rsp+50h+var_28], si
0x180029cc2  lea     rax, [rbp+var_C]
0x180029cc6  mov     r9d, ebx
0x180029cc9  mov     rcx, r14
0x180029ccc  mov     [rsp+50h+var_30], rax
0x180029cd1  call    WriteGenericRepeat
0x180029cd6  test    ax, ax
0x180029cd9  jnz     short loc_180029D1D
0x180029cdb  mov     edx, [rbp+var_C]
0x180029cde  add     edx, ebx
0x180029ce0  lea     r8, [rbp+arg_20]
0x180029ce4  mov     rcx, r14
0x180029ce7  mov     [rbp+arg_20], edx
0x180029cea  call    ZeroLongWordAlign
0x180029cef  xor     ecx, ecx
0x180029cf1  test    ax, ax
0x180029cf4  jnz     short loc_180029D1D
0x180029cf6  mov     ebx, [rbp+arg_20]
0x180029cf9  inc     r15w
0x180029cfd  movzx   r9d, [rbp+arg_18]
0x180029d02  mov     rdi, [rbp+arg_10]
0x180029d06  jmp     loc_180029AD1
0x180029d0b  mov     eax, 43Eh
0x180029d10  jmp     short loc_180029D1D
0x180029d12  mov     rax, [rbp+arg_30]
0x180029d16  sub     ebx, r13d
0x180029d19  mov     [rax], ebx
0x180029d1b  mov     eax, ecx
0x180029d1d  mov     rbx, [rsp+50h+arg_0]
0x180029d25  add     rsp, 50h
0x180029d29  pop     r15
0x180029d2b  pop     r14
0x180029d2d  pop     r13
0x180029d2f  pop     r12
0x180029d31  pop     rdi
0x180029d32  pop     rsi
0x180029d33  pop     rbp
0x180029d34  retn
```
