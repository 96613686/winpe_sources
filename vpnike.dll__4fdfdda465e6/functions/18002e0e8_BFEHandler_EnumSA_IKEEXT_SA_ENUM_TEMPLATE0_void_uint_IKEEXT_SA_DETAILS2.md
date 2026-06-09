# BFEHandler::EnumSA(IKEEXT_SA_ENUM_TEMPLATE0_ *,void * *,uint *,IKEEXT_SA_DETAILS2_ * * *)

- ea: `0x18002e0e8`
- end: `0x18002e6ee`
- name: `?EnumSA@BFEHandler@@IEAAKPEAUIKEEXT_SA_ENUM_TEMPLATE0_@@PEAPEAXPEAIPEAPEAPEAUIKEEXT_SA_DETAILS2_@@@Z`
- size: `1542`
- prototype: `__int64 __fastcall(void **this, struct IKEEXT_SA_ENUM_TEMPLATE0_ *, void **, unsigned int *, struct IKEEXT_SA_DETAILS2_ ***)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002d1d0`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18002e0e8`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x18002e2ac`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x18002e2ac`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x18002e53b`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x18002e53b`
- `fwpuclnt!IkeextSaEnum2` at `0x18002e3df`
- `fwpuclnt!IkeextSaEnum2` at `0x18002e3df`

## string_xrefs

- `0x18002e285`: `Create enum handle`
- `0x18002e33c`: `IkeextSaCreateEnumHandle failed: %d`

## pseudocode

```c
__int64 __fastcall BFEHandler::EnumSA(
        void **this,
        struct IKEEXT_SA_ENUM_TEMPLATE0_ *a2,
        void **a3,
        unsigned int *a4,
        struct IKEEXT_SA_DETAILS2_ ***a5)
{
  unsigned int v9; // r15d
  _QWORD *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  char *v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  __int128 *v16; // r9
  DWORD EnumHandle0; // eax
  PVOID *v18; // rcx
  _QWORD *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  char *v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rcx
  __int128 *v25; // r9
  unsigned int v26; // eax
  _QWORD *v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  _QWORD *v30; // rax
  __int64 v31; // rax
  __int64 v32; // rdx
  char *v33; // rcx
  _QWORD *v34; // rax
  __int64 v35; // rcx
  __int128 *v36; // r9
  _QWORD *v37; // rax
  __int64 v38; // rax
  char *v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // rcx
  __int128 *v42; // r9
  unsigned int v43; // ebx
  unsigned int v45; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v46; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v47; // [rsp+40h] [rbp-C0h]
  __int128 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+60h] [rbp-A0h]
  int v50; // [rsp+68h] [rbp-98h]
  int v51; // [rsp+6Ch] [rbp-94h]
  __int128 v52; // [rsp+70h] [rbp-90h] BYREF
  int v53; // [rsp+80h] [rbp-80h] BYREF
  __int128 v54; // [rsp+84h] [rbp-7Ch]
  __int128 v55; // [rsp+94h] [rbp-6Ch]
  int v56; // [rsp+A4h] [rbp-5Ch]
  int v57; // [rsp+B0h] [rbp-50h] BYREF
  char v58[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids);
  }
  v45 = 0;
  v57 = 0;
  memset_0(v58, 0, sizeof(v58));
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v52 = 0;
  v47 = 0;
  v46 = 0;
  v48 = 0;
  v49 = 0;
  v9 = -1;
  v50 = -1;
  v51 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v46,
      L"BFEHandler::EnumSA",
      &v45,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      this[6]);
  *a5 = 0;
  if ( *a3 )
    goto LABEL_46;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v53) = 0;
    v10 = this[6];
    if ( v10 && (v11 = v10[14]) != 0 && *(_QWORD *)(v11 + 16) )
      v12 = *(unsigned int *)(v11 + 16);
    else
      v12 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v53, v12);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v13 = (char *)this[6];
      v14 = v13 + 112;
      if ( v13 )
      {
        if ( *v14 )
          v15 = *v14 + 2686LL;
        else
          v15 = 0;
        if ( *v14 )
        {
          v16 = (__int128 *)(*v14 + 2120LL);
LABEL_23:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"Create enum handle",
            (_DWORD)v16,
            v15,
            (__int64)&v53);
          goto LABEL_24;
        }
      }
      else
      {
        v15 = 0;
      }
      v16 = &v52;
      goto LABEL_23;
    }
  }
LABEL_24:
  EnumHandle0 = IkeextSaCreateEnumHandle0(BFEHandler::hFwpEngine, a2, a3);
  v45 = EnumHandle0;
  if ( EnumHandle0 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, EnumHandle0);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_80;
    LOWORD(v57) = 0;
    LOWORD(v53) = 0;
    v19 = this[6];
    if ( v19 && (v20 = v19[14]) != 0 && *(_QWORD *)(v20 + 16) )
      v21 = *(unsigned int *)(v20 + 16);
    else
      v21 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v53, v21);
    FormatRRASErrorString(&v57, L"IkeextSaCreateEnumHandle failed: %d", v45);
LABEL_36:
    if ( (byte_1800AA941 & 4) == 0 )
    {
LABEL_79:
      v18 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_80;
    }
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
LABEL_45:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v57,
          (_DWORD)v25,
          v24,
          (__int64)&v53);
        goto LABEL_79;
      }
    }
    else
    {
      v24 = 0;
    }
    v25 = &v52;
    goto LABEL_45;
  }
LABEL_46:
  v26 = IkeextSaEnum2(BFEHandler::hFwpEngine, *a3, 10, a5, a4);
  v45 = v26;
  if ( v26 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v26);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_80;
    LOWORD(v57) = 0;
    LOWORD(v53) = 0;
    v27 = this[6];
    if ( v27 && (v28 = v27[14]) != 0 && *(_QWORD *)(v28 + 16) )
      v29 = *(unsigned int *)(v28 + 16);
    else
      v29 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v53, v29);
    FormatRRASErrorString(&v57, L"IkeextSaEnum failed: %d", v45);
    goto LABEL_36;
  }
  if ( *a4 > 9 )
    goto LABEL_79;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v53) = 0;
    v30 = this[6];
    if ( v30 && (v31 = v30[14]) != 0 && *(_QWORD *)(v31 + 16) )
      v32 = *(unsigned int *)(v31 + 16);
    else
      v32 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v53, v32);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v33 = (char *)this[6];
      v34 = v33 + 112;
      if ( v33 )
      {
        if ( *v34 )
          v35 = *v34 + 2686LL;
        else
          v35 = 0;
        if ( *v34 )
        {
          v36 = (__int128 *)(*v34 + 2120LL);
LABEL_74:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"Release enum handle",
            (_DWORD)v36,
            v35,
            (__int64)&v53);
          goto LABEL_75;
        }
      }
      else
      {
        v35 = 0;
      }
      v36 = &v52;
      goto LABEL_74;
    }
  }
LABEL_75:
  IkeextSaDestroyEnumHandle0(BFEHandler::hFwpEngine, *a3);
  *a3 = 0;
  v45 = 259;
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_84;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, 259);
    goto LABEL_79;
  }
LABEL_80:
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 5u )
  {
    WPP_SF_d(v18[2], 45, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, *a4);
    v18 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_84:
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v57) = 0;
    LOWORD(v53) = 0;
    v37 = this[6];
    if ( v37 )
    {
      v38 = v37[14];
      if ( v38 )
      {
        if ( *(_QWORD *)(v38 + 16) )
          v9 = *(_DWORD *)(v38 + 16);
      }
    }
    ConvertPortNoToString(&v53, v9);
    FormatRRASErrorString(&v57, L"EnumSAs returns [%d] entries Status=%d", *a4, v45);
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_99;
    v39 = (char *)this[6];
    v40 = v39 + 112;
    if ( v39 )
    {
      if ( *v40 )
        v41 = *v40 + 2686LL;
      else
        v41 = 0;
      if ( *v40 )
      {
        v42 = (__int128 *)(*v40 + 2120LL);
LABEL_98:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v57,
          (_DWORD)v42,
          v41,
          (__int64)&v53);
LABEL_99:
        v18 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_100;
      }
    }
    else
    {
      v41 = 0;
    }
    v42 = &v52;
    goto LABEL_98;
  }
LABEL_100:
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 6u )
    WPP_SF_d(v18[2], 46, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v45);
  v43 = v45;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v46);
  return v43;
}

```

## disassembly

```asm
0x18002e0e8  push    rbp
0x18002e0ea  push    rbx
0x18002e0eb  push    rsi
0x18002e0ec  push    rdi
0x18002e0ed  push    r12
0x18002e0ef  push    r13
0x18002e0f1  push    r14
0x18002e0f3  push    r15
0x18002e0f5  lea     rbp, [rsp-7C8h]
0x18002e0fd  sub     rsp, 8C8h
0x18002e104  mov     rax, cs:__security_cookie
0x18002e10b  xor     rax, rsp
0x18002e10e  mov     [rbp+800h+var_50], rax
0x18002e115  mov     r12, r9
0x18002e118  mov     rbx, r8
0x18002e11b  mov     r14, rdx
0x18002e11e  mov     rdi, rcx
0x18002e121  mov     rsi, [rbp+800h+arg_20]
0x18002e128  lea     rax, WPP_GLOBAL_Control
0x18002e12f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e136  cmp     rcx, rax
0x18002e139  jz      short loc_18002E15C
0x18002e13b  test    byte ptr [rcx+1Ch], 1
0x18002e13f  jz      short loc_18002E15C
0x18002e141  cmp     byte ptr [rcx+19h], 6
0x18002e145  jb      short loc_18002E15C
0x18002e147  mov     edx, 29h ; ')'
0x18002e14c  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002e153  mov     rcx, [rcx+10h]
0x18002e157  call    WPP_SF_
0x18002e15c  xor     r13d, r13d
0x18002e15f  mov     [rsp+900h+var_8D0], r13d
0x18002e164  mov     [rbp+800h+var_850], r13d
0x18002e168  xor     edx, edx; Val
0x18002e16a  mov     r8d, 7FCh; Size
0x18002e170  lea     rcx, [rbp+800h+var_84C]; void *
0x18002e174  call    memset_0
0x18002e179  mov     [rbp+800h+var_880], r13d
0x18002e17d  xorps   xmm0, xmm0
0x18002e180  xor     eax, eax
0x18002e182  movups  [rbp+800h+var_87C], xmm0
0x18002e186  movups  [rbp+800h+var_86C], xmm0
0x18002e18a  mov     [rbp+800h+var_85C], eax
0x18002e18d  movups  [rsp+900h+var_890], xmm0
0x18002e192  xorps   xmm1, xmm1
0x18002e195  movdqu  [rsp+900h+var_8C0], xmm1
0x18002e19b  mov     [rsp+900h+var_8C8], r13
0x18002e1a0  movdqu  [rsp+900h+var_8B0], xmm0
0x18002e1a6  mov     [rsp+900h+var_8A0], r13
0x18002e1ab  or      r15d, 0FFFFFFFFh
0x18002e1af  mov     [rsp+900h+var_898], r15d
0x18002e1b4  mov     [rsp+900h+var_894], r13d
0x18002e1b9  test    cs:byte_1800AA941, 8
0x18002e1c0  jz      short loc_18002E1E8
0x18002e1c2  mov     rax, [rdi+30h]
0x18002e1c6  mov     [rsp+900h+var_8E0], rax; void *
0x18002e1cb  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18002e1d2  lea     r8, [rsp+900h+var_8D0]; unsigned int *
0x18002e1d7  lea     rdx, aBfehandlerEnum_0; "BFEHandler::EnumSA"
0x18002e1de  lea     rcx, [rsp+900h+var_8C8]; this
0x18002e1e3  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18002e1e8  mov     [rsi], r13
0x18002e1eb  cmp     [rbx], r13
0x18002e1ee  jnz     loc_18002E3C7
0x18002e1f4  test    cs:byte_1800AA941, 8
0x18002e1fb  jz      loc_18002E29F
0x18002e201  mov     word ptr [rbp+800h+var_880], r13w
0x18002e206  mov     rax, [rdi+30h]
0x18002e20a  test    rax, rax
0x18002e20d  jz      short loc_18002E223
0x18002e20f  mov     rax, [rax+70h]
0x18002e213  test    rax, rax
0x18002e216  jz      short loc_18002E223
0x18002e218  cmp     [rax+10h], r13
0x18002e21c  jz      short loc_18002E223
0x18002e21e  mov     edx, [rax+10h]
0x18002e221  jmp     short loc_18002E226
0x18002e223  mov     edx, r15d
0x18002e226  lea     rcx, [rbp+800h+var_880]
0x18002e22a  call    ConvertPortNoToString
0x18002e22f  test    cs:byte_1800AA941, 8
0x18002e236  jz      short loc_18002E29F
0x18002e238  mov     rcx, [rdi+30h]
0x18002e23c  lea     rax, [rcx+70h]
0x18002e240  test    rcx, rcx
0x18002e243  jz      short loc_18002E26F
0x18002e245  mov     rdx, [rax]
0x18002e248  test    rdx, rdx
0x18002e24b  jz      short loc_18002E256
0x18002e24d  lea     rcx, [rdx+0A7Eh]
0x18002e254  jmp     short loc_18002E25E
0x18002e256  test    rcx, rcx
0x18002e259  jz      short loc_18002E26F
0x18002e25b  mov     rcx, r13
0x18002e25e  mov     rdx, [rax]
0x18002e261  test    rdx, rdx
0x18002e264  jz      short loc_18002E272
0x18002e266  lea     r9, [rdx+848h]
0x18002e26d  jmp     short loc_18002E277
0x18002e26f  mov     rcx, r13
0x18002e272  lea     r9, [rsp+900h+var_890]
0x18002e277  lea     rax, [rbp+800h+var_880]
0x18002e27b  mov     [rsp+900h+var_8D8], rax
0x18002e280  mov     [rsp+900h+var_8E0], rcx
0x18002e285  lea     r8, aCreateEnumHand; "Create enum handle"
0x18002e28c  lea     rdx, RasVpnIkeParamTraceInfo
0x18002e293  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002e29a  call    McTemplateU0zjzz_EventWriteTransfer
0x18002e29f  mov     r8, rbx; enumHandle
0x18002e2a2  mov     rdx, r14; enumTemplate
0x18002e2a5  mov     rcx, cs:?hFwpEngine@BFEHandler@@0PEAXEA; engineHandle
0x18002e2ac  call    cs:__imp_IkeextSaCreateEnumHandle0
0x18002e2b2  mov     [rsp+900h+var_8D0], eax
0x18002e2b6  test    eax, eax
0x18002e2b8  jz      loc_18002E3C7
0x18002e2be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e2c5  lea     rbx, WPP_GLOBAL_Control
0x18002e2cc  cmp     rcx, rbx
0x18002e2cf  jz      short loc_18002E2FC
0x18002e2d1  test    byte ptr [rcx+1Ch], 1
0x18002e2d5  jz      short loc_18002E2FC
0x18002e2d7  cmp     byte ptr [rcx+19h], 2
0x18002e2db  jb      short loc_18002E2FC
0x18002e2dd  mov     edx, 2Ah ; '*'
0x18002e2e2  mov     r9d, eax
0x18002e2e5  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002e2ec  mov     rcx, [rcx+10h]
0x18002e2f0  call    WPP_SF_d
0x18002e2f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e2fc  test    cs:byte_1800AA941, 4
0x18002e303  jz      loc_18002E593
0x18002e309  mov     word ptr [rbp+800h+var_850], r13w
0x18002e30e  mov     word ptr [rbp+800h+var_880], r13w
0x18002e313  mov     rax, [rdi+30h]
0x18002e317  test    rax, rax
0x18002e31a  jz      short loc_18002E330
0x18002e31c  mov     rax, [rax+70h]
0x18002e320  test    rax, rax
0x18002e323  jz      short loc_18002E330
0x18002e325  cmp     [rax+10h], r13
0x18002e329  jz      short loc_18002E330
0x18002e32b  mov     edx, [rax+10h]
0x18002e32e  jmp     short loc_18002E333
0x18002e330  mov     edx, r15d
0x18002e333  lea     rcx, [rbp+800h+var_880]
0x18002e337  call    ConvertPortNoToString
0x18002e33c  lea     rdx, aIkeextsacreate; "IkeextSaCreateEnumHandle failed: %d"
0x18002e343  mov     r8d, [rsp+900h+var_8D0]
0x18002e348  lea     rcx, [rbp+800h+var_850]
0x18002e34c  call    FormatRRASErrorString
0x18002e351  test    cs:byte_1800AA941, 4
0x18002e358  jz      loc_18002E58C
0x18002e35e  mov     rcx, [rdi+30h]
0x18002e362  lea     rax, [rcx+70h]
0x18002e366  test    rcx, rcx
0x18002e369  jz      short loc_18002E395
0x18002e36b  mov     rdx, [rax]
0x18002e36e  test    rdx, rdx
0x18002e371  jz      short loc_18002E37C
0x18002e373  lea     rcx, [rdx+0A7Eh]
0x18002e37a  jmp     short loc_18002E384
0x18002e37c  test    rcx, rcx
0x18002e37f  jz      short loc_18002E395
0x18002e381  mov     rcx, r13
0x18002e384  mov     rdx, [rax]
0x18002e387  test    rdx, rdx
0x18002e38a  jz      short loc_18002E398
0x18002e38c  lea     r9, [rdx+848h]
0x18002e393  jmp     short loc_18002E39D
0x18002e395  mov     rcx, r13
0x18002e398  lea     r9, [rsp+900h+var_890]
0x18002e39d  lea     rax, [rbp+800h+var_880]
0x18002e3a1  mov     [rsp+900h+var_8D8], rax
0x18002e3a6  mov     [rsp+900h+var_8E0], rcx
0x18002e3ab  lea     r8, [rbp+800h+var_850]
0x18002e3af  lea     rdx, RasVpnIkeParamTraceError
0x18002e3b6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002e3bd  call    McTemplateU0zjzz_EventWriteTransfer
0x18002e3c2  jmp     loc_18002E58C
0x18002e3c7  mov     [rsp+900h+var_8E0], r12
0x18002e3cc  mov     r9, rsi
0x18002e3cf  mov     r8d, 0Ah
0x18002e3d5  mov     rdx, [rbx]
0x18002e3d8  mov     rcx, cs:?hFwpEngine@BFEHandler@@0PEAXEA; void * BFEHandler::hFwpEngine
0x18002e3df  call    cs:__imp_IkeextSaEnum2
0x18002e3e5  mov     [rsp+900h+var_8D0], eax
0x18002e3e9  test    eax, eax
0x18002e3eb  jz      loc_18002E47B
0x18002e3f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e3f8  lea     rbx, WPP_GLOBAL_Control
0x18002e3ff  cmp     rcx, rbx
0x18002e402  jz      short loc_18002E42F
0x18002e404  test    byte ptr [rcx+1Ch], 1
0x18002e408  jz      short loc_18002E42F
0x18002e40a  cmp     byte ptr [rcx+19h], 2
0x18002e40e  jb      short loc_18002E42F
0x18002e410  mov     edx, 2Bh ; '+'
0x18002e415  mov     r9d, eax
0x18002e418  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002e41f  mov     rcx, [rcx+10h]
0x18002e423  call    WPP_SF_d
0x18002e428  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e42f  test    cs:byte_1800AA941, 4
0x18002e436  jz      loc_18002E593
0x18002e43c  mov     word ptr [rbp+800h+var_850], r13w
0x18002e441  mov     word ptr [rbp+800h+var_880], r13w
0x18002e446  mov     rax, [rdi+30h]
0x18002e44a  test    rax, rax
0x18002e44d  jz      short loc_18002E463
0x18002e44f  mov     rax, [rax+70h]
0x18002e453  test    rax, rax
0x18002e456  jz      short loc_18002E463
0x18002e458  cmp     [rax+10h], r13
0x18002e45c  jz      short loc_18002E463
0x18002e45e  mov     edx, [rax+10h]
0x18002e461  jmp     short loc_18002E466
0x18002e463  mov     edx, r15d
0x18002e466  lea     rcx, [rbp+800h+var_880]
0x18002e46a  call    ConvertPortNoToString
0x18002e46f  lea     rdx, aIkeextsaenumFa; "IkeextSaEnum failed: %d"
0x18002e476  jmp     loc_18002E343
0x18002e47b  cmp     dword ptr [r12], 9
0x18002e480  ja      loc_18002E585
0x18002e486  test    cs:byte_1800AA941, 8
0x18002e48d  jz      loc_18002E531
0x18002e493  mov     word ptr [rbp+800h+var_880], r13w
0x18002e498  mov     rax, [rdi+30h]
0x18002e49c  test    rax, rax
0x18002e49f  jz      short loc_18002E4B5
0x18002e4a1  mov     rax, [rax+70h]
0x18002e4a5  test    rax, rax
0x18002e4a8  jz      short loc_18002E4B5
0x18002e4aa  cmp     [rax+10h], r13
0x18002e4ae  jz      short loc_18002E4B5
0x18002e4b0  mov     edx, [rax+10h]
0x18002e4b3  jmp     short loc_18002E4B8
0x18002e4b5  mov     edx, r15d
0x18002e4b8  lea     rcx, [rbp+800h+var_880]
0x18002e4bc  call    ConvertPortNoToString
0x18002e4c1  test    cs:byte_1800AA941, 8
0x18002e4c8  jz      short loc_18002E531
0x18002e4ca  mov     rcx, [rdi+30h]
0x18002e4ce  lea     rax, [rcx+70h]
0x18002e4d2  test    rcx, rcx
0x18002e4d5  jz      short loc_18002E501
0x18002e4d7  mov     rdx, [rax]
0x18002e4da  test    rdx, rdx
0x18002e4dd  jz      short loc_18002E4E8
0x18002e4df  lea     rcx, [rdx+0A7Eh]
0x18002e4e6  jmp     short loc_18002E4F0
0x18002e4e8  test    rcx, rcx
0x18002e4eb  jz      short loc_18002E501
0x18002e4ed  mov     rcx, r13
0x18002e4f0  mov     rdx, [rax]
0x18002e4f3  test    rdx, rdx
0x18002e4f6  jz      short loc_18002E504
0x18002e4f8  lea     r9, [rdx+848h]
0x18002e4ff  jmp     short loc_18002E509
0x18002e501  mov     rcx, r13
0x18002e504  lea     r9, [rsp+900h+var_890]
0x18002e509  lea     rax, [rbp+800h+var_880]
0x18002e50d  mov     [rsp+900h+var_8D8], rax
0x18002e512  mov     [rsp+900h+var_8E0], rcx
0x18002e517  lea     r8, aReleaseEnumHan; "Release enum handle"
0x18002e51e  lea     rdx, RasVpnIkeParamTraceInfo
0x18002e525  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002e52c  call    McTemplateU0zjzz_EventWriteTransfer
0x18002e531  mov     rdx, [rbx]; enumHandle
0x18002e534  mov     rcx, cs:?hFwpEngine@BFEHandler@@0PEAXEA; engineHandle
0x18002e53b  call    cs:__imp_IkeextSaDestroyEnumHandle0
0x18002e541  mov     [rbx], r13
0x18002e544  mov     r9d, 103h
0x18002e54a  mov     [rsp+900h+var_8D0], r9d
0x18002e54f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e556  lea     rbx, WPP_GLOBAL_Control
0x18002e55d  cmp     rcx, rbx
0x18002e560  jz      short loc_18002E5C4
0x18002e562  test    byte ptr [rcx+1Ch], 1
0x18002e566  jz      short loc_18002E593
0x18002e568  cmp     byte ptr [rcx+19h], 2
0x18002e56c  jb      short loc_18002E593
0x18002e56e  mov     edx, 2Ch ; ','
0x18002e573  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002e57a  mov     rcx, [rcx+10h]
0x18002e57e  call    WPP_SF_d
0x18002e583  jmp     short loc_18002E58C
0x18002e585  lea     rbx, WPP_GLOBAL_Control
0x18002e58c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e593  cmp     rcx, rbx
0x18002e596  jz      short loc_18002E5C4
0x18002e598  test    byte ptr [rcx+1Ch], 1
0x18002e59c  jz      short loc_18002E5C4
0x18002e59e  cmp     byte ptr [rcx+19h], 5
0x18002e5a2  jb      short loc_18002E5C4
0x18002e5a4  mov     edx, 2Dh ; '-'
0x18002e5a9  mov     r9d, [r12]
0x18002e5ad  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002e5b4  mov     rcx, [rcx+10h]
0x18002e5b8  call    WPP_SF_d
0x18002e5bd  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
