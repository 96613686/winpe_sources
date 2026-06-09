# CWinRTServerTable::Lookup(HSTRING__ *,HSTRING__ *,void *,_GUID const &)

- ea: `0x180044940`
- end: `0x180044d69`
- name: `?Lookup@CWinRTServerTable@@QEAAPEAVCWinRTServerTableEntry@@PEAUHSTRING__@@0PEAXAEBU_GUID@@@Z`
- size: `1065`
- prototype: `struct CWinRTServerTableEntry *(CWinRTServerTable *__hidden this, HSTRING, HSTRING, void *, const struct _GUID *)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800065e4`
- `0x1800436b0`
- `0x180044640`
- `0x180044804`

## callees

- `0x18000ce5c`
- `0x1800210f8`
- `0x18003ca38`
- `0x180044940`
- `0x180095c0c`
- `0x1800a8240`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x1800bf7ec`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180044bcc`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180044bcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044afa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044b25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044d15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044afa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044b25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044d15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044a9a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044a9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800449ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800449ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800449c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800449c1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004499f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180044ce8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004499f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180044ce8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180044ac7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180044ac7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180044a80`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180044a80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800449fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044a3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044d25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800449fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044a3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044d25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180044a11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180044a55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180044a11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180044a55`

## string_xrefs

- `0x180044adb`: `onecore\com\combase\rpcss\olescm\ServerTableKey.hpp`
- `0x180044c4a`: `onecore\com\combase\rpcss\olescm\ServerTableKey.hpp`
- `0x180044c98`: `onecore\com\combase\rpcss\olescm\class.cxx`

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
    if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
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
0x180044940  push    rbp
0x180044942  push    rbx
0x180044943  push    rsi
0x180044944  push    rdi
0x180044945  push    r12
0x180044947  push    r13
0x180044949  push    r14
0x18004494b  push    r15
0x18004494d  lea     rbp, [rsp-28h]
0x180044952  sub     rsp, 128h
0x180044959  mov     rax, cs:__security_cookie
0x180044960  xor     rax, rsp
0x180044963  mov     [rbp+60h+var_50], rax
0x180044967  mov     rbx, [rcx+18h]
0x18004496b  mov     rsi, r9
0x18004496e  mov     rdi, r8
0x180044971  mov     r15, rdx
0x180044974  mov     r13, rcx
0x180044977  lock inc dword ptr [rbx+38h]
0x18004497b  lea     rcx, [rbx+3Ch]
0x18004497f  call    ??BCInterlockedInteger@@QEAAJXZ; CInterlockedInteger::operator long(void)
0x180044984  mov     r14d, 0FFFFFFFFh
0x18004498a  test    eax, eax
0x18004498c  jz      short loc_1800449CD
0x18004498e  mov     eax, r14d
0x180044991  lock xadd [rbx+38h], eax
0x180044996  cmp     eax, 1
0x180044999  jnz     short loc_1800449AB
0x18004499b  mov     rcx, [rbx+30h]; hEvent
0x18004499f  call    cs:__imp_SetEvent
0x1800449a6  nop     dword ptr [rax+rax+00h]
0x1800449ab  mov     rcx, rbx; lpCriticalSection
0x1800449ae  call    cs:__imp_EnterCriticalSection
0x1800449b5  nop     dword ptr [rax+rax+00h]
0x1800449ba  lock inc dword ptr [rbx+38h]
0x1800449be  mov     rcx, rbx; lpCriticalSection
0x1800449c1  call    cs:__imp_LeaveCriticalSection
0x1800449c8  nop     dword ptr [rax+rax+00h]
0x1800449cd  xor     r12d, r12d
0x1800449d0  xorps   xmm0, xmm0
0x1800449d3  mov     eax, r12d
0x1800449d6  xor     ecx, ecx; string
0x1800449d8  xchg    eax, [rbx+40h]
0x1800449db  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x1800449e2  lea     rax, ??_7CAcidPackageSidCpidKey@@6B@; const CAcidPackageSidCpidKey::`vftable'
0x1800449e9  mov     [rbp+60h+lpMem], r12
0x1800449ed  mov     [rbp+60h+var_80], rax
0x1800449f1  movups  [rbp+60h+var_60], xmm1
0x1800449f5  movdqu  xmmword ptr [rbp+60h+newString], xmm0
0x1800449fa  call    cs:__imp_WindowsDeleteString
0x180044a01  nop     dword ptr [rax+rax+00h]
0x180044a06  lea     rdx, [rbp+60h+newString]; newString
0x180044a0a  mov     [rbp+60h+newString], r12
0x180044a0e  mov     rcx, r15; string
0x180044a11  call    cs:__imp_WindowsDuplicateString
0x180044a18  nop     dword ptr [rax+rax+00h]
0x180044a1d  mov     ebx, eax
0x180044a1f  test    eax, eax
0x180044a21  jns     short loc_180044A30
0x180044a23  mov     r9d, eax
0x180044a26  mov     edx, 0B0h
0x180044a2b  jmp     loc_180044C46
0x180044a30  mov     rcx, [rbp+60h+newString+8]; string
0x180044a34  test    rdi, rdi
0x180044a37  jz      short loc_180044A3E
0x180044a39  cmp     rdi, rcx
0x180044a3c  jz      short loc_180044A74
0x180044a3e  call    cs:__imp_WindowsDeleteString
0x180044a45  nop     dword ptr [rax+rax+00h]
0x180044a4a  lea     rdx, [rbp+60h+newString+8]; newString
0x180044a4e  mov     [rbp+60h+newString+8], r12
0x180044a52  mov     rcx, rdi; string
0x180044a55  call    cs:__imp_WindowsDuplicateString
0x180044a5c  nop     dword ptr [rax+rax+00h]
0x180044a61  mov     ebx, eax
0x180044a63  test    eax, eax
0x180044a65  jns     short loc_180044A74
0x180044a67  mov     r9d, eax
0x180044a6a  mov     edx, 0B1h
0x180044a6f  jmp     loc_180044C46
0x180044a74  test    rsi, rsi
0x180044a77  jz      loc_180044B31
0x180044a7d  mov     rcx, rsi; pSid
0x180044a80  call    cs:__imp_GetLengthSid
0x180044a87  nop     dword ptr [rax+rax+00h]
0x180044a8c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180044a93  xor     edx, edx; dwFlags
0x180044a95  mov     r8d, eax; dwBytes
0x180044a98  mov     ebx, eax
0x180044a9a  call    cs:__imp_HeapAlloc
0x180044aa1  nop     dword ptr [rax+rax+00h]
0x180044aa6  mov     rdi, rax
0x180044aa9  test    rax, rax
0x180044aac  jz      loc_180044C39
0x180044ab2  mov     r8d, ebx; Size
0x180044ab5  xor     edx, edx; Val
0x180044ab7  mov     rcx, rax; void *
0x180044aba  call    memset_0
0x180044abf  mov     r8, rsi; pSourceSid
0x180044ac2  mov     rdx, rdi; pDestinationSid
0x180044ac5  mov     ecx, ebx; nDestinationSidLength
0x180044ac7  call    cs:__imp_CopySid
0x180044ace  nop     dword ptr [rax+rax+00h]
0x180044ad3  test    eax, eax
0x180044ad5  jnz     short loc_180044B0F
0x180044ad7  mov     rcx, [rbp+68h]; this
0x180044adb  lea     r8, aOnecoreComComb_87; "onecore\\com\\combase\\rpcss\\olescm\\S"...
0x180044ae2  mov     edx, 0B8h; void *
0x180044ae7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180044aec  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180044af3  mov     r8, rdi; lpMem
0x180044af6  xor     edx, edx; dwFlags
0x180044af8  mov     ebx, eax
0x180044afa  call    cs:__imp_HeapFree
0x180044b01  nop     dword ptr [rax+rax+00h]
0x180044b06  test    ebx, ebx
0x180044b08  jns     short loc_180044B3F
0x180044b0a  jmp     loc_180044C56
0x180044b0f  mov     r8, [rbp+60h+lpMem]; lpMem
0x180044b13  mov     [rbp+60h+lpMem], rdi
0x180044b17  test    r8, r8
0x180044b1a  jz      short loc_180044B31
0x180044b1c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180044b23  xor     edx, edx; dwFlags
0x180044b25  call    cs:__imp_HeapFree
0x180044b2c  nop     dword ptr [rax+rax+00h]
0x180044b31  mov     rax, [rbp+60h+arg_20]
0x180044b38  movups  xmm0, xmmword ptr [rax]
0x180044b3b  movups  [rbp+60h+var_60], xmm0
0x180044b3f  mov     rax, [rbp+60h+var_80]
0x180044b43  lea     rcx, [rbp+60h+var_80]
0x180044b47  mov     rax, [rax]
0x180044b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b4f  xor     edx, edx
0x180044b51  div     dword ptr [r13+0]
0x180044b55  mov     rax, [r13+8]
0x180044b59  mov     rbx, [rax+rdx*8]
0x180044b5d  test    rbx, rbx
0x180044b60  jz      loc_180044BFC
0x180044b66  mov     rsi, 0DEADDEADDEADDEADh
0x180044b70  cmp     [rbx+10h], rsi
0x180044b74  jnz     short loc_180044BD8
0x180044b76  mov     rax, [rbp+68h]
0x180044b7a  lea     rcx, [rsp+160h+pExceptionRecord]; pExceptionRecord
0x180044b7f  xorps   xmm0, xmm0
0x180044b82  mov     [rsp+160h+pExceptionRecord.ExceptionCode], 80004003h
0x180044b8a  movups  xmmword ptr [rbp+60h+pExceptionRecord.ExceptionInformation+5Ch], xmm0
0x180044b8e  xor     edx, edx; pContextRecord
0x180044b90  mov     [rsp+160h+pExceptionRecord.ExceptionFlags], 1
0x180044b98  mov     r8d, 2; dwFlags
0x180044b9e  mov     [rsp+160h+pExceptionRecord.ExceptionRecord], r12
0x180044ba3  movups  xmmword ptr [rbp+60h+pExceptionRecord.ExceptionInformation+68h], xmm0
0x180044ba7  mov     [rsp+160h+pExceptionRecord.ExceptionAddress], rax
0x180044bac  movups  xmmword ptr [rsp+160h+pExceptionRecord+1Ch], xmm0
0x180044bb1  mov     [rsp+160h+pExceptionRecord.NumberParameters], r12d
0x180044bb6  movups  xmmword ptr [rsp+160h+pExceptionRecord.ExceptionInformation+0Ch], xmm0
0x180044bbb  movups  xmmword ptr [rsp+160h+pExceptionRecord.ExceptionInformation+1Ch], xmm0
0x180044bc0  movups  xmmword ptr [rbp+60h+pExceptionRecord.ExceptionInformation+2Ch], xmm0
0x180044bc4  movups  xmmword ptr [rbp+60h+pExceptionRecord.ExceptionInformation+3Ch], xmm0
0x180044bc8  movups  xmmword ptr [rbp+60h+pExceptionRecord.ExceptionInformation+4Ch], xmm0
0x180044bcc  call    cs:__imp_RaiseFailFastException
0x180044bd3  nop     dword ptr [rax+rax+00h]
0x180044bd8  mov     rax, [rbx]
0x180044bdb  lea     rdx, [rbp+60h+var_80]
0x180044bdf  mov     rcx, rbx
0x180044be2  mov     rax, [rax+28h]
0x180044be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044beb  test    al, al
0x180044bed  jnz     short loc_180044BFF
0x180044bef  mov     rbx, [rbx+10h]
0x180044bf3  test    rbx, rbx
0x180044bf6  jnz     loc_180044B70
0x180044bfc  mov     rbx, r12
0x180044bff  test    rbx, rbx
0x180044c02  lea     rdi, [rbx-0A0h]
0x180044c09  cmovz   rdi, r12
0x180044c0d  test    rdi, rdi
0x180044c10  jz      short loc_180044C19
0x180044c12  lock inc dword ptr [rdi+0A8h]
0x180044c19  mov     rbx, [r13+18h]
0x180044c1d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss> `wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss>::GetImpl(void)'::`2'::impl
0x180044c24  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss>::__private_IsEnabled(void)
0x180044c29  test    al, al
0x180044c2b  jz      short loc_180044CA9
0x180044c2d  mov     ecx, r12d
0x180044c30  xor     eax, eax
0x180044c32  lock cmpxchg [rbx+38h], ecx
0x180044c37  jmp     short loc_180044CAC
0x180044c39  mov     ebx, 8007000Eh
0x180044c3e  mov     edx, 0B7h; void *
0x180044c43  mov     r9d, ebx; char *
0x180044c46  mov     rcx, [rbp+68h]; this
0x180044c4a  lea     r8, aOnecoreComComb_87; "onecore\\com\\combase\\rpcss\\olescm\\S"...
0x180044c51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044c56  mov     eax, cs:dword_1801574B8
0x180044c5c  mov     rdi, r12
0x180044c5f  test    eax, eax
0x180044c61  jnz     short loc_180044C79
0x180044c63  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180044c6a  jz      short loc_180044C19
0x180044c6c  mov     rax, cs:WPP_GLOBAL_Control
0x180044c73  test    byte ptr [rax+1Ch], 1
0x180044c77  jz      short loc_180044C19
0x180044c79  lea     rax, aFailedToInitia; "Failed to initialize key for activatabl"...
0x180044c80  mov     [rsp+160h+var_138], ebx
0x180044c84  mov     r9d, 36Fh; int
0x180044c8a  mov     [rsp+160h+var_140], rax; unsigned __int16 *
0x180044c8f  lea     r8, aCwinrtserverta; "CWinRTServerTable::Lookup"
0x180044c96  mov     ecx, ebx; int
0x180044c98  lea     rdx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180044c9f  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x180044ca4  jmp     loc_180044C19
0x180044ca9  mov     eax, [rbx+38h]
0x180044cac  test    eax, eax
0x180044cae  jg      short loc_180044CB5
0x180044cb0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044cb5  lock xadd [rbx+38h], r14d
0x180044cbb  cmp     r14d, 1
0x180044cbf  jnz     short loc_180044CF4
0x180044cc1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss> `wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss>::GetImpl(void)'::`2'::impl
0x180044cc8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInCombaseAndRpcss>::__private_IsEnabled(void)
0x180044ccd  test    al, al
0x180044ccf  jz      short loc_180044CDD
0x180044cd1  mov     ecx, r12d
0x180044cd4  xor     eax, eax
0x180044cd6  lock cmpxchg [rbx+3Ch], ecx
0x180044cdb  jmp     short loc_180044CE0
0x180044cdd  mov     eax, [rbx+3Ch]
0x180044ce0  test    eax, eax
0x180044ce2  jz      short loc_180044CF4
0x180044ce4  mov     rcx, [rbx+30h]; hEvent
0x180044ce8  call    cs:__imp_SetEvent
0x180044cef  nop     dword ptr [rax+rax+00h]
0x180044cf4  mov     r8, [rbp+60h+lpMem]; lpMem
0x180044cf8  lea     rax, ??_7CAcidPackageSidCpidKey@@6B@; const CAcidPackageSidCpidKey::`vftable'
0x180044cff  mov     [rbp+60h+var_80], rax
0x180044d03  mov     [rbp+60h+lpMem], r12
0x180044d07  test    r8, r8
0x180044d0a  jz      short loc_180044D21
0x180044d0c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180044d13  xor     edx, edx; dwFlags
0x180044d15  call    cs:__imp_HeapFree
0x180044d1c  nop     dword ptr [rax+rax+00h]
0x180044d21  mov     rcx, [rbp+60h+newString+8]; string
0x180044d25  call    cs:__imp_WindowsDeleteString
0x180044d2c  nop     dword ptr [rax+rax+00h]
0x180044d31  mov     rcx, [rbp+60h+newString]; string
0x180044d35  mov     [rbp+60h+newString+8], r12
0x180044d39  call    cs:__imp_WindowsDeleteString
0x180044d40  nop     dword ptr [rax+rax+00h]
0x180044d45  mov     rax, rdi
0x180044d48  mov     rcx, [rbp+60h+var_50]
0x180044d4c  xor     rcx, rsp; StackCookie
0x180044d4f  call    __security_check_cookie
0x180044d54  add     rsp, 128h
0x180044d5b  pop     r15
0x180044d5d  pop     r14
0x180044d5f  pop     r13
0x180044d61  pop     r12
0x180044d63  pop     rdi
0x180044d64  pop     rsi
0x180044d65  pop     rbx
0x180044d66  pop     rbp
0x180044d67  retn
```
