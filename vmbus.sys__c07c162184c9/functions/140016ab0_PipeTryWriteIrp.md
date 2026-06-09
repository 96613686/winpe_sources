# PipeTryWriteIrp

- ea: `0x140016ab0`
- end: `0x140016c3f`
- name: `PipeTryWriteIrp`
- size: `399`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140002380`
- `0x14001661c`

## callees

- `0x140002560`
- `0x1400164d8`
- `0x140016994`
- `0x140016ab0`
- `0x140017000`
- `0x140017240`

## pseudocode

```c
__int64 __fastcall PipeTryWriteIrp(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r14
  int v7; // ebx
  unsigned __int64 v8; // rcx
  char v9; // r9
  unsigned int v11; // [rsp+40h] [rbp-40h] BYREF
  __int64 v12; // [rsp+48h] [rbp-38h] BYREF
  __int128 Src; // [rsp+50h] [rbp-30h] BYREF
  void *v14[2]; // [rsp+60h] [rbp-20h]
  size_t Size; // [rsp+70h] [rbp-10h]

  v3 = *(_QWORD *)(a2 + 184);
  v12 = 0;
  Src = 0;
  Size = 0;
  *(_OWORD *)v14 = 0;
  if ( *(_BYTE *)(a1 + 273) && !*(_DWORD *)(v3 + 8) && *(_BYTE *)(a1 + 274) )
  {
    v11 = 0;
    v7 = PipeTryWriteDeferred(a1, 1, (unsigned int)&v11, 1, a3, (__int64)&v12, (__int64)&Src);
    if ( v7 >= 0 )
      memmove(v14[1], &Src, (unsigned int)Size);
  }
  else
  {
    v8 = *(unsigned int *)(v3 + 8);
    if ( *(_QWORD *)(a2 + 56) >= v8 )
    {
      return 0;
    }
    else
    {
      while ( 1 )
      {
        v9 = *(_BYTE *)(a1 + 273);
        v11 = v8 - *(_DWORD *)(a2 + 56);
        v7 = PipeTryWriteDeferred(a1, 1, (unsigned int)&v11, v9, a3, (__int64)&v12, (__int64)&Src);
        if ( v7 < 0 )
          break;
        v7 = PipeMapChainedMdl(*(PMDL *)(a2 + 8));
        if ( v7 < 0 )
          break;
        memmove(v14[1], &Src, (unsigned int)Size);
        v7 = PipeReadWriteChainedMdl(*(_QWORD *)(a2 + 8), *(_DWORD *)(a2 + 56), v12, v11, 0);
        if ( v7 < 0 )
          break;
        v8 = v11;
        *(_QWORD *)(a2 + 56) += v11;
        *(_QWORD *)(*(_QWORD *)(a1 + 264) + 8LL) += v8;
        ++*(_QWORD *)(*(_QWORD *)(a1 + 264) + 24LL);
        LODWORD(v8) = *(_DWORD *)(v3 + 8);
        if ( *(_QWORD *)(a2 + 56) >= (unsigned __int64)(unsigned int)v8 )
          return 0;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140016ab0  mov     [rsp-28h+arg_18], rbx
0x140016ab5  push    rbp
0x140016ab6  push    rsi
0x140016ab7  push    rdi
0x140016ab8  push    r14
0x140016aba  push    r15
0x140016abc  mov     rbp, rsp
0x140016abf  sub     rsp, 80h
0x140016ac6  mov     rax, cs:__security_cookie
0x140016acd  xor     rax, rsp
0x140016ad0  mov     [rbp+var_8], rax
0x140016ad4  mov     r14, [rdx+0B8h]
0x140016adb  xor     eax, eax
0x140016add  xorps   xmm0, xmm0
0x140016ae0  mov     r15, r8
0x140016ae3  mov     rdi, rdx
0x140016ae6  mov     rsi, rcx
0x140016ae9  mov     [rbp+var_38], 0
0x140016af1  movups  [rbp+Src], xmm0
0x140016af5  mov     [rbp+Size], rax
0x140016af9  movups  xmmword ptr [rbp+var_20], xmm0
0x140016afd  cmp     [rcx+111h], al
0x140016b03  jz      short loc_140016B60
0x140016b05  cmp     [r14+8], eax
0x140016b09  jnz     short loc_140016B60
0x140016b0b  cmp     [rcx+112h], al
0x140016b11  jz      short loc_140016B60
0x140016b13  mov     [rbp+var_40], eax
0x140016b16  mov     r9b, 1
0x140016b19  lea     rax, [rbp+Src]
0x140016b1d  mov     edx, 1
0x140016b22  mov     [rsp+80h+var_50], rax
0x140016b27  lea     rax, [rbp+var_38]
0x140016b2b  mov     [rsp+80h+var_58], rax
0x140016b30  mov     [rsp+80h+var_60], r8
0x140016b35  lea     r8, [rbp+var_40]
0x140016b39  call    PipeTryWriteDeferred
0x140016b3e  mov     ebx, eax
0x140016b40  test    eax, eax
0x140016b42  js      loc_140016C19
0x140016b48  mov     r8d, dword ptr [rbp+Size]; Size
0x140016b4c  lea     rdx, [rbp+Src]; Src
0x140016b50  mov     rcx, [rbp+var_20+8]; void *
0x140016b54  nop
0x140016b55  call    memmove
0x140016b5a  nop
0x140016b5b  jmp     loc_140016C19
0x140016b60  mov     ecx, [r14+8]
0x140016b64  cmp     [rdx+38h], rcx
0x140016b68  jnb     loc_140016C17
0x140016b6e  sub     ecx, [rdi+38h]
0x140016b71  lea     rax, [rbp+Src]
0x140016b75  mov     r9b, [rsi+111h]
0x140016b7c  lea     r8, [rbp+var_40]
0x140016b80  mov     [rsp+80h+var_50], rax
0x140016b85  mov     edx, 1
0x140016b8a  lea     rax, [rbp+var_38]
0x140016b8e  mov     [rbp+var_40], ecx
0x140016b91  mov     [rsp+80h+var_58], rax
0x140016b96  mov     rcx, rsi
0x140016b99  mov     [rsp+80h+var_60], r15
0x140016b9e  call    PipeTryWriteDeferred
0x140016ba3  mov     ebx, eax
0x140016ba5  test    eax, eax
0x140016ba7  js      short loc_140016C19
0x140016ba9  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140016bad  call    PipeMapChainedMdl
0x140016bb2  mov     ebx, eax
0x140016bb4  test    eax, eax
0x140016bb6  js      short loc_140016C19
0x140016bb8  mov     r8d, dword ptr [rbp+Size]; Size
0x140016bbc  lea     rdx, [rbp+Src]; Src
0x140016bc0  mov     rcx, [rbp+var_20+8]; void *
0x140016bc4  nop
0x140016bc5  call    memmove
0x140016bca  mov     r9d, [rbp+var_40]
0x140016bce  mov     r8, [rbp+var_38]
0x140016bd2  mov     edx, [rdi+38h]
0x140016bd5  mov     rcx, [rdi+8]
0x140016bd9  mov     byte ptr [rsp+80h+var_60], 0
0x140016bde  call    PipeReadWriteChainedMdl
0x140016be3  mov     ebx, eax
0x140016be5  nop
0x140016be6  test    eax, eax
0x140016be8  js      short loc_140016C19
0x140016bea  mov     ecx, [rbp+var_40]
0x140016bed  add     [rdi+38h], rcx
0x140016bf1  mov     rax, [rsi+108h]
0x140016bf8  add     [rax+8], rcx
0x140016bfc  mov     rax, [rsi+108h]
0x140016c03  inc     qword ptr [rax+18h]
0x140016c07  mov     eax, [r14+8]
0x140016c0b  mov     ecx, eax
0x140016c0d  cmp     [rdi+38h], rax
0x140016c11  jb      loc_140016B6E
0x140016c17  xor     ebx, ebx
0x140016c19  mov     eax, ebx
0x140016c1b  mov     rcx, [rbp+var_8]
0x140016c1f  xor     rcx, rsp; StackCookie
0x140016c22  call    __security_check_cookie
0x140016c27  mov     rbx, [rsp+80h+arg_18]
0x140016c2f  add     rsp, 80h
0x140016c36  pop     r15
0x140016c38  pop     r14
0x140016c3a  pop     rdi
0x140016c3b  pop     rsi
0x140016c3c  pop     rbp
0x140016c3d  retn
```
