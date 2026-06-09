# SlbNatOptionalFindAndDeleteUnusedEntry

- ea: `0x140014b38`
- end: `0x140014ccb`
- name: `SlbNatOptionalFindAndDeleteUnusedEntry`
- size: `403`
- prototype: `char __fastcall(__int64, _QWORD *, void ***, char)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000b658`

## callees

- `0x140014b38`
- `0x1400191c4`
- `0x140019798`
- `0x14001f020`
- `0x14001f140`
- `0x1400310f8`

## pseudocode

```c
char __fastcall SlbNatOptionalFindAndDeleteUnusedEntry(__int64 a1, _QWORD *a2, void ***a3, char a4)
{
  _QWORD *v6; // r13
  __int64 v7; // rbx
  __int16 v8; // r15
  size_t v9; // rbp
  char v10; // bl
  int v11; // r8d
  void ***v12; // rbx
  int v13; // r8d
  void **v14; // rax
  void **v15; // rcx
  int v17; // [rsp+28h] [rbp-70h]
  char v18; // [rsp+40h] [rbp-58h] BYREF
  char v19; // [rsp+41h] [rbp-57h]
  _OWORD v20[5]; // [rsp+48h] [rbp-50h] BYREF

  v19 = a4;
  v20[0] = 0;
  v18 = 0;
  v6 = (_QWORD *)(a1 + 24);
  while ( 1 )
  {
    if ( a2 == v6 )
      return 0;
    v7 = a2[10];
    if ( v7 )
    {
      v8 = *((_WORD *)a2 + 26);
      v9 = 4;
      if ( v8 != 2 )
        v9 = 16;
      if ( !memcmp(a3 + 7, a2 + 7, v9) )
      {
        v10 = *(_BYTE *)(v7 + 32);
        if ( *((_BYTE *)a3[10] + 32) == v10 )
        {
          memmove(v20, a2 + 7, v9);
          v11 = 4;
          LOBYTE(v17) = v10;
          if ( v8 != 2 )
            v11 = 16;
          if ( (int)WinNatLibDeterminePortUsage(
                      (_DWORD)qword_1400263D8,
                      (unsigned int)v20,
                      v11,
                      *((unsigned __int16 *)a2 + 36),
                      *((_WORD *)a2 + 37),
                      v17,
                      (__int64)&v18) >= 0 )
          {
            if ( v19 )
            {
              if ( v18 )
                goto LABEL_22;
              v12 = (void ***)a2;
            }
            else
            {
              v12 = a3;
            }
            if ( v12 )
            {
              v13 = 4;
              if ( *((_WORD *)v12 + 26) != 2 )
                v13 = 16;
              if ( (int)WinNatLibTryDisableAddress(
                          (_DWORD)qword_1400263D8,
                          (unsigned int)v20,
                          v13,
                          *((unsigned __int16 *)v12 + 36),
                          *((_WORD *)v12 + 37)) >= 0 )
                break;
            }
          }
        }
      }
    }
LABEL_22:
    a2 = (_QWORD *)*a2;
  }
  v14 = *v12;
  if ( (*v12)[1] != v12 || (v15 = v12[1], *v15 != v12) )
    __fastfail(3u);
  *v15 = v14;
  v14[1] = v15;
  SlbNatDeleteExternalAddress(v12);
  return 1;
}

```

## disassembly

```asm
0x140014b38  mov     [rsp+arg_18], rbx
0x140014b3d  push    rbp
0x140014b3e  push    rsi
0x140014b3f  push    rdi
0x140014b40  push    r12
0x140014b42  push    r13
0x140014b44  push    r14
0x140014b46  push    r15
0x140014b48  sub     rsp, 60h
0x140014b4c  xorps   xmm0, xmm0
0x140014b4f  mov     [rsp+98h+var_57], r9b
0x140014b54  movups  [rsp+98h+var_50], xmm0
0x140014b59  mov     rsi, r8
0x140014b5c  mov     [rsp+98h+var_58], 0
0x140014b61  mov     rdi, rdx
0x140014b64  lea     r13, [rcx+18h]
0x140014b68  mov     r14, rcx
0x140014b6b  mov     r12d, 10h
0x140014b71  cmp     rdi, r13
0x140014b74  jz      loc_140014CB0
0x140014b7a  mov     rbx, [rdi+50h]
0x140014b7e  test    rbx, rbx
0x140014b81  jz      loc_140014CA1
0x140014b87  movzx   r15d, word ptr [rdi+34h]
0x140014b8c  lea     rcx, [rsi+38h]; Buf1
0x140014b90  cmp     r15w, 2
0x140014b95  lea     rdx, [rdi+38h]; Buf2
0x140014b99  mov     ebp, 4
0x140014b9e  cmovnz  rbp, r12
0x140014ba2  mov     r8, rbp; Size
0x140014ba5  call    memcmp
0x140014baa  test    eax, eax
0x140014bac  jnz     loc_140014C9B
0x140014bb2  mov     rax, [rsi+50h]
0x140014bb6  mov     bl, [rbx+20h]
0x140014bb9  cmp     [rax+20h], bl
0x140014bbc  jnz     loc_140014C9B
0x140014bc2  mov     r8, rbp; Size
0x140014bc5  lea     rdx, [rdi+38h]; Src
0x140014bc9  lea     rcx, [rsp+98h+var_50]; void *
0x140014bce  call    memmove
0x140014bd3  movzx   r9d, word ptr [rdi+48h]
0x140014bd8  lea     rax, [rsp+98h+var_58]
0x140014bdd  mov     rcx, cs:qword_1400263D8
0x140014be4  lea     rdx, [rsp+98h+var_50]
0x140014be9  mov     [rsp+98h+var_68], rax
0x140014bee  mov     r8d, 4
0x140014bf4  movzx   eax, word ptr [rdi+4Ah]
0x140014bf8  cmp     r15w, 2
0x140014bfd  mov     [rsp+98h+var_70], bl
0x140014c01  mov     [rsp+98h+var_78], ax
0x140014c06  lea     r12d, [r8+0Ch]
0x140014c0a  cmovnz  r8d, r12d
0x140014c0e  call    WinNatLibDeterminePortUsage
0x140014c13  test    eax, eax
0x140014c15  js      loc_140014CA1
0x140014c1b  cmp     [rsp+98h+var_57], 0
0x140014c20  jnz     short loc_140014C27
0x140014c22  mov     rbx, rsi
0x140014c25  jmp     short loc_140014C31
0x140014c27  cmp     [rsp+98h+var_58], 0
0x140014c2c  jnz     short loc_140014CA1
0x140014c2e  mov     rbx, rdi
0x140014c31  test    rbx, rbx
0x140014c34  jz      short loc_140014CA1
0x140014c36  mov     rax, [rdi+50h]
0x140014c3a  lea     rdx, [rsp+98h+var_50]
0x140014c3f  cmp     word ptr [rbx+34h], 2
0x140014c44  mov     r8d, 4
0x140014c4a  movzx   r9d, word ptr [rbx+48h]
0x140014c4f  mov     rcx, cs:qword_1400263D8
0x140014c56  cmovnz  r8d, r12d
0x140014c5a  mov     al, [rax+20h]
0x140014c5d  mov     [rsp+98h+var_70], al
0x140014c61  movzx   eax, word ptr [rbx+4Ah]
0x140014c65  mov     [rsp+98h+var_78], ax
0x140014c6a  call    WinNatLibTryDisableAddress
0x140014c6f  test    eax, eax
0x140014c71  js      short loc_140014CA1
0x140014c73  mov     rax, [rbx]
0x140014c76  cmp     [rax+8], rbx
0x140014c7a  jnz     short loc_140014CA9
0x140014c7c  mov     rcx, [rbx+8]
0x140014c80  cmp     [rcx], rbx
0x140014c83  jnz     short loc_140014CA9
0x140014c85  mov     [rcx], rax
0x140014c88  mov     rdx, r14
0x140014c8b  mov     [rax+8], rcx
0x140014c8f  mov     rcx, rbx; P
0x140014c92  call    SlbNatDeleteExternalAddress
0x140014c97  mov     al, 1
0x140014c99  jmp     short loc_140014CB2
0x140014c9b  mov     r12d, 10h
0x140014ca1  mov     rdi, [rdi]
0x140014ca4  jmp     loc_140014B71
0x140014ca9  mov     ecx, 3
0x140014cae  int     29h; Win8: RtlFailFast(ecx)
0x140014cb0  xor     al, al
0x140014cb2  mov     rbx, [rsp+98h+arg_18]
0x140014cba  add     rsp, 60h
0x140014cbe  pop     r15
0x140014cc0  pop     r14
0x140014cc2  pop     r13
0x140014cc4  pop     r12
0x140014cc6  pop     rdi
0x140014cc7  pop     rsi
0x140014cc8  pop     rbp
0x140014cc9  retn
```
