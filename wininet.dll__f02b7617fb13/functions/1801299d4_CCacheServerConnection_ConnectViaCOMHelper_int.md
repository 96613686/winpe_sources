# CCacheServerConnection::ConnectViaCOMHelper(int)

- ea: `0x1801299d4`
- end: `0x180129e21`
- name: `?ConnectViaCOMHelper@CCacheServerConnection@@AEAAJH@Z`
- size: `1101`
- prototype: `__int64 __fastcall(CCacheServerConnection *__hidden this, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1801299c0`

## callees

- `0x18001e408`
- `0x18001eaec`
- `0x180027ec0`
- `0x180046a1c`
- `0x180121278`
- `0x180121da4`
- `0x1801299d4`
- `0x18012ad4c`
- `0x18012af48`
- `0x18012b018`
- `0x18014a7a0`
- `0x18015fa24`
- `0x18015fd10`
- `0x1801e1790`
- `0x1801ee010`

## import_xrefs

- `RPCRT4!RpcBindingBind` at `0x180129ca2`
- `RPCRT4!RpcBindingBind` at `0x180129ca2`
- `RPCRT4!RpcBindingSetOption` at `0x180129c70`
- `RPCRT4!RpcBindingSetOption` at `0x180129c70`
- `RPCRT4!RpcBindingUnbind` at `0x180129b29`
- `RPCRT4!RpcBindingUnbind` at `0x180129d41`
- `RPCRT4!RpcBindingUnbind` at `0x180129b29`
- `RPCRT4!RpcBindingUnbind` at `0x180129d41`
- `RPCRT4!RpcBindingFree` at `0x180129b32`
- `RPCRT4!RpcBindingFree` at `0x180129d51`
- `RPCRT4!RpcBindingFree` at `0x180129b32`
- `RPCRT4!RpcBindingFree` at `0x180129d51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129d1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129d1a`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x180129b0a`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x180129b0a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180129a74`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180129bba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180129a74`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180129bba`

## pseudocode

```c
__int64 __fastcall CCacheServerConnection::ConnectViaCOMHelper(RPC_BINDING_HANDLE *this, unsigned int a2)
{
  IStream *v3; // rbx
  IUnknown *v5; // rdi
  int v6; // r12d
  int started; // esi
  int ManagerInterface; // eax
  __int64 v9; // rcx
  DWORD v10; // r8d
  int IWininetBroker; // eax
  RPC_STATUS v12; // eax
  RPC_STATUS v13; // eax
  unsigned int v15; // [rsp+30h] [rbp-50h] BYREF
  int v16; // [rsp+34h] [rbp-4Ch]
  LPSTREAM pStm; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int8 *v18; // [rsp+40h] [rbp-40h] BYREF
  IUnknown *v19; // [rsp+48h] [rbp-38h] BYREF
  RPC_BINDING_HANDLE hBinding; // [rsp+50h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-28h] BYREF
  int v22; // [rsp+60h] [rbp-20h] BYREF
  LPVOID v23; // [rsp+68h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-10h] BYREF

  v3 = 0;
  v16 = 0;
  pStm = 0;
  ppv = 0;
  v5 = 0;
  v23 = 0;
  v6 = 0;
  v19 = 0;
  pv = 0;
  hBinding = 0;
  v22 = 0;
  v18 = 0;
  v15 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 10, WPP_9c4c3569cf513e10024214760e760dc6_Traceguids, a2);
  started = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &ppv);
  if ( started < 0 )
  {
    v16 = 254;
    goto LABEL_45;
  }
  if ( a2 )
  {
    started = CWxMemoryStream::CreateInstance(&pStm);
    if ( started < 0 )
    {
      v3 = pStm;
      v16 = 278;
      goto LABEL_45;
    }
    ManagerInterface = CCacheServerConnection::SafeGetManagerInterface((CCacheServerConnection *)this, &v18, &v15);
    v3 = pStm;
    started = ManagerInterface;
    if ( ManagerInterface < 0 )
    {
      v16 = 283;
      goto LABEL_45;
    }
    started = CWxMemoryStream::AttachBuffer(pStm, &v18, v15);
    if ( started < 0 )
    {
      v16 = 288;
      goto LABEL_45;
    }
    started = CoUnmarshalInterface(v3, &IID_IUrlCacheManager, &v23);
    if ( started < 0 )
    {
      v16 = 289;
      goto LABEL_45;
    }
    RpcBindingUnbind(this[3]);
    RpcBindingFree(this + 3);
    this[3] = 0;
  }
  else if ( (unsigned int)IsProcessLessThanMediumIL()
         || GlobalKirAppBrokerForMediumILUWPApps && (unsigned int)IsPackagedProcess() )
  {
    IWininetBroker = GetIWininetBrokerEx(v9, &v19);
    v5 = v19;
    started = IWininetBroker;
    if ( IWininetBroker < 0 )
    {
      v16 = 310;
      goto LABEL_45;
    }
    started = ((__int64 (__fastcall *)(IUnknown *, LPVOID *))v19->lpVtbl[1].QueryInterface)(v19, &v23);
    if ( started < 0 )
    {
      v16 = 312;
      goto LABEL_45;
    }
  }
  else
  {
    v10 = 65540;
    if ( GlobalIsWow64 )
      v10 = 589828;
    started = CoCreateInstance(&CLSID_UrlCacheManager, 0, v10, &IID_IUrlCacheManager, &v23);
    if ( started < 0 )
    {
      v16 = 326;
      goto LABEL_45;
    }
  }
  started = (*(__int64 (__fastcall **)(LPVOID, LPVOID, GUID *, int *))(*(_QWORD *)ppv + 24LL))(
              ppv,
              v23,
              &IID_IUrlCacheManager,
              &v22);
  if ( started >= 0 )
  {
    started = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v23 + 24LL))(v23, &pv);
    if ( started >= 0 )
    {
      started = WxRpcBindingCreate((const unsigned __int16 *)pv, &hBinding);
      if ( started >= 0 )
      {
        v12 = RpcBindingSetOption(hBinding, 9u, 1u);
        started = v12;
        if ( v12 > 0 )
          started = (unsigned __int16)v12 | 0x80070000;
        if ( started >= 0 )
        {
          v13 = RpcBindingBind(0, hBinding, qword_1801EF030);
          started = v13;
          if ( v13 > 0 )
            started = (unsigned __int16)v13 | 0x80070000;
          if ( started >= 0 )
          {
            v6 = 1;
            started = CCacheServerConnection::StartMTAThread((CCacheServerConnection *)this);
            if ( started >= 0 )
            {
              started = CWxString::Set((CWxString *)(this + 1), (const unsigned __int16 *)pv);
              if ( started >= 0 )
              {
                this[3] = hBinding;
                *((_DWORD *)this + 1) = v22;
                v22 = 0;
                hBinding = 0;
              }
              else
              {
                v16 = 379;
              }
            }
            else
            {
              v16 = 377;
            }
          }
          else
          {
            v16 = 367;
          }
        }
        else
        {
          v16 = 365;
        }
      }
      else
      {
        v16 = 359;
      }
    }
    else
    {
      v16 = 353;
    }
  }
  else
  {
    v16 = 348;
  }
LABEL_45:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v18 )
    WxFreeHeapEx(&v18);
  if ( v6 )
  {
    if ( !hBinding )
      goto LABEL_54;
    RpcBindingUnbind(hBinding);
  }
  if ( hBinding )
  {
    RpcBindingFree(&hBinding);
    hBinding = 0;
    CWxString::Empty((CWxString *)(this + 1));
  }
LABEL_54:
  if ( v22 && ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
    v22 = 0;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 11, WPP_9c4c3569cf513e10024214760e760dc6_Traceguids, (unsigned int)started);
  if ( v3 )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v5 )
    ((void (__fastcall *)(IUnknown *))v5->lpVtbl->Release)(v5);
  if ( v23 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1801299d4  mov     [rsp-38h+arg_10], rbx
0x1801299d9  push    rbp
0x1801299da  push    rsi
0x1801299db  push    rdi
0x1801299dc  push    r12
0x1801299de  push    r13
0x1801299e0  push    r14
0x1801299e2  push    r15
0x1801299e4  mov     rbp, rsp
0x1801299e7  sub     rsp, 80h
0x1801299ee  mov     rax, cs:__security_cookie
0x1801299f5  xor     rax, rsp
0x1801299f8  mov     [rbp+var_8], rax
0x1801299fc  xor     r13d, r13d
0x1801299ff  mov     r15d, edx
0x180129a02  mov     ebx, r13d
0x180129a05  mov     [rbp+var_4C], r13d
0x180129a09  mov     [rbp+pStm], rbx
0x180129a0d  mov     r14, rcx
0x180129a10  mov     [rbp+var_10], r13
0x180129a14  mov     edi, r13d
0x180129a17  mov     [rbp+var_18], r13
0x180129a1b  mov     r12d, r13d
0x180129a1e  mov     [rbp+var_38], r13
0x180129a22  mov     [rbp+pv], r13
0x180129a26  mov     [rbp+hBinding], r13
0x180129a2a  mov     [rbp+var_20], r13d
0x180129a2e  mov     [rbp+var_40], r13
0x180129a32  mov     [rbp+var_50], r13d
0x180129a36  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180129a3d  jz      short loc_180129A57
0x180129a3f  lea     edx, [r13+0Ah]
0x180129a43  mov     ecx, 40Ch
0x180129a48  mov     r9d, r15d
0x180129a4b  lea     r8, WPP_9c4c3569cf513e10024214760e760dc6_Traceguids
0x180129a52  call    WPP_SF_d
0x180129a57  xor     edx, edx; pUnkOuter
0x180129a59  lea     rax, [rbp+var_10]
0x180129a5d  lea     r9, IID_IGlobalInterfaceTable; riid
0x180129a64  mov     [rsp+80h+ppv], rax; ppv
0x180129a69  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180129a70  lea     r8d, [rdx+1]; dwClsContext
0x180129a74  call    cs:__imp_CoCreateInstance
0x180129a7a  mov     esi, eax
0x180129a7c  test    eax, eax
0x180129a7e  jns     short loc_180129A8C
0x180129a80  mov     [rbp+var_4C], 0FEh
0x180129a87  jmp     loc_180129D11
0x180129a8c  test    r15d, r15d
0x180129a8f  jz      loc_180129B70
0x180129a95  lea     rcx, [rbp+pStm]; struct CWxMemoryStream **
0x180129a99  call    ?CreateInstance@CWxMemoryStream@@SAJPEAPEAV1@@Z; CWxMemoryStream::CreateInstance(CWxMemoryStream * *)
0x180129a9e  mov     esi, eax
0x180129aa0  test    eax, eax
0x180129aa2  jns     short loc_180129AB4
0x180129aa4  mov     rbx, [rbp+pStm]
0x180129aa8  mov     [rbp+var_4C], 116h
0x180129aaf  jmp     loc_180129D11
0x180129ab4  lea     r8, [rbp+var_50]; unsigned int *
0x180129ab8  mov     rcx, r14; this
0x180129abb  lea     rdx, [rbp+var_40]; unsigned __int8 **
0x180129abf  call    ?SafeGetManagerInterface@CCacheServerConnection@@AEAAJPEAPEAEPEAK@Z; CCacheServerConnection::SafeGetManagerInterface(uchar * *,ulong *)
0x180129ac4  mov     rbx, [rbp+pStm]
0x180129ac8  mov     esi, eax
0x180129aca  test    eax, eax
0x180129acc  jns     short loc_180129ADA
0x180129ace  mov     [rbp+var_4C], 11Bh
0x180129ad5  jmp     loc_180129D11
0x180129ada  mov     r8d, [rbp+var_50]; unsigned int
0x180129ade  lea     rdx, [rbp+var_40]; unsigned __int8 **
0x180129ae2  mov     rcx, rbx; this
0x180129ae5  call    ?AttachBuffer@CWxMemoryStream@@QEAAJPEAPEAEK@Z; CWxMemoryStream::AttachBuffer(uchar * *,ulong)
0x180129aea  mov     esi, eax
0x180129aec  test    eax, eax
0x180129aee  jns     short loc_180129AFC
0x180129af0  mov     [rbp+var_4C], 120h
0x180129af7  jmp     loc_180129D11
0x180129afc  lea     r8, [rbp+var_18]; ppv
0x180129b00  mov     rcx, rbx; pStm
0x180129b03  lea     rdx, IID_IUrlCacheManager; riid
0x180129b0a  call    cs:__imp_CoUnmarshalInterface
0x180129b10  mov     esi, eax
0x180129b12  test    eax, eax
0x180129b14  jns     short loc_180129B22
0x180129b16  mov     [rbp+var_4C], 121h
0x180129b1d  jmp     loc_180129D11
0x180129b22  lea     rsi, [r14+18h]
0x180129b26  mov     rcx, [rsi]; Binding
0x180129b29  call    cs:__imp_RpcBindingUnbind
0x180129b2f  mov     rcx, rsi; Binding
0x180129b32  call    cs:__imp_RpcBindingFree
0x180129b38  mov     [rsi], r13
0x180129b3b  mov     rcx, [rbp+var_10]
0x180129b3f  lea     r9, [rbp+var_20]
0x180129b43  mov     rdx, [rbp+var_18]
0x180129b47  lea     r8, IID_IUrlCacheManager
0x180129b4e  mov     rax, [rcx]
0x180129b51  mov     rax, [rax+18h]
0x180129b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129b5a  mov     esi, eax
0x180129b5c  test    eax, eax
0x180129b5e  jns     loc_180129C1E
0x180129b64  mov     [rbp+var_4C], 15Ch
0x180129b6b  jmp     loc_180129D11
0x180129b70  call    IsProcessLessThanMediumIL
0x180129b75  test    eax, eax
0x180129b77  jnz     short loc_180129BD6
0x180129b79  cmp     cs:GlobalKirAppBrokerForMediumILUWPApps, r13d
0x180129b80  jz      short loc_180129B8B
0x180129b82  call    IsPackagedProcess
0x180129b87  test    eax, eax
0x180129b89  jnz     short loc_180129BD6
0x180129b8b  cmp     cs:GlobalIsWow64, r13d
0x180129b92  lea     r9, IID_IUrlCacheManager; riid
0x180129b99  mov     eax, 90004h
0x180129b9e  lea     rcx, CLSID_UrlCacheManager; rclsid
0x180129ba5  mov     r8d, 10004h
0x180129bab  cmovnz  r8d, eax; dwClsContext
0x180129baf  lea     rax, [rbp+var_18]
0x180129bb3  xor     edx, edx; pUnkOuter
0x180129bb5  mov     [rsp+80h+ppv], rax; ppv
0x180129bba  call    cs:__imp_CoCreateInstance
0x180129bc0  mov     esi, eax
0x180129bc2  test    eax, eax
0x180129bc4  jns     loc_180129B3B
0x180129bca  mov     [rbp+var_4C], 146h
0x180129bd1  jmp     loc_180129D11
0x180129bd6  lea     rdx, [rbp+var_38]
0x180129bda  call    GetIWininetBrokerEx
0x180129bdf  mov     rdi, [rbp+var_38]
0x180129be3  mov     esi, eax
0x180129be5  test    eax, eax
0x180129be7  jns     short loc_180129BF5
0x180129be9  mov     [rbp+var_4C], 136h
0x180129bf0  jmp     loc_180129D11
0x180129bf5  mov     rax, [rdi]
0x180129bf8  lea     rdx, [rbp+var_18]
0x180129bfc  mov     rcx, rdi
0x180129bff  mov     rax, [rax+18h]
0x180129c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129c08  mov     esi, eax
0x180129c0a  test    eax, eax
0x180129c0c  jns     loc_180129B3B
0x180129c12  mov     [rbp+var_4C], 138h
0x180129c19  jmp     loc_180129D11
0x180129c1e  mov     rcx, [rbp+var_18]
0x180129c22  lea     rdx, [rbp+pv]
0x180129c26  mov     rax, [rcx]
0x180129c29  mov     rax, [rax+18h]
0x180129c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129c32  mov     esi, eax
0x180129c34  test    eax, eax
0x180129c36  jns     short loc_180129C44
0x180129c38  mov     [rbp+var_4C], 161h
0x180129c3f  jmp     loc_180129D11
0x180129c44  mov     rcx, [rbp+pv]; unsigned __int16 *
0x180129c48  lea     rdx, [rbp+hBinding]; void **
0x180129c4c  call    ?WxRpcBindingCreate@@YAJPEBGPEAPEAX@Z; WxRpcBindingCreate(ushort const *,void * *)
0x180129c51  mov     esi, eax
0x180129c53  test    eax, eax
0x180129c55  jns     short loc_180129C63
0x180129c57  mov     [rbp+var_4C], 167h
0x180129c5e  jmp     loc_180129D11
0x180129c63  mov     rcx, [rbp+hBinding]; hBinding
0x180129c67  mov     edx, 9; option
0x180129c6c  lea     r8d, [rdx-8]; optionValue
0x180129c70  call    cs:__imp_RpcBindingSetOption
0x180129c76  mov     esi, eax
0x180129c78  mov     r15d, 80070000h
0x180129c7e  test    eax, eax
0x180129c80  jle     short loc_180129C88
0x180129c82  movzx   esi, ax
0x180129c85  or      esi, r15d
0x180129c88  test    esi, esi
0x180129c8a  jns     short loc_180129C95
0x180129c8c  mov     [rbp+var_4C], 16Dh
0x180129c93  jmp     short loc_180129D11
0x180129c95  mov     rdx, [rbp+hBinding]; Binding
0x180129c99  lea     r8, qword_1801EF030; IfSpec
0x180129ca0  xor     ecx, ecx; pAsync
0x180129ca2  call    cs:__imp_RpcBindingBind
0x180129ca8  mov     esi, eax
0x180129caa  test    eax, eax
0x180129cac  jle     short loc_180129CB4
0x180129cae  movzx   esi, ax
0x180129cb1  or      esi, r15d
0x180129cb4  test    esi, esi
0x180129cb6  jns     short loc_180129CC1
0x180129cb8  mov     [rbp+var_4C], 16Fh
0x180129cbf  jmp     short loc_180129D11
0x180129cc1  mov     rcx, r14; this
0x180129cc4  mov     r12d, 1
0x180129cca  call    ?StartMTAThread@CCacheServerConnection@@AEAAJXZ; CCacheServerConnection::StartMTAThread(void)
0x180129ccf  mov     esi, eax
0x180129cd1  test    eax, eax
0x180129cd3  jns     short loc_180129CDE
0x180129cd5  mov     [rbp+var_4C], 179h
0x180129cdc  jmp     short loc_180129D11
0x180129cde  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180129ce2  lea     rcx, [r14+8]; this
0x180129ce6  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x180129ceb  mov     esi, eax
0x180129ced  test    eax, eax
0x180129cef  jns     short loc_180129CFA
0x180129cf1  mov     [rbp+var_4C], 17Bh
0x180129cf8  jmp     short loc_180129D11
0x180129cfa  mov     rax, [rbp+hBinding]
0x180129cfe  mov     [r14+18h], rax
0x180129d02  mov     eax, [rbp+var_20]
0x180129d05  mov     [r14+4], eax
0x180129d09  mov     [rbp+var_20], r13d
0x180129d0d  mov     [rbp+hBinding], r13
0x180129d11  mov     rcx, [rbp+pv]; pv
0x180129d15  test    rcx, rcx
0x180129d18  jz      short loc_180129D24
0x180129d1a  call    cs:__imp_CoTaskMemFree
0x180129d20  mov     [rbp+pv], r13
0x180129d24  cmp     [rbp+var_40], r13
0x180129d28  jz      short loc_180129D33
0x180129d2a  lea     rcx, [rbp+var_40]
0x180129d2e  call    WxFreeHeapEx
0x180129d33  test    r12d, r12d
0x180129d36  jz      short loc_180129D47
0x180129d38  mov     rcx, [rbp+hBinding]; Binding
0x180129d3c  test    rcx, rcx
0x180129d3f  jz      short loc_180129D64
0x180129d41  call    cs:__imp_RpcBindingUnbind
0x180129d47  cmp     [rbp+hBinding], r13
0x180129d4b  jz      short loc_180129D64
0x180129d4d  lea     rcx, [rbp+hBinding]; Binding
0x180129d51  call    cs:__imp_RpcBindingFree
0x180129d57  lea     rcx, [r14+8]; this
0x180129d5b  mov     [rbp+hBinding], r13
0x180129d5f  call    ?Empty@CWxString@@QEAAXXZ; CWxString::Empty(void)
0x180129d64  mov     edx, [rbp+var_20]
0x180129d67  test    edx, edx
0x180129d69  jz      short loc_180129D84
0x180129d6b  mov     rcx, [rbp+var_10]
0x180129d6f  test    rcx, rcx
0x180129d72  jz      short loc_180129D84
0x180129d74  mov     rax, [rcx]
0x180129d77  mov     rax, [rax+20h]
0x180129d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129d80  mov     [rbp+var_20], r13d
0x180129d84  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180129d8b  jz      short loc_180129DA6
0x180129d8d  mov     edx, 0Bh
0x180129d92  lea     r8, WPP_9c4c3569cf513e10024214760e760dc6_Traceguids
0x180129d99  mov     ecx, 40Ch
0x180129d9e  mov     r9d, esi
0x180129da1  call    WPP_SF_d
0x180129da6  test    rbx, rbx
0x180129da9  jz      short loc_180129DBA
0x180129dab  mov     rax, [rbx]
0x180129dae  mov     rcx, rbx
0x180129db1  mov     rax, [rax+10h]
0x180129db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129dba  test    rdi, rdi
0x180129dbd  jz      short loc_180129DCE
0x180129dbf  mov     rax, [rdi]
0x180129dc2  mov     rcx, rdi
0x180129dc5  mov     rax, [rax+10h]
0x180129dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129dce  mov     rcx, [rbp+var_18]
0x180129dd2  test    rcx, rcx
0x180129dd5  jz      short loc_180129DE3
0x180129dd7  mov     rax, [rcx]
0x180129dda  mov     rax, [rax+10h]
0x180129dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129de3  mov     rcx, [rbp+var_10]
0x180129de7  test    rcx, rcx
0x180129dea  jz      short loc_180129DF8
0x180129dec  mov     rdx, [rcx]
0x180129def  mov     rax, [rdx+10h]
0x180129df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129df8  mov     eax, esi
0x180129dfa  mov     rcx, [rbp+var_8]
0x180129dfe  xor     rcx, rsp; StackCookie
0x180129e01  call    __security_check_cookie
0x180129e06  mov     rbx, [rsp+80h+arg_10]
0x180129e0e  add     rsp, 80h
0x180129e15  pop     r15
0x180129e17  pop     r14
0x180129e19  pop     r13
0x180129e1b  pop     r12
0x180129e1d  pop     rdi
0x180129e1e  pop     rsi
0x180129e1f  pop     rbp
0x180129e20  retn
```
