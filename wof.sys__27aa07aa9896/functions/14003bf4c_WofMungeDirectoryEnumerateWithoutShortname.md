# WofMungeDirectoryEnumerateWithoutShortname

- ea: `0x14003bf4c`
- end: `0x14003c163`
- name: `WofMungeDirectoryEnumerateWithoutShortname`
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
- `0x140035ed0`
- `0x14003bf4c`

## pseudocode

```c
__int64 __fastcall WofMungeDirectoryEnumerateWithoutShortname(
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
    if ( v12 >= a3 - 88 )
      v12 = a3 - 88;
    if ( v8 == 60 )
    {
      v13 = (unsigned int *)(v9 + a4);
      v28 = v12 + 88;
      v14 = (void *)(v9 + a4);
      if ( a6 )
        RtlCopyToUser(v14, v7, 0x58u);
      else
        RtlCopyVolatileMemory(v14, v7, 0x58u);
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
      v18 = v11 + 22;
      v19 = v13 + 22;
      if ( a6 )
        RtlCopyToUser(v19, v18, v12);
      else
        RtlCopyVolatileMemory(v19, v18, v12);
      v10 = v12 + 88;
      v20 = (v12 + 95) & 0xFFFFFFF8;
      if ( a6 )
      {
        RtlWriteULongToUser(v13, v20);
        v10 = v12 + 88;
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
0x14003bf4c  mov     rax, rsp
0x14003bf4f  mov     [rax+20h], r9
0x14003bf53  mov     [rax+8], ecx
0x14003bf56  push    rbx
0x14003bf57  push    rsi
0x14003bf58  push    rdi
0x14003bf59  push    r12
0x14003bf5b  push    r13
0x14003bf5d  push    r14
0x14003bf5f  push    r15
0x14003bf61  sub     rsp, 40h
0x14003bf65  mov     rdi, rdx
0x14003bf68  mov     r10d, ecx
0x14003bf6b  mov     byte ptr [rax-58h], 0
0x14003bf6f  mov     [rsp+78h+arg_8], 0
0x14003bf7a  mov     ecx, r8d
0x14003bf7d  add     rcx, rdx
0x14003bf80  mov     [rsp+78h+var_48], rcx
0x14003bf85  xor     ebx, ebx
0x14003bf87  xor     edx, edx
0x14003bf89  mov     [rax+18h], edx
0x14003bf8c  mov     r14, rdi
0x14003bf8f  mov     r15b, [rsp+78h+arg_28]
0x14003bf97  mov     r13d, [r14+3Ch]
0x14003bf9b  lea     eax, [r8-58h]
0x14003bf9f  cmp     r13d, eax
0x14003bfa2  cmovnb  r13d, eax
0x14003bfa6  cmp     r10d, 3Ch ; '<'
0x14003bfaa  jnz     loc_14003C080
0x14003bfb0  lea     rsi, [rbx+r9]
0x14003bfb4  lea     eax, [r13+58h]
0x14003bfb8  mov     [rsp+78h+arg_10], eax
0x14003bfbf  mov     [rsp+78h+var_50], eax
0x14003bfc3  mov     [rsp+78h+var_58], 1
0x14003bfc8  lea     r8d, [r10+1Ch]; Size
0x14003bfcc  mov     rdx, rdi; Src
0x14003bfcf  mov     rcx, rsi; void *
0x14003bfd2  test    r15b, r15b
0x14003bfd5  jz      short loc_14003BFDE
0x14003bfd7  call    RtlCopyToUser
0x14003bfdc  jmp     short loc_14003BFE3
0x14003bfde  call    RtlCopyVolatileMemory
0x14003bfe3  mov     eax, cs:FileTag
0x14003bfe9  cmp     [r14+44h], eax
0x14003bfed  jnz     short loc_14003C030
0x14003bfef  xor     edx, edx
0x14003bff1  mov     ecx, [r14+38h]
0x14003bff5  call    WofSanitizeAttributes
0x14003bffa  lea     rcx, [rsi+38h]
0x14003bffe  test    r15b, r15b
0x14003c001  jz      short loc_14003C00C
0x14003c003  mov     edx, eax
0x14003c005  call    RtlWriteULongToUser
0x14003c00a  jmp     short loc_14003C00E
0x14003c00c  mov     [rcx], eax
0x14003c00e  cmp     cs:byte_140018454, 0
0x14003c015  jz      short loc_14003C030
0x14003c017  test    r15b, r15b
0x14003c01a  jz      short loc_14003C029
0x14003c01c  xor     edx, edx
0x14003c01e  lea     rcx, [rsi+44h]
0x14003c022  call    RtlWriteULongToUser
0x14003c027  jmp     short loc_14003C030
0x14003c029  mov     dword ptr [rsi+44h], 0
0x14003c030  lea     rdx, [r14+58h]; Src
0x14003c034  lea     rcx, [rsi+58h]; void *
0x14003c038  mov     r8d, r13d; Size
0x14003c03b  test    r15b, r15b
0x14003c03e  jz      short loc_14003C047
0x14003c040  call    RtlCopyToUser
0x14003c045  jmp     short loc_14003C04C
0x14003c047  call    RtlCopyVolatileMemory
0x14003c04c  mov     edx, [rsp+78h+arg_10]
0x14003c053  lea     eax, [rdx+7]
0x14003c056  and     eax, 0FFFFFFF8h
0x14003c059  test    r15b, r15b
0x14003c05c  jz      short loc_14003C071
0x14003c05e  mov     edx, eax
0x14003c060  mov     rcx, rsi
0x14003c063  call    RtlWriteULongToUser
0x14003c068  mov     edx, [rsp+78h+arg_10]
0x14003c06f  jmp     short loc_14003C073
0x14003c071  mov     [rsi], eax
0x14003c073  mov     [rsp+78h+var_58], 0
0x14003c078  mov     r9, [rsp+78h+arg_18]
0x14003c080  mov     [rsp+78h+var_58], 1
0x14003c085  cmp     dword ptr [rdi], 0
0x14003c088  jz      loc_14003C10F
0x14003c08e  mov     ecx, [rsp+78h+arg_20]
0x14003c095  sub     ecx, ebx
0x14003c097  lea     esi, [rdx+7]
0x14003c09a  and     esi, 0FFFFFFF8h
0x14003c09d  mov     r8d, esi
0x14003c0a0  cmp     esi, ecx
0x14003c0a2  cmovnb  r8d, ecx
0x14003c0a6  sub     r8d, edx; Size
0x14003c0a9  lea     ecx, [rdx+rbx]
0x14003c0ac  add     rcx, r9; void *
0x14003c0af  xor     edx, edx; Val
0x14003c0b1  test    r15b, r15b
0x14003c0b4  jz      short loc_14003C0BD
0x14003c0b6  call    RtlSetUserMemory
0x14003c0bb  jmp     short loc_14003C0C2
0x14003c0bd  call    RtlSetVolatileMemory
0x14003c0c2  mov     [rsp+78h+var_58], 0
0x14003c0c7  add     ebx, esi
0x14003c0c9  mov     [rsp+78h+var_54], ebx
0x14003c0cd  mov     eax, [rdi]
0x14003c0cf  add     rdi, rax
0x14003c0d2  mov     [rsp+78h+var_40], rdi
0x14003c0d7  mov     r14, rdi
0x14003c0da  mov     rcx, [rsp+78h+var_48]
0x14003c0df  cmp     rdi, rcx
0x14003c0e2  jnb     short loc_14003C13A
0x14003c0e4  cmp     ebx, [rsp+78h+arg_20]
0x14003c0eb  jnb     short loc_14003C13A
0x14003c0ed  mov     r8d, ecx
0x14003c0f0  sub     r8d, edi
0x14003c0f3  mov     edx, [rsp+78h+arg_10]
0x14003c0fa  mov     r9, [rsp+78h+arg_18]
0x14003c102  mov     r10d, [rsp+78h+arg_0]
0x14003c10a  jmp     loc_14003BF97
0x14003c10f  lea     rax, [rbx+r9]
0x14003c113  test    r15b, r15b
0x14003c116  jz      short loc_14003C124
0x14003c118  xor     edx, edx
0x14003c11a  mov     rcx, rax
0x14003c11d  call    RtlWriteULongToUser
0x14003c122  jmp     short loc_14003C12A
0x14003c124  mov     dword ptr [rax], 0
0x14003c12a  mov     [rsp+78h+var_58], 0
0x14003c12f  add     ebx, [rsp+78h+arg_10]
0x14003c136  mov     [rsp+78h+var_54], ebx
0x14003c13a  mov     rax, [rsp+78h+arg_30]
0x14003c142  mov     [rax], ebx
0x14003c144  mov     eax, [rsp+78h+arg_8]
0x14003c14b  jmp     short loc_14003C152
0x14003c14d  mov     eax, 0C00000E8h
0x14003c152  add     rsp, 40h
0x14003c156  pop     r15
0x14003c158  pop     r14
0x14003c15a  pop     r13
0x14003c15c  pop     r12
0x14003c15e  pop     rdi
0x14003c15f  pop     rsi
0x14003c160  pop     rbx
0x14003c161  retn
0x14003f0dc  push    rbp
0x14003f0de  sub     rsp, 20h
0x14003f0e2  mov     rbp, rdx
0x14003f0e5  xor     eax, eax
0x14003f0e7  cmp     [rbp+20h], al
0x14003f0ea  setnz   al
0x14003f0ed  add     rsp, 20h
0x14003f0f1  pop     rbp
0x14003f0f2  retn
```
