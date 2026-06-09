# Smb2ValidateProviderCallback

- ea: `0x140073ab0`
- end: `0x1400744ff`
- name: `Smb2ValidateProviderCallback`
- size: `2639`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
- tags: `broker_com_uri`

## callees

- `0x140004dcc`
- `0x140007400`
- `0x140013bf0`
- `0x14001cef0`
- `0x14001d624`
- `0x1400222ec`
- `0x140022958`
- `0x1400229ac`
- `0x1400260fc`
- `0x1400261cc`
- `0x140027304`
- `0x1400384d0`
- `0x140059f9c`
- `0x14005a9c0`
- `0x14005b1c0`
- `0x14005b5d0`
- `0x14005c010`
- `0x14005cba0`
- `0x14005d230`
- `0x14006a640`
- `0x14006a880`
- `0x14006af30`
- `0x140073ab0`
- `0x140074508`
- `0x140074ca0`
- `0x140081f40`
- `0x1400834f0`
- `0x1400862e0`
- `0x140087780`
- `0x1400884f0`
- `0x140088700`
- `0x140089550`
- `0x14008c450`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140074414`
- `ntoskrnl!RtlInitUnicodeString` at `0x140074414`
- `srvnet!SrvAdminAllowAnonymousAccess` at `0x140073e9c`
- `srvnet!SrvAdminAllowAnonymousAccess` at `0x140073e9c`
- `ksecdd!FreeContextBuffer` at `0x14007446a`
- `ksecdd!FreeContextBuffer` at `0x14007446a`
- `ksecdd!QueryContextAttributesW` at `0x140073f8d`
- `ksecdd!QueryContextAttributesW` at `0x140073f8d`

## pseudocode

```c
__int64 __fastcall Smb2ValidateProviderCallback(ULONG_PTR BugCheckParameter4, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rsi
  __int64 v6; // rdi
  __int64 v7; // rbp
  unsigned int v8; // ecx
  PDEVICE_OBJECT v9; // rcx
  unsigned int v10; // ecx
  int v11; // edx
  int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  int v15; // eax
  int v16; // edi
  __int64 (__fastcall *v17)(); // rax
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rdx
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  char v24; // al
  int v25; // ebp
  struct _UNICODE_STRING v26; // xmm0
  bool v27; // r14
  int v28; // r15d
  __int64 *v29; // rcx
  __int64 v30; // rsi
  struct _SecHandle *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rbp
  ADDRESS_FAMILY *v34; // rdi
  UCHAR v35; // al
  __int64 v36; // r11
  __int64 v37; // rdx
  int v38; // ecx
  __int16 v39; // r10
  __int64 *v40; // rax
  __int64 v41; // rdi
  UCHAR v42; // al
  __int64 v43; // r11
  __int64 v44; // r10
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-38h] BYREF
  WCHAR *pBuffer; // [rsp+90h] [rbp+8h] BYREF

  v5 = *(_QWORD *)(BugCheckParameter4 + 560);
  v6 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 304) + 24LL);
  v7 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL);
  *(_DWORD *)(v5 + 8) = 0;
  *(_QWORD *)(v5 + 24) = BugCheckParameter4;
  *(_QWORD *)(v5 + 168) = -1;
  *(_QWORD *)(BugCheckParameter4 + 536) = Smb2PreSendPacket;
  v8 = *(_DWORD *)(*(_QWORD *)(BugCheckParameter4 + 304) + 36LL);
  if ( v8 < 4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
        BugCheckParameter4);
    }
    *(_BYTE *)(BugCheckParameter4 + 474) = 1;
    Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 0);
    return 3221225485LL;
  }
  if ( *(_DWORD *)v6 == 1112364030 )
  {
    if ( v8 < 0x40 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4);
      }
      *(_BYTE *)(BugCheckParameter4 + 474) = 1;
      Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 2);
      return 3221225485LL;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDiiD(
        WPP_GLOBAL_Control->AttachedDevice,
        *(unsigned __int16 *)(v6 + 12),
        a3,
        BugCheckParameter4,
        *(unsigned __int16 *)(v6 + 12),
        *(_QWORD *)(v6 + 24),
        *(_QWORD *)(v6 + 40),
        *(_DWORD *)(v6 + 16));
    }
    if ( *(_WORD *)(v6 + 12) >= 0x14u )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4);
      }
      *(_BYTE *)(BugCheckParameter4 + 474) = 1;
      Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 3);
      return 3221225485LL;
    }
    if ( !*(_BYTE *)(*(_QWORD *)(BugCheckParameter4 + 96) + 510LL)
      && !(unsigned __int8)SrvAdminAllowAnonymousAccess(v9, a2, a3, a4)
      && *(_WORD *)(v6 + 12) >= 2u )
    {
      if ( Microsoft_Windows_SMBServerEnableBits < 0 )
      {
        v29 = *(__int64 **)(v5 + 32);
        v30 = (__int64)(v29 + 9);
        if ( v29 )
        {
          v33 = *v29;
        }
        else
        {
          v30 = 0;
          LOBYTE(v33) = 0;
        }
        v34 = (ADDRESS_FAMILY *)(*(_QWORD *)(BugCheckParameter4 + 96) + 216LL);
        v35 = SOCKADDR_SIZE(*v34);
        McTemplateK0qbr0hzr2ijj_EtwWriteTransfer(
          v38,
          v37,
          BugCheckParameter4 + 584,
          v35,
          (__int64)v34,
          v39,
          *(_QWORD *)(v36 + 368),
          v33,
          v30,
          v37);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4);
      }
      *(_BYTE *)(BugCheckParameter4 + 474) = 1;
      return 3221225485LL;
    }
    if ( *(_WORD *)(v6 + 4) != 64 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          18,
          WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4);
      }
      *(_BYTE *)(BugCheckParameter4 + 474) = 1;
      Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 4);
      return 3221225485LL;
    }
    v10 = *(unsigned __int16 *)(v6 + 12);
    v11 = *(unsigned __int16 *)(v7 + 44);
    if ( (_WORD)v10 )
    {
      if ( (_WORD)v11 == 0xFFFF || (_WORD)v11 == 767 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
            BugCheckParameter4);
        }
        *(_BYTE *)(BugCheckParameter4 + 474) = 1;
        Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 5);
        return 3221225485LL;
      }
    }
    else if ( (_WORD)v11 != 0xFFFF && (_WORD)v11 != 767 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4,
          v11);
      }
      *(_BYTE *)(BugCheckParameter4 + 474) = 1;
      Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 6);
      return 3221225485LL;
    }
    if ( (*(_BYTE *)(v7 + 49) & 2) == 0 || v10 > 0x11 || (v12 = 248576, !_bittest(&v12, v10)) )
    {
      v22 = *(_DWORD *)(BugCheckParameter4 + 404);
      if ( v22 > 0x11000 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            21,
            WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
            BugCheckParameter4,
            v22,
            69632);
        }
        *(_BYTE *)(BugCheckParameter4 + 474) = 1;
        Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 7);
        return 3221225485LL;
      }
    }
    if ( !*(_BYTE *)(BugCheckParameter4 + 472) && !*(_BYTE *)(BugCheckParameter4 + 473) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          22,
          WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4);
      }
      v20 = 772;
      v21 = 3221225626LL;
      goto LABEL_37;
    }
    *(_BYTE *)(v5 + 5) = (*(_DWORD *)(v6 + 16) & 0x20000000) != 0;
    *(_WORD *)(v5 + 12) = *(_WORD *)(v6 + 8);
    v13 = *(_DWORD *)(v6 + 16);
    if ( (v13 & 0x70) == 0 || (v14 = ((v13 >> 4) & 7) - 1, v14 > 2) )
      v14 = 2;
    *(_DWORD *)(v5 + 188) = v14;
    if ( (*(_DWORD *)(BugCheckParameter4 + 484) & 0x1000) != 0 )
    {
      if ( (*(_BYTE *)(v7 + 49) & 8) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
            BugCheckParameter4);
        }
        *(_BYTE *)(BugCheckParameter4 + 474) = 1;
        Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 8);
        return 3221225485LL;
      }
      v15 = *(_DWORD *)(v6 + 16);
      if ( (v15 & 8) != 0 )
      {
        *(_DWORD *)(v6 + 16) = v15 & 0xFFFFFFF7;
        *(_OWORD *)(v6 + 48) = 0;
      }
      *(_DWORD *)(v5 + 8) = 2;
      LOBYTE(a4) = 1;
      v16 = Smb2VerifySessionExEx(BugCheckParameter4, *(_QWORD *)(v6 + 40), v6, a4, 0, 0);
      if ( v16 >= 0 )
        goto LABEL_24;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4);
      }
      v20 = 830;
    }
    else
    {
      if ( (*(_BYTE *)(v6 + 16) & 8) != 0 )
      {
        if ( !*(_QWORD *)(v7 + 8) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              25,
              WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
              BugCheckParameter4);
          }
          Smb2SetError(
            BugCheckParameter4,
            3221225485LL,
            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\validate.c",
            847);
          Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 9);
          return 0;
        }
        if ( *(_WORD *)(v6 + 12) != 1 )
          goto LABEL_66;
        v23 = *(_DWORD *)(*(_QWORD *)(BugCheckParameter4 + 304) + 36LL);
        if ( v23 < 0x58 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              26,
              WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
              BugCheckParameter4,
              v23);
          }
          Smb2SetError(
            BugCheckParameter4,
            3221225485LL,
            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\validate.c",
            871);
          Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 10);
          return 0;
        }
        if ( (*(_BYTE *)(v6 + 66) & 1) != 0 )
          v24 = 1;
        else
LABEL_66:
          v24 = 0;
        LOBYTE(a4) = 1;
        v25 = Smb2VerifySessionExEx(BugCheckParameter4, *(_QWORD *)(v6 + 40), v6, a4, 0, v24);
        if ( v25 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              27,
              WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
              BugCheckParameter4);
          }
          Smb2SetError(
            BugCheckParameter4,
            (unsigned int)v25,
            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\validate.c",
            892);
          return 0;
        }
        if ( !*(_QWORD *)(v5 + 112) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              28,
              WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
              BugCheckParameter4);
          }
          Smb2SetError(
            BugCheckParameter4,
            3221225485LL,
            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\validate.c",
            906);
          Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 11);
          return 0;
        }
        v26 = *(struct _UNICODE_STRING *)(v6 + 48);
        *(_OWORD *)(v6 + 48) = 0;
        DestinationString = v26;
        v27 = *(_WORD *)(v6 + 12) != 1 || (*(_BYTE *)(v6 + 16) & 1) == 0;
        v28 = Smb2VerifySignature(BugCheckParameter4, &DestinationString);
        *(struct _UNICODE_STRING *)(v6 + 48) = DestinationString;
        if ( v28 < 0 )
        {
          *(_QWORD *)&DestinationString.Length = 0;
          DestinationString.Buffer = 0;
          pBuffer = 0;
          v31 = *(struct _SecHandle **)(v5 + 48);
          if ( v31
            && (v31[2].dwLower || v31[2].dwUpper)
            && QueryContextAttributesW(v31 + 2, 1u, &pBuffer) >= 0
            && pBuffer )
          {
            RtlInitUnicodeString(&DestinationString, pBuffer);
          }
          else
          {
            DestinationString = 0;
          }
          if ( v27 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                29,
                WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
                BugCheckParameter4);
            }
            if ( byte_14004C339 < 0 )
            {
              v40 = *(__int64 **)(v5 + 32);
              if ( v40 )
                v41 = *v40;
              else
                LOBYTE(v41) = 0;
              v42 = SOCKADDR_SIZE(*(_WORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 216LL));
              McTemplateK0hzr0hzr2qbr4i_EtwWriteTransfer(
                DestinationString.Length >> 1,
                v42,
                BugCheckParameter4 + 584,
                *(_WORD *)(v43 + 360) >> 1,
                *(_QWORD *)(v43 + 368),
                DestinationString.Length >> 1,
                (__int64)DestinationString.Buffer,
                v42,
                v44,
                v41);
            }
          }
          if ( pBuffer )
            FreeContextBuffer(pBuffer);
          Smb2SetError(
            BugCheckParameter4,
            (unsigned int)v28,
            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\validate.c",
            963);
          return 0;
        }
        *(_QWORD *)(BugCheckParameter4 + 536) = Smb2SignPacket;
        *(_DWORD *)(v5 + 8) = 1;
        goto LABEL_24;
      }
      v19 = *(_QWORD *)(v6 + 40);
      if ( !v19
        || *(_WORD *)(v6 + 12) == 1
        || (LOBYTE(a4) = 1, v16 = Smb2VerifySessionExEx(BugCheckParameter4, v19, v6, a4, 1, 0), v16 >= 0) )
      {
LABEL_24:
        if ( !*(_DWORD *)(BugCheckParameter4 + 480) )
        {
          if ( (*(_DWORD *)(BugCheckParameter4 + 484) & 0x40) != 0 )
          {
            v32 = *(_QWORD *)(BugCheckParameter4 + 416);
            if ( v32 )
              *(_DWORD *)(v32 + 484) |= 0x40u;
          }
          goto LABEL_26;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            31,
            WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
            BugCheckParameter4);
        }
        Smb2SetError(
          BugCheckParameter4,
          3221225760LL,
          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\validate.c",
          1000);
        return 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          30,
          WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
          BugCheckParameter4);
      }
      v20 = 984;
    }
    v21 = (unsigned int)v16;
LABEL_37:
    Smb2SetError(BugCheckParameter4, v21, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\validate.c", v20);
    return 0;
  }
  if ( *(_DWORD *)v6 == 1112364031 && *(_WORD *)(v7 + 44) == 0xFFFF )
  {
    *(_WORD *)(v5 + 14) = 0;
LABEL_26:
    v17 = Smb2ValidateRoutines[*(unsigned __int16 *)(v5 + 14)];
    if ( v17 )
      return ((__int64 (__fastcall *)(ULONG_PTR))v17)(BugCheckParameter4);
    else
      return Smb2ValidateNotImplemented(BugCheckParameter4);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_aea5a74431453b5fb009fb1719eaafa4_Traceguids,
      BugCheckParameter4);
  }
  *(_BYTE *)(BugCheckParameter4 + 474) = 1;
  Smb2LkmdTelCollectParsingFailureValidateHelper(v5, 1);
  return 3221225485LL;
}

```

## disassembly

```asm
0x140073ab0  mov     r11, rsp
0x140073ab3  push    rbx
0x140073ab4  push    rbp
0x140073ab5  push    rsi
0x140073ab6  push    rdi
0x140073ab7  push    r12
0x140073ab9  sub     rsp, 60h
0x140073abd  mov     rax, [rcx+130h]
0x140073ac4  mov     rbx, rcx
0x140073ac7  mov     rsi, [rcx+230h]
0x140073ace  mov     rdi, [rax+18h]
0x140073ad2  mov     rax, [rcx+60h]
0x140073ad6  mov     rbp, [rax+1F0h]
0x140073add  lea     rax, Smb2PreSendPacket
0x140073ae4  mov     dword ptr [rsi+8], 0
0x140073aeb  mov     [rsi+18h], rcx
0x140073aef  mov     qword ptr [rsi+0A8h], 0FFFFFFFFFFFFFFFFh
0x140073afa  mov     [rcx+218h], rax
0x140073b01  mov     rax, [rcx+130h]
0x140073b08  mov     ecx, [rax+24h]
0x140073b0b  cmp     ecx, 4
0x140073b0e  jb      loc_140073D73
0x140073b14  mov     eax, [rdi]
0x140073b16  mov     [r11+10h], r14
0x140073b1a  mov     [r11+18h], r15
0x140073b1e  cmp     eax, 424D53FEh
0x140073b23  jnz     loc_140073DAC
0x140073b29  cmp     ecx, 40h ; '@'
0x140073b2c  jb      loc_140073F22
0x140073b32  mov     rcx, cs:WPP_GLOBAL_Control
0x140073b39  lea     r12, WPP_GLOBAL_Control
0x140073b40  cmp     rcx, r12
0x140073b43  jz      short loc_140073B52
0x140073b45  test    dword ptr [rcx+2Ch], 800h
0x140073b4c  jnz     loc_14007410B
0x140073b52  cmp     word ptr [rdi+0Ch], 14h
0x140073b57  jnb     loc_140074147
0x140073b5d  mov     rax, [rbx+60h]
0x140073b61  cmp     byte ptr [rax+1FEh], 0
0x140073b68  jz      loc_140073E9C
0x140073b6e  cmp     word ptr [rdi+4], 40h ; '@'
0x140073b73  jnz     loc_140074010
0x140073b79  movzx   ecx, word ptr [rdi+0Ch]
0x140073b7d  mov     eax, 0FFFFh
0x140073b82  movzx   edx, word ptr [rbp+2Ch]
0x140073b86  test    cx, cx
0x140073b89  jz      loc_14009681A
0x140073b8f  cmp     dx, ax
0x140073b92  jz      loc_140073FE2
0x140073b98  mov     eax, 2FFh
0x140073b9d  cmp     dx, ax
0x140073ba0  jz      loc_140073FE2
0x140073ba6  test    byte ptr [rbp+31h], 2
0x140073baa  jz      loc_140073D31
0x140073bb0  cmp     ecx, 11h
0x140073bb3  ja      loc_140073D31
0x140073bb9  mov     eax, 3CB00h
0x140073bbe  bt      eax, ecx
0x140073bc1  jnb     loc_140073D31
0x140073bc7  cmp     byte ptr [rbx+1D8h], 0
0x140073bce  jz      loc_140096888
0x140073bd4  mov     eax, [rdi+10h]
0x140073bd7  shr     eax, 1Dh
0x140073bda  and     al, 1
0x140073bdc  mov     [rsi+5], al
0x140073bdf  movzx   eax, word ptr [rdi+8]
0x140073be3  mov     [rsi+0Ch], ax
0x140073be7  mov     eax, [rdi+10h]
0x140073bea  test    al, 70h
0x140073bec  jz      short loc_140073BFB
0x140073bee  shr     eax, 4
0x140073bf1  and     eax, 7
0x140073bf4  dec     eax
0x140073bf6  cmp     eax, 2
0x140073bf9  jbe     short loc_140073C00
0x140073bfb  mov     eax, 2
0x140073c00  mov     [rsi+0BCh], eax
0x140073c06  test    dword ptr [rbx+1E4h], 1000h
0x140073c10  jz      loc_140073CAF
0x140073c16  test    byte ptr [rbp+31h], 8
0x140073c1a  jz      loc_140074235
0x140073c20  mov     eax, [rdi+10h]
0x140073c23  test    al, 8
0x140073c25  jnz     loc_14007427A
0x140073c2b  mov     dword ptr [rsi+8], 2
0x140073c32  mov     r9b, 1
0x140073c35  mov     rdx, [rdi+28h]
0x140073c39  mov     r8, rdi
0x140073c3c  mov     byte ptr [rsp+88h+var_60], 0
0x140073c41  mov     rcx, rbx
0x140073c44  mov     byte ptr [rsp+88h+var_68], 0
0x140073c49  call    Smb2VerifySessionExEx
0x140073c4e  mov     edi, eax
0x140073c50  test    eax, eax
0x140073c52  js      loc_140073D03
0x140073c58  cmp     dword ptr [rbx+1E0h], 0
0x140073c5f  jnz     loc_14007403E
0x140073c65  mov     eax, [rbx+1E4h]
0x140073c6b  test    al, 40h
0x140073c6d  jnz     loc_1400744E3
0x140073c73  movzx   eax, word ptr [rsi+0Eh]
0x140073c77  lea     rcx, Smb2ValidateRoutines
0x140073c7e  mov     rax, ds:(Smb2ValidateRoutines - 14003F000h)[rcx+rax*8]
0x140073c82  mov     rcx, rbx; BugCheckParameter4
0x140073c85  test    rax, rax
0x140073c88  jz      loc_140073DD1
0x140073c8e  call    _guard_dispatch_icall
0x140073c93  mov     r14, [rsp+88h+arg_8]
0x140073c9b  mov     r15, [rsp+88h+arg_10]
0x140073ca3  add     rsp, 60h
0x140073ca7  pop     r12
0x140073ca9  pop     rdi
0x140073caa  pop     rsi
0x140073cab  pop     rbp
0x140073cac  pop     rbx
0x140073cad  retn
0x140073caf  test    byte ptr [rdi+10h], 8
0x140073cb3  jnz     loc_140073DDB
0x140073cb9  mov     rdx, [rdi+28h]
0x140073cbd  test    rdx, rdx
0x140073cc0  jz      short loc_140073C58
0x140073cc2  cmp     word ptr [rdi+0Ch], 1
0x140073cc7  jz      short loc_140073C58
0x140073cc9  mov     byte ptr [rsp+88h+var_60], 0
0x140073cce  mov     r9b, 1
0x140073cd1  mov     r8, rdi
0x140073cd4  mov     byte ptr [rsp+88h+var_68], 1
0x140073cd9  mov     rcx, rbx
0x140073cdc  call    Smb2VerifySessionExEx
0x140073ce1  mov     edi, eax
0x140073ce3  test    eax, eax
0x140073ce5  jns     loc_140073C58
0x140073ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x140073cf2  cmp     rcx, r12
0x140073cf5  jnz     loc_14007447B
0x140073cfb  mov     r9d, 3D8h
0x140073d01  jmp     short loc_140073D19
0x140073d03  mov     rcx, cs:WPP_GLOBAL_Control
0x140073d0a  cmp     rcx, r12
0x140073d0d  jnz     loc_14007428C
0x140073d13  mov     r9d, 33Eh
0x140073d19  mov     edx, edi
0x140073d1b  lea     r8, aOnecoreBaseFsR_18; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140073d22  mov     rcx, rbx
0x140073d25  call    _Smb2SetError
0x140073d2a  xor     eax, eax
0x140073d2c  jmp     loc_140073C93
0x140073d31  mov     r8d, [rbx+194h]
0x140073d38  cmp     r8d, 11000h
0x140073d3f  jbe     loc_140073BC7
0x140073d45  mov     rcx, cs:WPP_GLOBAL_Control
0x140073d4c  cmp     rcx, r12
0x140073d4f  jnz     loc_1400741F4
0x140073d55  mov     edx, 7
0x140073d5a  mov     byte ptr [rbx+1DAh], 1
0x140073d61  mov     rcx, rsi
0x140073d64  call    Smb2LkmdTelCollectParsingFailureValidateHelper
0x140073d69  mov     eax, 0C000000Dh
0x140073d6e  jmp     loc_140073C93
0x140073d73  mov     rcx, cs:WPP_GLOBAL_Control
0x140073d7a  lea     r12, WPP_GLOBAL_Control
0x140073d81  cmp     rcx, r12
0x140073d84  jnz     loc_14007406F
0x140073d8a  xor     edx, edx
0x140073d8c  mov     byte ptr [rbx+1DAh], 1
0x140073d93  mov     rcx, rsi
0x140073d96  call    Smb2LkmdTelCollectParsingFailureValidateHelper
0x140073d9b  mov     eax, 0C000000Dh
0x140073da0  add     rsp, 60h
0x140073da4  pop     r12
0x140073da6  pop     rdi
0x140073da7  pop     rsi
0x140073da8  pop     rbp
0x140073da9  pop     rbx
0x140073daa  retn
0x140073dac  cmp     eax, 424D53FFh
0x140073db1  jnz     loc_140073EE6
0x140073db7  mov     eax, 0FFFFh
0x140073dbc  cmp     [rbp+2Ch], ax
0x140073dc0  jnz     loc_140073EE6
0x140073dc6  xor     eax, eax
0x140073dc8  mov     [rsi+0Eh], ax
0x140073dcc  jmp     loc_140073C73
0x140073dd1  call    Smb2ValidateNotImplemented
0x140073dd6  jmp     loc_140073C93
0x140073ddb  cmp     qword ptr [rbp+8], 0
0x140073de0  jz      loc_1400742C0
0x140073de6  cmp     word ptr [rdi+0Ch], 1
0x140073deb  jnz     loc_140073F1B
0x140073df1  mov     rax, [rbx+130h]
0x140073df8  mov     r8d, [rax+24h]
0x140073dfc  cmp     r8d, 58h ; 'X'
0x140073e00  jb      loc_140074305
0x140073e06  test    byte ptr [rdi+42h], 1
0x140073e0a  jz      loc_140073F1B
0x140073e10  mov     al, 1
0x140073e12  mov     rdx, [rdi+28h]
0x140073e16  mov     r9b, 1
0x140073e19  mov     byte ptr [rsp+88h+var_60], al
0x140073e1d  mov     r8, rdi
0x140073e20  mov     rcx, rbx
0x140073e23  mov     byte ptr [rsp+88h+var_68], 0
0x140073e28  call    Smb2VerifySessionExEx
0x140073e2d  mov     ebp, eax
0x140073e2f  test    eax, eax
0x140073e31  js      loc_14007434F
0x140073e37  cmp     qword ptr [rsi+70h], 0
0x140073e3c  jz      loc_140074394
0x140073e42  movups  xmm0, xmmword ptr [rdi+30h]
0x140073e46  mov     ebp, 1
0x140073e4b  xorps   xmm1, xmm1
0x140073e4e  movups  xmmword ptr [rdi+30h], xmm1
0x140073e52  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x140073e57  cmp     bp, [rdi+0Ch]
0x140073e5b  jz      loc_1400743D9
0x140073e61  movzx   r14d, bpl
0x140073e65  lea     rdx, [rsp+88h+DestinationString]
0x140073e6a  mov     rcx, rbx
0x140073e6d  call    Smb2VerifySignature
0x140073e72  mov     r15d, eax
0x140073e75  movups  xmm0, xmmword ptr [rsp+88h+DestinationString.Length]
0x140073e7a  movups  xmmword ptr [rdi+30h], xmm0
0x140073e7e  test    eax, eax
0x140073e80  js      loc_140073F57
0x140073e86  lea     rax, Smb2SignPacket
0x140073e8d  mov     [rbx+218h], rax
0x140073e94  mov     [rsi+8], ebp
0x140073e97  jmp     loc_140073C58
0x140073e9c  call    cs:__imp_SrvAdminAllowAnonymousAccess
0x140073ea3  nop     dword ptr [rax+rax+00h]
0x140073ea8  test    al, al
0x140073eaa  jnz     loc_140073B6E
0x140073eb0  cmp     word ptr [rdi+0Ch], 2
0x140073eb5  jb      loc_140073B6E
0x140073ebb  cmp     cs:Microsoft_Windows_SMBServerEnableBits, al
0x140073ec1  jge     loc_1400967D6
0x140073ec7  mov     rcx, [rsi+20h]
0x140073ecb  xor     eax, eax
0x140073ecd  test    rcx, rcx
0x140073ed0  lea     rsi, [rcx+48h]
0x140073ed4  cmovz   rsi, rax
0x140073ed8  jz      loc_140096774
0x140073ede  mov     rbp, [rcx]
0x140073ee1  jmp     loc_140096776
0x140073ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x140073eed  lea     r12, WPP_GLOBAL_Control
0x140073ef4  cmp     rcx, r12
0x140073ef7  jnz     loc_1400740A3
0x140073efd  mov     edx, 1
0x140073f02  mov     byte ptr [rbx+1DAh], 1
0x140073f09  mov     rcx, rsi
0x140073f0c  call    Smb2LkmdTelCollectParsingFailureValidateHelper
0x140073f11  mov     eax, 0C000000Dh
0x140073f16  jmp     loc_140073C93
0x140073f1b  xor     al, al
0x140073f1d  jmp     loc_140073E12
0x140073f22  mov     rcx, cs:WPP_GLOBAL_Control
0x140073f29  lea     r12, WPP_GLOBAL_Control
0x140073f30  cmp     rcx, r12
0x140073f33  jnz     loc_1400740D7
0x140073f39  mov     edx, 2
0x140073f3e  mov     byte ptr [rbx+1DAh], 1
0x140073f45  mov     rcx, rsi
0x140073f48  call    Smb2LkmdTelCollectParsingFailureValidateHelper
0x140073f4d  mov     eax, 0C000000Dh
0x140073f52  jmp     loc_140073C93
0x140073f57  xor     eax, eax
0x140073f59  mov     qword ptr [rsp+88h+DestinationString.Length], rax
0x140073f5e  mov     [rsp+88h+DestinationString.Buffer], rax
0x140073f63  mov     [rsp+88h+pBuffer], rax
0x140073f6b  mov     rax, [rsi+30h]
0x140073f6f  test    rax, rax
0x140073f72  jz      short loc_140073FA1
0x140073f74  cmp     qword ptr [rax+20h], 0
0x140073f79  lea     rcx, [rax+20h]; phContext
0x140073f7d  jz      loc_1400743EB
0x140073f83  lea     r8, [rsp+88h+pBuffer]; pBuffer
0x140073f8b  mov     edx, ebp; ulAttribute
0x140073f8d  call    cs:__imp_QueryContextAttributesW
0x140073f94  nop     dword ptr [rax+rax+00h]
0x140073f99  test    eax, eax
0x140073f9b  jns     loc_1400743FB
0x140073fa1  xorps   xmm0, xmm0
0x140073fa4  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x140073fa9  test    r14b, r14b
0x140073fac  jnz     loc_140074425
0x140073fb2  mov     rcx, [rsp+88h+pBuffer]; pvContextBuffer
0x140073fba  test    rcx, rcx
0x140073fbd  jnz     loc_14007446A
0x140073fc3  mov     r9d, 3C3h
0x140073fc9  lea     r8, aOnecoreBaseFsR_18; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140073fd0  mov     edx, r15d
0x140073fd3  mov     rcx, rbx
0x140073fd6  call    _Smb2SetError
0x140073fdb  xor     eax, eax
0x140073fdd  jmp     loc_140073C93
0x140073fe2  mov     rcx, cs:WPP_GLOBAL_Control
0x140073fe9  cmp     rcx, r12
0x140073fec  jnz     loc_1400741C0
0x140073ff2  mov     edx, 5
  ... truncated ...
```
