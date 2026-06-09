# SlbNatUpdateInternalPrefixInstanceInterfaces

- ea: `0x140034fd8`
- end: `0x14003557b`
- name: `SlbNatUpdateInternalPrefixInstanceInterfaces`
- size: `1443`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002f560`
- `0x140034fa8`

## callees

- `0x1400096fc`
- `0x14000c7a0`
- `0x14000c808`
- `0x14000caa0`
- `0x14001f560`
- `0x14002e008`
- `0x14002e040`
- `0x14002e060`
- `0x14002e0c4`
- `0x14002f220`
- `0x14002f284`
- `0x14002f324`
- `0x140030b2c`
- `0x140031808`
- `0x140033bf0`
- `0x140033dc0`
- `0x140034334`
- `0x1400346bc`
- `0x140034fd8`
- `0x140035584`

## import_xrefs

- `NETIO!ConvertInterfaceLuidToIndex` at `0x1400350e9`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x140035345`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x1400350e9`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x140035345`

## string_xrefs

- `0x140035552`: `SlbNatUpdateInternalPrefixInstanceInterfaces`

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
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 *i; // rbx
  size_t v22; // r8
  int ExternalAddressBothFamilies; // eax
  int InternalAddress; // eax
  unsigned int j; // r14d
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // eax
  int v29; // eax
  int v31; // [rsp+20h] [rbp-10h]
  ULONG InterfaceIndex; // [rsp+70h] [rbp+40h] BYREF
  unsigned int v33; // [rsp+78h] [rbp+48h]
  __int64 v34; // [rsp+80h] [rbp+50h]

  v5 = 0;
  v8 = a2;
  v33 = 0;
  InterfaceIndex = 0;
  if ( !*(_BYTE *)(a1 + 230) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  if ( (xmmword_1400272E0 & 2) != 0 )
    WPP_SF_S(a1, 20, a3, a1 + 80);
  if ( a3 && (xmmword_1400272E0 & 2) != 0 )
    WPP_SF_d(1025, 21, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, LODWORD(a3[1].Value));
  v10 = 16;
  v11 = a4;
  if ( v8 != 2 )
    v10 = 24;
  v12 = 0;
  v34 = v10;
  if ( a5 )
  {
    v13 = (unsigned int)v10;
    do
    {
      if ( (xmmword_1400272E0 & 2) != 0 )
        WPP_SF_d(1025, 22, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, LODWORD(v11[1].Value));
      ++v12;
      v11 = (const NET_LUID *)((char *)v11 + v13);
    }
    while ( v12 < a5 );
    v5 = v33;
  }
  if ( v8 != *(_WORD *)(a1 + 228) )
    return v5;
  v14 = 32;
  if ( v8 != 2 )
    v14 = 128;
  if ( *(unsigned __int8 *)(a1 + 230) > (unsigned int)v14 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, a2, a3);
  if ( a3 )
  {
    if ( a4 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, a2, a3);
    v15 = ConvertInterfaceLuidToIndex(a3, &InterfaceIndex);
    v5 = v15;
    if ( v15 < 0 )
    {
      if ( (xmmword_1400272D0 & 2) != 0 )
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
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18);
        if ( !LODWORD(a3[1].Value) )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18);
        for ( i = *(__int64 **)(a1 + 24); i != (__int64 *)(a1 + 24); i = (__int64 *)*i )
        {
          if ( v8 == *((_WORD *)i + 26) )
          {
            v22 = 4;
            if ( v8 != 2 )
              v22 = 16;
            if ( !memcmp(i + 7, &a3[1], v22) )
            {
              if ( i )
              {
                if ( (xmmword_1400272E0 & 2) == 0 )
                  return v5;
                v19 = 25;
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
          if ( (xmmword_1400272D0 & 2) != 0 )
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
      if ( (xmmword_1400272E0 & 2) == 0 )
        return v5;
      v19 = 24;
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
        if ( (xmmword_1400272D0 & 2) == 0 )
          return v5;
        v19 = 27;
        v20 = 513;
        goto LABEL_33;
      }
      if ( SlbNatFindInternalAddress(a1, &a3[1]) )
      {
        if ( (xmmword_1400272E0 & 2) == 0 )
          return v5;
        v19 = 28;
LABEL_32:
        v20 = 1025;
LABEL_33:
        WPP_SF_(v20, v19, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids);
        return v5;
      }
    }
    InternalAddress = SlbNatCreateInternalAddress(a1, v8, a3, InterfaceIndex);
    v5 = InternalAddress;
    if ( InternalAddress < 0 )
    {
      if ( InternalAddress == -1073741670 )
      {
LABEL_50:
        SlbNatInitiateLowResourceHandling();
      }
      else if ( (xmmword_1400272D0 & 2) != 0 )
      {
        WPP_SF_d(513, 29, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, (unsigned int)InternalAddress);
      }
      return 0;
    }
    return v5;
  }
  LOBYTE(v33) = 0;
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, a2, a3);
  for ( j = 0; j < a5; ++j )
  {
    if ( ConvertInterfaceLuidToIndex(a4, &InterfaceIndex) < 0 )
    {
      if ( (xmmword_1400272D0 & 2) != 0 )
        WPP_SF_(513, 30, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids);
      goto LABEL_99;
    }
    if ( !(unsigned __int8)IsDefaultCompartment(a4->Value) )
      goto LABEL_99;
    if ( SlbNatIPPrefixMatch(&a4[1], (const void *)(a1 + 232), *(unsigned __int8 *)(a1 + 230)) )
    {
      if ( (unsigned __int8)SlbNatIsInterfaceExternal(InterfaceIndex) )
      {
        SlbNatRemoveExternalInterfaceFromInstances(InterfaceIndex);
LABEL_94:
        v29 = SlbNatCreateInternalAddress(a1, v8, a4, InterfaceIndex);
        v5 = v29;
        if ( v29 < 0 )
        {
          if ( v29 == -1073741670 )
            goto LABEL_50;
          if ( (xmmword_1400272D0 & 2) != 0 )
            WPP_SF_dd(513, 36, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, j, v29);
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
        if ( !SlbNatFindInternalAddress(a1, &a4[1]) )
          goto LABEL_94;
        if ( (xmmword_1400272E0 & 2) != 0 )
        {
          v26 = 35;
          goto LABEL_81;
        }
      }
      else if ( (xmmword_1400272D0 & 2) != 0 )
      {
        v26 = 34;
        v27 = 513;
        goto LABEL_82;
      }
    }
    else
    {
      if ( (unsigned __int8)SlbNatIsInterfaceInternal(InterfaceIndex) )
      {
        if ( (xmmword_1400272E0 & 2) == 0 )
          goto LABEL_99;
        v26 = 31;
LABEL_81:
        v27 = 1025;
LABEL_82:
        WPP_SF_d(v27, v26, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, j);
        goto LABEL_99;
      }
      LOBYTE(v33) = 1;
      LOBYTE(v31) = 1;
      if ( SlbNatFindExternalAddressByAddressAndPort(a1, &a4[1], v8, 0, v31) )
      {
        if ( (xmmword_1400272E0 & 2) != 0 )
        {
          v26 = 32;
          goto LABEL_81;
        }
      }
      else
      {
        v28 = SlbNatCreateExternalAddressBothFamilies(a1, v8, a4);
        v5 = v28;
        if ( v28 < 0 )
        {
          if ( v28 == -1073741670 )
            goto LABEL_50;
          if ( (xmmword_1400272D0 & 2) != 0 )
            WPP_SF_dd(513, 33, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, j, v28);
          v5 = 0;
        }
        SlbNatChangeInstanceExternalInterface(a1, a4);
      }
    }
LABEL_99:
    a4 = (const NET_LUID *)((char *)a4 + v34);
  }
  if ( !(_BYTE)v33 )
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
0x140034fd8  mov     [rsp-38h+arg_18], rbx
0x140034fdd  push    rbp
0x140034fde  push    rsi
0x140034fdf  push    rdi
0x140034fe0  push    r12
0x140034fe2  push    r13
0x140034fe4  push    r14
0x140034fe6  push    r15
0x140034fe8  mov     rbp, rsp
0x140034feb  sub     rsp, 30h
0x140034fef  xor     edi, edi
0x140034ff1  mov     r12, r9
0x140034ff4  mov     r14, r8
0x140034ff7  movzx   r13d, dx
0x140034ffb  mov     rsi, rcx
0x140034ffe  mov     [rbp+arg_8], edi
0x140035001  mov     [rbp+InterfaceIndex], edi
0x140035004  cmp     [rcx+0E6h], dil
0x14003500b  ja      short loc_140035012
0x14003500d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140035012  test    byte ptr cs:xmmword_1400272E0, 2
0x140035019  jz      short loc_140035029
0x14003501b  lea     r9, [rsi+50h]
0x14003501f  mov     edx, 14h
0x140035024  call    WPP_SF_S
0x140035029  test    r14, r14
0x14003502c  jz      short loc_140035051
0x14003502e  test    byte ptr cs:xmmword_1400272E0, 2
0x140035035  jz      short loc_140035051
0x140035037  mov     r9d, [r14+8]
0x14003503b  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140035042  mov     edx, 15h
0x140035047  mov     ecx, 401h
0x14003504c  call    WPP_SF_d
0x140035051  mov     eax, 10h
0x140035056  cmp     r13w, 2
0x14003505b  mov     r15, r12
0x14003505e  lea     ecx, [rax+8]
0x140035061  cmovnz  eax, ecx
0x140035064  xor     ebx, ebx
0x140035066  mov     [rbp+arg_10], rax
0x14003506a  cmp     [rbp+arg_20], ebx
0x14003506d  jbe     short loc_1400350A1
0x14003506f  mov     edi, eax
0x140035071  test    byte ptr cs:xmmword_1400272E0, 2
0x140035078  jz      short loc_140035094
0x14003507a  mov     r9d, [r15+8]
0x14003507e  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140035085  mov     edx, 16h
0x14003508a  mov     ecx, 401h
0x14003508f  call    WPP_SF_d
0x140035094  inc     ebx
0x140035096  add     r15, rdi
0x140035099  cmp     ebx, [rbp+arg_20]
0x14003509c  jb      short loc_140035071
0x14003509e  mov     edi, [rbp+arg_8]
0x1400350a1  cmp     r13w, [rsi+0E4h]
0x1400350a9  jnz     loc_140035560
0x1400350af  mov     ecx, 20h ; ' '
0x1400350b4  cmp     r13w, 2
0x1400350b9  lea     eax, [rcx+60h]
0x1400350bc  cmovnz  ecx, eax
0x1400350bf  movzx   eax, byte ptr [rsi+0E6h]
0x1400350c6  cmp     eax, ecx
0x1400350c8  jbe     short loc_1400350CF
0x1400350ca  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400350cf  test    r14, r14
0x1400350d2  jz      loc_14003531C
0x1400350d8  test    r12, r12
0x1400350db  jz      short loc_1400350E2
0x1400350dd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400350e2  lea     rdx, [rbp+InterfaceIndex]; InterfaceIndex
0x1400350e6  mov     rcx, r14; InterfaceLuid
0x1400350e9  call    cs:__imp_ConvertInterfaceLuidToIndex
0x1400350f0  nop     dword ptr [rax+rax+00h]
0x1400350f5  mov     edi, eax
0x1400350f7  test    eax, eax
0x1400350f9  jns     short loc_140035126
0x1400350fb  test    byte ptr cs:xmmword_1400272D0, 2
0x140035102  jz      loc_14003554B
0x140035108  mov     edx, 17h
0x14003510d  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140035114  mov     ecx, 201h
0x140035119  mov     r9d, eax
0x14003511c  call    WPP_SF_d
0x140035121  jmp     loc_14003554B
0x140035126  mov     rcx, [r14]
0x140035129  call    IsDefaultCompartment
0x14003512e  test    al, al
0x140035130  jz      loc_140035560
0x140035136  movzx   r8d, byte ptr [rsi+0E6h]
0x14003513e  lea     r12, [r14+8]
0x140035142  mov     rcx, r12
0x140035145  lea     rdx, [rsi+0E8h]
0x14003514c  call    SlbNatIPPrefixMatch
0x140035151  mov     ecx, [rbp+InterfaceIndex]
0x140035154  test    al, al
0x140035156  jnz     loc_14003525B
0x14003515c  call    SlbNatIsInterfaceInternal
0x140035161  test    al, al
0x140035163  jz      short loc_14003518D
0x140035165  test    byte ptr cs:xmmword_1400272E0, 2
0x14003516c  jz      loc_140035560
0x140035172  mov     edx, 18h
0x140035177  mov     ecx, 401h
0x14003517c  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140035183  call    WPP_SF_
0x140035188  jmp     loc_140035560
0x14003518d  xor     ebx, ebx
0x14003518f  cmp     r13w, 2
0x140035194  jz      short loc_14003519B
0x140035196  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003519b  cmp     [r12], ebx
0x14003519f  jnz     short loc_1400351A6
0x1400351a1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400351a6  lea     r15, [rsi+18h]
0x1400351aa  mov     rbx, [r15]
0x1400351ad  cmp     rbx, r15
0x1400351b0  jz      short loc_1400351FD
0x1400351b2  cmp     r13w, [rbx+34h]
0x1400351b7  jnz     short loc_1400351DC
0x1400351b9  mov     r8d, 4
0x1400351bf  lea     rcx, [rbx+38h]; Buf1
0x1400351c3  cmp     r13w, 2
0x1400351c8  mov     rdx, r12; Buf2
0x1400351cb  lea     eax, [r8+0Ch]
0x1400351cf  cmovnz  r8d, eax; Size
0x1400351d3  call    memcmp
0x1400351d8  test    eax, eax
0x1400351da  jz      short loc_1400351E1
0x1400351dc  mov     rbx, [rbx]
0x1400351df  jmp     short loc_1400351AD
0x1400351e1  test    rbx, rbx
0x1400351e4  jz      short loc_1400351FD
0x1400351e6  test    byte ptr cs:xmmword_1400272E0, 2
0x1400351ed  jz      loc_140035560
0x1400351f3  mov     edx, 19h
0x1400351f8  jmp     loc_140035177
0x1400351fd  mov     r8, r14
0x140035200  movzx   edx, r13w
0x140035204  mov     rcx, rsi
0x140035207  call    SlbNatCreateExternalAddressBothFamilies
0x14003520c  mov     edi, eax
0x14003520e  test    eax, eax
0x140035210  jns     short loc_14003524B
0x140035212  mov     ebx, 0C000009Ah
0x140035217  cmp     eax, ebx
0x140035219  jnz     short loc_140035227
0x14003521b  call    SlbNatInitiateLowResourceHandling
0x140035220  xor     edi, edi
0x140035222  jmp     loc_140035560
0x140035227  test    byte ptr cs:xmmword_1400272D0, 2
0x14003522e  jz      short loc_140035249
0x140035230  mov     edx, 1Ah
0x140035235  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x14003523c  mov     ecx, 201h
0x140035241  mov     r9d, eax
0x140035244  call    WPP_SF_d
0x140035249  xor     edi, edi
0x14003524b  mov     rdx, r14
0x14003524e  mov     rcx, rsi
0x140035251  call    SlbNatChangeInstanceExternalInterface
0x140035256  jmp     loc_140035560
0x14003525b  call    SlbNatIsInterfaceExternal
0x140035260  mov     ecx, [rbp+InterfaceIndex]
0x140035263  test    al, al
0x140035265  jz      short loc_1400352B9
0x140035267  call    SlbNatRemoveExternalInterfaceFromInstances
0x14003526c  mov     r9d, [rbp+InterfaceIndex]
0x140035270  mov     r8, r14
0x140035273  movzx   edx, r13w
0x140035277  mov     rcx, rsi
0x14003527a  call    SlbNatCreateInternalAddress
0x14003527f  mov     edi, eax
0x140035281  test    eax, eax
0x140035283  jns     loc_140035560
0x140035289  mov     ebx, 0C000009Ah
0x14003528e  cmp     eax, ebx
0x140035290  jz      short loc_14003521B
0x140035292  test    byte ptr cs:xmmword_1400272D0, 2
0x140035299  jz      short loc_140035220
0x14003529b  mov     edx, 1Dh
0x1400352a0  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x1400352a7  mov     ecx, 201h
0x1400352ac  mov     r9d, eax
0x1400352af  call    WPP_SF_d
0x1400352b4  jmp     loc_140035220
0x1400352b9  call    SlbNatIsInterfaceInternal
0x1400352be  test    al, al
0x1400352c0  jz      short loc_14003526C
0x1400352c2  mov     r8, [rsi+10h]
0x1400352c6  mov     edx, [rsi+44h]
0x1400352c9  mov     ecx, [rbp+InterfaceIndex]
0x1400352cc  call    SlbNatIsInterfaceMappingSet
0x1400352d1  test    al, al
0x1400352d3  jnz     short loc_1400352F1
0x1400352d5  test    byte ptr cs:xmmword_1400272D0, 2
0x1400352dc  jz      loc_140035560
0x1400352e2  mov     edx, 1Bh
0x1400352e7  mov     ecx, 201h
0x1400352ec  jmp     loc_14003517C
0x1400352f1  mov     rdx, r12
0x1400352f4  mov     rcx, rsi
0x1400352f7  call    SlbNatFindInternalAddress
0x1400352fc  test    rax, rax
0x1400352ff  jz      loc_14003526C
0x140035305  test    byte ptr cs:xmmword_1400272E0, 2
0x14003530c  jz      loc_140035560
0x140035312  mov     edx, 1Ch
0x140035317  jmp     loc_140035177
0x14003531c  mov     byte ptr [rbp+arg_8], 0
0x140035320  test    r12, r12
0x140035323  jnz     short loc_14003532A
0x140035325  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003532a  xor     r14d, r14d
0x14003532d  mov     ebx, 0C000009Ah
0x140035332  mov     eax, edi
0x140035334  cmp     r14d, [rbp+arg_20]
0x140035338  jnb     loc_140035530
0x14003533e  lea     rdx, [rbp+InterfaceIndex]; InterfaceIndex
0x140035342  mov     rcx, r12; InterfaceLuid
0x140035345  call    cs:__imp_ConvertInterfaceLuidToIndex
0x14003534c  nop     dword ptr [rax+rax+00h]
0x140035351  test    eax, eax
0x140035353  jns     short loc_14003537D
0x140035355  test    byte ptr cs:xmmword_1400272D0, 2
0x14003535c  jz      loc_1400354C9
0x140035362  mov     edx, 1Eh
0x140035367  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x14003536e  mov     ecx, 201h
0x140035373  call    WPP_SF_
0x140035378  jmp     loc_1400354C9
0x14003537d  mov     rcx, [r12]
0x140035381  call    IsDefaultCompartment
0x140035386  test    al, al
0x140035388  jz      loc_1400354C9
0x14003538e  movzx   r8d, byte ptr [rsi+0E6h]
0x140035396  lea     r15, [r12+8]
0x14003539b  mov     rcx, r15
0x14003539e  lea     rdx, [rsi+0E8h]
0x1400353a5  call    SlbNatIPPrefixMatch
0x1400353aa  mov     ecx, [rbp+InterfaceIndex]
0x1400353ad  test    al, al
0x1400353af  jnz     loc_14003546F
0x1400353b5  call    SlbNatIsInterfaceInternal
0x1400353ba  test    al, al
0x1400353bc  jz      short loc_1400353E9
0x1400353be  test    byte ptr cs:xmmword_1400272E0, 2
0x1400353c5  jz      loc_1400354C9
0x1400353cb  mov     edx, 1Fh
0x1400353d0  mov     ecx, 401h
0x1400353d5  mov     r9d, r14d
0x1400353d8  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x1400353df  call    WPP_SF_d
0x1400353e4  jmp     loc_1400354C9
0x1400353e9  xor     r9d, r9d
0x1400353ec  mov     byte ptr [rbp+arg_8], 1
0x1400353f0  movzx   r8d, r13w
0x1400353f4  mov     byte ptr [rsp+30h+var_10], 1
0x1400353f9  mov     rdx, r15
0x1400353fc  mov     rcx, rsi
0x1400353ff  call    SlbNatFindExternalAddressByAddressAndPort
0x140035404  test    rax, rax
0x140035407  jz      short loc_14003541D
0x140035409  test    byte ptr cs:xmmword_1400272E0, 2
0x140035410  jz      loc_1400354C9
0x140035416  mov     edx, 20h ; ' '
0x14003541b  jmp     short loc_1400353D0
0x14003541d  mov     r8, r12
0x140035420  movzx   edx, r13w
0x140035424  mov     rcx, rsi
0x140035427  call    SlbNatCreateExternalAddressBothFamilies
0x14003542c  mov     edi, eax
0x14003542e  test    eax, eax
0x140035430  jns     short loc_140035462
0x140035432  cmp     eax, ebx
0x140035434  jz      loc_14003521B
0x14003543a  test    byte ptr cs:xmmword_1400272D0, 2
0x140035441  jz      short loc_140035460
0x140035443  mov     edx, 21h ; '!'
0x140035448  mov     [rsp+30h+var_10], eax
0x14003544c  mov     ecx, 201h
0x140035451  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140035458  mov     r9d, r14d
0x14003545b  call    WPP_SF_dd
0x140035460  xor     edi, edi
0x140035462  mov     rdx, r12
0x140035465  mov     rcx, rsi
0x140035468  call    SlbNatChangeInstanceExternalInterface
0x14003546d  jmp     short loc_1400354C9
0x14003546f  call    SlbNatIsInterfaceExternal
0x140035474  mov     ecx, [rbp+InterfaceIndex]
0x140035477  test    al, al
0x140035479  jz      short loc_1400354D5
0x14003547b  call    SlbNatRemoveExternalInterfaceFromInstances
0x140035480  mov     r9d, [rbp+InterfaceIndex]
0x140035484  mov     r8, r12
0x140035487  movzx   edx, r13w
0x14003548b  mov     rcx, rsi
0x14003548e  call    SlbNatCreateInternalAddress
  ... truncated ...
```
