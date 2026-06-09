# WofMungeDirectoryEnumerateWithShortnameFileIdAll

- ea: `0x14003ba0c`
- end: `0x14003bc5c`
- name: `WofMungeDirectoryEnumerateWithShortnameFileIdAll`
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
- `0x14003ba0c`

## pseudocode

```c
__int64 __fastcall WofMungeDirectoryEnumerateWithShortnameFileIdAll(
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
    if ( v12 >= a3 - 122 )
      v12 = a3 - 122;
    if ( v8 == 81 )
    {
      v13 = (unsigned int *)(v9 + a4);
      v32 = v12 + 122;
      v14 = (void *)(v9 + a4);
      if ( a6 )
        RtlCopyToUser(v14, v7, 0x62u);
      else
        RtlCopyVolatileMemory(v14, v7, 0x62u);
      v15 = (char *)v13 + 97;
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
      v19 = *((char *)v11 + 96);
      v20 = (char *)v11 + 98;
      v21 = (char *)v13 + 98;
      if ( a6 )
        RtlCopyToUser(v21, v20, v19);
      else
        RtlCopyVolatileMemory(v21, v20, v19);
      v22 = (char *)v11 + 122;
      v23 = (char *)v13 + 122;
      if ( a6 )
        RtlCopyToUser(v23, v22, v12);
      else
        RtlCopyVolatileMemory(v23, v22, v12);
      v10 = v12 + 122;
      v24 = (v12 + 129) & 0xFFFFFFF8;
      if ( a6 )
      {
        RtlWriteULongToUser(v13, v24);
        v10 = v12 + 122;
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
0x14003ba0c  mov     rax, rsp
0x14003ba0f  mov     [rax+20h], r9
0x14003ba13  mov     [rax+8], ecx
0x14003ba16  push    rbx
0x14003ba17  push    rsi
0x14003ba18  push    rdi
0x14003ba19  push    r12
0x14003ba1b  push    r13
0x14003ba1d  push    r14
0x14003ba1f  push    r15
0x14003ba21  sub     rsp, 40h
0x14003ba25  mov     rdi, rdx
0x14003ba28  mov     r10d, ecx
0x14003ba2b  mov     byte ptr [rax-58h], 0
0x14003ba2f  mov     [rsp+78h+arg_8], 0
0x14003ba3a  mov     ecx, r8d
0x14003ba3d  add     rcx, rdx
0x14003ba40  mov     [rsp+78h+var_48], rcx
0x14003ba45  xor     ebx, ebx
0x14003ba47  xor     edx, edx
0x14003ba49  mov     [rax+18h], edx
0x14003ba4c  mov     r14, rdi
0x14003ba4f  mov     r15b, [rsp+78h+arg_28]
0x14003ba57  mov     r13d, [r14+3Ch]
0x14003ba5b  lea     eax, [r8-7Ah]
0x14003ba5f  cmp     r13d, eax
0x14003ba62  cmovnb  r13d, eax
0x14003ba66  cmp     r10d, 51h ; 'Q'
0x14003ba6a  jnz     loc_14003BB79
0x14003ba70  lea     rsi, [rbx+r9]
0x14003ba74  lea     eax, [r13+7Ah]
0x14003ba78  mov     [rsp+78h+arg_10], eax
0x14003ba7f  mov     [rsp+78h+var_50], eax
0x14003ba83  mov     [rsp+78h+var_58], 1
0x14003ba88  lea     r8d, [r10+11h]; Size
0x14003ba8c  mov     rdx, rdi; Src
0x14003ba8f  mov     rcx, rsi; void *
0x14003ba92  test    r15b, r15b
0x14003ba95  jz      short loc_14003BA9E
0x14003ba97  call    RtlCopyToUser
0x14003ba9c  jmp     short loc_14003BAA3
0x14003ba9e  call    RtlCopyVolatileMemory
0x14003baa3  lea     rcx, [rsi+61h]; void *
0x14003baa7  xor     edx, edx; Val
0x14003baa9  lea     r8d, [rdx+19h]; Size
0x14003baad  test    r15b, r15b
0x14003bab0  jz      short loc_14003BAB9
0x14003bab2  call    RtlSetUserMemory
0x14003bab7  jmp     short loc_14003BABE
0x14003bab9  call    RtlSetVolatileMemory
0x14003babe  mov     eax, cs:FileTag
0x14003bac4  cmp     [r14+44h], eax
0x14003bac8  jnz     short loc_14003BB0B
0x14003baca  xor     edx, edx
0x14003bacc  mov     ecx, [r14+38h]
0x14003bad0  call    WofSanitizeAttributes
0x14003bad5  lea     rcx, [rsi+38h]
0x14003bad9  test    r15b, r15b
0x14003badc  jz      short loc_14003BAE7
0x14003bade  mov     edx, eax
0x14003bae0  call    RtlWriteULongToUser
0x14003bae5  jmp     short loc_14003BAE9
0x14003bae7  mov     [rcx], eax
0x14003bae9  cmp     cs:byte_140018454, 0
0x14003baf0  jz      short loc_14003BB0B
0x14003baf2  test    r15b, r15b
0x14003baf5  jz      short loc_14003BB04
0x14003baf7  xor     edx, edx
0x14003baf9  lea     rcx, [rsi+44h]
0x14003bafd  call    RtlWriteULongToUser
0x14003bb02  jmp     short loc_14003BB0B
0x14003bb04  mov     dword ptr [rsi+44h], 0
0x14003bb0b  movsx   r8, byte ptr [r14+60h]; Size
0x14003bb10  lea     rdx, [r14+62h]; Src
0x14003bb14  lea     rcx, [rsi+62h]; void *
0x14003bb18  test    r15b, r15b
0x14003bb1b  jz      short loc_14003BB24
0x14003bb1d  call    RtlCopyToUser
0x14003bb22  jmp     short loc_14003BB29
0x14003bb24  call    RtlCopyVolatileMemory
0x14003bb29  lea     rdx, [r14+7Ah]; Src
0x14003bb2d  lea     rcx, [rsi+7Ah]; void *
0x14003bb31  mov     r8d, r13d; Size
0x14003bb34  test    r15b, r15b
0x14003bb37  jz      short loc_14003BB40
0x14003bb39  call    RtlCopyToUser
0x14003bb3e  jmp     short loc_14003BB45
0x14003bb40  call    RtlCopyVolatileMemory
0x14003bb45  mov     edx, [rsp+78h+arg_10]
0x14003bb4c  lea     eax, [rdx+7]
0x14003bb4f  and     eax, 0FFFFFFF8h
0x14003bb52  test    r15b, r15b
0x14003bb55  jz      short loc_14003BB6A
0x14003bb57  mov     edx, eax
0x14003bb59  mov     rcx, rsi
0x14003bb5c  call    RtlWriteULongToUser
0x14003bb61  mov     edx, [rsp+78h+arg_10]
0x14003bb68  jmp     short loc_14003BB6C
0x14003bb6a  mov     [rsi], eax
0x14003bb6c  mov     [rsp+78h+var_58], 0
0x14003bb71  mov     r9, [rsp+78h+arg_18]
0x14003bb79  mov     [rsp+78h+var_58], 1
0x14003bb7e  cmp     dword ptr [rdi], 0
0x14003bb81  jz      loc_14003BC08
0x14003bb87  mov     ecx, [rsp+78h+arg_20]
0x14003bb8e  sub     ecx, ebx
0x14003bb90  lea     esi, [rdx+7]
0x14003bb93  and     esi, 0FFFFFFF8h
0x14003bb96  mov     r8d, esi
0x14003bb99  cmp     esi, ecx
0x14003bb9b  cmovnb  r8d, ecx
0x14003bb9f  sub     r8d, edx; Size
0x14003bba2  lea     ecx, [rdx+rbx]
0x14003bba5  add     rcx, r9; void *
0x14003bba8  xor     edx, edx; Val
0x14003bbaa  test    r15b, r15b
0x14003bbad  jz      short loc_14003BBB6
0x14003bbaf  call    RtlSetUserMemory
0x14003bbb4  jmp     short loc_14003BBBB
0x14003bbb6  call    RtlSetVolatileMemory
0x14003bbbb  mov     [rsp+78h+var_58], 0
0x14003bbc0  add     ebx, esi
0x14003bbc2  mov     [rsp+78h+var_54], ebx
0x14003bbc6  mov     eax, [rdi]
0x14003bbc8  add     rdi, rax
0x14003bbcb  mov     [rsp+78h+var_40], rdi
0x14003bbd0  mov     r14, rdi
0x14003bbd3  mov     rcx, [rsp+78h+var_48]
0x14003bbd8  cmp     rdi, rcx
0x14003bbdb  jnb     short loc_14003BC33
0x14003bbdd  cmp     ebx, [rsp+78h+arg_20]
0x14003bbe4  jnb     short loc_14003BC33
0x14003bbe6  mov     r8d, ecx
0x14003bbe9  sub     r8d, edi
0x14003bbec  mov     edx, [rsp+78h+arg_10]
0x14003bbf3  mov     r9, [rsp+78h+arg_18]
0x14003bbfb  mov     r10d, [rsp+78h+arg_0]
0x14003bc03  jmp     loc_14003BA57
0x14003bc08  lea     rax, [rbx+r9]
0x14003bc0c  test    r15b, r15b
0x14003bc0f  jz      short loc_14003BC1D
0x14003bc11  xor     edx, edx
0x14003bc13  mov     rcx, rax
0x14003bc16  call    RtlWriteULongToUser
0x14003bc1b  jmp     short loc_14003BC23
0x14003bc1d  mov     dword ptr [rax], 0
0x14003bc23  mov     [rsp+78h+var_58], 0
0x14003bc28  add     ebx, [rsp+78h+arg_10]
0x14003bc2f  mov     [rsp+78h+var_54], ebx
0x14003bc33  mov     rax, [rsp+78h+arg_30]
0x14003bc3b  mov     [rax], ebx
0x14003bc3d  mov     eax, [rsp+78h+arg_8]
0x14003bc44  jmp     short loc_14003BC4B
0x14003bc46  mov     eax, 0C00000E8h
0x14003bc4b  add     rsp, 40h
0x14003bc4f  pop     r15
0x14003bc51  pop     r14
0x14003bc53  pop     r13
0x14003bc55  pop     r12
0x14003bc57  pop     rdi
0x14003bc58  pop     rsi
0x14003bc59  pop     rbx
0x14003bc5a  retn
0x14003f06e  push    rbp
0x14003f070  sub     rsp, 20h
0x14003f074  mov     rbp, rdx
0x14003f077  xor     eax, eax
0x14003f079  cmp     [rbp+20h], al
0x14003f07c  setnz   al
0x14003f07f  add     rsp, 20h
0x14003f083  pop     rbp
0x14003f084  retn
```
