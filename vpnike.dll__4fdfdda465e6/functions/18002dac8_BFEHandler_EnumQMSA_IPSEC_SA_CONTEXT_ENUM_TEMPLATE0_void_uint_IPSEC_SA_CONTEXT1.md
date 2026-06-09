# BFEHandler::EnumQMSA(IPSEC_SA_CONTEXT_ENUM_TEMPLATE0_ *,void * *,uint *,IPSEC_SA_CONTEXT1_ * * *)

- ea: `0x18002dac8`
- end: `0x18002e0e0`
- name: `?EnumQMSA@BFEHandler@@IEAAKPEAUIPSEC_SA_CONTEXT_ENUM_TEMPLATE0_@@PEAPEAXPEAIPEAPEAPEAUIPSEC_SA_CONTEXT1_@@@Z`
- size: `1560`
- prototype: `__int64 __fastcall(void **this, struct IPSEC_SA_CONTEXT_ENUM_TEMPLATE0_ *, void **, unsigned int *, struct IPSEC_SA_CONTEXT1_ ***entries)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ed60`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18002dac8`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `fwpuclnt!IPsecSaContextEnum1` at `0x18002ddbc`
- `fwpuclnt!IPsecSaContextEnum1` at `0x18002ddbc`
- `fwpuclnt!IPsecSaContextDestroyEnumHandle0` at `0x18002df2d`
- `fwpuclnt!IPsecSaContextDestroyEnumHandle0` at `0x18002df2d`
- `fwpuclnt!IPsecSaContextCreateEnumHandle0` at `0x18002dc8c`
- `fwpuclnt!IPsecSaContextCreateEnumHandle0` at `0x18002dc8c`

## string_xrefs

- `0x18002dc65`: `Create enum handle`
- `0x18002dd1c`: `IPsecSaContextCreateEnumHandle failed: %d`

## pseudocode

```c
__int64 __fastcall BFEHandler::EnumQMSA(
        void **this,
        struct IPSEC_SA_CONTEXT_ENUM_TEMPLATE0_ *a2,
        void **a3,
        unsigned int *a4,
        struct IPSEC_SA_CONTEXT1_ ***entries)
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
  DWORD v26; // eax
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids);
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
      L"BFEHandler::EnumQMSA",
      &v45,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      this[6]);
  *entries = 0;
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
  EnumHandle0 = IPsecSaContextCreateEnumHandle0(BFEHandler::hFwpEngine, a2, a3);
  v45 = EnumHandle0;
  if ( EnumHandle0 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, EnumHandle0);
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
    FormatRRASErrorString(&v57, L"IPsecSaContextCreateEnumHandle failed: %d", v45);
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
  v26 = IPsecSaContextEnum1(BFEHandler::hFwpEngine, *a3, 0xFFFFFFFF, entries, a4);
  v45 = v26;
  if ( v26 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v26);
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
    FormatRRASErrorString(&v57, L"IPsecSaContextEnum failed: %d", v45);
    goto LABEL_36;
  }
  if ( *a4 )
    goto LABEL_79;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v57) = 0;
    LOWORD(v53) = 0;
    v30 = this[6];
    if ( v30 && (v31 = v30[14]) != 0 && *(_QWORD *)(v31 + 16) )
      v32 = *(unsigned int *)(v31 + 16);
    else
      v32 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v53, v32);
    FormatRRASErrorString(&v57, L"dwNumQMSAs = %d ", *a4);
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
            (unsigned int)&v57,
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
  IPsecSaContextDestroyEnumHandle0(BFEHandler::hFwpEngine, *a3);
  *a3 = 0;
  v45 = 259;
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_84;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, 259);
    goto LABEL_79;
  }
LABEL_80:
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 5u )
  {
    WPP_SF_d(v18[2], 60, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, *a4);
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
    FormatRRASErrorString(&v57, L"EnumQMSAs returns [%d] entries Status = %d", *a4, v45);
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
    WPP_SF_d(v18[2], 61, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v45);
  v43 = v45;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v46);
  return v43;
}

```

## disassembly

```asm
0x18002dac8  push    rbp
0x18002daca  push    rbx
0x18002dacb  push    rsi
0x18002dacc  push    rdi
0x18002dacd  push    r12
0x18002dacf  push    r13
0x18002dad1  push    r14
0x18002dad3  push    r15
0x18002dad5  lea     rbp, [rsp-7C8h]
0x18002dadd  sub     rsp, 8C8h
0x18002dae4  mov     rax, cs:__security_cookie
0x18002daeb  xor     rax, rsp
0x18002daee  mov     [rbp+800h+var_50], rax
0x18002daf5  mov     r12, r9
0x18002daf8  mov     rbx, r8
0x18002dafb  mov     r14, rdx
0x18002dafe  mov     rdi, rcx
0x18002db01  mov     rsi, [rbp+800h+entries]
0x18002db08  lea     rax, WPP_GLOBAL_Control
0x18002db0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db16  cmp     rcx, rax
0x18002db19  jz      short loc_18002DB3C
0x18002db1b  test    byte ptr [rcx+1Ch], 1
0x18002db1f  jz      short loc_18002DB3C
0x18002db21  cmp     byte ptr [rcx+19h], 6
0x18002db25  jb      short loc_18002DB3C
0x18002db27  mov     edx, 38h ; '8'
0x18002db2c  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002db33  mov     rcx, [rcx+10h]
0x18002db37  call    WPP_SF_
0x18002db3c  xor     r13d, r13d
0x18002db3f  mov     [rsp+900h+var_8D0], r13d
0x18002db44  mov     [rbp+800h+var_850], r13d
0x18002db48  xor     edx, edx; Val
0x18002db4a  mov     r8d, 7FCh; Size
0x18002db50  lea     rcx, [rbp+800h+var_84C]; void *
0x18002db54  call    memset_0
0x18002db59  mov     [rbp+800h+var_880], r13d
0x18002db5d  xorps   xmm0, xmm0
0x18002db60  xor     eax, eax
0x18002db62  movups  [rbp+800h+var_87C], xmm0
0x18002db66  movups  [rbp+800h+var_86C], xmm0
0x18002db6a  mov     [rbp+800h+var_85C], eax
0x18002db6d  movups  [rsp+900h+var_890], xmm0
0x18002db72  xorps   xmm1, xmm1
0x18002db75  movdqu  [rsp+900h+var_8C0], xmm1
0x18002db7b  mov     [rsp+900h+var_8C8], r13
0x18002db80  movdqu  [rsp+900h+var_8B0], xmm0
0x18002db86  mov     [rsp+900h+var_8A0], r13
0x18002db8b  or      r15d, 0FFFFFFFFh
0x18002db8f  mov     [rsp+900h+var_898], r15d
0x18002db94  mov     [rsp+900h+var_894], r13d
0x18002db99  test    cs:byte_1800AA941, 8
0x18002dba0  jz      short loc_18002DBC8
0x18002dba2  mov     rax, [rdi+30h]
0x18002dba6  mov     [rsp+900h+numEntriesReturned], rax; void *
0x18002dbab  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18002dbb2  lea     r8, [rsp+900h+var_8D0]; unsigned int *
0x18002dbb7  lea     rdx, aBfehandlerEnum; "BFEHandler::EnumQMSA"
0x18002dbbe  lea     rcx, [rsp+900h+var_8C8]; this
0x18002dbc3  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18002dbc8  mov     [rsi], r13
0x18002dbcb  cmp     [rbx], r13
0x18002dbce  jnz     loc_18002DDA7
0x18002dbd4  test    cs:byte_1800AA941, 8
0x18002dbdb  jz      loc_18002DC7F
0x18002dbe1  mov     word ptr [rbp+800h+var_880], r13w
0x18002dbe6  mov     rax, [rdi+30h]
0x18002dbea  test    rax, rax
0x18002dbed  jz      short loc_18002DC03
0x18002dbef  mov     rax, [rax+70h]
0x18002dbf3  test    rax, rax
0x18002dbf6  jz      short loc_18002DC03
0x18002dbf8  cmp     [rax+10h], r13
0x18002dbfc  jz      short loc_18002DC03
0x18002dbfe  mov     edx, [rax+10h]
0x18002dc01  jmp     short loc_18002DC06
0x18002dc03  mov     edx, r15d
0x18002dc06  lea     rcx, [rbp+800h+var_880]
0x18002dc0a  call    ConvertPortNoToString
0x18002dc0f  test    cs:byte_1800AA941, 8
0x18002dc16  jz      short loc_18002DC7F
0x18002dc18  mov     rcx, [rdi+30h]
0x18002dc1c  lea     rax, [rcx+70h]
0x18002dc20  test    rcx, rcx
0x18002dc23  jz      short loc_18002DC4F
0x18002dc25  mov     rdx, [rax]
0x18002dc28  test    rdx, rdx
0x18002dc2b  jz      short loc_18002DC36
0x18002dc2d  lea     rcx, [rdx+0A7Eh]
0x18002dc34  jmp     short loc_18002DC3E
0x18002dc36  test    rcx, rcx
0x18002dc39  jz      short loc_18002DC4F
0x18002dc3b  mov     rcx, r13
0x18002dc3e  mov     rdx, [rax]
0x18002dc41  test    rdx, rdx
0x18002dc44  jz      short loc_18002DC52
0x18002dc46  lea     r9, [rdx+848h]
0x18002dc4d  jmp     short loc_18002DC57
0x18002dc4f  mov     rcx, r13
0x18002dc52  lea     r9, [rsp+900h+var_890]
0x18002dc57  lea     rax, [rbp+800h+var_880]
0x18002dc5b  mov     [rsp+900h+var_8D8], rax
0x18002dc60  mov     [rsp+900h+numEntriesReturned], rcx
0x18002dc65  lea     r8, aCreateEnumHand; "Create enum handle"
0x18002dc6c  lea     rdx, RasVpnIkeParamTraceInfo
0x18002dc73  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002dc7a  call    McTemplateU0zjzz_EventWriteTransfer
0x18002dc7f  mov     r8, rbx; enumHandle
0x18002dc82  mov     rdx, r14; enumTemplate
0x18002dc85  mov     rcx, cs:?hFwpEngine@BFEHandler@@0PEAXEA; engineHandle
0x18002dc8c  call    cs:__imp_IPsecSaContextCreateEnumHandle0
0x18002dc92  mov     [rsp+900h+var_8D0], eax
0x18002dc96  test    eax, eax
0x18002dc98  jz      loc_18002DDA7
0x18002dc9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dca5  lea     rbx, WPP_GLOBAL_Control
0x18002dcac  cmp     rcx, rbx
0x18002dcaf  jz      short loc_18002DCDC
0x18002dcb1  test    byte ptr [rcx+1Ch], 1
0x18002dcb5  jz      short loc_18002DCDC
0x18002dcb7  cmp     byte ptr [rcx+19h], 2
0x18002dcbb  jb      short loc_18002DCDC
0x18002dcbd  mov     edx, 39h ; '9'
0x18002dcc2  mov     r9d, eax
0x18002dcc5  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002dccc  mov     rcx, [rcx+10h]
0x18002dcd0  call    WPP_SF_d
0x18002dcd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dcdc  test    cs:byte_1800AA941, 4
0x18002dce3  jz      loc_18002DF85
0x18002dce9  mov     word ptr [rbp+800h+var_850], r13w
0x18002dcee  mov     word ptr [rbp+800h+var_880], r13w
0x18002dcf3  mov     rax, [rdi+30h]
0x18002dcf7  test    rax, rax
0x18002dcfa  jz      short loc_18002DD10
0x18002dcfc  mov     rax, [rax+70h]
0x18002dd00  test    rax, rax
0x18002dd03  jz      short loc_18002DD10
0x18002dd05  cmp     [rax+10h], r13
0x18002dd09  jz      short loc_18002DD10
0x18002dd0b  mov     edx, [rax+10h]
0x18002dd0e  jmp     short loc_18002DD13
0x18002dd10  mov     edx, r15d
0x18002dd13  lea     rcx, [rbp+800h+var_880]
0x18002dd17  call    ConvertPortNoToString
0x18002dd1c  lea     rdx, aIpsecsacontext; "IPsecSaContextCreateEnumHandle failed: "...
0x18002dd23  mov     r8d, [rsp+900h+var_8D0]
0x18002dd28  lea     rcx, [rbp+800h+var_850]
0x18002dd2c  call    FormatRRASErrorString
0x18002dd31  test    cs:byte_1800AA941, 4
0x18002dd38  jz      loc_18002DF7E
0x18002dd3e  mov     rcx, [rdi+30h]
0x18002dd42  lea     rax, [rcx+70h]
0x18002dd46  test    rcx, rcx
0x18002dd49  jz      short loc_18002DD75
0x18002dd4b  mov     rdx, [rax]
0x18002dd4e  test    rdx, rdx
0x18002dd51  jz      short loc_18002DD5C
0x18002dd53  lea     rcx, [rdx+0A7Eh]
0x18002dd5a  jmp     short loc_18002DD64
0x18002dd5c  test    rcx, rcx
0x18002dd5f  jz      short loc_18002DD75
0x18002dd61  mov     rcx, r13
0x18002dd64  mov     rdx, [rax]
0x18002dd67  test    rdx, rdx
0x18002dd6a  jz      short loc_18002DD78
0x18002dd6c  lea     r9, [rdx+848h]
0x18002dd73  jmp     short loc_18002DD7D
0x18002dd75  mov     rcx, r13
0x18002dd78  lea     r9, [rsp+900h+var_890]
0x18002dd7d  lea     rax, [rbp+800h+var_880]
0x18002dd81  mov     [rsp+900h+var_8D8], rax
0x18002dd86  mov     [rsp+900h+numEntriesReturned], rcx
0x18002dd8b  lea     r8, [rbp+800h+var_850]
0x18002dd8f  lea     rdx, RasVpnIkeParamTraceError
0x18002dd96  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002dd9d  call    McTemplateU0zjzz_EventWriteTransfer
0x18002dda2  jmp     loc_18002DF7E
0x18002dda7  mov     [rsp+900h+numEntriesReturned], r12; numEntriesReturned
0x18002ddac  mov     r9, rsi; entries
0x18002ddaf  mov     r8d, r15d; numEntriesRequested
0x18002ddb2  mov     rdx, [rbx]; enumHandle
0x18002ddb5  mov     rcx, cs:?hFwpEngine@BFEHandler@@0PEAXEA; engineHandle
0x18002ddbc  call    cs:__imp_IPsecSaContextEnum1
0x18002ddc2  mov     [rsp+900h+var_8D0], eax
0x18002ddc6  test    eax, eax
0x18002ddc8  jz      loc_18002DE58
0x18002ddce  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ddd5  lea     rbx, WPP_GLOBAL_Control
0x18002dddc  cmp     rcx, rbx
0x18002dddf  jz      short loc_18002DE0C
0x18002dde1  test    byte ptr [rcx+1Ch], 1
0x18002dde5  jz      short loc_18002DE0C
0x18002dde7  cmp     byte ptr [rcx+19h], 2
0x18002ddeb  jb      short loc_18002DE0C
0x18002dded  mov     edx, 3Ah ; ':'
0x18002ddf2  mov     r9d, eax
0x18002ddf5  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002ddfc  mov     rcx, [rcx+10h]
0x18002de00  call    WPP_SF_d
0x18002de05  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de0c  test    cs:byte_1800AA941, 4
0x18002de13  jz      loc_18002DF85
0x18002de19  mov     word ptr [rbp+800h+var_850], r13w
0x18002de1e  mov     word ptr [rbp+800h+var_880], r13w
0x18002de23  mov     rax, [rdi+30h]
0x18002de27  test    rax, rax
0x18002de2a  jz      short loc_18002DE40
0x18002de2c  mov     rax, [rax+70h]
0x18002de30  test    rax, rax
0x18002de33  jz      short loc_18002DE40
0x18002de35  cmp     [rax+10h], r13
0x18002de39  jz      short loc_18002DE40
0x18002de3b  mov     edx, [rax+10h]
0x18002de3e  jmp     short loc_18002DE43
0x18002de40  mov     edx, r15d
0x18002de43  lea     rcx, [rbp+800h+var_880]
0x18002de47  call    ConvertPortNoToString
0x18002de4c  lea     rdx, aIpsecsacontext_0; "IPsecSaContextEnum failed: %d"
0x18002de53  jmp     loc_18002DD23
0x18002de58  cmp     [r12], r13d
0x18002de5c  jnz     loc_18002DF77
0x18002de62  test    cs:byte_1800AA941, 8
0x18002de69  jz      loc_18002DF23
0x18002de6f  mov     word ptr [rbp+800h+var_850], r13w
0x18002de74  mov     word ptr [rbp+800h+var_880], r13w
0x18002de79  mov     rax, [rdi+30h]
0x18002de7d  test    rax, rax
0x18002de80  jz      short loc_18002DE96
0x18002de82  mov     rax, [rax+70h]
0x18002de86  test    rax, rax
0x18002de89  jz      short loc_18002DE96
0x18002de8b  cmp     [rax+10h], r13
0x18002de8f  jz      short loc_18002DE96
0x18002de91  mov     edx, [rax+10h]
0x18002de94  jmp     short loc_18002DE99
0x18002de96  mov     edx, r15d
0x18002de99  lea     rcx, [rbp+800h+var_880]
0x18002de9d  call    ConvertPortNoToString
0x18002dea2  mov     r8d, [r12]
0x18002dea6  lea     rdx, aDwnumqmsasD; "dwNumQMSAs = %d "
0x18002dead  lea     rcx, [rbp+800h+var_850]
0x18002deb1  call    FormatRRASErrorString
0x18002deb6  test    cs:byte_1800AA941, 8
0x18002debd  jz      short loc_18002DF23
0x18002debf  mov     rcx, [rdi+30h]
0x18002dec3  lea     rax, [rcx+70h]
0x18002dec7  test    rcx, rcx
0x18002deca  jz      short loc_18002DEF6
0x18002decc  mov     rdx, [rax]
0x18002decf  test    rdx, rdx
0x18002ded2  jz      short loc_18002DEDD
0x18002ded4  lea     rcx, [rdx+0A7Eh]
0x18002dedb  jmp     short loc_18002DEE5
0x18002dedd  test    rcx, rcx
0x18002dee0  jz      short loc_18002DEF6
0x18002dee2  mov     rcx, r13
0x18002dee5  mov     rdx, [rax]
0x18002dee8  test    rdx, rdx
0x18002deeb  jz      short loc_18002DEF9
0x18002deed  lea     r9, [rdx+848h]
0x18002def4  jmp     short loc_18002DEFE
0x18002def6  mov     rcx, r13
0x18002def9  lea     r9, [rsp+900h+var_890]
0x18002defe  lea     rax, [rbp+800h+var_880]
0x18002df02  mov     [rsp+900h+var_8D8], rax
0x18002df07  mov     [rsp+900h+numEntriesReturned], rcx
0x18002df0c  lea     r8, [rbp+800h+var_850]
0x18002df10  lea     rdx, RasVpnIkeParamTraceInfo
0x18002df17  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002df1e  call    McTemplateU0zjzz_EventWriteTransfer
0x18002df23  mov     rdx, [rbx]; enumHandle
0x18002df26  mov     rcx, cs:?hFwpEngine@BFEHandler@@0PEAXEA; engineHandle
0x18002df2d  call    cs:__imp_IPsecSaContextDestroyEnumHandle0
0x18002df33  mov     [rbx], r13
0x18002df36  mov     r9d, 103h
0x18002df3c  mov     [rsp+900h+var_8D0], r9d
0x18002df41  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df48  lea     rbx, WPP_GLOBAL_Control
0x18002df4f  cmp     rcx, rbx
0x18002df52  jz      short loc_18002DFB6
0x18002df54  test    byte ptr [rcx+1Ch], 1
0x18002df58  jz      short loc_18002DF85
0x18002df5a  cmp     byte ptr [rcx+19h], 2
0x18002df5e  jb      short loc_18002DF85
0x18002df60  mov     edx, 3Bh ; ';'
0x18002df65  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002df6c  mov     rcx, [rcx+10h]
0x18002df70  call    WPP_SF_d
0x18002df75  jmp     short loc_18002DF7E
0x18002df77  lea     rbx, WPP_GLOBAL_Control
0x18002df7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df85  cmp     rcx, rbx
0x18002df88  jz      short loc_18002DFB6
0x18002df8a  test    byte ptr [rcx+1Ch], 1
0x18002df8e  jz      short loc_18002DFB6
0x18002df90  cmp     byte ptr [rcx+19h], 5
0x18002df94  jb      short loc_18002DFB6
0x18002df96  mov     edx, 3Ch ; '<'
  ... truncated ...
```
