# VmmsFailoverReplicationBrokerManager::GetBrokerNameToken(Vml::VmAccessToken &)

- ea: `0x140502cf0`
- end: `0x140503273`
- name: `?GetBrokerNameToken@VmmsFailoverReplicationBrokerManager@@UEAAJAEAVVmAccessToken@Vml@@@Z`
- size: `1411`
- prototype: `int(VmmsFailoverReplicationBrokerManager *__hidden this, struct Vml::VmAccessToken *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x14001d048`
- `0x140022640`
- `0x14004aeac`
- `0x14004f3c4`
- `0x14005c630`
- `0x14006d65c`
- `0x140088ec0`
- `0x14008901c`
- `0x1400e01dc`
- `0x1400e7220`
- `0x140118430`
- `0x1401879a4`
- `0x140188e18`
- `0x140447e38`
- `0x1404828e0`
- `0x140502cd0`
- `0x140502cf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140502e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140502eff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140502fb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405030cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140502e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140502eff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140502fb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405030cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140502f68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140502f68`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1405030bf`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1405030bf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140503146`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1405031a1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140503146`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1405031a1`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x140502f97`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x140502f97`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x140502e58`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x140502e58`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseCluster` at `0x140503210`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseCluster` at `0x140503210`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x14050305d`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x14050305d`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x1405031fc`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x1405031fc`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x1405031e8`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x1405031e8`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterResource` at `0x140502ee6`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterResource` at `0x140502ee6`

## string_xrefs

- `0x140502dbe`: `onecore\vm\vmms\fr\lib\failoverreplicationbrokermanager.cpp`
- `0x140502eb8`: `onecore\vm\vmms\fr\lib\failoverreplicationbrokermanager.cpp`
- `0x140502f46`: `onecore\vm\vmms\fr\lib\failoverreplicationbrokermanager.cpp`
- `0x140502ff7`: `onecore\vm\vmms\fr\lib\failoverreplicationbrokermanager.cpp`
- `0x1405030a6`: `onecore\vm\vmms\fr\lib\failoverreplicationbrokermanager.cpp`
- `0x140503116`: `onecore\vm\vmms\fr\lib\failoverreplicationbrokermanager.cpp`
- `0x14050317e`: `onecore\vm\vmms\fr\lib\failoverreplicationbrokermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall VmmsFailoverReplicationBrokerManager::GetBrokerNameToken(
        VmmsFailoverReplicationBrokerManager *this,
        struct Vml::VmAccessToken *a2)
{
  int v4; // r15d
  int BrokerCapName; // esi
  __int64 v6; // rax
  __int64 v7; // rax
  struct _HCLUSTER *v8; // rax
  struct _HCLUSTER *v9; // rdi
  signed int LastError; // eax
  unsigned int v11; // esi
  const WCHAR *v12; // rdx
  struct _HRESOURCE *v13; // r14
  signed int v14; // eax
  unsigned int v15; // esi
  Vml *v16; // rcx
  const WCHAR *ComputerNameW; // rax
  struct _HNODE *v18; // r12
  signed int v19; // eax
  unsigned int v20; // esi
  signed int v21; // eax
  unsigned int v22; // esi
  int v23; // r9d
  signed int v24; // eax
  unsigned int v25; // esi
  const struct Vml::ExceptionTraceParameters *v26; // r8
  const struct Vml::ExceptionTraceParameters *v27; // r8
  __int64 result; // rax
  DWORD cbInBufferSize; // [rsp+20h] [rbp-D8h]
  DWORD cbInBufferSizea; // [rsp+20h] [rbp-D8h]
  int v31; // [rsp+40h] [rbp-B8h]
  HCLUSTER hCluster; // [rsp+48h] [rbp-B0h]
  HRESOURCE hResource; // [rsp+50h] [rbp-A8h]
  int HResultFromThrownExceptionAndTrace; // [rsp+58h] [rbp-A0h]
  struct _HNODE *v35; // [rsp+60h] [rbp-98h]
  _BYTE v36[32]; // [rsp+68h] [rbp-90h] BYREF
  _QWORD InBuffer[2]; // [rsp+88h] [rbp-70h] BYREF
  HANDLE OutBuffer; // [rsp+98h] [rbp-60h] BYREF
  DWORD BytesReturned; // [rsp+A0h] [rbp-58h] BYREF
  LPCWSTR lpszResourceName[2]; // [rsp+A8h] [rbp-50h] BYREF
  __m128i si128; // [rsp+B8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  Vml::VmAccessToken::Reset(a2, 0);
  try
  {
    v4 = 0;
    memset(InBuffer, 0, 12);
    BytesReturned = 0;
    *(_OWORD *)lpszResourceName = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpszResourceName[0]) = 0;
    BrokerCapName = VmmsFailoverReplicationBrokerManager::GetBrokerCapName(this, lpszResourceName);
    if ( BrokerCapName < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16804) )
        VmlDebugTraceWithError(16804, &off_140906510, (unsigned int)BrokerCapName);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8EA,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationbrokermanager.cpp",
        (const char *)(unsigned int)BrokerCapName,
        cbInBufferSize);
    }
    if ( (unsigned int)VmlIsDebugTraceEnabled(49572) )
      VmlDebugTraceEx(49572, &off_1409064F8);
    v6 = std::wstring::find(lpszResourceName, L".", 0);
    if ( v6 != -1 )
    {
      v7 = std::wstring::substr(lpszResourceName, v36, 0, v6);
      std::wstring::operator=(lpszResourceName, v7);
      std::wstring::_Tidy_deallocate(v36);
    }
    v8 = OpenCluster(0);
    v9 = v8;
    hCluster = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16804) )
        VmlDebugTraceWithError(16804, &off_140906610, v11);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8FC,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationbrokermanager.cpp",
        (const char *)v11,
        cbInBufferSize);
    }
    v12 = (const WCHAR *)lpszResourceName;
    if ( si128.m128i_i64[1] > 7uLL )
      v12 = lpszResourceName[0];
    v13 = OpenClusterResource(v8, v12);
    hResource = v13;
    if ( !v13 )
    {
      v14 = GetLastError();
      v15 = v14;
      if ( v14 > 0 )
        v15 = (unsigned __int16)v14 | 0x80070000;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16804) )
        VmlDebugTraceWithError(16804, &off_1409065F8, v15);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x905,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationbrokermanager.cpp",
        (const char *)v15,
        cbInBufferSize);
    }
    memset(InBuffer, 0, 12);
    LODWORD(InBuffer[0]) = GetCurrentProcessId();
    *(_QWORD *)((char *)InBuffer + 4) = 14;
    Vml::VmModuleBase::GetModuleBase();
    ComputerNameW = Vml::GetComputerNameW(v16);
    v18 = OpenClusterNode(v9, ComputerNameW);
    v35 = v18;
    if ( !v18 )
    {
      v19 = GetLastError();
      v20 = v19;
      if ( v19 > 0 )
        v20 = (unsigned __int16)v19 | 0x80070000;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16804) )
        VmlDebugTraceWithError(16804, &off_1409065E0, v20);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x914,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationbrokermanager.cpp",
        (const char *)v20,
        cbInBufferSize);
    }
    OutBuffer = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &OutBuffer,
      0);
    v21 = ClusterResourceControl(v13, v18, 0x100016Du, InBuffer, 0xCu, &OutBuffer, 8u, &BytesReturned);
    v22 = v21;
    if ( v21 )
    {
      if ( v21 > 0 )
        v22 = (unsigned __int16)v21 | 0x80070000;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16804) )
        VmlDebugTraceWithError(16804, &off_1409065C8, v22);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x927,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationbrokermanager.cpp",
        (const char *)v22,
        cbInBufferSizea);
    }
    if ( !ImpersonateLoggedOnUser(OutBuffer) )
    {
      v24 = GetLastError();
      v25 = v24;
      if ( v24 > 0 )
        v25 = (unsigned __int16)v24 | 0x80070000;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16804) )
        VmlDebugTraceWithError(16804, &off_1409065B0, v25);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x92F,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationbrokermanager.cpp",
        (const char *)v25,
        cbInBufferSizea);
    }
    try
    {
      Vml::VmlGetEffectiveAccessToken((PHANDLE)a2, 0xEu, 1, v23);
    }
    catch ( ... )
    {
      HResultFromThrownExceptionAndTrace = Vml::GetHResultFromThrownExceptionAndTrace(
                                             (Vml *)0x41A4,
                                             (unsigned __int16)&off_1409065A0,
                                             v26);
      if ( HResultFromThrownExceptionAndTrace < 0 )
      {
        RevertToSelf();
        if ( (unsigned int)VmlIsDebugTraceEnabled(16804) )
          VmlDebugTraceWithError(16804, &off_140906588, (unsigned int)HResultFromThrownExceptionAndTrace);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x93F,
          (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationbrokermanager.cpp",
          (const char *)(unsigned int)HResultFromThrownExceptionAndTrace,
          cbInBufferSizea);
      }
      v9 = hCluster;
      v4 = 0;
    }
    RevertToSelf();
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&OutBuffer);
    std::wstring::_Tidy_deallocate(lpszResourceName);
  }
  catch ( ... )
  {
    v31 = Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x41A4, (unsigned __int16)&off_140906578, v27);
    v18 = v35;
    v9 = hCluster;
    v13 = hResource;
    v4 = v31;
    if ( v35 )
      goto LABEL_49;
LABEL_50:
    if ( v13 )
      CloseClusterResource(v13);
    if ( v9 )
      CloseCluster(v9);
    if ( v4 < 0 && (unsigned int)VmlIsDebugTraceEnabled(16804) )
      VmlDebugTraceWithError(16804, &off_1409064E0, (unsigned int)v4);
    result = (unsigned int)v4;
  }
LABEL_49:
  CloseClusterNode(v18);
  goto LABEL_50;
}

```

## disassembly

```asm
0x140502cf0  mov     [rsp+arg_10], rbx
0x140502cf5  mov     [rsp+arg_18], rsi
0x140502cfa  push    rdi
0x140502cfb  push    r12
0x140502cfd  push    r13
0x140502cff  push    r14
0x140502d01  push    r15
0x140502d03  sub     rsp, 0D0h
0x140502d0a  mov     rax, cs:__security_cookie
0x140502d11  xor     rax, rsp
0x140502d14  mov     [rsp+0F8h+var_30], rax
0x140502d1c  mov     r13, rdx
0x140502d1f  mov     rdi, rcx
0x140502d22  xor     ebx, ebx
0x140502d24  mov     [rsp+0F8h+hCluster], rbx
0x140502d29  mov     [rsp+0F8h+hResource], rbx
0x140502d2e  mov     [rsp+0F8h+var_98], rbx
0x140502d33  xor     edx, edx; void *
0x140502d35  mov     rcx, r13; this
0x140502d38  call    ?Reset@VmAccessToken@Vml@@QEAAXPEAX@Z; Vml::VmAccessToken::Reset(void *)
0x140502d3d  mov     r15d, ebx
0x140502d40  xor     eax, eax
0x140502d42  mov     [rsp+0F8h+InBuffer], rax
0x140502d4a  mov     [rsp+0F8h+var_68], eax
0x140502d51  mov     [rsp+0F8h+BytesReturned], ebx
0x140502d58  xorps   xmm0, xmm0
0x140502d5b  movups  xmmword ptr [rsp+0F8h+lpszResourceName], xmm0
0x140502d63  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140502d6b  movdqu  [rsp+0F8h+var_40], xmm1
0x140502d74  mov     word ptr [rsp+0F8h+lpszResourceName], bx
0x140502d7c  lea     rdx, [rsp+0F8h+lpszResourceName]
0x140502d84  mov     rcx, rdi
0x140502d87  call    ?GetBrokerCapName@VmmsFailoverReplicationBrokerManager@@UEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; VmmsFailoverReplicationBrokerManager::GetBrokerCapName(std::wstring &)
0x140502d8c  mov     esi, eax
0x140502d8e  test    eax, eax
0x140502d90  jns     short loc_140502DCF
0x140502d92  mov     edi, 41A4h
0x140502d97  mov     ecx, edi
0x140502d99  call    VmlIsDebugTraceEnabled
0x140502d9e  test    eax, eax
0x140502da0  jz      short loc_140502DB3
0x140502da2  mov     r8d, esi
0x140502da5  lea     rdx, off_140906510; "Failed to get broker CAP name."
0x140502dac  mov     ecx, edi
0x140502dae  call    VmlDebugTraceWithError
0x140502db3  mov     rcx, [rsp+0F8h]; this
0x140502dbb  mov     r9d, esi; char *
0x140502dbe  lea     r8, aOnecoreVmVmmsF_20; "onecore\\vm\\vmms\\fr\\lib\\failoverrep"...
0x140502dc5  mov     edx, 8EAh; void *
0x140502dca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140502dcf  mov     edi, 0C1A4h
0x140502dd4  mov     ecx, edi
0x140502dd6  call    VmlIsDebugTraceEnabled
0x140502ddb  test    eax, eax
0x140502ddd  jz      short loc_140502E07
0x140502ddf  lea     r8, [rsp+0F8h+lpszResourceName]
0x140502de7  cmp     qword ptr [rsp+0F8h+var_40+8], 7
0x140502df0  cmova   r8, [rsp+0F8h+lpszResourceName]
0x140502df9  lea     rdx, off_1409064F8; "Broker CAP name - %ws"
0x140502e00  mov     ecx, edi
0x140502e02  call    VmlDebugTraceEx
0x140502e07  xor     r8d, r8d
0x140502e0a  lea     rdx, asc_1409EB35C; "."
0x140502e11  lea     rcx, [rsp+0F8h+lpszResourceName]
0x140502e19  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x140502e1e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140502e22  jz      short loc_140502E56
0x140502e24  mov     r9, rax
0x140502e27  xor     r8d, r8d
0x140502e2a  lea     rdx, [rsp+0F8h+var_90]
0x140502e2f  lea     rcx, [rsp+0F8h+lpszResourceName]
0x140502e37  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x140502e3c  mov     rdx, rax
0x140502e3f  lea     rcx, [rsp+0F8h+lpszResourceName]
0x140502e47  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140502e4c  lea     rcx, [rsp+0F8h+var_90]
0x140502e51  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140502e56  xor     ecx, ecx; lpszClusterName
0x140502e58  call    cs:__imp_OpenCluster
0x140502e5f  nop     dword ptr [rax+rax+00h]
0x140502e64  mov     rdi, rax
0x140502e67  mov     [rsp+0F8h+hCluster], rax
0x140502e6c  test    rax, rax
0x140502e6f  jnz     short loc_140502EC9
0x140502e71  call    cs:__imp_GetLastError
0x140502e78  nop     dword ptr [rax+rax+00h]
0x140502e7d  mov     esi, eax
0x140502e7f  test    eax, eax
0x140502e81  jle     short loc_140502E8C
0x140502e83  movzx   esi, ax
0x140502e86  or      esi, 80070000h
0x140502e8c  mov     edi, 41A4h
0x140502e91  mov     ecx, edi
0x140502e93  call    VmlIsDebugTraceEnabled
0x140502e98  test    eax, eax
0x140502e9a  jz      short loc_140502EAD
0x140502e9c  mov     r8d, esi
0x140502e9f  lea     rdx, off_140906610; "Failed to get cluster handle."
0x140502ea6  mov     ecx, edi
0x140502ea8  call    VmlDebugTraceWithError
0x140502ead  mov     rcx, [rsp+0F8h]; this
0x140502eb5  mov     r9d, esi; char *
0x140502eb8  lea     r8, aOnecoreVmVmmsF_20; "onecore\\vm\\vmms\\fr\\lib\\failoverrep"...
0x140502ebf  mov     edx, 8FCh; void *
0x140502ec4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140502ec9  lea     rdx, [rsp+0F8h+lpszResourceName]
0x140502ed1  cmp     qword ptr [rsp+0F8h+var_40+8], 7
0x140502eda  cmova   rdx, [rsp+0F8h+lpszResourceName]; lpszResourceName
0x140502ee3  mov     rcx, rdi; hCluster
0x140502ee6  call    cs:__imp_OpenClusterResource
0x140502eed  nop     dword ptr [rax+rax+00h]
0x140502ef2  mov     r14, rax
0x140502ef5  mov     [rsp+0F8h+hResource], rax
0x140502efa  test    rax, rax
0x140502efd  jnz     short loc_140502F57
0x140502eff  call    cs:__imp_GetLastError
0x140502f06  nop     dword ptr [rax+rax+00h]
0x140502f0b  mov     esi, eax
0x140502f0d  test    eax, eax
0x140502f0f  jle     short loc_140502F1A
0x140502f11  movzx   esi, ax
0x140502f14  or      esi, 80070000h
0x140502f1a  mov     edi, 41A4h
0x140502f1f  mov     ecx, edi
0x140502f21  call    VmlIsDebugTraceEnabled
0x140502f26  test    eax, eax
0x140502f28  jz      short loc_140502F3B
0x140502f2a  mov     r8d, esi
0x140502f2d  lea     rdx, off_1409065F8; "Failed to get broker CAP resource handl"...
0x140502f34  mov     ecx, edi
0x140502f36  call    VmlDebugTraceWithError
0x140502f3b  mov     rcx, [rsp+0F8h]; this
0x140502f43  mov     r9d, esi; char *
0x140502f46  lea     r8, aOnecoreVmVmmsF_20; "onecore\\vm\\vmms\\fr\\lib\\failoverrep"...
0x140502f4d  mov     edx, 905h; void *
0x140502f52  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140502f57  xor     eax, eax
0x140502f59  mov     [rsp+0F8h+InBuffer], rax
0x140502f61  mov     [rsp+0F8h+var_68], eax
0x140502f68  call    cs:__imp_GetCurrentProcessId
0x140502f6f  nop     dword ptr [rax+rax+00h]
0x140502f74  mov     dword ptr [rsp+0F8h+InBuffer], eax
0x140502f7b  mov     [rsp+0F8h+InBuffer+4], 0Eh
0x140502f87  call    ?GetModuleBase@VmModuleBase@Vml@@SAAEAV12@XZ; Vml::VmModuleBase::GetModuleBase(void)
0x140502f8c  call    ?GetComputerNameW@Vml@@YAPEBGXZ; Vml::GetComputerNameW(void)
0x140502f91  mov     rdx, rax; lpszNodeName
0x140502f94  mov     rcx, rdi; hCluster
0x140502f97  call    cs:__imp_OpenClusterNode
0x140502f9e  nop     dword ptr [rax+rax+00h]
0x140502fa3  mov     r12, rax
0x140502fa6  mov     [rsp+0F8h+var_98], rax
0x140502fab  test    rax, rax
0x140502fae  jnz     short loc_140503008
0x140502fb0  call    cs:__imp_GetLastError
0x140502fb7  nop     dword ptr [rax+rax+00h]
0x140502fbc  mov     esi, eax
0x140502fbe  test    eax, eax
0x140502fc0  jle     short loc_140502FCB
0x140502fc2  movzx   esi, ax
0x140502fc5  or      esi, 80070000h
0x140502fcb  mov     edi, 41A4h
0x140502fd0  mov     ecx, edi
0x140502fd2  call    VmlIsDebugTraceEnabled
0x140502fd7  test    eax, eax
0x140502fd9  jz      short loc_140502FEC
0x140502fdb  mov     r8d, esi
0x140502fde  lea     rdx, off_1409065E0; "Failed to get local node handle in clus"...
0x140502fe5  mov     ecx, edi
0x140502fe7  call    VmlDebugTraceWithError
0x140502fec  mov     rcx, [rsp+0F8h]; this
0x140502ff4  mov     r9d, esi; char *
0x140502ff7  lea     r8, aOnecoreVmVmmsF_20; "onecore\\vm\\vmms\\fr\\lib\\failoverrep"...
0x140502ffe  mov     edx, 914h; void *
0x140503003  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140503008  mov     [rsp+0F8h+OutBuffer], rbx
0x140503010  xor     edx, edx
0x140503012  lea     rcx, [rsp+0F8h+OutBuffer]
0x14050301a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14050301f  lea     rax, [rsp+0F8h+BytesReturned]
0x140503027  mov     [rsp+0F8h+lpBytesReturned], rax; lpBytesReturned
0x14050302c  mov     [rsp+0F8h+cbOutBufferSize], 8; cbOutBufferSize
0x140503034  lea     rax, [rsp+0F8h+OutBuffer]
0x14050303c  mov     [rsp+0F8h+lpOutBuffer], rax; lpOutBuffer
0x140503041  mov     [rsp+0F8h+cbInBufferSize], 0Ch; int
0x140503049  lea     r9, [rsp+0F8h+InBuffer]; lpInBuffer
0x140503051  mov     r8d, 100016Dh; dwControlCode
0x140503057  mov     rdx, r12; hHostNode
0x14050305a  mov     rcx, r14; hResource
0x14050305d  call    cs:__imp_ClusterResourceControl
0x140503064  nop     dword ptr [rax+rax+00h]
0x140503069  mov     esi, eax
0x14050306b  test    eax, eax
0x14050306d  jz      short loc_1405030B7
0x14050306f  jle     short loc_14050307A
0x140503071  movzx   esi, ax
0x140503074  or      esi, 80070000h
0x14050307a  mov     edi, 41A4h
0x14050307f  mov     ecx, edi
0x140503081  call    VmlIsDebugTraceEnabled
0x140503086  test    eax, eax
0x140503088  jz      short loc_14050309B
0x14050308a  mov     r8d, esi
0x14050308d  lea     rdx, off_1409065C8; "Failed to get cluster virtual server to"...
0x140503094  mov     ecx, edi
0x140503096  call    VmlDebugTraceWithError
0x14050309b  mov     rcx, [rsp+0F8h]; this
0x1405030a3  mov     r9d, esi; char *
0x1405030a6  lea     r8, aOnecoreVmVmmsF_20; "onecore\\vm\\vmms\\fr\\lib\\failoverrep"...
0x1405030ad  mov     edx, 927h; void *
0x1405030b2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1405030b7  mov     rcx, [rsp+0F8h+OutBuffer]; hToken
0x1405030bf  call    cs:__imp_ImpersonateLoggedOnUser
0x1405030c6  nop     dword ptr [rax+rax+00h]
0x1405030cb  test    eax, eax
0x1405030cd  jnz     short loc_140503128
0x1405030cf  call    cs:__imp_GetLastError
0x1405030d6  nop     dword ptr [rax+rax+00h]
0x1405030db  mov     esi, eax
0x1405030dd  test    eax, eax
0x1405030df  jle     short loc_1405030EA
0x1405030e1  movzx   esi, ax
0x1405030e4  or      esi, 80070000h
0x1405030ea  mov     edi, 41A4h
0x1405030ef  mov     ecx, edi
0x1405030f1  call    VmlIsDebugTraceEnabled
0x1405030f6  test    eax, eax
0x1405030f8  jz      short loc_14050310B
0x1405030fa  mov     r8d, esi
0x1405030fd  lea     rdx, off_1409065B0; "Failed to impersonate logged on user."
0x140503104  mov     ecx, edi
0x140503106  call    VmlDebugTraceWithError
0x14050310b  mov     rcx, [rsp+0F8h]; this
0x140503113  mov     r9d, esi; char *
0x140503116  lea     r8, aOnecoreVmVmmsF_20; "onecore\\vm\\vmms\\fr\\lib\\failoverrep"...
0x14050311d  mov     edx, 92Fh; void *
0x140503122  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140503128  mov     edx, 0Eh; DesiredAccess
0x14050312d  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x140503131  mov     rcx, r13; TokenHandle
0x140503134  call    ?VmlGetEffectiveAccessToken@Vml@@YAXAEAVVmAccessToken@1@KH@Z; Vml::VmlGetEffectiveAccessToken(Vml::VmAccessToken &,ulong,int)
0x140503139  nop
0x14050313a  jmp     short loc_1405031A1
0x14050313c  mov     esi, dword ptr [rsp+0F8h+var_A0]
0x140503140  xor     ebx, ebx
0x140503142  test    esi, esi
0x140503144  jns     short loc_14050318F
0x140503146  call    cs:__imp_RevertToSelf
0x14050314d  nop     dword ptr [rax+rax+00h]
0x140503152  mov     edi, 41A4h
0x140503157  mov     ecx, edi
0x140503159  call    VmlIsDebugTraceEnabled
0x14050315e  test    eax, eax
0x140503160  jz      short loc_140503173
0x140503162  mov     r8d, esi
0x140503165  lea     rdx, off_140906588; "Failed to get broker token."
0x14050316c  mov     ecx, edi
0x14050316e  call    VmlDebugTraceWithError
0x140503173  mov     rcx, [rsp+0F8h]; this
0x14050317b  mov     r9d, esi; char *
0x14050317e  lea     r8, aOnecoreVmVmmsF_20; "onecore\\vm\\vmms\\fr\\lib\\failoverrep"...
0x140503185  mov     edx, 93Fh; void *
0x14050318a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14050318f  mov     rdi, [rsp+0F8h+hCluster]
0x140503194  mov     r14, [rsp+0F8h+hResource]
0x140503199  mov     r12, [rsp+0F8h+var_98]
0x14050319e  mov     r15d, ebx
0x1405031a1  call    cs:__imp_RevertToSelf
0x1405031a8  nop     dword ptr [rax+rax+00h]
0x1405031ad  nop
0x1405031ae  lea     rcx, [rsp+0F8h+OutBuffer]
0x1405031b6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1405031bb  nop
0x1405031bc  lea     rcx, [rsp+0F8h+lpszResourceName]
0x1405031c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1405031c9  nop
0x1405031ca  jmp     short loc_1405031E5
0x1405031cc  mov     r12, [rsp+0F8h+var_98]
0x1405031d1  mov     rdi, [rsp+0F8h+hCluster]
0x1405031d6  mov     r14, [rsp+0F8h+hResource]
0x1405031db  mov     r15d, [rsp+0F8h+var_B8]
0x1405031e0  test    r12, r12
0x1405031e3  jz      short loc_1405031F4
0x1405031e5  mov     rcx, r12; hNode
0x1405031e8  call    cs:__imp_CloseClusterNode
0x1405031ef  nop     dword ptr [rax+rax+00h]
0x1405031f4  test    r14, r14
0x1405031f7  jz      short loc_140503208
0x1405031f9  mov     rcx, r14; hResource
0x1405031fc  call    cs:__imp_CloseClusterResource
0x140503203  nop     dword ptr [rax+rax+00h]
0x140503208  test    rdi, rdi
0x14050320b  jz      short loc_14050321C
0x14050320d  mov     rcx, rdi; hCluster
0x140503210  call    cs:__imp_CloseCluster
0x140503217  nop     dword ptr [rax+rax+00h]
0x14050321c  test    r15d, r15d
0x14050321f  jns     short loc_140503242
0x140503221  mov     edi, 41A4h
0x140503226  mov     ecx, edi
0x140503228  call    VmlIsDebugTraceEnabled
  ... truncated ...
```
