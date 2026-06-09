# VidSynicPortCreateEntry

- ea: `0x1400954ac`
- end: `0x140095a75`
- name: `VidSynicPortCreateEntry`
- size: `1481`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8, char, unsigned int, unsigned int *, HANDLE Handle, __int64)`
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
- `0x1400954ac`
- `0x14009712c`
- `0x1400972c8`
- `0x140097304`
- `0x1400973a4`
- `0x1400ef710`
- `0x1400f0270`

## import_xrefs

- `ntoskrnl!ExEventObjectType` at `0x140095674`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14009569f`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14009569f`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400957a1`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400957a1`
- `ntoskrnl!ExAllocatePool2` at `0x14009560e`
- `ntoskrnl!ExAllocatePool2` at `0x14009575f`
- `ntoskrnl!ExAllocatePool2` at `0x14009560e`
- `ntoskrnl!ExAllocatePool2` at `0x14009575f`
- `winhvr!WinHvSetPortProperty` at `0x14009591c`
- `winhvr!WinHvSetPortProperty` at `0x14009591c`
- `winhvr!WinHvGetPortProperty` at `0x140095859`
- `winhvr!WinHvGetPortProperty` at `0x140095859`
- `winhvr!WinHvConnectPort` at `0x14009597b`
- `winhvr!WinHvConnectPort` at `0x14009597b`
- `winhvr!WinHvDeletePort` at `0x1400959d8`
- `winhvr!WinHvDeletePort` at `0x1400959d8`
- `winhvr!WinHvCreatePort` at `0x140095809`
- `winhvr!WinHvCreatePort` at `0x140095809`
- `winhvr!WinHvAllocatePortId` at `0x1400956dc`
- `winhvr!WinHvAllocatePortId` at `0x1400956dc`

## string_xrefs

- `0x140095578`: `VidSynicPortCreateEntry`
- `0x14009562f`: `VidSynicPortCreateEntry`
- `0x1400956bc`: `VidSynicPortCreateEntry`
- `0x1400956fb`: `VidSynicPortCreateEntry`
- `0x140095781`: `VidSynicPortCreateEntry`
- `0x140095828`: `VidSynicPortCreateEntry`
- `0x140095878`: `VidSynicPortCreateEntry`
- `0x1400958a9`: `VidSynicPortCreateEntry`
- `0x14009593b`: `VidSynicPortCreateEntry`
- `0x14009599e`: `VidSynicPortCreateEntry`
- `0x140095a14`: `VidSynicPortCreateEntry`

## pseudocode

```c
__int64 __fastcall VidSynicPortCreateEntry(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3,
        char a4,
        int a5,
        unsigned int *a6,
        HANDLE Handle,
        __int64 a8)
{
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  int PortId; // edi
  __int64 Pool2; // rsi
  char v14; // r15
  __int64 v15; // rcx
  unsigned int *v16; // r12
  unsigned int v17; // ecx
  bool v18; // bl
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  void *v22; // rax
  __int64 v23; // r8
  __int64 v24; // r13
  __int64 v25; // rbx
  unsigned int v26; // ebx
  __int64 v27; // rdx
  _QWORD *v29; // rcx
  __int64 v30; // rax
  int Object; // [rsp+28h] [rbp-D8h]
  int HandleInformation; // [rsp+30h] [rbp-D0h]
  int HandleInformationa; // [rsp+30h] [rbp-D0h]
  unsigned int v36; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h]
  __int128 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h]
  unsigned __int64 v41; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+78h] [rbp-88h]
  __int128 v43; // [rsp+80h] [rbp-80h] BYREF
  char v44[32]; // [rsp+90h] [rbp-70h] BYREF
  char v45[16]; // [rsp+B0h] [rbp-50h] BYREF
  char v46[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v47; // [rsp+D0h] [rbp-30h]
  __int64 v48; // [rsp+D8h] [rbp-28h]
  unsigned int *v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+E8h] [rbp-18h]

  v38 = a1;
  v42 = a8;
  v43 = 0;
  HviGetHypervisorFeatures(&v43);
  v9 = *a6;
  v41 = 0;
  v40 = 0;
  v37 = -1;
  v39 = 0;
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 - 1 >= 2 )
      {
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v45, "VidSynicPortCreateEntry");
          tlgCreate1Sz_char(v46, "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c");
          LODWORD(v37) = 282;
          v47 = &v37;
          v36 = *a6;
          v48 = 4;
          v49 = &v36;
          v50 = 4;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, qword_140049020, 0, 0, 6, v44);
        }
        PortId = -1073741637;
        goto LABEL_58;
      }
    }
  }
  Pool2 = ExAllocatePool2(65, 136, 1917084758);
  if ( !Pool2 )
  {
    VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 297);
    PortId = -1073741801;
LABEL_58:
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VidSynicPortCreateEntry",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidsynicport.c",
      544,
      PortId,
      v38 + 656);
    return (unsigned int)PortId;
  }
  *(_DWORD *)Pool2 = *a6;
  if ( *a6 == 2 )
  {
    *(_QWORD *)(Pool2 + 64) = -1;
  }
  else if ( *a6 == 3 )
  {
    *(_QWORD *)(Pool2 + 120) = Pool2 + 112;
    *(_QWORD *)(Pool2 + 112) = Pool2 + 112;
  }
  v14 = 1;
  if ( *a6 == 3
    || ObReferenceObjectByHandleWithTag(
         Handle,
         2u,
         (POBJECT_TYPE)ExEventObjectType,
         1,
         0x72446456u,
         (PVOID *)(Pool2 + 16),
         0) >= 0 )
  {
    v16 = (unsigned int *)(Pool2 + 4);
    PortId = WinHvAllocatePortId(Pool2, Pool2 + 4);
    if ( PortId < 0 )
    {
      VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 344);
      goto LABEL_54;
    }
    v17 = *a6;
    v18 = (v43 & 0x100000000000LL) != 0;
    v40 = 0;
    v39 = 0;
    LODWORD(v39) = v17;
    v19 = v17 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( !v21 )
        {
          if ( (v43 & 0x100000000000LL) == 0 )
          {
            v22 = (void *)ExAllocatePool2(65, 4096, 1917084758);
            *(_QWORD *)(Pool2 + 104) = v22;
            if ( !v22 )
            {
              VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 391);
              PortId = -1073741801;
              goto LABEL_54;
            }
            *(_BYTE *)(Pool2 + 128) = 1;
            *((PHYSICAL_ADDRESS *)&v39 + 1) = MmGetPhysicalAddress(v22);
          }
LABEL_30:
          v23 = *v16;
          LOBYTE(HandleInformation) = a4;
          LOBYTE(Object) = 0;
          v36 = a3 | 0x80000000;
          PortId = WinHvCreatePort(-1, v36, v23, *(_QWORD *)(v38 + 648), &v39, Object, HandleInformation);
          if ( PortId < 0 )
          {
            VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 415);
            goto LABEL_54;
          }
          if ( *a6 == 3 )
          {
            if ( v18 )
            {
              PortId = WinHvGetPortProperty(-1, *v16, 2, &v41);
              if ( PortId < 0 )
              {
                VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 436);
                goto LABEL_52;
              }
              PortId = VidSynicPortpMapMonitorPage(Pool2, v41);
              if ( PortId < 0 )
              {
                VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 443);
                goto LABEL_52;
              }
            }
            VidSynicPortpInitializeMonitorPage(Pool2);
          }
          else if ( *a6 != 4 )
          {
            PortId = WinHvSetPortProperty(-1, *v16, 3, 1);
            if ( PortId < 0 )
            {
              VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 465);
              goto LABEL_52;
            }
          }
          v24 = v38 + 3328;
          VidLockAcquireExclusive(v38 + 3328);
          v25 = v38 + 3296;
          *(_QWORD *)&v43 = v38 + 3296;
          PortId = VidHandleTableAllocateEntry(v38 + 3296, Pool2, &v37);
          if ( PortId >= 0 )
          {
            if ( *a6 == 4 )
              v26 = *v16;
            else
              v26 = a5;
            LOBYTE(HandleInformationa) = a4;
            PortId = WinHvConnectPort(*(_QWORD *)(v38 + 648), v36, v26, -1, *v16, a6, HandleInformationa);
            if ( PortId >= 0 )
            {
              v29 = (_QWORD *)v42;
              v27 = -1;
              v30 = v37;
              v14 = 0;
              *(_DWORD *)(Pool2 + 8) = v26;
              Pool2 = 0;
              v25 = v43;
              PortId = 0;
              *v29 = v30;
LABEL_49:
              if ( v27 != -1 )
                VidHandleTableFreeEntry(v25, v27);
              VidLockRelease(v24);
              if ( !v14 )
              {
LABEL_53:
                if ( !Pool2 )
                  goto LABEL_57;
                goto LABEL_54;
              }
LABEL_52:
              WinHvDeletePort(-1, *(unsigned int *)(Pool2 + 4));
              goto LABEL_53;
            }
            VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 505);
            v25 = v43;
          }
          v27 = v37;
          goto LABEL_49;
        }
        if ( v21 != 1 )
          goto LABEL_30;
      }
      else
      {
        LODWORD(v40) = 0x10000;
      }
    }
    DWORD2(v39) = *(_DWORD *)(a2 + 16);
    HIDWORD(v39) = -1;
    goto LABEL_30;
  }
  VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 332);
  PortId = -1073741811;
LABEL_54:
  if ( *(_DWORD *)Pool2 == 3 )
    VidSynicPortpUnmapMonitorPage(Pool2);
  VidSynicPortpEntryFree(v15, Pool2);
LABEL_57:
  if ( PortId < 0 )
    goto LABEL_58;
  return (unsigned int)PortId;
}

```

## disassembly

```asm
0x1400954ac  push    rbp
0x1400954ae  push    rbx
0x1400954af  push    rsi
0x1400954b0  push    rdi
0x1400954b1  push    r12
0x1400954b3  push    r13
0x1400954b5  push    r14
0x1400954b7  push    r15
0x1400954b9  lea     rbp, [rsp-8]
0x1400954be  sub     rsp, 108h
0x1400954c5  mov     rax, cs:__security_cookie
0x1400954cc  xor     rax, rsp
0x1400954cf  mov     [rbp+40h+var_50], rax
0x1400954d3  mov     rax, [rbp+40h+arg_38]
0x1400954da  xorps   xmm0, xmm0
0x1400954dd  mov     r14, [rbp+40h+arg_28]
0x1400954e1  mov     r13, rdx
0x1400954e4  mov     rbx, [rbp+40h+Handle]
0x1400954eb  mov     [rsp+140h+var_F0], rcx
0x1400954f0  lea     rcx, [rbp+40h+var_C0]
0x1400954f4  mov     [rsp+140h+var_C8], rax
0x1400954f9  movups  [rbp+40h+var_C0], xmm0
0x1400954fd  mov     [rsp+140h+var_100], r9b
0x140095502  mov     [rsp+140h+var_FF], r8b
0x140095507  call    HviGetHypervisorFeatures
0x14009550c  mov     ecx, [r14]
0x14009550f  xor     eax, eax
0x140095511  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140095515  mov     [rsp+140h+var_D0], 0
0x14009551e  mov     [rsp+140h+var_D8], rax
0x140095523  xorps   xmm1, xmm1
0x140095526  mov     [rsp+140h+var_F8], rdi
0x14009552b  movups  [rsp+140h+var_E8], xmm1
0x140095530  sub     ecx, 1
0x140095533  jz      loc_1400955FD
0x140095539  sub     ecx, 1
0x14009553c  jz      loc_1400955FD
0x140095542  sub     ecx, 1
0x140095545  jz      loc_1400955FD
0x14009554b  cmp     ecx, 1
0x14009554e  jz      loc_1400955FD
0x140095554  mov     eax, cs:dword_140064110
0x14009555a  cmp     eax, 2
0x14009555d  jbe     loc_1400955F3
0x140095563  mov     edx, 100h
0x140095568  lea     rcx, dword_140064110
0x14009556f  call    _tlgKeywordOn
0x140095574  test    al, al
0x140095576  jz      short loc_1400955F3
0x140095578  lea     rdx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x14009557f  lea     rcx, [rbp+40h+var_90]
0x140095583  call    _tlgCreate1Sz_char
0x140095588  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x14009558f  lea     rcx, [rbp+40h+var_80]
0x140095593  call    _tlgCreate1Sz_char
0x140095598  lea     rax, [rsp+140h+var_F8]
0x14009559d  mov     dword ptr [rsp+140h+var_F8], 11Ah
0x1400955a5  mov     [rbp+40h+var_70], rax
0x1400955a9  lea     rdx, qword_140049020
0x1400955b0  mov     eax, [r14]
0x1400955b3  lea     rcx, dword_140064110
0x1400955ba  mov     [rsp+140h+var_FC], eax
0x1400955be  xor     r9d, r9d
0x1400955c1  lea     rax, [rsp+140h+var_FC]
0x1400955c6  mov     [rbp+40h+var_68], 4
0x1400955ce  mov     [rbp+40h+var_60], rax
0x1400955d2  xor     r8d, r8d
0x1400955d5  lea     rax, [rbp+40h+var_B0]
0x1400955d9  mov     [rbp+40h+var_58], 4
0x1400955e1  mov     [rsp+140h+Object], rax
0x1400955e6  mov     [rsp+140h+Tag], 6
0x1400955ee  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400955f3  mov     edi, 0C00000BBh
0x1400955f8  jmp     loc_140095A02
0x1400955fd  mov     edx, 88h
0x140095602  mov     r12d, 72446456h
0x140095608  mov     r8d, r12d
0x14009560b  lea     ecx, [rdx-47h]
0x14009560e  call    cs:__imp_ExAllocatePool2
0x140095615  nop     dword ptr [rax+rax+00h]
0x14009561a  mov     rsi, rax
0x14009561d  test    rax, rax
0x140095620  jnz     short loc_140095645
0x140095622  mov     r8d, 129h
0x140095628  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x14009562f  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x140095636  call    VidTraceErrorInternal0
0x14009563b  mov     edi, 0C0000017h
0x140095640  jmp     loc_140095A02
0x140095645  mov     eax, [r14]
0x140095648  mov     [rsi], eax
0x14009564a  mov     ecx, [r14]
0x14009564d  sub     ecx, 2
0x140095650  jz      short loc_140095664
0x140095652  cmp     ecx, 1
0x140095655  jnz     short loc_140095668
0x140095657  lea     rax, [rsi+70h]
0x14009565b  mov     [rax+8], rax
0x14009565f  mov     [rax], rax
0x140095662  jmp     short loc_140095668
0x140095664  mov     [rsi+40h], rdi
0x140095668  cmp     dword ptr [r14], 3
0x14009566c  mov     r15d, 1
0x140095672  jz      short loc_1400956D2
0x140095674  mov     r8, cs:ExEventObjectType
0x14009567b  lea     rax, [rsi+10h]
0x14009567f  mov     qword ptr [rsp+140h+HandleInformation], 0; HandleInformation
0x140095688  lea     edx, [r15+1]; DesiredAccess
0x14009568c  mov     [rsp+140h+Object], rax; Object
0x140095691  mov     r9b, r15b; AccessMode
0x140095694  mov     rcx, rbx; Handle
0x140095697  mov     [rsp+140h+Tag], r12d; Tag
0x14009569c  mov     r8, [r8]; ObjectType
0x14009569f  call    cs:__imp_ObReferenceObjectByHandleWithTag
0x1400956a6  nop     dword ptr [rax+rax+00h]
0x1400956ab  test    eax, eax
0x1400956ad  jns     short loc_1400956D2
0x1400956af  mov     r8d, 14Ch
0x1400956b5  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x1400956bc  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x1400956c3  call    VidTraceErrorInternal0
0x1400956c8  mov     edi, 0C000000Dh
0x1400956cd  jmp     loc_1400959E9
0x1400956d2  lea     r12, [rsi+4]
0x1400956d6  mov     rcx, rsi
0x1400956d9  mov     rdx, r12
0x1400956dc  call    cs:__imp_WinHvAllocatePortId
0x1400956e3  nop     dword ptr [rax+rax+00h]
0x1400956e8  mov     edi, eax
0x1400956ea  test    eax, eax
0x1400956ec  jns     short loc_14009570C
0x1400956ee  mov     r8d, 158h
0x1400956f4  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x1400956fb  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x140095702  call    VidTraceErrorInternal0
0x140095707  jmp     loc_1400959E9
0x14009570c  mov     ecx, [r14]
0x14009570f  xor     eax, eax
0x140095711  mov     rbx, qword ptr [rbp+40h+var_C0]
0x140095715  xorps   xmm0, xmm0
0x140095718  shr     rbx, 2Ch
0x14009571c  and     bl, r15b
0x14009571f  mov     [rsp+140h+var_D8], rax
0x140095724  movups  [rsp+140h+var_E8], xmm0
0x140095729  mov     dword ptr [rsp+140h+var_E8], ecx
0x14009572d  sub     ecx, r15d
0x140095730  jz      loc_1400957BC
0x140095736  sub     ecx, r15d
0x140095739  jz      short loc_1400957B4
0x14009573b  sub     ecx, r15d
0x14009573e  jz      short loc_14009574B
0x140095740  cmp     ecx, r15d
0x140095743  jnz     loc_1400957CC
0x140095749  jmp     short loc_1400957BC
0x14009574b  test    bl, bl
0x14009574d  jnz     short loc_1400957CC
0x14009574f  mov     edx, 1000h
0x140095754  mov     ecx, 41h ; 'A'
0x140095759  mov     r8d, 72446456h
0x14009575f  call    cs:__imp_ExAllocatePool2
0x140095766  nop     dword ptr [rax+rax+00h]
0x14009576b  mov     [rsi+68h], rax
0x14009576f  test    rax, rax
0x140095772  jnz     short loc_140095797
0x140095774  mov     r8d, 187h
0x14009577a  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140095781  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x140095788  call    VidTraceErrorInternal0
0x14009578d  mov     edi, 0C0000017h
0x140095792  jmp     loc_1400959E9
0x140095797  mov     rcx, rax; BaseAddress
0x14009579a  mov     [rsi+80h], r15b
0x1400957a1  call    cs:__imp_MmGetPhysicalAddress
0x1400957a8  nop     dword ptr [rax+rax+00h]
0x1400957ad  mov     qword ptr [rsp+140h+var_E8+8], rax
0x1400957b2  jmp     short loc_1400957CC
0x1400957b4  mov     dword ptr [rsp+140h+var_D8], 10000h
0x1400957bc  mov     eax, [r13+10h]
0x1400957c0  mov     dword ptr [rsp+140h+var_E8+8], eax
0x1400957c4  mov     dword ptr [rsp+140h+var_E8+0Ch], 0FFFFFFFFh
0x1400957cc  mov     cl, [rsp+140h+var_100]
0x1400957d0  or      r13, 0FFFFFFFFFFFFFFFFh
0x1400957d4  movzx   eax, [rsp+140h+var_FF]
0x1400957d9  mov     r8d, [r12]
0x1400957dd  bts     eax, 1Fh
0x1400957e1  mov     byte ptr [rsp+140h+HandleInformation], cl
0x1400957e5  mov     edx, eax
0x1400957e7  lea     rcx, [rsp+140h+var_E8]
0x1400957ec  mov     byte ptr [rsp+140h+Object], 0
0x1400957f1  mov     qword ptr [rsp+140h+Tag], rcx
0x1400957f6  mov     rcx, [rsp+140h+var_F0]
0x1400957fb  mov     [rsp+140h+var_FC], eax
0x1400957ff  mov     r9, [rcx+288h]
0x140095806  mov     rcx, r13
0x140095809  call    cs:__imp_WinHvCreatePort
0x140095810  nop     dword ptr [rax+rax+00h]
0x140095815  mov     edi, eax
0x140095817  test    eax, eax
0x140095819  jns     short loc_140095839
0x14009581b  mov     r8d, 19Fh
0x140095821  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140095828  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x14009582f  call    VidTraceErrorInternal0
0x140095834  jmp     loc_1400959E9
0x140095839  mov     eax, [r14]
0x14009583c  cmp     eax, 3
0x14009583f  jnz     loc_140095907
0x140095845  test    bl, bl
0x140095847  jz      short loc_1400958BA
0x140095849  mov     edx, [r12]
0x14009584d  lea     r9, [rsp+140h+var_D0]
0x140095852  lea     r8d, [rax-1]
0x140095856  mov     rcx, r13
0x140095859  call    cs:__imp_WinHvGetPortProperty
0x140095860  nop     dword ptr [rax+rax+00h]
0x140095865  mov     edi, eax
0x140095867  test    eax, eax
0x140095869  jns     short loc_140095889
0x14009586b  mov     r8d, 1B4h
0x140095871  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140095878  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x14009587f  call    VidTraceErrorInternal0
0x140095884  jmp     loc_1400959D2
0x140095889  mov     rdx, [rsp+140h+var_D0]
0x14009588e  mov     rcx, rsi
0x140095891  call    VidSynicPortpMapMonitorPage
0x140095896  mov     edi, eax
0x140095898  test    eax, eax
0x14009589a  jns     short loc_1400958BA
0x14009589c  mov     r8d, 1BBh
0x1400958a2  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x1400958a9  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x1400958b0  call    VidTraceErrorInternal0
0x1400958b5  jmp     loc_1400959D2
0x1400958ba  mov     rcx, rsi
0x1400958bd  call    VidSynicPortpInitializeMonitorPage
0x1400958c2  mov     rbx, [rsp+140h+var_F0]
0x1400958c7  lea     r13, [rbx+0D00h]
0x1400958ce  mov     rcx, r13
0x1400958d1  call    VidLockAcquireExclusive
0x1400958d6  add     rbx, 0CE0h
0x1400958dd  lea     r8, [rsp+140h+var_F8]
0x1400958e2  mov     rcx, rbx
0x1400958e5  mov     qword ptr [rbp+40h+var_C0], rbx
0x1400958e9  mov     rdx, rsi
0x1400958ec  call    VidHandleTableAllocateEntry
0x1400958f1  mov     edi, eax
0x1400958f3  test    eax, eax
0x1400958f5  js      loc_1400959AE
0x1400958fb  cmp     dword ptr [r14], 4
0x1400958ff  jnz     short loc_14009594C
0x140095901  mov     ebx, [r12]
0x140095905  jmp     short loc_14009594F
0x140095907  cmp     eax, 4
0x14009590a  jz      short loc_1400958C2
0x14009590c  mov     edx, [r12]
0x140095910  mov     r9, r15
0x140095913  mov     r8d, 3
0x140095919  mov     rcx, r13
0x14009591c  call    cs:__imp_WinHvSetPortProperty
0x140095923  nop     dword ptr [rax+rax+00h]
0x140095928  mov     edi, eax
0x14009592a  test    eax, eax
0x14009592c  jns     short loc_1400958C2
0x14009592e  mov     r8d, 1D1h
0x140095934  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x14009593b  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x140095942  call    VidTraceErrorInternal0
0x140095947  jmp     loc_1400959D2
0x14009594c  mov     ebx, [rbp+40h+arg_20]
0x14009594f  mov     al, [rsp+140h+var_100]
0x140095953  or      r9, 0FFFFFFFFFFFFFFFFh
0x140095957  mov     rcx, [rsp+140h+var_F0]
0x14009595c  mov     r8d, ebx
0x14009595f  mov     edx, [rsp+140h+var_FC]
0x140095963  mov     byte ptr [rsp+140h+HandleInformation], al
0x140095967  mov     eax, [r12]
0x14009596b  mov     rcx, [rcx+288h]
0x140095972  mov     [rsp+140h+Object], r14
0x140095977  mov     [rsp+140h+Tag], eax
0x14009597b  call    cs:__imp_WinHvConnectPort
0x140095982  nop     dword ptr [rax+rax+00h]
0x140095987  mov     edi, eax
0x140095989  test    eax, eax
0x14009598b  jns     loc_140095A51
0x140095991  mov     r8d, 1F9h
0x140095997  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x14009599e  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x1400959a5  call    VidTraceErrorInternal0
0x1400959aa  mov     rbx, qword ptr [rbp+40h+var_C0]
0x1400959ae  mov     rdx, [rsp+140h+var_F8]
0x1400959b3  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1400959b7  jz      short loc_1400959C1
0x1400959b9  mov     rcx, rbx
0x1400959bc  call    VidHandleTableFreeEntry
0x1400959c1  mov     rcx, r13
0x1400959c4  call    VidLockRelease
0x1400959c9  test    r15b, r15b
0x1400959cc  jz      short loc_1400959E4
0x1400959ce  or      r13, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
