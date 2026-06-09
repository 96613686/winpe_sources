# UpdateHandler::RemoteUHProcessHostWrapper::GetCommandLineArguments(tagUHUpdateHandler,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &)

- ea: `0x180036100`
- end: `0x180036233`
- name: `?GetCommandLineArguments@RemoteUHProcessHostWrapper@UpdateHandler@@MEAAJW4tagUHUpdateHandler@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(__int64, __int64, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001e8c`
- `0x180003950`
- `0x180009e38`
- `0x18000a448`
- `0x180036100`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800361f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800361f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036202`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036202`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003620a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003620a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800361ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800361ec`

## string_xrefs

- `0x18003613f`: `/ClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall UpdateHandler::RemoteUHProcessHostWrapper::GetCommandLineArguments(
        __int64 a1,
        __int64 a2,
        void **a3)
{
  int v4; // eax
  unsigned int v5; // edi
  unsigned int v6; // ebx
  void *v8; // rsi
  void *v9; // rbp
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  void *v12; // [rsp+40h] [rbp-148h] BYREF
  char v13[80]; // [rsp+50h] [rbp-138h] BYREF
  wchar_t Buffer[88]; // [rsp+A0h] [rbp-E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  Trace::GuidToString::GuidToString((Trace::GuidToString *)v13, (const struct _GUID *)(a1 + 8));
  v4 = StringCchPrintfW(Buffer, 0x53u, L"%ws %ws %d %ws {%ws}", L"/RemoteUHProcessHost");
  v5 = 0;
  v6 = v4;
  if ( v4 >= 0 )
  {
    v12 = 0;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
      &v12,
      Buffer,
      -1);
    v8 = v12;
    if ( v12 )
    {
      v9 = *a3;
      if ( *a3 )
      {
        LastError = GetLastError();
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v9);
        SetLastError(LastError);
      }
      *a3 = v8;
    }
    else
    {
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A8,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
        (const char *)0x8007000ELL,
        (int)L"/HandlerId");
    }
    return v5;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)(unsigned int)v4,
      (int)L"/HandlerId");
    return v6;
  }
}

```

## disassembly

```asm
0x180036100  push    rbx
0x180036102  push    rbp
0x180036103  push    rsi
0x180036104  push    rdi
0x180036105  push    r14
0x180036107  sub     rsp, 160h
0x18003610e  mov     rax, cs:__security_cookie
0x180036115  xor     rax, rsp
0x180036118  mov     [rsp+188h+var_38], rax
0x180036120  mov     ebx, edx
0x180036122  mov     r14, r8
0x180036125  lea     rdx, [rcx+8]; struct _GUID *
0x180036129  lea     rcx, [rsp+188h+var_138]; this
0x18003612e  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180036133  mov     [rsp+188h+var_150], rax
0x180036138  lea     r9, aRemoteuhproces_1; "/RemoteUHProcessHost"
0x18003613f  lea     rax, aClassid; "/ClassId"
0x180036146  mov     edx, 53h ; 'S'; unsigned __int64
0x18003614b  mov     [rsp+188h+var_158], rax
0x180036150  lea     r8, aWsWsDWsWs; "%ws %ws %d %ws {%ws}"
0x180036157  lea     rax, aHandlerid; "/HandlerId"
0x18003615e  mov     [rsp+188h+var_160], ebx
0x180036162  lea     rcx, [rsp+188h+Buffer]; Buffer
0x18003616a  mov     qword ptr [rsp+188h+var_168], rax; int
0x18003616f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180036174  xor     edi, edi
0x180036176  mov     ebx, eax
0x180036178  test    eax, eax
0x18003617a  jns     short loc_18003619C
0x18003617c  mov     rcx, [rsp+188h]; this
0x180036184  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003618b  mov     r9d, eax; char *
0x18003618e  mov     edx, 1A5h; void *
0x180036193  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036198  mov     eax, ebx
0x18003619a  jmp     short loc_180036215
0x18003619c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800361a0  mov     [rsp+188h+var_148], rdi
0x1800361a5  lea     rdx, [rsp+188h+Buffer]
0x1800361ad  lea     rcx, [rsp+188h+var_148]
0x1800361b2  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x1800361b7  mov     rsi, [rsp+188h+var_148]
0x1800361bc  test    rsi, rsi
0x1800361bf  jnz     short loc_1800361E4
0x1800361c1  mov     rcx, [rsp+188h]; this
0x1800361c9  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800361d0  mov     edi, 8007000Eh
0x1800361d5  mov     edx, 1A8h; void *
0x1800361da  mov     r9d, edi; char *
0x1800361dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800361e2  jmp     short loc_180036213
0x1800361e4  mov     rbp, [r14]
0x1800361e7  test    rbp, rbp
0x1800361ea  jz      short loc_180036210
0x1800361ec  call    cs:__imp_GetLastError
0x1800361f2  mov     ebx, eax
0x1800361f4  call    cs:__imp_GetProcessHeap
0x1800361fa  mov     r8, rbp; lpMem
0x1800361fd  xor     edx, edx; dwFlags
0x1800361ff  mov     rcx, rax; hHeap
0x180036202  call    cs:__imp_HeapFree
0x180036208  mov     ecx, ebx; dwErrCode
0x18003620a  call    cs:__imp_SetLastError
0x180036210  mov     [r14], rsi
0x180036213  mov     eax, edi
0x180036215  mov     rcx, [rsp+188h+var_38]
0x18003621d  xor     rcx, rsp; StackCookie
0x180036220  call    __security_check_cookie
0x180036225  add     rsp, 160h
0x18003622c  pop     r14
0x18003622e  pop     rdi
0x18003622f  pop     rsi
0x180036230  pop     rbp
0x180036231  pop     rbx
0x180036232  retn
```
