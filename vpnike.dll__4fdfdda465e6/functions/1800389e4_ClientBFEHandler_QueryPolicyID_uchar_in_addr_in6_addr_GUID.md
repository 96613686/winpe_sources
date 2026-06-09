# ClientBFEHandler::QueryPolicyID(uchar,in_addr *,in6_addr *,_GUID &)

- ea: `0x1800389e4`
- end: `0x18003926f`
- name: `?QueryPolicyID@ClientBFEHandler@@QEAAKEPEAUin_addr@@PEAUin6_addr@@AEAU_GUID@@@Z`
- size: `2187`
- prototype: `__int64 __fastcall(ClientBFEHandler *this, char, struct in_addr *, struct in6_addr *, struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bd20`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180007894`
- `0x18002e6f4`
- `0x1800389e4`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `fwpuclnt!FwpmProviderContextCreateEnumHandle0` at `0x180038bcb`
- `fwpuclnt!FwpmProviderContextCreateEnumHandle0` at `0x180038bcb`
- `fwpuclnt!FwpmProviderContextEnum3` at `0x180038d2f`
- `fwpuclnt!FwpmProviderContextEnum3` at `0x180038d2f`
- `fwpuclnt!FwpmFreeMemory0` at `0x180038ff3`
- `fwpuclnt!FwpmFreeMemory0` at `0x180038ff3`
- `WS2_32!__imp_ntohl` at `0x180038d78`
- `WS2_32!__imp_ntohl` at `0x180038d95`
- `WS2_32!__imp_ntohl` at `0x180038d78`
- `WS2_32!__imp_ntohl` at `0x180038d95`

## string_xrefs

- `0x180038c4e`: `QueryPolicyID: FwpmProviderContextCreateEnumHandle0 returned %d`

## pseudocode

```c
__int64 __fastcall ClientBFEHandler::QueryPolicyID(
        ClientBFEHandler *this,
        char a2,
        struct in_addr *a3,
        struct in6_addr *a4,
        struct _GUID *a5)
{
  unsigned int v6; // esi
  unsigned int v7; // r13d
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rax
  __int64 v13; // rcx
  __int128 *v14; // r9
  unsigned int v15; // edi
  unsigned int BfeHandle; // eax
  DWORD v17; // eax
  DWORD v18; // ebx
  PVOID *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rcx
  __int128 *v25; // r9
  int v27; // r12d
  unsigned int v28; // eax
  unsigned int v29; // r14d
  struct _GUID *v30; // rdx
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int128 *v42; // r9
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rdx
  _QWORD *v47; // rax
  __int64 v48; // rdx
  __int128 *v49; // r9
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rcx
  _QWORD *v53; // rax
  __int64 v54; // rcx
  __int128 *v55; // r9
  PVOID *v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rcx
  _QWORD *v61; // rax
  __int64 v62; // rcx
  __int128 *v63; // r9
  unsigned int v65; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v66; // [rsp+38h] [rbp-C8h]
  void *p; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE engineHandle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE enumHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID *v70; // [rsp+58h] [rbp-A8h]
  struct in_addr *v71; // [rsp+60h] [rbp-A0h]
  struct in6_addr *v72; // [rsp+68h] [rbp-98h]
  FWPM_PROVIDER_CONTEXT_ENUM_TEMPLATE0 enumTemplate; // [rsp+70h] [rbp-90h] BYREF
  __int128 v74; // [rsp+80h] [rbp-80h] BYREF
  int v75; // [rsp+90h] [rbp-70h] BYREF
  __int128 v76; // [rsp+94h] [rbp-6Ch]
  __int128 v77; // [rsp+A4h] [rbp-5Ch]
  int v78; // [rsp+B4h] [rbp-4Ch]
  int v79; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v80[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v70 = a5;
  v72 = a4;
  v71 = a3;
  v6 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = a2 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 188, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, a4);
  }
  enumHandle = 0;
  enumTemplate = 0;
  v65 = 0;
  p = 0;
  *a5 = GUID_NULL;
  engineHandle = 0;
  v79 = 0;
  memset_0(v80, 0, sizeof(v80));
  v75 = 0;
  v7 = -1;
  v76 = 0;
  v78 = 0;
  v77 = 0;
  v74 = 0;
  if ( (byte_1800AA941 & 8) == 0 )
    goto LABEL_21;
  v8 = *((_QWORD *)this + 6);
  LOWORD(v75) = 0;
  if ( v8 && (v9 = *(_QWORD *)(v8 + 112)) != 0 && *(_QWORD *)(v9 + 16) )
    v10 = *(unsigned int *)(v9 + 16);
  else
    v10 = 0xFFFFFFFFLL;
  ConvertPortNoToString(&v75, v10);
  if ( (byte_1800AA941 & 8) == 0 )
    goto LABEL_21;
  v11 = *((_QWORD *)this + 6);
  v12 = (_QWORD *)(v11 + 112);
  if ( !v11 )
  {
    v13 = 0;
LABEL_19:
    v14 = &v74;
    goto LABEL_20;
  }
  if ( *v12 )
    v13 = *v12 + 2686LL;
  else
    v13 = 0;
  if ( !*v12 )
    goto LABEL_19;
  v14 = (__int128 *)(*v12 + 2120LL);
LABEL_20:
  McTemplateU0zjzz_EventWriteTransfer(
    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
    (unsigned int)RasVpnIkeParamTraceInfo,
    (unsigned int)L"==> QueryPolicyID",
    (_DWORD)v14,
    v13,
    (__int64)&v75);
LABEL_21:
  v15 = *((_DWORD *)VpnIkeProtocolEngine + 24);
  BfeHandle = BFEHandler::GetBfeHandle(&engineHandle);
  if ( BfeHandle
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, BfeHandle);
  }
  enumTemplate.providerContextType = FWPM_IPSEC_IKEV2_QM_TUNNEL_CONTEXT;
  v17 = FwpmProviderContextCreateEnumHandle0(engineHandle, &enumTemplate, &enumHandle);
  v18 = v17;
  if ( v17 )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v17);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_47;
    v20 = *((_QWORD *)this + 6);
    LOWORD(v79) = 0;
    LOWORD(v75) = 0;
    if ( v20 )
    {
      v21 = *(_QWORD *)(v20 + 112);
      if ( v21 )
      {
        if ( *(_QWORD *)(v21 + 16) )
          v7 = *(_DWORD *)(v21 + 16);
      }
    }
    ConvertPortNoToString(&v75, v7);
    FormatRRASErrorString(&v79, L"QueryPolicyID: FwpmProviderContextCreateEnumHandle0 returned %d", v18);
    if ( (byte_1800AA941 & 4) == 0 )
    {
LABEL_46:
      v19 = (PVOID *)WPP_GLOBAL_Control;
LABEL_47:
      if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 6u )
        WPP_SF_d(v19[2], 191, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v18);
      return v18;
    }
    v22 = *((_QWORD *)this + 6);
    v23 = (_QWORD *)(v22 + 112);
    if ( v22 )
    {
      if ( *v23 )
        v24 = *v23 + 2686LL;
      else
        v24 = 0;
      if ( *v23 )
      {
        v25 = (__int128 *)(*v23 + 2120LL);
LABEL_45:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v79,
          (_DWORD)v25,
          v24,
          (__int64)&v75);
        goto LABEL_46;
      }
    }
    else
    {
      v24 = 0;
    }
    v25 = &v74;
    goto LABEL_45;
  }
  v27 = 0;
  v66 = v15 >> 31;
LABEL_53:
  v65 = 0;
  p = 0;
  v28 = FwpmProviderContextEnum3(engineHandle, enumHandle, 100, &p, &v65);
  v29 = v28;
  if ( !v28 )
  {
    while ( 1 )
    {
      if ( v6 >= v65 )
        goto LABEL_110;
      v30 = (struct _GUID *)*((_QWORD *)p + v6);
      v31 = *(_QWORD *)v30[4].Data4;
      if ( a2 )
      {
        if ( !*(_DWORD *)(v31 + 16)
          && *(_DWORD *)(v31 + 36) == ntohl(v71->S_un.S_addr)
          && (!v66 || *(_DWORD *)(v31 + 20) == ntohl(*(_DWORD *)(*((_QWORD *)this + 6) + 48LL))) )
        {
          *v70 = *(struct _GUID *)*((_QWORD *)p + v6);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
          }
          if ( (byte_1800AA941 & 8) != 0 )
          {
            LOWORD(v75) = 0;
            v32 = *((_QWORD *)this + 6);
            if ( v32 && (v33 = *(_QWORD *)(v32 + 112)) != 0 && *(_QWORD *)(v33 + 16) )
              v34 = *(unsigned int *)(v33 + 16);
            else
              v34 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v75, v34);
            if ( (byte_1800AA941 & 8) != 0 )
            {
              v38 = *((_QWORD *)this + 6);
              if ( v38 )
              {
                v39 = *(_QWORD *)(v38 + 112);
                if ( v39 )
                  v40 = v39 + 2686;
                else
                  v40 = 0;
                v41 = *(_QWORD *)(v38 + 112);
                if ( v41 )
                {
                  LODWORD(v42) = v41 + 2120;
                  goto LABEL_88;
                }
              }
              else
              {
                v40 = 0;
              }
              v42 = &v74;
LABEL_88:
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceInfo,
                (unsigned int)L"found matching V4 version.",
                (_DWORD)v42,
                v40,
                (__int64)&v75);
            }
          }
          v27 = 1;
LABEL_110:
          v6 = 0;
          goto LABEL_111;
        }
      }
      else if ( *(_DWORD *)(v31 + 16) == 1 )
      {
        v35 = *(_QWORD *)(v31 + 36) - *(_QWORD *)v72->u.Byte;
        if ( !v35 )
          v35 = *(_QWORD *)(v31 + 44) - *(_QWORD *)&v72->u.Word[4];
        if ( !v35 )
        {
          if ( !v66 )
            goto LABEL_90;
          v36 = *((_QWORD *)this + 6);
          v37 = *(_QWORD *)(v31 + 20) - *(_QWORD *)(v36 + 52);
          if ( !v37 )
            v37 = *(_QWORD *)(v31 + 28) - *(_QWORD *)(v36 + 60);
          if ( !v37 )
          {
LABEL_90:
            v27 = 1;
            *v70 = *v30;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
            }
            if ( (byte_1800AA941 & 8) == 0 )
              goto LABEL_110;
            v43 = *((_QWORD *)this + 6);
            v6 = 0;
            LOWORD(v75) = 0;
            if ( v43 && (v44 = *(_QWORD *)(v43 + 112)) != 0 && *(_QWORD *)(v44 + 16) )
              v45 = *(unsigned int *)(v44 + 16);
            else
              v45 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v75, v45);
            if ( (byte_1800AA941 & 8) != 0 )
            {
              v46 = *((_QWORD *)this + 6);
              v47 = (_QWORD *)(v46 + 112);
              if ( v46 )
              {
                if ( *v47 )
                  v48 = *v47 + 2686LL;
                else
                  v48 = 0;
                if ( *v47 )
                {
                  v49 = (__int128 *)(*v47 + 2120LL);
LABEL_109:
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasVpnIkeParamTraceInfo,
                    (unsigned int)L"found matching V6 version.",
                    (_DWORD)v49,
                    v48,
                    (__int64)&v75);
                  goto LABEL_111;
                }
              }
              else
              {
                v48 = 0;
              }
              v49 = &v74;
              goto LABEL_109;
            }
LABEL_111:
            FwpmFreeMemory0(&p);
            if ( !v65 )
            {
              if ( (byte_1800AA941 & 4) != 0 )
              {
                v50 = *((_QWORD *)this + 6);
                LOWORD(v75) = 0;
                if ( v50 )
                {
                  v51 = *(_QWORD *)(v50 + 112);
                  if ( v51 )
                  {
                    if ( *(_QWORD *)(v51 + 16) )
                      v7 = *(_DWORD *)(v51 + 16);
                  }
                }
                ConvertPortNoToString(&v75, v7);
                if ( (byte_1800AA941 & 4) != 0 )
                {
                  v52 = *((_QWORD *)this + 6);
                  v53 = (_QWORD *)(v52 + 112);
                  if ( v52 )
                  {
                    if ( *v53 )
                      v54 = *v53 + 2686LL;
                    else
                      v54 = 0;
                    if ( *v53 )
                    {
                      v55 = (__int128 *)(*v53 + 2120LL);
                      goto LABEL_126;
                    }
                  }
                  else
                  {
                    v54 = 0;
                  }
                  v55 = &v74;
LABEL_126:
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasVpnIkeParamTraceError,
                    (unsigned int)L"<== QueryPolicyID",
                    (_DWORD)v55,
                    v54,
                    (__int64)&v75);
                }
              }
              if ( v27 )
              {
LABEL_132:
                v56 = (PVOID *)WPP_GLOBAL_Control;
                goto LABEL_133;
              }
              v29 = 1168;
              v56 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    196,
                    &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                    1168);
                  goto LABEL_132;
                }
LABEL_133:
                if ( v56 != &WPP_GLOBAL_Control && (*((_BYTE *)v56 + 28) & 1) != 0 && *((_BYTE *)v56 + 25) >= 6u )
                {
                  v57 = 197;
                  goto LABEL_161;
                }
              }
              return v29;
            }
            goto LABEL_53;
          }
        }
      }
      ++v6;
    }
  }
  v56 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v28);
    v56 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (byte_1800AA941 & 4) != 0 )
  {
    v58 = *((_QWORD *)this + 6);
    LOWORD(v79) = 0;
    LOWORD(v75) = 0;
    if ( v58 )
    {
      v59 = *(_QWORD *)(v58 + 112);
      if ( v59 )
      {
        if ( *(_QWORD *)(v59 + 16) )
          v7 = *(_DWORD *)(v59 + 16);
      }
    }
    ConvertPortNoToString(&v75, v7);
    FormatRRASErrorString(&v79, L"QueryPolicyID: FwpmProviderContextEnum2 returned %d", v29);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v60 = *((_QWORD *)this + 6);
      v61 = (_QWORD *)(v60 + 112);
      if ( v60 )
      {
        if ( *v61 )
          v62 = *v61 + 2686LL;
        else
          v62 = 0;
        if ( *v61 )
        {
          v63 = (__int128 *)(*v61 + 2120LL);
          goto LABEL_155;
        }
      }
      else
      {
        v62 = 0;
      }
      v63 = &v74;
LABEL_155:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)&v79,
        (_DWORD)v63,
        v62,
        (__int64)&v75);
    }
    v56 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v56 != &WPP_GLOBAL_Control && (*((_BYTE *)v56 + 28) & 1) != 0 && *((_BYTE *)v56 + 25) >= 6u )
  {
    v57 = 193;
LABEL_161:
    WPP_SF_d(v56[2], v57, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v29);
  }
  return v29;
}

```

## disassembly

```asm
0x1800389e4  mov     [rsp-8+arg_8], rbx
0x1800389e9  push    rbp
0x1800389ea  push    rsi
0x1800389eb  push    rdi
0x1800389ec  push    r12
0x1800389ee  push    r13
0x1800389f0  push    r14
0x1800389f2  push    r15
0x1800389f4  lea     rbp, [rsp-7D0h]
0x1800389fc  sub     rsp, 8D0h
0x180038a03  mov     rax, cs:__security_cookie
0x180038a0a  xor     rax, rsp
0x180038a0d  mov     [rbp+800h+var_40], rax
0x180038a14  mov     rbx, [rbp+800h+arg_20]
0x180038a1b  mov     al, dl
0x180038a1d  mov     [rsp+900h+var_8A8], rbx
0x180038a22  mov     r15, rcx
0x180038a25  mov     [rsp+900h+var_898], r9
0x180038a2a  mov     [rsp+900h+var_8A0], r8
0x180038a2f  mov     [rsp+900h+var_8D0], dl
0x180038a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180038a3a  lea     r14, WPP_GLOBAL_Control
0x180038a41  xor     esi, esi
0x180038a43  lea     r12, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180038a4a  cmp     rcx, r14
0x180038a4d  jz      short loc_180038A72
0x180038a4f  test    byte ptr [rcx+1Ch], 1
0x180038a53  jz      short loc_180038A72
0x180038a55  cmp     byte ptr [rcx+19h], 6
0x180038a59  jb      short loc_180038A72
0x180038a5b  mov     rcx, [rcx+10h]
0x180038a5f  test    al, al
0x180038a61  mov     edx, 0BCh
0x180038a66  mov     r8, r12
0x180038a69  setnz   r9b
0x180038a6d  call    WPP_SF_c
0x180038a72  xorps   xmm0, xmm0
0x180038a75  mov     [rsp+900h+enumHandle], rsi
0x180038a7a  movups  xmmword ptr [rsp+900h+enumTemplate.providerKey], xmm0
0x180038a7f  xor     edx, edx; Val
0x180038a81  mov     r8d, 7FCh; Size
0x180038a87  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180038a8e  lea     rcx, [rbp+800h+var_83C]; void *
0x180038a92  mov     [rsp+900h+var_8CC], esi
0x180038a96  mov     [rsp+900h+p], rsi
0x180038a9b  movdqu  xmmword ptr [rbx], xmm0
0x180038a9f  mov     [rsp+900h+engineHandle], rsi
0x180038aa4  mov     [rbp+800h+var_840], esi
0x180038aa7  call    memset_0
0x180038aac  xorps   xmm0, xmm0
0x180038aaf  mov     [rbp+800h+var_870], esi
0x180038ab2  xor     eax, eax
0x180038ab4  or      r13d, 0FFFFFFFFh
0x180038ab8  test    cs:byte_1800AA941, 8
0x180038abf  movups  [rbp+800h+var_86C], xmm0
0x180038ac3  mov     [rbp+800h+var_84C], eax
0x180038ac6  movups  [rbp+800h+var_85C], xmm0
0x180038aca  movups  [rbp+800h+var_880], xmm0
0x180038ace  jz      loc_180038B70
0x180038ad4  mov     rax, [r15+30h]
0x180038ad8  mov     word ptr [rbp+800h+var_870], si
0x180038adc  test    rax, rax
0x180038adf  jz      short loc_180038AF5
0x180038ae1  mov     rax, [rax+70h]
0x180038ae5  test    rax, rax
0x180038ae8  jz      short loc_180038AF5
0x180038aea  cmp     [rax+10h], rsi
0x180038aee  jz      short loc_180038AF5
0x180038af0  mov     edx, [rax+10h]
0x180038af3  jmp     short loc_180038AF8
0x180038af5  mov     edx, r13d
0x180038af8  lea     rcx, [rbp+800h+var_870]
0x180038afc  call    ConvertPortNoToString
0x180038b01  test    cs:byte_1800AA941, 8
0x180038b08  jz      short loc_180038B70
0x180038b0a  mov     rcx, [r15+30h]
0x180038b0e  lea     rax, [rcx+70h]
0x180038b12  test    rcx, rcx
0x180038b15  jz      short loc_180038B41
0x180038b17  mov     rdx, [rax]
0x180038b1a  test    rdx, rdx
0x180038b1d  jz      short loc_180038B28
0x180038b1f  lea     rcx, [rdx+0A7Eh]
0x180038b26  jmp     short loc_180038B30
0x180038b28  test    rcx, rcx
0x180038b2b  jz      short loc_180038B41
0x180038b2d  mov     rcx, rsi
0x180038b30  mov     rdx, [rax]
0x180038b33  test    rdx, rdx
0x180038b36  jz      short loc_180038B44
0x180038b38  lea     r9, [rdx+848h]
0x180038b3f  jmp     short loc_180038B48
0x180038b41  mov     rcx, rsi
0x180038b44  lea     r9, [rbp+800h+var_880]
0x180038b48  lea     rax, [rbp+800h+var_870]
0x180038b4c  mov     [rsp+900h+var_8D8], rax
0x180038b51  lea     r8, aQuerypolicyid_0; "==> QueryPolicyID"
0x180038b58  mov     [rsp+900h+var_8E0], rcx
0x180038b5d  lea     rdx, RasVpnIkeParamTraceInfo
0x180038b64  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180038b6b  call    McTemplateU0zjzz_EventWriteTransfer
0x180038b70  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180038b77  lea     rcx, [rsp+900h+engineHandle]; void **
0x180038b7c  mov     edi, [rax+60h]
0x180038b7f  call    ?GetBfeHandle@BFEHandler@@SAKPEAPEAX@Z; BFEHandler::GetBfeHandle(void * *)
0x180038b84  test    eax, eax
0x180038b86  jz      short loc_180038BB4
0x180038b88  mov     rcx, cs:WPP_GLOBAL_Control
0x180038b8f  cmp     rcx, r14
0x180038b92  jz      short loc_180038BB4
0x180038b94  test    byte ptr [rcx+1Ch], 1
0x180038b98  jz      short loc_180038BB4
0x180038b9a  cmp     byte ptr [rcx+19h], 2
0x180038b9e  jb      short loc_180038BB4
0x180038ba0  mov     rcx, [rcx+10h]
0x180038ba4  mov     edx, 0BDh
0x180038ba9  mov     r9d, eax
0x180038bac  mov     r8, r12
0x180038baf  call    WPP_SF_d
0x180038bb4  mov     rcx, [rsp+900h+engineHandle]; engineHandle
0x180038bb9  lea     r8, [rsp+900h+enumHandle]; enumHandle
0x180038bbe  lea     rdx, [rsp+900h+enumTemplate]; enumTemplate
0x180038bc3  mov     [rsp+900h+enumTemplate.providerContextType], 9
0x180038bcb  call    cs:__imp_FwpmProviderContextCreateEnumHandle0
0x180038bd1  mov     ebx, eax
0x180038bd3  test    eax, eax
0x180038bd5  jz      loc_180038CFD
0x180038bdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180038be2  cmp     rcx, r14
0x180038be5  jz      short loc_180038C0E
0x180038be7  test    byte ptr [rcx+1Ch], 1
0x180038beb  jz      short loc_180038C0E
0x180038bed  cmp     byte ptr [rcx+19h], 2
0x180038bf1  jb      short loc_180038C0E
0x180038bf3  mov     rcx, [rcx+10h]
0x180038bf7  mov     edx, 0BEh
0x180038bfc  mov     r9d, eax
0x180038bff  mov     r8, r12
0x180038c02  call    WPP_SF_d
0x180038c07  mov     rcx, cs:WPP_GLOBAL_Control
0x180038c0e  test    cs:byte_1800AA941, 4
0x180038c15  jz      loc_180038CD1
0x180038c1b  mov     rax, [r15+30h]
0x180038c1f  mov     word ptr [rbp+800h+var_840], si
0x180038c23  mov     word ptr [rbp+800h+var_870], si
0x180038c27  test    rax, rax
0x180038c2a  jz      short loc_180038C3F
0x180038c2c  mov     rax, [rax+70h]
0x180038c30  test    rax, rax
0x180038c33  jz      short loc_180038C3F
0x180038c35  cmp     [rax+10h], rsi
0x180038c39  jz      short loc_180038C3F
0x180038c3b  mov     r13d, [rax+10h]
0x180038c3f  mov     edx, r13d
0x180038c42  lea     rcx, [rbp+800h+var_870]
0x180038c46  call    ConvertPortNoToString
0x180038c4b  mov     r8d, ebx
0x180038c4e  lea     rdx, aQuerypolicyidF_1; "QueryPolicyID: FwpmProviderContextCreat"...
0x180038c55  lea     rcx, [rbp+800h+var_840]
0x180038c59  call    FormatRRASErrorString
0x180038c5e  test    cs:byte_1800AA941, 4
0x180038c65  jz      short loc_180038CCA
0x180038c67  mov     rcx, [r15+30h]
0x180038c6b  lea     rax, [rcx+70h]
0x180038c6f  test    rcx, rcx
0x180038c72  jz      short loc_180038C9E
0x180038c74  mov     rdx, [rax]
0x180038c77  test    rdx, rdx
0x180038c7a  jz      short loc_180038C85
0x180038c7c  lea     rcx, [rdx+0A7Eh]
0x180038c83  jmp     short loc_180038C8D
0x180038c85  test    rcx, rcx
0x180038c88  jz      short loc_180038C9E
0x180038c8a  mov     rcx, rsi
0x180038c8d  mov     rdx, [rax]
0x180038c90  test    rdx, rdx
0x180038c93  jz      short loc_180038CA1
0x180038c95  lea     r9, [rdx+848h]
0x180038c9c  jmp     short loc_180038CA5
0x180038c9e  mov     rcx, rsi
0x180038ca1  lea     r9, [rbp+800h+var_880]
0x180038ca5  lea     rax, [rbp+800h+var_870]
0x180038ca9  mov     [rsp+900h+var_8D8], rax
0x180038cae  lea     r8, [rbp+800h+var_840]
0x180038cb2  mov     [rsp+900h+var_8E0], rcx
0x180038cb7  lea     rdx, RasVpnIkeParamTraceError
0x180038cbe  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180038cc5  call    McTemplateU0zjzz_EventWriteTransfer
0x180038cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180038cd1  cmp     rcx, r14
0x180038cd4  jz      short loc_180038CF6
0x180038cd6  test    byte ptr [rcx+1Ch], 1
0x180038cda  jz      short loc_180038CF6
0x180038cdc  cmp     byte ptr [rcx+19h], 6
0x180038ce0  jb      short loc_180038CF6
0x180038ce2  mov     rcx, [rcx+10h]
0x180038ce6  mov     edx, 0BFh
0x180038ceb  mov     r9d, ebx
0x180038cee  mov     r8, r12
0x180038cf1  call    WPP_SF_d
0x180038cf6  mov     eax, ebx
0x180038cf8  jmp     loc_180039245
0x180038cfd  shr     edi, 1Fh
0x180038d00  mov     r12d, esi
0x180038d03  mov     [rsp+900h+var_8C8], edi
0x180038d07  mov     rdx, [rsp+900h+enumHandle]
0x180038d0c  lea     rax, [rsp+900h+var_8CC]
0x180038d11  mov     rcx, [rsp+900h+engineHandle]
0x180038d16  lea     r9, [rsp+900h+p]
0x180038d1b  mov     r8d, 64h ; 'd'
0x180038d21  mov     [rsp+900h+var_8E0], rax
0x180038d26  mov     [rsp+900h+var_8CC], esi
0x180038d2a  mov     [rsp+900h+p], rsi
0x180038d2f  call    cs:__imp_FwpmProviderContextEnum3
0x180038d35  mov     r14d, eax
0x180038d38  test    eax, eax
0x180038d3a  jnz     loc_180039118
0x180038d40  cmp     esi, [rsp+900h+var_8CC]
0x180038d44  jnb     loc_180038FE5
0x180038d4a  mov     rcx, [rsp+900h+p]
0x180038d4f  xor     r8d, r8d
0x180038d52  mov     edi, esi
0x180038d54  mov     rdx, [rcx+rdi*8]
0x180038d58  mov     rbx, [rdx+48h]
0x180038d5c  cmp     [rsp+900h+var_8D0], r8b
0x180038d61  jz      loc_180038E1E
0x180038d67  cmp     [rbx+10h], r8d
0x180038d6b  jnz     loc_180038E69
0x180038d71  mov     rax, [rsp+900h+var_8A0]
0x180038d76  mov     ecx, [rax]; netlong
0x180038d78  call    cs:__imp_ntohl
0x180038d7e  cmp     [rbx+24h], eax
0x180038d81  jnz     loc_180038E69
0x180038d87  cmp     [rsp+900h+var_8C8], 0
0x180038d8c  jz      short loc_180038DA4
0x180038d8e  mov     rcx, [r15+30h]
0x180038d92  mov     ecx, [rcx+30h]; netlong
0x180038d95  call    cs:__imp_ntohl
0x180038d9b  cmp     [rbx+14h], eax
0x180038d9e  jnz     loc_180038E69
0x180038da4  mov     rax, [rsp+900h+p]
0x180038da9  mov     rcx, [rax+rdi*8]
0x180038dad  mov     rax, [rsp+900h+var_8A8]
0x180038db2  movups  xmm0, xmmword ptr [rcx]
0x180038db5  movdqu  xmmword ptr [rax], xmm0
0x180038db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180038dc0  lea     rbx, WPP_GLOBAL_Control
0x180038dc7  cmp     rcx, rbx
0x180038dca  jz      short loc_180038DED
0x180038dcc  test    byte ptr [rcx+1Ch], 1
0x180038dd0  jz      short loc_180038DED
0x180038dd2  cmp     byte ptr [rcx+19h], 5
0x180038dd6  jb      short loc_180038DED
0x180038dd8  mov     rcx, [rcx+10h]
0x180038ddc  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180038de3  mov     edx, 0C2h
0x180038de8  call    WPP_SF_
0x180038ded  test    cs:byte_1800AA941, 8
0x180038df4  jz      loc_180038EE7
0x180038dfa  xor     eax, eax
0x180038dfc  mov     word ptr [rbp+800h+var_870], ax
0x180038e00  mov     rax, [r15+30h]
0x180038e04  test    rax, rax
0x180038e07  jz      short loc_180038E70
0x180038e09  mov     rax, [rax+70h]
0x180038e0d  test    rax, rax
0x180038e10  jz      short loc_180038E70
0x180038e12  cmp     qword ptr [rax+10h], 0
0x180038e17  jz      short loc_180038E70
0x180038e19  mov     edx, [rax+10h]
0x180038e1c  jmp     short loc_180038E73
0x180038e1e  cmp     dword ptr [rbx+10h], 1
0x180038e22  jnz     short loc_180038E69
0x180038e24  mov     rcx, [rsp+900h+var_898]
0x180038e29  mov     rax, [rbx+24h]
0x180038e2d  sub     rax, [rcx]
0x180038e30  jnz     short loc_180038E3A
0x180038e32  mov     rax, [rbx+2Ch]
0x180038e36  sub     rax, [rcx+8]
0x180038e3a  test    rax, rax
0x180038e3d  jnz     short loc_180038E69
0x180038e3f  cmp     [rsp+900h+var_8C8], r8d
0x180038e44  jz      loc_180038EF2
0x180038e4a  mov     rcx, [r15+30h]
0x180038e4e  mov     rax, [rbx+14h]
0x180038e52  sub     rax, [rcx+34h]
0x180038e56  jnz     short loc_180038E60
0x180038e58  mov     rax, [rbx+1Ch]
0x180038e5c  sub     rax, [rcx+3Ch]
0x180038e60  test    rax, rax
0x180038e63  jz      loc_180038EF2
0x180038e69  inc     esi
0x180038e6b  jmp     loc_180038D40
0x180038e70  mov     edx, r13d
0x180038e73  lea     rcx, [rbp+800h+var_870]
0x180038e77  call    ConvertPortNoToString
0x180038e7c  test    cs:byte_1800AA941, 8
0x180038e83  jz      short loc_180038EE7
0x180038e85  mov     rcx, [r15+30h]
0x180038e89  test    rcx, rcx
  ... truncated ...
```
