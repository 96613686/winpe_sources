# WofMungeDirectoryEnumerateWithoutShortname

- ea: `0x14003befc`
- end: `0x14003c113`
- name: `WofMungeDirectoryEnumerateWithoutShortname`
- size: `535`
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
- `0x14003befc`

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
0x14003befc  mov     rax, rsp
0x14003beff  mov     [rax+20h], r9
0x14003bf03  mov     [rax+8], ecx
0x14003bf06  push    rbx
0x14003bf07  push    rsi
0x14003bf08  push    rdi
0x14003bf09  push    r12
0x14003bf0b  push    r13
0x14003bf0d  push    r14
0x14003bf0f  push    r15
0x14003bf11  sub     rsp, 40h
0x14003bf15  mov     rdi, rdx
0x14003bf18  mov     r10d, ecx
0x14003bf1b  mov     byte ptr [rax-58h], 0
0x14003bf1f  mov     [rsp+78h+arg_8], 0
0x14003bf2a  mov     ecx, r8d
0x14003bf2d  add     rcx, rdx
0x14003bf30  mov     [rsp+78h+var_48], rcx
0x14003bf35  xor     ebx, ebx
0x14003bf37  xor     edx, edx
0x14003bf39  mov     [rax+18h], edx
0x14003bf3c  mov     r14, rdi
0x14003bf3f  mov     r15b, [rsp+78h+arg_28]
0x14003bf47  mov     r13d, [r14+3Ch]
0x14003bf4b  lea     eax, [r8-58h]
0x14003bf4f  cmp     r13d, eax
0x14003bf52  cmovnb  r13d, eax
0x14003bf56  cmp     r10d, 3Ch ; '<'
0x14003bf5a  jnz     loc_14003C030
0x14003bf60  lea     rsi, [rbx+r9]
0x14003bf64  lea     eax, [r13+58h]
0x14003bf68  mov     [rsp+78h+arg_10], eax
0x14003bf6f  mov     [rsp+78h+var_50], eax
0x14003bf73  mov     [rsp+78h+var_58], 1
0x14003bf78  lea     r8d, [r10+1Ch]; Size
0x14003bf7c  mov     rdx, rdi; Src
0x14003bf7f  mov     rcx, rsi; void *
0x14003bf82  test    r15b, r15b
0x14003bf85  jz      short loc_14003BF8E
0x14003bf87  call    RtlCopyToUser
0x14003bf8c  jmp     short loc_14003BF93
0x14003bf8e  call    RtlCopyVolatileMemory
0x14003bf93  mov     eax, cs:FileTag
0x14003bf99  cmp     [r14+44h], eax
0x14003bf9d  jnz     short loc_14003BFE0
0x14003bf9f  xor     edx, edx
0x14003bfa1  mov     ecx, [r14+38h]
0x14003bfa5  call    WofSanitizeAttributes
0x14003bfaa  lea     rcx, [rsi+38h]
0x14003bfae  test    r15b, r15b
0x14003bfb1  jz      short loc_14003BFBC
0x14003bfb3  mov     edx, eax
0x14003bfb5  call    RtlWriteULongToUser
0x14003bfba  jmp     short loc_14003BFBE
0x14003bfbc  mov     [rcx], eax
0x14003bfbe  cmp     cs:byte_140018454, 0
0x14003bfc5  jz      short loc_14003BFE0
0x14003bfc7  test    r15b, r15b
0x14003bfca  jz      short loc_14003BFD9
0x14003bfcc  xor     edx, edx
0x14003bfce  lea     rcx, [rsi+44h]
0x14003bfd2  call    RtlWriteULongToUser
0x14003bfd7  jmp     short loc_14003BFE0
0x14003bfd9  mov     dword ptr [rsi+44h], 0
0x14003bfe0  lea     rdx, [r14+58h]; Src
0x14003bfe4  lea     rcx, [rsi+58h]; void *
0x14003bfe8  mov     r8d, r13d; Size
0x14003bfeb  test    r15b, r15b
0x14003bfee  jz      short loc_14003BFF7
0x14003bff0  call    RtlCopyToUser
0x14003bff5  jmp     short loc_14003BFFC
0x14003bff7  call    RtlCopyVolatileMemory
0x14003bffc  mov     edx, [rsp+78h+arg_10]
0x14003c003  lea     eax, [rdx+7]
0x14003c006  and     eax, 0FFFFFFF8h
0x14003c009  test    r15b, r15b
0x14003c00c  jz      short loc_14003C021
0x14003c00e  mov     edx, eax
0x14003c010  mov     rcx, rsi
0x14003c013  call    RtlWriteULongToUser
0x14003c018  mov     edx, [rsp+78h+arg_10]
0x14003c01f  jmp     short loc_14003C023
0x14003c021  mov     [rsi], eax
0x14003c023  mov     [rsp+78h+var_58], 0
0x14003c028  mov     r9, [rsp+78h+arg_18]
0x14003c030  mov     [rsp+78h+var_58], 1
0x14003c035  cmp     dword ptr [rdi], 0
0x14003c038  jz      loc_14003C0BF
0x14003c03e  mov     ecx, [rsp+78h+arg_20]
0x14003c045  sub     ecx, ebx
0x14003c047  lea     esi, [rdx+7]
0x14003c04a  and     esi, 0FFFFFFF8h
0x14003c04d  mov     r8d, esi
0x14003c050  cmp     esi, ecx
0x14003c052  cmovnb  r8d, ecx
0x14003c056  sub     r8d, edx; Size
0x14003c059  lea     ecx, [rdx+rbx]
0x14003c05c  add     rcx, r9; void *
0x14003c05f  xor     edx, edx; Val
0x14003c061  test    r15b, r15b
0x14003c064  jz      short loc_14003C06D
0x14003c066  call    RtlSetUserMemory
0x14003c06b  jmp     short loc_14003C072
0x14003c06d  call    RtlSetVolatileMemory
0x14003c072  mov     [rsp+78h+var_58], 0
0x14003c077  add     ebx, esi
0x14003c079  mov     [rsp+78h+var_54], ebx
0x14003c07d  mov     eax, [rdi]
0x14003c07f  add     rdi, rax
0x14003c082  mov     [rsp+78h+var_40], rdi
0x14003c087  mov     r14, rdi
0x14003c08a  mov     rcx, [rsp+78h+var_48]
0x14003c08f  cmp     rdi, rcx
0x14003c092  jnb     short loc_14003C0EA
0x14003c094  cmp     ebx, [rsp+78h+arg_20]
0x14003c09b  jnb     short loc_14003C0EA
0x14003c09d  mov     r8d, ecx
0x14003c0a0  sub     r8d, edi
0x14003c0a3  mov     edx, [rsp+78h+arg_10]
0x14003c0aa  mov     r9, [rsp+78h+arg_18]
0x14003c0b2  mov     r10d, [rsp+78h+arg_0]
0x14003c0ba  jmp     loc_14003BF47
0x14003c0bf  lea     rax, [rbx+r9]
0x14003c0c3  test    r15b, r15b
0x14003c0c6  jz      short loc_14003C0D4
0x14003c0c8  xor     edx, edx
0x14003c0ca  mov     rcx, rax
0x14003c0cd  call    RtlWriteULongToUser
0x14003c0d2  jmp     short loc_14003C0DA
0x14003c0d4  mov     dword ptr [rax], 0
0x14003c0da  mov     [rsp+78h+var_58], 0
0x14003c0df  add     ebx, [rsp+78h+arg_10]
0x14003c0e6  mov     [rsp+78h+var_54], ebx
0x14003c0ea  mov     rax, [rsp+78h+arg_30]
0x14003c0f2  mov     [rax], ebx
0x14003c0f4  mov     eax, [rsp+78h+arg_8]
0x14003c0fb  jmp     short loc_14003C102
0x14003c0fd  mov     eax, 0C00000E8h
0x14003c102  add     rsp, 40h
0x14003c106  pop     r15
0x14003c108  pop     r14
0x14003c10a  pop     r13
0x14003c10c  pop     r12
0x14003c10e  pop     rdi
0x14003c10f  pop     rsi
0x14003c110  pop     rbx
0x14003c111  retn
0x14003f08c  push    rbp
0x14003f08e  sub     rsp, 20h
0x14003f092  mov     rbp, rdx
0x14003f095  xor     eax, eax
0x14003f097  cmp     [rbp+20h], al
0x14003f09a  setnz   al
0x14003f09d  add     rsp, 20h
0x14003f0a1  pop     rbp
0x14003f0a2  retn
```
