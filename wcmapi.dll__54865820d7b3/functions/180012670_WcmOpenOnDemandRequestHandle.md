# WcmOpenOnDemandRequestHandle

- ea: `0x180012670`
- end: `0x180012b08`
- name: `WcmOpenOnDemandRequestHandle`
- size: `1176`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task`

## callees

- `0x180001858`
- `0x180002728`
- `0x180004450`
- `0x1800044b0`
- `0x1800065d4`
- `0x180008a90`
- `0x18000c7c0`
- `0x18000c8e0`
- `0x18000d264`
- `0x18000e6c8`
- `0x1800111dc`
- `0x180012670`
- `0x18001473c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180012775`
- `RPCRT4!NdrClientCall3` at `0x180012775`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180012941`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180012941`
- `RPCRT4!RpcExceptionFilter` at `0x18001d277`
- `RPCRT4!RpcExceptionFilter` at `0x18001d299`
- `RPCRT4!RpcExceptionFilter` at `0x18001d277`
- `RPCRT4!RpcExceptionFilter` at `0x18001d299`
- `MobileNetworking!HtNewHandle` at `0x1800128d0`
- `MobileNetworking!HtNewHandle` at `0x1800128d0`

## string_xrefs

- `0x180012713`: `WcmOpenOnDemandRequestHandle`
- `0x180012acb`: `WcmOpenOnDemandRequestHandle`

## pseudocode

```c
__int64 __fastcall WcmOpenOnDemandRequestHandle(
        int a1,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        __int64 a5,
        _QWORD *a6)
{
  __int64 v10; // rax
  CLIENT_CALL_RETURN v11; // rax
  unsigned int Pointer; // ebx
  int v13; // ebx
  unsigned int v14; // eax
  WcmPolicyManager *v15; // rcx
  __int64 v16; // rdx
  struct WCM_ONDEMAND_HANDLE_CONTEXT *v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned int v20; // r9d
  struct WCM_ONDEMAND_HANDLE_CONTEXT *v22; // [rsp+78h] [rbp-4D0h] BYREF
  __int64 v23; // [rsp+80h] [rbp-4C8h]
  WCHAR *v24; // [rsp+88h] [rbp-4C0h]
  unsigned __int16 *Simple; // [rsp+90h] [rbp-4B8h]
  __int64 v26; // [rsp+98h] [rbp-4B0h]
  const unsigned __int16 *v27; // [rsp+A0h] [rbp-4A8h]
  __int64 v28; // [rsp+A8h] [rbp-4A0h] BYREF
  GUID v29; // [rsp+B0h] [rbp-498h]
  void *ContextHandle; // [rsp+C0h] [rbp-488h] BYREF
  __int64 v31; // [rsp+C8h] [rbp-480h] BYREF
  _WORD v32[8]; // [rsp+D0h] [rbp-478h] BYREF
  unsigned __int16 v33[264]; // [rsp+E0h] [rbp-468h] BYREF
  WCHAR Filename[264]; // [rsp+2F0h] [rbp-258h] BYREF

  v24 = (WCHAR *)a2;
  v10 = a5;
  v23 = a5;
  v26 = (__int64)a6;
  ContextHandle = 0;
  v31 = 0;
  v22 = 0;
  v32[0] = 0;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      91,
      &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      "WcmOpenOnDemandRequestHandle");
    v10 = v23;
  }
  v11.Pointer = NdrClientCall3(
                  (MIDL_STUBLESS_PROXY_INFO *)&stru_18001F060,
                  0xBu,
                  0,
                  v32,
                  a1,
                  a2,
                  a3,
                  a4,
                  v10,
                  &ContextHandle).Pointer;
  Pointer = (unsigned int)v11.Pointer;
  Simple = (unsigned __int16 *)v11.Simple;
  if ( LODWORD(v11.Pointer) )
  {
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
        LODWORD(v11.Pointer));
    }
    v13 = ServiceStatus(Pointer);
    goto LABEL_23;
  }
  v14 = ClientCreateOnDemandContext(&v22);
  v13 = v14;
  if ( v14 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WcmPolicyManager *)&WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 25)
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_23;
    }
    v16 = 94;
LABEL_16:
    WPP_SF_D(*((_QWORD *)v15 + 2), v16, &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids, v14);
    goto LABEL_23;
  }
  v17 = v22;
  *(_QWORD *)v22 = ContextHandle;
  v14 = HtNewHandle(g_hHandleTable, v17, 1129074260, ClientDestroyOnDemandContext, 1, &v31);
  v13 = v14;
  if ( !v14 )
  {
    v18 = v31;
    *a6 = v31;
    *((_QWORD *)v22 + 1) = v18;
    goto LABEL_23;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v16 = 95;
    goto LABEL_16;
  }
LABEL_23:
  if ( v13 )
  {
    if ( ContextHandle )
      RpcCloseOnDemandRequestHandle(&ContextHandle);
    if ( v22 )
      ClientDestroyOnDemandContext((char *)v22);
  }
  GetContextInfo(Filename, v33);
  if ( (unsigned int)dword_18002A000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18002A000, 0x400000000000LL) )
  {
    v26 = 2048;
    Simple = v33;
    v24 = Filename;
    v27 = a2;
    LODWORD(v22) = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v19,
      byte_180024BD5);
  }
  if ( v13 > 0 )
    v20 = (unsigned __int16)v13 | 0x80070000;
  else
    v20 = v13;
  v28 = 4;
  v29 = GUID_NULL;
  NetworkingTriageScenario::OnDemand::OnDemandRequestByPackageNameAction(
    (const struct NetworkingTriageScenario::OnDemand::RequiredFields *)&v28,
    a2,
    (const unsigned __int16 *)(v23 + 512),
    v20);
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sL(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      96,
      (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      (unsigned int)"WcmOpenOnDemandRequestHandle",
      v13);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180012670  push    rbx
0x180012672  push    rsi
0x180012673  push    rdi
0x180012674  push    r12
0x180012676  push    r13
0x180012678  push    r14
0x18001267a  push    r15
0x18001267c  sub     rsp, 510h
0x180012683  mov     rax, cs:__security_cookie
0x18001268a  xor     rax, rsp
0x18001268d  mov     [rsp+548h+var_48], rax
0x180012695  mov     ebx, r9d
0x180012698  mov     r13d, r8d
0x18001269b  mov     r15, rdx
0x18001269e  mov     r12d, ecx
0x1800126a1  mov     [rsp+548h+var_4D8], ecx
0x1800126a5  mov     [rsp+548h+var_4C0], rdx
0x1800126ad  mov     [rsp+548h+var_4E0], r8d
0x1800126b2  mov     rax, [rsp+548h+arg_20]
0x1800126ba  mov     [rsp+548h+var_4C8], rax
0x1800126c2  mov     rsi, [rsp+548h+arg_28]
0x1800126ca  mov     [rsp+548h+var_4B0], rsi
0x1800126d2  xor     edi, edi
0x1800126d4  mov     [rsp+548h+ContextHandle], rdi
0x1800126dc  mov     [rsp+548h+var_480], rdi
0x1800126e4  mov     [rsp+548h+var_4D0], rdi
0x1800126e9  mov     [rsp+548h+var_478], di
0x1800126f1  lea     r14, WPP_GLOBAL_Control
0x1800126f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126ff  cmp     rcx, r14
0x180012702  jz      short loc_180012732
0x180012704  cmp     byte ptr [rcx+19h], 5
0x180012708  jb      short loc_180012732
0x18001270a  test    byte ptr [rcx+1Ch], 1
0x18001270e  jz      short loc_180012732
0x180012710  lea     edx, [rdi+5Bh]
0x180012713  lea     r9, aWcmopenondeman_2; "WcmOpenOnDemandRequestHandle"
0x18001271a  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180012721  mov     rcx, [rcx+10h]
0x180012725  call    WPP_SF_s
0x18001272a  mov     rax, [rsp+548h+var_4C8]
0x180012732  mov     [rsp+548h+var_4B8], rdi
0x18001273a  lea     rcx, [rsp+548h+ContextHandle]
0x180012742  mov     [rsp+548h+var_500], rcx
0x180012747  mov     [rsp+548h+var_508], rax
0x18001274c  mov     dword ptr [rsp+548h+var_510], ebx
0x180012750  mov     dword ptr [rsp+548h+var_518], r13d
0x180012755  mov     [rsp+548h+var_520], r15
0x18001275a  mov     dword ptr [rsp+548h+var_528], r12d
0x18001275f  lea     r9, [rsp+548h+var_478]
0x180012767  xor     r8d, r8d; pReturnValue
0x18001276a  lea     edx, [r8+0Bh]; nProcNum
0x18001276e  lea     rcx, stru_18001F060; pProxyInfo
0x180012775  call    cs:__imp_NdrClientCall3
0x18001277c  nop     dword ptr [rax+rax+00h]
0x180012781  mov     rbx, rax
0x180012784  mov     [rsp+548h+var_4B8], rax
0x18001278c  mov     [rsp+548h+var_4E8], eax
0x180012790  mov     rcx, cs:WPP_GLOBAL_Control
0x180012797  jmp     short loc_180012800
0x180012799  mov     ebx, eax
0x18001279b  mov     [rsp+548h+var_4E8], eax
0x18001279f  lea     rdx, WPP_GLOBAL_Control
0x1800127a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127ad  cmp     rcx, rdx
0x1800127b0  jz      short loc_1800127DD
0x1800127b2  cmp     byte ptr [rcx+19h], 1
0x1800127b6  jb      short loc_1800127DD
0x1800127b8  test    byte ptr [rcx+1Ch], 1
0x1800127bc  jz      short loc_1800127DD
0x1800127be  mov     edx, 5Ch ; '\'
0x1800127c3  mov     r9d, eax
0x1800127c6  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x1800127cd  mov     rcx, [rcx+10h]
0x1800127d1  call    WPP_SF_D
0x1800127d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127dd  xor     edi, edi
0x1800127df  lea     r14, WPP_GLOBAL_Control
0x1800127e6  mov     r13d, [rsp+548h+var_4E0]
0x1800127eb  mov     r12d, [rsp+548h+var_4D8]
0x1800127f0  mov     r15, [rsp+548h+var_4C0]
0x1800127f8  mov     rsi, [rsp+548h+var_4B0]
0x180012800  test    ebx, ebx
0x180012802  jz      short loc_18001283F
0x180012804  cmp     rcx, r14
0x180012807  jz      short loc_18001282D
0x180012809  cmp     byte ptr [rcx+19h], 1
0x18001280d  jb      short loc_18001282D
0x18001280f  test    byte ptr [rcx+1Ch], 1
0x180012813  jz      short loc_18001282D
0x180012815  mov     edx, 5Dh ; ']'
0x18001281a  mov     r9d, ebx
0x18001281d  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180012824  mov     rcx, [rcx+10h]
0x180012828  call    WPP_SF_D
0x18001282d  mov     ecx, ebx; unsigned int
0x18001282f  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x180012834  mov     ebx, eax
0x180012836  mov     [rsp+548h+var_4E8], eax
0x18001283a  jmp     loc_18001291C
0x18001283f  lea     rcx, [rsp+548h+var_4D0]; struct WCM_ONDEMAND_HANDLE_CONTEXT **
0x180012844  call    ?ClientCreateOnDemandContext@@YAKPEAPEAUWCM_ONDEMAND_HANDLE_CONTEXT@@@Z; ClientCreateOnDemandContext(WCM_ONDEMAND_HANDLE_CONTEXT * *)
0x180012849  mov     ebx, eax
0x18001284b  mov     [rsp+548h+var_4E8], eax
0x18001284f  test    eax, eax
0x180012851  jz      short loc_180012894
0x180012853  mov     rcx, cs:WPP_GLOBAL_Control
0x18001285a  cmp     rcx, r14
0x18001285d  jz      loc_18001291C
0x180012863  cmp     byte ptr [rcx+19h], 1
0x180012867  jb      loc_18001291C
0x18001286d  test    byte ptr [rcx+1Ch], 1
0x180012871  jz      loc_18001291C
0x180012877  mov     edx, 5Eh ; '^'
0x18001287c  mov     r9d, eax
0x18001287f  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180012886  mov     rcx, [rcx+10h]
0x18001288a  call    WPP_SF_D
0x18001288f  jmp     loc_18001291C
0x180012894  mov     rax, [rsp+548h+ContextHandle]
0x18001289c  mov     rcx, [rsp+548h+var_4D0]
0x1800128a1  mov     [rcx], rax
0x1800128a4  lea     rax, [rsp+548h+var_480]
0x1800128ac  mov     [rsp+548h+var_520], rax
0x1800128b1  mov     dword ptr [rsp+548h+var_528], 1
0x1800128b9  lea     r9, ?ClientDestroyOnDemandContext@@YAXPEAX@Z; ClientDestroyOnDemandContext(void *)
0x1800128c0  mov     r8d, 434C4E54h
0x1800128c6  mov     rdx, rcx
0x1800128c9  mov     rcx, cs:g_hHandleTable
0x1800128d0  call    cs:__imp_HtNewHandle
0x1800128d7  nop     dword ptr [rax+rax+00h]
0x1800128dc  mov     ebx, eax
0x1800128de  mov     [rsp+548h+var_4E8], eax
0x1800128e2  test    eax, eax
0x1800128e4  jz      short loc_180012908
0x1800128e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128ed  cmp     rcx, r14
0x1800128f0  jz      short loc_18001291C
0x1800128f2  cmp     byte ptr [rcx+19h], 1
0x1800128f6  jb      short loc_18001291C
0x1800128f8  test    byte ptr [rcx+1Ch], 1
0x1800128fc  jz      short loc_18001291C
0x1800128fe  mov     edx, 5Fh ; '_'
0x180012903  jmp     loc_18001287C
0x180012908  mov     rcx, [rsp+548h+var_480]
0x180012910  mov     [rsi], rcx
0x180012913  mov     rax, [rsp+548h+var_4D0]
0x180012918  mov     [rax+8], rcx
0x18001291c  test    ebx, ebx
0x18001291e  jz      short loc_180012979
0x180012920  cmp     [rsp+548h+ContextHandle], rdi
0x180012928  jz      short loc_18001296A
0x18001292a  lea     rcx, [rsp+548h+ContextHandle]
0x180012932  call    RpcCloseOnDemandRequestHandle
0x180012937  jmp     short loc_18001296A
0x180012939  lea     rcx, [rsp+548h+ContextHandle]; ContextHandle
0x180012941  call    cs:__imp_RpcSsDestroyClientContext
0x180012948  nop     dword ptr [rax+rax+00h]
0x18001294d  lea     r14, WPP_GLOBAL_Control
0x180012954  mov     ebx, [rsp+548h+var_4E8]
0x180012958  mov     r13d, [rsp+548h+var_4E0]
0x18001295d  mov     r12d, [rsp+548h+var_4D8]
0x180012962  mov     r15, [rsp+548h+var_4C0]
0x18001296a  mov     rcx, [rsp+548h+var_4D0]; lpMem
0x18001296f  test    rcx, rcx
0x180012972  jz      short loc_180012979
0x180012974  call    ?ClientDestroyOnDemandContext@@YAXPEAX@Z; ClientDestroyOnDemandContext(void *)
0x180012979  lea     rdx, [rsp+548h+var_468]; unsigned __int16 *
0x180012981  lea     rcx, [rsp+548h+Filename]; lpFilename
0x180012989  call    ?GetContextInfo@@YAXPEAG0@Z; GetContextInfo(ushort *,ushort *)
0x18001298e  mov     eax, cs:dword_18002A000
0x180012994  cmp     eax, 5
0x180012997  jbe     loc_180012A5B
0x18001299d  mov     rdx, 400000000000h
0x1800129a7  lea     rcx, dword_18002A000
0x1800129ae  call    _tlgKeywordOn
0x1800129b3  test    al, al
0x1800129b5  jz      loc_180012A5B
0x1800129bb  mov     [rsp+548h+var_4B0], 800h
0x1800129c7  lea     rax, [rsp+548h+var_468]
0x1800129cf  mov     [rsp+548h+var_4B8], rax
0x1800129d7  lea     rax, [rsp+548h+Filename]
0x1800129df  mov     [rsp+548h+var_4C0], rax
0x1800129e7  mov     [rsp+548h+var_4D8], ebx
0x1800129eb  mov     [rsp+548h+var_4E0], r13d
0x1800129f0  mov     [rsp+548h+var_4A8], r15
0x1800129f8  mov     dword ptr [rsp+548h+var_4D0], r12d
0x1800129fd  lea     rax, [rsp+548h+var_4B0]
0x180012a05  mov     [rsp+548h+var_4F8], rax
0x180012a0a  lea     rax, [rsp+548h+var_4B8]
0x180012a12  mov     [rsp+548h+var_500], rax
0x180012a17  lea     rax, [rsp+548h+var_4C0]
0x180012a1f  mov     [rsp+548h+var_508], rax
0x180012a24  lea     rax, [rsp+548h+var_4D8]
0x180012a29  mov     [rsp+548h+var_510], rax
0x180012a2e  lea     rax, [rsp+548h+var_4E0]
0x180012a33  mov     [rsp+548h+var_518], rax
0x180012a38  lea     rax, [rsp+548h+var_4A8]
0x180012a40  mov     [rsp+548h+var_520], rax
0x180012a45  lea     rax, [rsp+548h+var_4D0]
0x180012a4a  mov     [rsp+548h+var_528], rax
0x180012a4f  lea     rdx, byte_180024BD5
0x180012a56  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@U1@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3344AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180012a5b  test    ebx, ebx
0x180012a5d  jg      short loc_180012A64
0x180012a5f  mov     r9d, ebx
0x180012a62  jmp     short loc_180012A6F
0x180012a64  movzx   r9d, bx
0x180012a68  or      r9d, 80070000h; int
0x180012a6f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180012a76  mov     [rsp+548h+var_4A0], 4
0x180012a82  movdqu  [rsp+548h+var_498], xmm0
0x180012a8b  mov     r8, [rsp+548h+var_4C8]
0x180012a93  add     r8, 200h; unsigned __int16 *
0x180012a9a  mov     rdx, r15; unsigned __int16 *
0x180012a9d  lea     rcx, [rsp+548h+var_4A0]; struct NetworkingTriageScenario::OnDemand::RequiredFields *
0x180012aa5  call    ?OnDemandRequestByPackageNameAction@OnDemand@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBG1J@Z; NetworkingTriageScenario::OnDemand::OnDemandRequestByPackageNameAction(NetworkingTriageScenario::OnDemand::RequiredFields const &,ushort const *,ushort const *,long)
0x180012aaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ab1  cmp     rcx, r14
0x180012ab4  jz      short loc_180012AE2
0x180012ab6  cmp     byte ptr [rcx+19h], 5
0x180012aba  jb      short loc_180012AE2
0x180012abc  test    byte ptr [rcx+1Ch], 1
0x180012ac0  jz      short loc_180012AE2
0x180012ac2  mov     edx, 60h ; '`'
0x180012ac7  mov     dword ptr [rsp+548h+var_528], ebx
0x180012acb  lea     r9, aWcmopenondeman_2; "WcmOpenOnDemandRequestHandle"
0x180012ad2  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180012ad9  mov     rcx, [rcx+10h]
0x180012add  call    WPP_SF_sL
0x180012ae2  mov     eax, ebx
0x180012ae4  mov     rcx, [rsp+548h+var_48]
0x180012aec  xor     rcx, rsp; StackCookie
0x180012aef  call    __security_check_cookie
0x180012af4  add     rsp, 510h
0x180012afb  pop     r15
0x180012afd  pop     r14
0x180012aff  pop     r13
0x180012b01  pop     r12
0x180012b03  pop     rdi
0x180012b04  pop     rsi
0x180012b05  pop     rbx
0x180012b06  retn
0x18001d269  push    rbp
0x18001d26b  sub     rsp, 60h
0x18001d26f  mov     rbp, rdx
0x18001d272  mov     rcx, [rcx]
0x18001d275  mov     ecx, [rcx]; ExceptionCode
0x18001d277  call    cs:__imp_RpcExceptionFilter
0x18001d27e  nop     dword ptr [rax+rax+00h]
0x18001d283  nop
0x18001d284  add     rsp, 60h
0x18001d288  pop     rbp
0x18001d289  retn
0x18001d28b  push    rbp
0x18001d28d  sub     rsp, 60h
0x18001d291  mov     rbp, rdx
0x18001d294  mov     rcx, [rcx]
0x18001d297  mov     ecx, [rcx]; ExceptionCode
0x18001d299  call    cs:__imp_RpcExceptionFilter
0x18001d2a0  nop     dword ptr [rax+rax+00h]
0x18001d2a5  nop
0x18001d2a6  add     rsp, 60h
0x18001d2aa  pop     rbp
0x18001d2ab  retn
```
