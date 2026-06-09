# ClientEAPAuthHandler::ProcessAuthResult(_PPPAP_RESULT &,_PPPAP_INPUT &,uchar &)

- ea: `0x180044ad0`
- end: `0x180045b6c`
- name: `?ProcessAuthResult@ClientEAPAuthHandler@@MEAAKAEAU_PPPAP_RESULT@@AEAU_PPPAP_INPUT@@AEAE@Z`
- size: `4252`
- prototype: `__int64 __fastcall(ClientEAPAuthHandler *this, struct _PPPAP_RESULT *, struct _PPPAP_INPUT *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004ab8`
- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180008df8`
- `0x18000a3ec`
- `0x180044ad0`
- `0x180045b74`
- `0x18004611c`
- `0x180046424`
- `0x180046dec`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800457ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800457ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004579f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004579f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045a57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045a57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800459fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800459fd`
- `RASAPI32!RasSetEapUserDataAEx` at `0x180045343`
- `RASAPI32!RasSetEapUserDataAEx` at `0x180045343`

## string_xrefs

- `0x1800456a0`: `Updating Eap Configuration BLOB`
- `0x180045872`: `CreateSynchronizingEvent failed: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClientEAPAuthHandler::ProcessAuthResult(
        ClientEAPAuthHandler *this,
        struct _PPPAP_RESULT *a2,
        struct _PPPAP_INPUT *a3,
        unsigned __int8 *a4)
{
  struct _PPPAP_RESULT *v6; // rsi
  int v8; // r12d
  unsigned int v9; // r14d
  unsigned int v10; // r15d
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __int128 *v19; // r9
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  _QWORD *v24; // rax
  __int64 v25; // rcx
  __int128 *v26; // r9
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  _QWORD *v31; // rax
  __int64 v32; // rcx
  __int128 *v33; // r9
  unsigned int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int128 *v44; // r9
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int128 *v52; // r9
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rcx
  _QWORD *v57; // rax
  __int64 v58; // rcx
  __int128 *v59; // r9
  unsigned int v60; // eax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rcx
  _QWORD *v65; // rax
  __int64 v66; // rcx
  __int128 *v67; // r9
  unsigned int v68; // eax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rcx
  _QWORD *v73; // rax
  __int64 v74; // rcx
  __int128 *v75; // r9
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rdx
  __int64 v79; // rcx
  _QWORD *v80; // rax
  __int64 v81; // rcx
  __int128 *v82; // r9
  void *v83; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int SynchronizingEvent; // eax
  __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rcx
  _QWORD *v89; // rax
  __int64 v90; // rcx
  __int128 *v91; // r9
  PVOID *v92; // rcx
  _OWORD *v93; // r8
  unsigned int v94; // eax
  __int64 v95; // rax
  __int64 v96; // rax
  unsigned int v97; // eax
  unsigned int v98; // ebx
  unsigned int v100; // [rsp+40h] [rbp-C0h] BYREF
  int v101; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v102; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v103; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v104; // [rsp+60h] [rbp-A0h]
  __int128 v105; // [rsp+70h] [rbp-90h]
  __int64 v106; // [rsp+80h] [rbp-80h]
  int v107; // [rsp+88h] [rbp-78h]
  int v108; // [rsp+8Ch] [rbp-74h]
  __int128 v109; // [rsp+90h] [rbp-70h] BYREF
  int v110; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v111; // [rsp+A4h] [rbp-5Ch]
  __int128 v112; // [rsp+B4h] [rbp-4Ch]
  int v113; // [rsp+C4h] [rbp-3Ch]
  int v114; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v115[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  *((_QWORD *)&v102 + 1) = a4;
  v6 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a2) = *((_DWORD *)a2 + 82) != 0;
    WPP_SF_dDccd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      WPP_GLOBAL_Control,
      *(unsigned int *)v6,
      *((_DWORD *)v6 + 2),
      *((_DWORD *)v6 + 3) != 0,
      (_BYTE)a2,
      *((_DWORD *)v6 + 90));
  }
  v100 = 0;
  v8 = 0;
  v9 = 0;
  v101 = 0;
  v114 = 0;
  memset_0(v115, 0, sizeof(v115));
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v113 = 0;
  v109 = 0;
  v104 = 0;
  v103 = 0;
  v105 = 0;
  v106 = 0;
  v10 = -1;
  v107 = -1;
  v108 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v103,
      L"ClientEAPAuthHandler::ProcessAuthResult",
      &v100,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      *((void **)this + 70));
  memset_0(a3, 0, 0x108u);
  *a4 = 0;
  if ( *(_DWORD *)v6 != 1 && *(_DWORD *)v6 != 2 )
  {
    if ( *(_DWORD *)v6 == 3 || (unsigned int)(*(_DWORD *)v6 - 4) <= 1 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v12 = 39;
LABEL_238:
        WPP_SF_(v11[2], v12, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
        v11 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_239;
      }
      goto LABEL_239;
    }
    goto LABEL_233;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_BYTE *)this + 281) && (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v114) = 0;
    LOWORD(v110) = 0;
    v13 = *((_QWORD *)this + 70);
    if ( v13 && (v14 = *(_QWORD *)(v13 + 112)) != 0 && *(_QWORD *)(v14 + 16) )
      v15 = *(unsigned int *)(v14 + 16);
    else
      v15 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v110, v15);
    FormatRRASErrorString(&v114, L"Local User:%S", (char *)this + 281);
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_36;
    v16 = *((_QWORD *)this + 70);
    v17 = (_QWORD *)(v16 + 112);
    if ( v16 )
    {
      if ( *v17 )
        v18 = *v17 + 2686LL;
      else
        v18 = 0;
      if ( *v17 )
      {
        v19 = (__int128 *)(*v17 + 2120LL);
LABEL_35:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v114,
          (_DWORD)v19,
          v18,
          (__int64)&v110);
LABEL_36:
        v11 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_37;
      }
    }
    else
    {
      v18 = 0;
    }
    v19 = &v109;
    goto LABEL_35;
  }
LABEL_37:
  if ( *((_DWORD *)v6 + 2) )
  {
    if ( *((_DWORD *)v6 + 2) == 648 )
    {
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      {
        WPP_SF_(v11[2], 47, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      v9 = 7;
      goto LABEL_66;
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
    {
      WPP_SF_(v11[2], 48, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)v6 + 3) )
    {
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      {
        WPP_SF_(v11[2], 49, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( (byte_1800AA941 & 8) == 0 )
        goto LABEL_65;
      LOWORD(v110) = 0;
      v20 = *((_QWORD *)this + 70);
      if ( v20 && (v21 = *(_QWORD *)(v20 + 112)) != 0 && *(_QWORD *)(v21 + 16) )
        v22 = *(unsigned int *)(v21 + 16);
      else
        v22 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v110, v22);
      if ( (byte_1800AA941 & 8) == 0 )
      {
LABEL_64:
        v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_65:
        v9 = 2;
LABEL_66:
        v8 = 1;
        v101 = v9;
        goto LABEL_234;
      }
      v23 = *((_QWORD *)this + 70);
      v24 = (_QWORD *)(v23 + 112);
      if ( v23 )
      {
        if ( *v24 )
          v25 = *v24 + 2686LL;
        else
          v25 = 0;
        if ( *v24 )
        {
          v26 = (__int128 *)(*v24 + 2120LL);
LABEL_63:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"Sending auth retry message to UI",
            (_DWORD)v26,
            v25,
            (__int64)&v110);
          goto LABEL_64;
        }
      }
      else
      {
        v25 = 0;
      }
      v26 = &v109;
      goto LABEL_63;
    }
    if ( (byte_1800AA941 & 4) == 0 )
    {
LABEL_84:
      v34 = *((_DWORD *)v6 + 2);
      v100 = v34;
      if ( v34 )
      {
        if ( v11 == &WPP_GLOBAL_Control )
          goto LABEL_239;
        if ( (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 2u )
        {
          v35 = 50;
LABEL_89:
          WPP_SF_d(v11[2], v35, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v34);
LABEL_233:
          v11 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_234;
        }
      }
      goto LABEL_234;
    }
    LOWORD(v114) = 0;
    LOWORD(v110) = 0;
    v27 = *((_QWORD *)this + 70);
    if ( v27 && (v28 = *(_QWORD *)(v27 + 112)) != 0 && *(_QWORD *)(v28 + 16) )
      v29 = *(unsigned int *)(v28 + 16);
    else
      v29 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v110, v29);
    FormatRRASErrorString(&v114, L"Auth failed :( %d", *((unsigned int *)v6 + 2));
    if ( (byte_1800AA941 & 4) == 0 )
    {
LABEL_83:
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_84;
    }
    v30 = *((_QWORD *)this + 70);
    v31 = (_QWORD *)(v30 + 112);
    if ( v30 )
    {
      if ( *v31 )
        v32 = *v31 + 2686LL;
      else
        v32 = 0;
      if ( *v31 )
      {
        v33 = (__int128 *)(*v31 + 2120LL);
LABEL_82:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v114,
          (_DWORD)v33,
          v32,
          (__int64)&v110);
        goto LABEL_83;
      }
    }
    else
    {
      v32 = 0;
    }
    v33 = &v109;
    goto LABEL_82;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
  {
    WPP_SF_(v11[2], 41, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  v36 = *((_QWORD *)this + 72);
  if ( !*((_DWORD *)this + 422) )
  {
    LODWORD(v102) = 128;
    DWORD1(v102) = *((_DWORD *)v6 + 90);
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_116;
    LOWORD(v110) = 0;
    v37 = *((_QWORD *)this + 70);
    if ( v37 && (v38 = *(_QWORD *)(v37 + 112)) != 0 && *(_QWORD *)(v38 + 16) )
      v39 = *(unsigned int *)(v38 + 16);
    else
      v39 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v110, v39);
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_116;
    v40 = *((_QWORD *)this + 70);
    if ( v40 )
    {
      v41 = *(_QWORD *)(v40 + 112);
      if ( v41 )
        v42 = v41 + 2686;
      else
        v42 = 0;
      v43 = *(_QWORD *)(v40 + 112);
      if ( v43 )
      {
        LODWORD(v44) = v43 + 2120;
LABEL_115:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"Updating Eap Method Id for discovery scenario",
          (_DWORD)v44,
          v42,
          (__int64)&v110);
LABEL_116:
        VPNIKEProtocolEngine::NotifyCaller(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 70) + 112LL) + 16LL), 13, &v102);
        v11 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_117;
      }
    }
    else
    {
      v42 = 0;
    }
    v44 = &v109;
    goto LABEL_115;
  }
LABEL_117:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
  {
    WPP_SF_(v11[2], 42, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v110) = 0;
    v45 = *((_QWORD *)this + 70);
    if ( v45 && (v46 = *(_QWORD *)(v45 + 112)) != 0 && *(_QWORD *)(v46 + 16) )
      v47 = *(unsigned int *)(v46 + 16);
    else
      v47 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v110, v47);
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_137;
    v48 = *((_QWORD *)this + 70);
    if ( v48 )
    {
      v49 = *(_QWORD *)(v48 + 112);
      if ( v49 )
        v50 = v49 + 2686;
      else
        v50 = 0;
      v51 = *(_QWORD *)(v48 + 112);
      if ( v51 )
      {
        LODWORD(v52) = v51 + 2120;
LABEL_136:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"Auth success :)",
          (_DWORD)v52,
          v50,
          (__int64)&v110);
LABEL_137:
        v11 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_138;
      }
    }
    else
    {
      v50 = 0;
    }
    v52 = &v109;
    goto LABEL_136;
  }
LABEL_138:
  if ( (*(_DWORD *)(v36 + 364) || *(_DWORD *)(v36 + 352)) && *((_DWORD *)v6 + 91) )
  {
    if ( (byte_1800AA941 & 8) == 0
      || ((LOWORD(v110) = 0, (v53 = *((_QWORD *)this + 70)) == 0)
       || (v54 = *(_QWORD *)(v53 + 112)) == 0
       || !*(_QWORD *)(v54 + 16)
        ? (v55 = 0xFFFFFFFFLL)
        : (v55 = *(unsigned int *)(v54 + 16)),
          ConvertPortNoToString(&v110, v55),
          (byte_1800AA941 & 8) == 0) )
    {
LABEL_157:
      v60 = RasSetEapUserDataAEx(
              *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 70) + 112LL) + 64LL),
              *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 70) + 112LL) + 72LL),
              *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 70) + 112LL) + 80LL),
              *((_QWORD *)v6 + 46),
              *((_DWORD *)v6 + 94),
              *((_DWORD *)v6 + 90));
      v100 = v60;
      if ( !v60 )
        goto LABEL_181;
      if ( (byte_1800AA941 & 8) == 0 )
      {
LABEL_175:
        if ( v60
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v60);
        }
        v100 = 0;
LABEL_181:
        v68 = (*((__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))&xmmword_1800AA980 + 1))(
                *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 70) + 112LL) + 24LL),
                13,
                *((_QWORD *)v6 + 46),
                *((unsigned int *)v6 + 94));
        v100 = v68;
        if ( !v68 )
        {
LABEL_203:
          ClientEAPAuthHandler::SaveCustomAuthData(
            this,
            (struct _RAS_CUSTOM_AUTH_DATA **)this + 213,
            *((_DWORD *)v6 + 94),
            *((unsigned __int8 **)v6 + 46));
          v11 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_204;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v68);
        }
        if ( (byte_1800AA941 & 8) == 0
          || ((LOWORD(v114) = 0, LOWORD(v110) = 0, (v69 = *((_QWORD *)this + 70)) == 0)
           || (v70 = *(_QWORD *)(v69 + 112)) == 0
           || !*(_QWORD *)(v70 + 16)
            ? (v71 = 0xFFFFFFFFLL)
            : (v71 = *(unsigned int *)(v70 + 16)),
              ConvertPortNoToString(&v110, v71),
              FormatRRASErrorString(
                &v114,
                L"RasSetConnectionUserData(CONNECTION_CUSTOMUSERDATA_INDEX) failed: %d",
                v100),
              (byte_1800AA941 & 8) == 0) )
        {
LABEL_202:
          v100 = 0;
          goto LABEL_203;
        }
        v72 = *((_QWORD *)this + 70);
        v73 = (_QWORD *)(v72 + 112);
        if ( v72 )
        {
          if ( *v73 )
            v74 = *v73 + 2686LL;
          else
            v74 = 0;
          if ( *v73 )
          {
            v75 = (__int128 *)(*v73 + 2120LL);
LABEL_201:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)&v114,
              (_DWORD)v75,
              v74,
              (__int64)&v110);
            goto LABEL_202;
          }
        }
        else
        {
          v74 = 0;
        }
        v75 = &v109;
        goto LABEL_201;
      }
      LOWORD(v114) = 0;
      LOWORD(v110) = 0;
      v61 = *((_QWORD *)this + 70);
      if ( v61 && (v62 = *(_QWORD *)(v61 + 112)) != 0 && *(_QWORD *)(v62 + 16) )
        v63 = *(unsigned int *)(v62 + 16);
      else
        v63 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v110, v63);
      FormatRRASErrorString(&v114, L"RasSetEapUserDataA failed: %d", v100);
      if ( (byte_1800AA941 & 8) == 0 )
      {
LABEL_174:
        v60 = v100;
        goto LABEL_175;
      }
      v64 = *((_QWORD *)this + 70);
      v65 = (_QWORD *)(v64 + 112);
      if ( v64 )
      {
        if ( *v65 )
          v66 = *v65 + 2686LL;
        else
          v66 = 0;
        if ( *v65 )
        {
          v67 = (__int128 *)(*v65 + 2120LL);
LABEL_173:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)&v114,
            (_DWORD)v67,
            v66,
            (__int64)&v110);
          goto LABEL_174;
        }
      }
      else
      {
        v66 = 0;
      }
      v67 = &v109;
      goto LABEL_173;
    }
    v56 = *((_QWORD *)this + 70);
    v57 = (_QWORD *)(v56 + 112);
    if ( v56 )
    {
      if ( *v57 )
        v58 = *v57 + 2686LL;
      else
        v58 = 0;
      if ( *v57 )
      {
        v59 = (__int128 *)(*v57 + 2120LL);
LABEL_156:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"Updating Eap User BLOB",
          (_DWORD)v59,
          v58,
          (__int64)&v110);
        goto LABEL_157;
      }
    }
    else
    {
      v58 = 0;
    }
    v59 = &v109;
    goto LABEL_156;
  }
LABEL_204:
  if ( *((_DWORD *)v6 + 96) && *((_DWORD *)v6 + 100) )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      WPP_SF_(v11[2], 45, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_226;
    LOWORD(v110) = 0;
    v76 = *((_QWORD *)this + 70);
    if ( v76 && (v77 = *(_QWORD *)(v76 + 112)) != 0 && *(_QWORD *)(v77 + 16) )
      v78 = *(unsigned int *)(v77 + 16);
    else
      v78 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v110, v78);
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_226;
    v79 = *((_QWORD *)this + 70);
    v80 = (_QWORD *)(v79 + 112);
    if ( v79 )
    {
      if ( *v80 )
        v81 = *v80 + 2686LL;
      else
        v81 = 0;
      if ( *v80 )
      {
        v82 = (__int128 *)(*v80 + 2120LL);
LABEL_225:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"Updating Eap Configuration BLOB",
          (_DWORD)v82,
          v81,
          (__int64)&v110);
LABEL_226:
        VPNIKEProtocolEngine::NotifyCaller(
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 70) + 112LL) + 16LL),
          12,
          (struct _PPPAP_RESULT *)((char *)v6 + 392));
        ClientEAPAuthHandler::SaveCustomAuthData(
          this,
          (struct _RAS_CUSTOM_AUTH_DATA **)this + 212,
          *((_DWORD *)v6 + 100),
          *((unsigned __int8 **)v6 + 49));
        goto LABEL_227;
      }
    }
    else
    {
      v81 = 0;
    }
    v82 = &v109;
    goto LABEL_225;
  }
LABEL_227:
  v34 = ClientEAPAuthHandler::RetrieveAndSaveAuthAttributes(this, *((struct _RAS_AUTH_ATTRIBUTE **)v6 + 36));
  v100 = v34;
  if ( !v34 )
  {
    *((_QWORD *)this + 218) = *((_QWORD *)v6 + 36);
    goto LABEL_233;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_239;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v35 = 46;
    goto LABEL_89;
  }
LABEL_234:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
  {
    v12 = 51;
    goto LABEL_238;
  }
LABEL_239:
  if ( *((_DWORD *)v6 + 82) )
  {
    v9 = 11;
    v101 = 11;
    v83 = (void *)*((_QWORD *)this + 216);
    if ( v83 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v83);
      *(_OWORD *)((char *)this + 1720) = 0;
      *((_QWORD *)this + 217) = 0;
    }
  }
  else if ( !v8 )
  {
    goto LABEL_304;
  }
  SynchronizingEvent = CreateSynchronizingEvent(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 70) + 112LL) + 8LL));
  v100 = SynchronizingEvent;
  if ( SynchronizingEvent )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids,
        SynchronizingEvent);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_304;
    LOWORD(v114) = 0;
    LOWORD(v110) = 0;
    v86 = *((_QWORD *)this + 70);
    if ( v86 )
    {
      v87 = *(_QWORD *)(v86 + 112);
      if ( v87 )
      {
        if ( *(_QWORD *)(v87 + 16) )
          v10 = *(_DWORD *)(v87 + 16);
      }
    }
    ConvertPortNoToString(&v110, v10);
    FormatRRASErrorString(&v114, L"CreateSynchronizingEvent failed: %d", v100);
    goto LABEL_254;
  }
  v92 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v9);
    v92 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 == 2 )
  {
    if ( v92 != &WPP_GLOBAL_Control && (*((_BYTE *)v92 + 28) & 1) != 0 && *((_BYTE *)v92 + 25) >= 5u )
      WPP_SF_(v92[2], 54, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
    v93 = (_OWORD *)((char *)v6 + 8);
  }
  else if ( v9 == 7 )
  {
    if ( v92 != &WPP_GLOBAL_Control && (*((_BYTE *)v92 + 28) & 1) != 0 && *((_BYTE *)v92 + 25) >= 5u )
      WPP_SF_(v92[2], 55, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
    v93 = 0;
  }
  else
  {
    v93 = 0;
    if ( v9 == 11 )
    {
      if ( v92 != &WPP_GLOBAL_Control && (*((_BYTE *)v92 + 28) & 1) != 0 && *((_BYTE *)v92 + 25) >= 5u )
        WPP_SF_(v92[2], 56, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
      v93 = (_OWORD *)((char *)v6 + 336);
    }
  }
  VPNIKEProtocolEngine::NotifyCaller(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 70) + 112LL) + 16LL), v9, v93);
  LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 70) + 160LL));
  v94 = WaitOnSynchronizingEvent(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 70) + 112LL) + 8LL));
  v100 = v94;
  if ( v94
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v94);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 70) + 160LL));
  if ( v100 )
  {
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_303;
    LOWORD(v114) = 0;
    LOWORD(v110) = 0;
    v95 = *((_QWORD *)this + 70);
    if ( v95 )
    {
      v96 = *(_QWORD *)(v95 + 112);
      if ( v96 )
      {
        if ( *(_QWORD *)(v96 + 16) )
          v10 = *(_DWORD *)(v96 + 16);
      }
    }
    ConvertPortNoToString(&v110, v10);
    FormatRRASErrorString(&v114, L"WaitOnSynchronizingEvent failed: %d", v100);
LABEL_254:
    if ( (byte_1800AA941 & 4) == 0 )
    {
LABEL_303:
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_304;
    }
    v88 = *((_QWORD *)this + 70);
    v89 = (_QWORD *)(v88 + 112);
    if ( v88 )
    {
      if ( *v89 )
        v90 = *v89 + 2686LL;
      else
        v90 = 0;
      if ( *v89 )
      {
        v91 = (__int128 *)(*v89 + 2120LL);
LABEL_263:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v114,
          (_DWORD)v91,
          v90,
          (__int64)&v110);
        goto LABEL_303;
      }
    }
    else
    {
      v90 = 0;
    }
    v91 = &v109;
    goto LABEL_263;
  }
  v97 = ClientEAPAuthHandler::ProcessInteractiveUIRequest(
          this,
          (const enum _PROTOCOL_RESULT_ID *)&v101,
          a3,
          *((unsigned __int8 **)&v102 + 1));
  v100 = v97;
  if ( !v97 )
    goto LABEL_303;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_308;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v97);
    goto LABEL_303;
  }
LABEL_304:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 6u )
    WPP_SF_d(v11[2], 59, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v100);
LABEL_308:
  v98 = v100;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v103);
  return v98;
}

```

## disassembly

```asm
0x180044ad0  push    rbp
0x180044ad2  push    rbx
0x180044ad3  push    rsi
0x180044ad4  push    rdi
0x180044ad5  push    r12
0x180044ad7  push    r13
0x180044ad9  push    r14
0x180044adb  push    r15
0x180044add  lea     rbp, [rsp-7E8h]
0x180044ae5  sub     rsp, 8E8h
0x180044aec  mov     rax, cs:__security_cookie
0x180044af3  xor     rax, rsp
0x180044af6  mov     [rbp+820h+var_50], rax
0x180044afd  mov     rbx, r9
0x180044b00  mov     [rsp+920h+var_8D0], rbx
0x180044b05  mov     r13, r8
0x180044b08  mov     rsi, rdx
0x180044b0b  mov     rdi, rcx
0x180044b0e  lea     rax, WPP_GLOBAL_Control
0x180044b15  xor     r15d, r15d
0x180044b18  mov     r8, cs:WPP_GLOBAL_Control
0x180044b1f  cmp     r8, rax
0x180044b22  jz      short loc_180044B68
0x180044b24  test    byte ptr [r8+1Ch], 1
0x180044b29  jz      short loc_180044B68
0x180044b2b  cmp     byte ptr [r8+19h], 6
0x180044b30  jb      short loc_180044B68
0x180044b32  cmp     [rdx+148h], r15d
0x180044b39  setnz   dl
0x180044b3c  cmp     [rsi+0Ch], r15d
0x180044b40  setnz   cl
0x180044b43  mov     eax, [rsi+168h]
0x180044b49  mov     [rsp+920h+var_8E8], eax
0x180044b4d  mov     [rsp+920h+var_8F0], dl
0x180044b51  mov     byte ptr [rsp+920h+var_8F8], cl
0x180044b55  mov     eax, [rsi+8]
0x180044b58  mov     dword ptr [rsp+920h+var_900], eax
0x180044b5c  mov     r9d, [rsi]
0x180044b5f  mov     rcx, [r8+10h]
0x180044b63  call    WPP_SF_dDccd
0x180044b68  mov     [rsp+920h+var_8E0], r15d
0x180044b6d  mov     r12d, r15d
0x180044b70  mov     r14d, r15d
0x180044b73  mov     [rsp+920h+var_8DC], r15d
0x180044b78  mov     [rbp+820h+var_850], r15d
0x180044b7c  xor     edx, edx; Val
0x180044b7e  mov     r8d, 7FCh; Size
0x180044b84  lea     rcx, [rbp+820h+var_84C]; void *
0x180044b88  call    memset_0
0x180044b8d  mov     [rbp+820h+var_880], r15d
0x180044b91  xorps   xmm0, xmm0
0x180044b94  xor     eax, eax
0x180044b96  movups  [rbp+820h+var_87C], xmm0
0x180044b9a  movups  [rbp+820h+var_86C], xmm0
0x180044b9e  mov     [rbp+820h+var_85C], eax
0x180044ba1  movups  [rbp+820h+var_890], xmm0
0x180044ba5  xorps   xmm1, xmm1
0x180044ba8  movdqu  [rsp+920h+var_8C0], xmm1
0x180044bae  mov     [rsp+920h+var_8C8], r15
0x180044bb3  movdqu  [rsp+920h+var_8B0], xmm0
0x180044bb9  mov     [rbp+820h+var_8A0], r15
0x180044bbd  or      r15d, 0FFFFFFFFh
0x180044bc1  mov     [rbp+820h+var_898], r15d
0x180044bc5  mov     [rbp+820h+var_894], eax
0x180044bc8  test    cs:byte_1800AA941, 8
0x180044bcf  jz      short loc_180044BFA
0x180044bd1  mov     rax, [rdi+230h]
0x180044bd8  mov     [rsp+920h+var_900], rax; void *
0x180044bdd  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180044be4  lea     r8, [rsp+920h+var_8E0]; unsigned int *
0x180044be9  lea     rdx, aClienteapauthh_8; "ClientEAPAuthHandler::ProcessAuthResult"
0x180044bf0  lea     rcx, [rsp+920h+var_8C8]; this
0x180044bf5  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x180044bfa  xor     edx, edx; Val
0x180044bfc  mov     r8d, 108h; Size
0x180044c02  mov     rcx, r13; void *
0x180044c05  call    memset_0
0x180044c0a  mov     byte ptr [rbx], 0
0x180044c0d  mov     ecx, [rsi]
0x180044c0f  sub     ecx, 1
0x180044c12  jz      short loc_180044C61
0x180044c14  sub     ecx, 1
0x180044c17  jz      short loc_180044C61
0x180044c19  sub     ecx, 1
0x180044c1c  jz      short loc_180044C2C
0x180044c1e  sub     ecx, 1
0x180044c21  jz      short loc_180044C2C
0x180044c23  cmp     ecx, 1
0x180044c26  jnz     loc_180045744
0x180044c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180044c33  lea     rax, WPP_GLOBAL_Control
0x180044c3a  cmp     rcx, rax
0x180044c3d  jz      loc_18004577F
0x180044c43  test    byte ptr [rcx+1Ch], 1
0x180044c47  jz      loc_18004577F
0x180044c4d  cmp     byte ptr [rcx+19h], 5
0x180044c51  jb      loc_18004577F
0x180044c57  mov     edx, 27h ; '''
0x180044c5c  jmp     loc_180045768
0x180044c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180044c68  lea     rax, WPP_GLOBAL_Control
0x180044c6f  cmp     rcx, rax
0x180044c72  jz      short loc_180044C9C
0x180044c74  test    byte ptr [rcx+1Ch], 1
0x180044c78  jz      short loc_180044C9C
0x180044c7a  cmp     byte ptr [rcx+19h], 5
0x180044c7e  jb      short loc_180044C9C
0x180044c80  mov     edx, 28h ; '('
0x180044c85  lea     r8, WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids
0x180044c8c  mov     rcx, [rcx+10h]
0x180044c90  call    WPP_SF_
0x180044c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180044c9c  lea     rbx, [rdi+119h]
0x180044ca3  cmp     byte ptr [rbx], 0
0x180044ca6  jz      loc_180044D77
0x180044cac  test    cs:byte_1800AA941, 8
0x180044cb3  jz      loc_180044D77
0x180044cb9  xor     eax, eax
0x180044cbb  mov     word ptr [rbp+820h+var_850], ax
0x180044cbf  mov     word ptr [rbp+820h+var_880], ax
0x180044cc3  mov     rax, [rdi+230h]
0x180044cca  test    rax, rax
0x180044ccd  jz      short loc_180044CE4
0x180044ccf  mov     rax, [rax+70h]
0x180044cd3  test    rax, rax
0x180044cd6  jz      short loc_180044CE4
0x180044cd8  cmp     qword ptr [rax+10h], 0
0x180044cdd  jz      short loc_180044CE4
0x180044cdf  mov     edx, [rax+10h]
0x180044ce2  jmp     short loc_180044CE7
0x180044ce4  mov     edx, r15d
0x180044ce7  lea     rcx, [rbp+820h+var_880]
0x180044ceb  call    ConvertPortNoToString
0x180044cf0  mov     r8, rbx
0x180044cf3  lea     rdx, aLocalUserS; "Local User:%S"
0x180044cfa  lea     rcx, [rbp+820h+var_850]
0x180044cfe  call    FormatRRASErrorString
0x180044d03  test    cs:byte_1800AA941, 8
0x180044d0a  jz      short loc_180044D70
0x180044d0c  mov     rcx, [rdi+230h]
0x180044d13  lea     rax, [rcx+70h]
0x180044d17  test    rcx, rcx
0x180044d1a  jz      short loc_180044D45
0x180044d1c  mov     rdx, [rax]
0x180044d1f  test    rdx, rdx
0x180044d22  jz      short loc_180044D2D
0x180044d24  lea     rcx, [rdx+0A7Eh]
0x180044d2b  jmp     short loc_180044D34
0x180044d2d  test    rcx, rcx
0x180044d30  jz      short loc_180044D45
0x180044d32  xor     ecx, ecx
0x180044d34  mov     rdx, [rax]
0x180044d37  test    rdx, rdx
0x180044d3a  jz      short loc_180044D47
0x180044d3c  lea     r9, [rdx+848h]
0x180044d43  jmp     short loc_180044D4B
0x180044d45  xor     ecx, ecx
0x180044d47  lea     r9, [rbp+820h+var_890]
0x180044d4b  lea     rax, [rbp+820h+var_880]
0x180044d4f  mov     [rsp+920h+var_8F8], rax
0x180044d54  mov     [rsp+920h+var_900], rcx
0x180044d59  lea     r8, [rbp+820h+var_850]
0x180044d5d  lea     rdx, RasVpnIkeParamTraceInfo
0x180044d64  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180044d6b  call    McTemplateU0zjzz_EventWriteTransfer
0x180044d70  mov     rcx, cs:WPP_GLOBAL_Control
0x180044d77  cmp     dword ptr [rsi+8], 0
0x180044d7b  jz      loc_180045028
0x180044d81  cmp     dword ptr [rsi+8], 288h
0x180044d88  jz      loc_180044FE9
0x180044d8e  lea     rax, WPP_GLOBAL_Control
0x180044d95  cmp     rcx, rax
0x180044d98  jz      short loc_180044DC9
0x180044d9a  test    byte ptr [rcx+1Ch], 1
0x180044d9e  jz      short loc_180044DC9
0x180044da0  cmp     byte ptr [rcx+19h], 5
0x180044da4  jb      short loc_180044DC9
0x180044da6  mov     edx, 30h ; '0'
0x180044dab  lea     r8, WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids
0x180044db2  mov     rcx, [rcx+10h]
0x180044db6  call    WPP_SF_
0x180044dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180044dc2  lea     rax, WPP_GLOBAL_Control
0x180044dc9  cmp     dword ptr [rsi+0Ch], 0
0x180044dcd  jz      loc_180044ECD
0x180044dd3  cmp     rcx, rax
0x180044dd6  jz      short loc_180044E00
0x180044dd8  test    byte ptr [rcx+1Ch], 1
0x180044ddc  jz      short loc_180044E00
0x180044dde  cmp     byte ptr [rcx+19h], 5
0x180044de2  jb      short loc_180044E00
0x180044de4  mov     edx, 31h ; '1'
0x180044de9  lea     r8, WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids
0x180044df0  mov     rcx, [rcx+10h]
0x180044df4  call    WPP_SF_
0x180044df9  mov     rcx, cs:WPP_GLOBAL_Control
0x180044e00  test    cs:byte_1800AA941, 8
0x180044e07  jz      loc_180044EB7
0x180044e0d  xor     eax, eax
0x180044e0f  mov     word ptr [rbp+820h+var_880], ax
0x180044e13  mov     rax, [rdi+230h]
0x180044e1a  test    rax, rax
0x180044e1d  jz      short loc_180044E34
0x180044e1f  mov     rax, [rax+70h]
0x180044e23  test    rax, rax
0x180044e26  jz      short loc_180044E34
0x180044e28  cmp     qword ptr [rax+10h], 0
0x180044e2d  jz      short loc_180044E34
0x180044e2f  mov     edx, [rax+10h]
0x180044e32  jmp     short loc_180044E37
0x180044e34  mov     edx, r15d
0x180044e37  lea     rcx, [rbp+820h+var_880]
0x180044e3b  call    ConvertPortNoToString
0x180044e40  test    cs:byte_1800AA941, 8
0x180044e47  jz      short loc_180044EB0
0x180044e49  mov     rcx, [rdi+230h]
0x180044e50  lea     rax, [rcx+70h]
0x180044e54  test    rcx, rcx
0x180044e57  jz      short loc_180044E82
0x180044e59  mov     rdx, [rax]
0x180044e5c  test    rdx, rdx
0x180044e5f  jz      short loc_180044E6A
0x180044e61  lea     rcx, [rdx+0A7Eh]
0x180044e68  jmp     short loc_180044E71
0x180044e6a  test    rcx, rcx
0x180044e6d  jz      short loc_180044E82
0x180044e6f  xor     ecx, ecx
0x180044e71  mov     rdx, [rax]
0x180044e74  test    rdx, rdx
0x180044e77  jz      short loc_180044E84
0x180044e79  lea     r9, [rdx+848h]
0x180044e80  jmp     short loc_180044E88
0x180044e82  xor     ecx, ecx
0x180044e84  lea     r9, [rbp+820h+var_890]
0x180044e88  lea     rax, [rbp+820h+var_880]
0x180044e8c  mov     [rsp+920h+var_8F8], rax
0x180044e91  mov     [rsp+920h+var_900], rcx
0x180044e96  lea     r8, aSendingAuthRet; "Sending auth retry message to UI"
0x180044e9d  lea     rdx, RasVpnIkeParamTraceInfo
0x180044ea4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180044eab  call    McTemplateU0zjzz_EventWriteTransfer
0x180044eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180044eb7  mov     r14d, 2
0x180044ebd  mov     r12d, 1
0x180044ec3  mov     [rsp+920h+var_8DC], r14d
0x180044ec8  jmp     loc_18004574B
0x180044ecd  test    cs:byte_1800AA941, 4
0x180044ed4  jz      loc_180044F99
0x180044eda  xor     eax, eax
0x180044edc  mov     word ptr [rbp+820h+var_850], ax
0x180044ee0  mov     word ptr [rbp+820h+var_880], ax
0x180044ee4  mov     rax, [rdi+230h]
0x180044eeb  test    rax, rax
0x180044eee  jz      short loc_180044F05
0x180044ef0  mov     rax, [rax+70h]
0x180044ef4  test    rax, rax
0x180044ef7  jz      short loc_180044F05
0x180044ef9  cmp     qword ptr [rax+10h], 0
0x180044efe  jz      short loc_180044F05
0x180044f00  mov     edx, [rax+10h]
0x180044f03  jmp     short loc_180044F08
0x180044f05  mov     edx, r15d
0x180044f08  lea     rcx, [rbp+820h+var_880]
0x180044f0c  call    ConvertPortNoToString
0x180044f11  mov     r8d, [rsi+8]
0x180044f15  lea     rdx, aAuthFailedD; "Auth failed :( %d"
0x180044f1c  lea     rcx, [rbp+820h+var_850]
0x180044f20  call    FormatRRASErrorString
0x180044f25  test    cs:byte_1800AA941, 4
0x180044f2c  jz      short loc_180044F92
0x180044f2e  mov     rcx, [rdi+230h]
0x180044f35  lea     rax, [rcx+70h]
0x180044f39  test    rcx, rcx
0x180044f3c  jz      short loc_180044F67
0x180044f3e  mov     rdx, [rax]
0x180044f41  test    rdx, rdx
0x180044f44  jz      short loc_180044F4F
0x180044f46  lea     rcx, [rdx+0A7Eh]
0x180044f4d  jmp     short loc_180044F56
0x180044f4f  test    rcx, rcx
0x180044f52  jz      short loc_180044F67
0x180044f54  xor     ecx, ecx
0x180044f56  mov     rdx, [rax]
0x180044f59  test    rdx, rdx
0x180044f5c  jz      short loc_180044F69
0x180044f5e  lea     r9, [rdx+848h]
0x180044f65  jmp     short loc_180044F6D
0x180044f67  xor     ecx, ecx
0x180044f69  lea     r9, [rbp+820h+var_890]
0x180044f6d  lea     rax, [rbp+820h+var_880]
0x180044f71  mov     [rsp+920h+var_8F8], rax
0x180044f76  mov     [rsp+920h+var_900], rcx
0x180044f7b  lea     r8, [rbp+820h+var_850]
0x180044f7f  lea     rdx, RasVpnIkeParamTraceError
0x180044f86  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180044f8d  call    McTemplateU0zjzz_EventWriteTransfer
0x180044f92  mov     rcx, cs:WPP_GLOBAL_Control
0x180044f99  mov     eax, [rsi+8]
0x180044f9c  mov     [rsp+920h+var_8E0], eax
0x180044fa0  test    eax, eax
  ... truncated ...
```
