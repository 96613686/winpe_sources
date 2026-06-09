# SlbNatCreateStaticMapping

- ea: `0x1400319dc`
- end: `0x140032112`
- name: `SlbNatCreateStaticMapping`
- size: `1846`
- prototype: `__int64 __fastcall(wchar_t *Str2, __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x140030ad0`
- `0x140036580`

## callees

- `0x1400080a8`
- `0x14000c7a0`
- `0x14000caa0`
- `0x14000d648`
- `0x14000d7c8`
- `0x1400149bc`
- `0x14001526c`
- `0x14001b9ec`
- `0x14001bcbc`
- `0x14001f320`
- `0x140031114`
- `0x1400319dc`
- `0x140032118`
- `0x140032228`
- `0x140033b60`
- `0x140033c3c`
- `0x140033c8c`
- `0x140033fa8`
- `0x140035584`
- `0x140035808`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140031e72`
- `ntoskrnl!IoAllocateWorkItem` at `0x140031e72`
- `ntoskrnl!ExAllocatePool2` at `0x140031d76`
- `ntoskrnl!ExAllocatePool2` at `0x140031e3f`
- `ntoskrnl!ExAllocatePool2` at `0x140031d76`
- `ntoskrnl!ExAllocatePool2` at `0x140031e3f`
- `ntoskrnl!IoFreeIrp` at `0x1400320dc`
- `ntoskrnl!IoFreeIrp` at `0x1400320dc`
- `ntoskrnl!IoAllocateIrp` at `0x140031a5c`
- `ntoskrnl!IoAllocateIrp` at `0x140031a5c`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140031acd`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140032068`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140031acd`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140032068`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140031a48`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140031b2f`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140031a48`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140031b2f`
- `NETIO!CloseCompartment` at `0x140032055`
- `NETIO!CloseCompartment` at `0x140032055`

## string_xrefs

- `0x14003208e`: `Create static mapping`

## pseudocode

```c
__int64 __fastcall SlbNatCreateStaticMapping(wchar_t *Str2, __int64 a2)
{
  IRP *v4; // rbx
  int StaticBindingEntry; // edi
  __int64 Instance; // rax
  bool v7; // zf
  char v8; // bl
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r13
  unsigned __int16 v18; // ax
  __int64 v19; // rcx
  __int64 ExternalAddressByAddressAndPort; // rax
  _QWORD *v21; // r15
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  int v25; // eax
  unsigned __int8 v26; // al
  __int16 v27; // cx
  bool v28; // cc
  unsigned int v29; // r12d
  unsigned int v30; // eax
  __int64 Pool2; // rax
  int v32; // ecx
  int v33; // r9d
  __int64 v34; // r14
  __int64 AssociatedStaticMapping; // rax
  int v36; // edi
  __int64 v37; // rcx
  __int64 v38; // rdi
  void **v39; // rcx
  int v40; // ecx
  int v41; // r8d
  int v42; // eax
  _QWORD *v43; // rax
  void **v44; // rcx
  int v45; // edx
  int v46; // r8d
  char v48; // [rsp+70h] [rbp-90h]
  char v49; // [rsp+71h] [rbp-8Fh]
  char v50; // [rsp+72h] [rbp-8Eh]
  char v51[5]; // [rsp+73h] [rbp-8Dh] BYREF
  PIRP Irp; // [rsp+78h] [rbp-88h]
  int v53; // [rsp+80h] [rbp-80h]
  __int64 v54; // [rsp+88h] [rbp-78h]
  _QWORD *v55; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v56; // [rsp+98h] [rbp-68h]
  __int128 v57; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v58[2]; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v59[16]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v60[2]; // [rsp+F0h] [rbp-10h] BYREF

  v56 = Str2;
  v54 = 0;
  memset(v59, 0, 28);
  memset(v60, 0, 28);
  v50 = 0;
  v51[0] = 0;
  v58[0] = 0;
  v57 = 0;
  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  Irp = IoAllocateIrp(1, 0);
  v4 = Irp;
  if ( !Irp )
  {
    StaticBindingEntry = -1073741823;
    goto LABEL_91;
  }
  Instance = SlbNatFindInstance(Str2);
  if ( !Instance )
  {
    StaticBindingEntry = -1073741275;
    goto LABEL_91;
  }
  if ( *(_BYTE *)(Instance + 182) )
  {
    v7 = *(_DWORD *)(a2 + 80) == 0;
  }
  else
  {
    if ( !*(_DWORD *)(a2 + 80) )
      goto LABEL_11;
    v7 = *(_DWORD *)(a2 + 8) == 0;
  }
  if ( !v7 )
  {
    StaticBindingEntry = -1073741811;
    goto LABEL_91;
  }
LABEL_11:
  v8 = *(_BYTE *)(Instance + 230);
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  if ( v8 )
  {
    v11 = *(unsigned __int16 *)(a2 + 40);
    LOWORD(v11) = __ROR2__(v11, 8);
    LOBYTE(v10) = 1;
    LOBYTE(v9) = *(_BYTE *)a2 == 6;
    v12 = SlbNatAllocatePorts(v9, &v57, v11, v10);
    v53 = v12;
    v50 = 1;
    if ( !*(_WORD *)(a2 + 40) && v12 >= 0 )
    {
      v15 = (unsigned __int16)v57;
      *(_WORD *)(a2 + 40) = v57;
      if ( WORD1(v57) != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v15, v13, v14);
    }
  }
  else
  {
    v53 = -1073741823;
  }
  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  v16 = SlbNatFindInstance(Str2);
  v17 = v16;
  if ( v16 )
  {
    v18 = *(unsigned __int8 *)(v16 + 230);
    if ( (_BYTE)v18 && !(unsigned __int8)SlbNatIPPrefixMatch(v17 + 232, a2 + 24, v18) )
    {
      StaticBindingEntry = -1073741811;
      goto LABEL_90;
    }
    if ( SlbNatFindStaticMappingInInstance(v17, *((unsigned int *)Str2 + 20), 0) )
    {
      StaticBindingEntry = -1073741635;
      goto LABEL_90;
    }
    v19 = *(unsigned __int16 *)(a2 + 40);
    v49 = 0;
    if ( *(_DWORD *)(a2 + 8) )
      ExternalAddressByAddressAndPort = SlbNatFindExternalAddressByAddressAndPort(
                                          v17,
                                          a2 + 8,
                                          *(unsigned __int16 *)(a2 + 2),
                                          (unsigned __int16)v19,
                                          0);
    else
      ExternalAddressByAddressAndPort = SlbNatFindWildcardExternalAddressByPort(v19);
    v55 = (_QWORD *)ExternalAddressByAddressAndPort;
    v21 = (_QWORD *)ExternalAddressByAddressAndPort;
    if ( !ExternalAddressByAddressAndPort )
    {
      if ( *(_BYTE *)(v17 + 230) && *(_WORD *)(a2 + 2) == 2 && !*(_DWORD *)(a2 + 8) )
      {
        StaticBindingEntry = SlbNatCreateWildcardExternalAddress(v17, 2, *(unsigned __int16 *)(a2 + 40), &v55);
        if ( StaticBindingEntry < 0 )
          goto LABEL_90;
        v21 = v55;
        v49 = 1;
        if ( !v55 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v23, v22, v24);
      }
      if ( !v21 )
      {
        StaticBindingEntry = -1073741198;
        goto LABEL_86;
      }
    }
    if ( *(_BYTE *)a2 != 6 && *(_BYTE *)a2 != 17 )
    {
LABEL_38:
      StaticBindingEntry = -1073741811;
      goto LABEL_86;
    }
    v25 = *(_DWORD *)(a2 + 4);
    if ( v25 != 2 )
    {
      v48 = 0;
      if ( v25 != 1 )
      {
        StaticBindingEntry = -1073741637;
        goto LABEL_86;
      }
LABEL_47:
      v29 = *(_DWORD *)(v17 + 68);
      if ( !v29 )
      {
        v30 = SlbNatConvertRdIdtoCompartmentId((GUID *)(a2 + 44));
        v29 = v30;
        if ( !v30 )
        {
          StaticBindingEntry = -1073741264;
          goto LABEL_86;
        }
        if ( v30 == 1 )
        {
          StaticBindingEntry = -1073741637;
          goto LABEL_86;
        }
      }
      StaticBindingEntry = SlbNatVerifyStaticMapping(v21, a2, v29);
      if ( StaticBindingEntry < 0 )
        goto LABEL_86;
      INETADDR_SETSOCKADDR(
        *(unsigned __int16 *)(a2 + 2),
        (unsigned int)v60,
        a2 + 24,
        0,
        __ROR2__(*(_WORD *)(a2 + 42), 8));
      INETADDR_SETSOCKADDR(
        *(unsigned __int16 *)(a2 + 2),
        (unsigned int)v59,
        a2 + 8,
        0,
        __ROR2__(*(_WORD *)(a2 + 40), 8));
      StaticBindingEntry = WinNatLibCreateStaticBindingEntry(
                             (_DWORD)qword_1400273D8,
                             (unsigned int)v60,
                             (unsigned int)v59,
                             v29,
                             *(_BYTE *)a2,
                             v48,
                             (__int64)v58,
                             *(_DWORD *)(a2 + 80));
      if ( StaticBindingEntry < 0 )
        goto LABEL_86;
      Pool2 = ExAllocatePool2(256, 136, 1836273235);
      v34 = Pool2;
      if ( !Pool2 )
      {
        StaticBindingEntry = -1073741670;
LABEL_85:
        WinNatLibDeleteStaticBindingEntry(
          (_DWORD)qword_1400273D8,
          (unsigned int)v59,
          (unsigned int)v60,
          v29,
          *(_BYTE *)a2,
          *(_DWORD *)(a2 + 80));
        goto LABEL_86;
      }
      *(_DWORD *)(Pool2 + 32) = *((_DWORD *)v56 + 20);
      *(_DWORD *)(Pool2 + 16) = v29;
      *(_QWORD *)(Pool2 + 24) = v54;
      *(_QWORD *)(Pool2 + 128) = *(_QWORD *)(v17 + 288);
      if ( !*(_BYTE *)(v17 + 230) )
      {
LABEL_74:
        *(_OWORD *)(v34 + 36) = *(_OWORD *)a2;
        *(_OWORD *)(v34 + 52) = *(_OWORD *)(a2 + 16);
        *(_OWORD *)(v34 + 68) = *(_OWORD *)(a2 + 32);
        *(_OWORD *)(v34 + 84) = *(_OWORD *)(a2 + 48);
        *(_OWORD *)(v34 + 100) = *(_OWORD *)(a2 + 64);
        *(_DWORD *)(v34 + 116) = *(_DWORD *)(a2 + 80);
        v39 = (void **)v21[3];
        if ( *v39 != v21 + 2 )
          goto LABEL_99;
        *(_QWORD *)v34 = v21 + 2;
        *(_QWORD *)(v34 + 8) = v39;
        StaticBindingEntry = 0;
        *v39 = (void *)v34;
        v21[3] = v34;
        ++*((_DWORD *)v21 + 8);
        v54 = 0;
        v49 = 0;
        if ( (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
        {
          v40 = *(unsigned __int16 *)(v34 + 38);
          memset(v58, 0, 28);
          INETADDR_SETSOCKADDR(v40, (unsigned int)v58, v34 + 100, 0, 0);
          if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
          {
            v41 = 28;
            if ( v59[0] == 2 )
              v41 = 16;
            McTemplateK0zqqqbr3br3jqbr3q_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
              (unsigned int)WINNATM_STATIC_MAPPING_ADDITION,
              v41,
              v17 + 80,
              *(_BYTE *)(v34 + 36),
              *(_DWORD *)(v34 + 40),
              v41,
              (__int64)v59,
              (__int64)v60,
              v34 + 80,
              *(_DWORD *)(v34 + 16),
              (__int64)v58,
              *(_BYTE *)(v34 + 96));
          }
        }
        v42 = *((_DWORD *)v56 + 20);
        if ( *(_DWORD *)(v17 + 260) < (unsigned int)(v42 + 1) || v42 == -1 )
          *(_DWORD *)(v17 + 260) = v42 + 1;
LABEL_86:
        if ( !v49 )
          goto LABEL_90;
        v43 = (_QWORD *)*v21;
        if ( *(_QWORD **)(*v21 + 8LL) == v21 )
        {
          v44 = (void **)v21[1];
          if ( *v44 == v21 )
          {
            *v44 = v43;
            v43[1] = v44;
            SlbNatDeleteExternalAddress(v21);
            goto LABEL_90;
          }
        }
LABEL_99:
        __fastfail(3u);
      }
      AssociatedStaticMapping = 0;
      if ( !*(_DWORD *)(a2 + 8) )
      {
        v36 = *(_DWORD *)(a2 + 80);
        LOBYTE(v32) = *(_BYTE *)a2;
        LOBYTE(v33) = 1;
        AssociatedStaticMapping = SlbNatFindAssociatedStaticMapping(
                                    v32,
                                    *(unsigned __int16 *)(a2 + 40),
                                    v36,
                                    v33,
                                    (__int64)v51);
        if ( v51[0] )
        {
          StaticBindingEntry = -1073741635;
          goto LABEL_85;
        }
        if ( AssociatedStaticMapping )
        {
          if ( *(_DWORD *)(AssociatedStaticMapping + 116) )
          {
            if ( !v36 )
              goto LABEL_72;
          }
          else if ( v36 )
          {
            goto LABEL_72;
          }
        }
      }
      StaticBindingEntry = v53;
      if ( v53 >= 0 )
      {
LABEL_69:
        v38 = ExAllocatePool2(256, 40, 1634750035);
        if ( !v38 )
        {
          StaticBindingEntry = -1073741801;
          goto LABEL_85;
        }
        *(_QWORD *)v38 = IoAllocateWorkItem(deviceObject);
        *(_QWORD *)(v38 + 24) = Irp;
        v7 = *(_BYTE *)a2 == 6;
        Irp = 0;
        *(_BYTE *)(v38 + 32) = v7;
        *(_OWORD *)(v38 + 8) = v57;
        *(_QWORD *)(v34 + 120) = v38;
        goto LABEL_74;
      }
      v50 = 0;
      if ( !AssociatedStaticMapping )
        goto LABEL_85;
      v37 = *(_QWORD *)(AssociatedStaticMapping + 120);
      if ( v37 )
      {
        v57 = *(_OWORD *)(v37 + 8);
        goto LABEL_69;
      }
LABEL_72:
      StaticBindingEntry = -1073741811;
      goto LABEL_85;
    }
    v26 = *(_BYTE *)(a2 + 60);
    if ( !v26 )
      goto LABEL_38;
    v27 = *(_WORD *)(a2 + 2);
    if ( v27 == 2 )
    {
      v28 = v26 <= 0x20u;
    }
    else
    {
      if ( v27 != 23 )
      {
LABEL_46:
        LOBYTE(v58[0]) = *(_BYTE *)(a2 + 60);
        *((_QWORD *)&v58[0] + 1) = a2 + 64;
        v48 = 1;
        goto LABEL_47;
      }
      v28 = v26 <= 0x80u;
    }
    if ( !v28 )
      goto LABEL_38;
    goto LABEL_46;
  }
  StaticBindingEntry = -1073741275;
LABEL_90:
  v4 = Irp;
LABEL_91:
  if ( v54 )
    CloseCompartment();
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  if ( StaticBindingEntry >= 0 )
    goto LABEL_100;
  if ( dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
    McTemplateK0qzqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      v45,
      v46,
      3008,
      (__int64)L"Create static mapping",
      0,
      StaticBindingEntry);
  if ( v50 )
  {
    SlbNatFreePortReservationWithIrp(v4);
  }
  else
  {
LABEL_100:
    if ( v4 )
      IoFreeIrp(v4);
  }
  return (unsigned int)StaticBindingEntry;
}

```

## disassembly

```asm
0x1400319dc  mov     [rsp-8+arg_10], rbx
0x1400319e1  push    rbp
0x1400319e2  push    rsi
0x1400319e3  push    rdi
0x1400319e4  push    r12
0x1400319e6  push    r13
0x1400319e8  push    r14
0x1400319ea  push    r15
0x1400319ec  lea     rbp, [rsp-20h]
0x1400319f1  sub     rsp, 120h
0x1400319f8  mov     rax, cs:__security_cookie
0x1400319ff  xor     rax, rsp
0x140031a02  mov     [rbp+50h+var_40], rax
0x140031a06  xorps   xmm0, xmm0
0x140031a09  mov     [rbp+50h+var_B8], rcx
0x140031a0d  xorps   xmm1, xmm1
0x140031a10  xor     r12d, r12d
0x140031a13  mov     r14, rcx
0x140031a16  mov     [rbp+50h+var_C8], r12
0x140031a1a  movups  xmmword ptr [rbp+50h+var_80], xmm0
0x140031a1e  xor     eax, eax
0x140031a20  lea     rcx, Resource; Resource
0x140031a27  movups  [rbp+50h+var_60], xmm1
0x140031a2b  mov     rsi, rdx
0x140031a2e  mov     [rsp+150h+var_DE], r12b
0x140031a33  movups  xmmword ptr [rbp+50h+var_80+0Ch], xmm0
0x140031a37  mov     [rsp+150h+var_DD], r12b
0x140031a3c  movups  [rbp+50h+var_60+0Ch], xmm1
0x140031a40  movups  [rbp+50h+var_A0], xmm0
0x140031a44  movups  [rbp+50h+var_B0], xmm1
0x140031a48  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140031a4f  nop     dword ptr [rax+rax+00h]
0x140031a54  xor     edx, edx; ChargeQuota
0x140031a56  lea     edi, [rdx+1]
0x140031a59  mov     cl, dil; StackSize
0x140031a5c  call    cs:__imp_IoAllocateIrp
0x140031a63  nop     dword ptr [rax+rax+00h]
0x140031a68  mov     [rsp+150h+var_D8], rax
0x140031a6d  mov     rbx, rax
0x140031a70  lea     r15d, [r12+10h]
0x140031a75  test    rax, rax
0x140031a78  jnz     short loc_140031A84
0x140031a7a  mov     edi, 0C0000001h
0x140031a7f  jmp     loc_14003204C
0x140031a84  mov     rcx, r14; Str2
0x140031a87  call    SlbNatFindInstance
0x140031a8c  test    rax, rax
0x140031a8f  jnz     short loc_140031A9B
0x140031a91  mov     edi, 0C0000225h
0x140031a96  jmp     loc_14003204C
0x140031a9b  cmp     [rax+0B6h], r12b
0x140031aa2  jbe     short loc_140031AB4
0x140031aa4  cmp     [rsi+50h], r12d
0x140031aa8  jz      short loc_140031AC0
0x140031aaa  mov     edi, 0C000000Dh
0x140031aaf  jmp     loc_14003204C
0x140031ab4  cmp     [rsi+50h], r12d
0x140031ab8  jz      short loc_140031AC0
0x140031aba  cmp     [rsi+8], r12d
0x140031abe  jmp     short loc_140031AA8
0x140031ac0  mov     bl, [rax+0E6h]
0x140031ac6  lea     rcx, Resource; Resource
0x140031acd  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140031ad4  nop     dword ptr [rax+rax+00h]
0x140031ad9  test    bl, bl
0x140031adb  jz      short loc_140031B21
0x140031add  movzx   r8d, word ptr [rsi+28h]
0x140031ae2  lea     rdx, [rbp+50h+var_B0]
0x140031ae6  ror     r8w, 8
0x140031aeb  mov     r9b, dil
0x140031aee  cmp     byte ptr [rsi], 6
0x140031af1  setz    cl
0x140031af4  call    SlbNatAllocatePorts
0x140031af9  mov     [rbp+50h+var_D0], eax
0x140031afc  mov     [rsp+150h+var_DE], dil
0x140031b01  cmp     [rsi+28h], r12w
0x140031b06  jnz     short loc_140031B28
0x140031b08  test    eax, eax
0x140031b0a  js      short loc_140031B28
0x140031b0c  movzx   ecx, word ptr [rbp+50h+var_B0]
0x140031b10  mov     [rsi+28h], cx
0x140031b14  cmp     word ptr [rbp+50h+var_B0+2], di
0x140031b18  jz      short loc_140031B28
0x140031b1a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140031b1f  jmp     short loc_140031B28
0x140031b21  mov     [rbp+50h+var_D0], 0C0000001h
0x140031b28  lea     rcx, Resource; Resource
0x140031b2f  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140031b36  nop     dword ptr [rax+rax+00h]
0x140031b3b  mov     rcx, r14; Str2
0x140031b3e  call    SlbNatFindInstance
0x140031b43  mov     r13, rax
0x140031b46  test    rax, rax
0x140031b49  jnz     short loc_140031B55
0x140031b4b  mov     edi, 0C0000225h
0x140031b50  jmp     loc_140032047
0x140031b55  movzx   eax, byte ptr [rax+0E6h]
0x140031b5c  test    al, al
0x140031b5e  jz      short loc_140031B82
0x140031b60  movzx   r8d, ax
0x140031b64  lea     rdx, [rsi+18h]
0x140031b68  lea     rcx, [r13+0E8h]
0x140031b6f  call    SlbNatIPPrefixMatch
0x140031b74  test    al, al
0x140031b76  jnz     short loc_140031B82
0x140031b78  mov     edi, 0C000000Dh
0x140031b7d  jmp     loc_140032047
0x140031b82  mov     edx, [r14+50h]
0x140031b86  xor     r8d, r8d
0x140031b89  mov     rcx, r13
0x140031b8c  call    SlbNatFindStaticMappingInInstance
0x140031b91  test    rax, rax
0x140031b94  jz      short loc_140031BA0
0x140031b96  mov     edi, 0C00000BDh
0x140031b9b  jmp     loc_140032047
0x140031ba0  movzx   ecx, word ptr [rsi+28h]
0x140031ba4  lea     r14, [rsi+8]
0x140031ba8  mov     [rsp+150h+var_DF], r12b
0x140031bad  cmp     [r14], r12d
0x140031bb0  jnz     short loc_140031BB9
0x140031bb2  call    SlbNatFindWildcardExternalAddressByPort
0x140031bb7  jmp     short loc_140031BD2
0x140031bb9  movzx   r8d, word ptr [rsi+2]
0x140031bbe  movzx   r9d, cx
0x140031bc2  mov     rcx, r13
0x140031bc5  mov     byte ptr [rsp+150h+var_130], r12b
0x140031bca  mov     rdx, r14
0x140031bcd  call    SlbNatFindExternalAddressByAddressAndPort
0x140031bd2  mov     [rbp+50h+var_C0], rax
0x140031bd6  mov     r15, rax
0x140031bd9  mov     edx, 2
0x140031bde  test    rax, rax
0x140031be1  jnz     short loc_140031C3D
0x140031be3  cmp     [r13+0E6h], r12b
0x140031bea  jbe     short loc_140031C2E
0x140031bec  cmp     [rsi+2], dx
0x140031bf0  jnz     short loc_140031C2E
0x140031bf2  cmp     [r14], r12d
0x140031bf5  jnz     short loc_140031C2E
0x140031bf7  movzx   r8d, word ptr [rsi+28h]
0x140031bfc  lea     r9, [rbp+50h+var_C0]
0x140031c00  mov     rcx, r13
0x140031c03  call    SlbNatCreateWildcardExternalAddress
0x140031c08  mov     edi, eax
0x140031c0a  test    eax, eax
0x140031c0c  js      loc_140032041
0x140031c12  lea     edi, [r15+1]
0x140031c16  mov     r15, [rbp+50h+var_C0]
0x140031c1a  mov     [rsp+150h+var_DF], dil
0x140031c1f  test    r15, r15
0x140031c22  jnz     short loc_140031C29
0x140031c24  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140031c29  mov     edx, 2
0x140031c2e  test    r15, r15
0x140031c31  jnz     short loc_140031C3D
0x140031c33  mov     edi, 0C0000272h
0x140031c38  jmp     loc_14003200E
0x140031c3d  mov     al, [rsi]
0x140031c3f  cmp     al, 6
0x140031c41  jz      short loc_140031C51
0x140031c43  cmp     al, 11h
0x140031c45  jz      short loc_140031C51
0x140031c47  mov     edi, 0C000000Dh
0x140031c4c  jmp     loc_14003200E
0x140031c51  mov     eax, [rsi+4]
0x140031c54  cmp     eax, edx
0x140031c56  jnz     short loc_140031CAD
0x140031c58  mov     al, [rsi+3Ch]
0x140031c5b  test    al, al
0x140031c5d  jz      short loc_140031C47
0x140031c5f  movzx   ecx, word ptr [rsi+2]
0x140031c63  cmp     cx, dx
0x140031c66  jnz     short loc_140031C6C
0x140031c68  cmp     al, 20h ; ' '
0x140031c6a  jmp     short loc_140031C74
0x140031c6c  cmp     cx, 17h
0x140031c70  jnz     short loc_140031C76
0x140031c72  cmp     al, 80h
0x140031c74  ja      short loc_140031C47
0x140031c76  mov     byte ptr [rbp+50h+var_A0], al
0x140031c79  lea     rax, [rsi+40h]
0x140031c7d  mov     qword ptr [rbp+50h+var_A0+8], rax
0x140031c81  mov     [rsp+150h+var_E0], dil
0x140031c86  mov     r12d, [r13+44h]
0x140031c8a  test    r12d, r12d
0x140031c8d  jnz     short loc_140031CCE
0x140031c8f  lea     rcx, [rsi+2Ch]; CompartmentGuid
0x140031c93  lea     rdx, [rbp+50h+var_C8]
0x140031c97  call    SlbNatConvertRdIdtoCompartmentId
0x140031c9c  mov     r12d, eax
0x140031c9f  test    eax, eax
0x140031ca1  jnz     short loc_140031CC0
0x140031ca3  mov     edi, 0C0000230h
0x140031ca8  jmp     loc_14003200B
0x140031cad  mov     [rsp+150h+var_E0], r12b
0x140031cb2  cmp     eax, edi
0x140031cb4  jz      short loc_140031C86
0x140031cb6  mov     edi, 0C00000BBh
0x140031cbb  jmp     loc_14003200E
0x140031cc0  cmp     eax, edi
0x140031cc2  jnz     short loc_140031CCE
0x140031cc4  mov     edi, 0C00000BBh
0x140031cc9  jmp     loc_14003200B
0x140031cce  mov     r8d, r12d
0x140031cd1  mov     rdx, rsi
0x140031cd4  mov     rcx, r15
0x140031cd7  call    SlbNatVerifyStaticMapping
0x140031cdc  mov     edi, eax
0x140031cde  test    eax, eax
0x140031ce0  js      loc_14003200B
0x140031ce6  movzx   eax, word ptr [rsi+2Ah]
0x140031cea  lea     r8, [rsi+18h]
0x140031cee  movzx   ecx, word ptr [rsi+2]
0x140031cf2  lea     rdx, [rbp+50h+var_60]
0x140031cf6  ror     ax, 8
0x140031cfa  xor     ebx, ebx
0x140031cfc  mov     r9d, ebx
0x140031cff  mov     word ptr [rsp+150h+var_130], ax
0x140031d04  call    INETADDR_SETSOCKADDR
0x140031d09  movzx   eax, word ptr [rsi+28h]
0x140031d0d  lea     rdx, [rbp+50h+var_80]
0x140031d11  movzx   ecx, word ptr [rsi+2]
0x140031d15  mov     r9d, ebx
0x140031d18  ror     ax, 8
0x140031d1c  mov     r8, r14
0x140031d1f  mov     word ptr [rsp+150h+var_130], ax
0x140031d24  call    INETADDR_SETSOCKADDR
0x140031d29  mov     eax, [rsi+50h]
0x140031d2c  lea     r8, [rbp+50h+var_80]
0x140031d30  mov     rcx, cs:qword_1400273D8
0x140031d37  lea     rdx, [rbp+50h+var_60]
0x140031d3b  mov     dword ptr [rsp+150h+var_118], eax
0x140031d3f  mov     r9d, r12d
0x140031d42  lea     rax, [rbp+50h+var_A0]
0x140031d46  mov     [rsp+150h+var_120], rax
0x140031d4b  mov     al, [rsp+150h+var_E0]
0x140031d4f  mov     byte ptr [rsp+150h+var_128], al
0x140031d53  mov     al, [rsi]
0x140031d55  mov     byte ptr [rsp+150h+var_130], al
0x140031d59  call    WinNatLibCreateStaticBindingEntry
0x140031d5e  mov     edi, eax
0x140031d60  test    eax, eax
0x140031d62  js      loc_14003200B
0x140031d68  mov     edx, 88h
0x140031d6d  mov     r8d, 6D734E53h
0x140031d73  lea     ecx, [rdx+78h]
0x140031d76  call    cs:__imp_ExAllocatePool2
0x140031d7d  nop     dword ptr [rax+rax+00h]
0x140031d82  mov     r14, rax
0x140031d85  test    rax, rax
0x140031d88  jnz     short loc_140031D94
0x140031d8a  mov     edi, 0C000009Ah
0x140031d8f  jmp     loc_140031FE7
0x140031d94  mov     rax, [rbp+50h+var_B8]
0x140031d98  mov     eax, [rax+50h]
0x140031d9b  mov     [r14+20h], eax
0x140031d9f  mov     [r14+10h], r12d
0x140031da3  mov     rax, [rbp+50h+var_C8]
0x140031da7  mov     [r14+18h], rax
0x140031dab  mov     rax, [r13+120h]
0x140031db2  mov     [r14+80h], rax
0x140031db9  cmp     [r13+0E6h], bl
0x140031dc0  jbe     loc_140031EA7
0x140031dc6  xor     eax, eax
0x140031dc8  cmp     [rsi+8], eax
0x140031dcb  jnz     short loc_140031E09
0x140031dcd  mov     edi, [rsi+50h]
0x140031dd0  lea     rax, [rsp+150h+var_DD]
0x140031dd5  movzx   edx, word ptr [rsi+28h]
0x140031dd9  mov     r8d, edi
0x140031ddc  mov     cl, [rsi]
0x140031dde  mov     r9b, 1
0x140031de1  mov     [rsp+150h+var_130], rax
0x140031de6  call    SlbNatFindAssociatedStaticMapping
0x140031deb  cmp     [rsp+150h+var_DD], bl
0x140031def  jz      short loc_140031DFB
0x140031df1  mov     edi, 0C00000BDh
0x140031df6  jmp     loc_140031FE7
0x140031dfb  test    rax, rax
0x140031dfe  jz      short loc_140031E09
0x140031e00  cmp     [rax+74h], ebx
0x140031e03  jz      short loc_140031E5D
0x140031e05  test    edi, edi
0x140031e07  jz      short loc_140031E61
0x140031e09  mov     edi, [rbp+50h+var_D0]
0x140031e0c  test    edi, edi
0x140031e0e  jns     short loc_140031E2F
0x140031e10  mov     [rsp+150h+var_DE], bl
0x140031e14  test    rax, rax
0x140031e17  jz      loc_140031FE7
0x140031e1d  mov     rcx, [rax+78h]
0x140031e21  test    rcx, rcx
0x140031e24  jz      short loc_140031E61
0x140031e26  movups  xmm0, xmmword ptr [rcx+8]
0x140031e2a  movdqu  [rbp+50h+var_B0], xmm0
0x140031e2f  mov     edx, 28h ; '('
0x140031e34  mov     ecx, 100h
0x140031e39  mov     r8d, 61704E53h
0x140031e3f  call    cs:__imp_ExAllocatePool2
0x140031e46  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
