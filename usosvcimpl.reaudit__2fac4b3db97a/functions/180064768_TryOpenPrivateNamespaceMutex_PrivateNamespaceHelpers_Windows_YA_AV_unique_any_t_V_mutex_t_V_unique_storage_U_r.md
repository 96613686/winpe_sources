# ?TryOpenPrivateNamespaceMutex@PrivateNamespaceHelpers@Windows@@YA?AV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEB_WK_N@Z

- ea: `0x180064768`
- end: `0x1800648f4`
- name: `?TryOpenPrivateNamespaceMutex@PrivateNamespaceHelpers@Windows@@YA?AV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEB_WK_N@Z`
- size: `396`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180030c78`

## callees

- `0x1800081c0`
- `0x180008ea8`
- `0x1800112d0`
- `0x180011680`
- `0x180063f38`
- `0x1800640a4`
- `0x1800642b8`
- `0x18006448c`
- `0x180064768`
- `0x180064ba4`
- `0x1800dd930`
- `0x1800dddf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180064808`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180064808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006481e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006481e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006483f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006483f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006482a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006482a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064885`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064885`

## string_xrefs

- `0x1800648d7`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void **__fastcall Windows::PrivateNamespaceHelpers::TryOpenPrivateNamespaceMutex(void **a1)
{
  char v2; // r14
  __int64 v3; // rax
  wil::details *v4; // rcx
  HANDLE v5; // rsi
  void *v6; // rbx
  DWORD LastError; // r15d
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastErrorFailHr; // ebx
  HLOCAL hMem[2]; // [rsp+28h] [rbp-58h] BYREF
  void **v13; // [rsp+38h] [rbp-48h]
  _BYTE v14[32]; // [rsp+40h] [rbp-40h] BYREF
  __int128 v15; // [rsp+60h] [rbp-20h] BYREF
  __int64 v16; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v13 = a1;
  v15 = 0;
  v16 = 0;
  anonymous_namespace_::GetSids((__int64)&v15);
  *(_OWORD *)hMem = 0;
  anonymous_namespace_::SecurityDescriptorAndAcls::SecurityDescriptorAndAcls((struct _ACL **)hMem, (PSID **)&v15);
  anonymous_namespace_::CreateOrOpenPrivateNamespace((PSID **)&v15);
  *a1 = 0;
  v2 = 1;
  v3 = anonymous_namespace_::FullObjectName((__int64)v14, (__int64)L"\\UsoCoreworkerRunning");
  if ( *(_QWORD *)(v3 + 24) > 7u )
    v3 = *(_QWORD *)v3;
  v5 = OpenMutexW(0x1F0001u, 0, (LPCWSTR)v3);
  if ( v5 )
  {
    v6 = *a1;
    if ( *a1 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v8, v9);
      SetLastError(LastError);
    }
    *a1 = v5;
    LastErrorFailHr = 0;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v4);
  }
  std::wstring::~wstring(v14);
  if ( (int)(LastErrorFailHr + 0x80000000) < 0 || LastErrorFailHr == -2147024894 )
    v2 = 0;
  if ( v2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PrivateNamespaceHelpers.cpp",
      (const char *)LastErrorFailHr,
      1);
  if ( hMem[1] )
    LocalFree(hMem[1]);
  if ( hMem[0] )
    operator delete(hMem[0], (const struct std::nothrow_t *)8);
  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v15);
  return a1;
}

```

## disassembly

```asm
0x180064768  mov     [rsp-18h+arg_8], rbx
0x18006476d  mov     [rsp-18h+arg_10], rsi
0x180064772  mov     [rsp-18h+arg_18], rdi
0x180064777  push    rbp
0x180064778  push    r14
0x18006477a  push    r15
0x18006477c  mov     rbp, rsp
0x18006477f  sub     rsp, 80h
0x180064786  mov     rax, cs:__security_cookie
0x18006478d  xor     rax, rsp
0x180064790  mov     [rbp+var_8], rax
0x180064794  mov     rdi, rcx
0x180064797  mov     [rbp+var_48], rcx
0x18006479b  mov     [rbp+var_60], 0
0x1800647a2  xorps   xmm0, xmm0
0x1800647a5  xor     eax, eax
0x1800647a7  movups  [rbp+var_20], xmm0
0x1800647ab  mov     [rbp+var_10], rax
0x1800647af  lea     rcx, [rbp+var_20]
0x1800647b3  call    _anonymous_namespace___GetSids
0x1800647b8  nop
0x1800647b9  xorps   xmm0, xmm0
0x1800647bc  movups  xmmword ptr [rbp+hMem], xmm0
0x1800647c0  lea     rdx, [rbp+var_20]
0x1800647c4  lea     rcx, [rbp+hMem]
0x1800647c8  call    _anonymous_namespace___SecurityDescriptorAndAcls__SecurityDescriptorAndAcls
0x1800647cd  nop
0x1800647ce  lea     rcx, [rbp+var_20]
0x1800647d2  call    _anonymous_namespace___CreateOrOpenPrivateNamespace
0x1800647d7  xor     eax, eax
0x1800647d9  mov     [rdi], rax
0x1800647dc  lea     r14d, [rax+1]
0x1800647e0  mov     [rbp+var_60], r14d
0x1800647e4  lea     rdx, aUsocoreworkerr_0; "\\UsoCoreworkerRunning"
0x1800647eb  lea     rcx, [rbp+var_40]
0x1800647ef  call    _anonymous_namespace___FullObjectName
0x1800647f4  cmp     qword ptr [rax+18h], 7
0x1800647f9  jbe     short loc_1800647FE
0x1800647fb  mov     rax, [rax]
0x1800647fe  mov     r8, rax; lpName
0x180064801  xor     edx, edx; bInheritHandle
0x180064803  mov     ecx, 1F0001h; dwDesiredAccess
0x180064808  call    cs:__imp_OpenMutexW
0x18006480e  mov     rsi, rax
0x180064811  test    rax, rax
0x180064814  jz      short loc_18006484C
0x180064816  mov     rbx, [rdi]
0x180064819  test    rbx, rbx
0x18006481c  jz      short loc_180064845
0x18006481e  call    cs:__imp_GetLastError
0x180064824  mov     r15d, eax
0x180064827  mov     rcx, rbx; hObject
0x18006482a  call    cs:__imp_CloseHandle
0x180064830  mov     rcx, [rbp+18h]; this
0x180064834  test    eax, eax
0x180064836  jz      loc_1800648E9
0x18006483c  mov     ecx, r15d; dwErrCode
0x18006483f  call    cs:__imp_SetLastError
0x180064845  mov     [rdi], rsi
0x180064848  xor     ebx, ebx
0x18006484a  jmp     short loc_180064853
0x18006484c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180064851  mov     ebx, eax
0x180064853  lea     rcx, [rbp+var_40]; void *
0x180064857  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006485c  mov     ecx, 80000000h
0x180064861  lea     eax, [rbx+rcx]
0x180064864  test    ecx, eax
0x180064866  jnz     short loc_180064870
0x180064868  cmp     ebx, 80070002h
0x18006486e  jnz     short loc_180064873
0x180064870  xor     r14b, r14b
0x180064873  mov     rcx, [rbp+18h]; this
0x180064877  test    r14b, r14b
0x18006487a  jnz     short loc_1800648D4
0x18006487c  mov     rcx, [rbp+hMem+8]; hMem
0x180064880  test    rcx, rcx
0x180064883  jz      short loc_18006488B
0x180064885  call    cs:__imp_LocalFree
0x18006488b  mov     rcx, [rbp+hMem]; void *
0x18006488f  test    rcx, rcx
0x180064892  jz      short loc_18006489F
0x180064894  mov     edx, 8; struct std::nothrow_t *
0x180064899  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006489e  nop
0x18006489f  lea     rcx, [rbp+var_20]
0x1800648a3  call    ??1?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1800648a8  mov     rax, rdi
0x1800648ab  mov     rcx, [rbp+var_8]
0x1800648af  xor     rcx, rsp; StackCookie
0x1800648b2  call    __security_check_cookie
0x1800648b7  lea     r11, [rsp+80h+var_s0]
0x1800648bf  mov     rbx, [r11+28h]
0x1800648c3  mov     rsi, [r11+30h]
0x1800648c7  mov     rdi, [r11+38h]
0x1800648cb  mov     rsp, r11
0x1800648ce  pop     r15
0x1800648d0  pop     r14
0x1800648d2  pop     rbp
0x1800648d3  retn
0x1800648d4  mov     r9d, ebx; char *
0x1800648d7  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800648de  mov     edx, 0B2h; void *
0x1800648e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800648e9  mov     edx, 9D1h; void *
0x1800648ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
