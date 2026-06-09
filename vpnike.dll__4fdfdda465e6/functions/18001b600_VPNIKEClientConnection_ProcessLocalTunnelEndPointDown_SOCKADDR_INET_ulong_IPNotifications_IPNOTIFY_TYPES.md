# VPNIKEClientConnection::ProcessLocalTunnelEndPointDown(_SOCKADDR_INET &,ulong,IPNotifications::_IPNOTIFY_TYPES_)

- ea: `0x18001b600`
- end: `0x18001b9bc`
- name: `?ProcessLocalTunnelEndPointDown@VPNIKEClientConnection@@UEAAKAEAT_SOCKADDR_INET@@KW4_IPNOTIFY_TYPES_@IPNotifications@@@Z`
- size: `956`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180004ab8`
- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x1800109c0`
- `0x18001b600`
- `0x18001f10c`
- `0x18004b20c`
- `0x18004c8a8`
- `0x18004fca8`
- `0x180050368`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `rasman!RasSetPortUserData` at `0x18001b93e`
- `rasman!RasSetPortUserData` at `0x18001b93e`

## string_xrefs

- `0x18001b78f`: `Client connection is interested in Delete notifications only.`

## pseudocode

```c
__int64 __fastcall VPNIKEClientConnection::ProcessLocalTunnelEndPointDown(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4)
{
  PVOID *v8; // rbx
  unsigned int v9; // esi
  char v10; // al
  __int64 v11; // rax
  __int64 v12; // rdx
  __int128 *v13; // r9
  __int64 v14; // rax
  __int64 v15; // rdx
  __int128 *v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rax
  __int64 v24; // rdx
  __int128 *v25; // r9
  unsigned int v26; // ebx
  unsigned int v28; // [rsp+30h] [rbp-D0h] BYREF
  int v29; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v31; // [rsp+40h] [rbp-C0h]
  __int128 v32; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+6Ch] [rbp-94h]
  __int128 v36; // [rsp+70h] [rbp-90h] BYREF
  int v37; // [rsp+80h] [rbp-80h] BYREF
  __int128 v38; // [rsp+84h] [rbp-7Ch]
  __int128 v39; // [rsp+94h] [rbp-6Ch]
  int v40; // [rsp+A4h] [rbp-5Ch]
  int v41; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v42[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v28 = 0;
  v41 = 0;
  memset_0(v42, 0, sizeof(v42));
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v36 = 0;
  v31 = 0;
  v30 = 0;
  v32 = 0;
  v33 = 0;
  v9 = -1;
  v34 = -1;
  v35 = 0;
  v10 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v30,
      L"VPNIKEClientConnection::ProcessLocalTunnelEndPointDown",
      &v28,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *(void **)(a1 + 112));
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v10 = byte_1800AA941;
  }
  if ( a4 == 2 )
  {
    v28 = VPNIKEConnection::ProcessLocalTunnelEndPointDown(a1, a2, a3);
    if ( v28 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v41) = 0;
        LOWORD(v37) = 0;
        v14 = *(_QWORD *)(a1 + 112);
        if ( v14 && *(_QWORD *)(v14 + 16) )
          v9 = *(_DWORD *)(v14 + 16);
        ConvertPortNoToString(&v37, v9);
        FormatRRASErrorString(&v41, L"ProcessLocalTunnelEndPointDown failed: %d.", v28);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v15 = *(_QWORD *)(a1 + 112);
          LODWORD(v16) = v15 + 2120;
          if ( !v15 )
            v16 = &v36;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v41,
            (_DWORD)v16,
            (v15 + 2686) & -(__int64)(v15 != 0),
            (__int64)&v37);
        }
      }
    }
    else
    {
      VPNIKEClientConnection::UpdateConnectionState((VPNIKEClientConnection *)a1, 0x200000u);
      if ( IPv4Helper::DoNegotiate(*(IPv4Helper **)(a1 + 32), v17, v18, v19) )
        IPv4Helper::UpdateDefaultRoutes(*(IPv4Helper **)(a1 + 32), 0);
      if ( IPv6Helper::DoNegotiate(*(IPv6Helper **)(a1 + 40), v20, v21, v22) )
        IPv6Helper::UpdateDefaultRoutes(*(IPv6Helper **)(a1 + 40), 0);
      v29 = 1;
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v37) = 0;
        v23 = *(_QWORD *)(a1 + 112);
        if ( v23 && *(_QWORD *)(v23 + 16) )
          v9 = *(_DWORD *)(v23 + 16);
        ConvertPortNoToString(&v37, v9);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v24 = *(_QWORD *)(a1 + 112);
          LODWORD(v25) = v24 + 2120;
          if ( !v24 )
            v25 = &v36;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)L"Setting RASPortSubStatus to RASCSS_Dormant.",
            (_DWORD)v25,
            (v24 + 2686) & -(__int64)(v24 != 0),
            (__int64)&v37);
        }
      }
      RasSetPortUserData(*(_QWORD *)(a1 + 24), 14, &v29);
      VPNIKEProtocolEngine::NotifyCaller(*(_QWORD *)(a1 + 24), 14, 0);
    }
    goto LABEL_39;
  }
  v28 = 87;
  if ( (v10 & 4) != 0 )
  {
    LOWORD(v37) = 0;
    v11 = *(_QWORD *)(a1 + 112);
    if ( v11 && *(_QWORD *)(v11 + 16) )
      v9 = *(_DWORD *)(v11 + 16);
    ConvertPortNoToString(&v37, v9);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v12 = *(_QWORD *)(a1 + 112);
      LODWORD(v13) = v12 + 2120;
      if ( !v12 )
        v13 = &v36;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)L"Client connection is interested in Delete notifications only.",
        (_DWORD)v13,
        (v12 + 2686) & -(__int64)(v12 != 0),
        (__int64)&v37);
    }
LABEL_39:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 51, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids, v28);
  v26 = v28;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v30);
  return v26;
}

```

## disassembly

```asm
0x18001b600  push    rbp
0x18001b602  push    rbx
0x18001b603  push    rsi
0x18001b604  push    rdi
0x18001b605  push    r12
0x18001b607  push    r14
0x18001b609  push    r15
0x18001b60b  lea     rbp, [rsp-7C0h]
0x18001b613  sub     rsp, 8C0h
0x18001b61a  mov     rax, cs:__security_cookie
0x18001b621  xor     rax, rsp
0x18001b624  mov     [rbp+7F0h+var_40], rax
0x18001b62b  mov     r14d, r9d
0x18001b62e  mov     r12d, r8d
0x18001b631  mov     r15, rdx
0x18001b634  mov     rdi, rcx
0x18001b637  lea     rax, WPP_GLOBAL_Control
0x18001b63e  mov     rbx, cs:WPP_GLOBAL_Control
0x18001b645  cmp     rbx, rax
0x18001b648  jz      short loc_18001B672
0x18001b64a  test    byte ptr [rbx+1Ch], 1
0x18001b64e  jz      short loc_18001B672
0x18001b650  cmp     byte ptr [rbx+19h], 6
0x18001b654  jb      short loc_18001B672
0x18001b656  mov     edx, 32h ; '2'
0x18001b65b  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001b662  mov     rcx, [rbx+10h]
0x18001b666  call    WPP_SF_
0x18001b66b  mov     rbx, cs:WPP_GLOBAL_Control
0x18001b672  mov     [rsp+8F0h+var_8C0], 0
0x18001b67a  xor     eax, eax
0x18001b67c  mov     [rbp+7F0h+var_840], eax
0x18001b67f  xor     edx, edx; Val
0x18001b681  mov     r8d, 7FCh; Size
0x18001b687  lea     rcx, [rbp+7F0h+var_83C]; void *
0x18001b68b  call    memset_0
0x18001b690  xor     eax, eax
0x18001b692  mov     [rbp+7F0h+var_870], eax
0x18001b695  xorps   xmm0, xmm0
0x18001b698  movups  [rbp+7F0h+var_86C], xmm0
0x18001b69c  movups  [rbp+7F0h+var_85C], xmm0
0x18001b6a0  mov     [rbp+7F0h+var_84C], eax
0x18001b6a3  movups  [rsp+8F0h+var_880], xmm0
0x18001b6a8  xorps   xmm1, xmm1
0x18001b6ab  movdqu  [rsp+8F0h+var_8B0], xmm1
0x18001b6b1  mov     [rsp+8F0h+var_8B8], rax
0x18001b6b6  movdqu  [rsp+8F0h+var_8A0], xmm0
0x18001b6bc  mov     [rsp+8F0h+var_890], rax
0x18001b6c1  or      esi, 0FFFFFFFFh
0x18001b6c4  mov     [rsp+8F0h+var_888], esi
0x18001b6c8  mov     [rsp+8F0h+var_884], eax
0x18001b6cc  mov     al, cs:byte_1800AA941
0x18001b6d2  test    al, 8
0x18001b6d4  jz      short loc_18001B709
0x18001b6d6  mov     rax, [rdi+70h]
0x18001b6da  mov     [rsp+8F0h+var_8D0], rax; void *
0x18001b6df  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18001b6e6  lea     r8, [rsp+8F0h+var_8C0]; unsigned int *
0x18001b6eb  lea     rdx, aVpnikeclientco_5; "VPNIKEClientConnection::ProcessLocalTun"...
0x18001b6f2  lea     rcx, [rsp+8F0h+var_8B8]; this
0x18001b6f7  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18001b6fc  mov     rbx, cs:WPP_GLOBAL_Control
0x18001b703  mov     al, cs:byte_1800AA941
0x18001b709  mov     r9d, 2
0x18001b70f  cmp     r14d, r9d
0x18001b712  jz      loc_18001B7AE
0x18001b718  mov     [rsp+8F0h+var_8C0], 57h ; 'W'
0x18001b720  test    al, 4
0x18001b722  jz      loc_18001B959
0x18001b728  xor     eax, eax
0x18001b72a  mov     word ptr [rbp+7F0h+var_870], ax
0x18001b72e  mov     rax, [rdi+70h]
0x18001b732  test    rax, rax
0x18001b735  jz      short loc_18001B741
0x18001b737  cmp     qword ptr [rax+10h], 0
0x18001b73c  jz      short loc_18001B741
0x18001b73e  mov     esi, [rax+10h]
0x18001b741  mov     edx, esi
0x18001b743  lea     rcx, [rbp+7F0h+var_870]
0x18001b747  call    ConvertPortNoToString
0x18001b74c  test    cs:byte_1800AA941, 4
0x18001b753  jz      loc_18001B952
0x18001b759  mov     rdx, [rdi+70h]
0x18001b75d  mov     rax, rdx
0x18001b760  lea     rcx, [rdx+0A7Eh]
0x18001b767  neg     rax
0x18001b76a  sbb     r8, r8
0x18001b76d  and     r8, rcx
0x18001b770  test    rdx, rdx
0x18001b773  lea     r9, [rdx+848h]
0x18001b77a  jnz     short loc_18001B781
0x18001b77c  lea     r9, [rsp+8F0h+var_880]
0x18001b781  lea     rax, [rbp+7F0h+var_870]
0x18001b785  mov     [rsp+8F0h+var_8C8], rax
0x18001b78a  mov     [rsp+8F0h+var_8D0], r8
0x18001b78f  lea     r8, aClientConnecti; "Client connection is interested in Dele"...
0x18001b796  lea     rdx, RasVpnIkeParamTraceError
0x18001b79d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001b7a4  call    McTemplateU0zjzz_EventWriteTransfer
0x18001b7a9  jmp     loc_18001B952
0x18001b7ae  mov     r8d, r12d
0x18001b7b1  mov     rdx, r15
0x18001b7b4  mov     rcx, rdi
0x18001b7b7  call    ?ProcessLocalTunnelEndPointDown@VPNIKEConnection@@UEAAKAEAT_SOCKADDR_INET@@KW4_IPNOTIFY_TYPES_@IPNotifications@@@Z; VPNIKEConnection::ProcessLocalTunnelEndPointDown(_SOCKADDR_INET &,ulong,IPNotifications::_IPNOTIFY_TYPES_)
0x18001b7bc  mov     [rsp+8F0h+var_8C0], eax
0x18001b7c0  test    eax, eax
0x18001b7c2  jz      loc_18001B85E
0x18001b7c8  test    cs:byte_1800AA941, 4
0x18001b7cf  jz      loc_18001B952
0x18001b7d5  xor     eax, eax
0x18001b7d7  mov     word ptr [rbp+7F0h+var_840], ax
0x18001b7db  mov     word ptr [rbp+7F0h+var_870], ax
0x18001b7df  mov     rax, [rdi+70h]
0x18001b7e3  test    rax, rax
0x18001b7e6  jz      short loc_18001B7F2
0x18001b7e8  cmp     qword ptr [rax+10h], 0
0x18001b7ed  jz      short loc_18001B7F2
0x18001b7ef  mov     esi, [rax+10h]
0x18001b7f2  mov     edx, esi
0x18001b7f4  lea     rcx, [rbp+7F0h+var_870]
0x18001b7f8  call    ConvertPortNoToString
0x18001b7fd  mov     r8d, [rsp+8F0h+var_8C0]
0x18001b802  lea     rdx, aProcesslocaltu; "ProcessLocalTunnelEndPointDown failed: "...
0x18001b809  lea     rcx, [rbp+7F0h+var_840]
0x18001b80d  call    FormatRRASErrorString
0x18001b812  test    cs:byte_1800AA941, 4
0x18001b819  jz      loc_18001B952
0x18001b81f  mov     rdx, [rdi+70h]
0x18001b823  mov     rax, rdx
0x18001b826  lea     rcx, [rdx+0A7Eh]
0x18001b82d  neg     rax
0x18001b830  sbb     r8, r8
0x18001b833  and     r8, rcx
0x18001b836  test    rdx, rdx
0x18001b839  lea     r9, [rdx+848h]
0x18001b840  jnz     short loc_18001B847
0x18001b842  lea     r9, [rsp+8F0h+var_880]
0x18001b847  lea     rax, [rbp+7F0h+var_870]
0x18001b84b  mov     [rsp+8F0h+var_8C8], rax
0x18001b850  mov     [rsp+8F0h+var_8D0], r8
0x18001b855  lea     r8, [rbp+7F0h+var_840]
0x18001b859  jmp     loc_18001B796
0x18001b85e  mov     edx, 200000h; unsigned int
0x18001b863  mov     rcx, rdi; this
0x18001b866  call    ?UpdateConnectionState@VPNIKEClientConnection@@IEAAXK@Z; VPNIKEClientConnection::UpdateConnectionState(ulong)
0x18001b86b  mov     rcx, [rdi+20h]; this
0x18001b86f  call    ?DoNegotiate@IPv4Helper@@QEAAEXZ; IPv4Helper::DoNegotiate(void)
0x18001b874  test    al, al
0x18001b876  jz      short loc_18001B883
0x18001b878  xor     edx, edx; unsigned __int8
0x18001b87a  mov     rcx, [rdi+20h]; this
0x18001b87e  call    ?UpdateDefaultRoutes@IPv4Helper@@QEAAXE@Z; IPv4Helper::UpdateDefaultRoutes(uchar)
0x18001b883  mov     rcx, [rdi+28h]; this
0x18001b887  call    ?DoNegotiate@IPv6Helper@@QEAAEXZ; IPv6Helper::DoNegotiate(void)
0x18001b88c  test    al, al
0x18001b88e  jz      short loc_18001B89B
0x18001b890  xor     edx, edx; unsigned __int8
0x18001b892  mov     rcx, [rdi+28h]; this
0x18001b896  call    ?UpdateDefaultRoutes@IPv6Helper@@QEAAXE@Z; IPv6Helper::UpdateDefaultRoutes(uchar)
0x18001b89b  mov     [rsp+8F0h+var_8BC], 1
0x18001b8a3  test    cs:byte_1800AA941, 4
0x18001b8aa  jz      short loc_18001B929
0x18001b8ac  xor     eax, eax
0x18001b8ae  mov     word ptr [rbp+7F0h+var_870], ax
0x18001b8b2  mov     rax, [rdi+70h]
0x18001b8b6  test    rax, rax
0x18001b8b9  jz      short loc_18001B8C5
0x18001b8bb  cmp     qword ptr [rax+10h], 0
0x18001b8c0  jz      short loc_18001B8C5
0x18001b8c2  mov     esi, [rax+10h]
0x18001b8c5  mov     edx, esi
0x18001b8c7  lea     rcx, [rbp+7F0h+var_870]
0x18001b8cb  call    ConvertPortNoToString
0x18001b8d0  test    cs:byte_1800AA941, 4
0x18001b8d7  jz      short loc_18001B929
0x18001b8d9  mov     rdx, [rdi+70h]
0x18001b8dd  mov     rax, rdx
0x18001b8e0  lea     rcx, [rdx+0A7Eh]
0x18001b8e7  neg     rax
0x18001b8ea  sbb     r8, r8
0x18001b8ed  and     r8, rcx
0x18001b8f0  test    rdx, rdx
0x18001b8f3  lea     r9, [rdx+848h]
0x18001b8fa  jnz     short loc_18001B901
0x18001b8fc  lea     r9, [rsp+8F0h+var_880]
0x18001b901  lea     rax, [rbp+7F0h+var_870]
0x18001b905  mov     [rsp+8F0h+var_8C8], rax
0x18001b90a  mov     [rsp+8F0h+var_8D0], r8
0x18001b90f  lea     r8, aSettingRasport_2; "Setting RASPortSubStatus to RASCSS_Dorm"...
0x18001b916  lea     rdx, RasVpnIkeParamTraceError
0x18001b91d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001b924  call    McTemplateU0zjzz_EventWriteTransfer
0x18001b929  mov     r9d, 4
0x18001b92f  lea     r8, [rsp+8F0h+var_8BC]
0x18001b934  lea     ebx, [r9+0Ah]
0x18001b938  mov     edx, ebx
0x18001b93a  mov     rcx, [rdi+18h]
0x18001b93e  call    cs:__imp_RasSetPortUserData
0x18001b944  xor     r8d, r8d
0x18001b947  mov     edx, ebx
0x18001b949  mov     rcx, [rdi+18h]
0x18001b94d  call    ?NotifyCaller@VPNIKEProtocolEngine@@SAXPEAXW4_PROTOCOL_RESULT_ID@@0@Z; VPNIKEProtocolEngine::NotifyCaller(void *,_PROTOCOL_RESULT_ID,void *)
0x18001b952  mov     rbx, cs:WPP_GLOBAL_Control
0x18001b959  lea     rax, WPP_GLOBAL_Control
0x18001b960  cmp     rbx, rax
0x18001b963  jz      short loc_18001B98B
0x18001b965  test    byte ptr [rbx+1Ch], 1
0x18001b969  jz      short loc_18001B98B
0x18001b96b  cmp     byte ptr [rbx+19h], 6
0x18001b96f  jb      short loc_18001B98B
0x18001b971  mov     edx, 33h ; '3'
0x18001b976  mov     r9d, [rsp+8F0h+var_8C0]
0x18001b97b  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001b982  mov     rcx, [rbx+10h]
0x18001b986  call    WPP_SF_d
0x18001b98b  mov     ebx, [rsp+8F0h+var_8C0]
0x18001b98f  lea     rcx, [rsp+8F0h+var_8B8]; this
0x18001b994  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18001b999  mov     eax, ebx
0x18001b99b  mov     rcx, [rbp+7F0h+var_40]
0x18001b9a2  xor     rcx, rsp; StackCookie
0x18001b9a5  call    __security_check_cookie
0x18001b9aa  add     rsp, 8C0h
0x18001b9b1  pop     r15
0x18001b9b3  pop     r14
0x18001b9b5  pop     r12
0x18001b9b7  pop     rdi
0x18001b9b8  pop     rsi
0x18001b9b9  pop     rbx
0x18001b9ba  pop     rbp
0x18001b9bb  retn
```
