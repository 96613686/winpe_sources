# VsmmPhuStorepHvPartitionFree

- ea: `0x1400b6360`
- end: `0x1400b6624`
- name: `VsmmPhuStorepHvPartitionFree`
- size: `708`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400b4958`
- `0x1400b6088`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140024dc8`
- `0x1400b6360`
- `0x1400b8954`

## import_xrefs

- `winhvr!WinHvSetPartitionProperty` at `0x1400b63ab`
- `winhvr!WinHvSetPartitionProperty` at `0x1400b640d`
- `winhvr!WinHvSetPartitionProperty` at `0x1400b63ab`
- `winhvr!WinHvSetPartitionProperty` at `0x1400b640d`
- `winhvr!WinHvDeletePartition` at `0x1400b65d1`
- `winhvr!WinHvDeletePartition` at `0x1400b65d1`
- `winhvr!WinHvDeletePartitionRemote` at `0x1400b64f0`
- `winhvr!WinHvDeletePartitionRemote` at `0x1400b64f0`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorepHvPartitionFree(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  int v5; // eax
  int v6; // edx
  int v7; // ecx
  unsigned __int64 v8; // rcx
  int v9; // r8d
  int v10; // r8d
  int v11; // eax
  int v12; // edx
  int v13; // ecx
  int v15; // [rsp+30h] [rbp-69h] BYREF
  int v16; // [rsp+34h] [rbp-65h] BYREF
  __int64 v17; // [rsp+38h] [rbp-61h] BYREF
  __int64 v18; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v19[32]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v20[16]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v21[16]; // [rsp+80h] [rbp-19h] BYREF
  int *v22; // [rsp+90h] [rbp-9h]
  __int64 v23; // [rsp+98h] [rbp-1h]
  int *v24; // [rsp+A0h] [rbp+7h]
  __int64 v25; // [rsp+A8h] [rbp+Fh]
  __int64 *v26; // [rsp+B0h] [rbp+17h]
  __int64 v27; // [rsp+B8h] [rbp+1Fh]
  __int64 *v28; // [rsp+C0h] [rbp+27h]
  __int64 v29; // [rsp+C8h] [rbp+2Fh]

  v3 = *(_QWORD *)(a2 + 56);
  if ( (unsigned __int64)((*(_DWORD *)(a2 + 40) >> 10) & 0xF) - 2 <= 2 )
  {
    v5 = WinHvSetPartitionProperty(v3);
    if ( v5 < 0 )
      VidTracePartitionIdErrorInternal0(v7, v6, 7257, v3, v5);
  }
  v8 = *(_QWORD *)(a2 + 40);
  if ( (((v8 >> 10) & 0xF) - 2 <= 2 || ((((unsigned __int16)v8 & 0xC000) - 0x4000LL) & 0xFFFFFFFFFFFFBFFFuLL) == 0)
    && (int)WinHvSetPartitionProperty(v3) < 0
    && (unsigned int)dword_140064110 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v20, "VsmmPhuStorepHvPartitionFree");
    tlgCreate1Sz_char(v21, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    v16 = v9;
    v29 = 8;
    v22 = &v15;
    v15 = 7275;
    v24 = &v16;
    v23 = 4;
    v26 = (__int64 *)(a1 + 48);
    v25 = 4;
    v28 = &v17;
    v27 = 16;
    v17 = v3;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004F175, 0, 0, 8, v19);
  }
  if ( *(_QWORD *)(a2 + 104)
    && (int)WinHvDeletePartitionRemote(v3) < 0
    && (unsigned int)dword_140064110 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v20, "VsmmPhuStorepHvPartitionFree");
    tlgCreate1Sz_char(v21, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    v15 = v10;
    v27 = 8;
    v22 = &v16;
    v29 = 8;
    v24 = &v15;
    v16 = 7290;
    v26 = &v17;
    v18 = *(_QWORD *)(a2 + 104);
    v28 = &v18;
    v23 = 4;
    v25 = 4;
    v17 = v3;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &dword_14004F1D4, 0, 0, 8, v19);
  }
  if ( v3 )
  {
    v11 = WinHvDeletePartition(v3);
    if ( v11 < 0 )
      VidTracePartitionIdErrorInternal0(v13, v12, 7306, v3, v11);
  }
  *(_BYTE *)(a2 + 48) = 0;
  return VsmmPhuStorepSerializationChargeDecrease(a1, 144);
}

```

## disassembly

```asm
0x1400b6360  mov     [rsp-8+arg_10], rbx
0x1400b6365  push    rbp
0x1400b6366  push    rsi
0x1400b6367  push    rdi
0x1400b6368  lea     rbp, [rsp-47h]
0x1400b636d  sub     rsp, 0E0h
0x1400b6374  mov     rax, cs:__security_cookie
0x1400b637b  xor     rax, rsp
0x1400b637e  mov     [rbp+57h+var_20], rax
0x1400b6382  mov     eax, [rdx+28h]
0x1400b6385  mov     rdi, rdx
0x1400b6388  mov     rbx, [rdx+38h]
0x1400b638c  mov     rsi, rcx
0x1400b638f  shr     rax, 0Ah
0x1400b6393  and     eax, 0Fh
0x1400b6396  sub     rax, 2
0x1400b639a  cmp     rax, 2
0x1400b639e  ja      short loc_1400B63CD
0x1400b63a0  xor     r8d, r8d
0x1400b63a3  mov     edx, 5000Dh
0x1400b63a8  mov     rcx, rbx
0x1400b63ab  call    cs:__imp_WinHvSetPartitionProperty
0x1400b63b2  nop     dword ptr [rax+rax+00h]
0x1400b63b7  test    eax, eax
0x1400b63b9  jns     short loc_1400B63CD
0x1400b63bb  mov     r9, rbx
0x1400b63be  mov     [rsp+0F0h+var_D0], eax
0x1400b63c2  mov     r8d, 1C59h
0x1400b63c8  call    VidTracePartitionIdErrorInternal0
0x1400b63cd  mov     rcx, [rdi+28h]
0x1400b63d1  mov     rax, rcx
0x1400b63d4  shr     rax, 0Ah
0x1400b63d8  and     eax, 0Fh
0x1400b63db  sub     rax, 2
0x1400b63df  cmp     rax, 2
0x1400b63e3  jbe     short loc_1400B63FF
0x1400b63e5  and     ecx, 0C000h
0x1400b63eb  sub     rcx, 4000h
0x1400b63f2  test    rcx, 0FFFFFFFFFFFFBFFFh
0x1400b63f9  jnz     loc_1400B64E2
0x1400b63ff  mov     edx, 5000Ch
0x1400b6404  mov     r8d, 2
0x1400b640a  mov     rcx, rbx
0x1400b640d  call    cs:__imp_WinHvSetPartitionProperty
0x1400b6414  nop     dword ptr [rax+rax+00h]
0x1400b6419  mov     r8d, eax
0x1400b641c  test    eax, eax
0x1400b641e  jns     loc_1400B64E2
0x1400b6424  mov     ecx, cs:dword_140064110
0x1400b642a  cmp     ecx, 2
0x1400b642d  jbe     loc_1400B64E2
0x1400b6433  mov     edx, 100h
0x1400b6438  lea     rcx, dword_140064110
0x1400b643f  call    _tlgKeywordOn
0x1400b6444  test    al, al
0x1400b6446  jz      loc_1400B64E2
0x1400b644c  lea     rdx, aVsmmphustoreph_1; "VsmmPhuStorepHvPartitionFree"
0x1400b6453  lea     rcx, [rbp+57h+var_80]
0x1400b6457  call    _tlgCreate1Sz_char
0x1400b645c  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6463  lea     rcx, [rbp+57h+var_70]
0x1400b6467  call    _tlgCreate1Sz_char
0x1400b646c  mov     ecx, 8
0x1400b6471  mov     [rbp+57h+var_BC], r8d
0x1400b6475  lea     rax, [rbp+57h+var_C0]
0x1400b6479  mov     [rbp+57h+var_28], rcx
0x1400b647d  mov     [rbp+57h+var_60], rax
0x1400b6481  lea     rdx, byte_14004F175
0x1400b6488  lea     rax, [rbp+57h+var_BC]
0x1400b648c  mov     [rbp+57h+var_C0], 1C6Bh
0x1400b6493  mov     [rbp+57h+var_50], rax
0x1400b6497  xor     r9d, r9d
0x1400b649a  lea     rax, [rsi+30h]
0x1400b649e  mov     [rbp+57h+var_58], 4
0x1400b64a6  mov     [rbp+57h+var_40], rax
0x1400b64aa  xor     r8d, r8d
0x1400b64ad  lea     rax, [rbp+57h+var_B8]
0x1400b64b1  mov     [rbp+57h+var_48], 4
0x1400b64b9  mov     [rbp+57h+var_30], rax
0x1400b64bd  lea     rax, [rbp+57h+var_A0]
0x1400b64c1  mov     [rsp+0F0h+var_C8], rax
0x1400b64c6  mov     [rsp+0F0h+var_D0], ecx
0x1400b64ca  lea     rcx, dword_140064110
0x1400b64d1  mov     [rbp+57h+var_38], 10h
0x1400b64d9  mov     [rbp+57h+var_B8], rbx
0x1400b64dd  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b64e2  cmp     qword ptr [rdi+68h], 0
0x1400b64e7  jz      loc_1400B65C9
0x1400b64ed  mov     rcx, rbx
0x1400b64f0  call    cs:__imp_WinHvDeletePartitionRemote
0x1400b64f7  nop     dword ptr [rax+rax+00h]
0x1400b64fc  mov     r8d, eax
0x1400b64ff  test    eax, eax
0x1400b6501  jns     loc_1400B65C9
0x1400b6507  mov     ecx, cs:dword_140064110
0x1400b650d  cmp     ecx, 2
0x1400b6510  jbe     loc_1400B65C9
0x1400b6516  mov     edx, 100h
0x1400b651b  lea     rcx, dword_140064110
0x1400b6522  call    _tlgKeywordOn
0x1400b6527  test    al, al
0x1400b6529  jz      loc_1400B65C9
0x1400b652f  lea     rdx, aVsmmphustoreph_1; "VsmmPhuStorepHvPartitionFree"
0x1400b6536  lea     rcx, [rbp+57h+var_80]
0x1400b653a  call    _tlgCreate1Sz_char
0x1400b653f  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6546  lea     rcx, [rbp+57h+var_70]
0x1400b654a  call    _tlgCreate1Sz_char
0x1400b654f  mov     ecx, 8
0x1400b6554  mov     [rbp+57h+var_C0], r8d
0x1400b6558  lea     rax, [rbp+57h+var_BC]
0x1400b655c  mov     [rbp+57h+var_38], rcx
0x1400b6560  mov     [rbp+57h+var_60], rax
0x1400b6564  lea     rdx, dword_14004F1D4
0x1400b656b  lea     rax, [rbp+57h+var_C0]
0x1400b656f  mov     [rbp+57h+var_28], rcx
0x1400b6573  mov     [rbp+57h+var_50], rax
0x1400b6577  xor     r9d, r9d
0x1400b657a  lea     rax, [rbp+57h+var_B8]
0x1400b657e  mov     [rbp+57h+var_BC], 1C7Ah
0x1400b6585  mov     [rbp+57h+var_40], rax
0x1400b6589  xor     r8d, r8d
0x1400b658c  mov     rax, [rdi+68h]
0x1400b6590  mov     [rbp+57h+var_B0], rax
0x1400b6594  lea     rax, [rbp+57h+var_B0]
0x1400b6598  mov     [rbp+57h+var_30], rax
0x1400b659c  lea     rax, [rbp+57h+var_A0]
0x1400b65a0  mov     [rsp+0F0h+var_C8], rax
0x1400b65a5  mov     [rsp+0F0h+var_D0], ecx
0x1400b65a9  lea     rcx, dword_140064110
0x1400b65b0  mov     [rbp+57h+var_58], 4
0x1400b65b8  mov     [rbp+57h+var_48], 4
0x1400b65c0  mov     [rbp+57h+var_B8], rbx
0x1400b65c4  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b65c9  test    rbx, rbx
0x1400b65cc  jz      short loc_1400B65F3
0x1400b65ce  mov     rcx, rbx
0x1400b65d1  call    cs:__imp_WinHvDeletePartition
0x1400b65d8  nop     dword ptr [rax+rax+00h]
0x1400b65dd  test    eax, eax
0x1400b65df  jns     short loc_1400B65F3
0x1400b65e1  mov     r9, rbx
0x1400b65e4  mov     [rsp+0F0h+var_D0], eax
0x1400b65e8  mov     r8d, 1C8Ah
0x1400b65ee  call    VidTracePartitionIdErrorInternal0
0x1400b65f3  mov     edx, 90h
0x1400b65f8  mov     byte ptr [rdi+30h], 0
0x1400b65fc  mov     rcx, rsi
0x1400b65ff  call    VsmmPhuStorepSerializationChargeDecrease
0x1400b6604  mov     rcx, [rbp+57h+var_20]
0x1400b6608  xor     rcx, rsp; StackCookie
0x1400b660b  call    __security_check_cookie
0x1400b6610  mov     rbx, [rsp+0F0h+arg_10]
0x1400b6618  add     rsp, 0E0h
0x1400b661f  pop     rdi
0x1400b6620  pop     rsi
0x1400b6621  pop     rbp
0x1400b6622  retn
```
