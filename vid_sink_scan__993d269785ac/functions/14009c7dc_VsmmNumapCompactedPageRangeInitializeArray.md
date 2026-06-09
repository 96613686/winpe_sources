# VsmmNumapCompactedPageRangeInitializeArray

- ea: `0x14009c7dc`
- end: `0x14009cb2f`
- name: `VsmmNumapCompactedPageRangeInitializeArray`
- size: `851`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14009c458`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x1400217a0`
- `0x140038630`
- `0x14009c7dc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14009cb04`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009cb04`
- `ntoskrnl!ExAllocatePool2` at `0x14009c862`
- `ntoskrnl!ExAllocatePool2` at `0x14009c8c8`
- `ntoskrnl!ExAllocatePool2` at `0x14009c9e1`
- `ntoskrnl!ExAllocatePool2` at `0x14009c862`
- `ntoskrnl!ExAllocatePool2` at `0x14009c8c8`
- `ntoskrnl!ExAllocatePool2` at `0x14009c9e1`
- `ntoskrnl!HalDispatchTable` at `0x14009c7ff`
- `ntoskrnl!HalDispatchTable` at `0x14009c984`

## string_xrefs

- `0x14009c838`: `VsmmNumapCompactedPageRangeInitializeArray`
- `0x14009c888`: `VsmmNumapCompactedPageRangeInitializeArray`
- `0x14009c90b`: `VsmmNumapCompactedPageRangeInitializeArray`
- `0x14009c9b5`: `VsmmNumapCompactedPageRangeInitializeArray`
- `0x14009ca24`: `VsmmNumapCompactedPageRangeInitializeArray`

## pseudocode

```c
__int64 __fastcall VsmmNumapCompactedPageRangeInitializeArray(__int64 a1)
{
  int v2; // ebx
  unsigned int v3; // esi
  __int64 Pool2; // rax
  void *v5; // rdi
  unsigned int v6; // esi
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // edx
  __int64 v10; // r9
  __int64 v11; // r11
  unsigned int v12; // r10d
  bool v13; // cf
  __int64 v14; // r8
  unsigned int v16; // [rsp+30h] [rbp-59h] BYREF
  int v17; // [rsp+34h] [rbp-55h] BYREF
  int v18; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19[2]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v20[16]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v21[16]; // [rsp+70h] [rbp-19h] BYREF
  int *v22; // [rsp+80h] [rbp-9h]
  __int64 v23; // [rsp+88h] [rbp-1h]
  int *v24; // [rsp+90h] [rbp+7h]
  __int64 v25; // [rsp+98h] [rbp+Fh]

  v16 = 0;
  v2 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, unsigned int *))HalDispatchTable->HalQuerySystemInformation)(
         30,
         0,
         0,
         &v16);
  if ( v2 < 0 )
  {
    VidTraceErrorInternal0("VsmmNumapCompactedPageRangeInitializeArray", "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c", 816);
    return (unsigned int)v2;
  }
  v3 = v16;
  if ( !v16 )
  {
    Pool2 = ExAllocatePool2(256, 32, 1833788502);
    v5 = (void *)Pool2;
    if ( !Pool2 )
    {
      v2 = -1073741670;
      VidTraceErrorInternal0(
        "VsmmNumapCompactedPageRangeInitializeArray",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c",
        836);
      return (unsigned int)v2;
    }
    *(_DWORD *)(Pool2 + 8) = 0;
    v6 = 2;
    *(_QWORD *)Pool2 = 0;
    *(_DWORD *)(Pool2 + 24) = 0;
    *(_QWORD *)(Pool2 + 16) = -1;
    goto LABEL_14;
  }
  v7 = ExAllocatePool2(64, v16, 1833788502);
  v5 = (void *)v7;
  if ( v7 )
  {
    v2 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, unsigned int *))HalDispatchTable->HalQuerySystemInformation)(
           30,
           v3,
           v7,
           &v16);
    if ( v2 < 0 )
    {
      VidTraceErrorInternal0(
        "VsmmNumapCompactedPageRangeInitializeArray",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c",
        875);
LABEL_25:
      ExFreePoolWithTag(v5, 0x6D4D6456u);
      return (unsigned int)v2;
    }
    v6 = v16 >> 4;
LABEL_14:
    v8 = ExAllocatePool2(64, 24LL * v6, 1833788502);
    if ( v8 )
    {
      v9 = 0;
      if ( v6 )
      {
        v10 = 0;
        do
        {
          v11 = 3 * v10;
          v12 = v9 + 1;
          v13 = v9++ < v6 - 1;
          *(_BYTE *)(v8 + 8 * v11) = *((_BYTE *)v5 + 16 * v10 + 8);
          *(_QWORD *)(v8 + 8 * v11 + 8) = *((_QWORD *)v5 + 2 * v10);
          if ( v13 )
            v14 = *((_QWORD *)v5 + 2 * v12) - 1LL;
          else
            v14 = *((_QWORD *)v5 + 2 * v10);
          ++v10;
          *(_QWORD *)(v8 + 8 * v11 + 16) = v14;
        }
        while ( v9 < v6 );
      }
      *(_DWORD *)(a1 + 296) = v6;
      *(_QWORD *)(a1 + 288) = v8;
    }
    else
    {
      v2 = -1073741670;
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v20, "VsmmNumapCompactedPageRangeInitializeArray");
        tlgCreate1Sz_char(v21, "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c");
        v18 = 896;
        v22 = &v18;
        v24 = &v17;
        v23 = 4;
        v17 = v6;
        v25 = 4;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140064110, (unsigned __int8 *)&unk_14004A1B8, 0, 0, 6u, v19);
      }
    }
    goto LABEL_25;
  }
  v2 = -1073741670;
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v20, "VsmmNumapCompactedPageRangeInitializeArray");
    tlgCreate1Sz_char(v21, "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c");
    v17 = 864;
    v22 = &v17;
    v24 = &v18;
    v23 = 4;
    v18 = v3;
    v25 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140064110, (unsigned __int8 *)&byte_14004A177, 0, 0, 6u, v19);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14009c7dc  push    rbp
0x14009c7de  push    rbx
0x14009c7df  push    rsi
0x14009c7e0  push    rdi
0x14009c7e1  push    r13
0x14009c7e3  push    r14
0x14009c7e5  lea     rbp, [rsp-2Fh]
0x14009c7ea  sub     rsp, 0B8h
0x14009c7f1  mov     rax, cs:__security_cookie
0x14009c7f8  xor     rax, rsp
0x14009c7fb  mov     [rbp+57h+var_40], rax
0x14009c7ff  mov     rax, cs:__imp_HalDispatchTable
0x14009c806  lea     r9, [rbp+57h+var_B0]
0x14009c80a  xor     edx, edx
0x14009c80c  mov     [rbp+57h+var_B0], 0
0x14009c813  mov     r13, rcx
0x14009c816  xor     r8d, r8d
0x14009c819  mov     rax, [rax+8]
0x14009c81d  lea     ecx, [rdx+1Eh]
0x14009c820  call    _guard_dispatch_icall
0x14009c825  mov     ebx, eax
0x14009c827  test    eax, eax
0x14009c829  jns     short loc_14009C849
0x14009c82b  mov     r8d, 330h
0x14009c831  lea     rdx, aOnecoreVmVidSy_58; "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c"
0x14009c838  lea     rcx, aVsmmnumapcompa; "VsmmNumapCompactedPageRangeInitializeAr"...
0x14009c83f  call    VidTraceErrorInternal0
0x14009c844  jmp     loc_14009CB10
0x14009c849  mov     esi, [rbp+57h+var_B0]
0x14009c84c  mov     r14d, 100h
0x14009c852  mov     r8d, 6D4D6456h
0x14009c858  test    esi, esi
0x14009c85a  jnz     short loc_14009C8C0
0x14009c85c  lea     edx, [rsi+20h]
0x14009c85f  mov     ecx, r14d
0x14009c862  call    cs:__imp_ExAllocatePool2
0x14009c869  nop     dword ptr [rax+rax+00h]
0x14009c86e  mov     rdi, rax
0x14009c871  test    rax, rax
0x14009c874  jnz     short loc_14009C899
0x14009c876  mov     ebx, 0C000009Ah
0x14009c87b  mov     r8d, 344h
0x14009c881  lea     rdx, aOnecoreVmVidSy_58; "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c"
0x14009c888  lea     rcx, aVsmmnumapcompa; "VsmmNumapCompactedPageRangeInitializeAr"...
0x14009c88f  call    VidTraceErrorInternal0
0x14009c894  jmp     loc_14009CB10
0x14009c899  mov     dword ptr [rax+8], 0
0x14009c8a0  mov     esi, 2
0x14009c8a5  mov     qword ptr [rax], 0
0x14009c8ac  mov     dword ptr [rax+18h], 0
0x14009c8b3  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x14009c8bb  jmp     loc_14009C9CC
0x14009c8c0  mov     rdx, rsi
0x14009c8c3  mov     ecx, 40h ; '@'
0x14009c8c8  call    cs:__imp_ExAllocatePool2
0x14009c8cf  nop     dword ptr [rax+rax+00h]
0x14009c8d4  mov     rdi, rax
0x14009c8d7  test    rax, rax
0x14009c8da  jnz     loc_14009C984
0x14009c8e0  mov     eax, cs:dword_140064110
0x14009c8e6  mov     ebx, 0C000009Ah
0x14009c8eb  cmp     eax, 2
0x14009c8ee  jbe     loc_14009CB10
0x14009c8f4  mov     rdx, r14
0x14009c8f7  lea     rcx, dword_140064110
0x14009c8fe  call    _tlgKeywordOn
0x14009c903  test    al, al
0x14009c905  jz      loc_14009CB10
0x14009c90b  lea     rdx, aVsmmnumapcompa; "VsmmNumapCompactedPageRangeInitializeAr"...
0x14009c912  lea     rcx, [rbp+57h+var_80]
0x14009c916  call    _tlgCreate1Sz_char
0x14009c91b  lea     rdx, aOnecoreVmVidSy_58; "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c"
0x14009c922  lea     rcx, [rbp+57h+var_70]
0x14009c926  call    _tlgCreate1Sz_char
0x14009c92b  lea     rax, [rbp+57h+var_AC]
0x14009c92f  mov     [rbp+57h+var_AC], 360h
0x14009c936  mov     [rbp+57h+var_60], rax
0x14009c93a  lea     rcx, [rbp+57h+var_A8]
0x14009c93e  lea     rax, [rbp+57h+var_A0]
0x14009c942  mov     [rbp+57h+var_50], rcx
0x14009c946  mov     [rsp+0E0h+var_B8], rax
0x14009c94b  lea     rdx, byte_14004A177
0x14009c952  xor     r9d, r9d
0x14009c955  mov     [rsp+0E0h+var_C0], 6
0x14009c95d  xor     r8d, r8d
0x14009c960  mov     [rbp+57h+var_58], 4
0x14009c968  lea     rcx, dword_140064110
0x14009c96f  mov     [rbp+57h+var_A8], esi
0x14009c972  mov     [rbp+57h+var_48], 4
0x14009c97a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14009c97f  jmp     loc_14009CB10
0x14009c984  mov     rax, cs:__imp_HalDispatchTable
0x14009c98b  lea     r9, [rbp+57h+var_B0]
0x14009c98f  mov     r8, rdi
0x14009c992  mov     edx, esi
0x14009c994  mov     ecx, 1Eh
0x14009c999  mov     rax, [rax+8]
0x14009c99d  call    _guard_dispatch_icall
0x14009c9a2  mov     ebx, eax
0x14009c9a4  test    eax, eax
0x14009c9a6  jns     short loc_14009C9C6
0x14009c9a8  mov     r8d, 36Bh
0x14009c9ae  lea     rdx, aOnecoreVmVidSy_58; "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c"
0x14009c9b5  lea     rcx, aVsmmnumapcompa; "VsmmNumapCompactedPageRangeInitializeAr"...
0x14009c9bc  call    VidTraceErrorInternal0
0x14009c9c1  jmp     loc_14009CAFC
0x14009c9c6  mov     esi, [rbp+57h+var_B0]
0x14009c9c9  shr     esi, 4
0x14009c9cc  mov     eax, esi
0x14009c9ce  mov     ecx, 40h ; '@'
0x14009c9d3  mov     r8d, 6D4D6456h
0x14009c9d9  lea     rdx, [rax+rax*2]
0x14009c9dd  shl     rdx, 3
0x14009c9e1  call    cs:__imp_ExAllocatePool2
0x14009c9e8  nop     dword ptr [rax+rax+00h]
0x14009c9ed  mov     rcx, rax
0x14009c9f0  test    rax, rax
0x14009c9f3  jnz     loc_14009CA9A
0x14009c9f9  mov     eax, cs:dword_140064110
0x14009c9ff  mov     ebx, 0C000009Ah
0x14009ca04  cmp     eax, 2
0x14009ca07  jbe     loc_14009CAFC
0x14009ca0d  mov     rdx, r14
0x14009ca10  lea     rcx, dword_140064110
0x14009ca17  call    _tlgKeywordOn
0x14009ca1c  test    al, al
0x14009ca1e  jz      loc_14009CAFC
0x14009ca24  lea     rdx, aVsmmnumapcompa; "VsmmNumapCompactedPageRangeInitializeAr"...
0x14009ca2b  lea     rcx, [rbp+57h+var_80]
0x14009ca2f  call    _tlgCreate1Sz_char
0x14009ca34  lea     rdx, aOnecoreVmVidSy_58; "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c"
0x14009ca3b  lea     rcx, [rbp+57h+var_70]
0x14009ca3f  call    _tlgCreate1Sz_char
0x14009ca44  lea     rax, [rbp+57h+var_A8]
0x14009ca48  mov     [rbp+57h+var_A8], 380h
0x14009ca4f  mov     [rbp+57h+var_60], rax
0x14009ca53  lea     rcx, [rbp+57h+var_AC]
0x14009ca57  lea     rax, [rbp+57h+var_A0]
0x14009ca5b  mov     [rbp+57h+var_50], rcx
0x14009ca5f  mov     [rsp+0E0h+var_B8], rax
0x14009ca64  lea     rdx, unk_14004A1B8
0x14009ca6b  xor     r9d, r9d
0x14009ca6e  mov     [rsp+0E0h+var_C0], 6
0x14009ca76  xor     r8d, r8d
0x14009ca79  mov     [rbp+57h+var_58], 4
0x14009ca81  lea     rcx, dword_140064110
0x14009ca88  mov     [rbp+57h+var_AC], esi
0x14009ca8b  mov     [rbp+57h+var_48], 4
0x14009ca93  call    _tlgWriteTransfer_EtwWriteTransfer
0x14009ca98  jmp     short loc_14009CAFC
0x14009ca9a  xor     edx, edx
0x14009ca9c  test    esi, esi
0x14009ca9e  jz      short loc_14009CAEE
0x14009caa0  lea     r14d, [rsi-1]
0x14009caa4  xor     r9d, r9d
0x14009caa7  lea     r11, [r9+r9*2]
0x14009caab  mov     r8, r9
0x14009caae  add     r8, r8
0x14009cab1  lea     r10d, [rdx+1]
0x14009cab5  cmp     edx, r14d
0x14009cab8  mov     edx, r10d
0x14009cabb  mov     al, [rdi+r8*8+8]
0x14009cac0  mov     [rcx+r11*8], al
0x14009cac4  mov     rax, [rdi+r8*8]
0x14009cac8  mov     [rcx+r11*8+8], rax
0x14009cacd  jnb     short loc_14009CADE
0x14009cacf  mov     eax, r10d
0x14009cad2  add     rax, rax
0x14009cad5  mov     r8, [rdi+rax*8]
0x14009cad9  dec     r8
0x14009cadc  jmp     short loc_14009CAE2
0x14009cade  mov     r8, [rdi+r8*8]
0x14009cae2  inc     r9
0x14009cae5  mov     [rcx+r11*8+10h], r8
0x14009caea  cmp     edx, esi
0x14009caec  jb      short loc_14009CAA7
0x14009caee  mov     [r13+128h], esi
0x14009caf5  mov     [r13+120h], rcx
0x14009cafc  mov     edx, 6D4D6456h; Tag
0x14009cb01  mov     rcx, rdi; P
0x14009cb04  call    cs:__imp_ExFreePoolWithTag
0x14009cb0b  nop     dword ptr [rax+rax+00h]
0x14009cb10  mov     eax, ebx
0x14009cb12  mov     rcx, [rbp+57h+var_40]
0x14009cb16  xor     rcx, rsp; StackCookie
0x14009cb19  call    __security_check_cookie
0x14009cb1e  add     rsp, 0B8h
0x14009cb25  pop     r14
0x14009cb27  pop     r13
0x14009cb29  pop     rdi
0x14009cb2a  pop     rsi
0x14009cb2b  pop     rbx
0x14009cb2c  pop     rbp
0x14009cb2d  retn
```
