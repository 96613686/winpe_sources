# CTls13ExtServer::ParseExtension(eTlsExtensions,uchar *,ushort)

- ea: `0x1800166b0`
- end: `0x18001704e`
- name: `?ParseExtension@CTls13ExtServer@@UEAAKW4eTlsExtensions@@PEAEG@Z`
- size: `2462`
- prototype: `unsigned int __fastcall(__int64, unsigned __int16, unsigned __int8 *, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting`

## callees

- `0x18000d280`
- `0x180014240`
- `0x1800165a4`
- `0x1800166b0`
- `0x180017060`
- `0x180017c84`
- `0x180018ad0`
- `0x1800214f0`
- `0x180021da8`
- `0x18004bca4`
- `0x180057c8c`
- `0x18005a160`
- `0x18005f1e4`
- `0x1800704e0`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016d82`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016d82`
- `ntdll!RtlInitUnicodeString` at `0x18008b50e`
- `ntdll!RtlInitUnicodeString` at `0x18008b51b`
- `ntdll!RtlInitUnicodeString` at `0x18008b57a`
- `ntdll!RtlInitUnicodeString` at `0x18008b587`
- `ntdll!RtlInitUnicodeString` at `0x18008b50e`
- `ntdll!RtlInitUnicodeString` at `0x18008b51b`
- `ntdll!RtlInitUnicodeString` at `0x18008b57a`
- `ntdll!RtlInitUnicodeString` at `0x18008b587`

## pseudocode

```c
unsigned int __fastcall CTls13ExtServer::ParseExtension(
        __int64 a1,
        unsigned __int16 a2,
        unsigned __int8 *a3,
        __int64 a4)
{
  __int64 v6; // r8
  unsigned __int16 v7; // si
  unsigned int v8; // eax
  __int16 v10; // ax
  __int64 v11; // r15
  __int64 v12; // rax
  const struct TlsVersion near *const *v13; // rcx
  unsigned __int8 *v14; // r14
  int v15; // edx
  unsigned __int8 *j; // r10
  unsigned int v17; // r12d
  int v18; // r8d
  __int16 v19; // ax
  bool v20; // zf
  int v21; // esi
  unsigned int result; // eax
  unsigned __int16 v23; // cx
  unsigned __int16 v24; // si
  __int64 v25; // rdi
  __int64 v26; // rax
  __int64 v27; // rcx
  const WCHAR *v28; // rdx
  const WCHAR *v29; // r15
  __int64 v30; // rax
  int v31; // ebx
  unsigned int v32; // r12d
  __int64 v33; // rdx
  int v34; // r15d
  __int64 v35; // r12
  int v36; // ebx
  __int16 v37; // ax
  _BYTE *v38; // r14
  _BYTE *i; // rcx
  __int64 v40; // rdi
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rax
  const WCHAR *v44; // rdx
  const WCHAR *v45; // r15
  int v46; // ebx
  unsigned int v47; // r12d
  __int64 v48; // rdx
  int v49; // r15d
  __int64 v50; // r12
  unsigned __int8 *v51; // r14
  __int64 v52; // rdi
  void *v53; // rcx
  HLOCAL v54; // rax
  __int64 v55; // rax
  __int64 v56; // rcx
  int v57; // ebx
  int v58; // edi
  __int64 v59; // r12
  bool v60; // dl
  unsigned __int64 v61; // r10
  __int64 v62; // rax
  unsigned int v63; // r10d
  struct kexch *KeyExchangeInfo; // rax
  int v65; // r10d
  __int64 v66; // r8
  __int64 v67; // r8
  struct _UNICODE_STRING v68; // [rsp+A0h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-70h] BYREF
  char v70[8]; // [rsp+C0h] [rbp-60h] BYREF
  unsigned __int64 v71; // [rsp+C8h] [rbp-58h]

  v6 = *(unsigned __int8 *)(a1 + 24);
  v7 = a4;
  v8 = v6 | (a2 << 8);
  if ( v8 > 0x2D01 )
  {
    if ( v8 != 13057 )
    {
      if ( v8 == 12545 )
      {
        if ( (_WORD)a4 )
          return -2146893048;
        *(_BYTE *)(*(_QWORD *)(a1 + 48) + 3210LL) = 1;
        return 0;
      }
LABEL_34:
      if ( a2 != 57 && a2 != 0xFFA5
        || (result = CTls13Context::RetrieveGenericExtension(*(_QWORD *)(a1 + 48) + 2720LL, a2, v6, a3, (_WORD)a4)) == 0 )
      {
        if ( *(_BYTE *)(a1 + 24) == 1 )
          return CTlsExtServer::ParseExtension(a1, a2, a3, v7);
        else
          return 0;
      }
      return result;
    }
    if ( a3 && (unsigned __int16)a4 >= 2u )
    {
      v23 = _byteswap_ushort(*(_WORD *)a3);
      if ( v23 )
      {
        if ( v23 >= 2u )
        {
          v24 = a4 - 2;
          if ( v23 == (_WORD)a4 - 2 )
          {
            v51 = a3 + 2;
            if ( (_WORD)a4 != 2 && !v51 )
              return 87;
            v52 = *(_QWORD *)(a1 + 48);
            v36 = 0;
            v53 = *(void **)(v52 + 3200);
            if ( v53 )
            {
              SPExternalFree(v53);
              *(_QWORD *)(v52 + 3200) = 0;
              *(_WORD *)(v52 + 3208) = 0;
            }
            if ( v24 )
            {
              if ( *(_DWORD *)(v52 + 92) != 71 || v24 >= 4u && *(_DWORD *)(v52 + 16) == ((*v51 << 8) | v51[1]) )
              {
                if ( LsaTable )
                  v54 = (HLOCAL)(*(__int64 (__fastcall **)(_QWORD))(LsaTable + 40))(v24);
                else
                  v54 = LocalAlloc(0x40u, v24);
                *(_QWORD *)(v52 + 3200) = v54;
                if ( !v54 )
                  return 14;
                memcpy_0(v54, v51, v24);
                result = 0;
                *(_WORD *)(v52 + 3208) = v24;
                return result;
              }
              return -2146893018;
            }
            return v36;
          }
        }
      }
      else if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 92LL) != 71 )
      {
        return 0;
      }
      v25 = *(_QWORD *)(a1 + 16);
      v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 352LL))(v25);
      v27 = *(_QWORD *)(v25 + 1848);
      if ( !*(_WORD *)(v27 + 34) )
      {
        *(_WORD *)(v27 + 34) = 1202;
        *(_DWORD *)(v27 + 36) = -2146893048;
      }
      *(_WORD *)(v25 + 120) = 12802;
      v28 = &Class;
      v29 = &Class;
      if ( v26 )
        v29 = (const WCHAR *)v26;
      v30 = *(_QWORD *)(v25 + 104);
      v31 = 0;
      if ( v30 )
      {
        v32 = *(_DWORD *)(v30 + 276);
        v28 = (const WCHAR *)(v30 + 280);
      }
      else
      {
        v32 = 0;
      }
      if ( (g_dwEventLogging & 4) != 0 )
      {
        v68 = 0;
        DestinationString = 0;
        RtlInitUnicodeString(&v68, v28);
        RtlInitUnicodeString(&DestinationString, v29);
        SchEventWrite(&SSLEVENT_GENERATE_FATAL_ALERT, L"duddu", v32, &v68, 50, 1202, &DestinationString);
      }
      memset_0(v70, 0, 0x680u);
      v33 = *(_QWORD *)(v25 + 8);
      if ( v33 )
        v31 = *(_DWORD *)(v33 + 28);
      v34 = *(unsigned __int16 *)(v25 + 34);
      v35 = *(_QWORD *)(v25 + 1856);
      HIDWORD(v71) = *(_DWORD *)(v25 + 16);
      LODWORD(v71) = v31;
      if ( v33 )
      {
        v67 = *(_QWORD *)(v25 + 112);
        if ( v67 )
          CSchannelTelemetryContext::LogKeyExchange(
            (CSchannelTelemetryContext *)(v25 + 144),
            *(_DWORD *)(v33 + 32),
            *(_DWORD *)(*(_QWORD *)(v67 + 40) + 8LL));
      }
      if ( CTelemetryContext::s_IsTelemetryGloballyInitialized )
      {
        *(_DWORD *)(v25 + 188) = HIDWORD(v71);
        *(_BYTE *)(v25 + 260) = 50;
        *(_DWORD *)(v25 + 256) = -2146893048;
        *(_DWORD *)(v25 + 264) = 1202;
        *(_DWORD *)(v25 + 184) = v31;
        *(_DWORD *)(v25 + 192) = v34;
        *(_QWORD *)(v25 + 280) = v35;
        *(_BYTE *)(v25 + 169) = 1;
      }
      CSchannelTelemetryContext::LogDebugTraceHandshakeInfo((CSchannelTelemetryContext *)(v25 + 144), L"Fatal Error");
      return -2146893048;
    }
LABEL_123:
    LOBYTE(a4) = 50;
    CSslContext::SetErrorAndFatalAlert(*(_QWORD *)(a1 + 16), 1202, 2148074248LL, a4);
    return -2146893048;
  }
  switch ( v8 )
  {
    case 0x2D01u:
      if ( a3 )
      {
        if ( (_WORD)a4 )
        {
          v37 = *a3;
          if ( (_BYTE)v37 )
          {
            if ( v37 == (_WORD)a4 - 1 )
            {
              v38 = a3 + 1;
              for ( i = v38; i < &v38[(unsigned __int16)(a4 - 1)]; ++i )
              {
                if ( *v38 == 1 )
                {
                  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e525a0d56b3f34a8cc938d0b0b1313e9_Traceguids);
                  }
                  *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1856LL) |= 0x2000000uLL;
                  return 0;
                }
              }
              if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_e525a0d56b3f34a8cc938d0b0b1313e9_Traceguids);
              }
              return 0;
            }
          }
        }
      }
      goto LABEL_123;
    case 0x2901u:
      return CTls13ExtServer::ParsePreSharedKeyExtension((CTls13ExtServer *)a1, a3, a4);
    case 0x50Bu:
      return CTlsExtServer::ParseExtension(a1, a2, a3, a4);
  }
  if ( v8 != 11009 )
    goto LABEL_34;
  if ( !a3 || !(_WORD)a4 || (v10 = *a3, (unsigned __int8)v10 < 2u) || (v10 & 1) != 0 || v10 != (_WORD)a4 - 1 )
  {
    LOBYTE(a4) = 50;
    CSslContext::SetErrorAndFatalAlert(*(_QWORD *)(a1 + 16), 1202, 2148074248LL, a4);
    return -2146893048;
  }
  v11 = *(_QWORD *)(a1 + 16);
  v12 = *(_QWORD *)(v11 + 104);
  if ( !v12 )
  {
    v55 = *(_QWORD *)(v11 + 1848);
    v21 = 1359;
    if ( !*(_WORD *)(v55 + 34) )
    {
      *(_WORD *)(v55 + 34) = 1202;
      *(_DWORD *)(v55 + 36) = 1359;
    }
    memset_0(v70, 0, 0x680u);
    v56 = *(_QWORD *)(v11 + 8);
    if ( v56 )
      v57 = *(_DWORD *)(v56 + 28);
    else
      v57 = 0;
    v58 = *(unsigned __int16 *)(v11 + 34);
    v59 = *(_QWORD *)(v11 + 1856);
    v60 = CTelemetryContext::s_IsTelemetryGloballyInitialized;
    HIDWORD(v71) = *(_DWORD *)(v11 + 16);
    LODWORD(v71) = v57;
    if ( v56 )
    {
      v62 = *(_QWORD *)(v11 + 112);
      if ( v62 )
      {
        if ( !CTelemetryContext::s_IsTelemetryGloballyInitialized )
          return v21;
        v63 = *(_DWORD *)(v56 + 32);
        *(_DWORD *)(v11 + 200) = *(_DWORD *)(*(_QWORD *)(v62 + 40) + 8LL);
        if ( v63 == 43522 || v63 == 41984 )
        {
          KeyExchangeInfo = GetKeyExchangeInfo(v63);
          if ( KeyExchangeInfo )
          {
            *(_DWORD *)(v11 + 204) = *((_DWORD *)KeyExchangeInfo + 8);
            *(_DWORD *)(v11 + 208) = *((_DWORD *)KeyExchangeInfo + 10);
            if ( v65 == 43522 )
              *(_DWORD *)(v11 + 212) = *((_DWORD *)KeyExchangeInfo + 12);
          }
        }
      }
    }
    if ( v60 )
    {
      v61 = HIDWORD(v71);
      *(_DWORD *)(v11 + 188) = HIDWORD(v71);
      *(_DWORD *)(v11 + 256) = 1359;
      *(_DWORD *)(v11 + 264) = 1202;
      *(_DWORD *)(v11 + 184) = v57;
      *(_DWORD *)(v11 + 192) = v58;
      *(_QWORD *)(v11 + 280) = v59;
      *(_BYTE *)(v11 + 169) = 1;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SSSdiiDDDDDddiDDd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11 + 304,
          v11 + 816,
          *(_DWORD *)(v11 + 176),
          *(_QWORD *)(v11 + 272),
          v59,
          v57,
          v61,
          v58,
          *(_DWORD *)(v11 + 196),
          *(_DWORD *)(v11 + 200),
          *(_WORD *)(v11 + 220),
          *(_WORD *)(v11 + 222),
          *(_QWORD *)(v11 + 248),
          79,
          *(_BYTE *)(v11 + 260),
          178);
    }
    return v21;
  }
  v13 = &TlsVersions;
  v14 = a3 + 1;
  while ( v13 < (const struct TlsVersion near *const *)WPP_85d23bd63ce93039b989ce8bab889993_Traceguids )
  {
    v15 = *(_DWORD *)(v12 + 216) & *(_DWORD *)v13 & 0x40051555;
    if ( v15 )
    {
      for ( j = v14; j < &v14[(unsigned __int16)(a4 - 1)]; j += 2 )
      {
        v17 = *((unsigned __int16 *)v13 + 2);
        v18 = (*j << 8) | j[1];
        if ( v18 == v17 )
        {
          *(_DWORD *)(v11 + 88) = v15;
          if ( (v15 & 0x3FFC) != 0 && (v15 & 0xF0000) != 0 )
          {
            v19 = 0;
          }
          else if ( (v15 & 0xC0000) != 0 )
          {
            v19 = -259;
          }
          else if ( (v15 & 0x30000) != 0 )
          {
            v19 = -257;
          }
          else if ( (v15 & 0x3000) != 0 )
          {
            v19 = 772;
          }
          else if ( (v15 & 0xC00) != 0 )
          {
            v19 = 771;
          }
          else
          {
            v19 = 768;
            if ( (v15 & 0x300) != 0 )
            {
              v19 = 770;
            }
            else if ( (v15 & 0xC0) != 0 )
            {
              v19 = 769;
            }
            else if ( (v15 & 0x30) == 0 )
            {
              v19 = 0;
              if ( (v15 & 0xC) != 0 )
                v19 = 2;
            }
          }
          v20 = !CTelemetryContext::s_IsTelemetryGloballyInitialized;
          *(_WORD *)(v11 + 34) = v19;
          *(_DWORD *)(*(_QWORD *)(a1 + 16) + 36LL) = v18;
          if ( !v20 )
            *(_DWORD *)(*(_QWORD *)(a1 + 16) + 196LL) = v18;
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e525a0d56b3f34a8cc938d0b0b1313e9_Traceguids, v17);
          }
          *(_BYTE *)(a1 + 35) = 1;
          return 0;
        }
      }
    }
    ++v13;
  }
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e525a0d56b3f34a8cc938d0b0b1313e9_Traceguids);
  v40 = *(_QWORD *)(a1 + 16);
  v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 352LL))(v40);
  v42 = *(_QWORD *)(v40 + 1848);
  if ( !*(_WORD *)(v42 + 34) )
  {
    *(_WORD *)(v42 + 34) = 1202;
    *(_DWORD *)(v42 + 36) = -2146893007;
  }
  v43 = *(_QWORD *)(v40 + 104);
  v44 = &Class;
  *(_WORD *)(v40 + 120) = 17922;
  v45 = &Class;
  if ( v41 )
    v45 = (const WCHAR *)v41;
  v46 = 0;
  if ( v43 )
  {
    v47 = *(_DWORD *)(v43 + 276);
    v44 = (const WCHAR *)(v43 + 280);
  }
  else
  {
    v47 = 0;
  }
  if ( (g_dwEventLogging & 4) != 0 )
  {
    DestinationString = 0;
    v68 = 0;
    RtlInitUnicodeString(&DestinationString, v44);
    RtlInitUnicodeString(&v68, v45);
    SchEventWrite(&SSLEVENT_GENERATE_FATAL_ALERT, L"duddu", v47, &DestinationString, 70, 1202, &v68);
  }
  memset_0(v70, 0, 0x680u);
  v48 = *(_QWORD *)(v40 + 8);
  if ( v48 )
    v46 = *(_DWORD *)(v48 + 28);
  v49 = *(unsigned __int16 *)(v40 + 34);
  v50 = *(_QWORD *)(v40 + 1856);
  HIDWORD(v71) = *(_DWORD *)(v40 + 16);
  LODWORD(v71) = v46;
  if ( v48 )
  {
    v66 = *(_QWORD *)(v40 + 112);
    if ( v66 )
      CSchannelTelemetryContext::LogKeyExchange(
        (CSchannelTelemetryContext *)(v40 + 144),
        *(_DWORD *)(v48 + 32),
        *(_DWORD *)(*(_QWORD *)(v66 + 40) + 8LL));
  }
  if ( CTelemetryContext::s_IsTelemetryGloballyInitialized )
  {
    *(_DWORD *)(v40 + 188) = HIDWORD(v71);
    *(_BYTE *)(v40 + 260) = 70;
    *(_DWORD *)(v40 + 256) = -2146893007;
    *(_DWORD *)(v40 + 264) = 1202;
    *(_DWORD *)(v40 + 184) = v46;
    *(_DWORD *)(v40 + 192) = v49;
    *(_QWORD *)(v40 + 280) = v50;
    *(_BYTE *)(v40 + 169) = 1;
  }
  CSchannelTelemetryContext::LogDebugTraceHandshakeInfo((CSchannelTelemetryContext *)(v40 + 144), L"Fatal Error");
  return -2146893007;
}

```

## disassembly

```asm
0x1800166b0  push    rbp
0x1800166b2  push    rbx
0x1800166b3  push    rsi
0x1800166b4  push    rdi
0x1800166b5  push    r12
0x1800166b7  push    r14
0x1800166b9  push    r15
0x1800166bb  lea     rbp, [rsp-620h]
0x1800166c3  sub     rsp, 740h
0x1800166ca  movzx   ebx, dx
0x1800166cd  mov     r14, r8
0x1800166d0  movzx   r8d, byte ptr [rcx+18h]
0x1800166d5  mov     eax, ebx
0x1800166d7  shl     eax, 8
0x1800166da  movzx   esi, r9w
0x1800166de  or      eax, r8d
0x1800166e1  mov     rdi, rcx
0x1800166e4  cmp     eax, 2D01h
0x1800166e9  ja      loc_180016851
0x1800166ef  jz      loc_1800169E9
0x1800166f5  cmp     eax, 2901h
0x1800166fa  jz      loc_1800168A8
0x180016700  cmp     eax, 50Bh
0x180016705  jz      loc_180016CAD
0x18001670b  cmp     eax, 2B01h
0x180016710  jnz     loc_180016863
0x180016716  test    r14, r14
0x180016719  jz      loc_180016DC7
0x18001671f  test    r9w, r9w
0x180016723  jz      loc_180016DC7
0x180016729  movzx   eax, byte ptr [r14]
0x18001672d  cmp     al, 2
0x18001672f  jb      loc_180016DC7
0x180016735  test    al, 1
0x180016737  jnz     loc_180016DC7
0x18001673d  dec     si
0x180016740  cmp     ax, si
0x180016743  jnz     loc_180016DC7
0x180016749  mov     r15, [rcx+10h]
0x18001674d  mov     rax, [r15+68h]
0x180016751  test    rax, rax
0x180016754  jz      loc_180016BDC
0x18001675a  mov     r11d, [rax+0D8h]
0x180016761  lea     rcx, ?TlsVersions@@3QBUTlsVersion@@B; TlsVersion const near * const TlsVersions
0x180016768  inc     r14
0x18001676b  lea     rbx, WPP_85d23bd63ce93039b989ce8bab889993_Traceguids
0x180016772  cmp     rcx, rbx
0x180016775  jnb     loc_180016A71
0x18001677b  mov     edx, [rcx]
0x18001677d  and     edx, r11d
0x180016780  and     edx, 40051555h
0x180016786  jz      loc_180016D69
0x18001678c  movzx   r9d, si
0x180016790  mov     r10, r14
0x180016793  add     r9, r14
0x180016796  cmp     r10, r9
0x180016799  jnb     loc_180016D69
0x18001679f  movzx   eax, byte ptr [r10]
0x1800167a3  movzx   r8d, byte ptr [r10+1]
0x1800167a8  movzx   r12d, word ptr [rcx+4]
0x1800167ad  shl     eax, 8
0x1800167b0  or      r8d, eax
0x1800167b3  cmp     r8d, r12d
0x1800167b6  jnz     loc_180016E35
0x1800167bc  test    edx, 3FFCh
0x1800167c2  mov     [r15+58h], edx
0x1800167c6  setnz   cl
0x1800167c9  test    edx, 0F0000h
0x1800167cf  setnz   al
0x1800167d2  xor     ebx, ebx
0x1800167d4  test    al, cl
0x1800167d6  jnz     loc_180016DF1
0x1800167dc  test    edx, 0C0000h
0x1800167e2  jnz     loc_180016DF9
0x1800167e8  test    edx, 30000h
0x1800167ee  jnz     loc_180016DE7
0x1800167f4  test    edx, 3000h
0x1800167fa  jnz     loc_180016A67
0x180016800  test    edx, 0C00h
0x180016806  jz      loc_180016DAB
0x18001680c  mov     eax, 303h
0x180016811  cmp     cs:?s_IsTelemetryGloballyInitialized@CTelemetryContext@@1_NA, bl; bool CTelemetryContext::s_IsTelemetryGloballyInitialized
0x180016817  mov     [r15+22h], ax
0x18001681c  mov     rax, [rdi+10h]
0x180016820  mov     [rax+24h], r8d
0x180016824  jnz     loc_180016E5B
0x18001682a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016831  lea     rax, WPP_GLOBAL_Control
0x180016838  cmp     rcx, rax
0x18001683b  jz      short loc_180016847
0x18001683d  test    byte ptr [rcx+1Ch], 4
0x180016841  jnz     loc_180016E6B
0x180016847  mov     byte ptr [rdi+23h], 1
0x18001684b  mov     esi, ebx
0x18001684d  mov     eax, esi
0x18001684f  jmp     short loc_180016896
0x180016851  cmp     eax, 3301h
0x180016856  jz      short loc_1800168B6
0x180016858  cmp     eax, 3101h
0x18001685d  jz      loc_1800169CE
0x180016863  cmp     ebx, 39h ; '9'
0x180016866  jz      loc_180016E03
0x18001686c  mov     eax, 0FFA5h
0x180016871  cmp     bx, ax
0x180016874  jz      loc_180016E03
0x18001687a  cmp     byte ptr [rdi+18h], 1
0x18001687e  jnz     loc_180016F75
0x180016884  movzx   r9d, si
0x180016888  mov     r8, r14
0x18001688b  movzx   edx, bx
0x18001688e  mov     rcx, rdi
0x180016891  call    ?ParseExtension@CTlsExtServer@@UEAAKW4eTlsExtensions@@PEAEG@Z; CTlsExtServer::ParseExtension(eTlsExtensions,uchar *,ushort)
0x180016896  add     rsp, 740h
0x18001689d  pop     r15
0x18001689f  pop     r14
0x1800168a1  pop     r12
0x1800168a3  pop     rdi
0x1800168a4  pop     rsi
0x1800168a5  pop     rbx
0x1800168a6  pop     rbp
0x1800168a7  retn
0x1800168a8  movzx   r8d, si; unsigned __int16
0x1800168ac  mov     rdx, r14; unsigned __int8 *
0x1800168af  call    ?ParsePreSharedKeyExtension@CTls13ExtServer@@AEAAKPEAEG@Z; CTls13ExtServer::ParsePreSharedKeyExtension(uchar *,ushort)
0x1800168b4  jmp     short loc_180016896
0x1800168b6  test    r14, r14
0x1800168b9  jz      loc_180016D8D
0x1800168bf  cmp     si, 2
0x1800168c3  jb      loc_180016D8D
0x1800168c9  movzx   ecx, byte ptr [r14]
0x1800168cd  movzx   eax, byte ptr [r14+1]
0x1800168d2  shl     cx, 8
0x1800168d6  or      cx, ax
0x1800168d9  jz      loc_180016F7C
0x1800168df  cmp     cx, 2
0x1800168e3  jb      short loc_1800168F2
0x1800168e5  sub     si, 2
0x1800168e9  cmp     cx, si
0x1800168ec  jz      loc_180016B65
0x1800168f2  mov     rdi, [rdi+10h]
0x1800168f6  mov     rcx, rdi
0x1800168f9  mov     rax, [rdi]
0x1800168fc  mov     rax, [rax+160h]
0x180016903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016908  mov     rcx, [rdi+738h]
0x18001690f  mov     esi, 80090308h
0x180016914  mov     r14d, 4B2h
0x18001691a  cmp     word ptr [rcx+22h], 0
0x18001691f  jnz     short loc_180016929
0x180016921  mov     [rcx+22h], r14w
0x180016926  mov     [rcx+24h], esi
0x180016929  test    rax, rax
0x18001692c  mov     word ptr [rdi+78h], 3202h
0x180016932  lea     rdx, Class
0x180016939  mov     r15, rdx
0x18001693c  cmovnz  r15, rax
0x180016940  mov     rax, [rdi+68h]
0x180016944  xor     ebx, ebx
0x180016946  test    rax, rax
0x180016949  jz      loc_180016D61
0x18001694f  mov     r12d, [rax+114h]
0x180016956  lea     rdx, [rax+118h]; SourceString
0x18001695d  test    cs:?g_dwEventLogging@@3KA, 4; ulong g_dwEventLogging
0x180016964  jnz     loc_18008B568
0x18001696a  xor     edx, edx; Val
0x18001696c  lea     rcx, [rbp+650h+var_6B0]; void *
0x180016970  mov     r8d, 680h; Size
0x180016976  call    memset_0
0x18001697b  mov     rdx, [rdi+8]
0x18001697f  test    rdx, rdx
0x180016982  jz      short loc_180016987
0x180016984  mov     ebx, [rdx+1Ch]
0x180016987  mov     eax, [rdi+10h]
0x18001698a  movzx   r15d, word ptr [rdi+22h]
0x18001698f  mov     r12, [rdi+740h]
0x180016996  mov     dword ptr [rbp+650h+var_6A8+4], eax
0x180016999  mov     dword ptr [rbp+650h+var_6A8], ebx
0x18001699c  test    rdx, rdx
0x18001699f  jnz     loc_180016FD9
0x1800169a5  cmp     cs:?s_IsTelemetryGloballyInitialized@CTelemetryContext@@1_NA, 0; bool CTelemetryContext::s_IsTelemetryGloballyInitialized
0x1800169ac  lea     rcx, [rdi+90h]; this
0x1800169b3  jnz     loc_180017002
0x1800169b9  lea     rdx, aFatalError; "Fatal Error"
0x1800169c0  call    ?LogDebugTraceHandshakeInfo@CSchannelTelemetryContext@@QEAAXQEAG@Z; CSchannelTelemetryContext::LogDebugTraceHandshakeInfo(ushort * const)
0x1800169c5  mov     ebx, esi
0x1800169c7  mov     eax, ebx
0x1800169c9  jmp     loc_180016896
0x1800169ce  test    si, si
0x1800169d1  jnz     loc_180017044
0x1800169d7  mov     rax, [rcx+30h]
0x1800169db  xor     ebx, ebx
0x1800169dd  mov     byte ptr [rax+0C8Ah], 1
0x1800169e4  jmp     loc_18001684B
0x1800169e9  test    r14, r14
0x1800169ec  jz      loc_180016D8D
0x1800169f2  test    si, si
0x1800169f5  jz      loc_180016D8D
0x1800169fb  movzx   eax, byte ptr [r14]
0x1800169ff  cmp     al, 1
0x180016a01  jb      loc_180016D8D
0x180016a07  dec     si
0x180016a0a  cmp     ax, si
0x180016a0d  jnz     loc_180016D8D
0x180016a13  inc     r14
0x180016a16  movzx   eax, si
0x180016a19  mov     rcx, r14
0x180016a1c  add     rax, r14
0x180016a1f  cmp     rcx, rax
0x180016a22  jnb     loc_180016F39
0x180016a28  cmp     byte ptr [r14], 1
0x180016a2c  jnz     loc_180016F17
0x180016a32  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a39  lea     rax, WPP_GLOBAL_Control
0x180016a40  cmp     rcx, rax
0x180016a43  jz      short loc_180016A4F
0x180016a45  test    byte ptr [rcx+1Ch], 4
0x180016a49  jnz     loc_180016F1F
0x180016a4f  mov     rax, [rdi+10h]
0x180016a53  or      qword ptr [rax+740h], 2000000h
0x180016a5e  xor     ebx, ebx
0x180016a60  mov     eax, ebx
0x180016a62  jmp     loc_180016896
0x180016a67  mov     eax, 304h
0x180016a6c  jmp     loc_180016811
0x180016a71  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a78  lea     rax, WPP_GLOBAL_Control
0x180016a7f  cmp     rcx, rax
0x180016a82  jnz     loc_180016E88
0x180016a88  mov     rdi, [rdi+10h]
0x180016a8c  mov     rcx, rdi
0x180016a8f  mov     rax, [rdi]
0x180016a92  mov     rax, [rax+160h]
0x180016a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a9e  mov     rcx, rax
0x180016aa1  mov     esi, 80090331h
0x180016aa6  mov     rax, [rdi+738h]
0x180016aad  mov     r14d, 4B2h
0x180016ab3  cmp     word ptr [rax+22h], 0
0x180016ab8  jnz     short loc_180016AC2
0x180016aba  mov     [rax+22h], r14w
0x180016abf  mov     [rax+24h], esi
0x180016ac2  mov     rax, [rdi+68h]
0x180016ac6  lea     rdx, Class
0x180016acd  test    rcx, rcx
0x180016ad0  mov     word ptr [rdi+78h], 4602h
0x180016ad6  mov     r15, rdx
0x180016ad9  cmovnz  r15, rcx
0x180016add  xor     ebx, ebx
0x180016adf  test    rax, rax
0x180016ae2  jz      loc_180016D72
0x180016ae8  mov     r12d, [rax+114h]
0x180016aef  lea     rdx, [rax+118h]; SourceString
0x180016af6  test    cs:?g_dwEventLogging@@3KA, 4; ulong g_dwEventLogging
0x180016afd  jnz     loc_18008B4FC
0x180016b03  xor     edx, edx; Val
0x180016b05  lea     rcx, [rbp+650h+var_6B0]; void *
0x180016b09  mov     r8d, 680h; Size
0x180016b0f  call    memset_0
0x180016b14  mov     rdx, [rdi+8]
0x180016b18  test    rdx, rdx
0x180016b1b  jz      short loc_180016B20
0x180016b1d  mov     ebx, [rdx+1Ch]
0x180016b20  mov     eax, [rdi+10h]
0x180016b23  movzx   r15d, word ptr [rdi+22h]
0x180016b28  mov     r12, [rdi+740h]
0x180016b2f  mov     dword ptr [rbp+650h+var_6A8+4], eax
0x180016b32  mov     dword ptr [rbp+650h+var_6A8], ebx
0x180016b35  test    rdx, rdx
0x180016b38  jnz     loc_180016EAC
0x180016b3e  cmp     cs:?s_IsTelemetryGloballyInitialized@CTelemetryContext@@1_NA, 0; bool CTelemetryContext::s_IsTelemetryGloballyInitialized
0x180016b45  lea     rcx, [rdi+90h]; this
0x180016b4c  jnz     loc_180016ED5
0x180016b52  lea     rdx, aFatalError; "Fatal Error"
0x180016b59  call    ?LogDebugTraceHandshakeInfo@CSchannelTelemetryContext@@QEAAXQEAG@Z; CSchannelTelemetryContext::LogDebugTraceHandshakeInfo(ushort * const)
0x180016b5e  mov     eax, esi
0x180016b60  jmp     loc_180016896
0x180016b65  add     r14, 2
0x180016b69  test    si, si
0x180016b6c  jz      short loc_180016B77
0x180016b6e  test    r14, r14
0x180016b71  jz      loc_180016F91
0x180016b77  mov     rdi, [rdi+30h]
0x180016b7b  xor     ebx, ebx
0x180016b7d  mov     rcx, [rdi+0C80h]; void *
0x180016b84  test    rcx, rcx
0x180016b87  jnz     loc_180016F9B
0x180016b8d  test    si, si
0x180016b90  jz      loc_1800169C7
0x180016b96  cmp     dword ptr [rdi+5Ch], 47h ; 'G'
0x180016b9a  jz      loc_180016FB3
0x180016ba0  mov     rax, cs:LsaTable
0x180016ba7  movzx   r15d, si
0x180016bab  test    rax, rax
0x180016bae  jz      loc_180016D7A
0x180016bb4  mov     rax, [rax+28h]
0x180016bb8  movzx   ecx, si
0x180016bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bc0  mov     [rdi+0C80h], rax
0x180016bc7  test    rax, rax
0x180016bca  jnz     loc_180016CBD
  ... truncated ...
```
