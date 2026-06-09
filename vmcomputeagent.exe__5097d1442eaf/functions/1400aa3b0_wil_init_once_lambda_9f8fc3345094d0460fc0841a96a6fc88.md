# wil::init_once__lambda_9f8fc3345094d0460fc0841a96a6fc88___

- ea: `0x1400aa3b0`
- end: `0x1400aa520`
- name: `wil::init_once__lambda_9f8fc3345094d0460fc0841a96a6fc88___`
- size: `368`
- prototype: `__int64 __fastcall(LPINIT_ONCE lpInitOnce)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400aa790`

## callees

- `0x140005360`
- `0x140009f8c`
- `0x14000ddac`
- `0x14000ea44`
- `0x14000ea60`
- `0x14004fc5c`
- `0x1400aa3b0`
- `0x1400e6a64`
- `0x1400e6b98`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1400aa3e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1400aa3e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400aa497`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400aa497`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400aa43b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400aa43b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400aa480`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400aa480`

## string_xrefs

- `0x1400aa4bb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400aa4f9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400aa4cd`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x1400aa4e2`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\processmanagement.cpp`
- `0x1400aa50e`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\processmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall wil::init_once__lambda_9f8fc3345094d0460fc0841a96a6fc88___(LPINIT_ONCE lpInitOnce, _QWORD *a2)
{
  const char *v4; // r9
  int ServiceStartEvent; // eax
  DWORD v6; // eax
  const char *v7; // r9
  __int64 v8; // rax
  int ServiceBinding; // eax
  const char *v10; // r9
  HANDLE hHandle[2]; // [rsp+20h] [rbp-38h] BYREF
  int v13; // [rsp+30h] [rbp-28h]
  WINBOOL fPending; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  fPending = 0;
  if ( !__std_init_once_begin_initialize(lpInitOnce, 0, &fPending, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3BC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      v4);
  if ( !fPending )
    return 0;
  hHandle[1] = lpInitOnce;
  v13 = 4;
  hHandle[0] = 0;
  ServiceStartEvent = ContainerGetServiceStartEvent(0, hHandle);
  if ( ServiceStartEvent < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\processmanagement.cpp",
      (const char *)(unsigned int)ServiceStartEvent,
      (int)hHandle[0]);
  v6 = WaitForSingleObjectEx(hHandle[0], 0x1388u, 0);
  if ( v6 != 258 && v6 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB0F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v7);
  v8 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(*a2 + 24LL);
  ServiceBinding = ContainerGetServiceBinding(0, v8);
  if ( ServiceBinding < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\processmanagement.cpp",
      (const char *)(unsigned int)ServiceBinding,
      (int)hHandle[0]);
  if ( hHandle[0] )
  {
    if ( !CloseHandle(hHandle[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
  }
  InitOnceComplete(lpInitOnce, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x1400aa3b0  mov     [rsp+arg_8], rsi
0x1400aa3b5  push    rdi
0x1400aa3b6  sub     rsp, 50h
0x1400aa3ba  mov     rax, cs:__security_cookie
0x1400aa3c1  xor     rax, rsp
0x1400aa3c4  mov     [rsp+58h+var_18], rax
0x1400aa3c9  mov     rdi, rdx
0x1400aa3cc  mov     rsi, rcx
0x1400aa3cf  mov     [rsp+58h+fPending], 0
0x1400aa3d7  xor     r9d, r9d; lpContext
0x1400aa3da  lea     r8, [rsp+58h+fPending]; fPending
0x1400aa3df  xor     edx, edx; dwFlags
0x1400aa3e1  call    cs:__imp___std_init_once_begin_initialize
0x1400aa3e7  mov     rcx, [rsp+58h]; this
0x1400aa3ec  test    eax, eax
0x1400aa3ee  jz      loc_1400AA4CD
0x1400aa3f4  cmp     [rsp+58h+fPending], 0
0x1400aa3f9  jz      loc_1400AA4A1
0x1400aa3ff  mov     [rsp+58h+var_30], rsi
0x1400aa404  mov     [rsp+58h+var_28], 4
0x1400aa40c  mov     [rsp+58h+hHandle], 0; int
0x1400aa415  lea     rdx, [rsp+58h+hHandle]
0x1400aa41a  xor     ecx, ecx
0x1400aa41c  call    ContainerGetServiceStartEvent
0x1400aa421  mov     rcx, [rsp+58h]; this
0x1400aa426  test    eax, eax
0x1400aa428  js      loc_1400AA4DF
0x1400aa42e  xor     r8d, r8d; bAlertable
0x1400aa431  mov     edx, 1388h; dwMilliseconds
0x1400aa436  mov     rcx, [rsp+58h+hHandle]; hHandle
0x1400aa43b  call    cs:__imp_WaitForSingleObjectEx
0x1400aa441  cmp     eax, 102h
0x1400aa446  jz      short loc_1400AA450
0x1400aa448  test    eax, eax
0x1400aa44a  jnz     loc_1400AA4F4
0x1400aa450  mov     rcx, [rdi]
0x1400aa453  add     rcx, 18h
0x1400aa457  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(void)
0x1400aa45c  mov     rdx, rax
0x1400aa45f  xor     ecx, ecx
0x1400aa461  call    ContainerGetServiceBinding
0x1400aa466  mov     rcx, [rsp+58h]; this
0x1400aa46b  test    eax, eax
0x1400aa46d  js      loc_1400AA50B
0x1400aa473  cmp     [rsp+58h+hHandle], 0
0x1400aa479  jz      short loc_1400AA48F
0x1400aa47b  mov     rcx, [rsp+58h+hHandle]; hObject
0x1400aa480  call    cs:__imp_CloseHandle
0x1400aa486  mov     rcx, [rsp+58h]; this
0x1400aa48b  test    eax, eax
0x1400aa48d  jz      short loc_1400AA4BB
0x1400aa48f  xor     r8d, r8d; lpContext
0x1400aa492  xor     edx, edx; dwFlags
0x1400aa494  mov     rcx, rsi; lpInitOnce
0x1400aa497  call    cs:__imp_InitOnceComplete
0x1400aa49d  mov     al, 1
0x1400aa49f  jmp     short loc_1400AA4A3
0x1400aa4a1  xor     al, al
0x1400aa4a3  mov     rcx, [rsp+58h+var_18]
0x1400aa4a8  xor     rcx, rsp; StackCookie
0x1400aa4ab  call    __security_check_cookie
0x1400aa4b0  mov     rsi, [rsp+58h+arg_8]
0x1400aa4b5  add     rsp, 50h
0x1400aa4b9  pop     rdi
0x1400aa4ba  retn
0x1400aa4bb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400aa4c2  mov     edx, 0A0Bh; void *
0x1400aa4c7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400aa4cd  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400aa4d4  mov     edx, 3BCh; void *
0x1400aa4d9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400aa4df  mov     r9d, eax; char *
0x1400aa4e2  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\management\\orche"...
0x1400aa4e9  mov     edx, 0ACh; void *
0x1400aa4ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400aa4f4  mov     rcx, [rsp+58h]; this
0x1400aa4f9  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400aa500  mov     edx, 0B0Fh; void *
0x1400aa505  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400aa50b  mov     r9d, eax; char *
0x1400aa50e  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\management\\orche"...
0x1400aa515  mov     edx, 0AEh; void *
0x1400aa51a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
