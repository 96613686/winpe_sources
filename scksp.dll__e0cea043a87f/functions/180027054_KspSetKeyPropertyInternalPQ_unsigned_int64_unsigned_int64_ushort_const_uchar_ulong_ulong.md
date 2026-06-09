# KspSetKeyPropertyInternalPQ(unsigned __int64,unsigned __int64,ushort const *,uchar *,ulong,ulong)

- ea: `0x180027054`
- end: `0x1800283d5`
- name: `?KspSetKeyPropertyInternalPQ@@YAJ_K0PEBGPEAEKK@Z`
- size: `4993`
- prototype: `int(unsigned __int64, unsigned __int64, const unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `21`
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
- `0x180027054`
- `0x18003af5c`
- `0x18003afc0`
- `0x18003bd68`
- `0x18003be00`
- `0x18003be1c`
- `0x18003bebc`
- `0x18003bf9c`
- `0x18003c20e`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x1800283a7`
- `ncrypt!NCryptDeleteKey` at `0x1800283a7`
- `ncrypt!NCryptFinalizeKey` at `0x18002829f`
- `ncrypt!NCryptFinalizeKey` at `0x18002829f`
- `ncrypt!NCryptImportKey` at `0x1800281f1`
- `ncrypt!NCryptImportKey` at `0x1800281f1`
- `ncrypt!NCryptSetProperty` at `0x180028252`
- `ncrypt!NCryptSetProperty` at `0x180028252`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KspSetKeyPropertyInternalPQ(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        DWORD a5,
        unsigned int a6)
{
  __int64 v10; // r13
  unsigned __int64 cbData; // r14
  unsigned int v12; // r13d
  PVOID v13; // rcx
  unsigned int Handle; // esi
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  int v17; // edx
  __int64 v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rcx
  _QWORD *v21; // rcx
  int v22; // edx
  __int64 v23; // r9
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rax
  unsigned int v36; // edi
  __int64 v37; // rcx
  __int64 PqcParamInfoByParameterSetName; // rdx
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r11
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rcx
  _QWORD *v48; // rcx
  int v49; // edx
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rdi
  __int64 v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rdi
  __int64 v58; // rcx
  __int64 v59; // rcx
  unsigned __int64 v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // r13
  __int64 v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  unsigned int phKey; // [rsp+20h] [rbp-58h]
  __int64 v72; // [rsp+40h] [rbp-38h] BYREF
  __int64 v73; // [rsp+48h] [rbp-30h] BYREF
  NCRYPT_KEY_HANDLE hObject; // [rsp+50h] [rbp-28h] BYREF
  void **v75; // [rsp+58h] [rbp-20h] BYREF
  __int64 v76; // [rsp+60h] [rbp-18h]
  int pbInput; // [rsp+C0h] [rbp+48h] BYREF

  v10 = 0;
  v72 = 0;
  v73 = 0;
  hObject = 0;
  pbInput = 3;
  v75 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v76 = 0;
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 337, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, 2148073511LL);
    }
    goto LABEL_296;
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
        338,
        (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        (_DWORD)WPP_pszIndent,
        v12);
    }
    WppTraceIndent(v13, 2);
    Handle = -2146893815;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 339, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, 2148073481LL);
    }
    goto LABEL_19;
  }
  Handle = HtGetHandle(a1, 3, &v72);
  if ( Handle )
  {
    WppTraceIndent(v15, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    v17 = 340;
LABEL_25:
    WPP_SF_sd(
      v16[2],
      v17,
      (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
      (_DWORD)WPP_pszIndent,
      Handle);
LABEL_19:
    v10 = v72;
    goto LABEL_296;
  }
  v18 = v72;
  Handle = KspEnterCriticalSection(v72 + 16);
  if ( Handle )
  {
    WppTraceIndent(v19, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    v17 = 341;
    goto LABEL_25;
  }
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v75, v18 + 16);
  Handle = HtGetHandle(a2, 2, &v73);
  if ( Handle )
  {
    WppTraceIndent(v20, 2);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_37;
    }
    v22 = 342;
    goto LABEL_36;
  }
  if ( !wcscmp_0(a3, L"Export Policy") )
  {
    if ( *(_DWORD *)(v73 + 1048) )
    {
      WppTraceIndent(v73, 2);
      v23 = 2148073483LL;
      Handle = -2146893813;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_37;
      }
      v25 = 343;
      goto LABEL_44;
    }
    v26 = *(_QWORD *)(v73 + 1088);
    if ( !v26 )
      goto LABEL_57;
    if ( *(_DWORD *)(v26 + 700) )
    {
      WppTraceIndent(v73, 2);
      v23 = 2148532276LL;
      Handle = -2146435020;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_37;
      }
      v25 = 344;
      goto LABEL_44;
    }
    if ( *(_DWORD *)(v26 + 708) )
    {
LABEL_57:
      if ( (_DWORD)cbData != 4 || (*(_DWORD *)a4 & 0xFFFFFFF3) != 0 )
      {
        WppTraceIndent(v73, 2);
        v23 = 2148073511LL;
        Handle = -2146893785;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_37;
        }
        v25 = 346;
      }
      else
      {
        if ( !dword_18004C298 )
        {
          *(_DWORD *)(v73 + 1184) = *(_DWORD *)a4;
          goto LABEL_37;
        }
        WppTraceIndent(v73, 2);
        Handle = -2146893783;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_37;
        }
        v25 = 347;
        v23 = 2148073513LL;
      }
      goto LABEL_44;
    }
    WppTraceIndent(v73, 2);
    v23 = 2148532258LL;
    Handle = -2146435038;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_37;
    }
    v25 = 345;
    goto LABEL_44;
  }
  if ( wcscmp_0(a3, L"Key Usage") )
  {
    if ( !wcscmp_0(a3, L"Length") )
    {
      v31 = v73;
      if ( *(_DWORD *)(v73 + 1048) )
      {
        WppTraceIndent(v30, 2);
        v23 = 2148073483LL;
        Handle = -2146893813;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_37;
        }
        v25 = 353;
        goto LABEL_44;
      }
      v32 = *(_QWORD *)(v73 + 1088);
      if ( !v32 )
        goto LABEL_116;
      if ( *(_DWORD *)(v32 + 700) )
      {
        WppTraceIndent(v32, 2);
        v23 = 2148532276LL;
        Handle = -2146435020;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_37;
        }
        v25 = 354;
        goto LABEL_44;
      }
      if ( *(_DWORD *)(v32 + 708) )
      {
LABEL_116:
        if ( (_DWORD)cbData == 4 )
        {
          v33 = *(unsigned int *)a4;
          if ( *(_DWORD *)(v73 + 1044) == (_DWORD)v33 || *(_DWORD *)(v73 + 1052) )
          {
            *(_DWORD *)(v73 + 1044) = v33;
            *(_DWORD *)(v31 + 1060) = 1;
            goto LABEL_37;
          }
          WppTraceIndent(v33, 2);
          v23 = 2148073511LL;
          Handle = -2146893785;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_37;
          }
          v25 = 357;
        }
        else
        {
          WppTraceIndent(v32, 2);
          v23 = 2148073511LL;
          Handle = -2146893785;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_37;
          }
          v25 = 356;
        }
        goto LABEL_44;
      }
      WppTraceIndent(v32, 2);
      v23 = 2148532258LL;
      Handle = -2146435038;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_37;
      }
      v25 = 355;
      goto LABEL_44;
    }
    if ( !wcscmp_0(a3, L"ParameterSetName") )
    {
      if ( *(_DWORD *)(v73 + 1048) )
      {
        WppTraceIndent(v34, 2);
        v23 = 2148073483LL;
        Handle = -2146893813;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_37;
        }
        v25 = 358;
        goto LABEL_44;
      }
      v35 = *(_QWORD *)(v73 + 1088);
      if ( !v35 )
        goto LABEL_303;
      if ( *(_DWORD *)(v35 + 700) )
      {
        WppTraceIndent(v34, 2);
        v23 = 2148532276LL;
        Handle = -2146435020;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_37;
        }
        v25 = 359;
        goto LABEL_44;
      }
      if ( *(_DWORD *)(v35 + 708) )
      {
LABEL_303:
        if ( !a4
          || (unsigned int)cbData > 0x7FFFFFFF
          || (cbData & 1) != 0
          || (unsigned int)cbData <= 2
          || *(_WORD *)&a4[2 * (cbData >> 1) - 2] )
        {
          WppTraceIndent(v34, 2);
          v23 = 2148073511LL;
          Handle = -2146893785;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_37;
          }
          v25 = 361;
        }
        else
        {
          v36 = *(_DWORD *)(v73 + 1040);
          if ( (unsigned int)IsPqcKey(v36) )
          {
            PqcParamInfoByParameterSetName = GetPqcParamInfoByParameterSetName(a4);
            if ( PqcParamInfoByParameterSetName )
            {
              if ( (unsigned int)IsMlDsaKey(v36, PqcParamInfoByParameterSetName)
                && (unsigned int)IsMlDsaKey(*(unsigned int *)(v40 + 32), v40)
                || (unsigned int)IsMlKemKey(v36) && (unsigned int)IsMlKemKey(*(unsigned int *)(v44 + 32)) )
              {
                *(_DWORD *)(v43 + 1040) = v42;
                *(_QWORD *)(v43 + 1208) = *(_QWORD *)v41;
                *(_DWORD *)(v43 + 1044) = *(_DWORD *)(v41 + 12);
                goto LABEL_37;
              }
              WppTraceIndent(v42, 2);
              v23 = 2148073511LL;
              Handle = -2146893785;
              v24 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_37;
              }
              v25 = 364;
            }
            else
            {
              WppTraceIndent(v39, 2);
              v23 = 2148073511LL;
              Handle = -2146893785;
              v24 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_37;
              }
              v25 = 363;
            }
          }
          else
          {
            WppTraceIndent(v37, 2);
            v23 = 2148073511LL;
            Handle = -2146893785;
            v24 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_37;
            }
            v25 = 362;
          }
        }
        goto LABEL_44;
      }
      WppTraceIndent(v34, 2);
      v23 = 2148532258LL;
      Handle = -2146435038;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_37;
      }
      v25 = 360;
LABEL_44:
      WPP_SF_d(v24[2], v25, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, v23);
      goto LABEL_37;
    }
    if ( !wcscmp_0(a3, L"ECCPRIVATEBLOB")
      || !wcscmp_0(a3, L"RSAPRIVATEBLOB")
      || !wcscmp_0(a3, L"PRIVATEBLOB")
      || !wcscmp_0(a3, L"PQDSAPRIVATEBLOB")
      || !wcscmp_0(a3, L"PQDSAPRIVATESEEDBLOB")
      || !wcscmp_0(a3, L"MLKEMPRIVATEBLOB")
      || !wcscmp_0(a3, L"MLKEMPRIVATESEEDBLOB")
      || !wcscmp_0(a3, L"CAPIPRIVATEBLOB") )
    {
      v64 = v73;
      if ( *(_DWORD *)(v73 + 1048) )
      {
        WppTraceIndent(v45, 2);
        v23 = 2148073483LL;
        Handle = -2146893813;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_37;
        }
        v25 = 365;
        goto LABEL_44;
      }
      v65 = *(_QWORD *)(v73 + 1088);
      if ( v65 )
      {
        if ( *(_DWORD *)(v65 + 700) )
        {
          WppTraceIndent(v45, 2);
          v23 = 2148532276LL;
          Handle = -2146435020;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_37;
          }
          v25 = 366;
          goto LABEL_44;
        }
        if ( !*(_DWORD *)(v65 + 708) )
        {
          WppTraceIndent(v45, 2);
          v23 = 2148532258LL;
          Handle = -2146435038;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_37;
          }
          v25 = 367;
          goto LABEL_44;
        }
      }
      Handle = NCryptImportKey(*(_QWORD *)(*(_QWORD *)v72 + 224LL), 0, a3, 0, &hObject, a4, cbData, 0x400u);
      if ( Handle )
      {
        WppTraceIndent(v66, 2);
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_37;
        }
        v22 = 368;
      }
      else
      {
        Handle = NCryptSetProperty(hObject, L"Export Policy", (PBYTE)&pbInput, 4u, 0);
        if ( Handle )
        {
          WppTraceIndent(v67, 2);
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_37;
          }
          v22 = 369;
        }
        else
        {
          Handle = NCryptFinalizeKey(hObject, 0);
          if ( Handle )
          {
            WppTraceIndent(v68, 2);
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_37;
            }
            v22 = 370;
          }
          else
          {
            *(_QWORD *)(v64 + 1176) = a3;
            Handle = KsppPrepareKeyImport(hObject);
            if ( !Handle )
              goto LABEL_37;
            WppTraceIndent(v69, 2);
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_37;
            }
            v22 = 371;
          }
        }
      }
    }
    else
    {
      if ( !wcscmp_0(a3, L"SmartCardPin") )
      {
        v46 = *(_QWORD *)(v73 + 1136);
        if ( v46 && *(_DWORD *)(v46 + 24) == 3 )
          goto LABEL_37;
        v10 = v72;
        Handle = KsppUpdatePin(v72, v73, a4, (unsigned int)cbData, 0);
        if ( !Handle )
          goto LABEL_296;
        WppTraceIndent(v47, 2);
        v48 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_296;
        }
        v49 = 372;
LABEL_189:
        WPP_SF_sd(
          v48[2],
          v49,
          (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
          (_DWORD)WPP_pszIndent,
          Handle);
        goto LABEL_296;
      }
      if ( !wcscmp_0(a3, L"SmartCardSecurePin") )
      {
        v50 = *(_QWORD *)(v73 + 1136);
        if ( v50 && *(_DWORD *)(v50 + 24) == 3 )
          goto LABEL_37;
        v10 = v72;
        Handle = KsppUpdatePin(v72, v73, a4, (unsigned int)cbData, 1);
        if ( !Handle )
          goto LABEL_296;
        WppTraceIndent(v51, 2);
        v48 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_296;
        }
        v49 = 373;
        goto LABEL_189;
      }
      if ( !wcscmp_0(a3, L"UI Policy") )
        goto LABEL_37;
      if ( !wcscmp_0(a3, L"SmartCardKeyCertificate") )
      {
        v53 = v73;
        v54 = *(_QWORD *)(v73 + 1088);
        if ( !v54 )
          goto LABEL_37;
        if ( *(_DWORD *)(v54 + 700) )
        {
          WppTraceIndent(v52, 2);
          v23 = 2148532276LL;
          Handle = -2146435020;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_37;
          }
          v25 = 374;
          goto LABEL_44;
        }
        if ( !*(_DWORD *)(v54 + 708) )
        {
          WppTraceIndent(v52, 2);
          v23 = 2148532258LL;
          Handle = -2146435038;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_37;
          }
          v25 = 375;
          goto LABEL_44;
        }
        phKey = v12;
        v10 = v72;
        Handle = KsppSetCertificate(v72, v73, a4, (unsigned int)cbData, phKey);
        if ( !Handle )
        {
          if ( (unsigned int)SmartCardCertsNotifyService(*(_QWORD *)(v53 + 1088) + 32LL) )
          {
            WppTraceIndent(v56, 2);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                377,
                &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
                WPP_pszIndent);
            }
          }
          goto LABEL_296;
        }
        WppTraceIndent(v55, 2);
        v48 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_296;
        }
        v49 = 376;
        goto LABEL_189;
      }
      if ( !wcscmp_0(a3, L"Use Context") )
      {
        v57 = v73;
        Handle = KsppAllocateAndCopyString(v73 + 1072, a4, (unsigned int)cbData);
        if ( !Handle )
        {
          v59 = *(_QWORD *)(v57 + 1072);
          v60 = -1;
          do
            ++v60;
          while ( *(_WORD *)(v59 + 2 * v60) );
          v10 = v72;
          if ( v60 > 0x7F )
            *(_WORD *)(v59 + 254) = 0;
          goto LABEL_296;
        }
        WppTraceIndent(v58, 2);
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_37;
        }
        v22 = 378;
      }
      else
      {
        if ( !wcscmp_0(a3, L"SmartCardDismissUITimeoutSeconds") )
        {
          if ( (_DWORD)cbData == 4 && a4 )
          {
            *(_DWORD *)(v73 + 1116) = *a4;
            goto LABEL_37;
          }
          WppTraceIndent(v61, 2);
          v23 = 2148073511LL;
          Handle = -2146893785;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_37;
          }
          v25 = 379;
          goto LABEL_44;
        }
        if ( !wcscmp_0(a3, L"HWND Handle") )
        {
          if ( (_DWORD)cbData == 8 )
          {
            *(_QWORD *)(v73 + 1104) = *(_QWORD *)a4;
            goto LABEL_37;
          }
          WppTraceIndent(v62, 2);
          v23 = 2148073511LL;
          Handle = -2146893785;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_37;
          }
          v25 = 380;
          goto LABEL_44;
        }
        if ( (v12 & 0x40000000) == 0 )
        {
          WppTraceIndent(v62, 2);
          v23 = 2148073511LL;
          Handle = -2146893785;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_37;
          }
          v25 = 382;
          goto LABEL_44;
        }
        Handle = KsppAddMiscProperty(v73 + 1192, a3, a4, (unsigned int)cbData);
        if ( !Handle )
          goto LABEL_37;
        WppTraceIndent(v63, 2);
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_37;
        }
        v22 = 381;
      }
    }
LABEL_36:
    WPP_SF_sd(
      v21[2],
      v22,
      (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
      (_DWORD)WPP_pszIndent,
      Handle);
LABEL_37:
    v10 = v72;
    goto LABEL_296;
  }
  v27 = v73;
  if ( *(_DWORD *)(v73 + 1048) )
  {
    WppTraceIndent(v73, 2);
    v23 = 2148073483LL;
    Handle = -2146893813;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_37;
    }
    v25 = 348;
    goto LABEL_44;
  }
  v28 = *(_QWORD *)(v73 + 1088);
  if ( v28 )
  {
    if ( *(_DWORD *)(v28 + 700) )
    {
      WppTraceIndent(v73, 2);
      v23 = 2148532276LL;
      Handle = -2146435020;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_37;
      }
      v25 = 349;
      goto LABEL_44;
    }
    if ( !*(_DWORD *)(v28 + 708) )
    {
      WppTraceIndent(v73, 2);
      v23 = 2148532258LL;
      Handle = -2146435038;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_37;
      }
      v25 = 350;
      goto LABEL_44;
    }
  }
  if ( (_DWORD)cbData != 4 )
  {
    WppTraceIndent(v73, 2);
    v23 = 2148073511LL;
    Handle = -2146893785;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_37;
    }
    v25 = 351;
    goto LABEL_44;
  }
  v29 = *(_DWORD *)a4;
  if ( *(_DWORD *)a4 != 0xFFFFFF && (v29 & 0xFFFFFFF8) != 0 )
  {
    WppTraceIndent(v73, 2);
    v23 = 2148073511LL;
    Handle = -2146893785;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_37;
    }
    v25 = 352;
    goto LABEL_44;
  }
  *(_DWORD *)(v73 + 1188) = v29;
  if ( *(_DWORD *)(v27 + 1040) != 1 )
    goto LABEL_37;
  v10 = v72;
  if ( (v29 & 7) == 2 )
    *(_DWORD *)(v27 + 1040) = 2;
LABEL_296:
  if ( v76 )
  {
    v76 = 0;
    KspLeaveCriticalSection(v10 + 16);
  }
  if ( hObject )
    NCryptDeleteKey(hObject, 0);
  v75 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v75);
  return Handle;
}

```

## disassembly

```asm
0x180027054  push    rbp
0x180027056  push    rbx
0x180027057  push    rsi
0x180027058  push    rdi
0x180027059  push    r12
0x18002705b  push    r13
0x18002705d  push    r14
0x18002705f  push    r15
0x180027061  mov     rbp, rsp
0x180027064  sub     rsp, 78h
0x180027068  mov     r15, r9
0x18002706b  mov     rdi, r8
0x18002706e  mov     r12, rdx
0x180027071  mov     rbx, rcx
0x180027074  xor     esi, esi
0x180027076  mov     r13d, esi
0x180027079  mov     [rbp+var_38], rsi
0x18002707d  mov     [rbp+var_30], rsi
0x180027081  mov     [rbp+hObject], rsi
0x180027085  mov     [rbp+pbInput], 3
0x18002708c  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180027093  mov     [rbp+var_20], rax
0x180027097  mov     [rbp+var_18], rsi
0x18002709b  test    rcx, rcx
0x18002709e  jz      loc_18002833E
0x1800270a4  test    rdx, rdx
0x1800270a7  jz      loc_18002833E
0x1800270ad  test    r8, r8
0x1800270b0  jz      loc_18002833E
0x1800270b6  mov     r14d, [rbp+arg_20]
0x1800270ba  test    r9, r9
0x1800270bd  jz      short loc_1800270C4
0x1800270bf  test    r14d, r14d
0x1800270c2  jnz     short loc_180027114
0x1800270c4  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x1800270cb  mov     rcx, rdi; String1
0x1800270ce  call    wcscmp_0
0x1800270d3  test    eax, eax
0x1800270d5  jz      short loc_180027114
0x1800270d7  lea     rdx, aUseContext; "Use Context"
0x1800270de  mov     rcx, rdi; String1
0x1800270e1  call    wcscmp_0
0x1800270e6  test    eax, eax
0x1800270e8  jz      short loc_180027114
0x1800270ea  lea     rdx, aSmartcardpin; "SmartCardPin"
0x1800270f1  mov     rcx, rdi; String1
0x1800270f4  call    wcscmp_0
0x1800270f9  test    eax, eax
0x1800270fb  jz      short loc_180027114
0x1800270fd  lea     rdx, aSmartcardsecur; "SmartCardSecurePin"
0x180027104  mov     rcx, rdi; String1
0x180027107  call    wcscmp_0
0x18002710c  test    eax, eax
0x18002710e  jnz     loc_18002833E
0x180027114  mov     r13d, [rbp+arg_28]
0x180027118  test    r13d, 3FFFFFA0h
0x18002711f  jz      loc_1800271B4
0x180027125  mov     ebx, 2
0x18002712a  mov     edx, ebx
0x18002712c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180027131  lea     rdi, WPP_GLOBAL_Control
0x180027138  mov     rcx, cs:WPP_GLOBAL_Control
0x18002713f  cmp     rcx, rdi
0x180027142  jz      short loc_180027170
0x180027144  test    byte ptr [rcx+1Ch], 1
0x180027148  jz      short loc_180027170
0x18002714a  cmp     [rcx+19h], bl
0x18002714d  jb      short loc_180027170
0x18002714f  mov     edx, 152h
0x180027154  mov     dword ptr [rsp+78h+phKey], r13d
0x180027159  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180027160  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180027167  mov     rcx, [rcx+10h]
0x18002716b  call    WPP_SF_sd
0x180027170  mov     edx, ebx
0x180027172  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180027177  mov     esi, 80090009h
0x18002717c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027183  cmp     rcx, rdi
0x180027186  jz      short loc_1800271AB
0x180027188  test    byte ptr [rcx+1Ch], 1
0x18002718c  jz      short loc_1800271AB
0x18002718e  cmp     [rcx+19h], bl
0x180027191  jb      short loc_1800271AB
0x180027193  mov     edx, 153h
0x180027198  mov     r9d, esi
0x18002719b  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x1800271a2  mov     rcx, [rcx+10h]
0x1800271a6  call    WPP_SF_d
0x1800271ab  mov     r13, [rbp+var_38]
0x1800271af  jmp     loc_180028386
0x1800271b4  lea     r8, [rbp+var_38]
0x1800271b8  mov     edx, 3
0x1800271bd  mov     rcx, rbx
0x1800271c0  call    HtGetHandle
0x1800271c5  mov     esi, eax
0x1800271c7  test    eax, eax
0x1800271c9  jz      short loc_180027217
0x1800271cb  mov     ebx, 2
0x1800271d0  mov     edx, ebx
0x1800271d2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800271d7  lea     rdi, WPP_GLOBAL_Control
0x1800271de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271e5  cmp     rcx, rdi
0x1800271e8  jz      short loc_1800271AB
0x1800271ea  test    byte ptr [rcx+1Ch], 1
0x1800271ee  jz      short loc_1800271AB
0x1800271f0  cmp     [rcx+19h], bl
0x1800271f3  jb      short loc_1800271AB
0x1800271f5  mov     edx, 154h
0x1800271fa  mov     dword ptr [rsp+78h+phKey], esi
0x1800271fe  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180027205  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18002720c  mov     rcx, [rcx+10h]
0x180027210  call    WPP_SF_sd
0x180027215  jmp     short loc_1800271AB
0x180027217  mov     rbx, [rbp+var_38]
0x18002721b  lea     rcx, [rbx+10h]
0x18002721f  call    KspEnterCriticalSection
0x180027224  mov     esi, eax
0x180027226  test    eax, eax
0x180027228  jz      short loc_180027267
0x18002722a  mov     ebx, 2
0x18002722f  mov     edx, ebx
0x180027231  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180027236  lea     rdi, WPP_GLOBAL_Control
0x18002723d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027244  cmp     rcx, rdi
0x180027247  jz      loc_1800271AB
0x18002724d  test    byte ptr [rcx+1Ch], 1
0x180027251  jz      loc_1800271AB
0x180027257  cmp     [rcx+19h], bl
0x18002725a  jb      loc_1800271AB
0x180027260  mov     edx, 155h
0x180027265  jmp     short loc_1800271FA
0x180027267  lea     rdx, [rbx+10h]
0x18002726b  lea     rcx, [rbp+var_20]
0x18002726f  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180027274  lea     r8, [rbp+var_30]
0x180027278  mov     ebx, 2
0x18002727d  mov     edx, ebx
0x18002727f  mov     rcx, r12
0x180027282  call    HtGetHandle
0x180027287  mov     esi, eax
0x180027289  xor     r12d, r12d
0x18002728c  test    eax, eax
0x18002728e  jz      short loc_1800272DE
0x180027290  mov     edx, ebx
0x180027292  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180027297  lea     rdi, WPP_GLOBAL_Control
0x18002729e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800272a5  cmp     rcx, rdi
0x1800272a8  jz      short loc_1800272D5
0x1800272aa  test    byte ptr [rcx+1Ch], 1
0x1800272ae  jz      short loc_1800272D5
0x1800272b0  cmp     [rcx+19h], bl
0x1800272b3  jb      short loc_1800272D5
0x1800272b5  mov     edx, 156h
0x1800272ba  mov     dword ptr [rsp+78h+phKey], esi
0x1800272be  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800272c5  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x1800272cc  mov     rcx, [rcx+10h]
0x1800272d0  call    WPP_SF_sd
0x1800272d5  mov     r13, [rbp+var_38]
0x1800272d9  jmp     loc_180028389
0x1800272de  lea     rdx, aExportPolicy; "Export Policy"
0x1800272e5  mov     rcx, rdi; String1
0x1800272e8  call    wcscmp_0
0x1800272ed  test    eax, eax
0x1800272ef  jnz     loc_180027499
0x1800272f5  mov     rcx, [rbp+var_30]
0x1800272f9  cmp     [rcx+418h], r12d
0x180027300  jz      short loc_180027347
0x180027302  mov     edx, ebx
0x180027304  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180027309  mov     r9d, 8009000Bh
0x18002730f  mov     esi, r9d
0x180027312  lea     rdi, WPP_GLOBAL_Control
0x180027319  mov     rcx, cs:WPP_GLOBAL_Control
0x180027320  cmp     rcx, rdi
0x180027323  jz      short loc_1800272D5
0x180027325  test    byte ptr [rcx+1Ch], 1
0x180027329  jz      short loc_1800272D5
0x18002732b  cmp     [rcx+19h], bl
0x18002732e  jb      short loc_1800272D5
0x180027330  mov     edx, 157h
0x180027335  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18002733c  mov     rcx, [rcx+10h]
0x180027340  call    WPP_SF_d
0x180027345  jmp     short loc_1800272D5
0x180027347  mov     rax, [rcx+440h]
0x18002734e  test    rax, rax
0x180027351  jz      loc_1800273EE
0x180027357  cmp     [rax+2BCh], r12d
0x18002735e  jz      short loc_1800273A1
0x180027360  mov     edx, ebx
0x180027362  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180027367  mov     r9d, 80100034h
0x18002736d  mov     esi, r9d
0x180027370  lea     rdi, WPP_GLOBAL_Control
0x180027377  mov     rcx, cs:WPP_GLOBAL_Control
0x18002737e  cmp     rcx, rdi
0x180027381  jz      loc_1800272D5
0x180027387  test    byte ptr [rcx+1Ch], 1
0x18002738b  jz      loc_1800272D5
0x180027391  cmp     [rcx+19h], bl
0x180027394  jb      loc_1800272D5
0x18002739a  mov     edx, 158h
0x18002739f  jmp     short loc_180027335
0x1800273a1  cmp     [rax+2C4h], r12d
0x1800273a8  jnz     short loc_1800273EE
0x1800273aa  mov     edx, ebx
0x1800273ac  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800273b1  mov     r9d, 80100022h
0x1800273b7  mov     esi, r9d
0x1800273ba  lea     rdi, WPP_GLOBAL_Control
0x1800273c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800273c8  cmp     rcx, rdi
0x1800273cb  jz      loc_1800272D5
0x1800273d1  test    byte ptr [rcx+1Ch], 1
0x1800273d5  jz      loc_1800272D5
0x1800273db  cmp     [rcx+19h], bl
0x1800273de  jb      loc_1800272D5
0x1800273e4  mov     edx, 159h
0x1800273e9  jmp     loc_180027335
0x1800273ee  cmp     r14d, 4
0x1800273f2  jnz     short loc_180027455
0x1800273f4  mov     eax, [r15]
0x1800273f7  test    eax, 0FFFFFFF3h
0x1800273fc  jnz     short loc_180027455
0x1800273fe  cmp     cs:dword_18004C298, r12d
0x180027405  jz      short loc_18002744A
0x180027407  mov     edx, ebx
0x180027409  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002740e  mov     esi, 80090029h
0x180027413  lea     rdi, WPP_GLOBAL_Control
0x18002741a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027421  cmp     rcx, rdi
0x180027424  jz      loc_1800272D5
0x18002742a  test    byte ptr [rcx+1Ch], 1
0x18002742e  jz      loc_1800272D5
0x180027434  cmp     [rcx+19h], bl
0x180027437  jb      loc_1800272D5
0x18002743d  mov     edx, 15Bh
0x180027442  mov     r9d, esi
0x180027445  jmp     loc_180027335
0x18002744a  mov     [rcx+4A0h], eax
0x180027450  jmp     loc_1800272D5
0x180027455  mov     edx, ebx
0x180027457  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002745c  mov     r9d, 80090027h
0x180027462  mov     esi, r9d
0x180027465  lea     rdi, WPP_GLOBAL_Control
0x18002746c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027473  cmp     rcx, rdi
0x180027476  jz      loc_1800272D5
0x18002747c  test    byte ptr [rcx+1Ch], 1
0x180027480  jz      loc_1800272D5
0x180027486  cmp     [rcx+19h], bl
0x180027489  jb      loc_1800272D5
0x18002748f  mov     edx, 15Ah
0x180027494  jmp     loc_180027335
0x180027499  lea     rdx, aKeyUsage; "Key Usage"
0x1800274a0  mov     rcx, rdi; String1
0x1800274a3  call    wcscmp_0
0x1800274a8  test    eax, eax
0x1800274aa  jnz     loc_180027676
0x1800274b0  mov     rcx, [rbp+var_30]
0x1800274b4  cmp     [rcx+418h], r12d
0x1800274bb  jz      short loc_180027501
0x1800274bd  mov     edx, ebx
0x1800274bf  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800274c4  mov     r9d, 8009000Bh
0x1800274ca  mov     esi, r9d
0x1800274cd  lea     rdi, WPP_GLOBAL_Control
0x1800274d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800274db  cmp     rcx, rdi
0x1800274de  jz      loc_1800272D5
0x1800274e4  test    byte ptr [rcx+1Ch], 1
0x1800274e8  jz      loc_1800272D5
0x1800274ee  cmp     [rcx+19h], bl
0x1800274f1  jb      loc_1800272D5
0x1800274f7  mov     edx, 15Ch
0x1800274fc  jmp     loc_180027335
0x180027501  mov     rax, [rcx+440h]
0x180027508  test    rax, rax
0x18002750b  jz      loc_1800275AB
0x180027511  cmp     [rax+2BCh], r12d
0x180027518  jz      short loc_18002755E
0x18002751a  mov     edx, ebx
0x18002751c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180027521  mov     r9d, 80100034h
0x180027527  mov     esi, r9d
0x18002752a  lea     rdi, WPP_GLOBAL_Control
0x180027531  mov     rcx, cs:WPP_GLOBAL_Control
0x180027538  cmp     rcx, rdi
0x18002753b  jz      loc_1800272D5
0x180027541  test    byte ptr [rcx+1Ch], 1
0x180027545  jz      loc_1800272D5
0x18002754b  cmp     [rcx+19h], bl
  ... truncated ...
```
