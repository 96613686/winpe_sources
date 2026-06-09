# ClientBFEHandler::PopulateIKEPolicyFromRouterConfiguration(_ROUTER_IKEv2_IF_CUSTOM_CONFIG2 &,int,IKEEXT_AUTHENTICATION_METHOD_TYPE_ &,ulong &,ulong &,ulong &,IKEEXT_CERTIFICATE_CRITERIA0_ * *)

- ea: `0x180036250`
- end: `0x1800367da`
- name: `?PopulateIKEPolicyFromRouterConfiguration@ClientBFEHandler@@QEAAKAEAU_ROUTER_IKEv2_IF_CUSTOM_CONFIG2@@HAEAW4IKEEXT_AUTHENTICATION_METHOD_TYPE_@@AEAK22PEAPEAUIKEEXT_CERTIFICATE_CRITERIA0_@@@Z`
- size: `1418`
- prototype: `__int64 __fastcall(ClientBFEHandler *this, struct _ROUTER_IKEv2_IF_CUSTOM_CONFIG2 *, int, enum IKEEXT_AUTHENTICATION_METHOD_TYPE_ *, unsigned int *, unsigned int *, unsigned int *, struct IKEEXT_CERTIFICATE_CRITERIA0_ **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180032690`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18002e934`
- `0x18002f51c`
- `0x180036250`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036778`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036778`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036376`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800364da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036376`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800364da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036361`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800364c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003676a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036361`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800364c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003676a`
- `rtutils!RouterLogEventA` at `0x1800366a0`
- `rtutils!RouterLogEventA` at `0x1800366a0`

## string_xrefs

- `0x1800365ff`: `Failed to get the hash for the configured local auth certificate: %d. IPSec would choose a default certificate for local authentication`

## pseudocode

```c
__int64 __fastcall ClientBFEHandler::PopulateIKEPolicyFromRouterConfiguration(
        ClientBFEHandler *this,
        struct _ROUTER_IKEv2_IF_CUSTOM_CONFIG2 *a2,
        int a3,
        enum IKEEXT_AUTHENTICATION_METHOD_TYPE_ *a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned int *a7,
        struct IKEEXT_CERTIFICATE_CRITERIA0_ **a8)
{
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rax
  HANDLE ProcessHeap; // rax
  _DWORD *v17; // r14
  PVOID *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rcx
  __int128 *v25; // r9
  DWORD dwErrorCode; // ebx
  __int64 v27; // rax
  HANDLE v28; // rax
  _DWORD *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  DWORD LocalAuthCertificateHash; // eax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rcx
  _QWORD *v38; // rax
  __int64 v39; // rcx
  __int128 *v40; // r9
  __int64 v41; // rcx
  _QWORD *v42; // rax
  __int64 v43; // rcx
  __int128 *v44; // r9
  HANDLE v45; // rax
  __int128 v47; // [rsp+38h] [rbp-C8h] BYREF
  int v48; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v49; // [rsp+4Ch] [rbp-B4h]
  __int128 v50; // [rsp+5Ch] [rbp-A4h]
  int v51; // [rsp+6Ch] [rbp-94h]
  int v52; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v53[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
  }
  v52 = 0;
  memset_0(v53, 0, sizeof(v53));
  v48 = 0;
  v51 = 0;
  v12 = *(_DWORD *)a2;
  v49 = 0;
  v50 = 0;
  v47 = 0;
  if ( v12 )
    *a6 = v12;
  v13 = *((_DWORD *)a2 + 12);
  if ( v13 )
    *a5 = v13;
  v14 = *((_DWORD *)a2 + 1);
  if ( v14 )
    *a7 = v14;
  if ( !a3 )
  {
    v15 = *((_QWORD *)a2 + 3);
    if ( v15 )
    {
      if ( *(_DWORD *)(v15 + 20) == 4 )
      {
        *a4 = IKEEXT_CERTIFICATE_ECDSA_P256;
      }
      else if ( *(_DWORD *)(v15 + 20) == 5 )
      {
        *a4 = IKEEXT_CERTIFICATE_ECDSA_P384;
      }
    }
  }
  ProcessHeap = GetProcessHeap();
  v17 = HeapAlloc(ProcessHeap, 8u, 0x14u);
  if ( v17 )
  {
    dwErrorCode = 0;
    if ( *((_DWORD *)a2 + 8)
      && (unsigned int)BFEHandler::IsValidLocalAuthCertificateHash((struct _CRYPTOAPI_BLOB *)a2 + 2) )
    {
      v27 = *((_QWORD *)a2 + 5);
      *(_OWORD *)v17 = *(_OWORD *)v27;
      v17[4] = *(_DWORD *)(v27 + 16);
      goto LABEL_43;
    }
    if ( !*((_DWORD *)a2 + 2) )
    {
LABEL_89:
      v45 = GetProcessHeap();
      HeapFree(v45, 0, v17);
      goto LABEL_90;
    }
    LocalAuthCertificateHash = BFEHandler::GetLocalAuthCertificateHash(
                                 (struct _CRYPTOAPI_BLOB *)((char *)a2 + 8),
                                 (unsigned __int8 *)v17);
    dwErrorCode = LocalAuthCertificateHash;
    if ( !LocalAuthCertificateHash )
    {
LABEL_43:
      v28 = GetProcessHeap();
      v29 = HeapAlloc(v28, 8u, 0x38u);
      if ( v29 )
      {
        v29[4] = 20;
        *((_QWORD *)v29 + 3) = v17;
        v29[12] = 256;
        *a8 = (struct IKEEXT_CERTIFICATE_CRITERIA0_ *)v29;
LABEL_90:
        v18 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_91;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, 8);
      }
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_87;
      v30 = *((_QWORD *)this + 6);
      LOWORD(v52) = 0;
      LOWORD(v48) = 0;
      if ( v30 && (v31 = *(_QWORD *)(v30 + 112)) != 0 && *(_QWORD *)(v31 + 16) )
        v32 = *(unsigned int *)(v31 + 16);
      else
        v32 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v48, v32);
      FormatRRASErrorString(&v52, L"VPNIKE_MALLOC failed: %d", 8);
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_87;
      v41 = *((_QWORD *)this + 6);
      v42 = (_QWORD *)(v41 + 112);
      if ( v41 )
      {
        if ( *v42 )
          v43 = *v42 + 2686LL;
        else
          v43 = 0;
        if ( *v42 )
        {
          v44 = (__int128 *)(*v42 + 2120LL);
LABEL_86:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v52,
            (_DWORD)v44,
            v43,
            (__int64)&v48);
LABEL_87:
          dwErrorCode = 8;
          goto LABEL_89;
        }
      }
      else
      {
        v43 = 0;
      }
      v44 = &v47;
      goto LABEL_86;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        77,
        &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
        LocalAuthCertificateHash);
    }
    if ( (byte_1800AA941 & 1) == 0
      || ((v34 = *((_QWORD *)this + 6), LOWORD(v52) = 0, LOWORD(v48) = 0, !v34)
       || (v35 = *(_QWORD *)(v34 + 112)) == 0
       || !*(_QWORD *)(v35 + 16)
        ? (v36 = 0xFFFFFFFFLL)
        : (v36 = *(unsigned int *)(v35 + 16)),
          ConvertPortNoToString(&v48, v36),
          FormatRRASErrorString(
            &v52,
            L"Failed to get the hash for the configured local auth certificate: %d. IPSec would choose a default certifica"
             "te for local authentication",
            dwErrorCode),
          (byte_1800AA941 & 1) == 0) )
    {
LABEL_75:
      RouterLogEventA(*((HANDLE *)VpnIkeProtocolEngine + 2), 1u, 0x4F3Du, 0, 0, dwErrorCode);
      dwErrorCode = 0;
      goto LABEL_89;
    }
    v37 = *((_QWORD *)this + 6);
    v38 = (_QWORD *)(v37 + 112);
    if ( v37 )
    {
      if ( *v38 )
        v39 = *v38 + 2686LL;
      else
        v39 = 0;
      if ( *v38 )
      {
        v40 = (__int128 *)(*v38 + 2120LL);
LABEL_74:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceAdminError,
          (unsigned int)&v52,
          (_DWORD)v40,
          v39,
          (__int64)&v48);
        goto LABEL_75;
      }
    }
    else
    {
      v39 = 0;
    }
    v40 = &v47;
    goto LABEL_74;
  }
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, 8);
    v18 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (byte_1800AA941 & 4) == 0 )
    goto LABEL_39;
  v19 = *((_QWORD *)this + 6);
  LOWORD(v52) = 0;
  LOWORD(v48) = 0;
  if ( v19 && (v20 = *(_QWORD *)(v19 + 112)) != 0 && *(_QWORD *)(v20 + 16) )
    v21 = *(unsigned int *)(v20 + 16);
  else
    v21 = 0xFFFFFFFFLL;
  ConvertPortNoToString(&v48, v21);
  FormatRRASErrorString(&v52, L"VPNIKE_MALLOC failed: %d", 8);
  if ( (byte_1800AA941 & 4) != 0 )
  {
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
LABEL_37:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v52,
          (_DWORD)v25,
          v24,
          (__int64)&v48);
        goto LABEL_38;
      }
    }
    else
    {
      v24 = 0;
    }
    v25 = &v47;
    goto LABEL_37;
  }
LABEL_38:
  v18 = (PVOID *)WPP_GLOBAL_Control;
LABEL_39:
  dwErrorCode = 8;
LABEL_91:
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 6u )
    WPP_SF_d(v18[2], 79, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, dwErrorCode);
  return dwErrorCode;
}

```

## disassembly

```asm
0x180036250  mov     [rsp-8+arg_10], rbx
0x180036255  push    rbp
0x180036256  push    rsi
0x180036257  push    rdi
0x180036258  push    r12
0x18003625a  push    r13
0x18003625c  push    r14
0x18003625e  push    r15
0x180036260  lea     rbp, [rsp-780h]
0x180036268  sub     rsp, 880h
0x18003626f  mov     rax, cs:__security_cookie
0x180036276  xor     rax, rsp
0x180036279  mov     [rbp+7B0h+var_40], rax
0x180036280  mov     rax, [rbp+7B0h+arg_38]
0x180036287  mov     rbx, r9
0x18003628a  mov     r15, [rbp+7B0h+arg_20]
0x180036291  mov     r13d, r8d
0x180036294  mov     r14, [rbp+7B0h+arg_28]
0x18003629b  mov     rdi, rdx
0x18003629e  mov     r12, [rbp+7B0h+arg_30]
0x1800362a5  mov     rsi, rcx
0x1800362a8  mov     [rsp+8B0h+var_880], rax
0x1800362ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362b4  lea     rax, WPP_GLOBAL_Control
0x1800362bb  cmp     rcx, rax
0x1800362be  jz      short loc_1800362E1
0x1800362c0  test    byte ptr [rcx+1Ch], 1
0x1800362c4  jz      short loc_1800362E1
0x1800362c6  cmp     byte ptr [rcx+19h], 6
0x1800362ca  jb      short loc_1800362E1
0x1800362cc  mov     rcx, [rcx+10h]
0x1800362d0  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x1800362d7  mov     edx, 4Bh ; 'K'
0x1800362dc  call    WPP_SF_
0x1800362e1  xor     eax, eax
0x1800362e3  lea     rcx, [rsp+8B0h+var_83C]; void *
0x1800362e8  xor     edx, edx; Val
0x1800362ea  mov     [rsp+8B0h+var_840], eax
0x1800362ee  mov     r8d, 7FCh; Size
0x1800362f4  call    memset_0
0x1800362f9  xor     eax, eax
0x1800362fb  xorps   xmm0, xmm0
0x1800362fe  mov     [rsp+8B0h+var_868], eax
0x180036302  mov     [rsp+8B0h+var_844], eax
0x180036306  mov     eax, [rdi]
0x180036308  movups  [rsp+8B0h+var_864], xmm0
0x18003630d  movups  [rsp+8B0h+var_854], xmm0
0x180036312  movups  [rsp+8B0h+var_878], xmm0
0x180036317  test    eax, eax
0x180036319  jz      short loc_18003631E
0x18003631b  mov     [r14], eax
0x18003631e  mov     eax, [rdi+30h]
0x180036321  test    eax, eax
0x180036323  jz      short loc_180036328
0x180036325  mov     [r15], eax
0x180036328  mov     eax, [rdi+4]
0x18003632b  xor     r15d, r15d
0x18003632e  test    eax, eax
0x180036330  jz      short loc_180036336
0x180036332  mov     [r12], eax
0x180036336  mov     r12d, 8
0x18003633c  test    r13d, r13d
0x18003633f  jnz     short loc_180036361
0x180036341  mov     rax, [rdi+18h]
0x180036345  test    rax, rax
0x180036348  jz      short loc_180036361
0x18003634a  cmp     dword ptr [rax+14h], 4
0x18003634e  jnz     short loc_180036358
0x180036350  mov     dword ptr [rbx], 7
0x180036356  jmp     short loc_180036361
0x180036358  cmp     dword ptr [rax+14h], 5
0x18003635c  jnz     short loc_180036361
0x18003635e  mov     [rbx], r12d
0x180036361  call    cs:__imp_GetProcessHeap
0x180036367  mov     r13d, 14h
0x18003636d  mov     edx, r12d; dwFlags
0x180036370  mov     rcx, rax; hHeap
0x180036373  mov     r8d, r13d; dwBytes
0x180036376  call    cs:__imp_HeapAlloc
0x18003637c  mov     r14, rax
0x18003637f  test    rax, rax
0x180036382  jnz     loc_180036499
0x180036388  mov     rcx, cs:WPP_GLOBAL_Control
0x18003638f  lea     rdi, WPP_GLOBAL_Control
0x180036396  cmp     rcx, rdi
0x180036399  jz      short loc_1800363C4
0x18003639b  test    byte ptr [rcx+1Ch], 1
0x18003639f  jz      short loc_1800363C4
0x1800363a1  cmp     byte ptr [rcx+19h], 2
0x1800363a5  jb      short loc_1800363C4
0x1800363a7  mov     rcx, [rcx+10h]
0x1800363ab  lea     edx, [rax+4Ch]
0x1800363ae  mov     r9d, r12d
0x1800363b1  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x1800363b8  call    WPP_SF_d
0x1800363bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800363c4  test    cs:byte_1800AA941, 4
0x1800363cb  jz      loc_180036491
0x1800363d1  mov     rdx, [rsi+30h]
0x1800363d5  mov     word ptr [rsp+8B0h+var_840], r15w
0x1800363db  mov     word ptr [rsp+8B0h+var_868], r15w
0x1800363e1  test    rdx, rdx
0x1800363e4  jz      short loc_1800363FA
0x1800363e6  mov     rdx, [rdx+70h]
0x1800363ea  test    rdx, rdx
0x1800363ed  jz      short loc_1800363FA
0x1800363ef  cmp     [rdx+10h], r15
0x1800363f3  jz      short loc_1800363FA
0x1800363f5  mov     edx, [rdx+10h]
0x1800363f8  jmp     short loc_1800363FD
0x1800363fa  or      edx, 0FFFFFFFFh
0x1800363fd  lea     rcx, [rsp+8B0h+var_868]
0x180036402  call    ConvertPortNoToString
0x180036407  mov     r8d, r12d
0x18003640a  lea     rdx, aVpnikeMallocFa_0; "VPNIKE_MALLOC failed: %d"
0x180036411  lea     rcx, [rsp+8B0h+var_840]
0x180036416  call    FormatRRASErrorString
0x18003641b  test    cs:byte_1800AA941, 4
0x180036422  jz      short loc_18003648A
0x180036424  mov     rcx, [rsi+30h]
0x180036428  lea     rax, [rcx+70h]
0x18003642c  test    rcx, rcx
0x18003642f  jz      short loc_18003645B
0x180036431  mov     rdx, [rax]
0x180036434  test    rdx, rdx
0x180036437  jz      short loc_180036442
0x180036439  lea     rcx, [rdx+0A7Eh]
0x180036440  jmp     short loc_18003644A
0x180036442  test    rcx, rcx
0x180036445  jz      short loc_18003645B
0x180036447  mov     rcx, r15
0x18003644a  mov     rdx, [rax]
0x18003644d  test    rdx, rdx
0x180036450  jz      short loc_18003645E
0x180036452  lea     r9, [rdx+848h]
0x180036459  jmp     short loc_180036463
0x18003645b  mov     rcx, r15
0x18003645e  lea     r9, [rsp+8B0h+var_878]
0x180036463  lea     rax, [rsp+8B0h+var_868]
0x180036468  mov     qword ptr [rsp+8B0h+dwErrorCode], rax
0x18003646d  lea     r8, [rsp+8B0h+var_840]
0x180036472  mov     [rsp+8B0h+plpszSubStringArray], rcx
0x180036477  lea     rdx, RasVpnIkeParamTraceError
0x18003647e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180036485  call    McTemplateU0zjzz_EventWriteTransfer
0x18003648a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036491  mov     ebx, r12d
0x180036494  jmp     loc_180036785
0x180036499  lea     rcx, [rdi+20h]; pvFindPara
0x18003649d  mov     ebx, r15d
0x1800364a0  cmp     [rcx], r15d
0x1800364a3  jz      loc_180036563
0x1800364a9  call    ?IsValidLocalAuthCertificateHash@BFEHandler@@KAHPEAU_CRYPTOAPI_BLOB@@@Z; BFEHandler::IsValidLocalAuthCertificateHash(_CRYPTOAPI_BLOB *)
0x1800364ae  test    eax, eax
0x1800364b0  jz      loc_180036563
0x1800364b6  mov     rax, [rdi+28h]
0x1800364ba  movups  xmm0, xmmword ptr [rax]
0x1800364bd  movups  xmmword ptr [r14], xmm0
0x1800364c1  mov     eax, [rax+10h]
0x1800364c4  mov     [r14+10h], eax
0x1800364c8  call    cs:__imp_GetProcessHeap
0x1800364ce  mov     r8d, 38h ; '8'; dwBytes
0x1800364d4  mov     edx, r12d; dwFlags
0x1800364d7  mov     rcx, rax; hHeap
0x1800364da  call    cs:__imp_HeapAlloc
0x1800364e0  test    rax, rax
0x1800364e3  jnz     loc_180036743
0x1800364e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800364f0  lea     rdi, WPP_GLOBAL_Control
0x1800364f7  cmp     rcx, rdi
0x1800364fa  jz      short loc_18003651E
0x1800364fc  test    byte ptr [rcx+1Ch], 1
0x180036500  jz      short loc_18003651E
0x180036502  cmp     byte ptr [rcx+19h], 2
0x180036506  jb      short loc_18003651E
0x180036508  mov     rcx, [rcx+10h]
0x18003650c  lea     edx, [rax+4Eh]
0x18003650f  mov     r9d, r12d
0x180036512  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180036519  call    WPP_SF_d
0x18003651e  test    cs:byte_1800AA941, 4
0x180036525  jz      loc_18003673E
0x18003652b  mov     rdx, [rsi+30h]
0x18003652f  mov     word ptr [rsp+8B0h+var_840], r15w
0x180036535  mov     word ptr [rsp+8B0h+var_868], r15w
0x18003653b  test    rdx, rdx
0x18003653e  jz      loc_1800366AE
0x180036544  mov     rdx, [rdx+70h]
0x180036548  test    rdx, rdx
0x18003654b  jz      loc_1800366AE
0x180036551  cmp     [rdx+10h], r15
0x180036555  jz      loc_1800366AE
0x18003655b  mov     edx, [rdx+10h]
0x18003655e  jmp     loc_1800366B1
0x180036563  lea     rcx, [rdi+8]; pvFindPara
0x180036567  cmp     [rcx], r15d
0x18003656a  jz      loc_180036763
0x180036570  mov     rdx, r14; pvData
0x180036573  call    ?GetLocalAuthCertificateHash@BFEHandler@@KAKPEAU_CRYPTOAPI_BLOB@@PEAE@Z; BFEHandler::GetLocalAuthCertificateHash(_CRYPTOAPI_BLOB *,uchar *)
0x180036578  mov     ebx, eax
0x18003657a  test    eax, eax
0x18003657c  jz      loc_1800364C8
0x180036582  mov     rcx, cs:WPP_GLOBAL_Control
0x180036589  lea     rdi, WPP_GLOBAL_Control
0x180036590  cmp     rcx, rdi
0x180036593  jz      short loc_1800365B9
0x180036595  test    byte ptr [rcx+1Ch], 1
0x180036599  jz      short loc_1800365B9
0x18003659b  cmp     byte ptr [rcx+19h], 2
0x18003659f  jb      short loc_1800365B9
0x1800365a1  mov     rcx, [rcx+10h]
0x1800365a5  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x1800365ac  mov     edx, 4Dh ; 'M'
0x1800365b1  mov     r9d, eax
0x1800365b4  call    WPP_SF_d
0x1800365b9  test    cs:byte_1800AA941, 1
0x1800365c0  jz      loc_18003667F
0x1800365c6  mov     rdx, [rsi+30h]
0x1800365ca  mov     word ptr [rsp+8B0h+var_840], r15w
0x1800365d0  mov     word ptr [rsp+8B0h+var_868], r15w
0x1800365d6  test    rdx, rdx
0x1800365d9  jz      short loc_1800365EF
0x1800365db  mov     rdx, [rdx+70h]
0x1800365df  test    rdx, rdx
0x1800365e2  jz      short loc_1800365EF
0x1800365e4  cmp     [rdx+10h], r15
0x1800365e8  jz      short loc_1800365EF
0x1800365ea  mov     edx, [rdx+10h]
0x1800365ed  jmp     short loc_1800365F2
0x1800365ef  or      edx, 0FFFFFFFFh
0x1800365f2  lea     rcx, [rsp+8B0h+var_868]
0x1800365f7  call    ConvertPortNoToString
0x1800365fc  mov     r8d, ebx
0x1800365ff  lea     rdx, aFailedToGetThe; "Failed to get the hash for the configur"...
0x180036606  lea     rcx, [rsp+8B0h+var_840]
0x18003660b  call    FormatRRASErrorString
0x180036610  test    cs:byte_1800AA941, 1
0x180036617  jz      short loc_18003667F
0x180036619  mov     rcx, [rsi+30h]
0x18003661d  lea     rax, [rcx+70h]
0x180036621  test    rcx, rcx
0x180036624  jz      short loc_180036650
0x180036626  mov     rdx, [rax]
0x180036629  test    rdx, rdx
0x18003662c  jz      short loc_180036637
0x18003662e  lea     rcx, [rdx+0A7Eh]
0x180036635  jmp     short loc_18003663F
0x180036637  test    rcx, rcx
0x18003663a  jz      short loc_180036650
0x18003663c  mov     rcx, r15
0x18003663f  mov     rdx, [rax]
0x180036642  test    rdx, rdx
0x180036645  jz      short loc_180036653
0x180036647  lea     r9, [rdx+848h]
0x18003664e  jmp     short loc_180036658
0x180036650  mov     rcx, r15
0x180036653  lea     r9, [rsp+8B0h+var_878]
0x180036658  lea     rax, [rsp+8B0h+var_868]
0x18003665d  mov     qword ptr [rsp+8B0h+dwErrorCode], rax
0x180036662  lea     r8, [rsp+8B0h+var_840]
0x180036667  mov     [rsp+8B0h+plpszSubStringArray], rcx
0x18003666c  lea     rdx, RasVpnIkeParamTraceAdminError
0x180036673  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003667a  call    McTemplateU0zjzz_EventWriteTransfer
0x18003667f  mov     rcx, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180036686  xor     r9d, r9d; dwSubStringCount
0x180036689  mov     [rsp+8B0h+dwErrorCode], ebx; dwErrorCode
0x18003668d  mov     r8d, 4F3Dh; dwMessageId
0x180036693  mov     [rsp+8B0h+plpszSubStringArray], r15; plpszSubStringArray
0x180036698  mov     rcx, [rcx+10h]; hLogHandle
0x18003669c  lea     edx, [r9+1]; dwEventType
0x1800366a0  call    cs:__imp_RouterLogEventA
0x1800366a6  mov     ebx, r15d
0x1800366a9  jmp     loc_18003676A
0x1800366ae  or      edx, 0FFFFFFFFh
0x1800366b1  lea     rcx, [rsp+8B0h+var_868]
0x1800366b6  call    ConvertPortNoToString
0x1800366bb  mov     r8d, r12d
0x1800366be  lea     rdx, aVpnikeMallocFa_0; "VPNIKE_MALLOC failed: %d"
0x1800366c5  lea     rcx, [rsp+8B0h+var_840]
0x1800366ca  call    FormatRRASErrorString
0x1800366cf  test    cs:byte_1800AA941, 4
0x1800366d6  jz      short loc_18003673E
0x1800366d8  mov     rcx, [rsi+30h]
0x1800366dc  lea     rax, [rcx+70h]
0x1800366e0  test    rcx, rcx
0x1800366e3  jz      short loc_18003670F
0x1800366e5  mov     rdx, [rax]
0x1800366e8  test    rdx, rdx
0x1800366eb  jz      short loc_1800366F6
0x1800366ed  lea     rcx, [rdx+0A7Eh]
0x1800366f4  jmp     short loc_1800366FE
0x1800366f6  test    rcx, rcx
0x1800366f9  jz      short loc_18003670F
0x1800366fb  mov     rcx, r15
0x1800366fe  mov     rdx, [rax]
0x180036701  test    rdx, rdx
0x180036704  jz      short loc_180036712
0x180036706  lea     r9, [rdx+848h]
0x18003670d  jmp     short loc_180036717
  ... truncated ...
```
