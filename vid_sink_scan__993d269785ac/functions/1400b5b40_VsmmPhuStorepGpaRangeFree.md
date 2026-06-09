# VsmmPhuStorepGpaRangeFree

- ea: `0x1400b5b40`
- end: `0x1400b5df8`
- name: `VsmmPhuStorepGpaRangeFree`
- size: `696`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400b3dcc`
- `0x1400b4958`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x1400b5b40`

## import_xrefs

- `winhvr!WinHvUnmapGpaPages` at `0x1400b5b93`
- `winhvr!WinHvUnmapGpaPages` at `0x1400b5b93`
- `winhvr!WinHvUncommitGpaPages` at `0x1400b5cb9`
- `winhvr!WinHvUncommitGpaPages` at `0x1400b5cb9`

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
    && (unsigned int)dword_140064110 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v16, "VsmmPhuStorepGpaRangeFree");
    tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    v10 = v6;
    v18 = &v9;
    v9 = 6835;
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
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140064110, (unsigned __int8 *)&byte_14004F237, 0, 0, 0xAu, v15);
  }
  result = WinHvUncommitGpaPages(v2, *a2, a2[1], &v11);
  if ( result < 0 && (unsigned int)dword_140064110 > 2 )
  {
    result = tlgKeywordOn(&dword_140064110, 256);
    if ( (_BYTE)result )
    {
      tlgCreate1Sz_char(v16, "VsmmPhuStorepGpaRangeFree");
      tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      v9 = v8;
      v18 = &v10;
      v10 = 6852;
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
                 (__int64)&dword_140064110,
                 (unsigned __int8 *)word_14004F2B2,
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
0x1400b5b40  mov     [rsp-8+arg_10], rbx
0x1400b5b45  push    rbp
0x1400b5b46  push    rsi
0x1400b5b47  push    rdi
0x1400b5b48  push    r13
0x1400b5b4a  push    r14
0x1400b5b4c  lea     rbp, [rsp-10h]
0x1400b5b51  sub     rsp, 110h
0x1400b5b58  mov     rax, cs:__security_cookie
0x1400b5b5f  xor     rax, rsp
0x1400b5b62  mov     [rbp+30h+var_30], rax
0x1400b5b66  mov     rdi, [rcx+4A0h]
0x1400b5b6d  lea     rax, [rsp+130h+var_F8]
0x1400b5b72  mov     r9, [rdx+8]
0x1400b5b76  xor     r14d, r14d
0x1400b5b79  mov     rbx, rdx
0x1400b5b7c  mov     [rsp+130h+var_F8], r14
0x1400b5b81  mov     rdx, [rdx]
0x1400b5b84  mov     rsi, rcx
0x1400b5b87  mov     rcx, rdi
0x1400b5b8a  mov     [rsp+130h+var_110], rax
0x1400b5b8f  lea     r8d, [r14+1]
0x1400b5b93  call    cs:__imp_WinHvUnmapGpaPages
0x1400b5b9a  nop     dword ptr [rax+rax+00h]
0x1400b5b9f  mov     r8d, eax
0x1400b5ba2  test    eax, eax
0x1400b5ba4  jns     loc_1400B5CAA
0x1400b5baa  mov     ecx, cs:dword_140064110
0x1400b5bb0  cmp     ecx, 2
0x1400b5bb3  jbe     loc_1400B5CAA
0x1400b5bb9  mov     edx, 100h
0x1400b5bbe  lea     rcx, dword_140064110
0x1400b5bc5  call    _tlgKeywordOn
0x1400b5bca  test    al, al
0x1400b5bcc  jz      loc_1400B5CAA
0x1400b5bd2  lea     rdx, aVsmmphustorepg_0; "VsmmPhuStorepGpaRangeFree"
0x1400b5bd9  lea     rcx, [rbp+30h+var_B0]
0x1400b5bdd  call    _tlgCreate1Sz_char
0x1400b5be2  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b5be9  lea     rcx, [rbp+30h+var_A0]
0x1400b5bed  call    _tlgCreate1Sz_char
0x1400b5bf2  lea     rax, [rsp+130h+var_100]
0x1400b5bf7  mov     [rsp+130h+var_FC], r8d
0x1400b5bfc  mov     [rbp+30h+var_90], rax
0x1400b5c00  lea     rdx, byte_14004F237
0x1400b5c07  lea     rax, [rsp+130h+var_FC]
0x1400b5c0c  mov     [rsp+130h+var_100], 1AB3h
0x1400b5c14  mov     [rbp+30h+var_80], rax
0x1400b5c18  lea     rcx, dword_140064110
0x1400b5c1f  lea     rax, [rsi+30h]
0x1400b5c23  mov     [rbp+30h+var_88], 4
0x1400b5c2b  mov     [rbp+30h+var_70], rax
0x1400b5c2f  xor     r9d, r9d
0x1400b5c32  mov     rax, [rbx]
0x1400b5c35  xor     r8d, r8d
0x1400b5c38  mov     [rsp+130h+var_F0], rax
0x1400b5c3d  lea     rax, [rsp+130h+var_F0]
0x1400b5c42  mov     [rbp+30h+var_60], rax
0x1400b5c46  mov     rax, [rbx+8]
0x1400b5c4a  mov     [rsp+130h+var_E8], rax
0x1400b5c4f  lea     rax, [rsp+130h+var_E8]
0x1400b5c54  mov     [rbp+30h+var_50], rax
0x1400b5c58  mov     rax, [rsp+130h+var_F8]
0x1400b5c5d  mov     [rsp+130h+var_E0], rax
0x1400b5c62  lea     rax, [rsp+130h+var_E0]
0x1400b5c67  mov     [rbp+30h+var_40], rax
0x1400b5c6b  lea     rax, [rsp+130h+var_D0]
0x1400b5c70  mov     [rsp+130h+var_108], rax
0x1400b5c75  mov     dword ptr [rsp+130h+var_110], 0Ah
0x1400b5c7d  mov     [rbp+30h+var_78], 4
0x1400b5c85  mov     [rbp+30h+var_68], 10h
0x1400b5c8d  mov     [rbp+30h+var_58], 8
0x1400b5c95  mov     [rbp+30h+var_48], 8
0x1400b5c9d  mov     [rbp+30h+var_38], 8
0x1400b5ca5  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b5caa  mov     r8, [rbx+8]
0x1400b5cae  lea     r9, [rsp+130h+var_F8]
0x1400b5cb3  mov     rdx, [rbx]
0x1400b5cb6  mov     rcx, rdi
0x1400b5cb9  call    cs:__imp_WinHvUncommitGpaPages
0x1400b5cc0  nop     dword ptr [rax+rax+00h]
0x1400b5cc5  mov     r8d, eax
0x1400b5cc8  test    eax, eax
0x1400b5cca  jns     loc_1400B5DD0
0x1400b5cd0  mov     ecx, cs:dword_140064110
0x1400b5cd6  cmp     ecx, 2
0x1400b5cd9  jbe     loc_1400B5DD0
0x1400b5cdf  mov     edx, 100h
0x1400b5ce4  lea     rcx, dword_140064110
0x1400b5ceb  call    _tlgKeywordOn
0x1400b5cf0  test    al, al
0x1400b5cf2  jz      loc_1400B5DD0
0x1400b5cf8  lea     rdx, aVsmmphustorepg_0; "VsmmPhuStorepGpaRangeFree"
0x1400b5cff  lea     rcx, [rbp+30h+var_B0]
0x1400b5d03  call    _tlgCreate1Sz_char
0x1400b5d08  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b5d0f  lea     rcx, [rbp+30h+var_A0]
0x1400b5d13  call    _tlgCreate1Sz_char
0x1400b5d18  lea     rax, [rsp+130h+var_FC]
0x1400b5d1d  mov     [rsp+130h+var_100], r8d
0x1400b5d22  mov     [rbp+30h+var_90], rax
0x1400b5d26  lea     rdx, word_14004F2B2
0x1400b5d2d  lea     rax, [rsp+130h+var_100]
0x1400b5d32  mov     [rsp+130h+var_FC], 1AC4h
0x1400b5d3a  mov     [rbp+30h+var_80], rax
0x1400b5d3e  lea     rcx, dword_140064110
0x1400b5d45  lea     rax, [rsi+30h]
0x1400b5d49  mov     [rbp+30h+var_88], 4
0x1400b5d51  mov     [rbp+30h+var_70], rax
0x1400b5d55  xor     r9d, r9d
0x1400b5d58  mov     rax, [rbx]
0x1400b5d5b  xor     r8d, r8d
0x1400b5d5e  mov     [rsp+130h+var_E0], rax
0x1400b5d63  lea     rax, [rsp+130h+var_E0]
0x1400b5d68  mov     [rbp+30h+var_60], rax
0x1400b5d6c  mov     rax, [rbx+8]
0x1400b5d70  mov     [rsp+130h+var_E8], rax
0x1400b5d75  lea     rax, [rsp+130h+var_E8]
0x1400b5d7a  mov     [rbp+30h+var_50], rax
0x1400b5d7e  mov     rax, [rsp+130h+var_F8]
0x1400b5d83  mov     [rsp+130h+var_F0], rax
0x1400b5d88  lea     rax, [rsp+130h+var_F0]
0x1400b5d8d  mov     [rbp+30h+var_40], rax
0x1400b5d91  lea     rax, [rsp+130h+var_D0]
0x1400b5d96  mov     [rsp+130h+var_108], rax
0x1400b5d9b  mov     dword ptr [rsp+130h+var_110], 0Ah
0x1400b5da3  mov     [rbp+30h+var_78], 4
0x1400b5dab  mov     [rbp+30h+var_68], 10h
0x1400b5db3  mov     [rbp+30h+var_58], 8
0x1400b5dbb  mov     [rbp+30h+var_48], 8
0x1400b5dc3  mov     [rbp+30h+var_38], 8
0x1400b5dcb  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b5dd0  mov     [rbx+20h], r14b
0x1400b5dd4  mov     rcx, [rbp+30h+var_30]
0x1400b5dd8  xor     rcx, rsp; StackCookie
0x1400b5ddb  call    __security_check_cookie
0x1400b5de0  mov     rbx, [rsp+130h+arg_10]
0x1400b5de8  add     rsp, 110h
0x1400b5def  pop     r14
0x1400b5df1  pop     r13
0x1400b5df3  pop     rdi
0x1400b5df4  pop     rsi
0x1400b5df5  pop     rbp
0x1400b5df6  retn
```
