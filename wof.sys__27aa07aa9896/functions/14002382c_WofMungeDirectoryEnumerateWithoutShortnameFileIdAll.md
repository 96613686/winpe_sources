# WofMungeDirectoryEnumerateWithoutShortnameFileIdAll

- ea: `0x14002382c`
- end: `0x140023a43`
- name: `WofMungeDirectoryEnumerateWithoutShortnameFileIdAll`
- size: `535`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140036e70`

## callees

- `0x140011590`
- `0x1400115b0`
- `0x140022fcc`
- `0x1400230a8`
- `0x140023198`
- `0x14002382c`
- `0x140035ed0`

## pseudocode

```c
__int64 __fastcall WofMungeDirectoryEnumerateWithoutShortnameFileIdAll(
        int a1,
        unsigned int *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        char a6,
        _DWORD *a7)
{
  unsigned int *v7; // rdi
  int v8; // r10d
  __int64 v9; // rbx
  unsigned int v10; // edx
  unsigned int *v11; // r14
  unsigned int v12; // r13d
  unsigned int *v13; // rsi
  void *v14; // rcx
  __int64 v15; // r8
  int v16; // eax
  int *v17; // rcx
  void *v18; // rdx
  void *v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  size_t v23; // r8
  void *v24; // rcx
  unsigned __int64 v26; // [rsp+30h] [rbp-48h]
  unsigned int v28; // [rsp+90h] [rbp+18h]
  __int64 v29; // [rsp+98h] [rbp+20h]

  v29 = a4;
  v7 = a2;
  v8 = a1;
  v26 = (unsigned __int64)a2 + a3;
  v9 = 0;
  v10 = 0;
  v28 = 0;
  v11 = v7;
  while ( 1 )
  {
    v12 = v11[15];
    if ( v12 >= a3 - 96 )
      v12 = a3 - 96;
    if ( v8 == 80 )
    {
      v13 = (unsigned int *)(v9 + a4);
      v28 = v12 + 96;
      v14 = (void *)(v9 + a4);
      if ( a6 )
        RtlCopyToUser(v14, v7, 0x60u);
      else
        RtlCopyVolatileMemory(v14, v7, 0x60u);
      if ( v11[17] == FileTag )
      {
        v16 = WofSanitizeAttributes(v11[14], 0, v15);
        v17 = (int *)(v13 + 14);
        if ( a6 )
          RtlWriteULongToUser(v17, v16);
        else
          *v17 = v16;
        if ( byte_140018454 )
        {
          if ( a6 )
            RtlWriteULongToUser(v13 + 17, 0);
          else
            v13[17] = 0;
        }
      }
      v18 = v11 + 24;
      v19 = v13 + 24;
      if ( a6 )
        RtlCopyToUser(v19, v18, v12);
      else
        RtlCopyVolatileMemory(v19, v18, v12);
      v10 = v12 + 96;
      v20 = (v12 + 103) & 0xFFFFFFF8;
      if ( a6 )
      {
        RtlWriteULongToUser(v13, v20);
        v10 = v12 + 96;
      }
      else
      {
        *v13 = v20;
      }
      a4 = v29;
    }
    if ( !*v7 )
      break;
    v21 = (v10 + 7) & 0xFFFFFFF8;
    v22 = v21;
    if ( v21 >= a5 - (unsigned int)v9 )
      v22 = a5 - v9;
    v23 = v22 - v10;
    v24 = (void *)(a4 + v10 + (unsigned int)v9);
    if ( a6 )
      RtlSetUserMemory(v24);
    else
      RtlSetVolatileMemory(v24, 0, v23);
    v9 = v21 + (unsigned int)v9;
    v7 = (unsigned int *)((char *)v7 + *v7);
    v11 = v7;
    if ( (unsigned __int64)v7 >= v26 || (unsigned int)v9 >= a5 )
      goto LABEL_36;
    a3 = v26 - (_DWORD)v7;
    v10 = v28;
    a4 = v29;
    v8 = a1;
  }
  if ( a6 )
    RtlWriteULongToUser((_DWORD *)(v9 + a4), 0);
  else
    *(_DWORD *)(v9 + a4) = 0;
  LODWORD(v9) = v28 + v9;
LABEL_36:
  *a7 = v9;
  return 0;
}

```

## disassembly

```asm
0x14002382c  mov     rax, rsp
0x14002382f  mov     [rax+20h], r9
0x140023833  mov     [rax+8], ecx
0x140023836  push    rbx
0x140023837  push    rsi
0x140023838  push    rdi
0x140023839  push    r12
0x14002383b  push    r13
0x14002383d  push    r14
0x14002383f  push    r15
0x140023841  sub     rsp, 40h
0x140023845  mov     rdi, rdx
0x140023848  mov     r10d, ecx
0x14002384b  mov     byte ptr [rax-58h], 0
0x14002384f  mov     [rsp+78h+arg_8], 0
0x14002385a  mov     ecx, r8d
0x14002385d  add     rcx, rdx
0x140023860  mov     [rsp+78h+var_48], rcx
0x140023865  xor     ebx, ebx
0x140023867  xor     edx, edx
0x140023869  mov     [rax+18h], edx
0x14002386c  mov     r14, rdi
0x14002386f  mov     r15b, [rsp+78h+arg_28]
0x140023877  mov     r13d, [r14+3Ch]
0x14002387b  lea     eax, [r8-60h]
0x14002387f  cmp     r13d, eax
0x140023882  cmovnb  r13d, eax
0x140023886  cmp     r10d, 50h ; 'P'
0x14002388a  jnz     loc_140023960
0x140023890  lea     rsi, [rbx+r9]
0x140023894  lea     eax, [r13+60h]
0x140023898  mov     [rsp+78h+arg_10], eax
0x14002389f  mov     [rsp+78h+var_50], eax
0x1400238a3  mov     [rsp+78h+var_58], 1
0x1400238a8  lea     r8d, [r10+10h]; Size
0x1400238ac  mov     rdx, rdi; Src
0x1400238af  mov     rcx, rsi; void *
0x1400238b2  test    r15b, r15b
0x1400238b5  jz      short loc_1400238BE
0x1400238b7  call    RtlCopyToUser
0x1400238bc  jmp     short loc_1400238C3
0x1400238be  call    RtlCopyVolatileMemory
0x1400238c3  mov     eax, cs:FileTag
0x1400238c9  cmp     [r14+44h], eax
0x1400238cd  jnz     short loc_140023910
0x1400238cf  xor     edx, edx
0x1400238d1  mov     ecx, [r14+38h]
0x1400238d5  call    WofSanitizeAttributes
0x1400238da  lea     rcx, [rsi+38h]
0x1400238de  test    r15b, r15b
0x1400238e1  jz      short loc_1400238EC
0x1400238e3  mov     edx, eax
0x1400238e5  call    RtlWriteULongToUser
0x1400238ea  jmp     short loc_1400238EE
0x1400238ec  mov     [rcx], eax
0x1400238ee  cmp     cs:byte_140018454, 0
0x1400238f5  jz      short loc_140023910
0x1400238f7  test    r15b, r15b
0x1400238fa  jz      short loc_140023909
0x1400238fc  xor     edx, edx
0x1400238fe  lea     rcx, [rsi+44h]
0x140023902  call    RtlWriteULongToUser
0x140023907  jmp     short loc_140023910
0x140023909  mov     dword ptr [rsi+44h], 0
0x140023910  lea     rdx, [r14+60h]; Src
0x140023914  lea     rcx, [rsi+60h]; void *
0x140023918  mov     r8d, r13d; Size
0x14002391b  test    r15b, r15b
0x14002391e  jz      short loc_140023927
0x140023920  call    RtlCopyToUser
0x140023925  jmp     short loc_14002392C
0x140023927  call    RtlCopyVolatileMemory
0x14002392c  mov     edx, [rsp+78h+arg_10]
0x140023933  lea     eax, [rdx+7]
0x140023936  and     eax, 0FFFFFFF8h
0x140023939  test    r15b, r15b
0x14002393c  jz      short loc_140023951
0x14002393e  mov     edx, eax
0x140023940  mov     rcx, rsi
0x140023943  call    RtlWriteULongToUser
0x140023948  mov     edx, [rsp+78h+arg_10]
0x14002394f  jmp     short loc_140023953
0x140023951  mov     [rsi], eax
0x140023953  mov     [rsp+78h+var_58], 0
0x140023958  mov     r9, [rsp+78h+arg_18]
0x140023960  mov     [rsp+78h+var_58], 1
0x140023965  cmp     dword ptr [rdi], 0
0x140023968  jz      loc_1400239EF
0x14002396e  mov     ecx, [rsp+78h+arg_20]
0x140023975  sub     ecx, ebx
0x140023977  lea     esi, [rdx+7]
0x14002397a  and     esi, 0FFFFFFF8h
0x14002397d  mov     r8d, esi
0x140023980  cmp     esi, ecx
0x140023982  cmovnb  r8d, ecx
0x140023986  sub     r8d, edx; Size
0x140023989  lea     ecx, [rdx+rbx]
0x14002398c  add     rcx, r9; void *
0x14002398f  xor     edx, edx; Val
0x140023991  test    r15b, r15b
0x140023994  jz      short loc_14002399D
0x140023996  call    RtlSetUserMemory
0x14002399b  jmp     short loc_1400239A2
0x14002399d  call    RtlSetVolatileMemory
0x1400239a2  mov     [rsp+78h+var_58], 0
0x1400239a7  add     ebx, esi
0x1400239a9  mov     [rsp+78h+var_54], ebx
0x1400239ad  mov     eax, [rdi]
0x1400239af  add     rdi, rax
0x1400239b2  mov     [rsp+78h+var_40], rdi
0x1400239b7  mov     r14, rdi
0x1400239ba  mov     rcx, [rsp+78h+var_48]
0x1400239bf  cmp     rdi, rcx
0x1400239c2  jnb     short loc_140023A1A
0x1400239c4  cmp     ebx, [rsp+78h+arg_20]
0x1400239cb  jnb     short loc_140023A1A
0x1400239cd  mov     r8d, ecx
0x1400239d0  sub     r8d, edi
0x1400239d3  mov     edx, [rsp+78h+arg_10]
0x1400239da  mov     r9, [rsp+78h+arg_18]
0x1400239e2  mov     r10d, [rsp+78h+arg_0]
0x1400239ea  jmp     loc_140023877
0x1400239ef  lea     rax, [rbx+r9]
0x1400239f3  test    r15b, r15b
0x1400239f6  jz      short loc_140023A04
0x1400239f8  xor     edx, edx
0x1400239fa  mov     rcx, rax
0x1400239fd  call    RtlWriteULongToUser
0x140023a02  jmp     short loc_140023A0A
0x140023a04  mov     dword ptr [rax], 0
0x140023a0a  mov     [rsp+78h+var_58], 0
0x140023a0f  add     ebx, [rsp+78h+arg_10]
0x140023a16  mov     [rsp+78h+var_54], ebx
0x140023a1a  mov     rax, [rsp+78h+arg_30]
0x140023a22  mov     [rax], ebx
0x140023a24  mov     eax, [rsp+78h+arg_8]
0x140023a2b  jmp     short loc_140023A32
0x140023a2d  mov     eax, 0C00000E8h
0x140023a32  add     rsp, 40h
0x140023a36  pop     r15
0x140023a38  pop     r14
0x140023a3a  pop     r13
0x140023a3c  pop     r12
0x140023a3e  pop     rdi
0x140023a3f  pop     rsi
0x140023a40  pop     rbx
0x140023a41  retn
0x14003f118  push    rbp
0x14003f11a  sub     rsp, 20h
0x14003f11e  mov     rbp, rdx
0x14003f121  xor     eax, eax
0x14003f123  cmp     [rbp+20h], al
0x14003f126  setnz   al
0x14003f129  add     rsp, 20h
0x14003f12d  pop     rbp
0x14003f12e  retn
```
