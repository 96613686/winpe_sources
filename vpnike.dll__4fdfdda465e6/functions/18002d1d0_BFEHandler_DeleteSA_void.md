# BFEHandler::DeleteSA(void)

- ea: `0x18002d1d0`
- end: `0x18002d85a`
- name: `?DeleteSA@BFEHandler@@UEAAKXZ`
- size: `1674`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18002d1d0`
- `0x18002e0e8`
- `0x180030e04`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `fwpuclnt!FwpmFreeMemory0` at `0x18002d6c2`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002d6c2`
- `fwpuclnt!IkeextSaDeleteById0` at `0x18002d58e`
- `fwpuclnt!IkeextSaDeleteById0` at `0x18002d58e`
- `WS2_32!__imp_ntohl` at `0x18002d34b`
- `WS2_32!__imp_ntohl` at `0x18002d34b`

## string_xrefs

- `0x18002d2e1`: `BFEHandler::DeleteSA`
- `0x18002d632`: `IkeextSaDeleteById failed to delete saID:[%I64u]: %d`

## pseudocode

```c
__int64 __fastcall BFEHandler::DeleteSA(void **this)
{
  PVOID *v2; // rbx
  unsigned int v3; // r15d
  UINT64 *v4; // rax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  unsigned int i; // r14d
  _QWORD *v9; // rdx
  _DWORD *v10; // r9
  _QWORD *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  char *v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rcx
  __int128 *v17; // r9
  DWORD v18; // ebx
  _QWORD *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  char *v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rcx
  __int128 *v25; // r9
  _QWORD *v26; // rax
  __int64 v27; // rax
  char *v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // rcx
  __int128 *v31; // r9
  unsigned int v33; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v34; // [rsp+34h] [rbp-CCh] BYREF
  void *p; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v36; // [rsp+40h] [rbp-C0h] BYREF
  void *v37; // [rsp+48h] [rbp-B8h] BYREF
  IKEEXT_SA_ENUM_TEMPLATE0_ v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h] BYREF
  __int128 v40; // [rsp+88h] [rbp-78h]
  __int128 v41; // [rsp+98h] [rbp-68h]
  __int64 v42; // [rsp+A8h] [rbp-58h]
  int v43; // [rsp+B0h] [rbp-50h]
  int v44; // [rsp+B4h] [rbp-4Ch]
  __int128 v45; // [rsp+B8h] [rbp-48h] BYREF
  char v46; // [rsp+C8h] [rbp-38h]
  __int128 v47; // [rsp+D0h] [rbp-30h] BYREF
  int v48; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v49; // [rsp+E4h] [rbp-1Ch]
  __int128 v50; // [rsp+F4h] [rbp-Ch]
  int v51; // [rsp+104h] [rbp+4h]
  int v52; // [rsp+110h] [rbp+10h] BYREF
  char v53[2044]; // [rsp+114h] [rbp+14h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v52 = 0;
  memset_0(v53, 0, sizeof(v53));
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v47 = 0;
  v33 = 0;
  v34 = 0;
  v37 = 0;
  memset(&v38, 0, sizeof(v38));
  p = 0;
  v36 = 0;
  v45 = 0;
  v46 = 0;
  v40 = 0;
  v39 = 0;
  v41 = 0;
  v42 = 0;
  v3 = -1;
  v43 = -1;
  v44 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v39,
      L"BFEHandler::DeleteSA",
      &v33,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      this[6]);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  memset(&v38, 0, sizeof(v38));
  v36 = 0;
  v45 = 0;
  v46 = 0;
  if ( *((_BYTE *)this[6] + 16) )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
      WPP_SF_(v2[2], 48, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids);
    v36 = ntohl(*((_DWORD *)this[6] + 17)) | 0xFFFFFFFF00000000uLL;
    v38.remoteSubNet.type = FWP_V4_ADDR_MASK;
    v4 = &v36;
  }
  else
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
      WPP_SF_(v2[2], 49, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids);
    v45 = *(_OWORD *)((char *)this[6] + 72);
    v46 = 0x80;
    v38.remoteSubNet.type = FWP_V6_ADDR_MASK;
    v4 = (UINT64 *)&v45;
  }
  v38.remoteSubNet.uint64 = v4;
  while ( 1 )
  {
    v5 = BFEHandler::EnumSA((BFEHandler *)this, &v38, &v37, &v34, (struct IKEEXT_SA_DETAILS2_ ***)&p);
    v6 = v5;
    v33 = v5;
    if ( !v5 )
      goto LABEL_24;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v5);
      v6 = v33;
LABEL_24:
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !p )
      break;
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 5u )
    {
      WPP_SF_d(v7[2], 52, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v34);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    for ( i = 0; i < v34; ++i )
    {
      v9 = (_QWORD *)*((_QWORD *)p + i);
      v10 = this[6];
      if ( v10[2] != (unsigned int)v9[19] )
        continue;
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 5u )
        WPP_SF_dIi(v7[2], v9, v9[19], (unsigned int)v10[2], *v9, v9[19]);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v52) = 0;
        LOWORD(v48) = 0;
        v11 = this[6];
        if ( v11 && (v12 = v11[14]) != 0 && *(_QWORD *)(v12 + 16) )
          v13 = *(unsigned int *)(v12 + 16);
        else
          v13 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v48, v13);
        FormatRRASErrorString(
          &v52,
          L"Deleting SA: saID:[%I64u], tunnelId:[0x%I64X]",
          **((_QWORD **)p + i),
          *(_QWORD *)(*((_QWORD *)p + i) + 152LL));
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v14 = (char *)this[6];
          v15 = v14 + 112;
          if ( v14 )
          {
            if ( *v15 )
              v16 = *v15 + 2686LL;
            else
              v16 = 0;
            if ( *v15 )
            {
              v17 = (__int128 *)(*v15 + 2120LL);
LABEL_52:
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceInfo,
                (unsigned int)&v52,
                (_DWORD)v17,
                v16,
                (__int64)&v48);
              goto LABEL_53;
            }
          }
          else
          {
            v16 = 0;
          }
          v17 = &v47;
          goto LABEL_52;
        }
      }
LABEL_53:
      v18 = IkeextSaDeleteById0(BFEHandler::hFwpEngine, **((_QWORD **)p + i));
      if ( !v18 )
        goto LABEL_76;
      if ( !v33 )
        goto LABEL_59;
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v33);
LABEL_59:
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( (byte_1800AA941 & 8) == 0 )
        continue;
      LOWORD(v52) = 0;
      LOWORD(v48) = 0;
      v19 = this[6];
      if ( v19 && (v20 = v19[14]) != 0 && *(_QWORD *)(v20 + 16) )
        v21 = *(unsigned int *)(v20 + 16);
      else
        v21 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v48, v21);
      FormatRRASErrorString(&v52, L"IkeextSaDeleteById failed to delete saID:[%I64u]: %d", **((_QWORD **)p + i), v18);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v22 = (char *)this[6];
        v23 = v22 + 112;
        if ( v22 )
        {
          if ( *v23 )
            v24 = *v23 + 2686LL;
          else
            v24 = 0;
          if ( *v23 )
          {
            v25 = (__int128 *)(*v23 + 2120LL);
LABEL_75:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)&v52,
              (_DWORD)v25,
              v24,
              (__int64)&v48);
            goto LABEL_76;
          }
        }
        else
        {
          v24 = 0;
        }
        v25 = &v47;
        goto LABEL_75;
      }
LABEL_76:
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    FwpmFreeMemory0(&p);
    p = 0;
    v34 = 0;
    v6 = v33;
    if ( v33 == 259 )
    {
LABEL_101:
      v7 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_102;
    }
  }
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v52) = 0;
    LOWORD(v48) = 0;
    v26 = this[6];
    if ( v26 )
    {
      v27 = v26[14];
      if ( v27 )
      {
        if ( *(_QWORD *)(v27 + 16) )
          v3 = *(_DWORD *)(v27 + 16);
      }
    }
    ConvertPortNoToString(&v48, v3);
    FormatRRASErrorString(&v52, L"EnumSa returned nullptr list, Status = %!WINERROR!", v33);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v28 = (char *)this[6];
      v29 = v28 + 112;
      if ( v28 )
      {
        if ( *v29 )
          v30 = *v29 + 2686LL;
        else
          v30 = 0;
        if ( *v29 )
        {
          v31 = (__int128 *)(*v29 + 2120LL);
          goto LABEL_94;
        }
      }
      else
      {
        v30 = 0;
      }
      v31 = &v47;
LABEL_94:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)&v52,
        (_DWORD)v31,
        v30,
        (__int64)&v48);
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    v6 = v33;
  }
  if ( !v6 )
    goto LABEL_102;
  if ( v7 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 2u )
    {
      WPP_SF_d(v7[2], 51, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v6);
      v6 = v33;
      goto LABEL_101;
    }
LABEL_102:
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    {
      WPP_SF_d(v7[2], 55, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v6);
      v6 = v33;
    }
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v39);
  return v6;
}

```

## disassembly

```asm
0x18002d1d0  mov     [rsp-8+arg_8], rbx
0x18002d1d5  mov     [rsp-8+arg_10], rsi
0x18002d1da  push    rbp
0x18002d1db  push    rdi
0x18002d1dc  push    r12
0x18002d1de  push    r14
0x18002d1e0  push    r15
0x18002d1e2  lea     rbp, [rsp-820h]
0x18002d1ea  sub     rsp, 920h
0x18002d1f1  mov     rax, cs:__security_cookie
0x18002d1f8  xor     rax, rsp
0x18002d1fb  mov     [rbp+840h+var_30], rax
0x18002d202  mov     rdi, rcx
0x18002d205  lea     rsi, WPP_GLOBAL_Control
0x18002d20c  lea     r14, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002d213  mov     rbx, cs:WPP_GLOBAL_Control
0x18002d21a  cmp     rbx, rsi
0x18002d21d  jz      short loc_18002D243
0x18002d21f  test    byte ptr [rbx+1Ch], 1
0x18002d223  jz      short loc_18002D243
0x18002d225  cmp     byte ptr [rbx+19h], 6
0x18002d229  jb      short loc_18002D243
0x18002d22b  mov     edx, 2Fh ; '/'
0x18002d230  mov     r8, r14
0x18002d233  mov     rcx, [rbx+10h]
0x18002d237  call    WPP_SF_
0x18002d23c  mov     rbx, cs:WPP_GLOBAL_Control
0x18002d243  xor     r12d, r12d
0x18002d246  mov     [rbp+840h+var_830], r12d
0x18002d24a  xor     edx, edx; Val
0x18002d24c  mov     r8d, 7FCh; Size
0x18002d252  lea     rcx, [rbp+840h+var_82C]; void *
0x18002d256  call    memset_0
0x18002d25b  mov     [rbp+840h+var_860], r12d
0x18002d25f  xorps   xmm0, xmm0
0x18002d262  xor     eax, eax
0x18002d264  movups  [rbp+840h+var_85C], xmm0
0x18002d268  movups  [rbp+840h+var_84C], xmm0
0x18002d26c  mov     [rbp+840h+var_83C], eax
0x18002d26f  movups  [rbp+840h+var_870], xmm0
0x18002d273  mov     [rsp+940h+var_910], r12d
0x18002d278  mov     [rsp+940h+var_90C], r12d
0x18002d27d  mov     [rsp+940h+var_8F8], r12
0x18002d282  movups  xmmword ptr [rsp+940h+var_8F0.localSubNet.type], xmm0
0x18002d287  movups  xmmword ptr [rsp+940h+var_8F0.remoteSubNet.type], xmm0
0x18002d28c  movups  xmmword ptr [rsp+940h+var_8F0.localMainModeCertHash.size], xmm0
0x18002d291  mov     [rsp+940h+p], r12
0x18002d296  mov     [rsp+940h+var_900], r12
0x18002d29b  movups  [rbp+840h+var_888], xmm0
0x18002d29f  mov     [rbp+840h+var_878], al
0x18002d2a2  xorps   xmm1, xmm1
0x18002d2a5  movdqu  [rbp+840h+var_8B8], xmm1
0x18002d2aa  mov     [rbp+840h+var_8C0], r12
0x18002d2ae  movdqu  [rbp+840h+var_8A8], xmm0
0x18002d2b3  mov     [rbp+840h+var_898], r12
0x18002d2b7  or      r15d, 0FFFFFFFFh
0x18002d2bb  mov     [rbp+840h+var_890], r15d
0x18002d2bf  mov     [rbp+840h+var_88C], r12d
0x18002d2c3  test    cs:byte_1800AA941, 8
0x18002d2ca  jz      short loc_18002D2F8
0x18002d2cc  mov     rax, [rdi+30h]
0x18002d2d0  mov     [rsp+940h+var_920], rax; void *
0x18002d2d5  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18002d2dc  lea     r8, [rsp+940h+var_910]; unsigned int *
0x18002d2e1  lea     rdx, aBfehandlerDele; "BFEHandler::DeleteSA"
0x18002d2e8  lea     rcx, [rbp+840h+var_8C0]; this
0x18002d2ec  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18002d2f1  mov     rbx, cs:WPP_GLOBAL_Control
0x18002d2f8  xorps   xmm0, xmm0
0x18002d2fb  movups  xmmword ptr [rsp+940h+var_8F0.localSubNet.type], xmm0
0x18002d300  movups  xmmword ptr [rsp+940h+var_8F0.remoteSubNet.type], xmm0
0x18002d305  movups  xmmword ptr [rsp+940h+var_8F0.localMainModeCertHash.size], xmm0
0x18002d30a  mov     [rsp+940h+var_900], r12
0x18002d30f  xor     eax, eax
0x18002d311  movups  [rbp+840h+var_888], xmm0
0x18002d315  mov     [rbp+840h+var_878], al
0x18002d318  mov     rax, [rdi+30h]
0x18002d31c  cmp     [rax+10h], r12b
0x18002d320  jz      short loc_18002D369
0x18002d322  cmp     rbx, rsi
0x18002d325  jz      short loc_18002D344
0x18002d327  test    byte ptr [rbx+1Ch], 1
0x18002d32b  jz      short loc_18002D344
0x18002d32d  cmp     byte ptr [rbx+19h], 5
0x18002d331  jb      short loc_18002D344
0x18002d333  mov     edx, 30h ; '0'
0x18002d338  mov     r8, r14
0x18002d33b  mov     rcx, [rbx+10h]
0x18002d33f  call    WPP_SF_
0x18002d344  mov     rcx, [rdi+30h]
0x18002d348  mov     ecx, [rcx+44h]; netlong
0x18002d34b  call    cs:__imp_ntohl
0x18002d351  mov     dword ptr [rsp+940h+var_900], eax
0x18002d355  mov     dword ptr [rsp+940h+var_900+4], r15d
0x18002d35a  mov     [rsp+940h+var_8F0.remoteSubNet.type], 100h
0x18002d362  lea     rax, [rsp+940h+var_900]
0x18002d367  jmp     short loc_18002D3A8
0x18002d369  cmp     rbx, rsi
0x18002d36c  jz      short loc_18002D38B
0x18002d36e  test    byte ptr [rbx+1Ch], 1
0x18002d372  jz      short loc_18002D38B
0x18002d374  cmp     byte ptr [rbx+19h], 5
0x18002d378  jb      short loc_18002D38B
0x18002d37a  mov     edx, 31h ; '1'
0x18002d37f  mov     r8, r14
0x18002d382  mov     rcx, [rbx+10h]
0x18002d386  call    WPP_SF_
0x18002d38b  mov     rax, [rdi+30h]
0x18002d38f  movups  xmm0, xmmword ptr [rax+48h]
0x18002d393  movdqu  [rbp+840h+var_888], xmm0
0x18002d398  mov     [rbp+840h+var_878], 80h
0x18002d39c  mov     [rsp+940h+var_8F0.remoteSubNet.type], 101h
0x18002d3a4  lea     rax, [rbp+840h+var_888]
0x18002d3a8  mov     qword ptr [rsp+940h+var_8F0.remoteSubNet.8], rax
0x18002d3ad  lea     rax, [rsp+940h+p]
0x18002d3b2  mov     [rsp+940h+var_920], rax; struct IKEEXT_SA_DETAILS2_ ***
0x18002d3b7  lea     r9, [rsp+940h+var_90C]; unsigned int *
0x18002d3bc  lea     r8, [rsp+940h+var_8F8]; void **
0x18002d3c1  lea     rdx, [rsp+940h+var_8F0]; struct IKEEXT_SA_ENUM_TEMPLATE0_ *
0x18002d3c6  mov     rcx, rdi; this
0x18002d3c9  call    ?EnumSA@BFEHandler@@IEAAKPEAUIKEEXT_SA_ENUM_TEMPLATE0_@@PEAPEAXPEAIPEAPEAPEAUIKEEXT_SA_DETAILS2_@@@Z; BFEHandler::EnumSA(IKEEXT_SA_ENUM_TEMPLATE0_ *,void * *,uint *,IKEEXT_SA_DETAILS2_ * * *)
0x18002d3ce  mov     ebx, eax
0x18002d3d0  mov     [rsp+940h+var_910], eax
0x18002d3d4  test    eax, eax
0x18002d3d6  jz      short loc_18002D408
0x18002d3d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3df  cmp     rcx, rsi
0x18002d3e2  jz      short loc_18002D40F
0x18002d3e4  test    byte ptr [rcx+1Ch], 1
0x18002d3e8  jz      short loc_18002D40F
0x18002d3ea  cmp     byte ptr [rcx+19h], 2
0x18002d3ee  jb      short loc_18002D40F
0x18002d3f0  mov     edx, 32h ; '2'
0x18002d3f5  mov     r9d, eax
0x18002d3f8  mov     r8, r14
0x18002d3fb  mov     rcx, [rcx+10h]
0x18002d3ff  call    WPP_SF_d
0x18002d404  mov     ebx, [rsp+940h+var_910]
0x18002d408  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d40f  cmp     [rsp+940h+p], r12
0x18002d414  jz      loc_18002D6FC
0x18002d41a  cmp     rcx, rsi
0x18002d41d  jz      short loc_18002D448
0x18002d41f  test    byte ptr [rcx+1Ch], 1
0x18002d423  jz      short loc_18002D448
0x18002d425  cmp     byte ptr [rcx+19h], 5
0x18002d429  jb      short loc_18002D448
0x18002d42b  mov     edx, 34h ; '4'
0x18002d430  mov     r9d, [rsp+940h+var_90C]
0x18002d435  mov     r8, r14
0x18002d438  mov     rcx, [rcx+10h]
0x18002d43c  call    WPP_SF_d
0x18002d441  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d448  mov     r14d, r12d
0x18002d44b  cmp     r14d, [rsp+940h+var_90C]
0x18002d450  jnb     loc_18002D6BD
0x18002d456  mov     esi, r14d
0x18002d459  mov     rax, [rsp+940h+p]
0x18002d45e  mov     rdx, [rax+rsi*8]
0x18002d462  mov     r8, [rdx+98h]
0x18002d469  mov     r9, [rdi+30h]
0x18002d46d  mov     eax, r8d
0x18002d470  xor     eax, [r9+8]
0x18002d474  jnz     loc_18002D6B5
0x18002d47a  lea     rax, WPP_GLOBAL_Control
0x18002d481  cmp     rcx, rax
0x18002d484  jz      short loc_18002D4AC
0x18002d486  test    byte ptr [rcx+1Ch], 1
0x18002d48a  jz      short loc_18002D4AC
0x18002d48c  cmp     byte ptr [rcx+19h], 5
0x18002d490  jb      short loc_18002D4AC
0x18002d492  mov     [rsp+940h+var_918], r8
0x18002d497  mov     rax, [rdx]
0x18002d49a  mov     [rsp+940h+var_920], rax
0x18002d49f  mov     r9d, [r9+8]
0x18002d4a3  mov     rcx, [rcx+10h]
0x18002d4a7  call    WPP_SF_dIi
0x18002d4ac  test    cs:byte_1800AA941, 8
0x18002d4b3  jz      loc_18002D57B
0x18002d4b9  mov     word ptr [rbp+840h+var_830], r12w
0x18002d4be  mov     word ptr [rbp+840h+var_860], r12w
0x18002d4c3  mov     rax, [rdi+30h]
0x18002d4c7  test    rax, rax
0x18002d4ca  jz      short loc_18002D4E0
0x18002d4cc  mov     rax, [rax+70h]
0x18002d4d0  test    rax, rax
0x18002d4d3  jz      short loc_18002D4E0
0x18002d4d5  cmp     [rax+10h], r12
0x18002d4d9  jz      short loc_18002D4E0
0x18002d4db  mov     edx, [rax+10h]
0x18002d4de  jmp     short loc_18002D4E3
0x18002d4e0  mov     edx, r15d
0x18002d4e3  lea     rcx, [rbp+840h+var_860]
0x18002d4e7  call    ConvertPortNoToString
0x18002d4ec  mov     rax, [rsp+940h+p]
0x18002d4f1  mov     r8, [rax+rsi*8]
0x18002d4f5  mov     r9, [r8+98h]
0x18002d4fc  mov     r8, [r8]
0x18002d4ff  lea     rdx, aDeletingSaSaid; "Deleting SA: saID:[%I64u], tunnelId:[0x"...
0x18002d506  lea     rcx, [rbp+840h+var_830]
0x18002d50a  call    FormatRRASErrorString
0x18002d50f  test    cs:byte_1800AA941, 8
0x18002d516  jz      short loc_18002D57B
0x18002d518  mov     rcx, [rdi+30h]
0x18002d51c  lea     rax, [rcx+70h]
0x18002d520  test    rcx, rcx
0x18002d523  jz      short loc_18002D54F
0x18002d525  mov     rdx, [rax]
0x18002d528  test    rdx, rdx
0x18002d52b  jz      short loc_18002D536
0x18002d52d  lea     rcx, [rdx+0A7Eh]
0x18002d534  jmp     short loc_18002D53E
0x18002d536  test    rcx, rcx
0x18002d539  jz      short loc_18002D54F
0x18002d53b  mov     rcx, r12
0x18002d53e  mov     rdx, [rax]
0x18002d541  test    rdx, rdx
0x18002d544  jz      short loc_18002D552
0x18002d546  lea     r9, [rdx+848h]
0x18002d54d  jmp     short loc_18002D556
0x18002d54f  mov     rcx, r12
0x18002d552  lea     r9, [rbp+840h+var_870]
0x18002d556  lea     rax, [rbp+840h+var_860]
0x18002d55a  mov     [rsp+940h+var_918], rax
0x18002d55f  mov     [rsp+940h+var_920], rcx
0x18002d564  lea     r8, [rbp+840h+var_830]
0x18002d568  lea     rdx, RasVpnIkeParamTraceInfo
0x18002d56f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002d576  call    McTemplateU0zjzz_EventWriteTransfer
0x18002d57b  mov     rax, [rsp+940h+p]
0x18002d580  mov     rdx, [rax+rsi*8]
0x18002d584  mov     rdx, [rdx]; id
0x18002d587  mov     rcx, cs:?hFwpEngine@BFEHandler@@0PEAXEA; engineHandle
0x18002d58e  call    cs:__imp_IkeextSaDeleteById0
0x18002d594  mov     ebx, eax
0x18002d596  test    eax, eax
0x18002d598  jz      loc_18002D6AE
0x18002d59e  mov     r9d, [rsp+940h+var_910]
0x18002d5a3  test    r9d, r9d
0x18002d5a6  jz      short loc_18002D5DC
0x18002d5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5af  lea     rax, WPP_GLOBAL_Control
0x18002d5b6  cmp     rcx, rax
0x18002d5b9  jz      short loc_18002D5E3
0x18002d5bb  test    byte ptr [rcx+1Ch], 1
0x18002d5bf  jz      short loc_18002D5E3
0x18002d5c1  cmp     byte ptr [rcx+19h], 2
0x18002d5c5  jb      short loc_18002D5E3
0x18002d5c7  mov     edx, 36h ; '6'
0x18002d5cc  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002d5d3  mov     rcx, [rcx+10h]
0x18002d5d7  call    WPP_SF_d
0x18002d5dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5e3  test    cs:byte_1800AA941, 8
0x18002d5ea  jz      loc_18002D6B5
0x18002d5f0  mov     word ptr [rbp+840h+var_830], r12w
0x18002d5f5  mov     word ptr [rbp+840h+var_860], r12w
0x18002d5fa  mov     rax, [rdi+30h]
0x18002d5fe  test    rax, rax
0x18002d601  jz      short loc_18002D617
0x18002d603  mov     rax, [rax+70h]
0x18002d607  test    rax, rax
0x18002d60a  jz      short loc_18002D617
0x18002d60c  cmp     [rax+10h], r12
0x18002d610  jz      short loc_18002D617
0x18002d612  mov     edx, [rax+10h]
0x18002d615  jmp     short loc_18002D61A
0x18002d617  mov     edx, r15d
0x18002d61a  lea     rcx, [rbp+840h+var_860]
0x18002d61e  call    ConvertPortNoToString
0x18002d623  mov     rax, [rsp+940h+p]
0x18002d628  mov     r8, [rax+rsi*8]
0x18002d62c  mov     r9d, ebx
0x18002d62f  mov     r8, [r8]
0x18002d632  lea     rdx, aIkeextsadelete; "IkeextSaDeleteById failed to delete saI"...
0x18002d639  lea     rcx, [rbp+840h+var_830]
0x18002d63d  call    FormatRRASErrorString
0x18002d642  test    cs:byte_1800AA941, 8
0x18002d649  jz      short loc_18002D6AE
0x18002d64b  mov     rcx, [rdi+30h]
0x18002d64f  lea     rax, [rcx+70h]
0x18002d653  test    rcx, rcx
0x18002d656  jz      short loc_18002D682
0x18002d658  mov     rdx, [rax]
0x18002d65b  test    rdx, rdx
0x18002d65e  jz      short loc_18002D669
0x18002d660  lea     rcx, [rdx+0A7Eh]
0x18002d667  jmp     short loc_18002D671
0x18002d669  test    rcx, rcx
0x18002d66c  jz      short loc_18002D682
0x18002d66e  mov     rcx, r12
0x18002d671  mov     rdx, [rax]
0x18002d674  test    rdx, rdx
0x18002d677  jz      short loc_18002D685
0x18002d679  lea     r9, [rdx+848h]
0x18002d680  jmp     short loc_18002D689
0x18002d682  mov     rcx, r12
0x18002d685  lea     r9, [rbp+840h+var_870]
0x18002d689  lea     rax, [rbp+840h+var_860]
0x18002d68d  mov     [rsp+940h+var_918], rax
  ... truncated ...
```
