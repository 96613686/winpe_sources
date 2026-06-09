# Windows::Internal::Security::Authentication::TokenBroker::GetTokenBindingPublicKeyIdBytes(Windows::Security::Authentication::Web::TokenBindingKeyType,Windows::Foundation::IUriRuntimeClass *,Windows::Security::Authentication::Web::TokenBindingKeyType *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,ulong &)

- ea: `0x18003420c`
- end: `0x1800344b1`
- name: `?GetTokenBindingPublicKeyIdBytes@TokenBroker@Authentication@Security@Internal@Windows@@YAJW4TokenBindingKeyType@Web@235@PEAUIUriRuntimeClass@Foundation@5@PEAW467235@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAK@Z`
- size: `677`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034124`

## callees

- `0x18000bd40`
- `0x18001a510`
- `0x18003420c`
- `0x180045a04`
- `0x180055418`
- `0x180055498`
- `0x180091975`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800342da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800343bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034431`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034489`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800342da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800343bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034431`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034489`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800342cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800343ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034423`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003447b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800342cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800343ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034423`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003447b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800343f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800343f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800342fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003432c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800342fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003432c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800342bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003439f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034413`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003446c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800342bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003439f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034413`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003446c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800342a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800342a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800343da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800343da`
- `TOKENBINDING!TokenBindingGenerateIDForUri` at `0x18003433b`
- `TOKENBINDING!TokenBindingGenerateIDForUri` at `0x18003433b`

## string_xrefs

- `0x18003428f`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x18003434e`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::GetTokenBindingPublicKeyIdBytes(
        int a1,
        __int64 a2,
        _DWORD *a3,
        __int64 a4,
        _DWORD *a5)
{
  unsigned int v7; // edi
  int v8; // ecx
  int v9; // eax
  unsigned int v10; // ebx
  void *v11; // rbx
  HANDLE v12; // rax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  PCWSTR StringRawBuffer; // rax
  int v17; // eax
  unsigned int v18; // edi
  void *v19; // rbx
  unsigned int *v20; // rbx
  _BYTE *v21; // rax
  HANDLE v22; // rax
  HLOCAL v23; // rax
  signed int LastError; // eax
  void *v25; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v27; // rax
  int v29; // [rsp+20h] [rbp-30h]
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  void *v31; // [rsp+38h] [rbp-18h] BYREF
  void *p_lpMem; // [rsp+40h] [rbp-10h] BYREF
  char v33; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v35; // [rsp+70h] [rbp+20h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp+28h] BYREF

  v31 = 0;
  v7 = -1;
  lpMem = 0;
  p_lpMem = &lpMem;
  v33 = 1;
  if ( a1 )
  {
    v8 = a1 - 1;
    if ( v8 )
    {
      if ( v8 == 1 )
        v7 = 255;
    }
    else
    {
      v7 = 2;
    }
  }
  else
  {
    v7 = 0;
  }
  string = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 64LL))(a2, &string);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)(unsigned int)v9,
      v29);
LABEL_34:
    if ( string )
      WindowsDeleteString(string);
    v25 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v25);
    }
    goto LABEL_43;
  }
  if ( WindowsIsStringEmpty(string) )
  {
    if ( string )
      WindowsDeleteString(string);
    v11 = lpMem;
    if ( lpMem )
    {
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v11);
    }
    v10 = -2147024809;
    goto LABEL_43;
  }
  if ( (unsigned int)dword_180175000 > 5 )
  {
    p_lpMem = (void *)WindowsGetStringRawBuffer(string, 0);
    v35 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v13,
      (unsigned int)byte_1801454AD,
      v14,
      v15,
      (__int64)&v35,
      (__int64)&p_lpMem);
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v17 = TokenBindingGenerateIDForUri(v7, StringRawBuffer, &lpMem);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C3,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)(unsigned int)v17,
      v29);
    if ( string )
      WindowsDeleteString(string);
    v19 = lpMem;
LABEL_40:
    if ( v19 )
    {
      v27 = GetProcessHeap();
      HeapFree(v27, 0, v19);
    }
    v10 = v18;
    goto LABEL_43;
  }
  v20 = (unsigned int *)lpMem;
  v21 = (_BYTE *)*((_QWORD *)lpMem + 1);
  if ( !*v21 )
  {
    *a3 = 0;
LABEL_31:
    v23 = LocalAlloc(0x40u, v20[1]);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &v31,
      v23);
    if ( !v31 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_34;
    }
    memcpy_0(v31, *((const void **)lpMem + 1), *((unsigned int *)lpMem + 1));
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::swap(
      &v31,
      a4);
    v19 = lpMem;
    *a5 = *((_DWORD *)lpMem + 1);
    if ( string )
    {
      WindowsDeleteString(string);
      v19 = lpMem;
    }
    goto LABEL_40;
  }
  if ( *v21 != 1 )
  {
    if ( *v21 == 2 )
      *a3 = 1;
    goto LABEL_31;
  }
  if ( string )
  {
    WindowsDeleteString(string);
    v20 = (unsigned int *)lpMem;
  }
  if ( v20 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v20);
  }
  v10 = 50;
LABEL_43:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v31);
  return v10;
}

```

## disassembly

```asm
0x18003420c  mov     [rsp-18h+arg_10], rbx
0x180034211  mov     [rsp-18h+arg_18], rsi
0x180034216  push    rbp
0x180034217  push    rdi
0x180034218  push    r14
0x18003421a  mov     rbp, rsp
0x18003421d  sub     rsp, 50h
0x180034221  mov     r14, r9
0x180034224  mov     rsi, r8
0x180034227  mov     r8, rdx
0x18003422a  mov     [rbp+var_18], 0
0x180034232  or      edi, 0FFFFFFFFh
0x180034235  mov     [rbp+lpMem], 0
0x18003423d  lea     rax, [rbp+lpMem]
0x180034241  mov     [rbp+var_10], rax
0x180034245  mov     [rbp+var_8], 1
0x180034249  test    ecx, ecx
0x18003424b  jz      short loc_180034265
0x18003424d  sub     ecx, 1
0x180034250  jz      short loc_18003425E
0x180034252  cmp     ecx, 1
0x180034255  jnz     short loc_180034267
0x180034257  mov     edi, 0FFh
0x18003425c  jmp     short loc_180034267
0x18003425e  mov     edi, 2
0x180034263  jmp     short loc_180034267
0x180034265  xor     edi, edi
0x180034267  mov     [rbp+string], 0
0x18003426f  mov     rax, [rdx]
0x180034272  lea     rdx, [rbp+string]
0x180034276  mov     rcx, r8
0x180034279  mov     rax, [rax+40h]
0x18003427d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034282  mov     ebx, eax
0x180034284  test    eax, eax
0x180034286  jns     short loc_1800342A5
0x180034288  mov     rcx, [rbp+18h]; this
0x18003428c  mov     r9d, eax; char *
0x18003428f  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180034296  mov     edx, 1B0h; void *
0x18003429b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800342a0  jmp     loc_18003440A
0x1800342a5  mov     rcx, [rbp+string]; string
0x1800342a9  call    cs:__imp_WindowsIsStringEmpty
0x1800342af  test    eax, eax
0x1800342b1  jz      short loc_1800342EA
0x1800342b3  mov     rcx, [rbp+string]; string
0x1800342b7  test    rcx, rcx
0x1800342ba  jz      short loc_1800342C3
0x1800342bc  call    cs:__imp_WindowsDeleteString
0x1800342c2  nop
0x1800342c3  mov     rbx, [rbp+lpMem]
0x1800342c7  test    rbx, rbx
0x1800342ca  jz      short loc_1800342E0
0x1800342cc  call    cs:__imp_GetProcessHeap
0x1800342d2  mov     r8, rbx; lpMem
0x1800342d5  xor     edx, edx; dwFlags
0x1800342d7  mov     rcx, rax; hHeap
0x1800342da  call    cs:__imp_HeapFree
0x1800342e0  mov     ebx, 80070057h
0x1800342e5  jmp     loc_180034491
0x1800342ea  mov     eax, cs:dword_180175000
0x1800342f0  cmp     eax, 5
0x1800342f3  jbe     short loc_180034326
0x1800342f5  xor     edx, edx; length
0x1800342f7  mov     rcx, [rbp+string]; string
0x1800342fb  call    cs:__imp_WindowsGetStringRawBuffer
0x180034301  mov     [rbp+var_10], rax
0x180034305  mov     [rbp+arg_0], edi
0x180034308  lea     rax, [rbp+var_10]
0x18003430c  mov     [rsp+50h+var_28], rax
0x180034311  lea     rax, [rbp+arg_0]
0x180034315  mov     qword ptr [rsp+50h+var_30], rax; int
0x18003431a  lea     rdx, byte_1801454AD
0x180034321  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180034326  xor     edx, edx; length
0x180034328  mov     rcx, [rbp+string]; string
0x18003432c  call    cs:__imp_WindowsGetStringRawBuffer
0x180034332  lea     r8, [rbp+lpMem]
0x180034336  mov     rdx, rax
0x180034339  mov     ecx, edi
0x18003433b  call    cs:__imp_TokenBindingGenerateIDForUri
0x180034341  mov     edi, eax
0x180034343  test    eax, eax
0x180034345  jns     short loc_180034379
0x180034347  mov     rcx, [rbp+18h]; this
0x18003434b  mov     r9d, eax; char *
0x18003434e  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180034355  mov     edx, 1C3h; void *
0x18003435a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003435f  nop
0x180034360  mov     rcx, [rbp+string]; string
0x180034364  test    rcx, rcx
0x180034367  jz      short loc_180034370
0x180034369  call    cs:__imp_WindowsDeleteString
0x18003436f  nop
0x180034370  mov     rbx, [rbp+lpMem]
0x180034374  jmp     loc_180034476
0x180034379  mov     rbx, [rbp+lpMem]
0x18003437d  mov     rax, [rbx+8]
0x180034381  movzx   ecx, byte ptr [rax]
0x180034384  test    ecx, ecx
0x180034386  jz      short loc_1800343CC
0x180034388  sub     ecx, 1
0x18003438b  jz      short loc_180034396
0x18003438d  cmp     ecx, 1
0x180034390  jnz     short loc_1800343D2
0x180034392  mov     [rsi], ecx
0x180034394  jmp     short loc_1800343D2
0x180034396  mov     rcx, [rbp+string]; string
0x18003439a  test    rcx, rcx
0x18003439d  jz      short loc_1800343A9
0x18003439f  call    cs:__imp_WindowsDeleteString
0x1800343a5  mov     rbx, [rbp+lpMem]
0x1800343a9  test    rbx, rbx
0x1800343ac  jz      short loc_1800343C2
0x1800343ae  call    cs:__imp_GetProcessHeap
0x1800343b4  mov     r8, rbx; lpMem
0x1800343b7  xor     edx, edx; dwFlags
0x1800343b9  mov     rcx, rax; hHeap
0x1800343bc  call    cs:__imp_HeapFree
0x1800343c2  mov     ebx, 32h ; '2'
0x1800343c7  jmp     loc_180034491
0x1800343cc  mov     dword ptr [rsi], 0
0x1800343d2  mov     edx, [rbx+4]; uBytes
0x1800343d5  mov     ecx, 40h ; '@'; uFlags
0x1800343da  call    cs:__imp_LocalAlloc
0x1800343e0  mov     rdx, rax
0x1800343e3  lea     rcx, [rbp+var_18]
0x1800343e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800343ec  mov     rcx, [rbp+var_18]; void *
0x1800343f0  test    rcx, rcx
0x1800343f3  jnz     short loc_180034439
0x1800343f5  call    cs:__imp_GetLastError
0x1800343fb  mov     ebx, eax
0x1800343fd  test    eax, eax
0x1800343ff  jle     short loc_18003440A
0x180034401  movzx   ebx, ax
0x180034404  or      ebx, 80070000h
0x18003440a  mov     rcx, [rbp+string]; string
0x18003440e  test    rcx, rcx
0x180034411  jz      short loc_18003441A
0x180034413  call    cs:__imp_WindowsDeleteString
0x180034419  nop
0x18003441a  mov     rdi, [rbp+lpMem]
0x18003441e  test    rdi, rdi
0x180034421  jz      short loc_180034491
0x180034423  call    cs:__imp_GetProcessHeap
0x180034429  mov     r8, rdi; lpMem
0x18003442c  xor     edx, edx; dwFlags
0x18003442e  mov     rcx, rax; hHeap
0x180034431  call    cs:__imp_HeapFree
0x180034437  jmp     short loc_180034491
0x180034439  mov     rdx, [rbp+lpMem]
0x18003443d  mov     r8d, [rdx+4]; Size
0x180034441  mov     rdx, [rdx+8]; Src
0x180034445  call    memcpy_0
0x18003444a  mov     rdx, r14
0x18003444d  lea     rcx, [rbp+var_18]
0x180034451  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x180034456  mov     rbx, [rbp+lpMem]
0x18003445a  mov     ecx, [rbx+4]
0x18003445d  mov     rax, [rbp+arg_20]
0x180034461  mov     [rax], ecx
0x180034463  mov     rcx, [rbp+string]; string
0x180034467  test    rcx, rcx
0x18003446a  jz      short loc_180034476
0x18003446c  call    cs:__imp_WindowsDeleteString
0x180034472  mov     rbx, [rbp+lpMem]
0x180034476  test    rbx, rbx
0x180034479  jz      short loc_18003448F
0x18003447b  call    cs:__imp_GetProcessHeap
0x180034481  mov     r8, rbx; lpMem
0x180034484  xor     edx, edx; dwFlags
0x180034486  mov     rcx, rax; hHeap
0x180034489  call    cs:__imp_HeapFree
0x18003448f  mov     ebx, edi
0x180034491  lea     rcx, [rbp+var_18]
0x180034495  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003449a  mov     eax, ebx
0x18003449c  lea     r11, [rsp+50h+var_s0]
0x1800344a1  mov     rbx, [r11+30h]
0x1800344a5  mov     rsi, [r11+38h]
0x1800344a9  mov     rsp, r11
0x1800344ac  pop     r14
0x1800344ae  pop     rdi
0x1800344af  pop     rbp
0x1800344b0  retn
```
