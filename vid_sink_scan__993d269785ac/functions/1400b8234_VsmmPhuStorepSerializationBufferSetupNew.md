# VsmmPhuStorepSerializationBufferSetupNew

- ea: `0x1400b8234`
- end: `0x1400b84ce`
- name: `VsmmPhuStorepSerializationBufferSetupNew`
- size: `666`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400b408c`
- `0x1400b8974`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002f524`
- `0x1400b8234`
- `0x1400b8848`

## import_xrefs

- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400b829a`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400b829a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400b846a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400b846a`
- `ntoskrnl!ExAllocatePool2` at `0x1400b8302`
- `ntoskrnl!ExAllocatePool2` at `0x1400b8302`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x1400b82e5`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x1400b834b`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x1400b82e5`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x1400b834b`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrPersistMemoryWithMetadata` at `0x1400b8384`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrPersistMemoryWithMetadata` at `0x1400b8384`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorepSerializationBufferSetupNew(__int64 a1, __int64 a2, __int64 a3)
{
  PMDL PagesForMdl; // rax
  int v6; // ebx
  unsigned int *v7; // rsi
  __int64 Pool2; // rax
  __int64 v9; // r8
  __int64 v10; // rdx
  PVOID v11; // rax
  int v13; // [rsp+30h] [rbp-69h] BYREF
  int v14; // [rsp+34h] [rbp-65h] BYREF
  int v15; // [rsp+38h] [rbp-61h] BYREF
  __int64 v16; // [rsp+40h] [rbp-59h] BYREF
  char v17[32]; // [rsp+50h] [rbp-49h] BYREF
  char v18[16]; // [rsp+70h] [rbp-29h] BYREF
  char v19[16]; // [rsp+80h] [rbp-19h] BYREF
  int *v20; // [rsp+90h] [rbp-9h]
  __int64 v21; // [rsp+98h] [rbp-1h]
  int *v22; // [rsp+A0h] [rbp+7h]
  __int64 v23; // [rsp+A8h] [rbp+Fh]
  int *v24; // [rsp+B0h] [rbp+17h]
  __int64 v25; // [rsp+B8h] [rbp+1Fh]

  *(_OWORD *)a3 = 0;
  *(_OWORD *)(a3 + 16) = 0;
  *(_OWORD *)(a3 + 32) = 0;
  *(_QWORD *)(a3 + 48) = 0;
  v16 = 0;
  PagesForMdl = MmAllocatePagesForMdlEx(0, (PHYSICAL_ADDRESS)-1LL, 0, a2 << 12, MmCached, 0x15u);
  *(_QWORD *)(a3 + 16) = PagesForMdl;
  if ( PagesForMdl )
  {
    v7 = (unsigned int *)(a3 + 32);
    KsrMdlToMemoryRuns(PagesForMdl, 0, 0, a3 + 32);
    Pool2 = ExAllocatePool2(256, 8LL * *(unsigned int *)(a3 + 32), 1833788502);
    *(_QWORD *)(a3 + 24) = Pool2;
    if ( Pool2 )
    {
      KsrMdlToMemoryRuns(*(_QWORD *)(a3 + 16), Pool2, *v7, a3 + 32);
      v9 = *v7;
      v10 = *(_QWORD *)(a3 + 24);
      v16 = 0x14B646956LL;
      v6 = KsrPersistMemoryWithMetadata(a1, v10, v9, &v16, 8, a3 + 8);
      if ( v6 >= 0 )
      {
        v11 = MmMapLockedPagesSpecifyCache(*(PMDL *)(a3 + 16), 0, MmCached, 0, 0, 0x40000010u);
        *(_QWORD *)a3 = v11;
        if ( v11 )
          return 0;
        v6 = -1073741670;
        VidTraceErrorStatusInternal0(
          "VsmmPhuStorepSerializationBufferSetupNew",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
          10345);
      }
      else if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v18, "VsmmPhuStorepSerializationBufferSetupNew");
        tlgCreate1Sz_char(v19, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
        v13 = 10327;
        v20 = &v13;
        v21 = 4;
        v22 = &v14;
        v15 = *v7;
        v14 = v6;
        v24 = &v15;
        v23 = 4;
        v25 = 4;
        tlgWriteTransfer_EtwWriteTransfer(
          (__int64)&dword_140064110,
          (unsigned __int8 *)&word_14004EEF6,
          0,
          0,
          7u,
          (PEVENT_DATA_DESCRIPTOR)v17);
      }
    }
    else
    {
      v6 = -1073741670;
      VidTraceErrorStatusInternal0(
        "VsmmPhuStorepSerializationBufferSetupNew",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        10300);
    }
  }
  else
  {
    v6 = -1073741670;
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepSerializationBufferSetupNew",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      10277);
  }
  VsmmPhuStorepSerializationBufferTeardown(a1, 0, a3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400b8234  push    rbp
0x1400b8236  push    rbx
0x1400b8237  push    rsi
0x1400b8238  push    rdi
0x1400b8239  push    r14
0x1400b823b  lea     rbp, [rsp-37h]
0x1400b8240  sub     rsp, 0D0h
0x1400b8247  mov     rax, cs:__security_cookie
0x1400b824e  xor     rax, rsp
0x1400b8251  mov     [rbp+57h+var_30], rax
0x1400b8255  xorps   xmm0, xmm0
0x1400b8258  shl     rdx, 0Ch
0x1400b825c  movups  xmmword ptr [r8], xmm0
0x1400b8260  xor     eax, eax
0x1400b8262  mov     rdi, r8
0x1400b8265  movups  xmmword ptr [r8+10h], xmm0
0x1400b826a  mov     r14, rcx
0x1400b826d  mov     r9, rdx; TotalBytes
0x1400b8270  movups  xmmword ptr [r8+20h], xmm0
0x1400b8275  mov     [r8+30h], rax
0x1400b8279  xor     ecx, ecx; LowAddress
0x1400b827b  xor     r8d, r8d; SkipBytes
0x1400b827e  mov     [rsp+0F0h+Flags], 15h; Flags
0x1400b8286  or      rdx, 0FFFFFFFFFFFFFFFFh; HighAddress
0x1400b828a  mov     [rbp+57h+var_B0], 0
0x1400b8292  mov     [rsp+0F0h+CacheType], 1; CacheType
0x1400b829a  call    cs:__imp_MmAllocatePagesForMdlEx
0x1400b82a1  nop     dword ptr [rax+rax+00h]
0x1400b82a6  mov     [rdi+10h], rax
0x1400b82aa  test    rax, rax
0x1400b82ad  jnz     short loc_1400B82D6
0x1400b82af  mov     r9d, 0C000009Ah
0x1400b82b5  mov     ebx, r9d
0x1400b82b8  mov     r8d, 2825h
0x1400b82be  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b82c5  lea     rcx, aVsmmphustoreps_4; "VsmmPhuStorepSerializationBufferSetupNe"...
0x1400b82cc  call    VidTraceErrorStatusInternal0
0x1400b82d1  jmp     loc_1400B84A0
0x1400b82d6  lea     rsi, [rdi+20h]
0x1400b82da  xor     r8d, r8d
0x1400b82dd  mov     r9, rsi
0x1400b82e0  xor     edx, edx
0x1400b82e2  mov     rcx, rax
0x1400b82e5  call    cs:__imp_KsrMdlToMemoryRuns
0x1400b82ec  nop     dword ptr [rax+rax+00h]
0x1400b82f1  mov     edx, [rsi]
0x1400b82f3  mov     ecx, 100h
0x1400b82f8  shl     rdx, 3
0x1400b82fc  mov     r8d, 6D4D6456h
0x1400b8302  call    cs:__imp_ExAllocatePool2
0x1400b8309  nop     dword ptr [rax+rax+00h]
0x1400b830e  mov     [rdi+18h], rax
0x1400b8312  test    rax, rax
0x1400b8315  jnz     short loc_1400B833E
0x1400b8317  mov     r9d, 0C000009Ah
0x1400b831d  mov     ebx, r9d
0x1400b8320  mov     r8d, 283Ch
0x1400b8326  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b832d  lea     rcx, aVsmmphustoreps_4; "VsmmPhuStorepSerializationBufferSetupNe"...
0x1400b8334  call    VidTraceErrorStatusInternal0
0x1400b8339  jmp     loc_1400B84A0
0x1400b833e  mov     r8d, [rsi]
0x1400b8341  mov     r9, rsi
0x1400b8344  mov     rcx, [rdi+10h]
0x1400b8348  mov     rdx, rax
0x1400b834b  call    cs:__imp_KsrMdlToMemoryRuns
0x1400b8352  nop     dword ptr [rax+rax+00h]
0x1400b8357  mov     r8d, [rsi]
0x1400b835a  lea     rax, [rdi+8]
0x1400b835e  mov     rdx, [rdi+18h]
0x1400b8362  lea     r9, [rbp+57h+var_B0]
0x1400b8366  mov     qword ptr [rsp+0F0h+Flags], rax
0x1400b836b  mov     rcx, r14
0x1400b836e  mov     [rsp+0F0h+CacheType], 8
0x1400b8376  mov     dword ptr [rbp+57h+var_B0], 4B646956h
0x1400b837d  mov     dword ptr [rbp+57h+var_B0+4], 1
0x1400b8384  call    cs:__imp_KsrPersistMemoryWithMetadata
0x1400b838b  nop     dword ptr [rax+rax+00h]
0x1400b8390  mov     ebx, eax
0x1400b8392  test    eax, eax
0x1400b8394  jns     loc_1400B844D
0x1400b839a  mov     ecx, cs:dword_140064110
0x1400b83a0  cmp     ecx, 2
0x1400b83a3  jbe     loc_1400B84A0
0x1400b83a9  mov     edx, 100h
0x1400b83ae  lea     rcx, dword_140064110
0x1400b83b5  call    _tlgKeywordOn
0x1400b83ba  test    al, al
0x1400b83bc  jz      loc_1400B84A0
0x1400b83c2  lea     rdx, aVsmmphustoreps_4; "VsmmPhuStorepSerializationBufferSetupNe"...
0x1400b83c9  lea     rcx, [rbp+57h+var_80]
0x1400b83cd  call    _tlgCreate1Sz_char
0x1400b83d2  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b83d9  lea     rcx, [rbp+57h+var_70]
0x1400b83dd  call    _tlgCreate1Sz_char
0x1400b83e2  lea     rax, [rbp+57h+var_C0]
0x1400b83e6  mov     [rbp+57h+var_C0], 2857h
0x1400b83ed  mov     [rbp+57h+var_60], rax
0x1400b83f1  lea     rdx, word_14004EEF6
0x1400b83f8  lea     rax, [rbp+57h+var_BC]
0x1400b83fc  mov     [rbp+57h+var_58], 4
0x1400b8404  mov     [rbp+57h+var_50], rax
0x1400b8408  lea     rcx, dword_140064110
0x1400b840f  mov     eax, [rsi]
0x1400b8411  xor     r9d, r9d
0x1400b8414  mov     [rbp+57h+var_B8], eax
0x1400b8417  xor     r8d, r8d
0x1400b841a  lea     rax, [rbp+57h+var_B8]
0x1400b841e  mov     [rbp+57h+var_BC], ebx
0x1400b8421  mov     [rbp+57h+var_40], rax
0x1400b8425  lea     rax, [rbp+57h+var_A0]
0x1400b8429  mov     qword ptr [rsp+0F0h+Flags], rax
0x1400b842e  mov     [rsp+0F0h+CacheType], 7
0x1400b8436  mov     [rbp+57h+var_48], 4
0x1400b843e  mov     [rbp+57h+var_38], 4
0x1400b8446  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b844b  jmp     short loc_1400B84A0
0x1400b844d  mov     rcx, [rdi+10h]; MemoryDescriptorList
0x1400b8451  xor     r9d, r9d; RequestedAddress
0x1400b8454  mov     [rsp+0F0h+Flags], 40000010h; Priority
0x1400b845c  xor     edx, edx; AccessMode
0x1400b845e  mov     [rsp+0F0h+CacheType], 0; BugCheckOnFailure
0x1400b8466  lea     r8d, [r9+1]; CacheType
0x1400b846a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400b8471  nop     dword ptr [rax+rax+00h]
0x1400b8476  mov     [rdi], rax
0x1400b8479  test    rax, rax
0x1400b847c  jnz     short loc_1400B84AF
0x1400b847e  mov     r9d, 0C000009Ah
0x1400b8484  mov     ebx, r9d
0x1400b8487  mov     r8d, 2869h
0x1400b848d  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b8494  lea     rcx, aVsmmphustoreps_4; "VsmmPhuStorepSerializationBufferSetupNe"...
0x1400b849b  call    VidTraceErrorStatusInternal0
0x1400b84a0  mov     r8, rdi
0x1400b84a3  xor     edx, edx
0x1400b84a5  mov     rcx, r14
0x1400b84a8  call    VsmmPhuStorepSerializationBufferTeardown
0x1400b84ad  jmp     short loc_1400B84B1
0x1400b84af  xor     ebx, ebx
0x1400b84b1  mov     eax, ebx
0x1400b84b3  mov     rcx, [rbp+57h+var_30]
0x1400b84b7  xor     rcx, rsp; StackCookie
0x1400b84ba  call    __security_check_cookie
0x1400b84bf  add     rsp, 0D0h
0x1400b84c6  pop     r14
0x1400b84c8  pop     rdi
0x1400b84c9  pop     rsi
0x1400b84ca  pop     rbx
0x1400b84cb  pop     rbp
0x1400b84cc  retn
```
