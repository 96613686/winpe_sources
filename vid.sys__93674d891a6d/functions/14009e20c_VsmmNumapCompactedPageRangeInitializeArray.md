# VsmmNumapCompactedPageRangeInitializeArray

- ea: `0x14009e20c`
- end: `0x14009e55f`
- name: `VsmmNumapCompactedPageRangeInitializeArray`
- size: `851`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14009de88`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x140021db0`
- `0x1400386a0`
- `0x14009e20c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14009e534`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009e534`
- `ntoskrnl!ExAllocatePool2` at `0x14009e292`
- `ntoskrnl!ExAllocatePool2` at `0x14009e2f8`
- `ntoskrnl!ExAllocatePool2` at `0x14009e411`
- `ntoskrnl!ExAllocatePool2` at `0x14009e292`
- `ntoskrnl!ExAllocatePool2` at `0x14009e2f8`
- `ntoskrnl!ExAllocatePool2` at `0x14009e411`
- `ntoskrnl!HalDispatchTable` at `0x14009e22f`
- `ntoskrnl!HalDispatchTable` at `0x14009e3b4`

## string_xrefs

- `0x14009e268`: `VsmmNumapCompactedPageRangeInitializeArray`
- `0x14009e2b8`: `VsmmNumapCompactedPageRangeInitializeArray`
- `0x14009e33b`: `VsmmNumapCompactedPageRangeInitializeArray`
- `0x14009e3e5`: `VsmmNumapCompactedPageRangeInitializeArray`
- `0x14009e454`: `VsmmNumapCompactedPageRangeInitializeArray`

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
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v20, "VsmmNumapCompactedPageRangeInitializeArray");
        tlgCreate1Sz_char(v21, "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c");
        v18 = 896;
        v22 = &v18;
        v24 = &v17;
        v23 = 4;
        v17 = v6;
        v25 = 4;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, (unsigned __int8 *)&dword_14004A604, 0, 0, 6u, v19);
      }
    }
    goto LABEL_25;
  }
  v2 = -1073741670;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v20, "VsmmNumapCompactedPageRangeInitializeArray");
    tlgCreate1Sz_char(v21, "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c");
    v17 = 864;
    v22 = &v17;
    v24 = &v18;
    v23 = 4;
    v18 = v3;
    v25 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, (unsigned __int8 *)&dword_14004A64C, 0, 0, 6u, v19);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14009e20c  push    rbp
0x14009e20e  push    rbx
0x14009e20f  push    rsi
0x14009e210  push    rdi
0x14009e211  push    r13
0x14009e213  push    r14
0x14009e215  lea     rbp, [rsp-2Fh]
0x14009e21a  sub     rsp, 0B8h
0x14009e221  mov     rax, cs:__security_cookie
0x14009e228  xor     rax, rsp
0x14009e22b  mov     [rbp+57h+var_40], rax
0x14009e22f  mov     rax, cs:__imp_HalDispatchTable
0x14009e236  lea     r9, [rbp+57h+var_B0]
0x14009e23a  xor     edx, edx
0x14009e23c  mov     [rbp+57h+var_B0], 0
0x14009e243  mov     r13, rcx
0x14009e246  xor     r8d, r8d
0x14009e249  mov     rax, [rax+8]
0x14009e24d  lea     ecx, [rdx+1Eh]
0x14009e250  call    _guard_dispatch_icall
0x14009e255  mov     ebx, eax
0x14009e257  test    eax, eax
0x14009e259  jns     short loc_14009E279
0x14009e25b  mov     r8d, 330h
0x14009e261  lea     rdx, aOnecoreVmVidSy_58; "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c"
0x14009e268  lea     rcx, aVsmmnumapcompa; "VsmmNumapCompactedPageRangeInitializeAr"...
0x14009e26f  call    VidTraceErrorInternal0
0x14009e274  jmp     loc_14009E540
0x14009e279  mov     esi, [rbp+57h+var_B0]
0x14009e27c  mov     r14d, 100h
0x14009e282  mov     r8d, 6D4D6456h
0x14009e288  test    esi, esi
0x14009e28a  jnz     short loc_14009E2F0
0x14009e28c  lea     edx, [rsi+20h]
0x14009e28f  mov     ecx, r14d
0x14009e292  call    cs:__imp_ExAllocatePool2
0x14009e299  nop     dword ptr [rax+rax+00h]
0x14009e29e  mov     rdi, rax
0x14009e2a1  test    rax, rax
0x14009e2a4  jnz     short loc_14009E2C9
0x14009e2a6  mov     ebx, 0C000009Ah
0x14009e2ab  mov     r8d, 344h
0x14009e2b1  lea     rdx, aOnecoreVmVidSy_58; "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c"
0x14009e2b8  lea     rcx, aVsmmnumapcompa; "VsmmNumapCompactedPageRangeInitializeAr"...
0x14009e2bf  call    VidTraceErrorInternal0
0x14009e2c4  jmp     loc_14009E540
0x14009e2c9  mov     dword ptr [rax+8], 0
0x14009e2d0  mov     esi, 2
0x14009e2d5  mov     qword ptr [rax], 0
0x14009e2dc  mov     dword ptr [rax+18h], 0
0x14009e2e3  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x14009e2eb  jmp     loc_14009E3FC
0x14009e2f0  mov     rdx, rsi
0x14009e2f3  mov     ecx, 40h ; '@'
0x14009e2f8  call    cs:__imp_ExAllocatePool2
0x14009e2ff  nop     dword ptr [rax+rax+00h]
0x14009e304  mov     rdi, rax
0x14009e307  test    rax, rax
0x14009e30a  jnz     loc_14009E3B4
0x14009e310  mov     eax, cs:dword_140065110
0x14009e316  mov     ebx, 0C000009Ah
0x14009e31b  cmp     eax, 2
0x14009e31e  jbe     loc_14009E540
0x14009e324  mov     rdx, r14
0x14009e327  lea     rcx, dword_140065110
0x14009e32e  call    _tlgKeywordOn
0x14009e333  test    al, al
0x14009e335  jz      loc_14009E540
0x14009e33b  lea     rdx, aVsmmnumapcompa; "VsmmNumapCompactedPageRangeInitializeAr"...
0x14009e342  lea     rcx, [rbp+57h+var_80]
0x14009e346  call    _tlgCreate1Sz_char
0x14009e34b  lea     rdx, aOnecoreVmVidSy_58; "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c"
0x14009e352  lea     rcx, [rbp+57h+var_70]
0x14009e356  call    _tlgCreate1Sz_char
0x14009e35b  lea     rax, [rbp+57h+var_AC]
0x14009e35f  mov     [rbp+57h+var_AC], 360h
0x14009e366  mov     [rbp+57h+var_60], rax
0x14009e36a  lea     rcx, [rbp+57h+var_A8]
0x14009e36e  lea     rax, [rbp+57h+var_A0]
0x14009e372  mov     [rbp+57h+var_50], rcx
0x14009e376  mov     [rsp+0E0h+var_B8], rax
0x14009e37b  lea     rdx, dword_14004A64C
0x14009e382  xor     r9d, r9d
0x14009e385  mov     [rsp+0E0h+var_C0], 6
0x14009e38d  xor     r8d, r8d
0x14009e390  mov     [rbp+57h+var_58], 4
0x14009e398  lea     rcx, dword_140065110
0x14009e39f  mov     [rbp+57h+var_A8], esi
0x14009e3a2  mov     [rbp+57h+var_48], 4
0x14009e3aa  call    _tlgWriteTransfer_EtwWriteTransfer
0x14009e3af  jmp     loc_14009E540
0x14009e3b4  mov     rax, cs:__imp_HalDispatchTable
0x14009e3bb  lea     r9, [rbp+57h+var_B0]
0x14009e3bf  mov     r8, rdi
0x14009e3c2  mov     edx, esi
0x14009e3c4  mov     ecx, 1Eh
0x14009e3c9  mov     rax, [rax+8]
0x14009e3cd  call    _guard_dispatch_icall
0x14009e3d2  mov     ebx, eax
0x14009e3d4  test    eax, eax
0x14009e3d6  jns     short loc_14009E3F6
0x14009e3d8  mov     r8d, 36Bh
0x14009e3de  lea     rdx, aOnecoreVmVidSy_58; "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c"
0x14009e3e5  lea     rcx, aVsmmnumapcompa; "VsmmNumapCompactedPageRangeInitializeAr"...
0x14009e3ec  call    VidTraceErrorInternal0
0x14009e3f1  jmp     loc_14009E52C
0x14009e3f6  mov     esi, [rbp+57h+var_B0]
0x14009e3f9  shr     esi, 4
0x14009e3fc  mov     eax, esi
0x14009e3fe  mov     ecx, 40h ; '@'
0x14009e403  mov     r8d, 6D4D6456h
0x14009e409  lea     rdx, [rax+rax*2]
0x14009e40d  shl     rdx, 3
0x14009e411  call    cs:__imp_ExAllocatePool2
0x14009e418  nop     dword ptr [rax+rax+00h]
0x14009e41d  mov     rcx, rax
0x14009e420  test    rax, rax
0x14009e423  jnz     loc_14009E4CA
0x14009e429  mov     eax, cs:dword_140065110
0x14009e42f  mov     ebx, 0C000009Ah
0x14009e434  cmp     eax, 2
0x14009e437  jbe     loc_14009E52C
0x14009e43d  mov     rdx, r14
0x14009e440  lea     rcx, dword_140065110
0x14009e447  call    _tlgKeywordOn
0x14009e44c  test    al, al
0x14009e44e  jz      loc_14009E52C
0x14009e454  lea     rdx, aVsmmnumapcompa; "VsmmNumapCompactedPageRangeInitializeAr"...
0x14009e45b  lea     rcx, [rbp+57h+var_80]
0x14009e45f  call    _tlgCreate1Sz_char
0x14009e464  lea     rdx, aOnecoreVmVidSy_58; "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c"
0x14009e46b  lea     rcx, [rbp+57h+var_70]
0x14009e46f  call    _tlgCreate1Sz_char
0x14009e474  lea     rax, [rbp+57h+var_A8]
0x14009e478  mov     [rbp+57h+var_A8], 380h
0x14009e47f  mov     [rbp+57h+var_60], rax
0x14009e483  lea     rcx, [rbp+57h+var_AC]
0x14009e487  lea     rax, [rbp+57h+var_A0]
0x14009e48b  mov     [rbp+57h+var_50], rcx
0x14009e48f  mov     [rsp+0E0h+var_B8], rax
0x14009e494  lea     rdx, dword_14004A604
0x14009e49b  xor     r9d, r9d
0x14009e49e  mov     [rsp+0E0h+var_C0], 6
0x14009e4a6  xor     r8d, r8d
0x14009e4a9  mov     [rbp+57h+var_58], 4
0x14009e4b1  lea     rcx, dword_140065110
0x14009e4b8  mov     [rbp+57h+var_AC], esi
0x14009e4bb  mov     [rbp+57h+var_48], 4
0x14009e4c3  call    _tlgWriteTransfer_EtwWriteTransfer
0x14009e4c8  jmp     short loc_14009E52C
0x14009e4ca  xor     edx, edx
0x14009e4cc  test    esi, esi
0x14009e4ce  jz      short loc_14009E51E
0x14009e4d0  lea     r14d, [rsi-1]
0x14009e4d4  xor     r9d, r9d
0x14009e4d7  lea     r11, [r9+r9*2]
0x14009e4db  mov     r8, r9
0x14009e4de  add     r8, r8
0x14009e4e1  lea     r10d, [rdx+1]
0x14009e4e5  cmp     edx, r14d
0x14009e4e8  mov     edx, r10d
0x14009e4eb  mov     al, [rdi+r8*8+8]
0x14009e4f0  mov     [rcx+r11*8], al
0x14009e4f4  mov     rax, [rdi+r8*8]
0x14009e4f8  mov     [rcx+r11*8+8], rax
0x14009e4fd  jnb     short loc_14009E50E
0x14009e4ff  mov     eax, r10d
0x14009e502  add     rax, rax
0x14009e505  mov     r8, [rdi+rax*8]
0x14009e509  dec     r8
0x14009e50c  jmp     short loc_14009E512
0x14009e50e  mov     r8, [rdi+r8*8]
0x14009e512  inc     r9
0x14009e515  mov     [rcx+r11*8+10h], r8
0x14009e51a  cmp     edx, esi
0x14009e51c  jb      short loc_14009E4D7
0x14009e51e  mov     [r13+128h], esi
0x14009e525  mov     [r13+120h], rcx
0x14009e52c  mov     edx, 6D4D6456h; Tag
0x14009e531  mov     rcx, rdi; P
0x14009e534  call    cs:__imp_ExFreePoolWithTag
0x14009e53b  nop     dword ptr [rax+rax+00h]
0x14009e540  mov     eax, ebx
0x14009e542  mov     rcx, [rbp+57h+var_40]
0x14009e546  xor     rcx, rsp; StackCookie
0x14009e549  call    __security_check_cookie
0x14009e54e  add     rsp, 0B8h
0x14009e555  pop     r14
0x14009e557  pop     r13
0x14009e559  pop     rdi
0x14009e55a  pop     rsi
0x14009e55b  pop     rbx
0x14009e55c  pop     rbp
0x14009e55d  retn
```
