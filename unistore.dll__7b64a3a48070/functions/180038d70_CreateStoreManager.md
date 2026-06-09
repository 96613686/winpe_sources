# CreateStoreManager

- ea: `0x180038d70`
- end: `0x180038fc4`
- name: `CreateStoreManager`
- size: `596`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180036b70`
- `0x18007b910`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x18002995c`
- `0x180038d70`
- `0x1800390c0`
- `0x180039688`
- `0x18003bf70`
- `0x18006b9b4`
- `0x18006baa4`
- `0x18006bd68`
- `0x18007007c`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038dc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038dc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038e26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038e8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038ec6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038e26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038e8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038ec6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f4a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038db9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038db9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180038e34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180038e34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038da0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038da0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180038dd4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180038dd4`
- `UserDataPlatformHelperUtil!GetQueryProcessHandle` at `0x180038e40`
- `UserDataPlatformHelperUtil!GetQueryProcessHandle` at `0x180038e40`

## string_xrefs

- `0x180038eac`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180038ef6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180038f2b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180038f80`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180038df0`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180038f59`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall CreateStoreManager(unsigned int a1, void **a2)
{
  __int64 v2; // rbx
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  const char *v7; // r9
  unsigned int LastError; // edi
  DWORD CurrentProcessId; // eax
  int QueryProcessHandle; // eax
  void *v11; // rdx
  int StoreManager; // eax
  unsigned int v13; // ebx
  int Instance; // eax
  struct IUnknown *v16[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  HANDLE hObject; // [rsp+80h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp+48h] BYREF

  v2 = -1;
  hObject = 0;
  v16[0] = (struct IUnknown *)-1LL;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) || GetLastError() == 1008 )
  {
    if ( SetThreadToken(0, 0) )
    {
      v2 = (__int64)TokenHandle;
      v16[0] = (struct IUnknown *)TokenHandle;
      goto LABEL_8;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1C6,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v7);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1C2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v6);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
  }
  if ( (LastError & 0x80000000) != 0 )
  {
    Log_UnistoreHREvent_0(
      LastError,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
      245);
    if ( hObject )
      CloseHandle(hObject);
    return LastError;
  }
LABEL_8:
  if ( hObject )
    CloseHandle(hObject);
  hObject = 0;
  CurrentProcessId = GetCurrentProcessId();
  QueryProcessHandle = GetQueryProcessHandle(CurrentProcessId, &hObject);
  LastError = QueryProcessHandle;
  if ( QueryProcessHandle < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)QueryProcessHandle,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
      247);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v16);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&hObject);
    return LastError;
  }
  if ( v2 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v2, v11);
  TokenHandle = 0;
  StoreManager = _CreateStoreManager(hObject, a1, (struct IUSStoreManager **)&TokenHandle);
  v13 = StoreManager;
  if ( StoreManager < 0 )
  {
    if ( (a1 & 1) == 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)StoreManager,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
        267);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&TokenHandle);
      goto LABEL_15;
    }
    v16[0] = 0;
    Instance = ATL::CComObject<CUSClient_ServerManager>::CreateInstance(v16);
    v13 = Instance;
    if ( Instance < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)Instance,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
        262);
      if ( TokenHandle )
        (*(void (__fastcall **)(void *))(*(_QWORD *)TokenHandle + 16LL))(TokenHandle);
      goto LABEL_15;
    }
    if ( TokenHandle != v16[0] )
      ATL::AtlComPtrAssign((struct IUnknown **)&TokenHandle, v16[0]);
  }
  v13 = 0;
  *a2 = TokenHandle;
LABEL_15:
  if ( hObject )
    CloseHandle(hObject);
  return v13;
}

```

## disassembly

```asm
0x180038d70  mov     [rsp-28h+arg_0], rbx
0x180038d75  push    rbp
0x180038d76  push    rsi
0x180038d77  push    rdi
0x180038d78  push    r12
0x180038d7a  push    r14
0x180038d7c  mov     rbp, rsp
0x180038d7f  sub     rsp, 40h
0x180038d83  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180038d87  mov     [rbp+hObject], 0
0x180038d8f  mov     [rbp+var_10], rbx
0x180038d93  mov     r14, rdx
0x180038d96  mov     esi, ecx
0x180038d98  mov     [rbp+TokenHandle], 0
0x180038da0  call    cs:__imp_GetCurrentThread
0x180038da6  lea     r12d, [rbx+2]
0x180038daa  mov     edx, 0F01FFh; DesiredAccess
0x180038daf  mov     r8d, r12d; OpenAsSelf
0x180038db2  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180038db6  mov     rcx, rax; ThreadHandle
0x180038db9  call    cs:__imp_OpenThreadToken
0x180038dbf  test    eax, eax
0x180038dc1  jnz     short loc_180038DD0
0x180038dc3  call    cs:__imp_GetLastError
0x180038dc9  cmp     eax, 3F0h
0x180038dce  jnz     short loc_180038DEC
0x180038dd0  xor     edx, edx; Token
0x180038dd2  xor     ecx, ecx; Thread
0x180038dd4  call    cs:__imp_SetThreadToken
0x180038dda  test    eax, eax
0x180038ddc  jz      loc_180038F55
0x180038de2  mov     rbx, [rbp+TokenHandle]
0x180038de6  mov     [rbp+var_10], rbx
0x180038dea  jmp     short loc_180038E1D
0x180038dec  mov     rcx, [rbp+28h]; this
0x180038df0  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180038df7  mov     edx, 1C2h; void *
0x180038dfc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038e01  mov     rcx, [rbp+TokenHandle]; hObject
0x180038e05  mov     edi, eax
0x180038e07  lea     rax, [rcx-1]
0x180038e0b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180038e0f  jbe     loc_180038F4A
0x180038e15  test    edi, edi
0x180038e17  js      loc_180038EA6
0x180038e1d  mov     rcx, [rbp+hObject]; hObject
0x180038e21  test    rcx, rcx
0x180038e24  jz      short loc_180038E2C
0x180038e26  call    cs:__imp_CloseHandle
0x180038e2c  mov     [rbp+hObject], 0
0x180038e34  call    cs:__imp_GetCurrentProcessId
0x180038e3a  mov     ecx, eax
0x180038e3c  lea     rdx, [rbp+hObject]
0x180038e40  call    cs:__imp_GetQueryProcessHandle
0x180038e46  mov     edi, eax
0x180038e48  test    eax, eax
0x180038e4a  js      loc_180038F7A
0x180038e50  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180038e54  jz      short loc_180038E5E
0x180038e56  mov     rcx, rbx; Token
0x180038e59  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180038e5e  mov     rcx, [rbp+hObject]; void *
0x180038e62  lea     r8, [rbp+TokenHandle]; struct IUSStoreManager **
0x180038e66  mov     edx, esi; unsigned int
0x180038e68  mov     [rbp+TokenHandle], 0
0x180038e70  call    ?_CreateStoreManager@@YAJPEAXKPEAPEAUIUSStoreManager@@@Z; _CreateStoreManager(void *,ulong,IUSStoreManager * *)
0x180038e75  mov     ebx, eax
0x180038e77  test    eax, eax
0x180038e79  js      short loc_180038ED0
0x180038e7b  mov     rax, [rbp+TokenHandle]
0x180038e7f  xor     ebx, ebx
0x180038e81  mov     [r14], rax
0x180038e84  mov     rcx, [rbp+hObject]; hObject
0x180038e88  test    rcx, rcx
0x180038e8b  jz      short loc_180038E93
0x180038e8d  call    cs:__imp_CloseHandle
0x180038e93  mov     eax, ebx
0x180038e95  mov     rbx, [rsp+40h+arg_0]
0x180038e9a  add     rsp, 40h
0x180038e9e  pop     r14
0x180038ea0  pop     r12
0x180038ea2  pop     rdi
0x180038ea3  pop     rsi
0x180038ea4  pop     rbp
0x180038ea5  retn
0x180038ea6  mov     r9d, 0F5h
0x180038eac  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180038eb3  mov     edx, r12d
0x180038eb6  mov     ecx, edi
0x180038eb8  call    Log_UnistoreHREvent_0
0x180038ebd  mov     rcx, [rbp+hObject]; hObject
0x180038ec1  test    rcx, rcx
0x180038ec4  jz      short loc_180038ECC
0x180038ec6  call    cs:__imp_CloseHandle
0x180038ecc  mov     eax, edi
0x180038ece  jmp     short loc_180038E95
0x180038ed0  test    r12b, sil
0x180038ed3  jz      short loc_180038F25
0x180038ed5  lea     rcx, [rbp+var_10]
0x180038ed9  mov     [rbp+var_10], 0
0x180038ee1  call    ?CreateInstance@?$CComObject@VCUSClient_ServerManager@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUSClient_ServerManager>::CreateInstance(ATL::CComObject<CUSClient_ServerManager> * *)
0x180038ee6  mov     ebx, eax
0x180038ee8  test    eax, eax
0x180038eea  jns     loc_180038FA8
0x180038ef0  mov     r9d, 106h
0x180038ef6  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180038efd  mov     edx, r12d
0x180038f00  mov     ecx, eax
0x180038f02  call    Log_UnistoreHREvent_0
0x180038f07  mov     rcx, [rbp+TokenHandle]
0x180038f0b  test    rcx, rcx
0x180038f0e  jz      loc_180038E84
0x180038f14  mov     rax, [rcx]
0x180038f17  mov     rax, [rax+10h]
0x180038f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f20  jmp     loc_180038E84
0x180038f25  mov     r9d, 10Bh
0x180038f2b  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180038f32  mov     edx, r12d
0x180038f35  mov     ecx, eax
0x180038f37  call    Log_UnistoreHREvent_0
0x180038f3c  lea     rcx, [rbp+TokenHandle]; void *
0x180038f40  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180038f45  jmp     loc_180038E84
0x180038f4a  call    cs:__imp_CloseHandle
0x180038f50  jmp     loc_180038E15
0x180038f55  mov     rcx, [rbp+28h]; this
0x180038f59  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180038f60  mov     edx, 1C6h; void *
0x180038f65  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038f6a  lea     rcx, [rbp+TokenHandle]
0x180038f6e  mov     edi, eax
0x180038f70  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180038f75  jmp     loc_180038E15
0x180038f7a  mov     r9d, 0F7h
0x180038f80  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180038f87  mov     edx, r12d
0x180038f8a  mov     ecx, edi
0x180038f8c  call    Log_UnistoreHREvent_0
0x180038f91  lea     rcx, [rbp+var_10]
0x180038f95  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180038f9a  lea     rcx, [rbp+hObject]
0x180038f9e  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180038fa3  jmp     loc_180038ECC
0x180038fa8  mov     rdx, [rbp+var_10]; struct IUnknown *
0x180038fac  cmp     [rbp+TokenHandle], rdx
0x180038fb0  jz      loc_180038E7B
0x180038fb6  lea     rcx, [rbp+TokenHandle]; struct IUnknown **
0x180038fba  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180038fbf  jmp     loc_180038E7B
```
