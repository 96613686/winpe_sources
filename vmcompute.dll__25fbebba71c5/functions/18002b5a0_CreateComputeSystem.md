# CreateComputeSystem

- ea: `0x18002b5a0`
- end: `0x18002b7ad`
- name: `CreateComputeSystem`
- size: `525`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002f50`
- `0x180008c34`
- `0x18000c294`
- `0x18000d0ec`
- `0x18000d108`
- `0x18000e648`
- `0x18000ebb0`
- `0x1800252f0`
- `0x180025750`
- `0x180027560`
- `0x180028790`
- `0x18002b5a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002b5fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002b5fa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002b67f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002b67f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b612`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b612`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b6d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b6d4`

## string_xrefs

- `0x18002b75c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002b76e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002b785`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18002b6aa`: `onecore\vm\compute\dll\legacy\src\computeservicelegacy.cpp`
- `0x18002b746`: `onecore\vm\compute\dll\legacy\src\computeservicelegacy.cpp`
- `0x18002b79a`: `onecore\vm\compute\dll\legacy\src\computeservicelegacy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CreateComputeSystem(const WCHAR *a1, const WCHAR *a2)
{
  HRESULT v2; // ebx
  HANDLE Event; // rbx
  const char *v4; // r9
  HANDLE v5; // rbx
  int v6; // eax
  DWORD v7; // eax
  const char *v8; // r9
  unsigned int v9; // esi
  const char *v10; // r9
  int v12; // [rsp+20h] [rbp-48h]
  HCS_SYSTEM computeSystem; // [rsp+30h] [rbp-38h] BYREF
  HANDLE hHandle; // [rsp+38h] [rbp-30h] BYREF
  void *v15; // [rsp+40h] [rbp-28h] BYREF
  HANDLE v16; // [rsp+48h] [rbp-20h] BYREF
  int v17; // [rsp+50h] [rbp-18h]
  char *v18; // [rsp+54h] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  computeSystem = 0;
  v2 = HcsCreateComputeSystem(a1, a2, 0, (const SECURITY_DESCRIPTOR *)&computeSystem, 0);
  if ( v2 == -1070137085 )
  {
    hHandle = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( !Event )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1CC8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        v4);
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &hHandle,
      Event);
    LODWORD(v18) = -2147418113;
    v5 = hHandle;
    v16 = hHandle;
    v17 = 2;
    v15 = 0;
    v6 = HcsRegisterComputeSystemCallback(computeSystem, ComputeService::Client::NotificationWatcher, &v16, &v15);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\computeservicelegacy.cpp",
        (const char *)(unsigned int)v6,
        v12);
    v7 = WaitForSingleObjectEx(v5, 0xFFFFFFFF, 0);
    if ( v7 != 258 && v7 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xB0F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    v9 = (unsigned int)v18;
    if ( (int)v18 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\computeservicelegacy.cpp",
        (const char *)(unsigned int)v18,
        v12);
    if ( v15 )
      HcsUnregisterComputeSystemCallback(v15);
    if ( v5 && !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    if ( computeSystem )
      HcsCloseComputeSystem(computeSystem);
    return v9;
  }
  else
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA2,
        (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\computeservicelegacy.cpp",
        (const char *)(unsigned int)v2,
        v12);
    if ( computeSystem )
      HcsCloseComputeSystem(computeSystem);
    return (unsigned int)v2;
  }
}

```

## disassembly

```asm
0x18002b5a0  mov     r11, rsp
0x18002b5a3  mov     [r11+18h], rbx
0x18002b5a7  push    rsi
0x18002b5a8  sub     rsp, 60h
0x18002b5ac  mov     rax, cs:__security_cookie
0x18002b5b3  xor     rax, rsp
0x18002b5b6  mov     [rsp+68h+var_14+4], rax
0x18002b5bb  mov     qword ptr [r11-38h], 0
0x18002b5c3  mov     qword ptr [r11-48h], 0
0x18002b5cb  lea     r9, [r11-38h]; securityDescriptor
0x18002b5cf  xor     r8d, r8d; operation
0x18002b5d2  call    HcsCreateComputeSystem
0x18002b5d7  mov     ebx, eax
0x18002b5d9  cmp     eax, 0C0370103h
0x18002b5de  jnz     loc_18002B703
0x18002b5e4  mov     [rsp+68h+hHandle], 0
0x18002b5ed  mov     r9d, 1F0003h; dwDesiredAccess
0x18002b5f3  xor     r8d, r8d; dwFlags
0x18002b5f6  xor     edx, edx; lpName
0x18002b5f8  xor     ecx, ecx; lpEventAttributes
0x18002b5fa  call    cs:__imp_CreateEventExW
0x18002b601  nop     dword ptr [rax+rax+00h]
0x18002b606  mov     rbx, rax
0x18002b609  test    rax, rax
0x18002b60c  jz      loc_18002B780
0x18002b612  call    cs:__imp_GetLastError
0x18002b619  nop     dword ptr [rax+rax+00h]
0x18002b61e  mov     rdx, rbx
0x18002b621  lea     rcx, [rsp+68h+hHandle]
0x18002b626  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002b62b  mov     dword ptr [rsp+68h+var_14], 8000FFFFh
0x18002b633  mov     rbx, [rsp+68h+hHandle]
0x18002b638  mov     [rsp+68h+var_20], rbx
0x18002b63d  mov     [rsp+68h+var_18], 2
0x18002b645  mov     [rsp+68h+var_28], 0
0x18002b64e  lea     r9, [rsp+68h+var_28]
0x18002b653  lea     r8, [rsp+68h+var_20]
0x18002b658  lea     rdx, ?NotificationWatcher@Client@ComputeService@@YAXKPEAXJPEBG@Z; ComputeService::Client::NotificationWatcher(ulong,void *,long,ushort const *)
0x18002b65f  mov     rcx, [rsp+68h+computeSystem]
0x18002b664  call    HcsRegisterComputeSystemCallback
0x18002b669  mov     rcx, [rsp+68h]; this
0x18002b66e  test    eax, eax
0x18002b670  js      loc_18002B743
0x18002b676  xor     r8d, r8d; bAlertable
0x18002b679  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002b67c  mov     rcx, rbx; hHandle
0x18002b67f  call    cs:__imp_WaitForSingleObjectEx
0x18002b686  nop     dword ptr [rax+rax+00h]
0x18002b68b  cmp     eax, 102h
0x18002b690  jz      short loc_18002B69A
0x18002b692  test    eax, eax
0x18002b694  jnz     loc_18002B757
0x18002b69a  mov     esi, dword ptr [rsp+68h+var_14]
0x18002b69e  test    esi, esi
0x18002b6a0  jns     short loc_18002B6BC
0x18002b6a2  mov     rcx, [rsp+68h]; this
0x18002b6a7  mov     r9d, esi; char *
0x18002b6aa  lea     r8, aOnecoreVmCompu_10; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x18002b6b1  mov     edx, 9Eh; void *
0x18002b6b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b6bb  nop
0x18002b6bc  mov     rcx, [rsp+68h+var_28]; void *
0x18002b6c1  test    rcx, rcx
0x18002b6c4  jz      short loc_18002B6CC
0x18002b6c6  call    HcsUnregisterComputeSystemCallback
0x18002b6cb  nop
0x18002b6cc  test    rbx, rbx
0x18002b6cf  jz      short loc_18002B6ED
0x18002b6d1  mov     rcx, rbx; hObject
0x18002b6d4  call    cs:__imp_CloseHandle
0x18002b6db  nop     dword ptr [rax+rax+00h]
0x18002b6e0  mov     rcx, [rsp+68h]; this
0x18002b6e5  test    eax, eax
0x18002b6e7  jz      loc_18002B76E
0x18002b6ed  cmp     [rsp+68h+computeSystem], 0
0x18002b6f3  jz      short loc_18002B6FF
0x18002b6f5  mov     rcx, [rsp+68h+computeSystem]; computeSystem
0x18002b6fa  call    HcsCloseComputeSystem
0x18002b6ff  mov     eax, esi
0x18002b701  jmp     short loc_18002B727
0x18002b703  mov     rcx, [rsp+68h]; this
0x18002b708  test    ebx, ebx
0x18002b70a  js      loc_18002B797
0x18002b710  mov     rcx, [rsp+68h+computeSystem]; computeSystem
0x18002b715  test    rcx, rcx
0x18002b718  jz      short loc_18002B71F
0x18002b71a  call    HcsCloseComputeSystem
0x18002b71f  mov     eax, ebx
0x18002b721  jmp     short loc_18002B727
0x18002b723  mov     eax, dword ptr [rsp+68h+computeSystem]
0x18002b727  mov     rcx, [rsp+68h+var_14+4]
0x18002b72c  xor     rcx, rsp; StackCookie
0x18002b72f  call    __security_check_cookie
0x18002b734  mov     rbx, [rsp+68h+arg_10]
0x18002b73c  add     rsp, 60h
0x18002b740  pop     rsi
0x18002b741  retn
0x18002b743  mov     r9d, eax; char *
0x18002b746  lea     r8, aOnecoreVmCompu_10; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x18002b74d  mov     edx, 9Bh; void *
0x18002b752  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b757  mov     rcx, [rsp+68h]; this
0x18002b75c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b763  mov     edx, 0B0Fh; void *
0x18002b768  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002b76e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b775  mov     edx, 0A0Bh; void *
0x18002b77a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002b780  mov     rcx, [rsp+68h]; this
0x18002b785  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b78c  mov     edx, 1CC8h; void *
0x18002b791  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002b797  mov     r9d, ebx; char *
0x18002b79a  lea     r8, aOnecoreVmCompu_10; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x18002b7a1  mov     edx, 0A2h; void *
0x18002b7a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
