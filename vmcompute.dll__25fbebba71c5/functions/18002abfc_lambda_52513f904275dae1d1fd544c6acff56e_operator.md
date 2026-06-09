# _lambda_52513f904275dae1d1fd544c6acff56e_::operator()

- ea: `0x18002abfc`
- end: `0x18002ae16`
- name: `_lambda_52513f904275dae1d1fd544c6acff56e_::operator()`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002ba30`

## callees

- `0x180002f50`
- `0x180008c34`
- `0x18000c294`
- `0x18000d108`
- `0x18000e648`
- `0x180027560`
- `0x180027d00`
- `0x180028790`
- `0x180028c00`
- `0x18002abfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002acac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002acac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ad16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ad5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ad16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ad5a`

## string_xrefs

- `0x18002adb2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002addc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002ae03`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002acea`: `onecore\vm\compute\dll\legacy\src\computeservicelegacy.cpp`
- `0x18002ad9c`: `onecore\vm\compute\dll\legacy\src\computeservicelegacy.cpp`
- `0x18002adca`: `onecore\vm\compute\dll\legacy\src\computeservicelegacy.cpp`
- `0x18002adf1`: `onecore\vm\compute\dll\legacy\src\computeservicelegacy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_52513f904275dae1d1fd544c6acff56e_::operator()(DWORD **a1, _QWORD *a2)
{
  char v4; // di
  int v5; // eax
  int v6; // ebx
  const char *v7; // r9
  DWORD v8; // eax
  unsigned int v9; // ebx
  __int64 result; // rax
  void *v11; // [rsp+20h] [rbp-38h] BYREF
  HANDLE hHandle; // [rsp+28h] [rbp-30h] BYREF
  HANDLE v13; // [rsp+30h] [rbp-28h] BYREF
  int v14; // [rsp+38h] [rbp-20h]
  char *v15; // [rsp+3Ch] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  try
  {
    hHandle = 0;
    v4 = 1;
    LODWORD(v11) = 1;
    ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
      &hHandle,
      (int *)&v11);
    LODWORD(v15) = -2147418113;
    v13 = hHandle;
    v14 = 1;
    v11 = 0;
    v5 = HcsRegisterComputeSystemCallback(a2, ComputeService::Client::NotificationWatcher, &v13, &v11);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF2,
        (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\computeservicelegacy.cpp",
        (const char *)(unsigned int)v5,
        (int)v11);
    v6 = HcsShutdownComputeSystem(a2, 0, 0);
    if ( v6 == -1070137085 )
    {
      v8 = WaitForSingleObjectEx(hHandle, **a1, 0);
      if ( v8 == 258 )
      {
        v4 = 0;
      }
      else if ( v8 )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB0F,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v7);
      }
      if ( !v4 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF8,
          (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\computeservicelegacy.cpp",
          (const char *)0x80070102LL,
          (int)v11);
      v9 = (unsigned int)v15;
      if ( (int)v15 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF9,
          (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\computeservicelegacy.cpp",
          (const char *)(unsigned int)v15,
          (int)v11);
      if ( v11 )
        HcsUnregisterComputeSystemCallback(v11);
      if ( hHandle && !CloseHandle(hHandle) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v7);
      result = v9;
    }
    else
    {
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFD,
          (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\computeservicelegacy.cpp",
          (const char *)(unsigned int)v6,
          (int)v11);
      if ( v11 )
        HcsUnregisterComputeSystemCallback(v11);
      if ( hHandle && !CloseHandle(hHandle) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v7);
      result = (unsigned int)v6;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x101,
                           (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\computeservicelegacy.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18002abfc  mov     r11, rsp
0x18002abff  mov     [r11+18h], rbx
0x18002ac03  mov     [r11+20h], rsi
0x18002ac07  push    rdi
0x18002ac08  sub     rsp, 50h
0x18002ac0c  mov     rax, cs:__security_cookie
0x18002ac13  xor     rax, rsp
0x18002ac16  mov     [rsp+58h+var_1C+4], rax
0x18002ac1b  mov     rbx, rdx
0x18002ac1e  mov     rsi, rcx
0x18002ac21  mov     qword ptr [r11-30h], 0
0x18002ac29  mov     edi, 1
0x18002ac2e  mov     dword ptr [rsp+58h+var_38], edi
0x18002ac32  lea     rdx, [r11-38h]
0x18002ac36  lea     rcx, [r11-30h]
0x18002ac3a  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18002ac3f  nop
0x18002ac40  mov     dword ptr [rsp+58h+var_1C], 8000FFFFh
0x18002ac48  mov     rax, [rsp+58h+hHandle]
0x18002ac4d  mov     [rsp+58h+var_28], rax
0x18002ac52  mov     [rsp+58h+var_20], edi
0x18002ac56  mov     [rsp+58h+var_38], 0; int
0x18002ac5f  lea     r9, [rsp+58h+var_38]
0x18002ac64  lea     r8, [rsp+58h+var_28]
0x18002ac69  lea     rdx, ?NotificationWatcher@Client@ComputeService@@YAXKPEAXJPEBG@Z; ComputeService::Client::NotificationWatcher(ulong,void *,long,ushort const *)
0x18002ac70  mov     rcx, rbx
0x18002ac73  call    HcsRegisterComputeSystemCallback
0x18002ac78  mov     rcx, [rsp+58h]; this
0x18002ac7d  test    eax, eax
0x18002ac7f  js      loc_18002AD99
0x18002ac85  xor     r8d, r8d
0x18002ac88  xor     edx, edx
0x18002ac8a  mov     rcx, rbx; void *
0x18002ac8d  call    HcsShutdownComputeSystem
0x18002ac92  mov     ebx, eax
0x18002ac94  cmp     eax, 0C0370103h
0x18002ac99  jnz     loc_18002AD33
0x18002ac9f  mov     rdx, [rsi]
0x18002aca2  xor     r8d, r8d; bAlertable
0x18002aca5  mov     edx, [rdx]; dwMilliseconds
0x18002aca7  mov     rcx, [rsp+58h+hHandle]; hHandle
0x18002acac  call    cs:__imp_WaitForSingleObjectEx
0x18002acb3  nop     dword ptr [rax+rax+00h]
0x18002acb8  cmp     eax, 102h
0x18002acbd  jz      short loc_18002ACC9
0x18002acbf  test    eax, eax
0x18002acc1  jnz     loc_18002ADAD
0x18002acc7  jmp     short loc_18002ACCC
0x18002acc9  xor     dil, dil
0x18002accc  mov     rcx, [rsp+58h]; this
0x18002acd1  test    dil, dil
0x18002acd4  jz      loc_18002ADC4
0x18002acda  mov     ebx, dword ptr [rsp+58h+var_1C]
0x18002acde  test    ebx, ebx
0x18002ace0  jns     short loc_18002ACFC
0x18002ace2  mov     rcx, [rsp+58h]; this
0x18002ace7  mov     r9d, ebx; char *
0x18002acea  lea     r8, aOnecoreVmCompu_10; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x18002acf1  mov     edx, 0F9h; void *
0x18002acf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002acfb  nop
0x18002acfc  mov     rcx, [rsp+58h+var_38]; void *
0x18002ad01  test    rcx, rcx
0x18002ad04  jz      short loc_18002AD0C
0x18002ad06  call    HcsUnregisterComputeSystemCallback
0x18002ad0b  nop
0x18002ad0c  mov     rcx, [rsp+58h+hHandle]; hObject
0x18002ad11  test    rcx, rcx
0x18002ad14  jz      short loc_18002AD2F
0x18002ad16  call    cs:__imp_CloseHandle
0x18002ad1d  nop     dword ptr [rax+rax+00h]
0x18002ad22  mov     rcx, [rsp+58h]; this
0x18002ad27  test    eax, eax
0x18002ad29  jz      loc_18002ADDC
0x18002ad2f  mov     eax, ebx
0x18002ad31  jmp     short loc_18002AD7B
0x18002ad33  mov     rcx, [rsp+58h]; this
0x18002ad38  test    ebx, ebx
0x18002ad3a  js      loc_18002ADEE
0x18002ad40  mov     rcx, [rsp+58h+var_38]; void *
0x18002ad45  test    rcx, rcx
0x18002ad48  jz      short loc_18002AD50
0x18002ad4a  call    HcsUnregisterComputeSystemCallback
0x18002ad4f  nop
0x18002ad50  mov     rcx, [rsp+58h+hHandle]; hObject
0x18002ad55  test    rcx, rcx
0x18002ad58  jz      short loc_18002AD73
0x18002ad5a  call    cs:__imp_CloseHandle
0x18002ad61  nop     dword ptr [rax+rax+00h]
0x18002ad66  mov     rcx, [rsp+58h]; this
0x18002ad6b  test    eax, eax
0x18002ad6d  jz      loc_18002AE03
0x18002ad73  mov     eax, ebx
0x18002ad75  jmp     short loc_18002AD7B
0x18002ad77  mov     eax, dword ptr [rsp+58h+var_38]
0x18002ad7b  mov     rcx, [rsp+58h+var_1C+4]
0x18002ad80  xor     rcx, rsp; StackCookie
0x18002ad83  call    __security_check_cookie
0x18002ad88  mov     rbx, [rsp+58h+arg_10]
0x18002ad8d  mov     rsi, [rsp+58h+arg_18]
0x18002ad92  add     rsp, 50h
0x18002ad96  pop     rdi
0x18002ad97  retn
0x18002ad99  mov     r9d, eax; char *
0x18002ad9c  lea     r8, aOnecoreVmCompu_10; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x18002ada3  mov     edx, 0F2h; void *
0x18002ada8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002adad  mov     rcx, [rsp+58h]; this
0x18002adb2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002adb9  mov     edx, 0B0Fh; void *
0x18002adbe  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002adc4  mov     r9d, 80070102h; char *
0x18002adca  lea     r8, aOnecoreVmCompu_10; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x18002add1  mov     edx, 0F8h; void *
0x18002add6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002addc  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ade3  mov     edx, 0A0Bh; void *
0x18002ade8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002adee  mov     r9d, ebx; char *
0x18002adf1  lea     r8, aOnecoreVmCompu_10; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x18002adf8  mov     edx, 0FDh; void *
0x18002adfd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ae03  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ae0a  mov     edx, 0A0Bh; void *
0x18002ae0f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
