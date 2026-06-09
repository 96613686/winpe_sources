# VsmmPhuStorepGpaRangeFree

- ea: `0x1400b7a80`
- end: `0x1400b7d38`
- name: `VsmmPhuStorepGpaRangeFree`
- size: `696`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400b5ccc`
- `0x1400b6858`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x1400b7a80`

## import_xrefs

- `winhvr!WinHvUnmapGpaPages` at `0x1400b7ad3`
- `winhvr!WinHvUnmapGpaPages` at `0x1400b7ad3`
- `winhvr!WinHvUncommitGpaPages` at `0x1400b7bf9`
- `winhvr!WinHvUncommitGpaPages` at `0x1400b7bf9`

## pseudocode

```c
NTSTATUS __fastcall VsmmPhuStorepGpaRangeFree(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rdi
  __int64 v3; // r9
  int v6; // r8d
  NTSTATUS result; // eax
  int v8; // r8d
  int v9; // [rsp+30h] [rbp-D0h] BYREF
  int v10; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v11; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v14[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v17[16]; // [rsp+90h] [rbp-70h] BYREF
  int *v18; // [rsp+A0h] [rbp-60h]
  __int64 v19; // [rsp+A8h] [rbp-58h]
  int *v20; // [rsp+B0h] [rbp-50h]
  __int64 v21; // [rsp+B8h] [rbp-48h]
  __int64 v22; // [rsp+C0h] [rbp-40h]
  __int64 v23; // [rsp+C8h] [rbp-38h]
  __int64 *v24; // [rsp+D0h] [rbp-30h]
  __int64 v25; // [rsp+D8h] [rbp-28h]
  __int64 *v26; // [rsp+E0h] [rbp-20h]
  __int64 v27; // [rsp+E8h] [rbp-18h]
  __int64 *v28; // [rsp+F0h] [rbp-10h]
  __int64 v29; // [rsp+F8h] [rbp-8h]

  v2 = *(_QWORD *)(a1 + 1184);
  v3 = a2[1];
  v11 = 0;
  if ( (int)WinHvUnmapGpaPages(v2, *a2, 1, v3, &v11) < 0
    && (unsigned int)dword_140065110 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v16, "VsmmPhuStorepGpaRangeFree");
    tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    v10 = v6;
    v18 = &v9;
    v9 = 6846;
    v20 = &v10;
    v19 = 4;
    v22 = a1 + 48;
    v12 = *a2;
    v24 = &v12;
    v13 = a2[1];
    v26 = &v13;
    v14[0] = v11;
    v28 = v14;
    v21 = 4;
    v23 = 16;
    v25 = 8;
    v27 = 8;
    v29 = 8;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, (unsigned __int8 *)&byte_14004F71F, 0, 0, 0xAu, v15);
  }
  result = WinHvUncommitGpaPages(v2, *a2, a2[1], &v11);
  if ( result < 0 && (unsigned int)dword_140065110 > 2 )
  {
    result = tlgKeywordOn(&dword_140065110, 256);
    if ( (_BYTE)result )
    {
      tlgCreate1Sz_char(v16, "VsmmPhuStorepGpaRangeFree");
      tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      v9 = v8;
      v18 = &v10;
      v10 = 6863;
      v20 = &v9;
      v19 = 4;
      v22 = a1 + 48;
      v14[0] = *a2;
      v24 = v14;
      v13 = a2[1];
      v26 = &v13;
      v12 = v11;
      v28 = &v12;
      v21 = 4;
      v23 = 16;
      v25 = 8;
      v27 = 8;
      v29 = 8;
      result = tlgWriteTransfer_EtwWriteTransfer(
                 (__int64)&dword_140065110,
                 (unsigned __int8 *)word_14004F79A,
                 0,
                 0,
                 0xAu,
                 v15);
    }
  }
  *((_BYTE *)a2 + 32) = 0;
  return result;
}

```

## disassembly

```asm
0x1400b7a80  mov     [rsp-8+arg_10], rbx
0x1400b7a85  push    rbp
0x1400b7a86  push    rsi
0x1400b7a87  push    rdi
0x1400b7a88  push    r13
0x1400b7a8a  push    r14
0x1400b7a8c  lea     rbp, [rsp-10h]
0x1400b7a91  sub     rsp, 110h
0x1400b7a98  mov     rax, cs:__security_cookie
0x1400b7a9f  xor     rax, rsp
0x1400b7aa2  mov     [rbp+30h+var_30], rax
0x1400b7aa6  mov     rdi, [rcx+4A0h]
0x1400b7aad  lea     rax, [rsp+130h+var_F8]
0x1400b7ab2  mov     r9, [rdx+8]
0x1400b7ab6  xor     r14d, r14d
0x1400b7ab9  mov     rbx, rdx
0x1400b7abc  mov     [rsp+130h+var_F8], r14
0x1400b7ac1  mov     rdx, [rdx]
0x1400b7ac4  mov     rsi, rcx
0x1400b7ac7  mov     rcx, rdi
0x1400b7aca  mov     [rsp+130h+var_110], rax
0x1400b7acf  lea     r8d, [r14+1]
0x1400b7ad3  call    cs:__imp_WinHvUnmapGpaPages
0x1400b7ada  nop     dword ptr [rax+rax+00h]
0x1400b7adf  mov     r8d, eax
0x1400b7ae2  test    eax, eax
0x1400b7ae4  jns     loc_1400B7BEA
0x1400b7aea  mov     ecx, cs:dword_140065110
0x1400b7af0  cmp     ecx, 2
0x1400b7af3  jbe     loc_1400B7BEA
0x1400b7af9  mov     edx, 100h
0x1400b7afe  lea     rcx, dword_140065110
0x1400b7b05  call    _tlgKeywordOn
0x1400b7b0a  test    al, al
0x1400b7b0c  jz      loc_1400B7BEA
0x1400b7b12  lea     rdx, aVsmmphustorepg_0; "VsmmPhuStorepGpaRangeFree"
0x1400b7b19  lea     rcx, [rbp+30h+var_B0]
0x1400b7b1d  call    _tlgCreate1Sz_char
0x1400b7b22  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b7b29  lea     rcx, [rbp+30h+var_A0]
0x1400b7b2d  call    _tlgCreate1Sz_char
0x1400b7b32  lea     rax, [rsp+130h+var_100]
0x1400b7b37  mov     [rsp+130h+var_FC], r8d
0x1400b7b3c  mov     [rbp+30h+var_90], rax
0x1400b7b40  lea     rdx, byte_14004F71F
0x1400b7b47  lea     rax, [rsp+130h+var_FC]
0x1400b7b4c  mov     [rsp+130h+var_100], 1ABEh
0x1400b7b54  mov     [rbp+30h+var_80], rax
0x1400b7b58  lea     rcx, dword_140065110
0x1400b7b5f  lea     rax, [rsi+30h]
0x1400b7b63  mov     [rbp+30h+var_88], 4
0x1400b7b6b  mov     [rbp+30h+var_70], rax
0x1400b7b6f  xor     r9d, r9d
0x1400b7b72  mov     rax, [rbx]
0x1400b7b75  xor     r8d, r8d
0x1400b7b78  mov     [rsp+130h+var_F0], rax
0x1400b7b7d  lea     rax, [rsp+130h+var_F0]
0x1400b7b82  mov     [rbp+30h+var_60], rax
0x1400b7b86  mov     rax, [rbx+8]
0x1400b7b8a  mov     [rsp+130h+var_E8], rax
0x1400b7b8f  lea     rax, [rsp+130h+var_E8]
0x1400b7b94  mov     [rbp+30h+var_50], rax
0x1400b7b98  mov     rax, [rsp+130h+var_F8]
0x1400b7b9d  mov     [rsp+130h+var_E0], rax
0x1400b7ba2  lea     rax, [rsp+130h+var_E0]
0x1400b7ba7  mov     [rbp+30h+var_40], rax
0x1400b7bab  lea     rax, [rsp+130h+var_D0]
0x1400b7bb0  mov     [rsp+130h+var_108], rax
0x1400b7bb5  mov     dword ptr [rsp+130h+var_110], 0Ah
0x1400b7bbd  mov     [rbp+30h+var_78], 4
0x1400b7bc5  mov     [rbp+30h+var_68], 10h
0x1400b7bcd  mov     [rbp+30h+var_58], 8
0x1400b7bd5  mov     [rbp+30h+var_48], 8
0x1400b7bdd  mov     [rbp+30h+var_38], 8
0x1400b7be5  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b7bea  mov     r8, [rbx+8]
0x1400b7bee  lea     r9, [rsp+130h+var_F8]
0x1400b7bf3  mov     rdx, [rbx]
0x1400b7bf6  mov     rcx, rdi
0x1400b7bf9  call    cs:__imp_WinHvUncommitGpaPages
0x1400b7c00  nop     dword ptr [rax+rax+00h]
0x1400b7c05  mov     r8d, eax
0x1400b7c08  test    eax, eax
0x1400b7c0a  jns     loc_1400B7D10
0x1400b7c10  mov     ecx, cs:dword_140065110
0x1400b7c16  cmp     ecx, 2
0x1400b7c19  jbe     loc_1400B7D10
0x1400b7c1f  mov     edx, 100h
0x1400b7c24  lea     rcx, dword_140065110
0x1400b7c2b  call    _tlgKeywordOn
0x1400b7c30  test    al, al
0x1400b7c32  jz      loc_1400B7D10
0x1400b7c38  lea     rdx, aVsmmphustorepg_0; "VsmmPhuStorepGpaRangeFree"
0x1400b7c3f  lea     rcx, [rbp+30h+var_B0]
0x1400b7c43  call    _tlgCreate1Sz_char
0x1400b7c48  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b7c4f  lea     rcx, [rbp+30h+var_A0]
0x1400b7c53  call    _tlgCreate1Sz_char
0x1400b7c58  lea     rax, [rsp+130h+var_FC]
0x1400b7c5d  mov     [rsp+130h+var_100], r8d
0x1400b7c62  mov     [rbp+30h+var_90], rax
0x1400b7c66  lea     rdx, word_14004F79A
0x1400b7c6d  lea     rax, [rsp+130h+var_100]
0x1400b7c72  mov     [rsp+130h+var_FC], 1ACFh
0x1400b7c7a  mov     [rbp+30h+var_80], rax
0x1400b7c7e  lea     rcx, dword_140065110
0x1400b7c85  lea     rax, [rsi+30h]
0x1400b7c89  mov     [rbp+30h+var_88], 4
0x1400b7c91  mov     [rbp+30h+var_70], rax
0x1400b7c95  xor     r9d, r9d
0x1400b7c98  mov     rax, [rbx]
0x1400b7c9b  xor     r8d, r8d
0x1400b7c9e  mov     [rsp+130h+var_E0], rax
0x1400b7ca3  lea     rax, [rsp+130h+var_E0]
0x1400b7ca8  mov     [rbp+30h+var_60], rax
0x1400b7cac  mov     rax, [rbx+8]
0x1400b7cb0  mov     [rsp+130h+var_E8], rax
0x1400b7cb5  lea     rax, [rsp+130h+var_E8]
0x1400b7cba  mov     [rbp+30h+var_50], rax
0x1400b7cbe  mov     rax, [rsp+130h+var_F8]
0x1400b7cc3  mov     [rsp+130h+var_F0], rax
0x1400b7cc8  lea     rax, [rsp+130h+var_F0]
0x1400b7ccd  mov     [rbp+30h+var_40], rax
0x1400b7cd1  lea     rax, [rsp+130h+var_D0]
0x1400b7cd6  mov     [rsp+130h+var_108], rax
0x1400b7cdb  mov     dword ptr [rsp+130h+var_110], 0Ah
0x1400b7ce3  mov     [rbp+30h+var_78], 4
0x1400b7ceb  mov     [rbp+30h+var_68], 10h
0x1400b7cf3  mov     [rbp+30h+var_58], 8
0x1400b7cfb  mov     [rbp+30h+var_48], 8
0x1400b7d03  mov     [rbp+30h+var_38], 8
0x1400b7d0b  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b7d10  mov     [rbx+20h], r14b
0x1400b7d14  mov     rcx, [rbp+30h+var_30]
0x1400b7d18  xor     rcx, rsp; StackCookie
0x1400b7d1b  call    __security_check_cookie
0x1400b7d20  mov     rbx, [rsp+130h+arg_10]
0x1400b7d28  add     rsp, 110h
0x1400b7d2f  pop     r14
0x1400b7d31  pop     r13
0x1400b7d33  pop     rdi
0x1400b7d34  pop     rsi
0x1400b7d35  pop     rbp
0x1400b7d36  retn
```
