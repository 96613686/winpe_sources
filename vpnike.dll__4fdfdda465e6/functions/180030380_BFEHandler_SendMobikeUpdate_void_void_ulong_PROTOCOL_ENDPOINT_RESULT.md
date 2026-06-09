# BFEHandler::SendMobikeUpdate(void (*)(void *,ulong),_PROTOCOL_ENDPOINT_RESULT &)

- ea: `0x180030380`
- end: `0x180030879`
- name: `?SendMobikeUpdate@BFEHandler@@UEAAKP6AXPEAXK@ZAEAU_PROTOCOL_ENDPOINT_RESULT@@@Z`
- size: `1273`
- prototype: `__int64 __fastcall(void **this, void (*)(void *, unsigned int), struct _PROTOCOL_ENDPOINT_RESULT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180030380`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `fwpuclnt!IkeextSaUpdatePreferredAddressesByTunnelId0` at `0x1800305a2`
- `fwpuclnt!IkeextSaUpdatePreferredAddressesByTunnelId0` at `0x1800305a2`
- `WS2_32!__imp_ntohl` at `0x1800304ed`
- `WS2_32!__imp_ntohl` at `0x1800304fa`
- `WS2_32!__imp_ntohl` at `0x1800304ed`
- `WS2_32!__imp_ntohl` at `0x1800304fa`

## string_xrefs

- `0x180030479`: `BFEHandler::SendMobikeUpdate`
- `0x180030632`: `IkeextSaUpdatePreferredAddressesByTunnelId0 returned: %!WINERROR!`

## pseudocode

```c
__int64 __fastcall BFEHandler::SendMobikeUpdate(
        void **this,
        void (*a2)(void *, unsigned int),
        struct _PROTOCOL_ENDPOINT_RESULT *a3)
{
  PVOID *v6; // rbx
  unsigned int v7; // r14d
  char v8; // al
  unsigned int updated; // ebx
  _QWORD *v10; // rax
  __int64 v11; // rax
  char *v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rcx
  __int128 *v15; // r9
  unsigned int v17; // edi
  _QWORD *v18; // rax
  __int64 v19; // rax
  char *v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // rcx
  __int128 *v23; // r9
  unsigned int v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v26; // [rsp+40h] [rbp-C0h]
  __int128 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+6Ch] [rbp-94h]
  __int128 v31; // [rsp+70h] [rbp-90h] BYREF
  __int128 v32; // [rsp+80h] [rbp-80h]
  int v33; // [rsp+90h] [rbp-70h]
  __int128 v34; // [rsp+98h] [rbp-68h] BYREF
  int v35; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v36; // [rsp+ACh] [rbp-54h]
  __int128 v37; // [rsp+BCh] [rbp-44h]
  int v38; // [rsp+CCh] [rbp-34h]
  int v39; // [rsp+D0h] [rbp-30h] BYREF
  char v40[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v24 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v39 = 0;
  memset_0(v40, 0, sizeof(v40));
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v34 = 0;
  v26 = 0;
  v25 = 0;
  v27 = 0;
  v28 = 0;
  v7 = -1;
  v29 = -1;
  v30 = 0;
  v8 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v25,
      L"BFEHandler::SendMobikeUpdate",
      &v24,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      this[6]);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v8 = byte_1800AA941;
  }
  v31 = 0;
  v32 = 0;
  v33 = 0;
  if ( *(_DWORD *)a3 == 1 )
  {
    if ( *((_DWORD *)a3 + 5) == 1 )
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 5u )
        WPP_SF_(v6[2], 35, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids);
      LODWORD(v31) = 0;
      DWORD1(v31) = ntohl(*((_DWORD *)a3 + 1));
      DWORD1(v32) = ntohl(*((_DWORD *)a3 + 6));
      goto LABEL_21;
    }
LABEL_47:
    v17 = 87;
    v24 = 87;
    if ( (v8 & 4) == 0 )
    {
LABEL_63:
      if ( v6 == &WPP_GLOBAL_Control )
      {
LABEL_71:
        EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v25);
        return v17;
      }
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      {
        WPP_SF_d(v6[2], 37, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v17);
        v17 = v24;
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_67:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 6u )
      {
        WPP_SF_d(v6[2], 38, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v17);
        v17 = v24;
      }
      goto LABEL_71;
    }
    LOWORD(v39) = 0;
    LOWORD(v35) = 0;
    v18 = this[6];
    if ( v18 )
    {
      v19 = v18[14];
      if ( v19 )
      {
        if ( *(_QWORD *)(v19 + 16) )
          v7 = *(_DWORD *)(v19 + 16);
      }
    }
    ConvertPortNoToString(&v35, v7);
    FormatRRASErrorString(&v39, L"Invalid tunnel endpoints: %d", v24);
    if ( (byte_1800AA941 & 4) == 0 )
    {
LABEL_62:
      v17 = v24;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( !v24 )
        goto LABEL_67;
      goto LABEL_63;
    }
    v20 = (char *)this[6];
    v21 = v20 + 112;
    if ( v20 )
    {
      if ( *v21 )
        v22 = *v21 + 2686LL;
      else
        v22 = 0;
      if ( *v21 )
      {
        v23 = (__int128 *)(*v21 + 2120LL);
LABEL_61:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v39,
          (_DWORD)v23,
          v22,
          (__int64)&v35);
        goto LABEL_62;
      }
    }
    else
    {
      v22 = 0;
    }
    v23 = &v34;
    goto LABEL_61;
  }
  if ( *(_DWORD *)a3 != 2 || *((_DWORD *)a3 + 5) != 2 )
    goto LABEL_47;
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_(v6[2], 36, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids);
  LODWORD(v31) = 1;
  DWORD1(v31) = *((_DWORD *)a3 + 1);
  *((_QWORD *)&v31 + 1) = *((_QWORD *)a3 + 1);
  LODWORD(v32) = *((_DWORD *)a3 + 4);
  DWORD1(v32) = *((_DWORD *)a3 + 6);
  *((_QWORD *)&v32 + 1) = *(_QWORD *)((char *)a3 + 28);
  v33 = *((_DWORD *)a3 + 9);
LABEL_21:
  _InterlockedIncrement((volatile signed __int32 *)this[6] + 51);
  updated = IkeextSaUpdatePreferredAddressesByTunnelId0(
              BFEHandler::hFwpEngine,
              *((_QWORD *)this[6] + 1),
              &v31,
              a2,
              this[6]);
  v24 = updated;
  if ( !updated )
    goto LABEL_42;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, updated);
  }
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v39) = 0;
    LOWORD(v35) = 0;
    v10 = this[6];
    if ( v10 )
    {
      v11 = v10[14];
      if ( v11 )
      {
        if ( *(_QWORD *)(v11 + 16) )
          v7 = *(_DWORD *)(v11 + 16);
      }
    }
    ConvertPortNoToString(&v35, v7);
    FormatRRASErrorString(&v39, L"IkeextSaUpdatePreferredAddressesByTunnelId0 returned: %!WINERROR!", v24);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v12 = (char *)this[6];
      v13 = v12 + 112;
      if ( v12 )
      {
        if ( *v13 )
          v14 = *v13 + 2686LL;
        else
          v14 = 0;
        if ( *v13 )
        {
          v15 = (__int128 *)(*v13 + 2120LL);
LABEL_40:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v39,
            (_DWORD)v15,
            v14,
            (__int64)&v35);
          goto LABEL_41;
        }
      }
      else
      {
        v14 = 0;
      }
      v15 = &v34;
      goto LABEL_40;
    }
  }
LABEL_41:
  BaseConnection::DeleteRef((BaseConnection *)this[6]);
  updated = v24;
LABEL_42:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, updated);
    updated = v24;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v25);
  return updated;
}

```

## disassembly

```asm
0x180030380  mov     [rsp-8+arg_18], rbx
0x180030385  push    rbp
0x180030386  push    rsi
0x180030387  push    rdi
0x180030388  push    r14
0x18003038a  push    r15
0x18003038c  lea     rbp, [rsp-7E0h]
0x180030394  sub     rsp, 8E0h
0x18003039b  mov     rax, cs:__security_cookie
0x1800303a2  xor     rax, rsp
0x1800303a5  mov     [rbp+800h+var_30], rax
0x1800303ac  mov     rdi, r8
0x1800303af  mov     r15, rdx
0x1800303b2  mov     rsi, rcx
0x1800303b5  lea     rax, WPP_GLOBAL_Control
0x1800303bc  mov     rbx, cs:WPP_GLOBAL_Control
0x1800303c3  cmp     rbx, rax
0x1800303c6  jz      short loc_1800303F0
0x1800303c8  test    byte ptr [rbx+1Ch], 1
0x1800303cc  jz      short loc_1800303F0
0x1800303ce  cmp     byte ptr [rbx+19h], 6
0x1800303d2  jb      short loc_1800303F0
0x1800303d4  mov     edx, 22h ; '"'
0x1800303d9  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x1800303e0  mov     rcx, [rbx+10h]
0x1800303e4  call    WPP_SF_
0x1800303e9  mov     rbx, cs:WPP_GLOBAL_Control
0x1800303f0  mov     [rsp+900h+var_8D0], 0
0x1800303f8  xorps   xmm0, xmm0
0x1800303fb  xor     eax, eax
0x1800303fd  movups  [rsp+900h+var_890], xmm0
0x180030402  movups  [rbp+800h+var_880], xmm0
0x180030406  mov     [rbp+800h+var_870], eax
0x180030409  mov     [rbp+800h+var_830], eax
0x18003040c  xor     edx, edx; Val
0x18003040e  mov     r8d, 7FCh; Size
0x180030414  lea     rcx, [rbp+800h+var_82C]; void *
0x180030418  call    memset_0
0x18003041d  xor     eax, eax
0x18003041f  mov     [rbp+800h+var_858], eax
0x180030422  xorps   xmm0, xmm0
0x180030425  movups  [rbp+800h+var_854], xmm0
0x180030429  movups  [rbp+800h+var_844], xmm0
0x18003042d  mov     [rbp+800h+var_834], eax
0x180030430  movups  [rbp+800h+var_868], xmm0
0x180030434  xorps   xmm1, xmm1
0x180030437  movdqu  [rsp+900h+var_8C0], xmm1
0x18003043d  mov     [rsp+900h+var_8C8], rax
0x180030442  movdqu  [rsp+900h+var_8B0], xmm0
0x180030448  mov     [rsp+900h+var_8A0], rax
0x18003044d  or      r14d, 0FFFFFFFFh
0x180030451  mov     [rsp+900h+var_898], r14d
0x180030456  mov     [rsp+900h+var_894], eax
0x18003045a  mov     al, cs:byte_1800AA941
0x180030460  test    al, 8
0x180030462  jz      short loc_180030497
0x180030464  mov     rax, [rsi+30h]
0x180030468  mov     [rsp+900h+var_8E0], rax; void *
0x18003046d  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180030474  lea     r8, [rsp+900h+var_8D0]; unsigned int *
0x180030479  lea     rdx, aBfehandlerSend_0; "BFEHandler::SendMobikeUpdate"
0x180030480  lea     rcx, [rsp+900h+var_8C8]; this
0x180030485  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18003048a  mov     rbx, cs:WPP_GLOBAL_Control
0x180030491  mov     al, cs:byte_1800AA941
0x180030497  xorps   xmm0, xmm0
0x18003049a  xor     ecx, ecx
0x18003049c  movups  [rsp+900h+var_890], xmm0
0x1800304a1  movups  [rbp+800h+var_880], xmm0
0x1800304a5  mov     [rbp+800h+var_870], ecx
0x1800304a8  cmp     dword ptr [rdi], 1
0x1800304ab  jnz     short loc_180030505
0x1800304ad  cmp     dword ptr [rdi+14h], 1
0x1800304b1  jnz     loc_180030705
0x1800304b7  lea     rax, WPP_GLOBAL_Control
0x1800304be  cmp     rbx, rax
0x1800304c1  jz      short loc_1800304E2
0x1800304c3  test    byte ptr [rbx+1Ch], 1
0x1800304c7  jz      short loc_1800304E2
0x1800304c9  cmp     byte ptr [rbx+19h], 5
0x1800304cd  jb      short loc_1800304E2
0x1800304cf  lea     edx, [rcx+23h]
0x1800304d2  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x1800304d9  mov     rcx, [rbx+10h]
0x1800304dd  call    WPP_SF_
0x1800304e2  mov     dword ptr [rsp+900h+var_890], 0
0x1800304ea  mov     ecx, [rdi+4]; netlong
0x1800304ed  call    cs:__imp_ntohl
0x1800304f3  mov     dword ptr [rsp+900h+var_890+4], eax
0x1800304f7  mov     ecx, [rdi+18h]; netlong
0x1800304fa  call    cs:__imp_ntohl
0x180030500  mov     dword ptr [rbp+800h+var_880+4], eax
0x180030503  jmp     short loc_18003057B
0x180030505  cmp     dword ptr [rdi], 2
0x180030508  jnz     loc_180030705
0x18003050e  cmp     dword ptr [rdi+14h], 2
0x180030512  jnz     loc_180030705
0x180030518  lea     rax, WPP_GLOBAL_Control
0x18003051f  cmp     rbx, rax
0x180030522  jz      short loc_180030545
0x180030524  test    byte ptr [rbx+1Ch], 1
0x180030528  jz      short loc_180030545
0x18003052a  cmp     byte ptr [rbx+19h], 5
0x18003052e  jb      short loc_180030545
0x180030530  mov     edx, 24h ; '$'
0x180030535  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18003053c  mov     rcx, [rbx+10h]
0x180030540  call    WPP_SF_
0x180030545  mov     dword ptr [rsp+900h+var_890], 1
0x18003054d  mov     eax, [rdi+4]
0x180030550  mov     dword ptr [rsp+900h+var_890+4], eax
0x180030554  movsd   xmm0, qword ptr [rdi+8]
0x180030559  movsd   qword ptr [rsp+900h+var_890+8], xmm0
0x18003055f  mov     eax, [rdi+10h]
0x180030562  mov     dword ptr [rbp+800h+var_880], eax
0x180030565  mov     eax, [rdi+18h]
0x180030568  mov     dword ptr [rbp+800h+var_880+4], eax
0x18003056b  movsd   xmm0, qword ptr [rdi+1Ch]
0x180030570  movsd   qword ptr [rbp+800h+var_880+8], xmm0
0x180030575  mov     eax, [rdi+24h]
0x180030578  mov     [rbp+800h+var_870], eax
0x18003057b  mov     rax, [rsi+30h]
0x18003057f  lock inc dword ptr [rax+0CCh]
0x180030586  mov     rdx, [rsi+30h]
0x18003058a  mov     [rsp+900h+var_8E0], rdx
0x18003058f  mov     r9, r15
0x180030592  lea     r8, [rsp+900h+var_890]
0x180030597  mov     rdx, [rdx+8]
0x18003059b  mov     rcx, cs:?hFwpEngine@BFEHandler@@0PEAXEA; void * BFEHandler::hFwpEngine
0x1800305a2  call    cs:__imp_IkeextSaUpdatePreferredAddressesByTunnelId0
0x1800305a8  mov     ebx, eax
0x1800305aa  mov     [rsp+900h+var_8D0], eax
0x1800305ae  test    eax, eax
0x1800305b0  jz      loc_1800306B9
0x1800305b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305bd  lea     rax, WPP_GLOBAL_Control
0x1800305c4  cmp     rcx, rax
0x1800305c7  jz      short loc_1800305ED
0x1800305c9  test    byte ptr [rcx+1Ch], 1
0x1800305cd  jz      short loc_1800305ED
0x1800305cf  cmp     byte ptr [rcx+19h], 2
0x1800305d3  jb      short loc_1800305ED
0x1800305d5  mov     edx, 27h ; '''
0x1800305da  mov     r9d, ebx
0x1800305dd  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x1800305e4  mov     rcx, [rcx+10h]
0x1800305e8  call    WPP_SF_d
0x1800305ed  test    cs:byte_1800AA941, 4
0x1800305f4  jz      loc_1800306AC
0x1800305fa  xor     eax, eax
0x1800305fc  mov     word ptr [rbp+800h+var_830], ax
0x180030600  mov     word ptr [rbp+800h+var_858], ax
0x180030604  mov     rax, [rsi+30h]
0x180030608  test    rax, rax
0x18003060b  jz      short loc_180030621
0x18003060d  mov     rax, [rax+70h]
0x180030611  test    rax, rax
0x180030614  jz      short loc_180030621
0x180030616  cmp     qword ptr [rax+10h], 0
0x18003061b  jz      short loc_180030621
0x18003061d  mov     r14d, [rax+10h]
0x180030621  mov     edx, r14d
0x180030624  lea     rcx, [rbp+800h+var_858]
0x180030628  call    ConvertPortNoToString
0x18003062d  mov     r8d, [rsp+900h+var_8D0]
0x180030632  lea     rdx, aIkeextsaupdate_0; "IkeextSaUpdatePreferredAddressesByTunne"...
0x180030639  lea     rcx, [rbp+800h+var_830]
0x18003063d  call    FormatRRASErrorString
0x180030642  test    cs:byte_1800AA941, 4
0x180030649  jz      short loc_1800306AC
0x18003064b  mov     rcx, [rsi+30h]
0x18003064f  lea     rax, [rcx+70h]
0x180030653  test    rcx, rcx
0x180030656  jz      short loc_180030681
0x180030658  mov     rdx, [rax]
0x18003065b  test    rdx, rdx
0x18003065e  jz      short loc_180030669
0x180030660  lea     rcx, [rdx+0A7Eh]
0x180030667  jmp     short loc_180030670
0x180030669  test    rcx, rcx
0x18003066c  jz      short loc_180030681
0x18003066e  xor     ecx, ecx
0x180030670  mov     rdx, [rax]
0x180030673  test    rdx, rdx
0x180030676  jz      short loc_180030683
0x180030678  lea     r9, [rdx+848h]
0x18003067f  jmp     short loc_180030687
0x180030681  xor     ecx, ecx
0x180030683  lea     r9, [rbp+800h+var_868]
0x180030687  lea     rax, [rbp+800h+var_858]
0x18003068b  mov     [rsp+900h+var_8D8], rax
0x180030690  mov     [rsp+900h+var_8E0], rcx
0x180030695  lea     r8, [rbp+800h+var_830]
0x180030699  lea     rdx, RasVpnIkeParamTraceError
0x1800306a0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800306a7  call    McTemplateU0zjzz_EventWriteTransfer
0x1800306ac  mov     rcx, [rsi+30h]; this
0x1800306b0  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x1800306b5  mov     ebx, [rsp+900h+var_8D0]
0x1800306b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306c0  lea     rax, WPP_GLOBAL_Control
0x1800306c7  cmp     rcx, rax
0x1800306ca  jz      short loc_1800306F4
0x1800306cc  test    byte ptr [rcx+1Ch], 1
0x1800306d0  jz      short loc_1800306F4
0x1800306d2  cmp     byte ptr [rcx+19h], 6
0x1800306d6  jb      short loc_1800306F4
0x1800306d8  mov     edx, 28h ; '('
0x1800306dd  mov     r9d, ebx
0x1800306e0  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x1800306e7  mov     rcx, [rcx+10h]
0x1800306eb  call    WPP_SF_d
0x1800306f0  mov     ebx, [rsp+900h+var_8D0]
0x1800306f4  lea     rcx, [rsp+900h+var_8C8]; this
0x1800306f9  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800306fe  mov     eax, ebx
0x180030700  jmp     loc_180030853
0x180030705  mov     edi, 57h ; 'W'
0x18003070a  mov     [rsp+900h+var_8D0], edi
0x18003070e  test    al, 4
0x180030710  jz      loc_1800307DF
0x180030716  xor     eax, eax
0x180030718  mov     word ptr [rbp+800h+var_830], ax
0x18003071c  mov     word ptr [rbp+800h+var_858], ax
0x180030720  mov     rax, [rsi+30h]
0x180030724  test    rax, rax
0x180030727  jz      short loc_18003073C
0x180030729  mov     rax, [rax+70h]
0x18003072d  test    rax, rax
0x180030730  jz      short loc_18003073C
0x180030732  cmp     [rax+10h], rcx
0x180030736  jz      short loc_18003073C
0x180030738  mov     r14d, [rax+10h]
0x18003073c  mov     edx, r14d
0x18003073f  lea     rcx, [rbp+800h+var_858]
0x180030743  call    ConvertPortNoToString
0x180030748  mov     r8d, [rsp+900h+var_8D0]
0x18003074d  lea     rdx, aInvalidTunnelE; "Invalid tunnel endpoints: %d"
0x180030754  lea     rcx, [rbp+800h+var_830]
0x180030758  call    FormatRRASErrorString
0x18003075d  test    cs:byte_1800AA941, 4
0x180030764  jz      short loc_1800307C7
0x180030766  mov     rcx, [rsi+30h]
0x18003076a  lea     rax, [rcx+70h]
0x18003076e  test    rcx, rcx
0x180030771  jz      short loc_18003079C
0x180030773  mov     rdx, [rax]
0x180030776  test    rdx, rdx
0x180030779  jz      short loc_180030784
0x18003077b  lea     rcx, [rdx+0A7Eh]
0x180030782  jmp     short loc_18003078B
0x180030784  test    rcx, rcx
0x180030787  jz      short loc_18003079C
0x180030789  xor     ecx, ecx
0x18003078b  mov     rdx, [rax]
0x18003078e  test    rdx, rdx
0x180030791  jz      short loc_18003079E
0x180030793  lea     r9, [rdx+848h]
0x18003079a  jmp     short loc_1800307A2
0x18003079c  xor     ecx, ecx
0x18003079e  lea     r9, [rbp+800h+var_868]
0x1800307a2  lea     rax, [rbp+800h+var_858]
0x1800307a6  mov     [rsp+900h+var_8D8], rax
0x1800307ab  mov     [rsp+900h+var_8E0], rcx
0x1800307b0  lea     r8, [rbp+800h+var_830]
0x1800307b4  lea     rdx, RasVpnIkeParamTraceError
0x1800307bb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800307c2  call    McTemplateU0zjzz_EventWriteTransfer
0x1800307c7  mov     edi, [rsp+900h+var_8D0]
0x1800307cb  mov     rbx, cs:WPP_GLOBAL_Control
0x1800307d2  test    edi, edi
0x1800307d4  jnz     short loc_1800307DF
0x1800307d6  lea     rsi, WPP_GLOBAL_Control
0x1800307dd  jmp     short loc_18003081A
0x1800307df  lea     rsi, WPP_GLOBAL_Control
0x1800307e6  cmp     rbx, rsi
0x1800307e9  jz      short loc_180030847
0x1800307eb  test    byte ptr [rbx+1Ch], 1
0x1800307ef  jz      short loc_18003081A
0x1800307f1  cmp     byte ptr [rbx+19h], 2
0x1800307f5  jb      short loc_18003081A
0x1800307f7  mov     edx, 25h ; '%'
0x1800307fc  mov     r9d, edi
0x1800307ff  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x180030806  mov     rcx, [rbx+10h]
0x18003080a  call    WPP_SF_d
0x18003080f  mov     edi, [rsp+900h+var_8D0]
0x180030813  mov     rbx, cs:WPP_GLOBAL_Control
0x18003081a  cmp     rbx, rsi
0x18003081d  jz      short loc_180030847
0x18003081f  test    byte ptr [rbx+1Ch], 1
0x180030823  jz      short loc_180030847
0x180030825  cmp     byte ptr [rbx+19h], 6
0x180030829  jb      short loc_180030847
0x18003082b  mov     edx, 26h ; '&'
0x180030830  mov     r9d, edi
0x180030833  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18003083a  mov     rcx, [rbx+10h]
0x18003083e  call    WPP_SF_d
0x180030843  mov     edi, [rsp+900h+var_8D0]
  ... truncated ...
```
