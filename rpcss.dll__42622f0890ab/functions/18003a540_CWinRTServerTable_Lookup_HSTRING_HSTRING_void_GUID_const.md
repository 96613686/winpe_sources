# CWinRTServerTable::Lookup(HSTRING__ *,HSTRING__ *,void *,_GUID const &)

- ea: `0x18003a540`
- end: `0x18003a902`
- name: `?Lookup@CWinRTServerTable@@QEAAPEAVCWinRTServerTableEntry@@PEAUHSTRING__@@0PEAXAEBU_GUID@@@Z`
- size: `962`
- prototype: `struct CWinRTServerTableEntry *__fastcall(CWinRTServerTable *this, HSTRING, HSTRING, void *, const struct _GUID *)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005c80`
- `0x180039340`
- `0x18003a250`
- `0x18003a404`

## callees

- `0x18001ec28`
- `0x18002ba28`
- `0x18003a540`
- `0x1800814c8`
- `0x18008e98c`
- `0x1800a2c08`
- `0x1800b27e0`
- `0x1800b3128`
- `0x1800ba088`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18003a784`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18003a784`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a6be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a6e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a8c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a6be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a6e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a8c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a66a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a66a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a5a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a5a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a5b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a5b5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a59f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a89a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a59f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a89a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003a691`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003a691`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003a656`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003a656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a5e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a620`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a8cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a8d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a5e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a620`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a8cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a8d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003a5f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003a631`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003a5f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003a631`

## string_xrefs

- `0x18003a69f`: `onecore\com\combase\rpcss\olescm\ServerTableKey.hpp`
- `0x18003a7fc`: `onecore\com\combase\rpcss\olescm\ServerTableKey.hpp`
- `0x18003a84a`: `onecore\com\combase\rpcss\olescm\class.cxx`

## pseudocode

```c
struct CWinRTServerTableEntry *__fastcall CWinRTServerTable::Lookup(
        CWinRTServerTable *this,
        HSTRING a2,
        HSTRING a3,
        void *a4,
        const struct _GUID *a5)
{
  __int64 v5; // rbx
  HRESULT v10; // eax
  int LastError; // ebx
  __int64 v12; // r9
  __int64 v13; // rdx
  HRESULT v14; // eax
  SIZE_T LengthSid; // rbx
  void *v16; // rax
  void *v17; // rdi
  const char *v18; // r9
  void *v19; // r8
  _QWORD *v20; // rbx
  volatile signed __int32 *v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // rcx
  int v24; // eax
  void *v26; // r8
  int v28; // [rsp+20h] [rbp-E0h]
  struct _EXCEPTION_RECORD pExceptionRecord; // [rsp+40h] [rbp-C0h] BYREF
  void **v30; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING newString[2]; // [rsp+E8h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+F8h] [rbp-8h]
  GUID v33; // [rsp+100h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v5 = *((_QWORD *)this + 3);
  _InterlockedIncrement((volatile signed __int32 *)(v5 + 56));
  if ( (unsigned int)CInterlockedInteger::operator long(v5 + 60) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 56), 0xFFFFFFFF) == 1 )
      SetEvent(*(HANDLE *)(v5 + 48));
    EnterCriticalSection((LPCRITICAL_SECTION)v5);
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 56));
    LeaveCriticalSection((LPCRITICAL_SECTION)v5);
  }
  _InterlockedExchange((volatile __int32 *)(v5 + 64), 0);
  lpMem = 0;
  v30 = &CAcidPackageSidCpidKey::`vftable';
  v33 = GUID_NULL;
  *(_OWORD *)newString = 0;
  WindowsDeleteString(0);
  newString[0] = 0;
  v10 = WindowsDuplicateString(a2, newString);
  LastError = v10;
  if ( v10 < 0 )
  {
    v12 = (unsigned int)v10;
    v13 = 176;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\ServerTableKey.hpp",
      (const char *)v12,
      v28);
LABEL_33:
    v21 = 0;
    if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      ComTraceHr(
        LastError,
        "onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        "CWinRTServerTable::Lookup",
        879,
        L"Failed to initialize key for activatable class table: %!HRESULT!",
        LastError);
    goto LABEL_29;
  }
  if ( !a3 || a3 != newString[1] )
  {
    WindowsDeleteString(newString[1]);
    newString[1] = 0;
    v14 = WindowsDuplicateString(a3, &newString[1]);
    LastError = v14;
    if ( v14 < 0 )
    {
      v12 = (unsigned int)v14;
      v13 = 177;
      goto LABEL_32;
    }
  }
  if ( !a4 )
    goto LABEL_18;
  LengthSid = GetLengthSid(a4);
  v16 = HeapAlloc(g_hHeap, 0, LengthSid);
  v17 = v16;
  if ( !v16 )
  {
    LastError = -2147024882;
    v13 = 183;
    v12 = 2147942414LL;
    goto LABEL_32;
  }
  memset_0(v16, 0, (unsigned int)LengthSid);
  if ( CopySid(LengthSid, v17, a4) )
  {
    v19 = lpMem;
    lpMem = v17;
    if ( v19 )
      HeapFree(g_hHeap, 0, v19);
LABEL_18:
    v33 = *a5;
    goto LABEL_19;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0xB8,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\ServerTableKey.hpp",
                v18);
  HeapFree(g_hHeap, 0, v17);
  if ( LastError < 0 )
    goto LABEL_33;
LABEL_19:
  v20 = *(_QWORD **)(*((_QWORD *)this + 1)
                   + 8LL * (((unsigned int (__fastcall *)(void ***))*v30)(&v30) % *(_DWORD *)this));
  if ( v20 )
  {
    while ( 1 )
    {
      if ( v20[2] == 0xDEADDEADDEADDEADuLL )
      {
        pExceptionRecord.ExceptionCode = -2147467261;
        pExceptionRecord.ExceptionFlags = 1;
        pExceptionRecord.ExceptionRecord = 0;
        pExceptionRecord.ExceptionAddress = retaddr;
        memset(&pExceptionRecord.NumberParameters, 0, 128);
        RaiseFailFastException(&pExceptionRecord, 0, 2u);
      }
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, void ***))(*v20 + 40LL))(v20, &v30) )
        break;
      v20 = (_QWORD *)v20[2];
      if ( !v20 )
        goto LABEL_24;
    }
  }
  else
  {
LABEL_24:
    v20 = 0;
  }
  v21 = (volatile signed __int32 *)(v20 - 20);
  if ( !v20 )
    v21 = 0;
  if ( v21 )
    _InterlockedIncrement(v21 + 42);
LABEL_29:
  v22 = *((_QWORD *)this + 3);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss>::GetImpl'::`2'::impl) )
  {
    v23 = 0;
    v24 = _InterlockedCompareExchange((volatile signed __int32 *)(v22 + 56), 0, 0);
  }
  else
  {
    v24 = *(_DWORD *)(v22 + 56);
  }
  if ( v24 <= 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v23);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v22 + 56), 0xFFFFFFFF) == 1 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss>::GetImpl'::`2'::impl)
       ? _InterlockedCompareExchange((volatile signed __int32 *)(v22 + 60), 0, 0)
       : *(_DWORD *)(v22 + 60) )
    {
      SetEvent(*(HANDLE *)(v22 + 48));
    }
  }
  v26 = lpMem;
  v30 = &CAcidPackageSidCpidKey::`vftable';
  lpMem = 0;
  if ( v26 )
    HeapFree(g_hHeap, 0, v26);
  WindowsDeleteString(newString[1]);
  newString[1] = 0;
  WindowsDeleteString(newString[0]);
  return (struct CWinRTServerTableEntry *)v21;
}

```

## disassembly

```asm
0x18003a540  push    rbp
0x18003a542  push    rbx
0x18003a543  push    rsi
0x18003a544  push    rdi
0x18003a545  push    r12
0x18003a547  push    r13
0x18003a549  push    r14
0x18003a54b  push    r15
0x18003a54d  lea     rbp, [rsp-28h]
0x18003a552  sub     rsp, 128h
0x18003a559  mov     rax, cs:__security_cookie
0x18003a560  xor     rax, rsp
0x18003a563  mov     [rbp+60h+var_50], rax
0x18003a567  mov     rbx, [rcx+18h]
0x18003a56b  mov     rsi, r9
0x18003a56e  mov     rdi, r8
0x18003a571  mov     r15, rdx
0x18003a574  mov     r13, rcx
0x18003a577  lock inc dword ptr [rbx+38h]
0x18003a57b  lea     rcx, [rbx+3Ch]
0x18003a57f  call    ??BCInterlockedInteger@@QEAAJXZ; CInterlockedInteger::operator long(void)
0x18003a584  mov     r14d, 0FFFFFFFFh
0x18003a58a  test    eax, eax
0x18003a58c  jz      short loc_18003A5BB
0x18003a58e  mov     eax, r14d
0x18003a591  lock xadd [rbx+38h], eax
0x18003a596  cmp     eax, 1
0x18003a599  jnz     short loc_18003A5A5
0x18003a59b  mov     rcx, [rbx+30h]; hEvent
0x18003a59f  call    cs:__imp_SetEvent
0x18003a5a5  mov     rcx, rbx; lpCriticalSection
0x18003a5a8  call    cs:__imp_EnterCriticalSection
0x18003a5ae  lock inc dword ptr [rbx+38h]
0x18003a5b2  mov     rcx, rbx; lpCriticalSection
0x18003a5b5  call    cs:__imp_LeaveCriticalSection
0x18003a5bb  xor     r12d, r12d
0x18003a5be  xorps   xmm0, xmm0
0x18003a5c1  mov     eax, r12d
0x18003a5c4  xor     ecx, ecx; string
0x18003a5c6  xchg    eax, [rbx+40h]
0x18003a5c9  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18003a5d0  lea     rax, ??_7CAcidPackageSidCpidKey@@6B@; const CAcidPackageSidCpidKey::`vftable'
0x18003a5d7  mov     [rbp+60h+lpMem], r12
0x18003a5db  mov     [rbp+60h+var_80], rax
0x18003a5df  movups  [rbp+60h+var_60], xmm1
0x18003a5e3  movdqu  xmmword ptr [rbp+60h+newString], xmm0
0x18003a5e8  call    cs:__imp_WindowsDeleteString
0x18003a5ee  lea     rdx, [rbp+60h+newString]; newString
0x18003a5f2  mov     [rbp+60h+newString], r12
0x18003a5f6  mov     rcx, r15; string
0x18003a5f9  call    cs:__imp_WindowsDuplicateString
0x18003a5ff  mov     ebx, eax
0x18003a601  test    eax, eax
0x18003a603  jns     short loc_18003A612
0x18003a605  mov     r9d, eax
0x18003a608  mov     edx, 0B0h
0x18003a60d  jmp     loc_18003A7F8
0x18003a612  mov     rcx, [rbp+60h+newString+8]; string
0x18003a616  test    rdi, rdi
0x18003a619  jz      short loc_18003A620
0x18003a61b  cmp     rdi, rcx
0x18003a61e  jz      short loc_18003A64A
0x18003a620  call    cs:__imp_WindowsDeleteString
0x18003a626  lea     rdx, [rbp+60h+newString+8]; newString
0x18003a62a  mov     [rbp+60h+newString+8], r12
0x18003a62e  mov     rcx, rdi; string
0x18003a631  call    cs:__imp_WindowsDuplicateString
0x18003a637  mov     ebx, eax
0x18003a639  test    eax, eax
0x18003a63b  jns     short loc_18003A64A
0x18003a63d  mov     r9d, eax
0x18003a640  mov     edx, 0B1h
0x18003a645  jmp     loc_18003A7F8
0x18003a64a  test    rsi, rsi
0x18003a64d  jz      loc_18003A6E9
0x18003a653  mov     rcx, rsi; pSid
0x18003a656  call    cs:__imp_GetLengthSid
0x18003a65c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003a663  xor     edx, edx; dwFlags
0x18003a665  mov     r8d, eax; dwBytes
0x18003a668  mov     ebx, eax
0x18003a66a  call    cs:__imp_HeapAlloc
0x18003a670  mov     rdi, rax
0x18003a673  test    rax, rax
0x18003a676  jz      loc_18003A7EB
0x18003a67c  mov     r8d, ebx; Size
0x18003a67f  xor     edx, edx; Val
0x18003a681  mov     rcx, rax; void *
0x18003a684  call    memset_0
0x18003a689  mov     r8, rsi; pSourceSid
0x18003a68c  mov     rdx, rdi; pDestinationSid
0x18003a68f  mov     ecx, ebx; nDestinationSidLength
0x18003a691  call    cs:__imp_CopySid
0x18003a697  test    eax, eax
0x18003a699  jnz     short loc_18003A6CD
0x18003a69b  mov     rcx, [rbp+68h]; this
0x18003a69f  lea     r8, aOnecoreComComb_87; "onecore\\com\\combase\\rpcss\\olescm\\S"...
0x18003a6a6  mov     edx, 0B8h; void *
0x18003a6ab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003a6b0  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003a6b7  mov     r8, rdi; lpMem
0x18003a6ba  xor     edx, edx; dwFlags
0x18003a6bc  mov     ebx, eax
0x18003a6be  call    cs:__imp_HeapFree
0x18003a6c4  test    ebx, ebx
0x18003a6c6  jns     short loc_18003A6F7
0x18003a6c8  jmp     loc_18003A808
0x18003a6cd  mov     r8, [rbp+60h+lpMem]; lpMem
0x18003a6d1  mov     [rbp+60h+lpMem], rdi
0x18003a6d5  test    r8, r8
0x18003a6d8  jz      short loc_18003A6E9
0x18003a6da  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003a6e1  xor     edx, edx; dwFlags
0x18003a6e3  call    cs:__imp_HeapFree
0x18003a6e9  mov     rax, [rbp+60h+arg_20]
0x18003a6f0  movups  xmm0, xmmword ptr [rax]
0x18003a6f3  movups  [rbp+60h+var_60], xmm0
0x18003a6f7  mov     rax, [rbp+60h+var_80]
0x18003a6fb  lea     rcx, [rbp+60h+var_80]
0x18003a6ff  mov     rax, [rax]
0x18003a702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a707  xor     edx, edx
0x18003a709  div     dword ptr [r13+0]
0x18003a70d  mov     rax, [r13+8]
0x18003a711  mov     rbx, [rax+rdx*8]
0x18003a715  test    rbx, rbx
0x18003a718  jz      loc_18003A7AE
0x18003a71e  mov     rsi, 0DEADDEADDEADDEADh
0x18003a728  cmp     [rbx+10h], rsi
0x18003a72c  jnz     short loc_18003A78A
0x18003a72e  mov     rax, [rbp+68h]
0x18003a732  lea     rcx, [rsp+160h+pExceptionRecord]; pExceptionRecord
0x18003a737  xorps   xmm0, xmm0
0x18003a73a  mov     [rsp+160h+pExceptionRecord.ExceptionCode], 80004003h
0x18003a742  movups  xmmword ptr [rbp+60h+pExceptionRecord.ExceptionInformation+5Ch], xmm0
0x18003a746  xor     edx, edx; pContextRecord
0x18003a748  mov     [rsp+160h+pExceptionRecord.ExceptionFlags], 1
0x18003a750  mov     r8d, 2; dwFlags
0x18003a756  mov     [rsp+160h+pExceptionRecord.ExceptionRecord], r12
0x18003a75b  movups  xmmword ptr [rbp+60h+pExceptionRecord.ExceptionInformation+68h], xmm0
0x18003a75f  mov     [rsp+160h+pExceptionRecord.ExceptionAddress], rax
0x18003a764  movups  xmmword ptr [rsp+160h+pExceptionRecord+1Ch], xmm0
0x18003a769  mov     [rsp+160h+pExceptionRecord.NumberParameters], r12d
0x18003a76e  movups  xmmword ptr [rsp+160h+pExceptionRecord.ExceptionInformation+0Ch], xmm0
0x18003a773  movups  xmmword ptr [rsp+160h+pExceptionRecord.ExceptionInformation+1Ch], xmm0
0x18003a778  movups  xmmword ptr [rbp+60h+pExceptionRecord.ExceptionInformation+2Ch], xmm0
0x18003a77c  movups  xmmword ptr [rbp+60h+pExceptionRecord.ExceptionInformation+3Ch], xmm0
0x18003a780  movups  xmmword ptr [rbp+60h+pExceptionRecord.ExceptionInformation+4Ch], xmm0
0x18003a784  call    cs:__imp_RaiseFailFastException
0x18003a78a  mov     rax, [rbx]
0x18003a78d  lea     rdx, [rbp+60h+var_80]
0x18003a791  mov     rcx, rbx
0x18003a794  mov     rax, [rax+28h]
0x18003a798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a79d  test    al, al
0x18003a79f  jnz     short loc_18003A7B1
0x18003a7a1  mov     rbx, [rbx+10h]
0x18003a7a5  test    rbx, rbx
0x18003a7a8  jnz     loc_18003A728
0x18003a7ae  mov     rbx, r12
0x18003a7b1  test    rbx, rbx
0x18003a7b4  lea     rdi, [rbx-0A0h]
0x18003a7bb  cmovz   rdi, r12
0x18003a7bf  test    rdi, rdi
0x18003a7c2  jz      short loc_18003A7CB
0x18003a7c4  lock inc dword ptr [rdi+0A8h]
0x18003a7cb  mov     rbx, [r13+18h]
0x18003a7cf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss> `wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss>::GetImpl(void)'::`2'::impl
0x18003a7d6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss>::__private_IsEnabled(void)
0x18003a7db  test    al, al
0x18003a7dd  jz      short loc_18003A85B
0x18003a7df  mov     ecx, r12d
0x18003a7e2  xor     eax, eax
0x18003a7e4  lock cmpxchg [rbx+38h], ecx
0x18003a7e9  jmp     short loc_18003A85E
0x18003a7eb  mov     ebx, 8007000Eh
0x18003a7f0  mov     edx, 0B7h; void *
0x18003a7f5  mov     r9d, ebx; char *
0x18003a7f8  mov     rcx, [rbp+68h]; this
0x18003a7fc  lea     r8, aOnecoreComComb_87; "onecore\\com\\combase\\rpcss\\olescm\\S"...
0x18003a803  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a808  mov     eax, cs:dword_18014E4B8
0x18003a80e  mov     rdi, r12
0x18003a811  test    eax, eax
0x18003a813  jnz     short loc_18003A82B
0x18003a815  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18003a81c  jz      short loc_18003A7CB
0x18003a81e  mov     rax, cs:WPP_GLOBAL_Control
0x18003a825  test    byte ptr [rax+1Ch], 1
0x18003a829  jz      short loc_18003A7CB
0x18003a82b  lea     rax, aFailedToInitia; "Failed to initialize key for activatabl"...
0x18003a832  mov     [rsp+160h+var_138], ebx
0x18003a836  mov     r9d, 36Fh; int
0x18003a83c  mov     [rsp+160h+var_140], rax; unsigned __int16 *
0x18003a841  lea     r8, aCwinrtserverta; "CWinRTServerTable::Lookup"
0x18003a848  mov     ecx, ebx; int
0x18003a84a  lea     rdx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18003a851  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x18003a856  jmp     loc_18003A7CB
0x18003a85b  mov     eax, [rbx+38h]
0x18003a85e  test    eax, eax
0x18003a860  jg      short loc_18003A867
0x18003a862  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003a867  lock xadd [rbx+38h], r14d
0x18003a86d  cmp     r14d, 1
0x18003a871  jnz     short loc_18003A8A0
0x18003a873  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss> `wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss>::GetImpl(void)'::`2'::impl
0x18003a87a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss>::__private_IsEnabled(void)
0x18003a87f  test    al, al
0x18003a881  jz      short loc_18003A88F
0x18003a883  mov     ecx, r12d
0x18003a886  xor     eax, eax
0x18003a888  lock cmpxchg [rbx+3Ch], ecx
0x18003a88d  jmp     short loc_18003A892
0x18003a88f  mov     eax, [rbx+3Ch]
0x18003a892  test    eax, eax
0x18003a894  jz      short loc_18003A8A0
0x18003a896  mov     rcx, [rbx+30h]; hEvent
0x18003a89a  call    cs:__imp_SetEvent
0x18003a8a0  mov     r8, [rbp+60h+lpMem]; lpMem
0x18003a8a4  lea     rax, ??_7CAcidPackageSidCpidKey@@6B@; const CAcidPackageSidCpidKey::`vftable'
0x18003a8ab  mov     [rbp+60h+var_80], rax
0x18003a8af  mov     [rbp+60h+lpMem], r12
0x18003a8b3  test    r8, r8
0x18003a8b6  jz      short loc_18003A8C7
0x18003a8b8  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003a8bf  xor     edx, edx; dwFlags
0x18003a8c1  call    cs:__imp_HeapFree
0x18003a8c7  mov     rcx, [rbp+60h+newString+8]; string
0x18003a8cb  call    cs:__imp_WindowsDeleteString
0x18003a8d1  mov     rcx, [rbp+60h+newString]; string
0x18003a8d5  mov     [rbp+60h+newString+8], r12
0x18003a8d9  call    cs:__imp_WindowsDeleteString
0x18003a8df  mov     rax, rdi
0x18003a8e2  mov     rcx, [rbp+60h+var_50]
0x18003a8e6  xor     rcx, rsp; StackCookie
0x18003a8e9  call    __security_check_cookie
0x18003a8ee  add     rsp, 128h
0x18003a8f5  pop     r15
0x18003a8f7  pop     r14
0x18003a8f9  pop     r13
0x18003a8fb  pop     r12
0x18003a8fd  pop     rdi
0x18003a8fe  pop     rsi
0x18003a8ff  pop     rbx
0x18003a900  pop     rbp
0x18003a901  retn
```
