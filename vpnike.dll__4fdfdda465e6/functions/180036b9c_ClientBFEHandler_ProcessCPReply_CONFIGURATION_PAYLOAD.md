# ClientBFEHandler::ProcessCPReply(_CONFIGURATION_PAYLOAD_ *)

- ea: `0x180036b9c`
- end: `0x1800380c3`
- name: `?ProcessCPReply@ClientBFEHandler@@IEAAKPEAU_CONFIGURATION_PAYLOAD_@@@Z`
- size: `5415`
- prototype: `__int64 __fastcall(ClientBFEHandler *this, struct _CONFIGURATION_PAYLOAD_ *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800367e0`

## callees

- `0x180004ab8`
- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180007894`
- `0x180036b9c`
- `0x180039fa8`
- `0x18003a0d4`
- `0x18004ac7c`
- `0x18004c824`
- `0x18004fc20`
- `0x1800502e0`
- `0x18005dce0`
- `0x18005de2c`
- `0x180065d28`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `WS2_32!__imp_ntohl` at `0x18003776e`
- `WS2_32!__imp_ntohl` at `0x18003776e`

## string_xrefs

- `0x1800375da`: `Already processed two INTERNAL_IP4_DNS attributes. Ignoring this attribute value.`
- `0x1800373a9`: `Already processed two INTERNAL_IP4_NBNS attributes. Ignoring this attribute value.`
- `0x180037e94`: `Already processed two INTERNAL_IP6_DNS attributes. Ignoring this attribute value.`

## pseudocode

```c
__int64 __fastcall ClientBFEHandler::ProcessCPReply(ClientBFEHandler *this, struct _CONFIGURATION_PAYLOAD_ *a2)
{
  PVOID *v4; // rbx
  _QWORD *v5; // rsi
  int v6; // r13d
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // r15d
  unsigned int v10; // edi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  __int128 *v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r9
  PVOID v19; // rcx
  __int64 v20; // r9
  unsigned int v21; // r8d
  __int64 *v22; // rsi
  BaseConnection *v23; // rcx
  unsigned int v24; // r8d
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // rcx
  __int128 *v31; // r9
  int v32; // edi
  PVOID *v33; // rcx
  int v34; // edx
  int v35; // edx
  int v36; // edx
  int v37; // edx
  int v38; // edx
  int v39; // edx
  int v40; // edx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int128 *v49; // r9
  const wchar_t *v50; // r8
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // rax
  __int64 v88; // rdx
  __int64 v89; // rax
  _DWORD *v90; // rax
  u_long v91; // ebx
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rdx
  __int64 v95; // rcx
  __int64 v96; // rdx
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int128 *v99; // r9
  __int64 v100; // rdx
  __int64 v101; // rdx
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rdx
  __int64 v105; // rcx
  __int64 v106; // rdx
  __int64 v107; // rcx
  int v108; // edx
  int v109; // edx
  int v110; // edx
  int v111; // edx
  int v112; // edx
  int v113; // edx
  __int64 v114; // rdx
  __int64 v115; // rdx
  __int64 v116; // rdx
  int v117; // r8d
  __int64 v118; // rax
  __int64 v119; // rdx
  __int64 v120; // rcx
  __int64 v121; // rdx
  __int64 v122; // rcx
  __int64 v123; // rdx
  int v124; // r8d
  __int64 v125; // rax
  __int64 v126; // rdx
  __int64 v127; // rcx
  __int64 v128; // rdx
  __int64 v129; // rcx
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // rdx
  __int64 v133; // rcx
  __int64 v134; // rdx
  __int64 v135; // rcx
  int v136; // ebx
  int v137; // edi
  unsigned int v139; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v140; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v141; // [rsp+50h] [rbp-B0h]
  __int128 v142; // [rsp+60h] [rbp-A0h]
  __int64 v143; // [rsp+70h] [rbp-90h]
  int v144; // [rsp+78h] [rbp-88h]
  int v145; // [rsp+7Ch] [rbp-84h]
  __int128 v146; // [rsp+80h] [rbp-80h] BYREF
  int v147; // [rsp+90h] [rbp-70h] BYREF
  __int128 v148; // [rsp+94h] [rbp-6Ch]
  __int128 v149; // [rsp+A4h] [rbp-5Ch]
  int v150; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v151[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v152; // [rsp+C8h] [rbp-38h]
  __int16 v153; // [rsp+D8h] [rbp-28h]
  int v154; // [rsp+E0h] [rbp-20h] BYREF
  char v155[2044]; // [rsp+E4h] [rbp-1Ch] BYREF
  unsigned __int16 v156[280]; // [rsp+8E0h] [rbp+7E0h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v139 = 0;
  memset_0(v156, 0, 0x222u);
  *(_OWORD *)v151 = 0;
  v152 = 0;
  v153 = 0;
  v5 = (_QWORD *)*((_QWORD *)this + 6);
  v6 = *(_DWORD *)(v5[14] + 1472LL);
  v154 = 0;
  memset_0(v155, 0, sizeof(v155));
  v147 = 0;
  v148 = 0;
  v149 = 0;
  v150 = 0;
  v146 = 0;
  v141 = 0;
  v140 = 0;
  v142 = 0;
  v143 = 0;
  v9 = -1;
  v144 = -1;
  v145 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v140,
      L"ClientBFEHandler::ProcessCPReply",
      &v139,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      v5);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
  {
    LOBYTE(v8) = v6 == 2;
    WPP_SF_c(v4[2], 31, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v8);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v10 = 87;
    v139 = 87;
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_28;
    LOWORD(v147) = 0;
    v11 = *((_QWORD *)this + 6);
    if ( v11 )
    {
      v12 = *(_QWORD *)(v11 + 112);
      if ( v12 )
      {
        if ( *(_QWORD *)(v12 + 16) )
          v9 = *(_DWORD *)(v12 + 16);
      }
    }
    ConvertPortNoToString(&v147, v9);
    if ( (byte_1800AA941 & 4) == 0 )
    {
LABEL_27:
      v10 = v139;
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( !v139 )
      {
LABEL_32:
        if ( v4 == &WPP_GLOBAL_Control || (*((_BYTE *)v4 + 28) & 1) == 0 || *((_BYTE *)v4 + 25) < 6u )
          goto LABEL_470;
        v17 = 33;
LABEL_36:
        v18 = v10;
        v19 = v4[2];
LABEL_468:
        WPP_SF_d(v19, v17, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v18);
LABEL_469:
        v10 = v139;
        goto LABEL_470;
      }
LABEL_28:
      if ( v4 == &WPP_GLOBAL_Control )
        goto LABEL_470;
      if ( (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      {
        WPP_SF_d(v4[2], 32, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v10);
        v10 = v139;
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_32;
    }
    v13 = *((_QWORD *)this + 6);
    v14 = (_QWORD *)(v13 + 112);
    if ( v13 )
    {
      if ( *v14 )
        v15 = *v14 + 2686LL;
      else
        v15 = 0;
      if ( *v14 )
      {
        v16 = (__int128 *)(*v14 + 2120LL);
LABEL_26:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Invalid param",
          (_DWORD)v16,
          v15,
          (__int64)&v147);
        goto LABEL_27;
      }
    }
    else
    {
      v15 = 0;
    }
    v16 = &v146;
    goto LABEL_26;
  }
  if ( *(_DWORD *)a2 != 2 )
  {
    v10 = 87;
    v139 = 87;
    if ( v4 == &WPP_GLOBAL_Control )
      goto LABEL_470;
    if ( (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
    {
      WPP_SF_d(v4[2], 34, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, 87);
      v10 = v139;
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 == &WPP_GLOBAL_Control || (*((_BYTE *)v4 + 28) & 1) == 0 || *((_BYTE *)v4 + 25) < 6u )
      goto LABEL_470;
    v17 = 35;
    goto LABEL_36;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
  {
    v20 = *((_QWORD *)this + 6);
    WPP_SF_qIcdd(
      v4[2],
      *(int *)(v20 + 8),
      v7,
      *(_QWORD *)(v20 + 24),
      *(int *)(v20 + 8),
      *(_BYTE *)(v20 + 16) != 0,
      *(_DWORD *)(v20 + 88),
      *(_DWORD *)(v20 + 92));
  }
  VPNIKEProtocolEngine::NotifyCaller(*(_QWORD *)(*((_QWORD *)this + 6) + 24LL), 3, 0);
  v22 = (__int64 *)*((_QWORD *)a2 + 1);
  v23 = (BaseConnection *)*((_QWORD *)this + 6);
  if ( *(_DWORD *)(*((_QWORD *)v23 + 14) + 1472LL) != 2 )
    goto LABEL_68;
  BaseConnection::GetRemoteUserName(v23, v156, v21);
  BaseConnection::GetPortName(*((BaseConnection **)this + 6), v151, v24);
  v25 = *((_QWORD *)this + 6);
  if ( !*(_QWORD *)(v25 + 120) || (byte_1800AA941 & 8) == 0 )
    goto LABEL_68;
  LOWORD(v154) = 0;
  LOWORD(v147) = 0;
  if ( v25 && (v26 = *(_QWORD *)(v25 + 112)) != 0 && *(_QWORD *)(v26 + 16) )
    v27 = *(unsigned int *)(v26 + 16);
  else
    v27 = 0xFFFFFFFFLL;
  ConvertPortNoToString(&v147, v27);
  FormatRRASErrorString(
    &v154,
    L" username = %S portname = %S",
    *(_QWORD *)(*((_QWORD *)this + 6) + 120LL) + 8LL,
    *(_QWORD *)(*((_QWORD *)this + 6) + 112LL) + 1449LL);
  if ( (byte_1800AA941 & 8) == 0 )
    goto LABEL_68;
  v28 = *((_QWORD *)this + 6);
  v29 = (_QWORD *)(v28 + 112);
  if ( !v28 )
  {
    v30 = 0;
LABEL_66:
    v31 = &v146;
    goto LABEL_67;
  }
  if ( *v29 )
    v30 = *v29 + 2686LL;
  else
    v30 = 0;
  if ( !*v29 )
    goto LABEL_66;
  v31 = (__int128 *)(*v29 + 2120LL);
LABEL_67:
  McTemplateU0zjzz_EventWriteTransfer(
    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
    (unsigned int)RasVpnIkeParamTraceInfo,
    (unsigned int)&v154,
    (_DWORD)v31,
    v30,
    (__int64)&v147);
LABEL_68:
  v32 = 0;
  v33 = (PVOID *)WPP_GLOBAL_Control;
  while ( v22 )
  {
    if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
    {
      WPP_SF_d(v33[2], 37, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, *((unsigned int *)v22 + 2));
      v33 = (PVOID *)WPP_GLOBAL_Control;
    }
    v34 = *((_DWORD *)v22 + 2);
    if ( v34 > 23456 )
    {
      if ( v34 == 23457 )
      {
        if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
        {
          WPP_SF_(v33[2], 60, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
          v33 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v6 != 2 && *((_DWORD *)v22 + 3) == 16 )
        {
          *(_OWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 52LL) = *((_OWORD *)v22 + 1);
          goto LABEL_440;
        }
      }
    }
    else if ( v34 == 23456 )
    {
      if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
      {
        WPP_SF_(v33[2], 59, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
        v33 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 != 2 && *((_DWORD *)v22 + 3) == 4 )
      {
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 32LL) + 20LL) = *((_DWORD *)v22 + 4);
        goto LABEL_440;
      }
    }
    else if ( v34 > 8 )
    {
      v108 = v34 - 10;
      if ( v108 && (v109 = v108 - 1) != 0 && (v110 = v109 - 1) != 0 )
      {
        v111 = v110 - 1;
        if ( !v111 )
          goto LABEL_85;
        v112 = v111 - 2;
        if ( !v112 )
          goto LABEL_85;
        v113 = v112 - 5;
        if ( v113 )
        {
          if ( v113 == 1 )
          {
            if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
            {
              WPP_SF_(v33[2], 62, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
              v33 = (PVOID *)WPP_GLOBAL_Control;
            }
            v114 = *(_QWORD *)(*((_QWORD *)this + 6) + 112LL);
            if ( *(_DWORD *)(v114 + 4252) == 1 && *((_DWORD *)v22 + 3) == 16 )
            {
              *(_BYTE *)(v114 + 4264) = 23;
              *(_OWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 112LL) + 4268LL) = *((_OWORD *)v22 + 1);
              goto LABEL_440;
            }
          }
        }
        else
        {
          if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
          {
            WPP_SF_(v33[2], 61, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
            v33 = (PVOID *)WPP_GLOBAL_Control;
          }
          v115 = *(_QWORD *)(*((_QWORD *)this + 6) + 112LL);
          if ( *(_DWORD *)(v115 + 4252) == 1 && *((_DWORD *)v22 + 3) == 4 )
          {
            *(_BYTE *)(v115 + 4264) = 2;
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 112LL) + 4268LL) = *((_DWORD *)v22 + 4);
            goto LABEL_440;
          }
        }
      }
      else
      {
        if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
        {
          WPP_SF_(v33[2], 53, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
          v33 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( *((_DWORD *)v22 + 3) == 16 )
        {
          if ( *((_DWORD *)v22 + 2) == 10 )
          {
            if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
            {
              WPP_SF_(v33[2], 54, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
              v33 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( (v32 & 0x100) == 0 )
            {
              *(_OWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 68LL) = *((_OWORD *)v22 + 1);
              if ( IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 68LL)) )
                goto LABEL_440;
              v32 |= v117;
              if ( (byte_1800AA941 & 8) == 0 )
                goto LABEL_440;
              LOWORD(v147) = 0;
              if ( v116 && (v118 = *(_QWORD *)(v116 + 112)) != 0 && *(_QWORD *)(v118 + 16) )
                v119 = *(unsigned int *)(v118 + 16);
              else
                v119 = 0xFFFFFFFFLL;
              ConvertPortNoToString(&v147, v119);
              if ( (byte_1800AA941 & 8) == 0 )
                goto LABEL_440;
              v120 = *((_QWORD *)this + 6);
              if ( v120 )
              {
                v121 = *(_QWORD *)(v120 + 112);
                if ( v121 )
                  v47 = v121 + 2686;
                else
                  v47 = 0;
                v122 = *(_QWORD *)(v120 + 112);
                if ( v122 )
                {
                  LODWORD(v49) = v122 + 2120;
LABEL_385:
                  v50 = L"Processed first INTERNAL_IP6_DNS";
                  goto LABEL_126;
                }
              }
              else
              {
                v47 = 0;
              }
              v49 = &v146;
              goto LABEL_385;
            }
            if ( (v32 & 0x40000) == 0 )
            {
              *(_OWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 84LL) = *((_OWORD *)v22 + 1);
              if ( IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 84LL)) )
                goto LABEL_440;
              v32 |= v124;
              if ( (byte_1800AA941 & 8) == 0 )
                goto LABEL_440;
              LOWORD(v147) = 0;
              if ( v123 && (v125 = *(_QWORD *)(v123 + 112)) != 0 && *(_QWORD *)(v125 + 16) )
                v126 = *(unsigned int *)(v125 + 16);
              else
                v126 = 0xFFFFFFFFLL;
              ConvertPortNoToString(&v147, v126);
              if ( (byte_1800AA941 & 8) == 0 )
                goto LABEL_440;
              v127 = *((_QWORD *)this + 6);
              if ( v127 )
              {
                v128 = *(_QWORD *)(v127 + 112);
                if ( v128 )
                  v47 = v128 + 2686;
                else
                  v47 = 0;
                v129 = *(_QWORD *)(v127 + 112);
                if ( v129 )
                {
                  LODWORD(v49) = v129 + 2120;
LABEL_403:
                  v50 = L"Processed second INTERNAL_IP6_DNS";
                  goto LABEL_126;
                }
              }
              else
              {
                v47 = 0;
              }
              v49 = &v146;
              goto LABEL_403;
            }
            if ( (byte_1800AA941 & 8) == 0 )
              goto LABEL_441;
            LOWORD(v147) = 0;
            v130 = *((_QWORD *)this + 6);
            if ( v130 && (v131 = *(_QWORD *)(v130 + 112)) != 0 && *(_QWORD *)(v131 + 16) )
              v132 = *(unsigned int *)(v131 + 16);
            else
              v132 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v147, v132);
            if ( (byte_1800AA941 & 8) == 0 )
              goto LABEL_440;
            v133 = *((_QWORD *)this + 6);
            if ( v133 )
            {
              v134 = *(_QWORD *)(v133 + 112);
              if ( v134 )
                v47 = v134 + 2686;
              else
                v47 = 0;
              v135 = *(_QWORD *)(v133 + 112);
              if ( v135 )
              {
                LODWORD(v49) = v135 + 2120;
LABEL_419:
                v50 = L"Already processed two INTERNAL_IP6_DNS attributes. Ignoring this attribute value.";
                goto LABEL_126;
              }
            }
            else
            {
              v47 = 0;
            }
            v49 = &v146;
            goto LABEL_419;
          }
          if ( *((_DWORD *)v22 + 2) != 11 )
          {
            if ( *((_DWORD *)v22 + 2) != 12 )
              goto LABEL_441;
            if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
              WPP_SF_(v33[2], 56, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
            *(_OWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 100LL) = *((_OWORD *)v22 + 1);
            goto LABEL_440;
          }
          if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
          {
            v41 = 55;
LABEL_291:
            WPP_SF_(v33[2], v41, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
LABEL_440:
            v33 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
        else if ( !*((_DWORD *)v22 + 3) )
        {
          v139 = 13;
          if ( v33 == &WPP_GLOBAL_Control )
            goto LABEL_469;
          if ( (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 2u )
          {
            v101 = 57;
LABEL_301:
            WPP_SF_d(v33[2], v101, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, 13);
            v33 = (PVOID *)WPP_GLOBAL_Control;
          }
LABEL_463:
          if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 6u )
          {
            v17 = 65;
            v18 = v139;
            goto LABEL_467;
          }
          goto LABEL_469;
        }
      }
    }
    else if ( v34 == 8 )
    {
      if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
      {
        WPP_SF_(v33[2], 52, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
        v33 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( (v32 & 0x80u) == 0 && *((_DWORD *)v22 + 3) == 17 )
      {
        if ( v22[3] )
        {
          *(_OWORD *)*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) = *((_OWORD *)v22 + 1);
          *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 48LL) = *((_BYTE *)v22 + 32);
          v32 |= 0x80u;
          goto LABEL_440;
        }
        if ( (byte_1800AA941 & 8) == 0 )
          goto LABEL_441;
        LOWORD(v147) = 0;
        v102 = *((_QWORD *)this + 6);
        if ( v102 && (v103 = *(_QWORD *)(v102 + 112)) != 0 && *(_QWORD *)(v103 + 16) )
          v104 = *(unsigned int *)(v103 + 16);
        else
          v104 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v147, v104);
        if ( (byte_1800AA941 & 8) == 0 )
          goto LABEL_440;
        v105 = *((_QWORD *)this + 6);
        if ( v105 )
        {
          v106 = *(_QWORD *)(v105 + 112);
          if ( v106 )
            v47 = v106 + 2686;
          else
            v47 = 0;
          v107 = *(_QWORD *)(v105 + 112);
          if ( v107 )
          {
            LODWORD(v49) = v107 + 2120;
            goto LABEL_325;
          }
        }
        else
        {
          v47 = 0;
        }
        v49 = &v146;
LABEL_325:
        v50 = L"Invalid IPv6 identifier received from server.";
LABEL_126:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (_DWORD)v50,
          (_DWORD)v49,
          v47,
          (__int64)&v147);
        goto LABEL_440;
      }
    }
    else
    {
      v35 = v34 - 1;
      if ( v35 )
      {
        v36 = v35 - 1;
        if ( v36 )
        {
          v37 = v36 - 1;
          if ( v37 )
          {
            v38 = v37 - 1;
            if ( v38 )
            {
              v39 = v38 - 1;
              if ( !v39 )
                goto LABEL_85;
              v40 = v39 - 1;
              if ( v40 )
              {
                if ( v40 != 1 )
                  goto LABEL_441;
LABEL_85:
                if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
                {
                  v41 = 58;
                  goto LABEL_291;
                }
                goto LABEL_441;
              }
            }
          }
        }
      }
      if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
      {
        WPP_SF_(v33[2], 38, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
        v33 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( *((_DWORD *)v22 + 3) == 4 )
      {
        switch ( *((_DWORD *)v22 + 2) )
        {
          case 1:
            if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
            {
              WPP_SF_(v33[2], 39, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
              v33 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( (v32 & 1) != 0 )
            {
              if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
              {
                v41 = 46;
                goto LABEL_291;
              }
            }
            else
            {
              **(_DWORD **)(*((_QWORD *)this + 6) + 32LL) = *((_DWORD *)v22 + 4);
              if ( **(_DWORD **)(*((_QWORD *)this + 6) + 32LL) )
              {
                if ( v6 == 2 )
                {
                  v33 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                    v33 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  v87 = *((_QWORD *)this + 6);
                  v88 = *(_QWORD *)(v87 + 120);
                  if ( !v88 )
                  {
                    if ( v33 == &WPP_GLOBAL_Control || (*((_BYTE *)v33 + 28) & 1) == 0 || *((_BYTE *)v33 + 25) < 5u )
                      goto LABEL_286;
                    v100 = 44;
                    goto LABEL_284;
                  }
                  v89 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v88 + 16LL))(*(_QWORD *)(v87 + 120));
                  v90 = RasAuthAttributeGet(8, v89);
                  if ( !v90 )
                  {
                    v33 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
                    {
                      goto LABEL_286;
                    }
                    v100 = 43;
                    goto LABEL_284;
                  }
                  v91 = ntohl(v90[2]);
                  if ( (byte_1800AA941 & 8) != 0 )
                  {
                    LOWORD(v154) = 0;
                    LOWORD(v147) = 0;
                    v92 = *((_QWORD *)this + 6);
                    if ( v92 && (v93 = *(_QWORD *)(v92 + 112)) != 0 && *(_QWORD *)(v93 + 16) )
                      v94 = *(unsigned int *)(v93 + 16);
                    else
                      v94 = 0xFFFFFFFFLL;
                    ConvertPortNoToString(&v147, v94);
                    FormatRRASErrorString(&v154, L"ProcessCP IpAddressToHandout: 0x%x", v91);
                    if ( (byte_1800AA941 & 8) != 0 )
                    {
                      v95 = *((_QWORD *)this + 6);
                      if ( v95 )
                      {
                        v96 = *(_QWORD *)(v95 + 112);
                        if ( v96 )
                          v97 = v96 + 2686;
                        else
                          v97 = 0;
                        v98 = *(_QWORD *)(v95 + 112);
                        if ( v98 )
                        {
                          LODWORD(v99) = v98 + 2120;
                          goto LABEL_265;
                        }
                      }
                      else
                      {
                        v97 = 0;
                      }
                      v99 = &v146;
LABEL_265:
                      McTemplateU0zjzz_EventWriteTransfer(
                        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        (unsigned int)RasVpnIkeParamTraceInfo,
                        (unsigned int)&v154,
                        (_DWORD)v99,
                        v97,
                        (__int64)&v147);
                    }
                  }
                  if ( v91 == -16777217 )
                  {
                    v33 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                    {
                      v100 = 41;
                      goto LABEL_284;
                    }
LABEL_286:
                    v32 |= 1u;
                    break;
                  }
                  if ( v91 != -1 )
                  {
                    v33 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
                    {
                      goto LABEL_286;
                    }
                    v100 = 42;
LABEL_284:
                    WPP_SF_(v33[2], v100, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                  }
                }
                v33 = (PVOID *)WPP_GLOBAL_Control;
                goto LABEL_286;
              }
              v33 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v41 = 45;
                goto LABEL_291;
              }
            }
            break;
          case 2:
            if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
            {
              WPP_SF_(v33[2], 47, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
              v33 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( (byte_1800AA941 & 8) != 0 )
            {
              LOWORD(v147) = 0;
              v81 = *((_QWORD *)this + 6);
              if ( v81 && (v82 = *(_QWORD *)(v81 + 112)) != 0 && *(_QWORD *)(v82 + 16) )
                v83 = *(unsigned int *)(v82 + 16);
              else
                v83 = 0xFFFFFFFFLL;
              ConvertPortNoToString(&v147, v83);
              if ( (byte_1800AA941 & 8) == 0 )
                goto LABEL_440;
              v84 = *((_QWORD *)this + 6);
              if ( v84 )
              {
                v85 = *(_QWORD *)(v84 + 112);
                if ( v85 )
                  v47 = v85 + 2686;
                else
                  v47 = 0;
                v86 = *(_QWORD *)(v84 + 112);
                if ( v86 )
                {
                  LODWORD(v49) = v86 + 2120;
LABEL_236:
                  v50 = L"Ignoring INTERNAL_IP4_NETMASK attribute";
                  goto LABEL_126;
                }
              }
              else
              {
                v47 = 0;
              }
              v49 = &v146;
              goto LABEL_236;
            }
            break;
          case 3:
            if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
            {
              WPP_SF_(v33[2], 48, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
              v33 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( (v32 & 4) == 0 )
            {
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 32LL) + 32LL) = *((_DWORD *)v22 + 4);
              v63 = *((_QWORD *)this + 6);
              if ( !*(_DWORD *)(*(_QWORD *)(v63 + 32) + 32LL) )
                goto LABEL_440;
              v32 |= 4u;
              if ( (byte_1800AA941 & 8) == 0 )
                goto LABEL_440;
              LOWORD(v147) = 0;
              if ( v63 && (v64 = *(_QWORD *)(v63 + 112)) != 0 && *(_QWORD *)(v64 + 16) )
                v65 = *(unsigned int *)(v64 + 16);
              else
                v65 = 0xFFFFFFFFLL;
              ConvertPortNoToString(&v147, v65);
              if ( (byte_1800AA941 & 8) == 0 )
                goto LABEL_440;
              v66 = *((_QWORD *)this + 6);
              if ( v66 )
              {
                v67 = *(_QWORD *)(v66 + 112);
                if ( v67 )
                  v47 = v67 + 2686;
                else
                  v47 = 0;
                v68 = *(_QWORD *)(v66 + 112);
                if ( v68 )
                {
                  LODWORD(v49) = v68 + 2120;
LABEL_182:
                  v50 = L"Processed first INTERNAL_IP4_DNS";
                  goto LABEL_126;
                }
              }
              else
              {
                v47 = 0;
              }
              v49 = &v146;
              goto LABEL_182;
            }
            if ( (v32 & 0x10000) == 0 )
            {
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 32LL) + 36LL) = *((_DWORD *)v22 + 4);
              v69 = *((_QWORD *)this + 6);
              if ( !*(_DWORD *)(*(_QWORD *)(v69 + 32) + 36LL) )
                goto LABEL_440;
              v32 |= 0x10000u;
              if ( (byte_1800AA941 & 8) == 0 )
                goto LABEL_440;
              LOWORD(v147) = 0;
              if ( v69 && (v70 = *(_QWORD *)(v69 + 112)) != 0 && *(_QWORD *)(v70 + 16) )
                v71 = *(unsigned int *)(v70 + 16);
              else
                v71 = 0xFFFFFFFFLL;
              ConvertPortNoToString(&v147, v71);
              if ( (byte_1800AA941 & 8) == 0 )
                goto LABEL_440;
              v72 = *((_QWORD *)this + 6);
              if ( v72 )
              {
                v73 = *(_QWORD *)(v72 + 112);
                if ( v73 )
                  v47 = v73 + 2686;
                else
                  v47 = 0;
                v74 = *(_QWORD *)(v72 + 112);
                if ( v74 )
                {
                  LODWORD(v49) = v74 + 2120;
LABEL_200:
                  v50 = L"Processed second INTERNAL_IP4_DNS";
                  goto LABEL_126;
                }
              }
              else
              {
                v47 = 0;
              }
              v49 = &v146;
              goto LABEL_200;
            }
            if ( (byte_1800AA941 & 8) == 0 )
              break;
            LOWORD(v147) = 0;
            v75 = *((_QWORD *)this + 6);
            if ( v75 && (v76 = *(_QWORD *)(v75 + 112)) != 0 && *(_QWORD *)(v76 + 16) )
              v77 = *(unsigned int *)(v76 + 16);
            else
              v77 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v147, v77);
            if ( (byte_1800AA941 & 8) == 0 )
              goto LABEL_440;
            v78 = *((_QWORD *)this + 6);
            if ( v78 )
            {
              v79 = *(_QWORD *)(v78 + 112);
              if ( v79 )
                v47 = v79 + 2686;
              else
                v47 = 0;
              v80 = *(_QWORD *)(v78 + 112);
              if ( v80 )
              {
                LODWORD(v49) = v80 + 2120;
LABEL_216:
                v50 = L"Already processed two INTERNAL_IP4_DNS attributes. Ignoring this attribute value.";
                goto LABEL_126;
              }
            }
            else
            {
              v47 = 0;
            }
            v49 = &v146;
            goto LABEL_216;
          case 4:
            if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
            {
              WPP_SF_(v33[2], 49, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
              v33 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( (v32 & 8) == 0 )
            {
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 32LL) + 24LL) = *((_DWORD *)v22 + 4);
              v42 = *((_QWORD *)this + 6);
              if ( !*(_DWORD *)(*(_QWORD *)(v42 + 32) + 24LL) )
                goto LABEL_440;
              v32 |= 8u;
              if ( (byte_1800AA941 & 8) == 0 )
                goto LABEL_440;
              LOWORD(v147) = 0;
              if ( v42 && (v43 = *(_QWORD *)(v42 + 112)) != 0 && *(_QWORD *)(v43 + 16) )
                v44 = *(unsigned int *)(v43 + 16);
              else
                v44 = 0xFFFFFFFFLL;
              ConvertPortNoToString(&v147, v44);
              if ( (byte_1800AA941 & 8) == 0 )
                goto LABEL_440;
              v45 = *((_QWORD *)this + 6);
              if ( v45 )
              {
                v46 = *(_QWORD *)(v45 + 112);
                if ( v46 )
                  v47 = v46 + 2686;
                else
                  v47 = 0;
                v48 = *(_QWORD *)(v45 + 112);
                if ( v48 )
                {
                  LODWORD(v49) = v48 + 2120;
LABEL_125:
                  v50 = L"Processed first INTERNAL_IP4_NBNS";
                  goto LABEL_126;
                }
              }
              else
              {
                v47 = 0;
              }
              v49 = &v146;
              goto LABEL_125;
            }
            if ( (v32 & 0x20000) == 0 )
            {
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 32LL) + 28LL) = *((_DWORD *)v22 + 4);
              v51 = *((_QWORD *)this + 6);
              if ( !*(_DWORD *)(*(_QWORD *)(v51 + 32) + 28LL) )
                goto LABEL_440;
              v32 |= 0x20000u;
              if ( (byte_1800AA941 & 8) == 0 )
                goto LABEL_440;
              LOWORD(v147) = 0;
              if ( v51 && (v52 = *(_QWORD *)(v51 + 112)) != 0 && *(_QWORD *)(v52 + 16) )
                v53 = *(unsigned int *)(v52 + 16);
              else
                v53 = 0xFFFFFFFFLL;
              ConvertPortNoToString(&v147, v53);
              if ( (byte_1800AA941 & 8) == 0 )
                goto LABEL_440;
              v54 = *((_QWORD *)this + 6);
              if ( v54 )
              {
                v55 = *(_QWORD *)(v54 + 112);
                if ( v55 )
                  v47 = v55 + 2686;
                else
                  v47 = 0;
                v56 = *(_QWORD *)(v54 + 112);
                if ( v56 )
                {
                  LODWORD(v49) = v56 + 2120;
LABEL_144:
                  v50 = L"Processed second INTERNAL_IP4_NBNS";
                  goto LABEL_126;
                }
              }
              else
              {
                v47 = 0;
              }
              v49 = &v146;
              goto LABEL_144;
            }
            if ( (byte_1800AA941 & 8) == 0 )
              break;
            LOWORD(v147) = 0;
            v57 = *((_QWORD *)this + 6);
            if ( v57 && (v58 = *(_QWORD *)(v57 + 112)) != 0 && *(_QWORD *)(v58 + 16) )
              v59 = *(unsigned int *)(v58 + 16);
            else
              v59 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v147, v59);
            if ( (byte_1800AA941 & 8) == 0 )
              goto LABEL_440;
            v60 = *((_QWORD *)this + 6);
            if ( v60 )
            {
              v61 = *(_QWORD *)(v60 + 112);
              if ( v61 )
                v47 = v61 + 2686;
              else
                v47 = 0;
              v62 = *(_QWORD *)(v60 + 112);
              if ( v62 )
              {
                LODWORD(v49) = v62 + 2120;
LABEL_160:
                v50 = L"Already processed two INTERNAL_IP4_NBNS attributes. Ignoring this attribute value.";
                goto LABEL_126;
              }
            }
            else
            {
              v47 = 0;
            }
            v49 = &v146;
            goto LABEL_160;
          case 6:
            if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
              WPP_SF_(v33[2], 50, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 32LL) + 40LL) = *((_DWORD *)v22 + 4);
            goto LABEL_440;
          default:
            break;
        }
      }
      else if ( !*((_DWORD *)v22 + 3) )
      {
        v139 = 13;
        if ( v33 == &WPP_GLOBAL_Control )
          goto LABEL_469;
        if ( (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 2u )
        {
          v101 = 51;
          goto LABEL_301;
        }
        goto LABEL_463;
      }
    }
LABEL_441:
    v22 = (__int64 *)*v22;
  }
  v136 = v32 & 1;
  if ( (v32 & 1) != 0 )
  {
    IPv4Helper::SetNegotiate(*(IPv4Helper **)(*((_QWORD *)this + 6) + 32LL));
    goto LABEL_446;
  }
  if ( v6 != 2 )
  {
    IPv4Helper::ClearNegotiate(*(IPv4Helper **)(*((_QWORD *)this + 6) + 32LL));
LABEL_446:
    v33 = (PVOID *)WPP_GLOBAL_Control;
  }
  v137 = v32 & 0x80;
  if ( v137 )
  {
    IPv6Helper::SetNegotiate(*(IPv6Helper **)(*((_QWORD *)this + 6) + 40LL));
    goto LABEL_451;
  }
  if ( v6 != 2 )
  {
    IPv6Helper::ClearNegotiate(*(IPv6Helper **)(*((_QWORD *)this + 6) + 40LL));
LABEL_451:
    v33 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v136 || v137 || v6 == 2 )
    goto LABEL_463;
  v10 = 840;
  v139 = 840;
  if ( v33 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 2u )
    {
      WPP_SF_d(v33[2], 63, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, 840);
      v10 = v139;
      v33 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 6u )
    {
      v17 = 64;
      v18 = v10;
LABEL_467:
      v19 = v33[2];
      goto LABEL_468;
    }
  }
LABEL_470:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v140);
  return v10;
}

```

## disassembly

```asm
0x180036b9c  mov     [rsp-8+arg_10], rbx
0x180036ba1  push    rbp
0x180036ba2  push    rsi
0x180036ba3  push    rdi
0x180036ba4  push    r12
0x180036ba6  push    r13
0x180036ba8  push    r14
0x180036baa  push    r15
0x180036bac  lea     rbp, [rsp-0A20h]
0x180036bb4  sub     rsp, 0B20h
0x180036bbb  mov     rax, cs:__security_cookie
0x180036bc2  xor     rax, rsp
0x180036bc5  mov     [rbp+0A50h+var_40], rax
0x180036bcc  mov     rdi, rdx
0x180036bcf  mov     r14, rcx
0x180036bd2  lea     rax, WPP_GLOBAL_Control
0x180036bd9  mov     rbx, cs:WPP_GLOBAL_Control
0x180036be0  cmp     rbx, rax
0x180036be3  jz      short loc_180036C0D
0x180036be5  test    byte ptr [rbx+1Ch], 1
0x180036be9  jz      short loc_180036C0D
0x180036beb  cmp     byte ptr [rbx+19h], 6
0x180036bef  jb      short loc_180036C0D
0x180036bf1  mov     edx, 1Eh
0x180036bf6  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180036bfd  mov     rcx, [rbx+10h]
0x180036c01  call    WPP_SF_
0x180036c06  mov     rbx, cs:WPP_GLOBAL_Control
0x180036c0d  xor     r12d, r12d
0x180036c10  mov     [rsp+0B50h+var_B10], r12d
0x180036c15  xor     edx, edx; Val
0x180036c17  mov     r8d, 222h; Size
0x180036c1d  lea     rcx, [rbp+0A50h+var_270]; void *
0x180036c24  call    memset_0
0x180036c29  xorps   xmm0, xmm0
0x180036c2c  xor     eax, eax
0x180036c2e  movups  xmmword ptr [rbp+0A50h+var_A98], xmm0
0x180036c32  movups  [rbp+0A50h+var_A88], xmm0
0x180036c36  mov     [rbp+0A50h+var_A78], ax
0x180036c3a  mov     rsi, [r14+30h]
0x180036c3e  mov     rax, [rsi+70h]
0x180036c42  mov     r13d, [rax+5C0h]
0x180036c49  mov     [rbp+0A50h+var_A70], r12d
0x180036c4d  xor     edx, edx; Val
0x180036c4f  mov     r8d, 7FCh; Size
0x180036c55  lea     rcx, [rbp+0A50h+var_A6C]; void *
0x180036c59  call    memset_0
0x180036c5e  mov     [rbp+0A50h+var_AC0], r12d
0x180036c62  xorps   xmm0, xmm0
0x180036c65  xor     eax, eax
0x180036c67  movups  [rbp+0A50h+var_ABC], xmm0
0x180036c6b  movups  [rbp+0A50h+var_AAC], xmm0
0x180036c6f  mov     [rbp+0A50h+var_A9C], eax
0x180036c72  movups  [rbp+0A50h+var_AD0], xmm0
0x180036c76  xorps   xmm1, xmm1
0x180036c79  movdqu  [rsp+0B50h+var_B00], xmm1
0x180036c7f  mov     [rsp+0B50h+var_B08], r12
0x180036c84  movdqu  [rsp+0B50h+var_AF0], xmm0
0x180036c8a  mov     [rsp+0B50h+var_AE0], r12
0x180036c8f  or      r15d, 0FFFFFFFFh
0x180036c93  mov     [rsp+0B50h+var_AD8], r15d
0x180036c98  mov     [rsp+0B50h+var_AD4], r12d
0x180036c9d  test    cs:byte_1800AA941, 8
0x180036ca4  jz      short loc_180036CCF
0x180036ca6  mov     [rsp+0B50h+var_B30], rsi; void *
0x180036cab  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180036cb2  lea     r8, [rsp+0B50h+var_B10]; unsigned int *
0x180036cb7  lea     rdx, aClientbfehandl_6; "ClientBFEHandler::ProcessCPReply"
0x180036cbe  lea     rcx, [rsp+0B50h+var_B08]; this
0x180036cc3  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x180036cc8  mov     rbx, cs:WPP_GLOBAL_Control
0x180036ccf  lea     rsi, WPP_GLOBAL_Control
0x180036cd6  cmp     rbx, rsi
0x180036cd9  jz      short loc_180036D0B
0x180036cdb  test    byte ptr [rbx+1Ch], 1
0x180036cdf  jz      short loc_180036D0B
0x180036ce1  cmp     byte ptr [rbx+19h], 5
0x180036ce5  jb      short loc_180036D0B
0x180036ce7  cmp     r13d, 2
0x180036ceb  setz    r9b
0x180036cef  mov     edx, 1Fh
0x180036cf4  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180036cfb  mov     rcx, [rbx+10h]
0x180036cff  call    WPP_SF_c
0x180036d04  mov     rbx, cs:WPP_GLOBAL_Control
0x180036d0b  test    rdi, rdi
0x180036d0e  jnz     loc_180036E3B
0x180036d14  mov     edi, 57h ; 'W'
0x180036d19  mov     [rsp+0B50h+var_B10], edi
0x180036d1d  test    cs:byte_1800AA941, 4
0x180036d24  jz      loc_180036DD5
0x180036d2a  mov     word ptr [rbp+0A50h+var_AC0], r12w
0x180036d2f  mov     rax, [r14+30h]
0x180036d33  test    rax, rax
0x180036d36  jz      short loc_180036D4B
0x180036d38  mov     rax, [rax+70h]
0x180036d3c  test    rax, rax
0x180036d3f  jz      short loc_180036D4B
0x180036d41  cmp     [rax+10h], r12
0x180036d45  jz      short loc_180036D4B
0x180036d47  mov     r15d, [rax+10h]
0x180036d4b  mov     edx, r15d
0x180036d4e  lea     rcx, [rbp+0A50h+var_AC0]
0x180036d52  call    ConvertPortNoToString
0x180036d57  test    cs:byte_1800AA941, 4
0x180036d5e  jz      short loc_180036DC6
0x180036d60  mov     rcx, [r14+30h]
0x180036d64  lea     rax, [rcx+70h]
0x180036d68  test    rcx, rcx
0x180036d6b  jz      short loc_180036D97
0x180036d6d  mov     rdx, [rax]
0x180036d70  test    rdx, rdx
0x180036d73  jz      short loc_180036D7E
0x180036d75  lea     rcx, [rdx+0A7Eh]
0x180036d7c  jmp     short loc_180036D86
0x180036d7e  test    rcx, rcx
0x180036d81  jz      short loc_180036D97
0x180036d83  mov     rcx, r12
0x180036d86  mov     rdx, [rax]
0x180036d89  test    rdx, rdx
0x180036d8c  jz      short loc_180036D9A
0x180036d8e  lea     r9, [rdx+848h]
0x180036d95  jmp     short loc_180036D9E
0x180036d97  mov     rcx, r12
0x180036d9a  lea     r9, [rbp+0A50h+var_AD0]
0x180036d9e  lea     rax, [rbp+0A50h+var_AC0]
0x180036da2  mov     [rsp+0B50h+var_B28], rax
0x180036da7  mov     [rsp+0B50h+var_B30], rcx
0x180036dac  lea     r8, aInvalidParam; "Invalid param"
0x180036db3  lea     rdx, RasVpnIkeParamTraceError
0x180036dba  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180036dc1  call    McTemplateU0zjzz_EventWriteTransfer
0x180036dc6  mov     edi, [rsp+0B50h+var_B10]
0x180036dca  mov     rbx, cs:WPP_GLOBAL_Control
0x180036dd1  test    edi, edi
0x180036dd3  jz      short loc_180036E0D
0x180036dd5  cmp     rbx, rsi
0x180036dd8  jz      loc_18003808D
0x180036dde  test    byte ptr [rbx+1Ch], 1
0x180036de2  jz      short loc_180036E0D
0x180036de4  cmp     byte ptr [rbx+19h], 2
0x180036de8  jb      short loc_180036E0D
0x180036dea  mov     edx, 20h ; ' '
0x180036def  mov     r9d, edi
0x180036df2  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180036df9  mov     rcx, [rbx+10h]
0x180036dfd  call    WPP_SF_d
0x180036e02  mov     edi, [rsp+0B50h+var_B10]
0x180036e06  mov     rbx, cs:WPP_GLOBAL_Control
0x180036e0d  cmp     rbx, rsi
0x180036e10  jz      loc_18003808D
0x180036e16  test    byte ptr [rbx+1Ch], 1
0x180036e1a  jz      loc_18003808D
0x180036e20  cmp     byte ptr [rbx+19h], 6
0x180036e24  jb      loc_18003808D
0x180036e2a  mov     edx, 21h ; '!'
0x180036e2f  mov     r9d, edi
0x180036e32  mov     rcx, [rbx+10h]
0x180036e36  jmp     loc_18003807D
0x180036e3b  cmp     dword ptr [rdi], 2
0x180036e3e  jz      short loc_180036EA3
0x180036e40  mov     edi, 57h ; 'W'
0x180036e45  mov     [rsp+0B50h+var_B10], edi
0x180036e49  cmp     rbx, rsi
0x180036e4c  jz      loc_18003808D
0x180036e52  test    byte ptr [rbx+1Ch], 1
0x180036e56  jz      short loc_180036E7F
0x180036e58  cmp     byte ptr [rbx+19h], 2
0x180036e5c  jb      short loc_180036E7F
0x180036e5e  lea     edx, [rdi-35h]
0x180036e61  mov     r9d, edi
0x180036e64  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180036e6b  mov     rcx, [rbx+10h]
0x180036e6f  call    WPP_SF_d
0x180036e74  mov     edi, [rsp+0B50h+var_B10]
0x180036e78  mov     rbx, cs:WPP_GLOBAL_Control
0x180036e7f  cmp     rbx, rsi
0x180036e82  jz      loc_18003808D
0x180036e88  test    byte ptr [rbx+1Ch], 1
0x180036e8c  jz      loc_18003808D
0x180036e92  cmp     byte ptr [rbx+19h], 6
0x180036e96  jb      loc_18003808D
0x180036e9c  mov     edx, 23h ; '#'
0x180036ea1  jmp     short loc_180036E2F
0x180036ea3  cmp     rbx, rsi
0x180036ea6  jz      short loc_180036EE9
0x180036ea8  test    byte ptr [rbx+1Ch], 1
0x180036eac  jz      short loc_180036EE9
0x180036eae  cmp     byte ptr [rbx+19h], 5
0x180036eb2  jb      short loc_180036EE9
0x180036eb4  mov     r9, [r14+30h]
0x180036eb8  cmp     [r9+10h], r12b
0x180036ebc  setnz   cl
0x180036ebf  movsxd  rdx, dword ptr [r9+8]
0x180036ec3  mov     eax, [r9+5Ch]
0x180036ec7  mov     [rsp+0B50h+var_B18], eax
0x180036ecb  mov     eax, [r9+58h]
0x180036ecf  mov     [rsp+0B50h+var_B20], eax
0x180036ed3  mov     byte ptr [rsp+0B50h+var_B28], cl
0x180036ed7  mov     [rsp+0B50h+var_B30], rdx
0x180036edc  mov     r9, [r9+18h]
0x180036ee0  mov     rcx, [rbx+10h]
0x180036ee4  call    WPP_SF_qIcdd
0x180036ee9  mov     rcx, [r14+30h]
0x180036eed  xor     r8d, r8d
0x180036ef0  lea     edx, [r8+3]
0x180036ef4  mov     rcx, [rcx+18h]
0x180036ef8  call    ?NotifyCaller@VPNIKEProtocolEngine@@SAXPEAXW4_PROTOCOL_RESULT_ID@@0@Z; VPNIKEProtocolEngine::NotifyCaller(void *,_PROTOCOL_RESULT_ID,void *)
0x180036efd  mov     rsi, [rdi+8]
0x180036f01  mov     rcx, [r14+30h]; this
0x180036f05  mov     rax, [rcx+70h]
0x180036f09  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180036f10  cmp     dword ptr [rax+5C0h], 2
0x180036f17  jnz     loc_18003700F
0x180036f1d  lea     rdx, [rbp+0A50h+var_270]; unsigned __int16 *
0x180036f24  call    ?GetRemoteUserName@BaseConnection@@QEAAKPEAGK@Z; BaseConnection::GetRemoteUserName(ushort *,ulong)
0x180036f29  lea     rdx, [rbp+0A50h+var_A98]; unsigned __int16 *
0x180036f2d  mov     rcx, [r14+30h]; this
0x180036f31  call    ?GetPortName@BaseConnection@@QEAAKPEAGK@Z; BaseConnection::GetPortName(ushort *,ulong)
0x180036f36  mov     rcx, [r14+30h]
0x180036f3a  cmp     qword ptr [rcx+78h], 0
0x180036f3f  jz      loc_18003700F
0x180036f45  test    cs:byte_1800AA941, 8
0x180036f4c  jz      loc_18003700F
0x180036f52  xor     eax, eax
0x180036f54  mov     word ptr [rbp+0A50h+var_A70], ax
0x180036f58  mov     word ptr [rbp+0A50h+var_AC0], ax
0x180036f5c  test    rcx, rcx
0x180036f5f  jz      short loc_180036F76
0x180036f61  mov     rax, [rcx+70h]
0x180036f65  test    rax, rax
0x180036f68  jz      short loc_180036F76
0x180036f6a  cmp     qword ptr [rax+10h], 0
0x180036f6f  jz      short loc_180036F76
0x180036f71  mov     edx, [rax+10h]
0x180036f74  jmp     short loc_180036F79
0x180036f76  mov     edx, r15d
0x180036f79  lea     rcx, [rbp+0A50h+var_AC0]
0x180036f7d  call    ConvertPortNoToString
0x180036f82  mov     rax, [r14+30h]
0x180036f86  mov     r9, [rax+70h]
0x180036f8a  add     r9, 5A9h
0x180036f91  mov     r8, [rax+78h]
0x180036f95  add     r8, 8
0x180036f99  lea     rdx, aUsernameSPortn_0; " username = %S portname = %S"
0x180036fa0  lea     rcx, [rbp+0A50h+var_A70]
0x180036fa4  call    FormatRRASErrorString
0x180036fa9  test    cs:byte_1800AA941, 8
0x180036fb0  jz      short loc_18003700F
0x180036fb2  mov     rcx, [r14+30h]
0x180036fb6  lea     rax, [rcx+70h]
0x180036fba  test    rcx, rcx
0x180036fbd  jz      short loc_180036FE8
0x180036fbf  mov     rdx, [rax]
0x180036fc2  test    rdx, rdx
0x180036fc5  jz      short loc_180036FD0
0x180036fc7  lea     rcx, [rdx+0A7Eh]
0x180036fce  jmp     short loc_180036FD7
0x180036fd0  test    rcx, rcx
0x180036fd3  jz      short loc_180036FE8
0x180036fd5  xor     ecx, ecx
0x180036fd7  mov     rdx, [rax]
0x180036fda  test    rdx, rdx
0x180036fdd  jz      short loc_180036FEA
0x180036fdf  lea     r9, [rdx+848h]
0x180036fe6  jmp     short loc_180036FEE
0x180036fe8  xor     ecx, ecx
0x180036fea  lea     r9, [rbp+0A50h+var_AD0]
0x180036fee  lea     rax, [rbp+0A50h+var_AC0]
0x180036ff2  mov     [rsp+0B50h+var_B28], rax
0x180036ff7  mov     [rsp+0B50h+var_B30], rcx
0x180036ffc  lea     r8, [rbp+0A50h+var_A70]
0x180037000  lea     rdx, RasVpnIkeParamTraceInfo
0x180037007  mov     rcx, r12
0x18003700a  call    McTemplateU0zjzz_EventWriteTransfer
0x18003700f  xor     edi, edi
0x180037011  mov     rcx, cs:WPP_GLOBAL_Control
0x180037018  test    rsi, rsi
0x18003701b  jz      loc_180037F85
0x180037021  lea     rbx, WPP_GLOBAL_Control
0x180037028  cmp     rcx, rbx
0x18003702b  jz      short loc_180037059
0x18003702d  test    byte ptr [rcx+1Ch], 1
0x180037031  jz      short loc_180037059
0x180037033  cmp     byte ptr [rcx+19h], 5
0x180037037  jb      short loc_180037059
0x180037039  mov     edx, 25h ; '%'
0x18003703e  mov     r9d, [rsi+8]
0x180037042  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180037049  mov     rcx, [rcx+10h]
0x18003704d  call    WPP_SF_d
0x180037052  mov     rcx, cs:WPP_GLOBAL_Control
0x180037059  mov     edx, [rsi+8]
0x18003705c  cmp     edx, 5BA0h
0x180037062  jg      loc_180037F24
0x180037068  jz      loc_180037EDB
0x18003706e  cmp     edx, 8
0x180037071  jg      loc_180037A95
0x180037077  jz      loc_180037997
0x18003707d  sub     edx, 1
  ... truncated ...
```
