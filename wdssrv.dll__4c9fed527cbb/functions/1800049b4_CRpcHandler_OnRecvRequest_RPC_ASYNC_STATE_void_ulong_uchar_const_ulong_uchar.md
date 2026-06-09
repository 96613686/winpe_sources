# CRpcHandler::OnRecvRequest(_RPC_ASYNC_STATE *,void *,ulong,uchar * const,ulong *,uchar * *)

- ea: `0x1800049b4`
- end: `0x18000534d`
- name: `?OnRecvRequest@CRpcHandler@@QEAAXPEAU_RPC_ASYNC_STATE@@PEAXKQEAEPEAKPEAPEAE@Z`
- size: `2457`
- prototype: `void __fastcall(CRpcHandler *this, struct _RPC_ASYNC_STATE *, void *, unsigned int, unsigned __int8 *const, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006380`

## callees

- `0x180003944`
- `0x180003bb4`
- `0x180004054`
- `0x1800049b4`
- `0x180005560`
- `0x180011a90`
- `0x1800157c0`
- `0x18001c11e`
- `0x18001c12a`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180004ff4`
- `KERNEL32!LeaveCriticalSection` at `0x1800052de`
- `KERNEL32!LeaveCriticalSection` at `0x180004ff4`
- `KERNEL32!LeaveCriticalSection` at `0x1800052de`
- `KERNEL32!EnterCriticalSection` at `0x180004c37`
- `KERNEL32!EnterCriticalSection` at `0x180004c37`
- `RPCRT4!RpcBindingFree` at `0x180005320`
- `RPCRT4!RpcBindingFree` at `0x180005320`
- `RPCRT4!RpcStringFreeW` at `0x1800052f4`
- `RPCRT4!RpcStringFreeW` at `0x18000530a`
- `RPCRT4!RpcStringFreeW` at `0x1800052f4`
- `RPCRT4!RpcStringFreeW` at `0x18000530a`
- `RPCRT4!RpcAsyncAbortCall` at `0x180005231`
- `RPCRT4!RpcAsyncAbortCall` at `0x180005231`
- `RPCRT4!RpcStringBindingParseW` at `0x180004a88`
- `RPCRT4!RpcStringBindingParseW` at `0x180004a88`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180004a49`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180004a49`
- `RPCRT4!RpcBindingServerFromClient` at `0x180004a14`
- `RPCRT4!RpcBindingServerFromClient` at `0x180004a14`
- `RPCRT4!RpcRevertToSelf` at `0x180004de8`
- `RPCRT4!RpcRevertToSelf` at `0x180004de8`
- `RPCRT4!RpcImpersonateClient` at `0x180004da4`
- `RPCRT4!RpcImpersonateClient` at `0x180004da4`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x180004b65`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x180004b65`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180004c00`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180005129`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180005220`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800052a2`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180004c00`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180005129`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180005220`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800052a2`
- `WdsServerCommonLib!?Batch@CPerfCounters@@QEAAKKZZ` at `0x180005163`
- `WdsServerCommonLib!?Batch@CPerfCounters@@QEAAKKZZ` at `0x180005163`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180004f41`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180004f41`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180004bdd`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180004cd9`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180004d81`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180004e52`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180004bdd`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180004cd9`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180004d81`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180004e52`
- `WdsServerCommonLib!?Allocate@CMemoryBuffer@@SAPEAV1@K@Z` at `0x180004f63`
- `WdsServerCommonLib!?Allocate@CMemoryBuffer@@SAPEAV1@K@Z` at `0x180004f63`

## pseudocode

```c
void __fastcall CRpcHandler::OnRecvRequest(
        CRpcHandler *this,
        struct _RPC_ASYNC_STATE *a2,
        void *a3,
        unsigned int a4,
        unsigned __int8 *const a5,
        unsigned int *a6,
        unsigned __int8 **a7)
{
  struct _RPC_ASYNC_STATE *v7; // r13
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 v10; // r14
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rbx
  unsigned int v15; // eax
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  unsigned __int64 v20; // rax
  __int64 v21; // r13
  __int64 v22; // r9
  __int64 v23; // rcx
  unsigned int v24; // ecx
  unsigned __int8 *v25; // rax
  __m128i v26; // xmm6
  int v27; // r12d
  __int128 v28; // xmm0
  __int64 v29; // rax
  __int64 v30; // rdx
  unsigned int v31; // esi
  __int64 v32; // r9
  int v33; // eax
  int v34; // ecx
  unsigned int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 ObjectW; // rax
  _WORD *v39; // rcx
  RPC_WSTR v40; // rdx
  _WORD *v41; // rax
  unsigned int v42; // eax
  struct CMemoryBuffer *v43; // rax
  __int64 v44; // r13
  unsigned int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rsi
  const wchar_t *v48; // rcx
  __m128i v49; // xmm0
  int v50; // r9d
  int v51; // r10d
  int v52; // r11d
  int v53; // ebx
  int v54; // r14d
  int v55; // r15d
  int v56; // r12d
  const wchar_t *v57; // rsi
  RPC_WSTR v58; // r12
  const wchar_t *v59; // rsi
  const wchar_t *v60; // r15
  RPC_WSTR v61; // rcx
  const wchar_t *v62; // rax
  __int64 v63; // r9
  const wchar_t *v64; // r9
  RPC_STATUS v65; // eax
  int v66; // ebx
  RPC_STATUS v67; // edx
  __int64 v68; // rax
  RPC_WSTR *Endpoint; // [rsp+28h] [rbp-F0h]
  RPC_WSTR *NetworkOptions; // [rsp+30h] [rbp-E8h]
  __int64 v71; // [rsp+38h] [rbp-E0h]
  __int64 v72; // [rsp+38h] [rbp-E0h]
  RPC_WSTR NetworkAddr; // [rsp+98h] [rbp-80h] BYREF
  int v74; // [rsp+A0h] [rbp-78h]
  int v75; // [rsp+A4h] [rbp-74h]
  unsigned int AuthnLevel; // [rsp+A8h] [rbp-70h] BYREF
  RPC_WSTR StringBinding; // [rsp+B0h] [rbp-68h] BYREF
  RPC_BINDING_HANDLE ServerBinding; // [rsp+B8h] [rbp-60h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+C0h] [rbp-58h]
  RPC_AUTHZ_HANDLE Privs; // [rsp+C8h] [rbp-50h] BYREF
  _OWORD v81[3]; // [rsp+D8h] [rbp-40h] BYREF
  _BYTE v82[4]; // [rsp+108h] [rbp-10h] BYREF
  int v83; // [rsp+10Ch] [rbp-Ch]
  __int128 v84; // [rsp+114h] [rbp-4h]

  v7 = a2;
  v8 = a4;
  Privs = 0;
  ServerBinding = 0;
  v9 = 0;
  AuthnLevel = 0;
  StringBinding = 0;
  v10 = 0;
  NetworkAddr = 0;
  v74 = 0;
  v75 = 0;
  v12 = RpcBindingServerFromClient(a3, &ServerBinding);
  LODWORD(v14) = ElValidateWin32(v12, v13, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 800);
  if ( (_DWORD)v14 )
    goto LABEL_60;
  v15 = RpcBindingToStringBindingW(ServerBinding, &StringBinding);
  LODWORD(v14) = ElValidateWin32(v15, v16, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 804);
  if ( (_DWORD)v14 )
    goto LABEL_60;
  v17 = RpcStringBindingParseW(StringBinding, 0, 0, &NetworkAddr, 0, 0);
  LODWORD(v14) = ElValidateWin32(v17, v18, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 813);
  if ( (_DWORD)v14 )
    goto LABEL_60;
  v20 = -1;
  do
    ++v20;
  while ( NetworkAddr[v20] );
  v21 = 512;
  if ( v20 >= 0x200 )
  {
    v22 = 820;
    v23 = 111;
    goto LABEL_57;
  }
  if ( (unsigned int)v8 < 0x28 )
  {
    v22 = 829;
LABEL_56:
    v23 = 13;
LABEL_57:
    v33 = ElValidateWin32(v23, v19, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", v22);
LABEL_58:
    LODWORD(v14) = v33;
    if ( !v33 )
    {
      v66 = v74;
LABEL_83:
      if ( v10 )
        RpcRequest::Release((RpcRequest *)v10);
      if ( v75 )
        _InterlockedDecrement((volatile signed __int32 *)(v9 + 56));
      if ( v66 )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
      goto LABEL_89;
    }
LABEL_59:
    v7 = a2;
LABEL_60:
    v58 = L"(Unknown)";
    v59 = L"<Unknown>";
    v60 = L"Unknown";
    v61 = L"(Unknown)";
    if ( NetworkAddr )
      v61 = NetworkAddr;
    if ( v74 && v9 )
    {
      v62 = (const wchar_t *)(v9 + 1288);
    }
    else
    {
      v62 = L"Unknown";
      if ( !v74 || !v9 )
      {
        v64 = L"Unknown";
        goto LABEL_71;
      }
    }
    v63 = *(_QWORD *)(v9 + 64);
    if ( v63 )
      v64 = *(const wchar_t **)(v63 + 16);
    else
      v64 = L"<Unknown>";
LABEL_71:
    LODWORD(v71) = v14;
    CTrace::Trace(
      (CTrace *)qword_180039310,
      0x80000u,
      L"[%s][RPC][Ep:%s] Error processing request from client %s (rc=%u)",
      v64,
      v62,
      v61,
      v71);
    v65 = RpcAsyncAbortCall(v7, v14);
    v66 = v74;
    v67 = v65;
    if ( v65 )
    {
      if ( NetworkAddr )
        v58 = NetworkAddr;
      if ( v74 && v9 )
      {
        v60 = (const wchar_t *)(v9 + 1288);
        v68 = *(_QWORD *)(v9 + 64);
        if ( v68 )
          v59 = *(const wchar_t **)(v68 + 16);
      }
      else
      {
        v59 = L"Unknown";
      }
      LODWORD(v72) = v67;
      CTrace::Trace(
        (CTrace *)qword_180039310,
        0x80000u,
        L"[%s][RPC][Ep:%s] Failed to abort RPC call when processing request from client %s (abort status=%d)",
        v59,
        v60,
        v58,
        v72);
    }
    goto LABEL_83;
  }
  if ( *(_WORD *)a5 != 40 || *((_WORD *)a5 + 1) != 256 )
  {
    v22 = 841;
    goto LABEL_56;
  }
  v24 = 0;
  v25 = a5 + 24;
  do
  {
    if ( *v25 )
    {
      v22 = 852;
      goto LABEL_56;
    }
    ++v24;
    ++v25;
  }
  while ( v24 < 0x10 );
  if ( (_DWORD)v8 - *(unsigned __int16 *)a5 != *((_DWORD *)a5 + 1) )
  {
    v22 = 862;
    goto LABEL_56;
  }
  v26 = *(__m128i *)(a5 + 8);
  if ( RpcBindingInqAuthClientW(a3, &Privs, 0, &AuthnLevel, 0, 0) )
  {
    v27 = 2;
  }
  else
  {
    if ( AuthnLevel != 6 )
    {
      v81[0] = v26;
      HIDWORD(v71) = HIDWORD(NetworkAddr);
      CEventLog::Log((CEventLog *)qword_180039300, 0xC1010407, 3);
      CTrace::Trace(
        (CTrace *)qword_180039310,
        0x10000u,
        L"[RPC] Request received but auth level (%u) was invalid",
        AuthnLevel);
      v22 = 901;
      goto LABEL_56;
    }
    v27 = 1;
  }
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 112);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v74 = 1;
  memset_0(v82, 0, 0x41Cu);
  v28 = *(_OWORD *)(a5 + 8);
  v83 = 1;
  v84 = v28;
  v29 = CRegEndpoint::Find<CRegRpcEndpoint>((char *)this + 96, v82);
  LODWORD(v14) = 0;
  v9 = v29;
  if ( !v29 )
  {
    v31 = v8 - *(unsigned __int16 *)a5;
    v81[0] = v26;
    if ( v31 > 0x20 )
      v31 = 32;
    LODWORD(NetworkOptions) = 1;
    CEventLog::Log((CEventLog *)qword_180039300, 0xC1010408, 3, 8, v81, NetworkOptions, NetworkAddr, 10, a5 + 40, v31);
    LODWORD(v14) = 2;
    goto LABEL_59;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v29 + 60), 0) )
  {
    v32 = 942;
LABEL_28:
    v33 = ElValidateWin32(2, v30, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", v32);
    v9 = 0;
    goto LABEL_58;
  }
  v34 = *(_DWORD *)(v29 + 80);
  if ( (v27 & v34) != v27 )
  {
    v81[1] = v26;
    HIDWORD(v71) = HIDWORD(NetworkAddr);
    CEventLog::Log((CEventLog *)qword_180039300, (v34 & 1) - 1056898039, 3);
    v32 = 961;
    goto LABEL_28;
  }
  if ( (v34 & 2) == 0 )
  {
    v35 = RpcImpersonateClient(a3);
    LODWORD(v14) = ElValidateWin32(v35, v36, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 727);
    if ( !(_DWORD)v14 )
    {
      v14 = (unsigned int)CRegRpcEndpoint::AccessCheck((CRegRpcEndpoint *)v9);
      ElValidateWin32(v14, v37, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 737);
      RpcRevertToSelf();
    }
  }
  if ( (_DWORD)v14 )
  {
    v81[2] = v26;
    HIDWORD(v71) = HIDWORD(NetworkAddr);
    CEventLog::Log((CEventLog *)qword_180039300, 0xC101040B, 3);
    goto LABEL_59;
  }
  ObjectW = CPool<RpcRequest>::GetObjectW((char *)this + 32);
  v10 = ObjectW;
  if ( !ObjectW )
  {
LABEL_37:
    LODWORD(v14) = 8;
    goto LABEL_59;
  }
  *(_QWORD *)(ObjectW + 56) = a2;
  *(_QWORD *)(ObjectW + 64) = a3;
  *(_QWORD *)(ObjectW + 88) = a6;
  *(_QWORD *)(ObjectW + 96) = a7;
  *(_DWORD *)(ObjectW + 72) = v8;
  *(_QWORD *)(ObjectW + 80) = a5;
  *(_QWORD *)(ObjectW + 2240) = v9;
  memmove_0((void *)(ObjectW + 1156), (const void *)(v9 + 72), 0x41Cu);
  *(_DWORD *)(v10 + 104) = 1052;
  v39 = (_WORD *)(v10 + 132);
  *(_DWORD *)(v10 + 108) = 1;
  *(_DWORD *)(v10 + 112) = v27;
  v40 = NetworkAddr;
  do
  {
    if ( v21 == -2147483134 )
      break;
    if ( !*v40 )
      break;
    *v39++ = *v40++;
    --v21;
  }
  while ( v21 );
  v41 = v39 - 1;
  if ( v21 )
    v41 = v39;
  *v41 = 0;
  if ( !v21 )
  {
    v42 = WIN32_FROM_HRESULT(-2147024774);
    v22 = 1015;
    v23 = v42;
    goto LABEL_57;
  }
  v43 = CMemoryBuffer::Allocate(v8);
  *(_QWORD *)(v10 + 2208) = v43;
  if ( !v43 )
    goto LABEL_37;
  v44 = v8 - 40;
  memmove_0(*((void **)v43 + 5), a5 + 40, v8 - 40);
  *(_DWORD *)(*(_QWORD *)(v10 + 2208) + 48LL) = v8 - 40;
  *(_DWORD *)(v10 + 32) = 1;
  *(_QWORD *)(v10 + 40) = ((unsigned __int64)this + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  _InterlockedIncrement((volatile signed __int32 *)(v9 + 56));
  v75 = 1;
  v45 = WdsQueueWorkItem(v10);
  LODWORD(v14) = ElValidateWin32(v45, v46, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 1047);
  if ( (_DWORD)v14 )
    goto LABEL_59;
  LeaveCriticalSection(lpCriticalSection);
  v47 = *(_QWORD *)(v9 + 64);
  v48 = L"Yes";
  v49 = _mm_srli_si128(v26, 15);
  if ( (v27 & 1) == 0 )
    v48 = L"No";
  v50 = (unsigned __int8)_mm_cvtsi128_si32(v49);
  v51 = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v26, 14));
  v52 = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v26, 13));
  v53 = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v26, 12));
  v54 = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v26, 11));
  v55 = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v26, 10));
  v56 = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v26, 9));
  v75 = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v26, 8));
  if ( v47 )
    v57 = *(const wchar_t **)(v47 + 16);
  else
    v57 = L"<Unknown>";
  LODWORD(NetworkOptions) = _mm_extract_epi16(v26, 2);
  LODWORD(Endpoint) = _mm_cvtsi128_si32(v26);
  CTrace::Trace(
    (CTrace *)qword_180039310,
    0x10000u,
    L"[%s][RPC][Ep:{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}] Request Received From:%s Len:%u Auth:%s",
    v57,
    Endpoint,
    NetworkOptions,
    _mm_extract_epi16(v26, 3),
    v75,
    v56,
    v55,
    v54,
    v53,
    v52,
    v51,
    v50,
    NetworkAddr,
    v44,
    v48);
  CPerfCounters::Batch((CPerfCounters *)&g_PerfCounters, 2u, 0);
LABEL_89:
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( NetworkAddr )
    RpcStringFreeW(&NetworkAddr);
  if ( ServerBinding )
    RpcBindingFree(&ServerBinding);
}

```

## disassembly

```asm
0x1800049b4  mov     rax, rsp
0x1800049b7  mov     [rax+20h], rbx
0x1800049bb  mov     [rax+18h], r8
0x1800049bf  mov     [rax+10h], rdx
0x1800049c3  mov     [rax+8], rcx
0x1800049c7  push    rbp
0x1800049c8  push    rsi
0x1800049c9  push    rdi
0x1800049ca  push    r12
0x1800049cc  push    r13
0x1800049ce  push    r14
0x1800049d0  push    r15
0x1800049d2  lea     rbp, [rax-458h]
0x1800049d9  sub     rsp, 530h
0x1800049e0  movaps  xmmword ptr [rax-48h], xmm6
0x1800049e4  mov     r13, rdx
0x1800049e7  xor     eax, eax
0x1800049e9  mov     esi, r9d
0x1800049ec  lea     rdx, [rbp+450h+ServerBinding]; ServerBinding
0x1800049f0  mov     [rbp+450h+Privs], rax
0x1800049f4  mov     rcx, r8; ClientBinding
0x1800049f7  mov     [rbp+450h+ServerBinding], rax
0x1800049fb  mov     edi, eax
0x1800049fd  mov     [rbp+450h+AuthnLevel], eax
0x180004a00  mov     [rbp+450h+StringBinding], rax
0x180004a04  mov     r14d, eax
0x180004a07  mov     [rbp+450h+NetworkAddr], rax
0x180004a0b  mov     r12, r8
0x180004a0e  mov     [rbp+450h+var_4C8], eax
0x180004a11  mov     [rbp+450h+var_4C4], eax
0x180004a14  call    cs:__imp_RpcBindingServerFromClient
0x180004a1b  nop     dword ptr [rax+rax+00h]
0x180004a20  lea     r15, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x180004a27  mov     r9d, 320h
0x180004a2d  mov     ecx, eax
0x180004a2f  mov     r8, r15
0x180004a32  call    ElValidateWin32
0x180004a37  mov     ebx, eax
0x180004a39  test    eax, eax
0x180004a3b  jnz     loc_1800051A4
0x180004a41  mov     rcx, [rbp+450h+ServerBinding]; Binding
0x180004a45  lea     rdx, [rbp+450h+StringBinding]; StringBinding
0x180004a49  call    cs:__imp_RpcBindingToStringBindingW
0x180004a50  nop     dword ptr [rax+rax+00h]
0x180004a55  mov     r9d, 324h
0x180004a5b  mov     r8, r15
0x180004a5e  mov     ecx, eax
0x180004a60  call    ElValidateWin32
0x180004a65  mov     ebx, eax
0x180004a67  xor     eax, eax
0x180004a69  test    ebx, ebx
0x180004a6b  jnz     loc_1800051A4
0x180004a71  mov     rcx, [rbp+450h+StringBinding]; StringBinding
0x180004a75  lea     r9, [rbp+450h+NetworkAddr]; NetworkAddr
0x180004a79  mov     [rsp+560h+NetworkOptions], rax; NetworkOptions
0x180004a7e  xor     r8d, r8d; Protseq
0x180004a81  xor     edx, edx; ObjUuid
0x180004a83  mov     [rsp+560h+Endpoint], rax; Endpoint
0x180004a88  call    cs:__imp_RpcStringBindingParseW
0x180004a8f  nop     dword ptr [rax+rax+00h]
0x180004a94  mov     r9d, 32Dh
0x180004a9a  mov     r8, r15
0x180004a9d  mov     ecx, eax
0x180004a9f  call    ElValidateWin32
0x180004aa4  mov     ebx, eax
0x180004aa6  test    eax, eax
0x180004aa8  jnz     loc_1800051A4
0x180004aae  mov     rcx, [rbp+450h+NetworkAddr]
0x180004ab2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004ab6  xor     ebx, ebx
0x180004ab8  inc     rax
0x180004abb  cmp     [rcx+rax*2], bx
0x180004abf  jnz     short loc_180004AB8
0x180004ac1  mov     r13d, 200h
0x180004ac7  cmp     rax, r13
0x180004aca  jb      short loc_180004ADF
0x180004acc  mov     r9d, 334h
0x180004ad2  mov     r8, r15
0x180004ad5  mov     ecx, 6Fh ; 'o'
0x180004ada  jmp     loc_18000518E
0x180004adf  mov     eax, 28h ; '('
0x180004ae4  cmp     esi, eax
0x180004ae6  jnb     short loc_180004AF6
0x180004ae8  mov     r9d, 33Dh
0x180004aee  mov     r8, r15
0x180004af1  jmp     loc_180005189
0x180004af6  mov     r15, [rbp+450h+arg_20]
0x180004afd  cmp     [r15], ax
0x180004b01  jnz     loc_18000517C
0x180004b07  mov     eax, 100h
0x180004b0c  cmp     [r15+2], ax
0x180004b11  jnz     loc_18000517C
0x180004b17  mov     ecx, ebx
0x180004b19  lea     rax, [r15+18h]
0x180004b1d  cmp     [rax], bl
0x180004b1f  jnz     loc_180005174
0x180004b25  inc     ecx
0x180004b27  inc     rax
0x180004b2a  cmp     ecx, 10h
0x180004b2d  jb      short loc_180004B1D
0x180004b2f  movzx   eax, word ptr [r15]
0x180004b33  mov     ecx, esi
0x180004b35  sub     ecx, eax
0x180004b37  cmp     ecx, [r15+4]
0x180004b3b  jz      short loc_180004B48
0x180004b3d  mov     r9d, 35Eh
0x180004b43  jmp     loc_180005182
0x180004b48  movups  xmm6, xmmword ptr [r15+8]
0x180004b4d  mov     [rsp+560h+NetworkOptions], rbx; AuthzSvc
0x180004b52  lea     r9, [rbp+450h+AuthnLevel]; AuthnLevel
0x180004b56  xor     r8d, r8d; ServerPrincName
0x180004b59  mov     [rsp+560h+Endpoint], rbx; AuthnSvc
0x180004b5e  lea     rdx, [rbp+450h+Privs]; Privs
0x180004b62  mov     rcx, r12; ClientBinding
0x180004b65  call    cs:__imp_RpcBindingInqAuthClientW
0x180004b6c  nop     dword ptr [rax+rax+00h]
0x180004b71  test    eax, eax
0x180004b73  jnz     loc_180004C1F
0x180004b79  cmp     [rbp+450h+AuthnLevel], 6
0x180004b7d  jz      loc_180004C17
0x180004b83  movzx   eax, word ptr [r15]
0x180004b87  lea     rcx, qword_180039300
0x180004b8e  sub     esi, eax
0x180004b90  movdqa  [rbp+450h+var_490], xmm6
0x180004b95  mov     eax, 20h ; ' '
0x180004b9a  mov     r9d, 8
0x180004ba0  cmp     esi, eax
0x180004ba2  mov     edx, 0C1010407h
0x180004ba7  cmova   esi, eax
0x180004baa  lea     rax, [r15+28h]
0x180004bae  mov     [rsp+560h+var_518], esi
0x180004bb2  lea     r8d, [r9-5]
0x180004bb6  mov     qword ptr [rsp+560h+var_520], rax
0x180004bbb  mov     rax, [rbp+450h+NetworkAddr]
0x180004bbf  mov     dword ptr [rsp+560h+var_528], 0Ah
0x180004bc7  mov     qword ptr [rsp+560h+var_530], rax
0x180004bcc  lea     rax, [rbp+450h+var_490]
0x180004bd0  mov     dword ptr [rsp+560h+NetworkOptions], 1
0x180004bd8  mov     [rsp+560h+Endpoint], rax
0x180004bdd  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180004be4  nop     dword ptr [rax+rax+00h]
0x180004be9  mov     r9d, [rbp+450h+AuthnLevel]
0x180004bed  lea     r8, aRpcRequestRece; "[RPC] Request received but auth level ("...
0x180004bf4  mov     edx, 10000h
0x180004bf9  lea     rcx, qword_180039310
0x180004c00  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180004c07  nop     dword ptr [rax+rax+00h]
0x180004c0c  mov     r9d, 385h
0x180004c12  jmp     loc_180005182
0x180004c17  mov     r12d, 1
0x180004c1d  jmp     short loc_180004C25
0x180004c1f  mov     r12d, 2
0x180004c25  mov     rbx, [rbp+450h+arg_0]
0x180004c2c  lea     rax, [rbx+70h]
0x180004c30  mov     rcx, rax; lpCriticalSection
0x180004c33  mov     [rbp+450h+lpCriticalSection], rax
0x180004c37  call    cs:__imp_EnterCriticalSection
0x180004c3e  nop     dword ptr [rax+rax+00h]
0x180004c43  xor     edx, edx; Val
0x180004c45  mov     [rbp+450h+var_4C8], 1
0x180004c4c  mov     r8d, 41Ch; Size
0x180004c52  lea     rcx, [rbp+450h+var_460]; void *
0x180004c56  call    memset_0
0x180004c5b  movups  xmm0, xmmword ptr [r15+8]
0x180004c60  lea     rcx, [rbx+60h]
0x180004c64  mov     [rbp+450h+var_45C], 1
0x180004c6b  lea     rdx, [rbp+450h+var_460]
0x180004c6f  movdqu  [rbp+450h+var_454], xmm0
0x180004c74  call    ??$Find@VCRegRpcEndpoint@@@CRegEndpoint@@SAPEAVCRegRpcEndpoint@@PEAV?$CList@VCRegRpcEndpoint@@VCCriticalSection@@@@PEAUtagWDS_ENDPOINT@@@Z; CRegEndpoint::Find<CRegRpcEndpoint>(CList<CRegRpcEndpoint,CCriticalSection> *,tagWDS_ENDPOINT *)
0x180004c79  xor     ebx, ebx
0x180004c7b  mov     rdi, rax
0x180004c7e  test    rax, rax
0x180004c81  jnz     short loc_180004CED
0x180004c83  movzx   ecx, word ptr [r15]
0x180004c87  lea     eax, [rdi+20h]
0x180004c8a  sub     esi, ecx
0x180004c8c  movdqa  [rbp+450h+var_490], xmm6
0x180004c91  cmp     esi, eax
0x180004c93  lea     r9d, [rdi+8]
0x180004c97  mov     edx, 0C1010408h
0x180004c9c  lea     r8d, [rdi+3]
0x180004ca0  cmova   esi, eax
0x180004ca3  lea     rcx, qword_180039300
0x180004caa  mov     [rsp+560h+var_518], esi
0x180004cae  lea     rax, [r15+28h]
0x180004cb2  mov     qword ptr [rsp+560h+var_520], rax
0x180004cb7  mov     rax, [rbp+450h+NetworkAddr]
0x180004cbb  mov     dword ptr [rsp+560h+var_528], 0Ah
0x180004cc3  mov     qword ptr [rsp+560h+var_530], rax
0x180004cc8  lea     rax, [rbp+450h+var_490]
0x180004ccc  mov     dword ptr [rsp+560h+NetworkOptions], 1
0x180004cd4  mov     [rsp+560h+Endpoint], rax
0x180004cd9  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180004ce0  nop     dword ptr [rax+rax+00h]
0x180004ce5  lea     ebx, [rdi+2]
0x180004ce8  jmp     loc_18000519D
0x180004ced  mov     eax, ebx
0x180004cef  lock xadd [rdi+3Ch], eax
0x180004cf4  test    eax, eax
0x180004cf6  jz      short loc_180004D16
0x180004cf8  mov     r9d, 3AEh
0x180004cfe  lea     r8, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x180004d05  mov     ecx, 2
0x180004d0a  call    ElValidateWin32
0x180004d0f  xor     edi, edi
0x180004d11  jmp     loc_180005193
0x180004d16  mov     ecx, [rdi+50h]
0x180004d19  mov     eax, ecx
0x180004d1b  and     eax, r12d
0x180004d1e  cmp     eax, r12d
0x180004d21  jz      short loc_180004D98
0x180004d23  movzx   eax, word ptr [r15]
0x180004d27  mov     r9d, 8
0x180004d2d  sub     esi, eax
0x180004d2f  movdqa  [rbp+450h+var_480], xmm6
0x180004d34  mov     eax, 20h ; ' '
0x180004d39  cmp     esi, eax
0x180004d3b  lea     r8d, [r9-5]
0x180004d3f  cmova   esi, eax
0x180004d42  and     ecx, 1
0x180004d45  mov     [rsp+560h+var_518], esi
0x180004d49  lea     rax, [r15+28h]
0x180004d4d  mov     qword ptr [rsp+560h+var_520], rax
0x180004d52  mov     rax, [rbp+450h+NetworkAddr]
0x180004d56  mov     dword ptr [rsp+560h+var_528], 0Ah
0x180004d5e  lea     edx, [rcx-3EFEFBF7h]
0x180004d64  mov     qword ptr [rsp+560h+var_530], rax
0x180004d69  lea     rcx, qword_180039300
0x180004d70  lea     rax, [rbp+450h+var_480]
0x180004d74  mov     dword ptr [rsp+560h+NetworkOptions], 1
0x180004d7c  mov     [rsp+560h+Endpoint], rax
0x180004d81  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180004d88  nop     dword ptr [rax+rax+00h]
0x180004d8d  mov     r9d, 3C1h
0x180004d93  jmp     loc_180004CFE
0x180004d98  test    cl, 2
0x180004d9b  jnz     short loc_180004DF4
0x180004d9d  mov     rcx, [rbp+450h+BindingHandle]; BindingHandle
0x180004da4  call    cs:__imp_RpcImpersonateClient
0x180004dab  nop     dword ptr [rax+rax+00h]
0x180004db0  mov     r9d, 2D7h
0x180004db6  lea     r8, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x180004dbd  mov     ecx, eax
0x180004dbf  call    ElValidateWin32
0x180004dc4  mov     ebx, eax
0x180004dc6  test    eax, eax
0x180004dc8  jnz     short loc_180004DF4
0x180004dca  mov     rcx, rdi; this
0x180004dcd  call    ?AccessCheck@CRegRpcEndpoint@@QEAAKXZ; CRegRpcEndpoint::AccessCheck(void)
0x180004dd2  mov     r9d, 2E1h
0x180004dd8  lea     r8, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x180004ddf  mov     ecx, eax
0x180004de1  mov     ebx, eax
0x180004de3  call    ElValidateWin32
0x180004de8  call    cs:__imp_RpcRevertToSelf
0x180004def  nop     dword ptr [rax+rax+00h]
0x180004df4  test    ebx, ebx
0x180004df6  jz      short loc_180004E63
0x180004df8  movzx   eax, word ptr [r15]
0x180004dfc  lea     rcx, qword_180039300
0x180004e03  sub     esi, eax
0x180004e05  movdqa  [rbp+450h+var_470], xmm6
0x180004e0a  mov     eax, 20h ; ' '
0x180004e0f  mov     r9d, 8
0x180004e15  cmp     esi, eax
0x180004e17  mov     edx, 0C101040Bh
0x180004e1c  cmova   esi, eax
0x180004e1f  lea     rax, [r15+28h]
0x180004e23  mov     [rsp+560h+var_518], esi
0x180004e27  lea     r8d, [r9-5]
0x180004e2b  mov     qword ptr [rsp+560h+var_520], rax
0x180004e30  mov     rax, [rbp+450h+NetworkAddr]
0x180004e34  mov     dword ptr [rsp+560h+var_528], 0Ah
0x180004e3c  mov     qword ptr [rsp+560h+var_530], rax
0x180004e41  lea     rax, [rbp+450h+var_470]
0x180004e45  mov     dword ptr [rsp+560h+NetworkOptions], 1
0x180004e4d  mov     [rsp+560h+Endpoint], rax
0x180004e52  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180004e59  nop     dword ptr [rax+rax+00h]
0x180004e5e  jmp     loc_18000519D
0x180004e63  mov     rbx, [rbp+450h+arg_0]
0x180004e6a  lea     rcx, [rbx+20h]
0x180004e6e  call    ?GetObjectW@?$CPool@URpcRequest@@@@QEAAPEAURpcRequest@@H@Z; CPool<RpcRequest>::GetObjectW(int)
0x180004e73  mov     r14, rax
0x180004e76  test    rax, rax
0x180004e79  jnz     short loc_180004E85
0x180004e7b  mov     ebx, 8
0x180004e80  jmp     loc_18000519D
0x180004e85  mov     rax, [rbp+450h+arg_8]
0x180004e8c  lea     rdx, [rdi+48h]; Src
0x180004e90  mov     [r14+38h], rax
0x180004e94  lea     rcx, [r14+484h]; void *
0x180004e9b  mov     rax, [rbp+450h+BindingHandle]
0x180004ea2  mov     r8d, 41Ch; Size
0x180004ea8  mov     [r14+40h], rax
0x180004eac  mov     rax, [rbp+450h+arg_28]
0x180004eb3  mov     [r14+58h], rax
0x180004eb7  mov     rax, [rbp+450h+arg_30]
0x180004ebe  mov     [r14+60h], rax
0x180004ec2  mov     [r14+48h], esi
  ... truncated ...
```
