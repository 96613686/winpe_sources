# WofMungeDirectoryEnumerateWithShortnameFileIdAll

- ea: `0x14003ba5c`
- end: `0x14003bcac`
- name: `WofMungeDirectoryEnumerateWithShortnameFileIdAll`
- size: `592`
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
- `0x14003ba5c`

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
0x14003ba5c  mov     rax, rsp
0x14003ba5f  mov     [rax+20h], r9
0x14003ba63  mov     [rax+8], ecx
0x14003ba66  push    rbx
0x14003ba67  push    rsi
0x14003ba68  push    rdi
0x14003ba69  push    r12
0x14003ba6b  push    r13
0x14003ba6d  push    r14
0x14003ba6f  push    r15
0x14003ba71  sub     rsp, 40h
0x14003ba75  mov     rdi, rdx
0x14003ba78  mov     r10d, ecx
0x14003ba7b  mov     byte ptr [rax-58h], 0
0x14003ba7f  mov     [rsp+78h+arg_8], 0
0x14003ba8a  mov     ecx, r8d
0x14003ba8d  add     rcx, rdx
0x14003ba90  mov     [rsp+78h+var_48], rcx
0x14003ba95  xor     ebx, ebx
0x14003ba97  xor     edx, edx
0x14003ba99  mov     [rax+18h], edx
0x14003ba9c  mov     r14, rdi
0x14003ba9f  mov     r15b, [rsp+78h+arg_28]
0x14003baa7  mov     r13d, [r14+3Ch]
0x14003baab  lea     eax, [r8-7Ah]
0x14003baaf  cmp     r13d, eax
0x14003bab2  cmovnb  r13d, eax
0x14003bab6  cmp     r10d, 51h ; 'Q'
0x14003baba  jnz     loc_14003BBC9
0x14003bac0  lea     rsi, [rbx+r9]
0x14003bac4  lea     eax, [r13+7Ah]
0x14003bac8  mov     [rsp+78h+arg_10], eax
0x14003bacf  mov     [rsp+78h+var_50], eax
0x14003bad3  mov     [rsp+78h+var_58], 1
0x14003bad8  lea     r8d, [r10+11h]; Size
0x14003badc  mov     rdx, rdi; Src
0x14003badf  mov     rcx, rsi; void *
0x14003bae2  test    r15b, r15b
0x14003bae5  jz      short loc_14003BAEE
0x14003bae7  call    RtlCopyToUser
0x14003baec  jmp     short loc_14003BAF3
0x14003baee  call    RtlCopyVolatileMemory
0x14003baf3  lea     rcx, [rsi+61h]; void *
0x14003baf7  xor     edx, edx; Val
0x14003baf9  lea     r8d, [rdx+19h]; Size
0x14003bafd  test    r15b, r15b
0x14003bb00  jz      short loc_14003BB09
0x14003bb02  call    RtlSetUserMemory
0x14003bb07  jmp     short loc_14003BB0E
0x14003bb09  call    RtlSetVolatileMemory
0x14003bb0e  mov     eax, cs:FileTag
0x14003bb14  cmp     [r14+44h], eax
0x14003bb18  jnz     short loc_14003BB5B
0x14003bb1a  xor     edx, edx
0x14003bb1c  mov     ecx, [r14+38h]
0x14003bb20  call    WofSanitizeAttributes
0x14003bb25  lea     rcx, [rsi+38h]
0x14003bb29  test    r15b, r15b
0x14003bb2c  jz      short loc_14003BB37
0x14003bb2e  mov     edx, eax
0x14003bb30  call    RtlWriteULongToUser
0x14003bb35  jmp     short loc_14003BB39
0x14003bb37  mov     [rcx], eax
0x14003bb39  cmp     cs:byte_140018454, 0
0x14003bb40  jz      short loc_14003BB5B
0x14003bb42  test    r15b, r15b
0x14003bb45  jz      short loc_14003BB54
0x14003bb47  xor     edx, edx
0x14003bb49  lea     rcx, [rsi+44h]
0x14003bb4d  call    RtlWriteULongToUser
0x14003bb52  jmp     short loc_14003BB5B
0x14003bb54  mov     dword ptr [rsi+44h], 0
0x14003bb5b  movsx   r8, byte ptr [r14+60h]; Size
0x14003bb60  lea     rdx, [r14+62h]; Src
0x14003bb64  lea     rcx, [rsi+62h]; void *
0x14003bb68  test    r15b, r15b
0x14003bb6b  jz      short loc_14003BB74
0x14003bb6d  call    RtlCopyToUser
0x14003bb72  jmp     short loc_14003BB79
0x14003bb74  call    RtlCopyVolatileMemory
0x14003bb79  lea     rdx, [r14+7Ah]; Src
0x14003bb7d  lea     rcx, [rsi+7Ah]; void *
0x14003bb81  mov     r8d, r13d; Size
0x14003bb84  test    r15b, r15b
0x14003bb87  jz      short loc_14003BB90
0x14003bb89  call    RtlCopyToUser
0x14003bb8e  jmp     short loc_14003BB95
0x14003bb90  call    RtlCopyVolatileMemory
0x14003bb95  mov     edx, [rsp+78h+arg_10]
0x14003bb9c  lea     eax, [rdx+7]
0x14003bb9f  and     eax, 0FFFFFFF8h
0x14003bba2  test    r15b, r15b
0x14003bba5  jz      short loc_14003BBBA
0x14003bba7  mov     edx, eax
0x14003bba9  mov     rcx, rsi
0x14003bbac  call    RtlWriteULongToUser
0x14003bbb1  mov     edx, [rsp+78h+arg_10]
0x14003bbb8  jmp     short loc_14003BBBC
0x14003bbba  mov     [rsi], eax
0x14003bbbc  mov     [rsp+78h+var_58], 0
0x14003bbc1  mov     r9, [rsp+78h+arg_18]
0x14003bbc9  mov     [rsp+78h+var_58], 1
0x14003bbce  cmp     dword ptr [rdi], 0
0x14003bbd1  jz      loc_14003BC58
0x14003bbd7  mov     ecx, [rsp+78h+arg_20]
0x14003bbde  sub     ecx, ebx
0x14003bbe0  lea     esi, [rdx+7]
0x14003bbe3  and     esi, 0FFFFFFF8h
0x14003bbe6  mov     r8d, esi
0x14003bbe9  cmp     esi, ecx
0x14003bbeb  cmovnb  r8d, ecx
0x14003bbef  sub     r8d, edx; Size
0x14003bbf2  lea     ecx, [rdx+rbx]
0x14003bbf5  add     rcx, r9; void *
0x14003bbf8  xor     edx, edx; Val
0x14003bbfa  test    r15b, r15b
0x14003bbfd  jz      short loc_14003BC06
0x14003bbff  call    RtlSetUserMemory
0x14003bc04  jmp     short loc_14003BC0B
0x14003bc06  call    RtlSetVolatileMemory
0x14003bc0b  mov     [rsp+78h+var_58], 0
0x14003bc10  add     ebx, esi
0x14003bc12  mov     [rsp+78h+var_54], ebx
0x14003bc16  mov     eax, [rdi]
0x14003bc18  add     rdi, rax
0x14003bc1b  mov     [rsp+78h+var_40], rdi
0x14003bc20  mov     r14, rdi
0x14003bc23  mov     rcx, [rsp+78h+var_48]
0x14003bc28  cmp     rdi, rcx
0x14003bc2b  jnb     short loc_14003BC83
0x14003bc2d  cmp     ebx, [rsp+78h+arg_20]
0x14003bc34  jnb     short loc_14003BC83
0x14003bc36  mov     r8d, ecx
0x14003bc39  sub     r8d, edi
0x14003bc3c  mov     edx, [rsp+78h+arg_10]
0x14003bc43  mov     r9, [rsp+78h+arg_18]
0x14003bc4b  mov     r10d, [rsp+78h+arg_0]
0x14003bc53  jmp     loc_14003BAA7
0x14003bc58  lea     rax, [rbx+r9]
0x14003bc5c  test    r15b, r15b
0x14003bc5f  jz      short loc_14003BC6D
0x14003bc61  xor     edx, edx
0x14003bc63  mov     rcx, rax
0x14003bc66  call    RtlWriteULongToUser
0x14003bc6b  jmp     short loc_14003BC73
0x14003bc6d  mov     dword ptr [rax], 0
0x14003bc73  mov     [rsp+78h+var_58], 0
0x14003bc78  add     ebx, [rsp+78h+arg_10]
0x14003bc7f  mov     [rsp+78h+var_54], ebx
0x14003bc83  mov     rax, [rsp+78h+arg_30]
0x14003bc8b  mov     [rax], ebx
0x14003bc8d  mov     eax, [rsp+78h+arg_8]
0x14003bc94  jmp     short loc_14003BC9B
0x14003bc96  mov     eax, 0C00000E8h
0x14003bc9b  add     rsp, 40h
0x14003bc9f  pop     r15
0x14003bca1  pop     r14
0x14003bca3  pop     r13
0x14003bca5  pop     r12
0x14003bca7  pop     rdi
0x14003bca8  pop     rsi
0x14003bca9  pop     rbx
0x14003bcaa  retn
0x14003f0be  push    rbp
0x14003f0c0  sub     rsp, 20h
0x14003f0c4  mov     rbp, rdx
0x14003f0c7  xor     eax, eax
0x14003f0c9  cmp     [rbp+20h], al
0x14003f0cc  setnz   al
0x14003f0cf  add     rsp, 20h
0x14003f0d3  pop     rbp
0x14003f0d4  retn
```
