# VidSynicPortCreateGuestEntry

- ea: `0x140095a7c`
- end: `0x140095fbd`
- name: `VidSynicPortCreateGuestEntry`
- size: `1345`
- prototype: `__int64 __fastcall(__int64, unsigned __int8, char, unsigned int, unsigned int, unsigned int, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x140035698`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x140008fd8`
- `0x14000a4e0`
- `0x140021650`
- `0x140024754`
- `0x140030790`
- `0x1400307d0`
- `0x140038630`
- `0x140095a7c`
- `0x14009712c`
- `0x1400972c8`
- `0x140097304`
- `0x1400973a4`
- `0x1400ef710`
- `0x1400f0270`

## import_xrefs

- `ntoskrnl!MmGetPhysicalAddress` at `0x140095d5f`
- `ntoskrnl!MmGetPhysicalAddress` at `0x140095d5f`
- `ntoskrnl!ExAllocatePool2` at `0x140095bcb`
- `ntoskrnl!ExAllocatePool2` at `0x140095d22`
- `ntoskrnl!ExAllocatePool2` at `0x140095bcb`
- `ntoskrnl!ExAllocatePool2` at `0x140095d22`
- `winhvr!WinHvGetPortProperty` at `0x140095cdb`
- `winhvr!WinHvGetPortProperty` at `0x140095cdb`
- `winhvr!WinHvDisconnectPort` at `0x140095ef7`
- `winhvr!WinHvDisconnectPort` at `0x140095ef7`
- `winhvr!WinHvConnectPort` at `0x140095e40`
- `winhvr!WinHvConnectPort` at `0x140095e40`
- `winhvr!WinHvDeletePort` at `0x140095f48`
- `winhvr!WinHvDeletePort` at `0x140095f48`
- `winhvr!WinHvCreatePort` at `0x140095c7c`
- `winhvr!WinHvCreatePort` at `0x140095c7c`
- `winhvr!WinHvFreePortId` at `0x140095f1a`
- `winhvr!WinHvFreePortId` at `0x140095f1a`
- `winhvr!WinHvAllocatePortId` at `0x140095db1`
- `winhvr!WinHvAllocatePortId` at `0x140095db1`

## string_xrefs

- `0x140095b39`: `VidSynicPortCreateGuestEntry`
- `0x140095bec`: `VidSynicPortCreateGuestEntry`
- `0x140095c9b`: `VidSynicPortCreateGuestEntry`
- `0x140095cfa`: `VidSynicPortCreateGuestEntry`
- `0x140095d44`: `VidSynicPortCreateGuestEntry`
- `0x140095dd0`: `VidSynicPortCreateGuestEntry`
- `0x140095e5f`: `VidSynicPortCreateGuestEntry`
- `0x140095e9a`: `VidSynicPortCreateGuestEntry`
- `0x140095f8e`: `VidSynicPortCreateGuestEntry`

## pseudocode

```c
__int64 __fastcall VidSynicPortCreateGuestEntry(
        __int64 a1,
        unsigned __int8 a2,
        char a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        __int64 a7,
        __int64 *a8)
{
  unsigned int v10; // r14d
  unsigned int v12; // ecx
  char v13; // r12
  unsigned int v14; // ecx
  __int64 v15; // rbx
  int PortProperty; // edi
  __int64 Pool2; // rax
  __int64 v18; // rdx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  bool v21; // r14
  PHYSICAL_ADDRESS PhysicalAddress; // rax
  void *v23; // rax
  char v24; // r15
  __int64 v25; // rax
  __int64 v26; // rcx
  int v28; // [rsp+30h] [rbp-D0h]
  char v29; // [rsp+40h] [rbp-C0h]
  char v30; // [rsp+41h] [rbp-BFh]
  unsigned int v31; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v32; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v35; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+70h] [rbp-90h]
  __int64 *v37; // [rsp+78h] [rbp-88h]
  __int128 v38; // [rsp+80h] [rbp-80h] BYREF
  char v39[32]; // [rsp+90h] [rbp-70h] BYREF
  char v40[16]; // [rsp+B0h] [rbp-50h] BYREF
  char v41[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v42; // [rsp+D0h] [rbp-30h]
  __int64 v43; // [rsp+D8h] [rbp-28h]
  unsigned int *v44; // [rsp+E0h] [rbp-20h]
  __int64 v45; // [rsp+E8h] [rbp-18h]

  v37 = a8;
  v38 = 0;
  v10 = a2;
  HviGetHypervisorFeatures(&v38);
  v12 = *(_DWORD *)a7;
  v13 = 0;
  v36 = 0;
  v34 = 0;
  v33 = -1;
  v30 = 0;
  v31 = 0xFFFFFF;
  v35 = 0;
  v14 = v12 - 1;
  if ( v14 && v14 != 2 )
  {
    v15 = 0;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v40, "VidSynicPortCreateGuestEntry");
      tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c");
      LODWORD(v33) = 625;
      v42 = &v33;
      v32 = *(_DWORD *)a7;
      v43 = 4;
      v44 = &v32;
      v45 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140048FD1, 0, 0, 6, v39);
    }
    PortProperty = -1073741637;
    goto LABEL_44;
  }
  Pool2 = ExAllocatePool2(65, 136, 1917084758);
  v15 = Pool2;
  if ( !Pool2 )
  {
    VidTraceErrorInternal0("VidSynicPortCreateGuestEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 640);
LABEL_9:
    PortProperty = -1073741801;
    goto LABEL_44;
  }
  v18 = v10;
  *(_DWORD *)Pool2 = *(_DWORD *)a7;
  *(_BYTE *)(Pool2 + 40) = 1;
  *(_DWORD *)(Pool2 + 4) = a6;
  v19 = *(_DWORD *)a7;
  v35 = 0;
  LODWORD(v35) = v19;
  v32 = v10 | 0x80000000;
  v36 = 0;
  v20 = v19 - 1;
  if ( v20 )
  {
    if ( v20 == 2 )
    {
      *(_QWORD *)(Pool2 + 120) = Pool2 + 112;
      *(_QWORD *)(Pool2 + 112) = Pool2 + 112;
      *((_QWORD *)&v35 + 1) = *(_QWORD *)(a7 + 8);
    }
  }
  else
  {
    *((_QWORD *)&v35 + 1) = __PAIR64__(a5, a4);
  }
  LODWORD(v18) = v10 | 0x80000000;
  PortProperty = WinHvCreatePort(*(_QWORD *)(a1 + 648), v18, a6, -1, &v35, a3, 0);
  if ( PortProperty < 0 )
  {
    VidTraceErrorInternal0("VidSynicPortCreateGuestEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 683);
    goto LABEL_44;
  }
  v21 = (v38 & 0x100000000000LL) != 0;
  if ( *(_DWORD *)a7 == 3 )
  {
    if ( (v38 & 0x100000000000LL) != 0 )
    {
      PortProperty = WinHvGetPortProperty(*(_QWORD *)(a1 + 648), *(unsigned int *)(v15 + 4), 2, &v34);
      if ( PortProperty < 0 )
      {
        VidTraceErrorInternal0("VidSynicPortCreateGuestEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 703);
        goto LABEL_44;
      }
      PhysicalAddress.QuadPart = v34;
    }
    else
    {
      v23 = (void *)ExAllocatePool2(65, 4096, 1917084758);
      *(_QWORD *)(v15 + 104) = v23;
      if ( !v23 )
      {
        VidTraceErrorInternal0("VidSynicPortCreateGuestEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 725);
        goto LABEL_9;
      }
      *(_BYTE *)(v15 + 128) = 1;
      PhysicalAddress = MmGetPhysicalAddress(v23);
    }
    *(PHYSICAL_ADDRESS *)(a7 + 8) = PhysicalAddress;
  }
  v29 = 1;
  v24 = 0;
  v30 = 1;
  VidLockAcquireExclusive(a1 + 3328);
  PortProperty = VidHandleTableAllocateEntry(a1 + 3296, v15, &v33);
  if ( PortProperty >= 0 )
  {
    PortProperty = WinHvAllocatePortId(v15, &v31);
    if ( PortProperty >= 0 )
    {
      *(_DWORD *)(v15 + 8) = v31;
      v38 = 0;
      HviGetHypervisorFeatures(&v38);
      if ( (v38 & 0x100000000LL) != 0 && !v21 )
        *(_DWORD *)(v15 + 8) = *(_DWORD *)(v15 + 8) & 0x3FFFFFFF | 0x40000000;
      LOBYTE(v28) = 0;
      PortProperty = WinHvConnectPort(
                       -1,
                       v32,
                       *(unsigned int *)(v15 + 8),
                       *(_QWORD *)(a1 + 648),
                       *(_DWORD *)(v15 + 4),
                       a7,
                       v28);
      if ( PortProperty >= 0 )
      {
        if ( *(_DWORD *)a7 == 3 )
        {
          if ( v21 )
          {
            PortProperty = VidSynicPortpMapMonitorPage(v15, v34);
            if ( PortProperty < 0 )
            {
              v24 = 1;
              VidTraceErrorInternal0(
                "VidSynicPortCreateGuestEntry",
                "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c",
                792);
              goto LABEL_39;
            }
          }
          VidSynicPortpInitializeMonitorPage(v15);
        }
        v25 = v33;
        v15 = 0;
        v31 |= 0xFFFFFFu;
        v33 = -1;
        *v37 = v25;
        v29 = 0;
        PortProperty = 0;
        goto LABEL_39;
      }
      VidTraceErrorInternal0("VidSynicPortCreateGuestEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 777);
    }
    else
    {
      VidTraceErrorInternal0("VidSynicPortCreateGuestEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 752);
    }
  }
LABEL_39:
  if ( v33 != -1 )
    VidHandleTableFreeEntry(a1 + 3296, v33);
  if ( v24 )
    WinHvDisconnectPort(-1, *(unsigned int *)(v15 + 8));
  v13 = v29;
LABEL_44:
  v26 = v31;
  if ( (v31 & 0xFFFFFF) != 0xFFFFFF )
    WinHvFreePortId();
  if ( v30 )
    VidLockRelease(a1 + 3328);
  if ( v13 )
    WinHvDeletePort(*(_QWORD *)(a1 + 648), *(unsigned int *)(v15 + 4));
  if ( v15 )
  {
    if ( *(_DWORD *)v15 == 3 )
      VidSynicPortpUnmapMonitorPage(v15);
    VidSynicPortpEntryFree(v26, v15);
  }
  if ( PortProperty < 0 )
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VidSynicPortCreateGuestEntry",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidsynicport.c",
      848,
      PortProperty,
      a1 + 656);
  return (unsigned int)PortProperty;
}

```

## disassembly

```asm
0x140095a7c  push    rbp
0x140095a7e  push    rbx
0x140095a7f  push    rsi
0x140095a80  push    rdi
0x140095a81  push    r12
0x140095a83  push    r13
0x140095a85  push    r14
0x140095a87  push    r15
0x140095a89  lea     rbp, [rsp-8]
0x140095a8e  sub     rsp, 108h
0x140095a95  mov     rax, cs:__security_cookie
0x140095a9c  xor     rax, rsp
0x140095a9f  mov     [rbp+40h+var_50], rax
0x140095aa3  mov     rax, [rbp+40h+arg_38]
0x140095aaa  mov     r13, rcx
0x140095aad  mov     rsi, [rbp+40h+arg_30]
0x140095ab4  lea     rcx, [rbp+40h+var_C0]
0x140095ab8  xorps   xmm0, xmm0
0x140095abb  mov     [rsp+140h+var_C8], rax
0x140095ac0  movups  [rbp+40h+var_C0], xmm0
0x140095ac4  mov     edi, r9d
0x140095ac7  movzx   r14d, dl
0x140095acb  mov     r15b, r8b
0x140095ace  call    HviGetHypervisorFeatures
0x140095ad3  mov     ecx, [rsi]
0x140095ad5  xor     eax, eax
0x140095ad7  xor     r12b, r12b
0x140095ada  mov     [rsp+140h+var_D0], rax
0x140095adf  mov     [rsp+140h+var_E8], rax
0x140095ae4  xorps   xmm1, xmm1
0x140095ae7  mov     [rsp+140h+var_F0], 0FFFFFFFFFFFFFFFFh
0x140095af0  mov     [rsp+140h+var_FF], al
0x140095af4  mov     [rsp+140h+var_FC], 0FFFFFFh
0x140095afc  movups  [rsp+140h+var_E0], xmm1
0x140095b01  sub     ecx, 1
0x140095b04  jz      loc_140095BBD
0x140095b0a  cmp     ecx, 2
0x140095b0d  jz      loc_140095BBD
0x140095b13  mov     eax, cs:dword_140064110
0x140095b19  xor     ebx, ebx
0x140095b1b  cmp     eax, 2
0x140095b1e  jbe     loc_140095BB3
0x140095b24  mov     edx, 100h
0x140095b29  lea     rcx, dword_140064110
0x140095b30  call    _tlgKeywordOn
0x140095b35  test    al, al
0x140095b37  jz      short loc_140095BB3
0x140095b39  lea     rdx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x140095b40  lea     rcx, [rbp+40h+var_90]
0x140095b44  call    _tlgCreate1Sz_char
0x140095b49  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140095b50  lea     rcx, [rbp+40h+var_80]
0x140095b54  call    _tlgCreate1Sz_char
0x140095b59  lea     rax, [rsp+140h+var_F0]
0x140095b5e  mov     dword ptr [rsp+140h+var_F0], 271h
0x140095b66  mov     [rbp+40h+var_70], rax
0x140095b6a  lea     rdx, byte_140048FD1
0x140095b71  mov     eax, [rsi]
0x140095b73  lea     rcx, dword_140064110
0x140095b7a  mov     [rsp+140h+var_F8], eax
0x140095b7e  xor     r9d, r9d
0x140095b81  lea     rax, [rsp+140h+var_F8]
0x140095b86  mov     [rbp+40h+var_68], 4
0x140095b8e  mov     [rbp+40h+var_60], rax
0x140095b92  xor     r8d, r8d
0x140095b95  lea     rax, [rbp+40h+var_B0]
0x140095b99  mov     [rbp+40h+var_58], 4
0x140095ba1  mov     [rsp+140h+var_118], rax
0x140095ba6  mov     dword ptr [rsp+140h+var_120], 6
0x140095bae  call    _tlgWriteTransfer_EtwWriteTransfer
0x140095bb3  mov     edi, 0C00000BBh
0x140095bb8  jmp     loc_140095F08
0x140095bbd  mov     edx, 88h
0x140095bc2  mov     r8d, 72446456h
0x140095bc8  lea     ecx, [rdx-47h]
0x140095bcb  call    cs:__imp_ExAllocatePool2
0x140095bd2  nop     dword ptr [rax+rax+00h]
0x140095bd7  mov     rbx, rax
0x140095bda  test    rax, rax
0x140095bdd  jnz     short loc_140095C02
0x140095bdf  mov     r8d, 280h
0x140095be5  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140095bec  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x140095bf3  call    VidTraceErrorInternal0
0x140095bf8  mov     edi, 0C0000017h
0x140095bfd  jmp     loc_140095F08
0x140095c02  mov     eax, [rsi]
0x140095c04  mov     edx, r14d
0x140095c07  mov     r8d, [rbp+40h+arg_28]
0x140095c0b  bts     edx, 1Fh
0x140095c0f  mov     [rbx], eax
0x140095c11  xorps   xmm0, xmm0
0x140095c14  mov     byte ptr [rbx+28h], 1
0x140095c18  xor     eax, eax
0x140095c1a  mov     [rbx+4], r8d
0x140095c1e  mov     ecx, [rsi]
0x140095c20  movups  [rsp+140h+var_E0], xmm0
0x140095c25  mov     dword ptr [rsp+140h+var_E0], ecx
0x140095c29  mov     [rsp+140h+var_F8], edx
0x140095c2d  mov     [rsp+140h+var_D0], rax
0x140095c32  sub     ecx, 1
0x140095c35  jz      short loc_140095C52
0x140095c37  cmp     ecx, 2
0x140095c3a  jnz     short loc_140095C5D
0x140095c3c  lea     rax, [rbx+70h]
0x140095c40  mov     [rax+8], rax
0x140095c44  mov     [rax], rax
0x140095c47  mov     rax, [rsi+8]
0x140095c4b  mov     qword ptr [rsp+140h+var_E0+8], rax
0x140095c50  jmp     short loc_140095C5D
0x140095c52  mov     eax, [rbp+40h+arg_20]
0x140095c55  mov     dword ptr [rsp+140h+var_E0+0Ch], eax
0x140095c59  mov     dword ptr [rsp+140h+var_E0+8], edi
0x140095c5d  mov     rcx, [r13+288h]
0x140095c64  lea     rax, [rsp+140h+var_E0]
0x140095c69  mov     byte ptr [rsp+140h+var_110], r12b
0x140095c6e  or      r9, 0FFFFFFFFFFFFFFFFh
0x140095c72  mov     byte ptr [rsp+140h+var_118], r15b
0x140095c77  mov     [rsp+140h+var_120], rax
0x140095c7c  call    cs:__imp_WinHvCreatePort
0x140095c83  nop     dword ptr [rax+rax+00h]
0x140095c88  mov     edi, eax
0x140095c8a  test    eax, eax
0x140095c8c  jns     short loc_140095CAC
0x140095c8e  mov     r8d, 2ABh
0x140095c94  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140095c9b  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x140095ca2  call    VidTraceErrorInternal0
0x140095ca7  jmp     loc_140095F08
0x140095cac  mov     r14, qword ptr [rbp+40h+var_C0]
0x140095cb0  shr     r14, 2Ch
0x140095cb4  and     r14b, 1
0x140095cb8  cmp     dword ptr [rsi], 3
0x140095cbb  jnz     loc_140095D6F
0x140095cc1  test    r14b, r14b
0x140095cc4  jz      short loc_140095D12
0x140095cc6  mov     edx, [rbx+4]
0x140095cc9  lea     r9, [rsp+140h+var_E8]
0x140095cce  mov     rcx, [r13+288h]
0x140095cd5  mov     r8d, 2
0x140095cdb  call    cs:__imp_WinHvGetPortProperty
0x140095ce2  nop     dword ptr [rax+rax+00h]
0x140095ce7  mov     edi, eax
0x140095ce9  test    eax, eax
0x140095ceb  jns     short loc_140095D0B
0x140095ced  mov     r8d, 2BFh
0x140095cf3  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140095cfa  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x140095d01  call    VidTraceErrorInternal0
0x140095d06  jmp     loc_140095F08
0x140095d0b  mov     rax, [rsp+140h+var_E8]
0x140095d10  jmp     short loc_140095D6B
0x140095d12  mov     edx, 1000h
0x140095d17  mov     ecx, 41h ; 'A'
0x140095d1c  mov     r8d, 72446456h
0x140095d22  call    cs:__imp_ExAllocatePool2
0x140095d29  nop     dword ptr [rax+rax+00h]
0x140095d2e  mov     [rbx+68h], rax
0x140095d32  test    rax, rax
0x140095d35  jnz     short loc_140095D55
0x140095d37  mov     r8d, 2D5h
0x140095d3d  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140095d44  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x140095d4b  call    VidTraceErrorInternal0
0x140095d50  jmp     loc_140095BF8
0x140095d55  mov     rcx, rax; BaseAddress
0x140095d58  mov     byte ptr [rbx+80h], 1
0x140095d5f  call    cs:__imp_MmGetPhysicalAddress
0x140095d66  nop     dword ptr [rax+rax+00h]
0x140095d6b  mov     [rsi+8], rax
0x140095d6f  lea     rcx, [r13+0D00h]
0x140095d76  mov     [rsp+140h+var_100], 1
0x140095d7b  xor     r15b, r15b
0x140095d7e  mov     [rsp+140h+var_FF], 1
0x140095d83  call    VidLockAcquireExclusive
0x140095d88  lea     r12, [r13+0CE0h]
0x140095d8f  mov     rdx, rbx
0x140095d92  mov     rcx, r12
0x140095d95  lea     r8, [rsp+140h+var_F0]
0x140095d9a  call    VidHandleTableAllocateEntry
0x140095d9f  mov     edi, eax
0x140095da1  test    eax, eax
0x140095da3  js      loc_140095ED8
0x140095da9  lea     rdx, [rsp+140h+var_FC]
0x140095dae  mov     rcx, rbx
0x140095db1  call    cs:__imp_WinHvAllocatePortId
0x140095db8  nop     dword ptr [rax+rax+00h]
0x140095dbd  mov     edi, eax
0x140095dbf  test    eax, eax
0x140095dc1  jns     short loc_140095DE1
0x140095dc3  mov     r8d, 2F0h
0x140095dc9  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140095dd0  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x140095dd7  call    VidTraceErrorInternal0
0x140095ddc  jmp     loc_140095ED8
0x140095de1  mov     eax, [rsp+140h+var_FC]
0x140095de5  lea     rcx, [rbp+40h+var_C0]
0x140095de9  xorps   xmm0, xmm0
0x140095dec  mov     [rbx+8], eax
0x140095def  movups  [rbp+40h+var_C0], xmm0
0x140095df3  call    HviGetHypervisorFeatures
0x140095df8  mov     rax, 100000000h
0x140095e02  test    qword ptr [rbp+40h+var_C0], rax
0x140095e06  jz      short loc_140095E1C
0x140095e08  test    r14b, r14b
0x140095e0b  jnz     short loc_140095E1C
0x140095e0d  mov     eax, [rbx+8]
0x140095e10  and     eax, 3FFFFFFFh
0x140095e15  bts     eax, 1Eh
0x140095e19  mov     [rbx+8], eax
0x140095e1c  mov     eax, [rbx+4]
0x140095e1f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140095e23  mov     r9, [r13+288h]
0x140095e2a  mov     r8d, [rbx+8]
0x140095e2e  mov     edx, [rsp+140h+var_F8]
0x140095e32  mov     byte ptr [rsp+140h+var_110], r15b
0x140095e37  mov     [rsp+140h+var_118], rsi
0x140095e3c  mov     dword ptr [rsp+140h+var_120], eax
0x140095e40  call    cs:__imp_WinHvConnectPort
0x140095e47  nop     dword ptr [rax+rax+00h]
0x140095e4c  mov     edi, eax
0x140095e4e  test    eax, eax
0x140095e50  jns     short loc_140095E6D
0x140095e52  mov     r8d, 309h
0x140095e58  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140095e5f  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x140095e66  call    VidTraceErrorInternal0
0x140095e6b  jmp     short loc_140095ED8
0x140095e6d  cmp     dword ptr [rsi], 3
0x140095e70  jnz     short loc_140095EB0
0x140095e72  test    r14b, r14b
0x140095e75  jz      short loc_140095EA8
0x140095e77  mov     rdx, [rsp+140h+var_E8]
0x140095e7c  mov     rcx, rbx
0x140095e7f  call    VidSynicPortpMapMonitorPage
0x140095e84  mov     edi, eax
0x140095e86  test    eax, eax
0x140095e88  jns     short loc_140095EA8
0x140095e8a  mov     r15b, 1
0x140095e8d  mov     r8d, 318h
0x140095e93  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140095e9a  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x140095ea1  call    VidTraceErrorInternal0
0x140095ea6  jmp     short loc_140095ED8
0x140095ea8  mov     rcx, rbx
0x140095eab  call    VidSynicPortpInitializeMonitorPage
0x140095eb0  mov     rax, [rsp+140h+var_F0]
0x140095eb5  xor     ebx, ebx
0x140095eb7  mov     rcx, [rsp+140h+var_C8]
0x140095ebc  or      [rsp+140h+var_FC], 0FFFFFFh
0x140095ec4  mov     [rsp+140h+var_F0], 0FFFFFFFFFFFFFFFFh
0x140095ecd  mov     [rcx], rax
0x140095ed0  xor     al, al
0x140095ed2  mov     [rsp+140h+var_100], al
0x140095ed6  xor     edi, edi
0x140095ed8  mov     rdx, [rsp+140h+var_F0]
0x140095edd  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140095ee1  jz      short loc_140095EEB
0x140095ee3  mov     rcx, r12
0x140095ee6  call    VidHandleTableFreeEntry
0x140095eeb  test    r15b, r15b
0x140095eee  jz      short loc_140095F03
0x140095ef0  mov     edx, [rbx+8]
0x140095ef3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140095ef7  call    cs:__imp_WinHvDisconnectPort
0x140095efe  nop     dword ptr [rax+rax+00h]
0x140095f03  mov     r12b, [rsp+140h+var_100]
0x140095f08  mov     ecx, [rsp+140h+var_FC]
0x140095f0c  mov     eax, ecx
0x140095f0e  and     eax, 0FFFFFFh
0x140095f13  cmp     eax, 0FFFFFFh
0x140095f18  jz      short loc_140095F26
0x140095f1a  call    cs:__imp_WinHvFreePortId
0x140095f21  nop     dword ptr [rax+rax+00h]
0x140095f26  cmp     [rsp+140h+var_FF], 0
0x140095f2b  jz      short loc_140095F39
0x140095f2d  lea     rcx, [r13+0D00h]
0x140095f34  call    VidLockRelease
0x140095f39  test    r12b, r12b
0x140095f3c  jz      short loc_140095F54
0x140095f3e  mov     edx, [rbx+4]
0x140095f41  mov     rcx, [r13+288h]
0x140095f48  call    cs:__imp_WinHvDeletePort
0x140095f4f  nop     dword ptr [rax+rax+00h]
0x140095f54  test    rbx, rbx
0x140095f57  jz      short loc_140095F6E
0x140095f59  cmp     dword ptr [rbx], 3
0x140095f5c  jnz     short loc_140095F66
0x140095f5e  mov     rcx, rbx
0x140095f61  call    VidSynicPortpUnmapMonitorPage
0x140095f66  mov     rdx, rbx
0x140095f69  call    VidSynicPortpEntryFree
0x140095f6e  test    edi, edi
0x140095f70  jns     short loc_140095F9A
0x140095f72  lea     rax, [r13+290h]
0x140095f79  mov     r9d, edi
0x140095f7c  mov     r8d, 350h
0x140095f82  mov     [rsp+140h+var_120], rax
0x140095f87  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140095f8e  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
  ... truncated ...
```
