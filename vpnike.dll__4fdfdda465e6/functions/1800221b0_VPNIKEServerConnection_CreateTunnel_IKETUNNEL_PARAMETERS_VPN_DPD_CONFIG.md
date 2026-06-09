# VPNIKEServerConnection::CreateTunnel(_IKETUNNEL_PARAMETERS_ &,_VPN_DPD_CONFIG_ *)

- ea: `0x1800221b0`
- end: `0x1800227e6`
- name: `?CreateTunnel@VPNIKEServerConnection@@UEAAKAEAU_IKETUNNEL_PARAMETERS_@@PEAU_VPN_DPD_CONFIG_@@@Z`
- size: `1590`
- prototype: `__int64 __fastcall(void **this, struct _IKETUNNEL_PARAMETERS_ *, struct _VPN_DPD_CONFIG_ *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001178`
- `0x180001208`
- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18000d620`
- `0x1800131c8`
- `0x1800135b0`
- `0x1800221b0`
- `0x180022ac0`
- `0x180023b10`
- `0x180023c64`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## string_xrefs

- `0x1800223bb`: `VPNIKEConnection::UpdateRoutes failed: %d`
- `0x180022291`: `VPNIKEServerConnection::CreateTunnel`
- `0x180022342`: `VPNIKEServerConnection::CreateTunnel failed.`

## pseudocode

```c
__int64 __fastcall VPNIKEServerConnection::CreateTunnel(
        void **this,
        struct _IKETUNNEL_PARAMETERS_ *a2,
        struct _VPN_DPD_CONFIG_ *a3)
{
  unsigned int v6; // edi
  _DWORD *v7; // rax
  void *v8; // rdx
  __int128 *v9; // r9
  _DWORD *v10; // rax
  void *v11; // rdx
  __int128 *v12; // r9
  _DWORD *v13; // rax
  void *v14; // rdx
  __int128 *v15; // r9
  _DWORD *v16; // rax
  void *v17; // rdx
  __int128 *v18; // r9
  char *v19; // rcx
  _QWORD *v20; // rcx
  _DWORD *v21; // rax
  void *v22; // rdx
  __int128 *v23; // r9
  __int64 v24; // rdx
  int v25; // ecx
  int v26; // ecx
  PVOID *v27; // rcx
  const wchar_t *v28; // r8
  __int64 v29; // rcx
  __int64 *v30; // r8
  __int64 v31; // r9
  unsigned int v32; // ebx
  unsigned int Tunnel; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v35; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v37; // [rsp+48h] [rbp-B8h]
  __int128 v38; // [rsp+58h] [rbp-A8h]
  __int64 v39; // [rsp+68h] [rbp-98h]
  int v40; // [rsp+70h] [rbp-90h]
  int v41; // [rsp+74h] [rbp-8Ch]
  __int128 v42; // [rsp+78h] [rbp-88h] BYREF
  int v43; // [rsp+88h] [rbp-78h] BYREF
  __int128 v44; // [rsp+8Ch] [rbp-74h]
  __int128 v45; // [rsp+9Ch] [rbp-64h]
  int v46; // [rsp+ACh] [rbp-54h]
  int v47; // [rsp+B0h] [rbp-50h] BYREF
  char v48[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids);
  }
  Tunnel = 0;
  v47 = 0;
  memset_0(v48, 0, sizeof(v48));
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v42 = 0;
  v37 = 0;
  v36 = 0;
  v38 = 0;
  v39 = 0;
  v6 = -1;
  v40 = -1;
  v41 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v36,
      L"VPNIKEServerConnection::CreateTunnel",
      &Tunnel,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      this[14]);
  if ( *((_DWORD *)this[14] + 368) == 2 )
    *((_BYTE *)this + 264) = 0;
  Tunnel = VPNIKEConnection::CreateTunnel((VPNIKEConnection *)this, a2, a3);
  if ( Tunnel )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v43) = 0;
      v7 = this[14];
      if ( v7 && *((_QWORD *)v7 + 2) )
        v6 = v7[4];
      ConvertPortNoToString(&v43, v6);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v8 = this[14];
        LODWORD(v9) = (_DWORD)v8 + 2120;
        if ( !v8 )
          v9 = &v42;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"VPNIKEServerConnection::CreateTunnel failed.",
          (_DWORD)v9,
          ((unsigned __int64)v8 + 2686) & -(__int64)(v8 != 0),
          (__int64)&v43);
      }
    }
    goto LABEL_89;
  }
  if ( !*((_BYTE *)this + 148) )
  {
    Tunnel = VPNIKEConnection::UpdateRoutes((VPNIKEConnection *)this);
    if ( Tunnel )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v47) = 0;
        LOWORD(v43) = 0;
        v10 = this[14];
        if ( v10 && *((_QWORD *)v10 + 2) )
          v6 = v10[4];
        ConvertPortNoToString(&v43, v6);
        FormatRRASErrorString(&v47, L"VPNIKEConnection::UpdateRoutes failed: %d", Tunnel);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v11 = this[14];
          LODWORD(v12) = (_DWORD)v11 + 2120;
          if ( !v11 )
            v12 = &v42;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v47,
            (_DWORD)v12,
            ((unsigned __int64)v11 + 2686) & -(__int64)(v11 != 0),
            (__int64)&v43);
        }
      }
      goto LABEL_89;
    }
  }
  if ( VPNIKEServerConnection::DoesNegotiatedEncryptionMatchPolicy((VPNIKEServerConnection *)this) )
  {
    Tunnel = VPNIKEServerConnection::NotifyDone((VPNIKEServerConnection *)this);
    if ( Tunnel )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v43) = 0;
        v16 = this[14];
        if ( v16 && *((_QWORD *)v16 + 2) )
          v6 = v16[4];
        ConvertPortNoToString(&v43, v6);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v17 = this[14];
          LODWORD(v18) = (_DWORD)v17 + 2120;
          if ( !v17 )
            v18 = &v42;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)L"NotifyDone failed.",
            (_DWORD)v18,
            ((unsigned __int64)v17 + 2686) & -(__int64)(v17 != 0),
            (__int64)&v43);
        }
      }
      goto LABEL_89;
    }
    v19 = (char *)this[14];
    if ( *((_DWORD *)v19 + 368) == 2
      && (v20 = v19 + 2120) != 0
      && (*v20 != *(_QWORD *)&GUID_NULL.Data1 || v20[1] != *(_QWORD *)GUID_NULL.Data4)
      || ((_DWORD)this[19] & 0x20000) != 0 )
    {
      Tunnel = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)this[16] + 8LL))(this[16]);
      if ( Tunnel )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v47) = 0;
          LOWORD(v43) = 0;
          v21 = this[14];
          if ( v21 && *((_QWORD *)v21 + 2) )
            v6 = v21[4];
          ConvertPortNoToString(&v43, v6);
          FormatRRASErrorString(&v47, L"StartAccounting failed with error: %d", Tunnel);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v22 = this[14];
            LODWORD(v23) = (_DWORD)v22 + 2120;
            if ( !v22 )
              v23 = &v42;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v47,
              (_DWORD)v23,
              ((unsigned __int64)v22 + 2686) & -(__int64)(v22 != 0),
              (__int64)&v43);
          }
        }
        Tunnel = 0;
      }
      else
      {
        VPNIKEConnection::UpdateConnectionState((VPNIKEConnection *)this, 0x80000u);
      }
    }
    (*((void (__fastcall **)(void **, char *))*this + 19))(this, (char *)VpnIkeProtocolEngine + 48);
    v25 = *((_DWORD *)this + 23);
    if ( !v25 )
    {
      v27 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids);
      }
      v28 = L"PSK";
      goto LABEL_86;
    }
    v26 = v25 - 1;
    if ( v26 )
    {
      if ( v26 != 10 )
        goto LABEL_75;
      v27 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_80:
        v28 = L"OTHER";
LABEL_86:
        if ( (unsigned int)dword_1800AA058 > 5 && (unsigned __int8)tlgKeywordOn(v27, v24, v28) )
        {
          v35 = v30;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v29,
            (__int64)qword_1800A0B30,
            (__int64)v30,
            v31,
            &v35);
        }
        goto LABEL_89;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
LABEL_71:
        if ( v27 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v27 + 28) & 1) == 0 || *((_BYTE *)v27 + 25) < 5u )
          {
LABEL_76:
            if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 1) != 0 && *((_BYTE *)v27 + 25) >= 5u )
              WPP_SF_(v27[2], 47, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids);
            goto LABEL_80;
          }
          WPP_SF_(v27[2], 46, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids);
LABEL_75:
          v27 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_76;
        }
        goto LABEL_80;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids);
    }
    v27 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_71;
  }
  Tunnel = 13868;
  if ( (byte_1800AA941 & 4) == 0 )
  {
LABEL_90:
    VPNIKEServerConnection::NotifyError((VPNIKEServerConnection *)this, Tunnel);
    goto LABEL_91;
  }
  LOWORD(v43) = 0;
  v13 = this[14];
  if ( v13 && *((_QWORD *)v13 + 2) )
    v6 = v13[4];
  ConvertPortNoToString(&v43, v6);
  if ( (byte_1800AA941 & 4) != 0 )
  {
    v14 = this[14];
    LODWORD(v15) = (_DWORD)v14 + 2120;
    if ( !v14 )
      v15 = &v42;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasVpnIkeParamTraceError,
      (unsigned int)L" Encryption does not match policy",
      (_DWORD)v15,
      ((unsigned __int64)v14 + 2686) & -(__int64)(v14 != 0),
      (__int64)&v43);
  }
LABEL_89:
  if ( Tunnel )
    goto LABEL_90;
LABEL_91:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids, Tunnel);
  }
  v32 = Tunnel;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v36);
  return v32;
}

```

## disassembly

```asm
0x1800221b0  push    rbp
0x1800221b2  push    rbx
0x1800221b3  push    rsi
0x1800221b4  push    rdi
0x1800221b5  push    r13
0x1800221b7  push    r14
0x1800221b9  push    r15
0x1800221bb  lea     rbp, [rsp-7C0h]
0x1800221c3  sub     rsp, 8C0h
0x1800221ca  mov     rax, cs:__security_cookie
0x1800221d1  xor     rax, rsp
0x1800221d4  mov     [rbp+7F0h+var_40], rax
0x1800221db  mov     r14, r8
0x1800221de  mov     rsi, rdx
0x1800221e1  mov     rbx, rcx
0x1800221e4  lea     r13, WPP_GLOBAL_Control
0x1800221eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221f2  cmp     rcx, r13
0x1800221f5  jz      short loc_180022218
0x1800221f7  test    byte ptr [rcx+1Ch], 1
0x1800221fb  jz      short loc_180022218
0x1800221fd  cmp     byte ptr [rcx+19h], 6
0x180022201  jb      short loc_180022218
0x180022203  mov     edx, 2Bh ; '+'
0x180022208  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x18002220f  mov     rcx, [rcx+10h]
0x180022213  call    WPP_SF_
0x180022218  xor     r15d, r15d
0x18002221b  mov     [rsp+8F0h+var_8C0], r15d
0x180022220  mov     [rbp+7F0h+var_840], r15d
0x180022224  xor     edx, edx; Val
0x180022226  mov     r8d, 7FCh; Size
0x18002222c  lea     rcx, [rbp+7F0h+var_83C]; void *
0x180022230  call    memset_0
0x180022235  mov     [rbp+7F0h+var_868], r15d
0x180022239  xorps   xmm0, xmm0
0x18002223c  xor     eax, eax
0x18002223e  movups  [rbp+7F0h+var_864], xmm0
0x180022242  movups  [rbp+7F0h+var_854], xmm0
0x180022246  mov     [rbp+7F0h+var_844], eax
0x180022249  movups  [rsp+8F0h+var_878], xmm0
0x18002224e  xorps   xmm1, xmm1
0x180022251  movdqu  [rsp+8F0h+var_8A8], xmm1
0x180022257  mov     [rsp+8F0h+var_8B0], r15
0x18002225c  movdqu  [rsp+8F0h+var_898], xmm0
0x180022262  mov     [rsp+8F0h+var_888], r15
0x180022267  or      edi, 0FFFFFFFFh
0x18002226a  mov     [rsp+8F0h+var_880], edi
0x18002226e  mov     [rsp+8F0h+var_87C], r15d
0x180022273  test    cs:byte_1800AA941, 8
0x18002227a  jz      short loc_1800222A2
0x18002227c  mov     rax, [rbx+70h]
0x180022280  mov     [rsp+8F0h+var_8D0], rax; void *
0x180022285  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18002228c  lea     r8, [rsp+8F0h+var_8C0]; unsigned int *
0x180022291  lea     rdx, aVpnikeserverco_26; "VPNIKEServerConnection::CreateTunnel"
0x180022298  lea     rcx, [rsp+8F0h+var_8B0]; this
0x18002229d  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x1800222a2  mov     rax, [rbx+70h]
0x1800222a6  cmp     dword ptr [rax+5C0h], 2
0x1800222ad  jnz     short loc_1800222B6
0x1800222af  mov     [rbx+108h], r15b
0x1800222b6  mov     r8, r14; struct _VPN_DPD_CONFIG_ *
0x1800222b9  mov     rdx, rsi; struct _IKETUNNEL_PARAMETERS_ *
0x1800222bc  mov     rcx, rbx; this
0x1800222bf  call    ?CreateTunnel@VPNIKEConnection@@UEAAKAEAU_IKETUNNEL_PARAMETERS_@@PEAU_VPN_DPD_CONFIG_@@@Z; VPNIKEConnection::CreateTunnel(_IKETUNNEL_PARAMETERS_ &,_VPN_DPD_CONFIG_ *)
0x1800222c4  mov     [rsp+8F0h+var_8C0], eax
0x1800222c8  test    eax, eax
0x1800222ca  jz      loc_180022361
0x1800222d0  test    cs:byte_1800AA941, 4
0x1800222d7  jz      loc_180022770
0x1800222dd  mov     word ptr [rbp+7F0h+var_868], r15w
0x1800222e2  mov     rax, [rbx+70h]
0x1800222e6  test    rax, rax
0x1800222e9  jz      short loc_1800222F4
0x1800222eb  cmp     [rax+10h], r15
0x1800222ef  jz      short loc_1800222F4
0x1800222f1  mov     edi, [rax+10h]
0x1800222f4  mov     edx, edi
0x1800222f6  lea     rcx, [rbp+7F0h+var_868]
0x1800222fa  call    ConvertPortNoToString
0x1800222ff  test    cs:byte_1800AA941, 4
0x180022306  jz      loc_180022770
0x18002230c  mov     rdx, [rbx+70h]
0x180022310  mov     rax, rdx
0x180022313  lea     rcx, [rdx+0A7Eh]
0x18002231a  neg     rax
0x18002231d  sbb     r8, r8
0x180022320  and     r8, rcx
0x180022323  test    rdx, rdx
0x180022326  lea     r9, [rdx+848h]
0x18002232d  jnz     short loc_180022334
0x18002232f  lea     r9, [rsp+8F0h+var_878]
0x180022334  lea     rax, [rbp+7F0h+var_868]
0x180022338  mov     [rsp+8F0h+var_8C8], rax
0x18002233d  mov     [rsp+8F0h+var_8D0], r8
0x180022342  lea     r8, aVpnikeserverco_0; "VPNIKEServerConnection::CreateTunnel fa"...
0x180022349  lea     rdx, RasVpnIkeParamTraceError
0x180022350  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180022357  call    McTemplateU0zjzz_EventWriteTransfer
0x18002235c  jmp     loc_180022770
0x180022361  cmp     [rbx+94h], r15b
0x180022368  jnz     loc_180022417
0x18002236e  mov     rcx, rbx; this
0x180022371  call    ?UpdateRoutes@VPNIKEConnection@@IEAAKXZ; VPNIKEConnection::UpdateRoutes(void)
0x180022376  mov     [rsp+8F0h+var_8C0], eax
0x18002237a  test    eax, eax
0x18002237c  jz      loc_180022417
0x180022382  test    cs:byte_1800AA941, 4
0x180022389  jz      loc_180022770
0x18002238f  mov     word ptr [rbp+7F0h+var_840], r15w
0x180022394  mov     word ptr [rbp+7F0h+var_868], r15w
0x180022399  mov     rax, [rbx+70h]
0x18002239d  test    rax, rax
0x1800223a0  jz      short loc_1800223AB
0x1800223a2  cmp     [rax+10h], r15
0x1800223a6  jz      short loc_1800223AB
0x1800223a8  mov     edi, [rax+10h]
0x1800223ab  mov     edx, edi
0x1800223ad  lea     rcx, [rbp+7F0h+var_868]
0x1800223b1  call    ConvertPortNoToString
0x1800223b6  mov     r8d, [rsp+8F0h+var_8C0]
0x1800223bb  lea     rdx, aVpnikeconnecti_5; "VPNIKEConnection::UpdateRoutes failed: "...
0x1800223c2  lea     rcx, [rbp+7F0h+var_840]
0x1800223c6  call    FormatRRASErrorString
0x1800223cb  test    cs:byte_1800AA941, 4
0x1800223d2  jz      loc_180022770
0x1800223d8  mov     rdx, [rbx+70h]
0x1800223dc  mov     rax, rdx
0x1800223df  lea     rcx, [rdx+0A7Eh]
0x1800223e6  neg     rax
0x1800223e9  sbb     r8, r8
0x1800223ec  and     r8, rcx
0x1800223ef  test    rdx, rdx
0x1800223f2  lea     r9, [rdx+848h]
0x1800223f9  jnz     short loc_180022400
0x1800223fb  lea     r9, [rsp+8F0h+var_878]
0x180022400  lea     rax, [rbp+7F0h+var_868]
0x180022404  mov     [rsp+8F0h+var_8C8], rax
0x180022409  mov     [rsp+8F0h+var_8D0], r8
0x18002240e  lea     r8, [rbp+7F0h+var_840]
0x180022412  jmp     loc_180022349
0x180022417  mov     rcx, rbx; this
0x18002241a  call    ?DoesNegotiatedEncryptionMatchPolicy@VPNIKEServerConnection@@IEAAEXZ; VPNIKEServerConnection::DoesNegotiatedEncryptionMatchPolicy(void)
0x18002241f  test    al, al
0x180022421  jnz     loc_1800224AD
0x180022427  mov     [rsp+8F0h+var_8C0], 362Ch
0x18002242f  test    cs:byte_1800AA941, 4
0x180022436  jz      loc_180022777
0x18002243c  mov     word ptr [rbp+7F0h+var_868], r15w
0x180022441  mov     rax, [rbx+70h]
0x180022445  test    rax, rax
0x180022448  jz      short loc_180022453
0x18002244a  cmp     [rax+10h], r15
0x18002244e  jz      short loc_180022453
0x180022450  mov     edi, [rax+10h]
0x180022453  mov     edx, edi
0x180022455  lea     rcx, [rbp+7F0h+var_868]
0x180022459  call    ConvertPortNoToString
0x18002245e  test    cs:byte_1800AA941, 4
0x180022465  jz      loc_180022770
0x18002246b  mov     rdx, [rbx+70h]
0x18002246f  mov     rax, rdx
0x180022472  lea     rcx, [rdx+0A7Eh]
0x180022479  neg     rax
0x18002247c  sbb     r8, r8
0x18002247f  and     r8, rcx
0x180022482  test    rdx, rdx
0x180022485  lea     r9, [rdx+848h]
0x18002248c  jnz     short loc_180022493
0x18002248e  lea     r9, [rsp+8F0h+var_878]
0x180022493  lea     rax, [rbp+7F0h+var_868]
0x180022497  mov     [rsp+8F0h+var_8C8], rax
0x18002249c  mov     [rsp+8F0h+var_8D0], r8
0x1800224a1  lea     r8, aEncryptionDoes; " Encryption does not match policy"
0x1800224a8  jmp     loc_180022349
0x1800224ad  mov     rcx, rbx; this
0x1800224b0  call    ?NotifyDone@VPNIKEServerConnection@@IEAAKXZ; VPNIKEServerConnection::NotifyDone(void)
0x1800224b5  mov     [rsp+8F0h+var_8C0], eax
0x1800224b9  test    eax, eax
0x1800224bb  jz      short loc_18002253B
0x1800224bd  test    cs:byte_1800AA941, 4
0x1800224c4  jz      loc_180022770
0x1800224ca  mov     word ptr [rbp+7F0h+var_868], r15w
0x1800224cf  mov     rax, [rbx+70h]
0x1800224d3  test    rax, rax
0x1800224d6  jz      short loc_1800224E1
0x1800224d8  cmp     [rax+10h], r15
0x1800224dc  jz      short loc_1800224E1
0x1800224de  mov     edi, [rax+10h]
0x1800224e1  mov     edx, edi
0x1800224e3  lea     rcx, [rbp+7F0h+var_868]
0x1800224e7  call    ConvertPortNoToString
0x1800224ec  test    cs:byte_1800AA941, 4
0x1800224f3  jz      loc_180022770
0x1800224f9  mov     rdx, [rbx+70h]
0x1800224fd  mov     rax, rdx
0x180022500  lea     rcx, [rdx+0A7Eh]
0x180022507  neg     rax
0x18002250a  sbb     r8, r8
0x18002250d  and     r8, rcx
0x180022510  test    rdx, rdx
0x180022513  lea     r9, [rdx+848h]
0x18002251a  jnz     short loc_180022521
0x18002251c  lea     r9, [rsp+8F0h+var_878]
0x180022521  lea     rax, [rbp+7F0h+var_868]
0x180022525  mov     [rsp+8F0h+var_8C8], rax
0x18002252a  mov     [rsp+8F0h+var_8D0], r8
0x18002252f  lea     r8, aNotifydoneFail; "NotifyDone failed."
0x180022536  jmp     loc_180022349
0x18002253b  mov     rcx, [rbx+70h]
0x18002253f  cmp     dword ptr [rcx+5C0h], 2
0x180022546  jnz     short loc_18002256A
0x180022548  add     rcx, 848h
0x18002254f  jz      short loc_18002256A
0x180022551  mov     rax, [rcx]
0x180022554  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18002255b  jnz     short loc_18002257A
0x18002255d  mov     rax, [rcx+8]
0x180022561  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180022568  jnz     short loc_18002257A
0x18002256a  test    dword ptr [rbx+98h], 20000h
0x180022574  jz      loc_18002264B
0x18002257a  mov     rcx, [rbx+80h]
0x180022581  mov     rax, [rcx]
0x180022584  mov     rax, [rax+8]
0x180022588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002258d  mov     [rsp+8F0h+var_8C0], eax
0x180022591  test    eax, eax
0x180022593  jnz     short loc_1800225A7
0x180022595  mov     edx, 80000h; unsigned int
0x18002259a  mov     rcx, rbx; this
0x18002259d  call    ?UpdateConnectionState@VPNIKEConnection@@IEAAXK@Z; VPNIKEConnection::UpdateConnectionState(ulong)
0x1800225a2  jmp     loc_18002264B
0x1800225a7  test    cs:byte_1800AA941, 4
0x1800225ae  jz      loc_180022646
0x1800225b4  mov     word ptr [rbp+7F0h+var_840], r15w
0x1800225b9  mov     word ptr [rbp+7F0h+var_868], r15w
0x1800225be  mov     rax, [rbx+70h]
0x1800225c2  test    rax, rax
0x1800225c5  jz      short loc_1800225D0
0x1800225c7  cmp     [rax+10h], r15
0x1800225cb  jz      short loc_1800225D0
0x1800225cd  mov     edi, [rax+10h]
0x1800225d0  mov     edx, edi
0x1800225d2  lea     rcx, [rbp+7F0h+var_868]
0x1800225d6  call    ConvertPortNoToString
0x1800225db  mov     r8d, [rsp+8F0h+var_8C0]
0x1800225e0  lea     rdx, aStartaccountin; "StartAccounting failed with error: %d"
0x1800225e7  lea     rcx, [rbp+7F0h+var_840]
0x1800225eb  call    FormatRRASErrorString
0x1800225f0  test    cs:byte_1800AA941, 4
0x1800225f7  jz      short loc_180022646
0x1800225f9  mov     rdx, [rbx+70h]
0x1800225fd  mov     rax, rdx
0x180022600  lea     rcx, [rdx+0A7Eh]
0x180022607  neg     rax
0x18002260a  sbb     r8, r8
0x18002260d  and     r8, rcx
0x180022610  test    rdx, rdx
0x180022613  lea     r9, [rdx+848h]
0x18002261a  jnz     short loc_180022621
0x18002261c  lea     r9, [rsp+8F0h+var_878]
0x180022621  lea     rax, [rbp+7F0h+var_868]
0x180022625  mov     [rsp+8F0h+var_8C8], rax
0x18002262a  mov     [rsp+8F0h+var_8D0], r8
0x18002262f  lea     r8, [rbp+7F0h+var_840]
0x180022633  lea     rdx, RasVpnIkeParamTraceError
0x18002263a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180022641  call    McTemplateU0zjzz_EventWriteTransfer
0x180022646  mov     [rsp+8F0h+var_8C0], r15d
0x18002264b  mov     rax, [rbx]
0x18002264e  mov     rdx, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180022655  add     rdx, 30h ; '0'
0x180022659  mov     rcx, rbx
0x18002265c  mov     rax, [rax+98h]
0x180022663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022668  mov     ecx, [rbx+5Ch]
0x18002266b  test    ecx, ecx
0x18002266d  jz      loc_18002270D
0x180022673  sub     ecx, 1
0x180022676  jz      short loc_1800226AA
0x180022678  cmp     ecx, 0Ah
0x18002267b  jnz     short loc_1800226D7
0x18002267d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022684  cmp     rcx, r13
0x180022687  jz      short loc_180022704
0x180022689  test    byte ptr [rcx+1Ch], 1
0x18002268d  jz      short loc_1800226B1
0x18002268f  cmp     byte ptr [rcx+19h], 5
0x180022693  jb      short loc_1800226B1
0x180022695  mov     edx, 2Dh ; '-'
0x18002269a  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x1800226a1  mov     rcx, [rcx+10h]
0x1800226a5  call    WPP_SF_
0x1800226aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800226b1  cmp     rcx, r13
0x1800226b4  jz      short loc_180022704
0x1800226b6  test    byte ptr [rcx+1Ch], 1
0x1800226ba  jz      short loc_1800226DE
  ... truncated ...
```
