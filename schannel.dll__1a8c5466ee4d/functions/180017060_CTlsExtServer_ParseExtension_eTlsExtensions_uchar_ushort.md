# CTlsExtServer::ParseExtension(eTlsExtensions,uchar *,ushort)

- ea: `0x180017060`
- end: `0x180017c7c`
- name: `?ParseExtension@CTlsExtServer@@UEAAKW4eTlsExtensions@@PEAEG@Z`
- size: `3100`
- prototype: `unsigned int __fastcall(__int64, unsigned __int16, unsigned __int8 *, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800166b0`

## callees

- `0x180005930`
- `0x18000dc60`
- `0x180017060`
- `0x1800214f0`
- `0x180021e64`
- `0x180030200`
- `0x1800319c0`
- `0x1800391b0`
- `0x18003a190`
- `0x180057c8c`
- `0x1800597b0`
- `0x180082388`
- `0x180082958`
- `0x1800829e4`
- `0x180082af8`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180017895`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180017895`

## pseudocode

```c
unsigned int __fastcall CTlsExtServer::ParseExtension(__int64 a1, unsigned __int16 a2, unsigned __int8 *a3, __int64 a4)
{
  unsigned int result; // eax
  unsigned int v7; // ecx
  int v8; // edi
  CCipherMill *v9; // rcx
  __int64 v10; // rdx
  __int64 *v11; // r8
  __int64 v12; // rax
  int v13; // ebx
  unsigned __int16 *v14; // rcx
  unsigned int v15; // edx
  __int64 v16; // rcx
  __int64 v17; // rax
  CCipherMill *v18; // rcx
  __int64 v19; // rdx
  int v20; // r8d
  __int64 v21; // rsi
  __int64 v22; // r14
  unsigned __int64 v23; // rcx
  size_t v24; // rbp
  unsigned __int16 *v25; // r13
  unsigned __int8 *v26; // rdi
  unsigned __int8 *v27; // r15
  unsigned int v28; // ebx
  unsigned __int16 *v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  unsigned __int16 MatchingProtectionProfile; // r14
  unsigned __int8 *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rax
  unsigned __int8 v36; // r14
  unsigned __int8 *v37; // r8
  unsigned __int8 v38; // bp
  _BYTE *v39; // rdx
  unsigned __int64 v40; // r9
  unsigned __int64 v41; // rax
  unsigned __int8 *v42; // rbx
  unsigned __int8 *v43; // rcx
  __int64 v44; // r13
  int v45; // ebp
  unsigned int v46; // ebp
  unsigned __int16 v47; // di
  unsigned int v48; // ebp
  char *v49; // r14
  __int64 v50; // rbx
  const void *v51; // rcx
  int v52; // eax
  void *Memory; // rax
  __int64 v54; // rax
  __int64 v55; // rcx
  unsigned int v56; // r8d
  unsigned int v57; // edi
  __int64 v58; // r15
  unsigned int v59; // ebp
  CCipherMill *v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // r9
  CCipherMill *v63; // rcx
  unsigned __int8 *v64; // r14
  char v65; // dl
  unsigned int v66; // edi
  __int64 v67; // rax
  __int64 v68; // rax
  unsigned int v69; // [rsp+30h] [rbp-78h] BYREF
  __int16 v70; // [rsp+38h] [rbp-70h] BYREF
  __int128 v71; // [rsp+3Ah] [rbp-6Eh]
  __int128 v72; // [rsp+4Ah] [rbp-5Eh]
  __int16 v73; // [rsp+5Ah] [rbp-4Eh]

  if ( !a3 && (_WORD)a4 )
    return -2146892963;
  if ( a2 > 0xFF01u )
    return 0;
  if ( a2 == 65281 )
  {
    v54 = *(_QWORD *)(a1 + 16);
    if ( *(_DWORD *)(v54 + 2136) && !*(_BYTE *)(v54 + 2273) )
    {
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_cd6f20d9ea0c3e340de51d24b577b520_Traceguids);
      LOBYTE(a4) = 40;
      CSslContext::SetErrorAndFatalAlert(*(_QWORD *)(a1 + 16), 1207, 2148074310LL, a4);
      v55 = *(_QWORD *)(a1 + 16);
      result = -2146892986;
      *(_DWORD *)(v55 + 92) = 96;
      *(_WORD *)(v55 + 120) = 10242;
      return result;
    }
    *(_BYTE *)(v54 + 2273) = 1;
    if ( !(_WORD)a4 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 66;
        goto LABEL_151;
      }
      return -2146893018;
    }
    v56 = *a3;
    v57 = (unsigned __int16)a4;
    if ( v56 + 1 != (unsigned __int16)a4 )
    {
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          WPP_cd6f20d9ea0c3e340de51d24b577b520_Traceguids,
          v56,
          (unsigned __int16)a4);
      }
      return -2146893018;
    }
    v58 = *(_QWORD *)(a1 + 16);
    v59 = *(_DWORD *)(v58 + 2136);
    if ( (_WORD)a4 == 1 )
    {
      v60 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_cd6f20d9ea0c3e340de51d24b577b520_Traceguids);
        v60 = WPP_GLOBAL_Control;
      }
      if ( !v59 )
        return 0;
      if ( v60 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v60 + 28) & 1) != 0 )
      {
        v61 = 69;
        v62 = v57;
LABEL_169:
        WPP_SF_dd(*((_QWORD *)v60 + 2), v61, WPP_cd6f20d9ea0c3e340de51d24b577b520_Traceguids, v62, v59);
      }
    }
    else
    {
      if ( v56 != v59 )
      {
        v60 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_182;
        v61 = 70;
        v62 = v56;
        goto LABEL_169;
      }
      v63 = WPP_GLOBAL_Control;
      v64 = a3 + 1;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_cd6f20d9ea0c3e340de51d24b577b520_Traceguids);
          v63 = WPP_GLOBAL_Control;
        }
        if ( v63 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_DWORD *)v63 + 7) & 0x800) != 0 )
          WPP_SF_(*((_QWORD *)v63 + 2), 72, WPP_cd6f20d9ea0c3e340de51d24b577b520_Traceguids);
      }
      v65 = 0;
      v66 = 0;
      if ( !v59 )
        return 0;
      do
      {
        v67 = v66++;
        v65 |= v64[v67] ^ *(_BYTE *)(v58 + v67 + 2097);
      }
      while ( v66 < v59 );
      if ( !v65 )
        return 0;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_cd6f20d9ea0c3e340de51d24b577b520_Traceguids);
    }
LABEL_182:
    LOBYTE(a4) = 40;
    CSslContext::SetErrorAndFatalAlert(*(_QWORD *)(a1 + 16), 1207, 2148074310LL, a4);
    v68 = *(_QWORD *)(a1 + 16);
    *(_DWORD *)(v68 + 92) = 96;
    *(_WORD *)(v68 + 120) = 10242;
    return -2146892986;
  }
  switch ( a2 )
  {
    case 0u:
      if ( (unsigned __int16)a4 < 2u || _byteswap_ushort(*(_WORD *)a3) < 3u )
        return 0;
      v43 = a3 + 2;
      v44 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 104LL);
      v45 = (unsigned __int16)a4 - 2;
      if ( (unsigned __int16)a4 == 2 )
        goto LABEL_139;
      while ( 2 )
      {
        v46 = v45 - 1;
        if ( v46 < 2 )
          return 0;
        v47 = _byteswap_ushort(*(_WORD *)(v43 + 1));
        if ( !v47 )
          return 0;
        v48 = v46 - 2;
        if ( v48 < v47 )
          return 0;
        v49 = (char *)(v43 + 3);
        if ( *v43 )
          goto LABEL_134;
        if ( v43 == (unsigned __int8 *)-3LL )
          return 0;
        v50 = *(_QWORD *)(a1 + 40);
        v51 = *(const void **)(v50 + 2664);
        if ( v51 )
        {
          v52 = *(unsigned __int16 *)(v50 + 2672);
          if ( (_WORD)v52 != v47 )
          {
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                62,
                WPP_4536224b51c63d9a1593beb928bc374a_Traceguids,
                v47,
                v52);
            }
            return 0;
          }
          if ( RtlCompareMemory(v51, v49, v47) != v47 )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v10 = 63;
              v11 = WPP_4536224b51c63d9a1593beb928bc374a_Traceguids;
              goto LABEL_24;
            }
            return 0;
          }
        }
        else
        {
          Memory = CSslContext::GetMemory(*(CSslContext **)(a1 + 40), v47, 1u);
          *(_QWORD *)(v50 + 2664) = Memory;
          if ( !Memory )
            return 0;
          memcpy_0(Memory, v49, v47);
          *(_WORD *)(v50 + 2672) = v47;
        }
LABEL_134:
        v45 = v48 - v47;
        if ( v45 )
        {
          v43 = (unsigned __int8 *)&v49[v47];
          continue;
        }
        break;
      }
LABEL_139:
      if ( (*(_DWORD *)(v44 + 220) & 0x100) != 0 )
        *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1856LL) |= 0x200000uLL;
      return 0;
    case 5u:
      if ( (_WORD)a4 && *a3 == 1 )
      {
        *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1856LL) |= 0x20000uLL;
        return 0;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        return 0;
      v10 = 57;
      v11 = WPP_cd6f20d9ea0c3e340de51d24b577b520_Traceguids;
      goto LABEL_24;
    case 6u:
      if ( !(_WORD)a4 )
        return -2146893018;
      v7 = *a3;
      if ( v7 != (unsigned __int16)a4 - 1 )
        return -2146893018;
      v8 = 0;
      if ( !*a3 )
        return 0;
      while ( a3[v8 + 1] != 64 )
      {
        if ( ++v8 >= v7 )
          return 0;
      }
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_cd6f20d9ea0c3e340de51d24b577b520_Traceguids);
      *(_BYTE *)(*(_QWORD *)(a1 + 16) + 2642LL) = 1;
      return 0;
    case 0xAu:
      return CTlsExtServer::ParseEllipticCurveExtension((CTlsExtServer *)a1, a3, (unsigned __int16)a4);
    case 0xDu:
      v12 = *(_QWORD *)(a1 + 16);
      if ( (*(_DWORD *)(v12 + 88) & 0x41400) == 0 )
        return 0;
      v71 = 0;
      v70 = 0;
      v72 = 0;
      v73 = 0;
      v69 = 0;
      if ( *(_BYTE *)(v12 + 2645) )
        return -2146893018;
      v13 = (unsigned __int16)a4;
      result = CTlsSignatureSuiteList::ParseSupportedSignatureAlgorithmsAndSet(
                 (CTlsSignatureSuiteList *)&v70,
                 a3,
                 (unsigned __int16)a4,
                 &v69);
      if ( result )
        return result;
      if ( v13 != v69 )
        return -2146893018;
      v14 = *(unsigned __int16 **)(a1 + 16);
      v14[1115] = 0;
      v14[1132] = 0;
      v15 = v14[1097];
      if ( v15 <= 0x10 )
      {
        v14[1115] = v15;
        v14[1132] = v14[1114];
        memcpy_0(v14 + 1116, v14 + 1098, 2LL * v15);
      }
      CTlsSignatureSuiteList::Restrict(
        (CTlsSignatureSuiteList *)(*(_QWORD *)(a1 + 16) + 2230LL),
        (const struct CTlsSignatureSuiteList *)&v70,
        *(_DWORD *)(*(_QWORD *)(a1 + 16) + 88LL));
      *(_BYTE *)(*(_QWORD *)(a1 + 16) + 2645LL) = 1;
      return 0;
    case 0xEu:
      v21 = *(_QWORD *)(a1 + 40);
      if ( !*(_BYTE *)(v21 + 1953) || !*(_QWORD *)(v21 + 2520) )
        return 0;
      if ( (unsigned __int16)a4 < 5u )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 60;
          goto LABEL_151;
        }
        return -2146893018;
      }
      v22 = _byteswap_ushort(*(_WORD *)a3);
      v23 = (unsigned __int16)(a4 - 2);
      if ( v23 < v22 + 1 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 61;
          goto LABEL_151;
        }
        return -2146893018;
      }
      v24 = a3[v22 + 2];
      v25 = (unsigned __int16 *)(a3 + 2);
      v26 = 0;
      v27 = 0;
      if ( !(_BYTE)v24 )
        goto LABEL_69;
      if ( (unsigned __int16)(v23 - v22 - 1) < (unsigned __int16)v24 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 62;
          goto LABEL_151;
        }
        return -2146893018;
      }
      v27 = &a3[v22 + 3];
LABEL_69:
      v28 = CSsl3TlsContext::ValidateProtectionProfiles(v25, v22, 1);
      if ( v28 )
        goto LABEL_74;
      v29 = *(unsigned __int16 **)(v21 + 2520);
      if ( !v29 )
        goto LABEL_73;
      if ( v27 )
      {
        if ( !(_BYTE)v24 )
          goto LABEL_73;
      }
      else if ( (_BYTE)v24 )
      {
        goto LABEL_73;
      }
      MatchingProtectionProfile = CSsl3TlsContext::FindMatchingProtectionProfile(v29 + 1, *v29, v25, v22);
      if ( !MatchingProtectionProfile )
      {
        CSsl3TlsContext::FreeSelectedSrtpParameters((CSsl3TlsContext *)v21);
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v10 = 66;
          v11 = WPP_4536224b51c63d9a1593beb928bc374a_Traceguids;
          goto LABEL_24;
        }
        return 0;
      }
      LOBYTE(v31) = 0;
      if ( (_BYTE)v24 && *(_BYTE *)(v21 + 2708) )
      {
        v33 = (unsigned __int8 *)(*(__int64 (__fastcall **)(__int64, size_t, __int64, __int64))(*(_QWORD *)v21 + 8LL))(
                                   v21,
                                   v24,
                                   v30,
                                   v31);
        v26 = v33;
        if ( !v33 )
          return 14;
        memcpy_0(v33, v27, v24);
        LOBYTE(v31) = v24;
      }
      v28 = CSsl3TlsContext::SetSelectedSrtpParameters((CSsl3TlsContext *)v21, MatchingProtectionProfile, v26, v31);
      if ( !v28 )
        return 0;
      if ( !v26 )
        goto LABEL_74;
      goto LABEL_86;
    case 0x10u:
      if ( !*(_QWORD *)(*(_QWORD *)(a1 + 16) + 2504LL) )
        return 0;
      if ( (unsigned __int16)a4 >= 4u )
      {
        v20 = _byteswap_ushort(*(_WORD *)a3);
        if ( v20 == (unsigned __int16)a4 - 2 )
          return CSsl3TlsServerContext::SetMutuallySupportedApplicationProtocols(
                   *(CSsl3TlsServerContext **)(a1 + 40),
                   a3 + 2,
                   v20);
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 59;
          goto LABEL_151;
        }
      }
      else
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 58;
          goto LABEL_151;
        }
      }
      return -2146893018;
    case 0x17u:
      if ( CSslGlobals::m_fDisableServerExtendedMS || (*(_DWORD *)(*(_QWORD *)(a1 + 40) + 88LL) & 0x51540) == 0 )
      {
        if ( CTelemetryContext::s_IsTelemetryGloballyInitialized )
          *(_WORD *)(*(_QWORD *)(a1 + 16) + 222LL) |= 0x10u;
      }
      else
      {
        *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1856LL) |= 0x8000000uLL;
      }
      return 0;
    case 0x18u:
      v21 = *(_QWORD *)(a1 + 40);
      v34 = *(_QWORD *)(v21 + 2536);
      if ( !v34 )
        return 0;
      if ( (unsigned __int16)a4 < 4u )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 63;
LABEL_151:
          WPP_SF_(*((_QWORD *)v18 + 2), v19, WPP_cd6f20d9ea0c3e340de51d24b577b520_Traceguids);
          return -2146893018;
        }
        return -2146893018;
      }
      v35 = a3[2];
      v36 = *a3;
      if ( (unsigned __int16)(a4 - 3) < (unsigned __int16)v35 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 64;
          goto LABEL_151;
        }
        return -2146893018;
      }
      if ( a3[2] )
      {
        v37 = a3 + 3;
        if ( v37 )
        {
          if ( *(_BYTE *)v34 == v36 && (v38 = a3[1], *(_BYTE *)(v34 + 1) == v38) )
          {
            v39 = (_BYTE *)(v34 + 4);
            v40 = v34 + 4 + *(unsigned __int16 *)(v34 + 2);
            v41 = (unsigned __int64)&v37[v35];
            if ( v34 + 4 >= v40 )
            {
              v42 = v37;
            }
            else
            {
              while ( 1 )
              {
                v42 = v37;
                if ( (unsigned __int64)v37 < v41 )
                  break;
LABEL_104:
                if ( (unsigned __int64)++v39 >= v40 )
                  goto LABEL_107;
              }
              while ( *v39 != *v42 )
              {
                if ( (unsigned __int64)++v42 >= v41 )
                  goto LABEL_104;
              }
            }
LABEL_107:
            if ( v39 != (_BYTE *)v40 )
            {
              v26 = (unsigned __int8 *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 8LL))(v21, 1);
              if ( !v26 )
                return 14;
              *v26 = *v42;
              v28 = CSsl3TlsContext::SetSelectedTBParameters((CSsl3TlsContext *)v21, v36, v38, v26, 1u);
              if ( v28 )
              {
LABEL_86:
                (*(void (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v21 + 16LL))(v21, v26);
                return v28;
              }
              return 0;
            }
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v10 = 68;
              v11 = WPP_4536224b51c63d9a1593beb928bc374a_Traceguids;
LABEL_24:
              WPP_SF_(*((_QWORD *)v9 + 2), v10, v11);
            }
          }
          else
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v10 = 67;
              v11 = WPP_4536224b51c63d9a1593beb928bc374a_Traceguids;
              goto LABEL_24;
            }
          }
          return 0;
        }
      }
LABEL_73:
      v28 = 87;
LABEL_74:
      result = v28;
      break;
    case 0x23u:
      v16 = *(_QWORD *)(a1 + 16);
      v17 = *(_QWORD *)(v16 + 1856);
      if ( (v17 & 0x800) != 0 )
      {
        if ( (_WORD)a4 )
        {
          *(_DWORD *)(v16 + 2704) = (unsigned __int16)a4;
          *(_QWORD *)(v16 + 2696) = a3;
        }
        else
        {
          *(_QWORD *)(v16 + 1856) = v17 | 0x400000;
        }
      }
      return 0;
    default:
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180017060  push    rsi
0x180017062  sub     rsp, 0A0h
0x180017069  mov     rax, cs:__security_cookie
0x180017070  xor     rax, rsp
0x180017073  mov     [rsp+0A8h+var_48], rax
0x180017078  mov     r10, r8
0x18001707b  mov     rsi, rcx
0x18001707e  test    r8, r8
0x180017081  jnz     short loc_180017093
0x180017083  test    r9w, r9w
0x180017087  jz      short loc_180017093
0x180017089  mov     eax, 8009035Dh
0x18001708e  jmp     loc_180017204
0x180017093  mov     [rsp+0A8h+arg_8], rbx
0x18001709b  mov     [rsp+0A8h+var_10], rbp
0x1800170a3  mov     [rsp+0A8h+var_18], rdi
0x1800170ab  mov     [rsp+0A8h+var_20], r12
0x1800170b3  mov     [rsp+0A8h+var_28], r13
0x1800170bb  movzx   eax, dx
0x1800170be  mov     [rsp+0A8h+var_30], r14
0x1800170c3  mov     [rsp+0A8h+var_38], r15
0x1800170c8  cmp     eax, 0FF01h
0x1800170cd  ja      def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x1800170d3  jz      loc_180017980
0x1800170d9  cmp     eax, 23h; switch 36 cases
0x1800170dc  ja      def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x1800170e2  lea     rdx, __ImageBase
0x1800170e9  movzx   eax, ds:(byte_180017C58 - 180000000h)[rdx+rax]
0x1800170f1  mov     ecx, ds:(jpt_1800170FB - 180000000h)[rdx+rax*4]
0x1800170f8  add     rcx, rdx
0x1800170fb  jmp     rcx; switch jump
0x1800170fd  test    r9w, r9w; jumptable 00000001800170FB case 6
0x180017101  jz      loc_180017A84
0x180017107  movzx   ecx, byte ptr [r8]
0x18001710b  movzx   eax, r9w
0x18001710f  dec     eax
0x180017111  cmp     ecx, eax
0x180017113  jnz     loc_180017A84
0x180017119  xor     edi, edi
0x18001711b  test    ecx, ecx
0x18001711d  jz      def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x180017123  mov     eax, edi
0x180017125  cmp     byte ptr [rax+r8+1], 40h ; '@'
0x18001712b  jz      short loc_180017138
0x18001712d  inc     edi
0x18001712f  cmp     edi, ecx
0x180017131  jb      short loc_180017123
0x180017133  jmp     def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x180017138  mov     rcx, cs:WPP_GLOBAL_Control
0x18001713f  lea     rbx, WPP_GLOBAL_Control
0x180017146  cmp     rcx, rbx
0x180017149  jz      short loc_180017166
0x18001714b  test    byte ptr [rcx+1Ch], 4
0x18001714f  jz      short loc_180017166
0x180017151  mov     rcx, [rcx+10h]
0x180017155  lea     r8, WPP_cd6f20d9ea0c3e340de51d24b577b520_Traceguids
0x18001715c  mov     edx, 37h ; '7'
0x180017161  call    WPP_SF_
0x180017166  mov     rax, [rsi+10h]
0x18001716a  mov     byte ptr [rax+0A52h], 1
0x180017171  jmp     short def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x180017173  movzx   r8d, r9w; jumptable 00000001800170FB case 10
0x180017177  mov     rdx, r10; unsigned __int8 *
0x18001717a  mov     rcx, rsi; this
0x18001717d  call    ?ParseEllipticCurveExtension@CTlsExtServer@@AEAAKPEAEK@Z; CTlsExtServer::ParseEllipticCurveExtension(uchar *,ulong)
0x180017182  jmp     short loc_1800171D2
0x180017184  cmp     r9w, 1; jumptable 00000001800170FB case 5
0x180017189  jb      short loc_1800171A2
0x18001718b  cmp     byte ptr [r8], 1
0x18001718f  jnz     short loc_1800171A2
0x180017191  mov     rax, [rsi+10h]
0x180017195  or      qword ptr [rax+740h], 20000h
0x1800171a0  jmp     short def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x1800171a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171a9  lea     rbx, WPP_GLOBAL_Control
0x1800171b0  cmp     rcx, rbx
0x1800171b3  jz      short def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x1800171b5  test    byte ptr [rcx+1Ch], 2
0x1800171b9  jz      short def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x1800171bb  mov     edx, 39h ; '9'
0x1800171c0  lea     r8, WPP_cd6f20d9ea0c3e340de51d24b577b520_Traceguids
0x1800171c7  mov     rcx, [rcx+10h]
0x1800171cb  call    WPP_SF_
0x1800171d0  xor     eax, eax; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x1800171d2  mov     r14, [rsp+0A8h+var_30]
0x1800171d7  mov     r13, [rsp+0A8h+var_28]
0x1800171df  mov     r12, [rsp+0A8h+var_20]
0x1800171e7  mov     rdi, [rsp+0A8h+var_18]
0x1800171ef  mov     rbp, [rsp+0A8h+var_10]
0x1800171f7  mov     rbx, [rsp+0A8h+arg_8]
0x1800171ff  mov     r15, [rsp+0A8h+var_38]
0x180017204  mov     rcx, [rsp+0A8h+var_48]
0x180017209  xor     rcx, rsp; StackCookie
0x18001720c  call    __security_check_cookie
0x180017211  add     rsp, 0A0h
0x180017218  pop     rsi
0x180017219  retn
0x18001721a  mov     rax, [rsi+10h]; jumptable 00000001800170FB case 13
0x18001721e  test    dword ptr [rax+58h], 41400h
0x180017225  jz      short def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x180017227  xor     edi, edi
0x180017229  xorps   xmm0, xmm0
0x18001722c  movups  [rsp+0A8h+var_6E], xmm0
0x180017231  mov     [rsp+0A8h+var_70], di
0x180017236  movups  [rsp+0A8h+var_5E], xmm0
0x18001723b  mov     [rsp+0A8h+var_4E], di
0x180017240  mov     [rsp+0A8h+var_78], edi
0x180017244  cmp     [rax+0A55h], dil
0x18001724b  jnz     loc_180017A84
0x180017251  movzx   ebx, r9w
0x180017255  lea     rcx, [rsp+0A8h+var_70]; this
0x18001725a  mov     r8d, ebx; unsigned int
0x18001725d  lea     r9, [rsp+0A8h+var_78]; unsigned int *
0x180017262  mov     rdx, r10; unsigned __int8 *
0x180017265  call    ?ParseSupportedSignatureAlgorithmsAndSet@CTlsSignatureSuiteList@@QEAAKPEAEKPEAK@Z; CTlsSignatureSuiteList::ParseSupportedSignatureAlgorithmsAndSet(uchar *,ulong,ulong *)
0x18001726a  test    eax, eax
0x18001726c  jnz     loc_1800171D2
0x180017272  cmp     ebx, [rsp+0A8h+var_78]
0x180017276  jnz     loc_180017A84
0x18001727c  mov     rcx, [rsi+10h]
0x180017280  mov     [rcx+8B6h], di
0x180017287  mov     [rcx+8D8h], di
0x18001728e  movzx   edx, word ptr [rcx+892h]
0x180017295  cmp     edx, 10h
0x180017298  ja      short loc_1800172C8
0x18001729a  mov     [rcx+8B6h], dx
0x1800172a1  mov     r8d, edx
0x1800172a4  movzx   eax, word ptr [rcx+8B4h]
0x1800172ab  lea     rdx, [rcx+894h]; Src
0x1800172b2  mov     [rcx+8D8h], ax
0x1800172b9  add     r8, r8; Size
0x1800172bc  add     rcx, 8B8h; void *
0x1800172c3  call    memcpy_0
0x1800172c8  mov     r8, [rsi+10h]
0x1800172cc  lea     rdx, [rsp+0A8h+var_70]; struct CTlsSignatureSuiteList *
0x1800172d1  lea     rcx, [r8+8B6h]; this
0x1800172d8  mov     r8d, [r8+58h]; unsigned int
0x1800172dc  call    ?Restrict@CTlsSignatureSuiteList@@QEAAEPEBV1@K@Z; CTlsSignatureSuiteList::Restrict(CTlsSignatureSuiteList const *,ulong)
0x1800172e1  mov     rax, [rsi+10h]
0x1800172e5  mov     byte ptr [rax+0A55h], 1
0x1800172ec  jmp     def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x1800172f1  mov     rcx, [rsi+10h]; jumptable 00000001800170FB case 35
0x1800172f5  mov     rax, [rcx+740h]
0x1800172fc  bt      rax, 0Bh
0x180017301  jnb     def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x180017307  test    r9w, r9w
0x18001730b  jz      short loc_180017323
0x18001730d  movzx   eax, r9w
0x180017311  mov     [rcx+0A90h], eax
0x180017317  mov     [rcx+0A88h], r10
0x18001731e  jmp     def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x180017323  bts     rax, 16h
0x180017328  mov     [rcx+740h], rax
0x18001732f  jmp     def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x180017334  mov     rax, [rsi+10h]; jumptable 00000001800170FB case 16
0x180017338  cmp     qword ptr [rax+9C8h], 0
0x180017340  jz      def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x180017346  cmp     r9w, 4
0x18001734b  jnb     short loc_180017378
0x18001734d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017354  lea     rbx, WPP_GLOBAL_Control
0x18001735b  cmp     rcx, rbx
0x18001735e  jz      loc_180017A84
0x180017364  test    byte ptr [rcx+1Ch], 1
0x180017368  jz      loc_180017A84
0x18001736e  mov     edx, 3Ah ; ':'
0x180017373  jmp     loc_180017A22
0x180017378  movzx   eax, byte ptr [r8]
0x18001737c  movzx   ecx, byte ptr [r8+1]
0x180017381  shl     ax, 8
0x180017385  or      cx, ax
0x180017388  movzx   eax, r9w
0x18001738c  sub     eax, 2
0x18001738f  movzx   r8d, cx; unsigned __int16
0x180017393  cmp     r8d, eax
0x180017396  jz      short loc_1800173C3
0x180017398  mov     rcx, cs:WPP_GLOBAL_Control
0x18001739f  lea     rbx, WPP_GLOBAL_Control
0x1800173a6  cmp     rcx, rbx
0x1800173a9  jz      loc_180017A84
0x1800173af  test    byte ptr [rcx+1Ch], 1
0x1800173b3  jz      loc_180017A84
0x1800173b9  mov     edx, 3Bh ; ';'
0x1800173be  jmp     loc_180017A22
0x1800173c3  mov     rcx, [rsi+28h]; this
0x1800173c7  lea     rdx, [r10+2]; unsigned __int8 *
0x1800173cb  call    ?SetMutuallySupportedApplicationProtocols@CSsl3TlsServerContext@@QEAAKQEAEG@Z; CSsl3TlsServerContext::SetMutuallySupportedApplicationProtocols(uchar * const,ushort)
0x1800173d0  jmp     loc_1800171D2
0x1800173d5  cmp     cs:?m_fDisableServerExtendedMS@CSslGlobals@@2HA, 0; jumptable 00000001800170FB case 23
0x1800173dc  jnz     short loc_1800173FF
0x1800173de  mov     rax, [rsi+28h]
0x1800173e2  test    dword ptr [rax+58h], 51540h
0x1800173e9  jz      short loc_1800173FF
0x1800173eb  mov     rax, [rsi+10h]
0x1800173ef  or      qword ptr [rax+740h], 8000000h
0x1800173fa  jmp     def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x1800173ff  cmp     cs:?s_IsTelemetryGloballyInitialized@CTelemetryContext@@1_NA, 0; bool CTelemetryContext::s_IsTelemetryGloballyInitialized
0x180017406  jz      def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x18001740c  mov     rax, [rsi+10h]
0x180017410  or      word ptr [rax+0DEh], 10h
0x180017418  jmp     def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x18001741d  mov     rsi, [rsi+28h]; jumptable 00000001800170FB case 14
0x180017421  cmp     byte ptr [rsi+7A1h], 0
0x180017428  jz      def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x18001742e  cmp     qword ptr [rsi+9D8h], 0
0x180017436  jz      def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x18001743c  cmp     r9w, 5
0x180017441  jnb     short loc_18001746E
0x180017443  mov     rcx, cs:WPP_GLOBAL_Control
0x18001744a  lea     rbx, WPP_GLOBAL_Control
0x180017451  cmp     rcx, rbx
0x180017454  jz      loc_180017A84
0x18001745a  test    byte ptr [rcx+1Ch], 1
0x18001745e  jz      loc_180017A84
0x180017464  mov     edx, 3Ch ; '<'
0x180017469  jmp     loc_180017A22
0x18001746e  movzx   eax, byte ptr [r8]
0x180017472  sub     r9w, 2
0x180017477  movzx   ecx, byte ptr [r8+1]
0x18001747c  shl     ax, 8
0x180017480  or      cx, ax
0x180017483  movzx   r14d, cx
0x180017487  movzx   ecx, r9w
0x18001748b  lea     rax, [r14+1]
0x18001748f  cmp     rcx, rax
0x180017492  jnb     short loc_1800174BF
0x180017494  mov     rcx, cs:WPP_GLOBAL_Control
0x18001749b  lea     rbx, WPP_GLOBAL_Control
0x1800174a2  cmp     rcx, rbx
0x1800174a5  jz      loc_180017A84
0x1800174ab  test    byte ptr [rcx+1Ch], 1
0x1800174af  jz      loc_180017A84
0x1800174b5  mov     edx, 3Dh ; '='
0x1800174ba  jmp     loc_180017A22
0x1800174bf  movzx   ebp, byte ptr [r14+r8+2]
0x1800174c5  lea     r13, [r8+2]
0x1800174c9  xor     edi, edi
0x1800174cb  mov     r15d, edi
0x1800174ce  test    bpl, bpl
0x1800174d1  jz      short loc_180017511
0x1800174d3  sub     cx, r14w
0x1800174d7  dec     cx
0x1800174da  cmp     cx, bp
0x1800174dd  jnb     short loc_18001750A
0x1800174df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174e6  lea     rbx, WPP_GLOBAL_Control
0x1800174ed  cmp     rcx, rbx
0x1800174f0  jz      loc_180017A84
0x1800174f6  test    byte ptr [rcx+1Ch], 1
0x1800174fa  jz      loc_180017A84
0x180017500  mov     edx, 3Eh ; '>'
0x180017505  jmp     loc_180017A22
0x18001750a  lea     r15, [r13+1]
0x18001750e  add     r15, r14
0x180017511  mov     r8d, 1; int
0x180017517  movzx   edx, r14w; unsigned __int16
0x18001751b  mov     rcx, r13; unsigned __int16 *
0x18001751e  call    ?ValidateProtectionProfiles@CSsl3TlsContext@@KAKQEAGGH@Z; CSsl3TlsContext::ValidateProtectionProfiles(ushort * const,ushort,int)
0x180017523  mov     ebx, eax
0x180017525  test    eax, eax
0x180017527  jnz     short loc_180017544
0x180017529  mov     rdx, [rsi+9D8h]
0x180017530  test    rdx, rdx
0x180017533  jz      short loc_18001753F
0x180017535  test    r15, r15
0x180017538  jnz     short loc_18001754B
0x18001753a  test    bpl, bpl
0x18001753d  jz      short loc_180017550
0x18001753f  mov     ebx, 57h ; 'W'
0x180017544  mov     eax, ebx
0x180017546  jmp     loc_1800171D2
0x18001754b  test    bpl, bpl
0x18001754e  jz      short loc_18001753F
0x180017550  lea     rcx, [rdx+2]; unsigned __int16 *
0x180017554  movzx   r9d, r14w; unsigned __int16
0x180017558  movzx   edx, word ptr [rdx]; unsigned __int16
0x18001755b  mov     r8, r13; unsigned __int16 *
0x18001755e  call    ?FindMatchingProtectionProfile@CSsl3TlsContext@@KAGQEAGG0G@Z; CSsl3TlsContext::FindMatchingProtectionProfile(ushort * const,ushort,ushort * const,ushort)
0x180017563  movzx   r14d, ax
0x180017567  test    ax, ax
0x18001756a  jnz     short loc_1800175A6
0x18001756c  mov     rcx, rsi; this
0x18001756f  call    ?FreeSelectedSrtpParameters@CSsl3TlsContext@@IEAAXXZ; CSsl3TlsContext::FreeSelectedSrtpParameters(void)
0x180017574  mov     rcx, cs:WPP_GLOBAL_Control
0x18001757b  lea     rbx, WPP_GLOBAL_Control
0x180017582  cmp     rcx, rbx
0x180017585  jz      def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x18001758b  test    byte ptr [rcx+1Ch], 2
0x18001758f  jz      def_1800170FB; jumptable 00000001800170FB default case, cases 1-4,7-9,11,12,15,17-22,25-34
0x180017595  mov     edx, 42h ; 'B'
0x18001759a  lea     r8, WPP_4536224b51c63d9a1593beb928bc374a_Traceguids
0x1800175a1  jmp     loc_1800171C7
0x1800175a6  xor     r9b, r9b
0x1800175a9  test    bpl, bpl
0x1800175ac  jz      short loc_1800175E7
0x1800175ae  cmp     [rsi+0A94h], dil
0x1800175b5  jz      short loc_1800175E7
0x1800175b7  mov     rax, [rsi]
0x1800175ba  mov     rdx, rbp
0x1800175bd  mov     rcx, rsi
  ... truncated ...
```
