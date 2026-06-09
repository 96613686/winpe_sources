# _lambda_e13261a407275c01b6d253e9ee404d5b_::operator()

- ea: `0x1800edfb4`
- end: `0x1800ee15a`
- name: `_lambda_e13261a407275c01b6d253e9ee404d5b_::operator()`
- size: `422`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002f7b0`
- `0x180069940`

## callees

- `0x18001ec28`
- `0x18002ba28`
- `0x18002f8cc`
- `0x18004105c`
- `0x1800410d4`
- `0x18006f610`
- `0x1800edfb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee0a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee0a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ee0bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ee0bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ee072`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ee072`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800ee011`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800ee011`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800ee03a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800ee08e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800ee03a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800ee08e`

## string_xrefs

- `0x1800edfe5`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x1800ee0e9`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x1800ee108`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x1800ee127`: `onecore\com\combase\rpcss\olescm\launchk.cxx`

## pseudocode

```c
__int64 __fastcall lambda_e13261a407275c01b6d253e9ee404d5b_::operator()(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  SC_HANDLE v4; // rax
  const char *v5; // r9
  SC_HANDLE v6; // rbx
  __int64 v7; // rdx
  DWORD LastError; // edi
  int i; // esi
  struct _QUERY_SERVICE_CONFIGW *v10; // rax
  struct _QUERY_SERVICE_CONFIGW *v11; // r14
  unsigned int v13; // eax
  unsigned int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  DWORD pcbBytesNeeded; // [rsp+58h] [rbp+38h] BYREF
  HANDLE Token; // [rsp+60h] [rbp+40h] BYREF
  SC_HANDLE v18; // [rsp+68h] [rbp+48h] BYREF

  Token = 0;
  v2 = SuspendImpersonate(&Token);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8FE,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launchk.cxx",
      (const char *)(unsigned int)v2,
      savedregs);
    return v3;
  }
  v4 = OpenServiceW(g_hServiceController, **(LPCWSTR **)a1, 0x80000000);
  v18 = v4;
  v6 = v4;
  if ( v4 )
  {
    pcbBytesNeeded = 0;
    QueryServiceConfigW(v4, 0, 0, &pcbBytesNeeded);
    if ( GetLastError() == 122 )
    {
      LastError = 122;
      for ( i = 3; i; --i )
      {
        v10 = (struct _QUERY_SERVICE_CONFIGW *)HeapAlloc(g_hHeap, 0, pcbBytesNeeded);
        v11 = v10;
        if ( !v10 )
        {
          v3 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x90F,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launchk.cxx",
            (const char *)0x8007000ELL,
            savedregs);
          goto LABEL_21;
        }
        if ( QueryServiceConfigW(v6, v10, pcbBytesNeeded, &pcbBytesNeeded) )
        {
          LastError = 0;
          ***(_DWORD ***)(a1 + 8) = v11->dwServiceType;
        }
        else
        {
          LastError = GetLastError();
        }
        HeapFree(g_hHeap, 0, v11);
        if ( LastError != 122 )
        {
          if ( !LastError )
          {
            wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
            ResumeImpersonate(Token);
            return 0;
          }
          break;
        }
      }
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x91C,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launchk.cxx",
              (const char *)LastError,
              savedregs);
      goto LABEL_20;
    }
    v7 = 2310;
  }
  else
  {
    v7 = 2306;
  }
  v13 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)v7,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launchk.cxx",
          v5);
LABEL_20:
  v3 = v13;
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
  ResumeImpersonate(Token);
  return v3;
}

```

## disassembly

```asm
0x1800edfb4  mov     [rsp-28h+arg_0], rbx
0x1800edfb9  push    rbp
0x1800edfba  push    rsi
0x1800edfbb  push    rdi
0x1800edfbc  push    r14
0x1800edfbe  push    r15; unsigned int
0x1800edfc0  mov     rbp, rsp
0x1800edfc3  sub     rsp, 20h
0x1800edfc7  mov     r15, rcx
0x1800edfca  mov     [rbp+Token], 0
0x1800edfd2  lea     rcx, [rbp+Token]; TokenHandle
0x1800edfd6  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x1800edfdb  mov     ebx, eax
0x1800edfdd  test    eax, eax
0x1800edfdf  jns     short loc_1800EDFFE
0x1800edfe1  mov     rcx, [rbp+28h]; this
0x1800edfe5  lea     r8, aOnecoreComComb_70; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x1800edfec  mov     r9d, eax; char *
0x1800edfef  mov     edx, 8FEh; void *
0x1800edff4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800edff9  jmp     loc_1800EE147
0x1800edffe  mov     rdx, [r15]
0x1800ee001  mov     r8d, 80000000h; dwDesiredAccess
0x1800ee007  mov     rcx, cs:?g_hServiceController@@3PEAUSC_HANDLE__@@EA; hSCManager
0x1800ee00e  mov     rdx, [rdx]; lpServiceName
0x1800ee011  call    cs:__imp_OpenServiceW
0x1800ee017  mov     [rbp+arg_18], rax
0x1800ee01b  mov     rbx, rax
0x1800ee01e  test    rax, rax
0x1800ee021  jz      loc_1800EE11E
0x1800ee027  lea     r9, [rbp+pcbBytesNeeded]; pcbBytesNeeded
0x1800ee02b  mov     [rbp+pcbBytesNeeded], 0
0x1800ee032  xor     r8d, r8d; cbBufSize
0x1800ee035  xor     edx, edx; lpServiceConfig
0x1800ee037  mov     rcx, rax; hService
0x1800ee03a  call    cs:__imp_QueryServiceConfigW
0x1800ee040  call    cs:__imp_GetLastError
0x1800ee046  cmp     eax, 7Ah ; 'z'
0x1800ee049  jz      short loc_1800EE055
0x1800ee04b  mov     edx, 906h
0x1800ee050  jmp     loc_1800EE123
0x1800ee055  mov     edi, 7Ah ; 'z'
0x1800ee05a  lea     esi, [rdi-77h]
0x1800ee05d  test    esi, esi
0x1800ee05f  jz      loc_1800EE104
0x1800ee065  mov     r8d, [rbp+pcbBytesNeeded]; dwBytes
0x1800ee069  xor     edx, edx; dwFlags
0x1800ee06b  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ee072  call    cs:__imp_HeapAlloc
0x1800ee078  mov     r14, rax
0x1800ee07b  test    rax, rax
0x1800ee07e  jz      short loc_1800EE0E5
0x1800ee080  mov     r8d, [rbp+pcbBytesNeeded]; cbBufSize
0x1800ee084  lea     r9, [rbp+pcbBytesNeeded]; pcbBytesNeeded
0x1800ee088  mov     rdx, rax; lpServiceConfig
0x1800ee08b  mov     rcx, rbx; hService
0x1800ee08e  call    cs:__imp_QueryServiceConfigW
0x1800ee094  test    eax, eax
0x1800ee096  jz      short loc_1800EE0A8
0x1800ee098  mov     rax, [r15+8]
0x1800ee09c  xor     edi, edi
0x1800ee09e  mov     rcx, [rax]
0x1800ee0a1  mov     eax, [r14]
0x1800ee0a4  mov     [rcx], eax
0x1800ee0a6  jmp     short loc_1800EE0B0
0x1800ee0a8  call    cs:__imp_GetLastError
0x1800ee0ae  mov     edi, eax
0x1800ee0b0  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ee0b7  mov     r8, r14; lpMem
0x1800ee0ba  xor     edx, edx; dwFlags
0x1800ee0bc  call    cs:__imp_HeapFree
0x1800ee0c2  cmp     edi, 7Ah ; 'z'
0x1800ee0c5  jnz     short loc_1800EE0CB
0x1800ee0c7  dec     esi
0x1800ee0c9  jmp     short loc_1800EE05D
0x1800ee0cb  test    edi, edi
0x1800ee0cd  jnz     short loc_1800EE104
0x1800ee0cf  lea     rcx, [rbp+arg_18]
0x1800ee0d3  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800ee0d8  mov     rcx, [rbp+Token]; Token
0x1800ee0dc  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x1800ee0e1  xor     eax, eax
0x1800ee0e3  jmp     short loc_1800EE149
0x1800ee0e5  mov     rcx, [rbp+28h]; this
0x1800ee0e9  lea     r8, aOnecoreComComb_70; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x1800ee0f0  mov     ebx, 8007000Eh
0x1800ee0f5  mov     edx, 90Fh; void *
0x1800ee0fa  mov     r9d, ebx; char *
0x1800ee0fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ee102  jmp     short loc_1800EE135
0x1800ee104  mov     rcx, [rbp+28h]; this
0x1800ee108  lea     r8, aOnecoreComComb_70; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x1800ee10f  mov     r9d, edi; char *
0x1800ee112  mov     edx, 91Ch; void *
0x1800ee117  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ee11c  jmp     short loc_1800EE133
0x1800ee11e  mov     edx, 902h; void *
0x1800ee123  mov     rcx, [rbp+28h]; this
0x1800ee127  lea     r8, aOnecoreComComb_70; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x1800ee12e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ee133  mov     ebx, eax
0x1800ee135  lea     rcx, [rbp+arg_18]
0x1800ee139  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800ee13e  mov     rcx, [rbp+Token]; Token
0x1800ee142  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x1800ee147  mov     eax, ebx
0x1800ee149  mov     rbx, [rsp+20h+arg_0]
0x1800ee14e  add     rsp, 20h
0x1800ee152  pop     r15
0x1800ee154  pop     r14
0x1800ee156  pop     rdi
0x1800ee157  pop     rsi
0x1800ee158  pop     rbp
0x1800ee159  retn
```
