# VidDeleteResourcePartition

- ea: `0x1400918f0`
- end: `0x140091c69`
- name: `VidDeleteResourcePartition`
- size: `889`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x140007234`
- `0x1400087b8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002f524`
- `0x1400307d0`
- `0x140033900`
- `0x1400769f8`
- `0x1400918f0`
- `0x1400942f8`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x140091b83`
- `ntoskrnl!RtlRbRemoveNode` at `0x140091b83`

## string_xrefs

- `0x14009193c`: `VidDeleteResourcePartition`
- `0x1400919af`: `VidDeleteResourcePartition`
- `0x140091a74`: `VidDeleteResourcePartition`
- `0x140091aef`: `VidDeleteResourcePartition`
- `0x140091bb5`: `VidDeleteResourcePartition`

## pseudocode

```c
__int64 __fastcall VidDeleteResourcePartition(int *a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // edi
  _DWORD *v5; // rbx
  char *v6; // r15
  char *v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  char *v11; // rbx
  __int16 *v12; // rdx
  int *v13; // rax
  char *v14; // rax
  __int64 v15; // r8
  int v17; // [rsp+30h] [rbp-59h] BYREF
  _DWORD v18[3]; // [rsp+34h] [rbp-55h] BYREF
  _BYTE v19[32]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v20[16]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v21[16]; // [rsp+70h] [rbp-19h] BYREF
  int *v22; // [rsp+80h] [rbp-9h]
  __int64 v23; // [rsp+88h] [rbp-1h]
  int *v24; // [rsp+90h] [rbp+7h]
  __int64 v25; // [rsp+98h] [rbp+Fh]
  char *v26; // [rsp+A0h] [rbp+17h]
  __int64 v27; // [rsp+A8h] [rbp+1Fh]

  if ( a2 )
  {
    v4 = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidDeleteResourcePartition",
      "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c",
      1863);
    return v4;
  }
  v5 = VidDeviceExtension;
  v6 = (char *)VidDeviceExtension + 1640;
  v7 = (char *)VidDeviceExtension + 2200;
  VidLockAcquireShared((char *)VidDeviceExtension + 1640, 0, a3);
  VidPushLockAcquireExclusive(v7);
  if ( v5[409] )
  {
    v11 = 0;
    v4 = -1073741436;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v20, "VidDeleteResourcePartition");
      tlgCreate1Sz_char(v21, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
      v18[0] = 1881;
      v22 = v18;
      v12 = (__int16 *)&byte_140048027;
      v13 = &v17;
      v17 = -1073741436;
LABEL_7:
      v24 = v13;
      v27 = 16;
      v26 = (char *)a1;
      v25 = 4;
      v23 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v12, 0, 0, 7, v19);
    }
  }
  else
  {
    v14 = (char *)VidResourcePartitionFindById(v7, a1);
    v11 = v14;
    if ( v14 )
    {
      if ( *(_QWORD *)v14 )
      {
        v4 = -1073740024;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v20, "VidDeleteResourcePartition");
          tlgCreate1Sz_char(v21, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          v17 = 1912;
          v22 = &v17;
          v23 = 4;
          v24 = v18;
          v18[0] = -1073740024;
          v26 = v11 + 8;
          v25 = 4;
          v27 = 16;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_140047FD2, 0, 0, 7, v19);
        }
        v11 = 0;
      }
      else
      {
        RtlRbRemoveNode(v7 + 8, v14 + 32);
        v9 = 4;
        if ( (unsigned int)dword_140064110 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v20, "VidDeleteResourcePartition");
          tlgCreate1Sz_char(v21, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          v23 = v15;
          v22 = &v17;
          v17 = 1924;
          v24 = a1;
          v25 = 16;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &dword_140047F34, 0, 0, 6, v19);
        }
        v4 = 0;
      }
      goto LABEL_21;
    }
    v4 = -1073741275;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v20, "VidDeleteResourcePartition");
      tlgCreate1Sz_char(v21, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
      v17 = 1897;
      v22 = &v17;
      v12 = &word_140047F7E;
      v13 = v18;
      v18[0] = -1073741275;
      goto LABEL_7;
    }
  }
LABEL_21:
  VidPushLockRelease(v7, v8, v9, v10);
  VidLockRelease(v6);
  if ( v11 )
    VidResourcePartitionpFree(v11);
  return v4;
}

```

## disassembly

```asm
0x1400918f0  mov     [rsp-8+arg_8], rbx
0x1400918f5  mov     [rsp-8+arg_10], rsi
0x1400918fa  push    rbp
0x1400918fb  push    rdi
0x1400918fc  push    r12
0x1400918fe  push    r14
0x140091900  push    r15
0x140091902  lea     rbp, [rsp-37h]
0x140091907  sub     rsp, 0C0h
0x14009190e  mov     rax, cs:__security_cookie
0x140091915  xor     rax, rsp
0x140091918  mov     [rbp+57h+var_30], rax
0x14009191c  xor     r12d, r12d
0x14009191f  mov     r14, rcx
0x140091922  test    rdx, rdx
0x140091925  jz      short loc_14009194D
0x140091927  mov     edi, 0C000000Dh
0x14009192c  mov     r9d, edi
0x14009192f  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140091936  mov     r8d, 747h
0x14009193c  lea     rcx, aViddeleteresou; "VidDeleteResourcePartition"
0x140091943  call    VidTraceErrorStatusInternal0
0x140091948  jmp     loc_140091C3E
0x14009194d  mov     rbx, cs:VidDeviceExtension
0x140091954  lea     r15, [rbx+668h]
0x14009195b  mov     rcx, r15
0x14009195e  lea     rsi, [rbx+898h]
0x140091965  call    VidLockAcquireShared
0x14009196a  mov     rcx, rsi
0x14009196d  call    VidPushLockAcquireExclusive
0x140091972  cmp     [rbx+664h], r12d
0x140091979  jz      loc_140091A34
0x14009197f  mov     eax, cs:dword_140064110
0x140091985  mov     rbx, r12
0x140091988  mov     edi, 0C0000184h
0x14009198d  cmp     eax, 2
0x140091990  jbe     loc_140091C21
0x140091996  mov     edx, 100h
0x14009199b  lea     rcx, dword_140064110
0x1400919a2  call    _tlgKeywordOn
0x1400919a7  test    al, al
0x1400919a9  jz      loc_140091C21
0x1400919af  lea     rdx, aViddeleteresou; "VidDeleteResourcePartition"
0x1400919b6  lea     rcx, [rbp+57h+var_80]
0x1400919ba  call    _tlgCreate1Sz_char
0x1400919bf  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x1400919c6  lea     rcx, [rbp+57h+var_70]
0x1400919ca  call    _tlgCreate1Sz_char
0x1400919cf  lea     rax, [rbp+57h+var_AC]
0x1400919d3  mov     [rbp+57h+var_AC], 759h
0x1400919da  mov     [rbp+57h+var_60], rax
0x1400919de  lea     rdx, byte_140048027
0x1400919e5  lea     rax, [rbp+57h+var_B0]
0x1400919e9  mov     [rbp+57h+var_B0], edi
0x1400919ec  mov     [rbp+57h+var_50], rax
0x1400919f0  lea     rcx, dword_140064110
0x1400919f7  lea     rax, [rbp+57h+var_A0]
0x1400919fb  mov     [rbp+57h+var_38], 10h
0x140091a03  mov     [rsp+0E0h+var_B8], rax
0x140091a08  xor     r9d, r9d
0x140091a0b  xor     r8d, r8d
0x140091a0e  mov     [rsp+0E0h+var_C0], 7
0x140091a16  mov     [rbp+57h+var_40], r14
0x140091a1a  mov     [rbp+57h+var_48], 4
0x140091a22  mov     [rbp+57h+var_58], 4
0x140091a2a  call    _tlgWriteTransfer_EtwWriteTransfer
0x140091a2f  jmp     loc_140091C21
0x140091a34  mov     rdx, r14
0x140091a37  mov     rcx, rsi
0x140091a3a  call    VidResourcePartitionFindById
0x140091a3f  mov     rbx, rax
0x140091a42  test    rax, rax
0x140091a45  jnz     short loc_140091AB6
0x140091a47  mov     eax, cs:dword_140064110
0x140091a4d  mov     edi, 0C0000225h
0x140091a52  cmp     eax, 2
0x140091a55  jbe     loc_140091C21
0x140091a5b  mov     edx, 100h
0x140091a60  lea     rcx, dword_140064110
0x140091a67  call    _tlgKeywordOn
0x140091a6c  test    al, al
0x140091a6e  jz      loc_140091C21
0x140091a74  lea     rdx, aViddeleteresou; "VidDeleteResourcePartition"
0x140091a7b  lea     rcx, [rbp+57h+var_80]
0x140091a7f  call    _tlgCreate1Sz_char
0x140091a84  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140091a8b  lea     rcx, [rbp+57h+var_70]
0x140091a8f  call    _tlgCreate1Sz_char
0x140091a94  lea     rax, [rbp+57h+var_B0]
0x140091a98  mov     [rbp+57h+var_B0], 769h
0x140091a9f  mov     [rbp+57h+var_60], rax
0x140091aa3  lea     rdx, word_140047F7E
0x140091aaa  lea     rax, [rbp+57h+var_AC]
0x140091aae  mov     [rbp+57h+var_AC], edi
0x140091ab1  jmp     loc_1400919EC
0x140091ab6  mov     rax, [rax]
0x140091ab9  test    rax, rax
0x140091abc  jz      loc_140091B7B
0x140091ac2  mov     eax, cs:dword_140064110
0x140091ac8  mov     edi, 0C0000708h
0x140091acd  cmp     eax, 2
0x140091ad0  jbe     loc_140091B73
0x140091ad6  mov     edx, 100h
0x140091adb  lea     rcx, dword_140064110
0x140091ae2  call    _tlgKeywordOn
0x140091ae7  test    al, al
0x140091ae9  jz      loc_140091B73
0x140091aef  lea     rdx, aViddeleteresou; "VidDeleteResourcePartition"
0x140091af6  lea     rcx, [rbp+57h+var_80]
0x140091afa  call    _tlgCreate1Sz_char
0x140091aff  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140091b06  lea     rcx, [rbp+57h+var_70]
0x140091b0a  call    _tlgCreate1Sz_char
0x140091b0f  lea     rax, [rbp+57h+var_B0]
0x140091b13  mov     [rbp+57h+var_B0], 778h
0x140091b1a  mov     [rbp+57h+var_60], rax
0x140091b1e  lea     rdx, word_140047FD2
0x140091b25  lea     rax, [rbp+57h+var_AC]
0x140091b29  mov     [rbp+57h+var_58], 4
0x140091b31  mov     [rbp+57h+var_50], rax
0x140091b35  lea     rcx, dword_140064110
0x140091b3c  lea     rax, [rbx+8]
0x140091b40  mov     [rbp+57h+var_AC], edi
0x140091b43  mov     [rbp+57h+var_40], rax
0x140091b47  xor     r9d, r9d
0x140091b4a  lea     rax, [rbp+57h+var_A0]
0x140091b4e  mov     [rbp+57h+var_48], 4
0x140091b56  mov     [rsp+0E0h+var_B8], rax
0x140091b5b  xor     r8d, r8d
0x140091b5e  mov     [rsp+0E0h+var_C0], 7
0x140091b66  mov     [rbp+57h+var_38], 10h
0x140091b6e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140091b73  mov     rbx, r12
0x140091b76  jmp     loc_140091C21
0x140091b7b  lea     rdx, [rbx+20h]
0x140091b7f  lea     rcx, [rsi+8]
0x140091b83  call    cs:__imp_RtlRbRemoveNode
0x140091b8a  nop     dword ptr [rax+rax+00h]
0x140091b8f  mov     eax, cs:dword_140064110
0x140091b95  mov     r8d, 4
0x140091b9b  cmp     eax, r8d
0x140091b9e  jbe     short loc_140091C1E
0x140091ba0  mov     edx, 100h
0x140091ba5  lea     rcx, dword_140064110
0x140091bac  call    _tlgKeywordOn
0x140091bb1  test    al, al
0x140091bb3  jz      short loc_140091C1E
0x140091bb5  lea     rdx, aViddeleteresou; "VidDeleteResourcePartition"
0x140091bbc  lea     rcx, [rbp+57h+var_80]
0x140091bc0  call    _tlgCreate1Sz_char
0x140091bc5  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140091bcc  lea     rcx, [rbp+57h+var_70]
0x140091bd0  call    _tlgCreate1Sz_char
0x140091bd5  lea     rax, [rbp+57h+var_B0]
0x140091bd9  mov     [rbp+57h+var_58], r8
0x140091bdd  mov     [rbp+57h+var_60], rax
0x140091be1  lea     rdx, dword_140047F34
0x140091be8  lea     rax, [rbp+57h+var_A0]
0x140091bec  mov     [rbp+57h+var_B0], 784h
0x140091bf3  mov     [rsp+0E0h+var_B8], rax
0x140091bf8  lea     rcx, dword_140064110
0x140091bff  xor     r9d, r9d
0x140091c02  mov     [rsp+0E0h+var_C0], 6
0x140091c0a  xor     r8d, r8d
0x140091c0d  mov     [rbp+57h+var_50], r14
0x140091c11  mov     [rbp+57h+var_48], 10h
0x140091c19  call    _tlgWriteTransfer_EtwWriteTransfer
0x140091c1e  mov     edi, r12d
0x140091c21  mov     rcx, rsi
0x140091c24  call    VidPushLockRelease
0x140091c29  mov     rcx, r15
0x140091c2c  call    VidLockRelease
0x140091c31  test    rbx, rbx
0x140091c34  jz      short loc_140091C3E
0x140091c36  mov     rcx, rbx; P
0x140091c39  call    VidResourcePartitionpFree
0x140091c3e  mov     eax, edi
0x140091c40  mov     rcx, [rbp+57h+var_30]
0x140091c44  xor     rcx, rsp; StackCookie
0x140091c47  call    __security_check_cookie
0x140091c4c  lea     r11, [rsp+0E0h+var_20]
0x140091c54  mov     rbx, [r11+38h]
0x140091c58  mov     rsi, [r11+40h]
0x140091c5c  mov     rsp, r11
0x140091c5f  pop     r15
0x140091c61  pop     r14
0x140091c63  pop     r12
0x140091c65  pop     rdi
0x140091c66  pop     rbp
0x140091c67  retn
```
