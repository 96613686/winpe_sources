# WofMungeDirectoryEnumerateWithShortname

- ea: `0x14003e068`
- end: `0x14003e2b8`
- name: `WofMungeDirectoryEnumerateWithShortname`
- size: `592`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140036e20`

## callees

- `0x140011590`
- `0x1400115b0`
- `0x140022fcc`
- `0x1400230a8`
- `0x140023198`
- `0x140035e80`
- `0x14003e068`

## pseudocode

```c
__int64 __fastcall WofMungeDirectoryEnumerateWithShortname(
        int a1,
        _DWORD *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        char a6,
        _DWORD *a7)
{
  _DWORD *v7; // rdi
  int v8; // r10d
  __int64 v9; // rbx
  unsigned int v10; // edx
  _DWORD *v11; // r14
  unsigned int v12; // r13d
  unsigned int *v13; // rsi
  void *v14; // rcx
  void *v15; // rcx
  __int64 v16; // r8
  int v17; // eax
  int *v18; // rcx
  size_t v19; // r8
  void *v20; // rdx
  void *v21; // rcx
  void *v22; // rdx
  void *v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // esi
  unsigned int v26; // r8d
  size_t v27; // r8
  void *v28; // rcx
  unsigned __int64 v30; // [rsp+30h] [rbp-48h]
  unsigned int v32; // [rsp+90h] [rbp+18h]
  __int64 v33; // [rsp+98h] [rbp+20h]

  v33 = a4;
  v7 = a2;
  v8 = a1;
  v30 = (unsigned __int64)a2 + a3;
  v9 = 0;
  v10 = 0;
  v32 = 0;
  v11 = v7;
  while ( 1 )
  {
    v12 = v11[15];
    if ( v12 >= a3 - 114 )
      v12 = a3 - 114;
    if ( v8 == 63 )
    {
      v13 = (unsigned int *)(v9 + a4);
      v32 = v12 + 114;
      v14 = (void *)(v9 + a4);
      if ( a6 )
        RtlCopyToUser(v14, v7, 0x5Au);
      else
        RtlCopyVolatileMemory(v14, v7, 0x5Au);
      v15 = (char *)v13 + 89;
      if ( a6 )
        RtlSetUserMemory(v15);
      else
        RtlSetVolatileMemory(v15, 0, 0x19u);
      if ( v11[17] == FileTag )
      {
        v17 = WofSanitizeAttributes((unsigned int)v11[14], 0, v16);
        v18 = (int *)(v13 + 14);
        if ( a6 )
          RtlWriteULongToUser(v18, v17);
        else
          *v18 = v17;
        if ( byte_140018454 )
        {
          if ( a6 )
            RtlWriteULongToUser(v13 + 17, 0);
          else
            v13[17] = 0;
        }
      }
      v19 = *((char *)v11 + 88);
      v20 = (char *)v11 + 90;
      v21 = (char *)v13 + 90;
      if ( a6 )
        RtlCopyToUser(v21, v20, v19);
      else
        RtlCopyVolatileMemory(v21, v20, v19);
      v22 = (char *)v11 + 114;
      v23 = (char *)v13 + 114;
      if ( a6 )
        RtlCopyToUser(v23, v22, v12);
      else
        RtlCopyVolatileMemory(v23, v22, v12);
      v10 = v12 + 114;
      v24 = (v12 + 121) & 0xFFFFFFF8;
      if ( a6 )
      {
        RtlWriteULongToUser(v13, v24);
        v10 = v12 + 114;
      }
      else
      {
        *v13 = v24;
      }
      a4 = v33;
    }
    if ( !*v7 )
      break;
    v25 = (v10 + 7) & 0xFFFFFFF8;
    v26 = v25;
    if ( v25 >= a5 - (unsigned int)v9 )
      v26 = a5 - v9;
    v27 = v26 - v10;
    v28 = (void *)(a4 + v10 + (unsigned int)v9);
    if ( a6 )
      RtlSetUserMemory(v28);
    else
      RtlSetVolatileMemory(v28, 0, v27);
    v9 = v25 + (unsigned int)v9;
    v7 = (_DWORD *)((char *)v7 + (unsigned int)*v7);
    v11 = v7;
    if ( (unsigned __int64)v7 >= v30 || (unsigned int)v9 >= a5 )
      goto LABEL_42;
    a3 = v30 - (_DWORD)v7;
    v10 = v32;
    a4 = v33;
    v8 = a1;
  }
  if ( a6 )
    RtlWriteULongToUser((_DWORD *)(v9 + a4), 0);
  else
    *(_DWORD *)(v9 + a4) = 0;
  LODWORD(v9) = v32 + v9;
LABEL_42:
  *a7 = v9;
  return 0;
}

```

## disassembly

```asm
0x14003e068  mov     rax, rsp
0x14003e06b  mov     [rax+20h], r9
0x14003e06f  mov     [rax+8], ecx
0x14003e072  push    rbx
0x14003e073  push    rsi
0x14003e074  push    rdi
0x14003e075  push    r12
0x14003e077  push    r13
0x14003e079  push    r14
0x14003e07b  push    r15
0x14003e07d  sub     rsp, 40h
0x14003e081  mov     rdi, rdx
0x14003e084  mov     r10d, ecx
0x14003e087  mov     byte ptr [rax-58h], 0
0x14003e08b  mov     [rsp+78h+arg_8], 0
0x14003e096  mov     ecx, r8d
0x14003e099  add     rcx, rdx
0x14003e09c  mov     [rsp+78h+var_48], rcx
0x14003e0a1  xor     ebx, ebx
0x14003e0a3  xor     edx, edx
0x14003e0a5  mov     [rax+18h], edx
0x14003e0a8  mov     r14, rdi
0x14003e0ab  mov     r15b, [rsp+78h+arg_28]
0x14003e0b3  mov     r13d, [r14+3Ch]
0x14003e0b7  lea     eax, [r8-72h]
0x14003e0bb  cmp     r13d, eax
0x14003e0be  cmovnb  r13d, eax
0x14003e0c2  cmp     r10d, 3Fh ; '?'
0x14003e0c6  jnz     loc_14003E1D5
0x14003e0cc  lea     rsi, [rbx+r9]
0x14003e0d0  lea     eax, [r13+72h]
0x14003e0d4  mov     [rsp+78h+arg_10], eax
0x14003e0db  mov     [rsp+78h+var_50], eax
0x14003e0df  mov     [rsp+78h+var_58], 1
0x14003e0e4  lea     r8d, [r10+1Bh]; Size
0x14003e0e8  mov     rdx, rdi; Src
0x14003e0eb  mov     rcx, rsi; void *
0x14003e0ee  test    r15b, r15b
0x14003e0f1  jz      short loc_14003E0FA
0x14003e0f3  call    RtlCopyToUser
0x14003e0f8  jmp     short loc_14003E0FF
0x14003e0fa  call    RtlCopyVolatileMemory
0x14003e0ff  lea     rcx, [rsi+59h]; void *
0x14003e103  xor     edx, edx; Val
0x14003e105  lea     r8d, [rdx+19h]; Size
0x14003e109  test    r15b, r15b
0x14003e10c  jz      short loc_14003E115
0x14003e10e  call    RtlSetUserMemory
0x14003e113  jmp     short loc_14003E11A
0x14003e115  call    RtlSetVolatileMemory
0x14003e11a  mov     eax, cs:FileTag
0x14003e120  cmp     [r14+44h], eax
0x14003e124  jnz     short loc_14003E167
0x14003e126  xor     edx, edx
0x14003e128  mov     ecx, [r14+38h]
0x14003e12c  call    WofSanitizeAttributes
0x14003e131  lea     rcx, [rsi+38h]
0x14003e135  test    r15b, r15b
0x14003e138  jz      short loc_14003E143
0x14003e13a  mov     edx, eax
0x14003e13c  call    RtlWriteULongToUser
0x14003e141  jmp     short loc_14003E145
0x14003e143  mov     [rcx], eax
0x14003e145  cmp     cs:byte_140018454, 0
0x14003e14c  jz      short loc_14003E167
0x14003e14e  test    r15b, r15b
0x14003e151  jz      short loc_14003E160
0x14003e153  xor     edx, edx
0x14003e155  lea     rcx, [rsi+44h]
0x14003e159  call    RtlWriteULongToUser
0x14003e15e  jmp     short loc_14003E167
0x14003e160  mov     dword ptr [rsi+44h], 0
0x14003e167  movsx   r8, byte ptr [r14+58h]; Size
0x14003e16c  lea     rdx, [r14+5Ah]; Src
0x14003e170  lea     rcx, [rsi+5Ah]; void *
0x14003e174  test    r15b, r15b
0x14003e177  jz      short loc_14003E180
0x14003e179  call    RtlCopyToUser
0x14003e17e  jmp     short loc_14003E185
0x14003e180  call    RtlCopyVolatileMemory
0x14003e185  lea     rdx, [r14+72h]; Src
0x14003e189  lea     rcx, [rsi+72h]; void *
0x14003e18d  mov     r8d, r13d; Size
0x14003e190  test    r15b, r15b
0x14003e193  jz      short loc_14003E19C
0x14003e195  call    RtlCopyToUser
0x14003e19a  jmp     short loc_14003E1A1
0x14003e19c  call    RtlCopyVolatileMemory
0x14003e1a1  mov     edx, [rsp+78h+arg_10]
0x14003e1a8  lea     eax, [rdx+7]
0x14003e1ab  and     eax, 0FFFFFFF8h
0x14003e1ae  test    r15b, r15b
0x14003e1b1  jz      short loc_14003E1C6
0x14003e1b3  mov     edx, eax
0x14003e1b5  mov     rcx, rsi
0x14003e1b8  call    RtlWriteULongToUser
0x14003e1bd  mov     edx, [rsp+78h+arg_10]
0x14003e1c4  jmp     short loc_14003E1C8
0x14003e1c6  mov     [rsi], eax
0x14003e1c8  mov     [rsp+78h+var_58], 0
0x14003e1cd  mov     r9, [rsp+78h+arg_18]
0x14003e1d5  mov     [rsp+78h+var_58], 1
0x14003e1da  cmp     dword ptr [rdi], 0
0x14003e1dd  jz      loc_14003E264
0x14003e1e3  mov     ecx, [rsp+78h+arg_20]
0x14003e1ea  sub     ecx, ebx
0x14003e1ec  lea     esi, [rdx+7]
0x14003e1ef  and     esi, 0FFFFFFF8h
0x14003e1f2  mov     r8d, esi
0x14003e1f5  cmp     esi, ecx
0x14003e1f7  cmovnb  r8d, ecx
0x14003e1fb  sub     r8d, edx; Size
0x14003e1fe  lea     ecx, [rdx+rbx]
0x14003e201  add     rcx, r9; void *
0x14003e204  xor     edx, edx; Val
0x14003e206  test    r15b, r15b
0x14003e209  jz      short loc_14003E212
0x14003e20b  call    RtlSetUserMemory
0x14003e210  jmp     short loc_14003E217
0x14003e212  call    RtlSetVolatileMemory
0x14003e217  mov     [rsp+78h+var_58], 0
0x14003e21c  add     ebx, esi
0x14003e21e  mov     [rsp+78h+var_54], ebx
0x14003e222  mov     eax, [rdi]
0x14003e224  add     rdi, rax
0x14003e227  mov     [rsp+78h+var_40], rdi
0x14003e22c  mov     r14, rdi
0x14003e22f  mov     rcx, [rsp+78h+var_48]
0x14003e234  cmp     rdi, rcx
0x14003e237  jnb     short loc_14003E28F
0x14003e239  cmp     ebx, [rsp+78h+arg_20]
0x14003e240  jnb     short loc_14003E28F
0x14003e242  mov     r8d, ecx
0x14003e245  sub     r8d, edi
0x14003e248  mov     edx, [rsp+78h+arg_10]
0x14003e24f  mov     r9, [rsp+78h+arg_18]
0x14003e257  mov     r10d, [rsp+78h+arg_0]
0x14003e25f  jmp     loc_14003E0B3
0x14003e264  lea     rax, [rbx+r9]
0x14003e268  test    r15b, r15b
0x14003e26b  jz      short loc_14003E279
0x14003e26d  xor     edx, edx
0x14003e26f  mov     rcx, rax
0x14003e272  call    RtlWriteULongToUser
0x14003e277  jmp     short loc_14003E27F
0x14003e279  mov     dword ptr [rax], 0
0x14003e27f  mov     [rsp+78h+var_58], 0
0x14003e284  add     ebx, [rsp+78h+arg_10]
0x14003e28b  mov     [rsp+78h+var_54], ebx
0x14003e28f  mov     rax, [rsp+78h+arg_30]
0x14003e297  mov     [rax], ebx
0x14003e299  mov     eax, [rsp+78h+arg_8]
0x14003e2a0  jmp     short loc_14003E2A7
0x14003e2a2  mov     eax, 0C00000E8h
0x14003e2a7  add     rsp, 40h
0x14003e2ab  pop     r15
0x14003e2ad  pop     r14
0x14003e2af  pop     r13
0x14003e2b1  pop     r12
0x14003e2b3  pop     rdi
0x14003e2b4  pop     rsi
0x14003e2b5  pop     rbx
0x14003e2b6  retn
0x14003f0aa  push    rbp
0x14003f0ac  sub     rsp, 20h
0x14003f0b0  mov     rbp, rdx
0x14003f0b3  xor     eax, eax
0x14003f0b5  cmp     [rbp+20h], al
0x14003f0b8  setnz   al
0x14003f0bb  add     rsp, 20h
0x14003f0bf  pop     rbp
0x14003f0c0  retn
```
