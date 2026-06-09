# KspSetKeyPropertyInternal(unsigned __int64,unsigned __int64,ushort const *,uchar *,ulong,ulong)

- ea: `0x180025ff0`
- end: `0x18002704c`
- name: `?KspSetKeyPropertyInternal@@YAJ_K0PEBGPEAEKK@Z`
- size: `4188`
- prototype: `int(unsigned __int64, unsigned __int64, const unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002af90`

## callees

- `0x18000a3c8`
- `0x18000a408`
- `0x18000d2a8`
- `0x180011fd8`
- `0x1800135dc`
- `0x180013734`
- `0x180013aac`
- `0x180013e10`
- `0x180014070`
- `0x180019eb8`
- `0x18001a59c`
- `0x18001b6f8`
- `0x180025ff0`
- `0x18003af5c`
- `0x18003afc0`
- `0x18003bf9c`
- `0x18003c20e`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x18002616c`
- `ncrypt!NCryptDeleteKey` at `0x18002616c`
- `ncrypt!NCryptFinalizeKey` at `0x180026f5a`
- `ncrypt!NCryptFinalizeKey` at `0x180026f5a`
- `ncrypt!NCryptImportKey` at `0x180026e93`
- `ncrypt!NCryptImportKey` at `0x180026e93`
- `ncrypt!NCryptSetProperty` at `0x180026f10`
- `ncrypt!NCryptSetProperty` at `0x180026f10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KspSetKeyPropertyInternal(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        DWORD a5,
        unsigned int a6)
{
  __int64 v10; // r12
  DWORD cbData; // r15d
  unsigned int v12; // r12d
  PVOID v13; // rcx
  unsigned int Handle; // esi
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v19; // rcx
  _QWORD *v20; // rcx
  int v21; // edx
  __int64 v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rcx
  _QWORD *v36; // rcx
  int v37; // edx
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rdi
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rdi
  __int64 v46; // rcx
  __int64 v47; // rcx
  unsigned __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  unsigned int phKey; // [rsp+20h] [rbp-58h]
  __int64 v58; // [rsp+40h] [rbp-38h] BYREF
  __int64 v59; // [rsp+48h] [rbp-30h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+50h] [rbp-28h] BYREF
  void **v61; // [rsp+58h] [rbp-20h] BYREF
  __int64 v62; // [rsp+60h] [rbp-18h]
  int pbInput; // [rsp+C0h] [rbp+48h] BYREF

  v10 = 0;
  v58 = 0;
  v59 = 0;
  hKey = 0;
  pbInput = 3;
  v61 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v62 = 0;
  if ( !a1
    || !a2
    || !a3
    || ((cbData = a5, !a4) || !a5)
    && wcscmp_0(a3, L"SmartCardKeyCertificate")
    && wcscmp_0(a3, L"Use Context")
    && wcscmp_0(a3, L"SmartCardPin")
    && wcscmp_0(a3, L"SmartCardSecurePin") )
  {
    WppTraceIndent(a1, 2);
    Handle = -2146893785;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 298, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, 2148073511LL);
    }
    goto LABEL_22;
  }
  v12 = a6;
  if ( (a6 & 0x3FFFFFA0) != 0 )
  {
    WppTraceIndent(a1, 2);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        299,
        (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        (_DWORD)WPP_pszIndent,
        v12);
    }
    WppTraceIndent(v13, 2);
    Handle = -2146893815;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    v16 = 300;
LABEL_19:
    v17 = Handle;
    goto LABEL_20;
  }
  Handle = HtGetHandle(a1, 3, &v58);
  if ( Handle )
  {
    WppTraceIndent(v19, 2);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    v21 = 301;
    goto LABEL_32;
  }
  v22 = v58;
  Handle = KspEnterCriticalSection(v58 + 16);
  if ( Handle )
  {
    WppTraceIndent(v23, 2);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    v21 = 302;
    goto LABEL_32;
  }
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v61, v22 + 16);
  Handle = HtGetHandle(a2, 2, &v59);
  if ( Handle )
  {
    WppTraceIndent(v24, 2);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    v21 = 303;
    goto LABEL_32;
  }
  if ( !wcscmp_0(a3, L"Export Policy") )
  {
    if ( *(_DWORD *)(v59 + 1048) )
    {
      WppTraceIndent(v59, 2);
      v17 = 2148073483LL;
      Handle = -2146893813;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_21;
      }
      v16 = 304;
      goto LABEL_20;
    }
    v25 = *(_QWORD *)(v59 + 1088);
    if ( v25 )
    {
      if ( *(_DWORD *)(v25 + 700) )
      {
        WppTraceIndent(v59, 2);
        v17 = 2148532276LL;
        Handle = -2146435020;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_21;
        }
        v16 = 305;
        goto LABEL_20;
      }
      if ( !*(_DWORD *)(v25 + 708) )
      {
        WppTraceIndent(v59, 2);
        v17 = 2148532258LL;
        Handle = -2146435038;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_21;
        }
        v16 = 306;
        goto LABEL_20;
      }
    }
    if ( cbData != 4 || (*(_DWORD *)a4 & 0xFFFFFFF3) != 0 )
    {
      WppTraceIndent(v59, 2);
      v17 = 2148073511LL;
      Handle = -2146893785;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_21;
      }
      v16 = 307;
      goto LABEL_20;
    }
    if ( !dword_18004C298 )
    {
      *(_DWORD *)(v59 + 1184) = *(_DWORD *)a4;
      goto LABEL_21;
    }
    WppTraceIndent(v59, 2);
    Handle = -2146893783;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    v16 = 308;
    goto LABEL_19;
  }
  if ( wcscmp_0(a3, L"Key Usage") )
  {
    if ( !wcscmp_0(a3, L"Length") )
    {
      v30 = v59;
      if ( *(_DWORD *)(v59 + 1048) )
      {
        WppTraceIndent(v29, 2);
        v17 = 2148073483LL;
        Handle = -2146893813;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_21;
        }
        v16 = 314;
        goto LABEL_20;
      }
      v31 = *(_QWORD *)(v59 + 1088);
      if ( !v31 )
        goto LABEL_120;
      if ( *(_DWORD *)(v31 + 700) )
      {
        WppTraceIndent(v31, 2);
        v17 = 2148532276LL;
        Handle = -2146435020;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_21;
        }
        v16 = 315;
        goto LABEL_20;
      }
      if ( *(_DWORD *)(v31 + 708) )
      {
LABEL_120:
        if ( cbData == 4 )
        {
          v32 = *(unsigned int *)a4;
          if ( *(_DWORD *)(v59 + 1044) == (_DWORD)v32 || *(_DWORD *)(v59 + 1052) )
          {
            *(_DWORD *)(v59 + 1044) = v32;
            *(_DWORD *)(v30 + 1060) = 1;
            goto LABEL_21;
          }
          WppTraceIndent(v32, 2);
          v17 = 2148073511LL;
          Handle = -2146893785;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_21;
          }
          v16 = 318;
        }
        else
        {
          WppTraceIndent(v31, 2);
          v17 = 2148073511LL;
          Handle = -2146893785;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_21;
          }
          v16 = 317;
        }
        goto LABEL_20;
      }
      WppTraceIndent(v31, 2);
      v17 = 2148532258LL;
      Handle = -2146435038;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_21;
      }
      v16 = 316;
LABEL_20:
      WPP_SF_d(v15[2], v16, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, v17);
      goto LABEL_21;
    }
    if ( !wcscmp_0(a3, L"ECCPRIVATEBLOB")
      || !wcscmp_0(a3, L"RSAPRIVATEBLOB")
      || !wcscmp_0(a3, L"PRIVATEBLOB")
      || !wcscmp_0(a3, L"CAPIPRIVATEBLOB") )
    {
      if ( *(_DWORD *)(v59 + 1048) )
      {
        WppTraceIndent(v33, 2);
        v17 = 2148073483LL;
        Handle = -2146893813;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_21;
        }
        v16 = 319;
        goto LABEL_20;
      }
      v52 = *(_QWORD *)(v59 + 1088);
      if ( v52 )
      {
        if ( *(_DWORD *)(v52 + 700) )
        {
          WppTraceIndent(v33, 2);
          v17 = 2148532276LL;
          Handle = -2146435020;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_21;
          }
          v16 = 320;
          goto LABEL_20;
        }
        if ( !*(_DWORD *)(v52 + 708) )
        {
          WppTraceIndent(v33, 2);
          v17 = 2148532258LL;
          Handle = -2146435038;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_21;
          }
          v16 = 321;
          goto LABEL_20;
        }
      }
      v10 = v58;
      Handle = NCryptImportKey(*(_QWORD *)(*(_QWORD *)v58 + 224LL), 0, a3, 0, &hKey, a4, cbData, 0x400u);
      if ( Handle )
      {
        WppTraceIndent(v53, 2);
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_22;
        }
        v37 = 322;
      }
      else
      {
        Handle = NCryptSetProperty(hKey, L"Export Policy", (PBYTE)&pbInput, 4u, 0);
        if ( Handle )
        {
          WppTraceIndent(v54, 2);
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_22;
          }
          v37 = 323;
        }
        else
        {
          Handle = NCryptFinalizeKey(hKey, 0);
          if ( Handle )
          {
            WppTraceIndent(v55, 2);
            v36 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_22;
            }
            v37 = 324;
          }
          else
          {
            Handle = KsppPrepareKeyImport(hKey);
            if ( !Handle )
              goto LABEL_22;
            WppTraceIndent(v56, 2);
            v36 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_22;
            }
            v37 = 325;
          }
        }
      }
    }
    else if ( !wcscmp_0(a3, L"SmartCardPin") )
    {
      v34 = *(_QWORD *)(v59 + 1136);
      if ( v34 && *(_DWORD *)(v34 + 24) == 3 )
        goto LABEL_21;
      v10 = v58;
      Handle = KsppUpdatePin(v58, v59, a4, cbData, 0);
      if ( !Handle )
        goto LABEL_22;
      WppTraceIndent(v35, 2);
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_22;
      }
      v37 = 326;
    }
    else if ( !wcscmp_0(a3, L"SmartCardSecurePin") )
    {
      v38 = *(_QWORD *)(v59 + 1136);
      if ( v38 && *(_DWORD *)(v38 + 24) == 3 )
        goto LABEL_21;
      v10 = v58;
      Handle = KsppUpdatePin(v58, v59, a4, cbData, 1);
      if ( !Handle )
        goto LABEL_22;
      WppTraceIndent(v39, 2);
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_22;
      }
      v37 = 327;
    }
    else
    {
      if ( !wcscmp_0(a3, L"UI Policy") )
        goto LABEL_21;
      if ( wcscmp_0(a3, L"SmartCardKeyCertificate") )
      {
        if ( !wcscmp_0(a3, L"Use Context") )
        {
          v45 = v59;
          Handle = KsppAllocateAndCopyString(v59 + 1072, a4, cbData);
          if ( !Handle )
          {
            v47 = *(_QWORD *)(v45 + 1072);
            v48 = -1;
            do
              ++v48;
            while ( *(_WORD *)(v47 + 2 * v48) );
            if ( v48 > 0x7F )
              *(_WORD *)(v47 + 254) = 0;
            goto LABEL_21;
          }
          WppTraceIndent(v46, 2);
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_21:
            v10 = v58;
            goto LABEL_22;
          }
          v21 = 332;
        }
        else
        {
          if ( !wcscmp_0(a3, L"SmartCardDismissUITimeoutSeconds") )
          {
            if ( cbData == 4 && a4 )
            {
              *(_DWORD *)(v59 + 1116) = *a4;
              goto LABEL_21;
            }
            WppTraceIndent(v49, 2);
            v17 = 2148073511LL;
            Handle = -2146893785;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_21;
            }
            v16 = 333;
            goto LABEL_20;
          }
          if ( !wcscmp_0(a3, L"HWND Handle") )
          {
            if ( cbData == 8 )
            {
              *(_QWORD *)(v59 + 1104) = *(_QWORD *)a4;
              goto LABEL_21;
            }
            WppTraceIndent(v50, 2);
            v17 = 2148073511LL;
            Handle = -2146893785;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_21;
            }
            v16 = 334;
            goto LABEL_20;
          }
          if ( (v12 & 0x40000000) == 0 )
          {
            WppTraceIndent(v50, 2);
            v17 = 2148073511LL;
            Handle = -2146893785;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_21;
            }
            v16 = 336;
            goto LABEL_20;
          }
          Handle = KsppAddMiscProperty(v59 + 1192, a3, a4, cbData);
          if ( !Handle )
            goto LABEL_21;
          WppTraceIndent(v51, 2);
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_21;
          }
          v21 = 335;
        }
LABEL_32:
        WPP_SF_sd(
          v20[2],
          v21,
          (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
          (_DWORD)WPP_pszIndent,
          Handle);
        goto LABEL_21;
      }
      v41 = v59;
      v42 = *(_QWORD *)(v59 + 1088);
      if ( !v42 )
        goto LABEL_21;
      if ( *(_DWORD *)(v42 + 700) )
      {
        WppTraceIndent(v40, 2);
        v17 = 2148532276LL;
        Handle = -2146435020;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_21;
        }
        v16 = 328;
        goto LABEL_20;
      }
      if ( !*(_DWORD *)(v42 + 708) )
      {
        WppTraceIndent(v40, 2);
        v17 = 2148532258LL;
        Handle = -2146435038;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_21;
        }
        v16 = 329;
        goto LABEL_20;
      }
      phKey = v12;
      v10 = v58;
      Handle = KsppSetCertificate(v58, v59, a4, cbData, phKey);
      if ( !Handle )
      {
        if ( (unsigned int)SmartCardCertsNotifyService(*(_QWORD *)(v41 + 1088) + 32LL) )
        {
          WppTraceIndent(v44, 2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              331,
              &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
              WPP_pszIndent);
          }
        }
        goto LABEL_22;
      }
      WppTraceIndent(v43, 2);
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_22;
      }
      v37 = 330;
    }
    WPP_SF_sd(
      v36[2],
      v37,
      (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
      (_DWORD)WPP_pszIndent,
      Handle);
    goto LABEL_22;
  }
  v26 = v59;
  if ( *(_DWORD *)(v59 + 1048) )
  {
    WppTraceIndent(v59, 2);
    v17 = 2148073483LL;
    Handle = -2146893813;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    v16 = 309;
    goto LABEL_20;
  }
  v27 = *(_QWORD *)(v59 + 1088);
  if ( v27 )
  {
    if ( *(_DWORD *)(v27 + 700) )
    {
      WppTraceIndent(v59, 2);
      v17 = 2148532276LL;
      Handle = -2146435020;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_21;
      }
      v16 = 310;
      goto LABEL_20;
    }
    if ( !*(_DWORD *)(v27 + 708) )
    {
      WppTraceIndent(v59, 2);
      v17 = 2148532258LL;
      Handle = -2146435038;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_21;
      }
      v16 = 311;
      goto LABEL_20;
    }
  }
  if ( cbData != 4 )
  {
    WppTraceIndent(v59, 2);
    v17 = 2148073511LL;
    Handle = -2146893785;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    v16 = 312;
    goto LABEL_20;
  }
  v28 = *(_DWORD *)a4;
  if ( *(_DWORD *)a4 != 0xFFFFFF && (v28 & 0xFFFFFFF8) != 0 )
  {
    WppTraceIndent(v59, 2);
    v17 = 2148073511LL;
    Handle = -2146893785;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    v16 = 313;
    goto LABEL_20;
  }
  *(_DWORD *)(v59 + 1188) = v28;
  if ( *(_DWORD *)(v26 + 1040) != 1 )
    goto LABEL_21;
  v10 = v58;
  if ( (v28 & 7) == 2 )
    *(_DWORD *)(v26 + 1040) = 2;
LABEL_22:
  if ( v62 )
  {
    v62 = 0;
    KspLeaveCriticalSection(v10 + 16);
  }
  if ( hKey )
    NCryptDeleteKey(hKey, 0);
  v61 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v61);
  return Handle;
}

```

## disassembly

```asm
0x180025ff0  push    rbp
0x180025ff2  push    rbx
0x180025ff3  push    rsi
0x180025ff4  push    rdi
0x180025ff5  push    r12
0x180025ff7  push    r13
0x180025ff9  push    r14
0x180025ffb  push    r15
0x180025ffd  mov     rbp, rsp
0x180026000  sub     rsp, 78h
0x180026004  mov     r14, r9
0x180026007  mov     rdi, r8
0x18002600a  mov     r13, rdx
0x18002600d  mov     rbx, rcx
0x180026010  xor     esi, esi
0x180026012  mov     r12d, esi
0x180026015  mov     [rbp+var_38], rsi
0x180026019  mov     [rbp+var_30], rsi
0x18002601d  mov     [rbp+hKey], rsi
0x180026021  mov     [rbp+pbInput], 3
0x180026028  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18002602f  mov     [rbp+var_20], rax
0x180026033  mov     [rbp+var_18], rsi
0x180026037  test    rcx, rcx
0x18002603a  jz      loc_180026FF2
0x180026040  test    rdx, rdx
0x180026043  jz      loc_180026FF2
0x180026049  test    r8, r8
0x18002604c  jz      loc_180026FF2
0x180026052  mov     r15d, [rbp+arg_20]
0x180026056  test    r9, r9
0x180026059  jz      short loc_180026060
0x18002605b  test    r15d, r15d
0x18002605e  jnz     short loc_1800260B0
0x180026060  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180026067  mov     rcx, rdi; String1
0x18002606a  call    wcscmp_0
0x18002606f  test    eax, eax
0x180026071  jz      short loc_1800260B0
0x180026073  lea     rdx, aUseContext; "Use Context"
0x18002607a  mov     rcx, rdi; String1
0x18002607d  call    wcscmp_0
0x180026082  test    eax, eax
0x180026084  jz      short loc_1800260B0
0x180026086  lea     rdx, aSmartcardpin; "SmartCardPin"
0x18002608d  mov     rcx, rdi; String1
0x180026090  call    wcscmp_0
0x180026095  test    eax, eax
0x180026097  jz      short loc_1800260B0
0x180026099  lea     rdx, aSmartcardsecur; "SmartCardSecurePin"
0x1800260a0  mov     rcx, rdi; String1
0x1800260a3  call    wcscmp_0
0x1800260a8  test    eax, eax
0x1800260aa  jnz     loc_180026FF2
0x1800260b0  mov     r12d, [rbp+arg_28]
0x1800260b4  test    r12d, 3FFFFFA0h
0x1800260bb  jz      loc_18002619A
0x1800260c1  mov     ebx, 2
0x1800260c6  mov     edx, ebx
0x1800260c8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800260cd  lea     rdi, WPP_GLOBAL_Control
0x1800260d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800260db  cmp     rcx, rdi
0x1800260de  jz      short loc_18002610C
0x1800260e0  test    byte ptr [rcx+1Ch], 1
0x1800260e4  jz      short loc_18002610C
0x1800260e6  cmp     [rcx+19h], bl
0x1800260e9  jb      short loc_18002610C
0x1800260eb  mov     edx, 12Bh
0x1800260f0  mov     dword ptr [rsp+78h+phKey], r12d
0x1800260f5  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800260fc  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180026103  mov     rcx, [rcx+10h]
0x180026107  call    WPP_SF_sd
0x18002610c  mov     edx, ebx
0x18002610e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180026113  mov     esi, 80090009h
0x180026118  mov     rcx, cs:WPP_GLOBAL_Control
0x18002611f  cmp     rcx, rdi
0x180026122  jz      short loc_180026147
0x180026124  test    byte ptr [rcx+1Ch], 1
0x180026128  jz      short loc_180026147
0x18002612a  cmp     [rcx+19h], bl
0x18002612d  jb      short loc_180026147
0x18002612f  mov     edx, 12Ch
0x180026134  mov     r9d, esi
0x180026137  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18002613e  mov     rcx, [rcx+10h]
0x180026142  call    WPP_SF_d
0x180026147  mov     r12, [rbp+var_38]
0x18002614b  xor     ebx, ebx
0x18002614d  cmp     [rbp+var_18], rbx
0x180026151  jz      short loc_180026161
0x180026153  mov     [rbp+var_18], rbx
0x180026157  lea     rcx, [r12+10h]
0x18002615c  call    KspLeaveCriticalSection
0x180026161  mov     rcx, [rbp+hKey]; hKey
0x180026165  test    rcx, rcx
0x180026168  jz      short loc_180026173
0x18002616a  xor     edx, edx; dwFlags
0x18002616c  call    cs:__imp_NCryptDeleteKey
0x180026172  nop
0x180026173  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18002617a  mov     [rbp+var_20], rax
0x18002617e  lea     rcx, [rbp+var_20]
0x180026182  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x180026187  mov     eax, esi
0x180026189  add     rsp, 78h
0x18002618d  pop     r15
0x18002618f  pop     r14
0x180026191  pop     r13
0x180026193  pop     r12
0x180026195  pop     rdi
0x180026196  pop     rsi
0x180026197  pop     rbx
0x180026198  pop     rbp
0x180026199  retn
0x18002619a  lea     r8, [rbp+var_38]
0x18002619e  mov     edx, 3
0x1800261a3  mov     rcx, rbx
0x1800261a6  call    HtGetHandle
0x1800261ab  mov     esi, eax
0x1800261ad  test    eax, eax
0x1800261af  jz      short loc_18002620C
0x1800261b1  mov     ebx, 2
0x1800261b6  mov     edx, ebx
0x1800261b8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800261bd  lea     rdi, WPP_GLOBAL_Control
0x1800261c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261cb  cmp     rcx, rdi
0x1800261ce  jz      loc_180026147
0x1800261d4  test    byte ptr [rcx+1Ch], 1
0x1800261d8  jz      loc_180026147
0x1800261de  cmp     [rcx+19h], bl
0x1800261e1  jb      loc_180026147
0x1800261e7  mov     edx, 12Dh
0x1800261ec  mov     dword ptr [rsp+78h+phKey], esi
0x1800261f0  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800261f7  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x1800261fe  mov     rcx, [rcx+10h]
0x180026202  call    WPP_SF_sd
0x180026207  jmp     loc_180026147
0x18002620c  mov     rbx, [rbp+var_38]
0x180026210  lea     rcx, [rbx+10h]
0x180026214  call    KspEnterCriticalSection
0x180026219  mov     esi, eax
0x18002621b  test    eax, eax
0x18002621d  jz      short loc_18002625C
0x18002621f  mov     ebx, 2
0x180026224  mov     edx, ebx
0x180026226  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002622b  lea     rdi, WPP_GLOBAL_Control
0x180026232  mov     rcx, cs:WPP_GLOBAL_Control
0x180026239  cmp     rcx, rdi
0x18002623c  jz      loc_180026147
0x180026242  test    byte ptr [rcx+1Ch], 1
0x180026246  jz      loc_180026147
0x18002624c  cmp     [rcx+19h], bl
0x18002624f  jb      loc_180026147
0x180026255  mov     edx, 12Eh
0x18002625a  jmp     short loc_1800261EC
0x18002625c  lea     rdx, [rbx+10h]
0x180026260  lea     rcx, [rbp+var_20]
0x180026264  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180026269  lea     r8, [rbp+var_30]
0x18002626d  mov     ebx, 2
0x180026272  mov     edx, ebx
0x180026274  mov     rcx, r13
0x180026277  call    HtGetHandle
0x18002627c  mov     esi, eax
0x18002627e  xor     r13d, r13d
0x180026281  test    eax, eax
0x180026283  jz      short loc_1800262C0
0x180026285  mov     edx, ebx
0x180026287  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002628c  lea     rdi, WPP_GLOBAL_Control
0x180026293  mov     rcx, cs:WPP_GLOBAL_Control
0x18002629a  cmp     rcx, rdi
0x18002629d  jz      loc_180026147
0x1800262a3  test    byte ptr [rcx+1Ch], 1
0x1800262a7  jz      loc_180026147
0x1800262ad  cmp     [rcx+19h], bl
0x1800262b0  jb      loc_180026147
0x1800262b6  mov     edx, 12Fh
0x1800262bb  jmp     loc_1800261EC
0x1800262c0  lea     rdx, aExportPolicy; "Export Policy"
0x1800262c7  mov     rcx, rdi; String1
0x1800262ca  call    wcscmp_0
0x1800262cf  test    eax, eax
0x1800262d1  jnz     loc_18002647D
0x1800262d7  mov     rcx, [rbp+var_30]
0x1800262db  xor     r12d, r12d
0x1800262de  cmp     [rcx+418h], r12d
0x1800262e5  jz      short loc_18002632B
0x1800262e7  mov     edx, ebx
0x1800262e9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800262ee  mov     r9d, 8009000Bh
0x1800262f4  mov     esi, r9d
0x1800262f7  lea     rdi, WPP_GLOBAL_Control
0x1800262fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180026305  cmp     rcx, rdi
0x180026308  jz      loc_180026147
0x18002630e  test    byte ptr [rcx+1Ch], 1
0x180026312  jz      loc_180026147
0x180026318  cmp     [rcx+19h], bl
0x18002631b  jb      loc_180026147
0x180026321  mov     edx, 130h
0x180026326  jmp     loc_180026137
0x18002632b  mov     rax, [rcx+440h]
0x180026332  test    rax, rax
0x180026335  jz      loc_1800263D5
0x18002633b  cmp     [rax+2BCh], r12d
0x180026342  jz      short loc_180026388
0x180026344  mov     edx, ebx
0x180026346  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002634b  mov     r9d, 80100034h
0x180026351  mov     esi, r9d
0x180026354  lea     rdi, WPP_GLOBAL_Control
0x18002635b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026362  cmp     rcx, rdi
0x180026365  jz      loc_180026147
0x18002636b  test    byte ptr [rcx+1Ch], 1
0x18002636f  jz      loc_180026147
0x180026375  cmp     [rcx+19h], bl
0x180026378  jb      loc_180026147
0x18002637e  mov     edx, 131h
0x180026383  jmp     loc_180026137
0x180026388  cmp     [rax+2C4h], r12d
0x18002638f  jnz     short loc_1800263D5
0x180026391  mov     edx, ebx
0x180026393  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180026398  mov     r9d, 80100022h
0x18002639e  mov     esi, r9d
0x1800263a1  lea     rdi, WPP_GLOBAL_Control
0x1800263a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263af  cmp     rcx, rdi
0x1800263b2  jz      loc_180026147
0x1800263b8  test    byte ptr [rcx+1Ch], 1
0x1800263bc  jz      loc_180026147
0x1800263c2  cmp     [rcx+19h], bl
0x1800263c5  jb      loc_180026147
0x1800263cb  mov     edx, 132h
0x1800263d0  jmp     loc_180026137
0x1800263d5  cmp     r15d, 4
0x1800263d9  jnz     short loc_180026439
0x1800263db  mov     eax, [r14]
0x1800263de  test    eax, 0FFFFFFF3h
0x1800263e3  jnz     short loc_180026439
0x1800263e5  cmp     cs:dword_18004C298, r12d
0x1800263ec  jz      short loc_18002642E
0x1800263ee  mov     edx, ebx
0x1800263f0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800263f5  mov     esi, 80090029h
0x1800263fa  lea     rdi, WPP_GLOBAL_Control
0x180026401  mov     rcx, cs:WPP_GLOBAL_Control
0x180026408  cmp     rcx, rdi
0x18002640b  jz      loc_180026147
0x180026411  test    byte ptr [rcx+1Ch], 1
0x180026415  jz      loc_180026147
0x18002641b  cmp     [rcx+19h], bl
0x18002641e  jb      loc_180026147
0x180026424  mov     edx, 134h
0x180026429  jmp     loc_180026134
0x18002642e  mov     [rcx+4A0h], eax
0x180026434  jmp     loc_180026147
0x180026439  mov     edx, ebx
0x18002643b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180026440  mov     r9d, 80090027h
0x180026446  mov     esi, r9d
0x180026449  lea     rdi, WPP_GLOBAL_Control
0x180026450  mov     rcx, cs:WPP_GLOBAL_Control
0x180026457  cmp     rcx, rdi
0x18002645a  jz      loc_180026147
0x180026460  test    byte ptr [rcx+1Ch], 1
0x180026464  jz      loc_180026147
0x18002646a  cmp     [rcx+19h], bl
0x18002646d  jb      loc_180026147
0x180026473  mov     edx, 133h
0x180026478  jmp     loc_180026137
0x18002647d  lea     rdx, aKeyUsage; "Key Usage"
0x180026484  mov     rcx, rdi; String1
0x180026487  call    wcscmp_0
0x18002648c  test    eax, eax
0x18002648e  jnz     loc_18002665D
0x180026494  mov     rcx, [rbp+var_30]
0x180026498  xor     r12d, r12d
0x18002649b  cmp     [rcx+418h], r12d
0x1800264a2  jz      short loc_1800264E8
0x1800264a4  mov     edx, ebx
0x1800264a6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800264ab  mov     r9d, 8009000Bh
0x1800264b1  mov     esi, r9d
0x1800264b4  lea     rdi, WPP_GLOBAL_Control
0x1800264bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800264c2  cmp     rcx, rdi
0x1800264c5  jz      loc_180026147
0x1800264cb  test    byte ptr [rcx+1Ch], 1
0x1800264cf  jz      loc_180026147
0x1800264d5  cmp     [rcx+19h], bl
0x1800264d8  jb      loc_180026147
  ... truncated ...
```
