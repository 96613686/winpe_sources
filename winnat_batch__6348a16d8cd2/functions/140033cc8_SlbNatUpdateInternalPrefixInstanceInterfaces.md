# SlbNatUpdateInternalPrefixInstanceInterfaces

- ea: `0x140033cc8`
- end: `0x14003426b`
- name: `SlbNatUpdateInternalPrefixInstanceInterfaces`
- size: `1443`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002e560`
- `0x140033c98`

## callees

- `0x1400096fc`
- `0x14000c7a0`
- `0x14000c808`
- `0x14000caa0`
- `0x14001f020`
- `0x14002d008`
- `0x14002d040`
- `0x14002d060`
- `0x14002d0c4`
- `0x14002e220`
- `0x14002e284`
- `0x14002e324`
- `0x14002f9fc`
- `0x1400306d8`
- `0x140032ac0`
- `0x140032c90`
- `0x140033204`
- `0x14003358c`
- `0x140033cc8`
- `0x140034274`

## import_xrefs

- `NETIO!ConvertInterfaceLuidToIndex` at `0x140033dd9`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x140034035`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x140033dd9`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x140034035`

## string_xrefs

- `0x140034242`: `SlbNatUpdateInternalPrefixInstanceInterfaces`

## pseudocode

```c
__int64 __fastcall SlbNatUpdateInternalPrefixInstanceInterfaces(
        __int64 a1,
        __int64 a2,
        const NET_LUID *a3,
        const NET_LUID *a4,
        unsigned int a5)
{
  unsigned int v5; // edi
  const NET_LUID *v6; // r12
  unsigned __int16 v8; // r13
  __int64 v10; // rax
  const NET_LUID *v11; // r15
  unsigned int v12; // ebx
  __int64 v13; // rdi
  __int64 v14; // rcx
  NTSTATUS v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 *i; // rbx
  size_t v23; // r8
  int ExternalAddressBothFamilies; // eax
  int InternalAddress; // eax
  unsigned int j; // r14d
  __int64 v27; // rdx
  __int64 v28; // rcx
  int v29; // eax
  int v30; // eax
  int v32; // [rsp+20h] [rbp-10h]
  ULONG InterfaceIndex; // [rsp+70h] [rbp+40h] BYREF
  unsigned int v34; // [rsp+78h] [rbp+48h]
  __int64 v35; // [rsp+80h] [rbp+50h]

  v5 = 0;
  v6 = a4;
  v8 = a2;
  v34 = 0;
  InterfaceIndex = 0;
  if ( !*(_BYTE *)(a1 + 230) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  if ( (xmmword_1400262E0 & 2) != 0 )
    WPP_SF_S(a1, 20, a3, a1 + 80);
  if ( a3 && (xmmword_1400262E0 & 2) != 0 )
    WPP_SF_d(1025, 21, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, LODWORD(a3[1].Value));
  v10 = 16;
  v11 = v6;
  if ( v8 != 2 )
    v10 = 24;
  v12 = 0;
  v35 = v10;
  if ( a5 )
  {
    v13 = (unsigned int)v10;
    do
    {
      if ( (xmmword_1400262E0 & 2) != 0 )
        WPP_SF_d(1025, 22, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, LODWORD(v11[1].Value));
      ++v12;
      v11 = (const NET_LUID *)((char *)v11 + v13);
    }
    while ( v12 < a5 );
    v5 = v34;
  }
  if ( v8 != *(_WORD *)(a1 + 228) )
    return v5;
  v14 = 32;
  if ( v8 != 2 )
    v14 = 128;
  if ( *(unsigned __int8 *)(a1 + 230) > (unsigned int)v14 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, a2, a3, a4);
  if ( a3 )
  {
    if ( v6 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, a2, a3, a4);
    v15 = ConvertInterfaceLuidToIndex(a3, &InterfaceIndex);
    v5 = v15;
    if ( v15 < 0 )
    {
      if ( (xmmword_1400262D0 & 2) != 0 )
        WPP_SF_d(513, 23, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, (unsigned int)v15);
LABEL_110:
      if ( InterfaceIndex )
        SlbNatInsertErrorEntry(InterfaceIndex, v5, L"SlbNatUpdateInternalPrefixInstanceInterfaces");
      return v5;
    }
    if ( !(unsigned __int8)IsDefaultCompartment(a3->Value) )
      return v5;
    if ( !SlbNatIPPrefixMatch(&a3[1], (const void *)(a1 + 232), *(unsigned __int8 *)(a1 + 230)) )
    {
      if ( !(unsigned __int8)SlbNatIsInterfaceInternal(InterfaceIndex) )
      {
        if ( v8 != 2 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18, v19);
        if ( !LODWORD(a3[1].Value) )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18, v19);
        for ( i = *(__int64 **)(a1 + 24); i != (__int64 *)(a1 + 24); i = (__int64 *)*i )
        {
          if ( v8 == *((_WORD *)i + 26) )
          {
            v23 = 4;
            if ( v8 != 2 )
              v23 = 16;
            if ( !memcmp(i + 7, &a3[1], v23) )
            {
              if ( i )
              {
                if ( (xmmword_1400262E0 & 2) == 0 )
                  return v5;
                v20 = 25;
                goto LABEL_32;
              }
              break;
            }
          }
        }
        ExternalAddressBothFamilies = SlbNatCreateExternalAddressBothFamilies(a1, v8, a3);
        v5 = ExternalAddressBothFamilies;
        if ( ExternalAddressBothFamilies < 0 )
        {
          if ( ExternalAddressBothFamilies == -1073741670 )
            goto LABEL_50;
          if ( (xmmword_1400262D0 & 2) != 0 )
            WPP_SF_d(
              513,
              26,
              WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids,
              (unsigned int)ExternalAddressBothFamilies);
          v5 = 0;
        }
        SlbNatChangeInstanceExternalInterface(a1, a3);
        return v5;
      }
      if ( (xmmword_1400262E0 & 2) == 0 )
        return v5;
      v20 = 24;
      goto LABEL_32;
    }
    if ( (unsigned __int8)SlbNatIsInterfaceExternal(InterfaceIndex) )
    {
      SlbNatRemoveExternalInterfaceFromInstances(InterfaceIndex);
    }
    else if ( (unsigned __int8)SlbNatIsInterfaceInternal(InterfaceIndex) )
    {
      if ( !(unsigned __int8)SlbNatIsInterfaceMappingSet(
                               InterfaceIndex,
                               *(unsigned int *)(a1 + 68),
                               *(_QWORD *)(a1 + 16)) )
      {
        if ( (xmmword_1400262D0 & 2) == 0 )
          return v5;
        v20 = 27;
        v21 = 513;
        goto LABEL_33;
      }
      if ( SlbNatFindInternalAddress(a1, &a3[1]) )
      {
        if ( (xmmword_1400262E0 & 2) == 0 )
          return v5;
        v20 = 28;
LABEL_32:
        v21 = 1025;
LABEL_33:
        WPP_SF_(v21, v20, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids);
        return v5;
      }
    }
    InternalAddress = SlbNatCreateInternalAddress(a1, v8, (__int64)a3, InterfaceIndex);
    v5 = InternalAddress;
    if ( InternalAddress < 0 )
    {
      if ( InternalAddress == -1073741670 )
      {
LABEL_50:
        SlbNatInitiateLowResourceHandling();
      }
      else if ( (xmmword_1400262D0 & 2) != 0 )
      {
        WPP_SF_d(513, 29, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, (unsigned int)InternalAddress);
      }
      return 0;
    }
    return v5;
  }
  LOBYTE(v34) = 0;
  if ( !v6 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, a2, a3, a4);
  for ( j = 0; j < a5; ++j )
  {
    if ( ConvertInterfaceLuidToIndex(v6, &InterfaceIndex) < 0 )
    {
      if ( (xmmword_1400262D0 & 2) != 0 )
        WPP_SF_(513, 30, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids);
      goto LABEL_99;
    }
    if ( !(unsigned __int8)IsDefaultCompartment(v6->Value) )
      goto LABEL_99;
    if ( SlbNatIPPrefixMatch(&v6[1], (const void *)(a1 + 232), *(unsigned __int8 *)(a1 + 230)) )
    {
      if ( (unsigned __int8)SlbNatIsInterfaceExternal(InterfaceIndex) )
      {
        SlbNatRemoveExternalInterfaceFromInstances(InterfaceIndex);
LABEL_94:
        v30 = SlbNatCreateInternalAddress(a1, v8, (__int64)v6, InterfaceIndex);
        v5 = v30;
        if ( v30 < 0 )
        {
          if ( v30 == -1073741670 )
            goto LABEL_50;
          if ( (xmmword_1400262D0 & 2) != 0 )
            WPP_SF_dd(513, 36, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, j, v30);
          v5 = 0;
        }
        goto LABEL_99;
      }
      if ( !(unsigned __int8)SlbNatIsInterfaceInternal(InterfaceIndex) )
        goto LABEL_94;
      if ( (unsigned __int8)SlbNatIsInterfaceMappingSet(
                              InterfaceIndex,
                              *(unsigned int *)(a1 + 68),
                              *(_QWORD *)(a1 + 16)) )
      {
        if ( !SlbNatFindInternalAddress(a1, &v6[1]) )
          goto LABEL_94;
        if ( (xmmword_1400262E0 & 2) != 0 )
        {
          v27 = 35;
          goto LABEL_81;
        }
      }
      else if ( (xmmword_1400262D0 & 2) != 0 )
      {
        v27 = 34;
        v28 = 513;
        goto LABEL_82;
      }
    }
    else
    {
      if ( (unsigned __int8)SlbNatIsInterfaceInternal(InterfaceIndex) )
      {
        if ( (xmmword_1400262E0 & 2) == 0 )
          goto LABEL_99;
        v27 = 31;
LABEL_81:
        v28 = 1025;
LABEL_82:
        WPP_SF_d(v28, v27, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, j);
        goto LABEL_99;
      }
      LOBYTE(v34) = 1;
      LOBYTE(v32) = 1;
      if ( SlbNatFindExternalAddressByAddressAndPort(a1, &v6[1], v8, 0, v32) )
      {
        if ( (xmmword_1400262E0 & 2) != 0 )
        {
          v27 = 32;
          goto LABEL_81;
        }
      }
      else
      {
        v29 = SlbNatCreateExternalAddressBothFamilies(a1, v8, v6);
        v5 = v29;
        if ( v29 < 0 )
        {
          if ( v29 == -1073741670 )
            goto LABEL_50;
          if ( (xmmword_1400262D0 & 2) != 0 )
            WPP_SF_dd(513, 33, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, j, v29);
          v5 = 0;
        }
        SlbNatChangeInstanceExternalInterface(a1, v6);
      }
    }
LABEL_99:
    v6 = (const NET_LUID *)((char *)v6 + v35);
  }
  if ( !(_BYTE)v34 )
  {
    SlbNatChangeInstanceExternalInterface(a1, 0);
    v5 = -1073741198;
    goto LABEL_110;
  }
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_110;
  return v5;
}

```

## disassembly

```asm
0x140033cc8  mov     [rsp-38h+arg_18], rbx
0x140033ccd  push    rbp
0x140033cce  push    rsi
0x140033ccf  push    rdi
0x140033cd0  push    r12
0x140033cd2  push    r13
0x140033cd4  push    r14
0x140033cd6  push    r15
0x140033cd8  mov     rbp, rsp
0x140033cdb  sub     rsp, 30h
0x140033cdf  xor     edi, edi
0x140033ce1  mov     r12, r9
0x140033ce4  mov     r14, r8
0x140033ce7  movzx   r13d, dx
0x140033ceb  mov     rsi, rcx
0x140033cee  mov     [rbp+arg_8], edi
0x140033cf1  mov     [rbp+InterfaceIndex], edi
0x140033cf4  cmp     [rcx+0E6h], dil
0x140033cfb  ja      short loc_140033D02
0x140033cfd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140033d02  test    byte ptr cs:xmmword_1400262E0, 2
0x140033d09  jz      short loc_140033D19
0x140033d0b  lea     r9, [rsi+50h]
0x140033d0f  mov     edx, 14h
0x140033d14  call    WPP_SF_S
0x140033d19  test    r14, r14
0x140033d1c  jz      short loc_140033D41
0x140033d1e  test    byte ptr cs:xmmword_1400262E0, 2
0x140033d25  jz      short loc_140033D41
0x140033d27  mov     r9d, [r14+8]
0x140033d2b  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140033d32  mov     edx, 15h
0x140033d37  mov     ecx, 401h
0x140033d3c  call    WPP_SF_d
0x140033d41  mov     eax, 10h
0x140033d46  cmp     r13w, 2
0x140033d4b  mov     r15, r12
0x140033d4e  lea     ecx, [rax+8]
0x140033d51  cmovnz  eax, ecx
0x140033d54  xor     ebx, ebx
0x140033d56  mov     [rbp+arg_10], rax
0x140033d5a  cmp     [rbp+arg_20], ebx
0x140033d5d  jbe     short loc_140033D91
0x140033d5f  mov     edi, eax
0x140033d61  test    byte ptr cs:xmmword_1400262E0, 2
0x140033d68  jz      short loc_140033D84
0x140033d6a  mov     r9d, [r15+8]
0x140033d6e  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140033d75  mov     edx, 16h
0x140033d7a  mov     ecx, 401h
0x140033d7f  call    WPP_SF_d
0x140033d84  inc     ebx
0x140033d86  add     r15, rdi
0x140033d89  cmp     ebx, [rbp+arg_20]
0x140033d8c  jb      short loc_140033D61
0x140033d8e  mov     edi, [rbp+arg_8]
0x140033d91  cmp     r13w, [rsi+0E4h]
0x140033d99  jnz     loc_140034250
0x140033d9f  mov     ecx, 20h ; ' '
0x140033da4  cmp     r13w, 2
0x140033da9  lea     eax, [rcx+60h]
0x140033dac  cmovnz  ecx, eax
0x140033daf  movzx   eax, byte ptr [rsi+0E6h]
0x140033db6  cmp     eax, ecx
0x140033db8  jbe     short loc_140033DBF
0x140033dba  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140033dbf  test    r14, r14
0x140033dc2  jz      loc_14003400C
0x140033dc8  test    r12, r12
0x140033dcb  jz      short loc_140033DD2
0x140033dcd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140033dd2  lea     rdx, [rbp+InterfaceIndex]; InterfaceIndex
0x140033dd6  mov     rcx, r14; InterfaceLuid
0x140033dd9  call    cs:__imp_ConvertInterfaceLuidToIndex
0x140033de0  nop     dword ptr [rax+rax+00h]
0x140033de5  mov     edi, eax
0x140033de7  test    eax, eax
0x140033de9  jns     short loc_140033E16
0x140033deb  test    byte ptr cs:xmmword_1400262D0, 2
0x140033df2  jz      loc_14003423B
0x140033df8  mov     edx, 17h
0x140033dfd  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140033e04  mov     ecx, 201h
0x140033e09  mov     r9d, eax
0x140033e0c  call    WPP_SF_d
0x140033e11  jmp     loc_14003423B
0x140033e16  mov     rcx, [r14]
0x140033e19  call    IsDefaultCompartment
0x140033e1e  test    al, al
0x140033e20  jz      loc_140034250
0x140033e26  movzx   r8d, byte ptr [rsi+0E6h]
0x140033e2e  lea     r12, [r14+8]
0x140033e32  mov     rcx, r12
0x140033e35  lea     rdx, [rsi+0E8h]
0x140033e3c  call    SlbNatIPPrefixMatch
0x140033e41  mov     ecx, [rbp+InterfaceIndex]
0x140033e44  test    al, al
0x140033e46  jnz     loc_140033F4B
0x140033e4c  call    SlbNatIsInterfaceInternal
0x140033e51  test    al, al
0x140033e53  jz      short loc_140033E7D
0x140033e55  test    byte ptr cs:xmmword_1400262E0, 2
0x140033e5c  jz      loc_140034250
0x140033e62  mov     edx, 18h
0x140033e67  mov     ecx, 401h
0x140033e6c  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140033e73  call    WPP_SF_
0x140033e78  jmp     loc_140034250
0x140033e7d  xor     ebx, ebx
0x140033e7f  cmp     r13w, 2
0x140033e84  jz      short loc_140033E8B
0x140033e86  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140033e8b  cmp     [r12], ebx
0x140033e8f  jnz     short loc_140033E96
0x140033e91  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140033e96  lea     r15, [rsi+18h]
0x140033e9a  mov     rbx, [r15]
0x140033e9d  cmp     rbx, r15
0x140033ea0  jz      short loc_140033EED
0x140033ea2  cmp     r13w, [rbx+34h]
0x140033ea7  jnz     short loc_140033ECC
0x140033ea9  mov     r8d, 4
0x140033eaf  lea     rcx, [rbx+38h]; Buf1
0x140033eb3  cmp     r13w, 2
0x140033eb8  mov     rdx, r12; Buf2
0x140033ebb  lea     eax, [r8+0Ch]
0x140033ebf  cmovnz  r8d, eax; Size
0x140033ec3  call    memcmp
0x140033ec8  test    eax, eax
0x140033eca  jz      short loc_140033ED1
0x140033ecc  mov     rbx, [rbx]
0x140033ecf  jmp     short loc_140033E9D
0x140033ed1  test    rbx, rbx
0x140033ed4  jz      short loc_140033EED
0x140033ed6  test    byte ptr cs:xmmword_1400262E0, 2
0x140033edd  jz      loc_140034250
0x140033ee3  mov     edx, 19h
0x140033ee8  jmp     loc_140033E67
0x140033eed  mov     r8, r14
0x140033ef0  movzx   edx, r13w
0x140033ef4  mov     rcx, rsi
0x140033ef7  call    SlbNatCreateExternalAddressBothFamilies
0x140033efc  mov     edi, eax
0x140033efe  test    eax, eax
0x140033f00  jns     short loc_140033F3B
0x140033f02  mov     ebx, 0C000009Ah
0x140033f07  cmp     eax, ebx
0x140033f09  jnz     short loc_140033F17
0x140033f0b  call    SlbNatInitiateLowResourceHandling
0x140033f10  xor     edi, edi
0x140033f12  jmp     loc_140034250
0x140033f17  test    byte ptr cs:xmmword_1400262D0, 2
0x140033f1e  jz      short loc_140033F39
0x140033f20  mov     edx, 1Ah
0x140033f25  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140033f2c  mov     ecx, 201h
0x140033f31  mov     r9d, eax
0x140033f34  call    WPP_SF_d
0x140033f39  xor     edi, edi
0x140033f3b  mov     rdx, r14
0x140033f3e  mov     rcx, rsi
0x140033f41  call    SlbNatChangeInstanceExternalInterface
0x140033f46  jmp     loc_140034250
0x140033f4b  call    SlbNatIsInterfaceExternal
0x140033f50  mov     ecx, [rbp+InterfaceIndex]
0x140033f53  test    al, al
0x140033f55  jz      short loc_140033FA9
0x140033f57  call    SlbNatRemoveExternalInterfaceFromInstances
0x140033f5c  mov     r9d, [rbp+InterfaceIndex]
0x140033f60  mov     r8, r14
0x140033f63  movzx   edx, r13w
0x140033f67  mov     rcx, rsi
0x140033f6a  call    SlbNatCreateInternalAddress
0x140033f6f  mov     edi, eax
0x140033f71  test    eax, eax
0x140033f73  jns     loc_140034250
0x140033f79  mov     ebx, 0C000009Ah
0x140033f7e  cmp     eax, ebx
0x140033f80  jz      short loc_140033F0B
0x140033f82  test    byte ptr cs:xmmword_1400262D0, 2
0x140033f89  jz      short loc_140033F10
0x140033f8b  mov     edx, 1Dh
0x140033f90  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140033f97  mov     ecx, 201h
0x140033f9c  mov     r9d, eax
0x140033f9f  call    WPP_SF_d
0x140033fa4  jmp     loc_140033F10
0x140033fa9  call    SlbNatIsInterfaceInternal
0x140033fae  test    al, al
0x140033fb0  jz      short loc_140033F5C
0x140033fb2  mov     r8, [rsi+10h]
0x140033fb6  mov     edx, [rsi+44h]
0x140033fb9  mov     ecx, [rbp+InterfaceIndex]
0x140033fbc  call    SlbNatIsInterfaceMappingSet
0x140033fc1  test    al, al
0x140033fc3  jnz     short loc_140033FE1
0x140033fc5  test    byte ptr cs:xmmword_1400262D0, 2
0x140033fcc  jz      loc_140034250
0x140033fd2  mov     edx, 1Bh
0x140033fd7  mov     ecx, 201h
0x140033fdc  jmp     loc_140033E6C
0x140033fe1  mov     rdx, r12
0x140033fe4  mov     rcx, rsi
0x140033fe7  call    SlbNatFindInternalAddress
0x140033fec  test    rax, rax
0x140033fef  jz      loc_140033F5C
0x140033ff5  test    byte ptr cs:xmmword_1400262E0, 2
0x140033ffc  jz      loc_140034250
0x140034002  mov     edx, 1Ch
0x140034007  jmp     loc_140033E67
0x14003400c  mov     byte ptr [rbp+arg_8], 0
0x140034010  test    r12, r12
0x140034013  jnz     short loc_14003401A
0x140034015  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003401a  xor     r14d, r14d
0x14003401d  mov     ebx, 0C000009Ah
0x140034022  mov     eax, edi
0x140034024  cmp     r14d, [rbp+arg_20]
0x140034028  jnb     loc_140034220
0x14003402e  lea     rdx, [rbp+InterfaceIndex]; InterfaceIndex
0x140034032  mov     rcx, r12; InterfaceLuid
0x140034035  call    cs:__imp_ConvertInterfaceLuidToIndex
0x14003403c  nop     dword ptr [rax+rax+00h]
0x140034041  test    eax, eax
0x140034043  jns     short loc_14003406D
0x140034045  test    byte ptr cs:xmmword_1400262D0, 2
0x14003404c  jz      loc_1400341B9
0x140034052  mov     edx, 1Eh
0x140034057  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x14003405e  mov     ecx, 201h
0x140034063  call    WPP_SF_
0x140034068  jmp     loc_1400341B9
0x14003406d  mov     rcx, [r12]
0x140034071  call    IsDefaultCompartment
0x140034076  test    al, al
0x140034078  jz      loc_1400341B9
0x14003407e  movzx   r8d, byte ptr [rsi+0E6h]
0x140034086  lea     r15, [r12+8]
0x14003408b  mov     rcx, r15
0x14003408e  lea     rdx, [rsi+0E8h]
0x140034095  call    SlbNatIPPrefixMatch
0x14003409a  mov     ecx, [rbp+InterfaceIndex]
0x14003409d  test    al, al
0x14003409f  jnz     loc_14003415F
0x1400340a5  call    SlbNatIsInterfaceInternal
0x1400340aa  test    al, al
0x1400340ac  jz      short loc_1400340D9
0x1400340ae  test    byte ptr cs:xmmword_1400262E0, 2
0x1400340b5  jz      loc_1400341B9
0x1400340bb  mov     edx, 1Fh
0x1400340c0  mov     ecx, 401h
0x1400340c5  mov     r9d, r14d
0x1400340c8  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x1400340cf  call    WPP_SF_d
0x1400340d4  jmp     loc_1400341B9
0x1400340d9  xor     r9d, r9d
0x1400340dc  mov     byte ptr [rbp+arg_8], 1
0x1400340e0  movzx   r8d, r13w
0x1400340e4  mov     byte ptr [rsp+30h+var_10], 1
0x1400340e9  mov     rdx, r15
0x1400340ec  mov     rcx, rsi
0x1400340ef  call    SlbNatFindExternalAddressByAddressAndPort
0x1400340f4  test    rax, rax
0x1400340f7  jz      short loc_14003410D
0x1400340f9  test    byte ptr cs:xmmword_1400262E0, 2
0x140034100  jz      loc_1400341B9
0x140034106  mov     edx, 20h ; ' '
0x14003410b  jmp     short loc_1400340C0
0x14003410d  mov     r8, r12
0x140034110  movzx   edx, r13w
0x140034114  mov     rcx, rsi
0x140034117  call    SlbNatCreateExternalAddressBothFamilies
0x14003411c  mov     edi, eax
0x14003411e  test    eax, eax
0x140034120  jns     short loc_140034152
0x140034122  cmp     eax, ebx
0x140034124  jz      loc_140033F0B
0x14003412a  test    byte ptr cs:xmmword_1400262D0, 2
0x140034131  jz      short loc_140034150
0x140034133  mov     edx, 21h ; '!'
0x140034138  mov     [rsp+30h+var_10], eax
0x14003413c  mov     ecx, 201h
0x140034141  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140034148  mov     r9d, r14d
0x14003414b  call    WPP_SF_dd
0x140034150  xor     edi, edi
0x140034152  mov     rdx, r12
0x140034155  mov     rcx, rsi
0x140034158  call    SlbNatChangeInstanceExternalInterface
0x14003415d  jmp     short loc_1400341B9
0x14003415f  call    SlbNatIsInterfaceExternal
0x140034164  mov     ecx, [rbp+InterfaceIndex]
0x140034167  test    al, al
0x140034169  jz      short loc_1400341C5
0x14003416b  call    SlbNatRemoveExternalInterfaceFromInstances
0x140034170  mov     r9d, [rbp+InterfaceIndex]
0x140034174  mov     r8, r12
0x140034177  movzx   edx, r13w
0x14003417b  mov     rcx, rsi
0x14003417e  call    SlbNatCreateInternalAddress
  ... truncated ...
```
