# _lambda_bf91d661a0a10cdd5420b51a8fc443b7_::operator()

- ea: `0x18002b26c`
- end: `0x18002b440`
- name: `_lambda_bf91d661a0a10cdd5420b51a8fc443b7_::operator()`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002bae0`

## callees

- `0x180002f50`
- `0x180008c34`
- `0x18000c294`
- `0x18000d108`
- `0x18000e648`
- `0x180027560`
- `0x180028520`
- `0x180028790`
- `0x180028c00`
- `0x18002b26c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002b30f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002b30f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b366`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b3aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b366`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b3aa`

## string_xrefs

- `0x18002b3f4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002b406`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002b42d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002b33a`: `onecore\vm\compute\dll\legacy\src\computeservicelegacy.cpp`
- `0x18002b3de`: `onecore\vm\compute\dll\legacy\src\computeservicelegacy.cpp`
- `0x18002b41b`: `onecore\vm\compute\dll\legacy\src\computeservicelegacy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_bf91d661a0a10cdd5420b51a8fc443b7_::operator()(__int64 a1, HCS_SYSTEM a2)
{
  int v3; // eax
  HRESULT v4; // ebx
  const char *v5; // r9
  DWORD v6; // eax
  unsigned int v7; // ebx
  __int64 result; // rax
  void *v9; // [rsp+20h] [rbp-38h] BYREF
  HANDLE hHandle; // [rsp+28h] [rbp-30h] BYREF
  HANDLE v11; // [rsp+30h] [rbp-28h] BYREF
  int v12; // [rsp+38h] [rbp-20h]
  char *v13; // [rsp+3Ch] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  try
  {
    hHandle = 0;
    LODWORD(v9) = 1;
    ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
      &hHandle,
      (int *)&v9);
    LODWORD(v13) = -2147418113;
    v11 = hHandle;
    v12 = 1;
    v9 = 0;
    v3 = HcsRegisterComputeSystemCallback(a2, ComputeService::Client::NotificationWatcher, &v11, &v9);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11F,
        (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\computeservicelegacy.cpp",
        (const char *)(unsigned int)v3,
        (int)v9);
    v4 = HcsTerminateComputeSystem(a2, 0, 0);
    if ( v4 == -1070137085 )
    {
      v6 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
      if ( v6 != 258 && v6 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB0F,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v5);
      v7 = (unsigned int)v13;
      if ( (int)v13 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x126,
          (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\computeservicelegacy.cpp",
          (const char *)(unsigned int)v13,
          (int)v9);
      if ( v9 )
        HcsUnregisterComputeSystemCallback(v9);
      if ( hHandle && !CloseHandle(hHandle) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v5);
      result = v7;
    }
    else
    {
      if ( v4 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x12A,
          (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\computeservicelegacy.cpp",
          (const char *)(unsigned int)v4,
          (int)v9);
      if ( v9 )
        HcsUnregisterComputeSystemCallback(v9);
      if ( hHandle && !CloseHandle(hHandle) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v5);
      result = (unsigned int)v4;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x12E,
                           (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\computeservicelegacy.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x18002b26c  push    rbx
0x18002b26e  sub     rsp, 50h
0x18002b272  mov     rax, cs:__security_cookie
0x18002b279  xor     rax, rsp
0x18002b27c  mov     [rsp+58h+var_1C+4], rax
0x18002b281  mov     rbx, rdx
0x18002b284  mov     [rsp+58h+hHandle], 0
0x18002b28d  mov     dword ptr [rsp+58h+var_38], 1
0x18002b295  lea     rdx, [rsp+58h+var_38]
0x18002b29a  lea     rcx, [rsp+58h+hHandle]
0x18002b29f  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18002b2a4  nop
0x18002b2a5  mov     dword ptr [rsp+58h+var_1C], 8000FFFFh
0x18002b2ad  mov     rax, [rsp+58h+hHandle]
0x18002b2b2  mov     [rsp+58h+var_28], rax
0x18002b2b7  mov     [rsp+58h+var_20], 1
0x18002b2bf  mov     [rsp+58h+var_38], 0; int
0x18002b2c8  lea     r9, [rsp+58h+var_38]
0x18002b2cd  lea     r8, [rsp+58h+var_28]
0x18002b2d2  lea     rdx, ?NotificationWatcher@Client@ComputeService@@YAXKPEAXJPEBG@Z; ComputeService::Client::NotificationWatcher(ulong,void *,long,ushort const *)
0x18002b2d9  mov     rcx, rbx
0x18002b2dc  call    HcsRegisterComputeSystemCallback
0x18002b2e1  mov     rcx, [rsp+58h]; this
0x18002b2e6  test    eax, eax
0x18002b2e8  js      loc_18002B3DB
0x18002b2ee  xor     r8d, r8d; options
0x18002b2f1  xor     edx, edx; operation
0x18002b2f3  mov     rcx, rbx; computeSystem
0x18002b2f6  call    HcsTerminateComputeSystem
0x18002b2fb  mov     ebx, eax
0x18002b2fd  cmp     eax, 0C0370103h
0x18002b302  jnz     short loc_18002B383
0x18002b304  xor     r8d, r8d; bAlertable
0x18002b307  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002b30a  mov     rcx, [rsp+58h+hHandle]; hHandle
0x18002b30f  call    cs:__imp_WaitForSingleObjectEx
0x18002b316  nop     dword ptr [rax+rax+00h]
0x18002b31b  cmp     eax, 102h
0x18002b320  jz      short loc_18002B32A
0x18002b322  test    eax, eax
0x18002b324  jnz     loc_18002B3EF
0x18002b32a  mov     ebx, dword ptr [rsp+58h+var_1C]
0x18002b32e  test    ebx, ebx
0x18002b330  jns     short loc_18002B34C
0x18002b332  mov     rcx, [rsp+58h]; this
0x18002b337  mov     r9d, ebx; char *
0x18002b33a  lea     r8, aOnecoreVmCompu_10; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x18002b341  mov     edx, 126h; void *
0x18002b346  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b34b  nop
0x18002b34c  mov     rcx, [rsp+58h+var_38]; void *
0x18002b351  test    rcx, rcx
0x18002b354  jz      short loc_18002B35C
0x18002b356  call    HcsUnregisterComputeSystemCallback
0x18002b35b  nop
0x18002b35c  mov     rcx, [rsp+58h+hHandle]; hObject
0x18002b361  test    rcx, rcx
0x18002b364  jz      short loc_18002B37F
0x18002b366  call    cs:__imp_CloseHandle
0x18002b36d  nop     dword ptr [rax+rax+00h]
0x18002b372  mov     rcx, [rsp+58h]; this
0x18002b377  test    eax, eax
0x18002b379  jz      loc_18002B406
0x18002b37f  mov     eax, ebx
0x18002b381  jmp     short loc_18002B3C7
0x18002b383  mov     rcx, [rsp+58h]; this
0x18002b388  test    ebx, ebx
0x18002b38a  js      loc_18002B418
0x18002b390  mov     rcx, [rsp+58h+var_38]; void *
0x18002b395  test    rcx, rcx
0x18002b398  jz      short loc_18002B3A0
0x18002b39a  call    HcsUnregisterComputeSystemCallback
0x18002b39f  nop
0x18002b3a0  mov     rcx, [rsp+58h+hHandle]; hObject
0x18002b3a5  test    rcx, rcx
0x18002b3a8  jz      short loc_18002B3BF
0x18002b3aa  call    cs:__imp_CloseHandle
0x18002b3b1  nop     dword ptr [rax+rax+00h]
0x18002b3b6  mov     rcx, [rsp+58h]; this
0x18002b3bb  test    eax, eax
0x18002b3bd  jz      short loc_18002B42D
0x18002b3bf  mov     eax, ebx
0x18002b3c1  jmp     short loc_18002B3C7
0x18002b3c3  mov     eax, dword ptr [rsp+58h+var_38]
0x18002b3c7  mov     rcx, [rsp+58h+var_1C+4]
0x18002b3cc  xor     rcx, rsp; StackCookie
0x18002b3cf  call    __security_check_cookie
0x18002b3d4  add     rsp, 50h
0x18002b3d8  pop     rbx
0x18002b3d9  retn
0x18002b3db  mov     r9d, eax; char *
0x18002b3de  lea     r8, aOnecoreVmCompu_10; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x18002b3e5  mov     edx, 11Fh; void *
0x18002b3ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b3ef  mov     rcx, [rsp+58h]; this
0x18002b3f4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b3fb  mov     edx, 0B0Fh; void *
0x18002b400  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002b406  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b40d  mov     edx, 0A0Bh; void *
0x18002b412  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002b418  mov     r9d, ebx; char *
0x18002b41b  lea     r8, aOnecoreVmCompu_10; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x18002b422  mov     edx, 12Ah; void *
0x18002b427  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b42d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b434  mov     edx, 0A0Bh; void *
0x18002b439  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
