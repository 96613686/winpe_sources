# _lambda_62acbc56f99b48a59cae0a3b005ffc51_::operator()

- ea: `0x18002ae1c`
- end: `0x18002afda`
- name: `_lambda_62acbc56f99b48a59cae0a3b005ffc51_::operator()`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002bbd0`

## callees

- `0x180002f50`
- `0x180008c34`
- `0x18000d0ec`
- `0x18000d108`
- `0x18000e648`
- `0x18000ebb0`
- `0x180027740`
- `0x180028920`
- `0x18002ae1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002ae56`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002ae56`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002aedb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002aedb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002af32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002af32`

## string_xrefs

- `0x18002af86`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002afb0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002afc7`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18002af70`: `onecore\vm\compute\dll\legacy\src\computeservicelegacy.cpp`
- `0x18002af9e`: `onecore\vm\compute\dll\legacy\src\computeservicelegacy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall lambda_62acbc56f99b48a59cae0a3b005ffc51_::operator()(__int64 a1, __int64 a2)
{
  HANDLE Event; // rbx
  const char *v5; // r9
  HANDLE v6; // rbx
  int v7; // eax
  DWORD v8; // eax
  const char *v9; // r9
  char v10; // al
  unsigned int v11; // edi
  const char *v12; // r9
  HANDLE hHandle; // [rsp+20h] [rbp-38h] BYREF
  void *v15; // [rsp+28h] [rbp-30h] BYREF
  HANDLE v16; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v17; // [rsp+38h] [rbp-20h]
  int v18; // [rsp+3Ch] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  hHandle = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v5);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Event);
  v17 = 0;
  v18 = -1;
  v6 = hHandle;
  v16 = hHandle;
  v15 = 0;
  v7 = HcsRegisterProcessCallback(a2, lambda_efca8687a57aad5380c24d23af717fad_::_lambda_invoker_cdecl_, &v16, &v15);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\computeservicelegacy.cpp",
      (const char *)(unsigned int)v7,
      (int)hHandle);
  v8 = WaitForSingleObjectEx(v6, **(_DWORD **)a1, 0);
  if ( v8 == 258 )
  {
    v10 = 0;
  }
  else
  {
    if ( v8 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xB0F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
    v10 = 1;
  }
  if ( !v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x258,
      (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\computeservicelegacy.cpp",
      (const char *)0x80070102LL,
      (int)hHandle);
  ***(_DWORD ***)(a1 + 8) = v18;
  v11 = v17;
  if ( v15 )
    HcsUnregisterProcessCallback(v15);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v12);
  return v11;
}

```

## disassembly

```asm
0x18002ae1c  mov     [rsp+arg_10], rbx
0x18002ae21  mov     [rsp+arg_18], rsi
0x18002ae26  push    rdi
0x18002ae27  sub     rsp, 50h
0x18002ae2b  mov     rax, cs:__security_cookie
0x18002ae32  xor     rax, rsp
0x18002ae35  mov     [rsp+58h+var_18], rax
0x18002ae3a  mov     rsi, rdx
0x18002ae3d  mov     rdi, rcx
0x18002ae40  mov     [rsp+58h+hHandle], 0; int
0x18002ae49  mov     r9d, 1F0003h; dwDesiredAccess
0x18002ae4f  xor     r8d, r8d; dwFlags
0x18002ae52  xor     edx, edx; lpName
0x18002ae54  xor     ecx, ecx; lpEventAttributes
0x18002ae56  call    cs:__imp_CreateEventExW
0x18002ae5d  nop     dword ptr [rax+rax+00h]
0x18002ae62  mov     rbx, rax
0x18002ae65  test    rax, rax
0x18002ae68  jz      loc_18002AFC2
0x18002ae6e  call    cs:__imp_GetLastError
0x18002ae75  nop     dword ptr [rax+rax+00h]
0x18002ae7a  mov     rdx, rbx
0x18002ae7d  lea     rcx, [rsp+58h+hHandle]
0x18002ae82  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002ae87  mov     [rsp+58h+var_20], 0
0x18002ae8f  mov     [rsp+58h+var_1C], 0FFFFFFFFh
0x18002ae97  mov     rbx, [rsp+58h+hHandle]
0x18002ae9c  mov     [rsp+58h+var_28], rbx
0x18002aea1  mov     [rsp+58h+var_30], 0
0x18002aeaa  lea     r9, [rsp+58h+var_30]
0x18002aeaf  lea     r8, [rsp+58h+var_28]
0x18002aeb4  lea     rdx, _lambda_efca8687a57aad5380c24d23af717fad____lambda_invoker_cdecl_
0x18002aebb  mov     rcx, rsi
0x18002aebe  call    HcsRegisterProcessCallback
0x18002aec3  mov     rcx, [rsp+58h]; this
0x18002aec8  test    eax, eax
0x18002aeca  js      loc_18002AF6D
0x18002aed0  mov     rdx, [rdi]
0x18002aed3  xor     r8d, r8d; bAlertable
0x18002aed6  mov     edx, [rdx]; dwMilliseconds
0x18002aed8  mov     rcx, rbx; hHandle
0x18002aedb  call    cs:__imp_WaitForSingleObjectEx
0x18002aee2  nop     dword ptr [rax+rax+00h]
0x18002aee7  cmp     eax, 102h
0x18002aeec  jz      short loc_18002AEFA
0x18002aeee  test    eax, eax
0x18002aef0  jnz     loc_18002AF81
0x18002aef6  mov     al, 1
0x18002aef8  jmp     short loc_18002AEFC
0x18002aefa  xor     al, al
0x18002aefc  mov     rcx, [rsp+58h]; this
0x18002af01  test    al, al
0x18002af03  jz      loc_18002AF98
0x18002af09  mov     rax, [rdi+8]
0x18002af0d  mov     rcx, [rax]
0x18002af10  mov     eax, [rsp+58h+var_1C]
0x18002af14  mov     [rcx], eax
0x18002af16  mov     edi, [rsp+58h+var_20]
0x18002af1a  mov     rcx, [rsp+58h+var_30]; void *
0x18002af1f  test    rcx, rcx
0x18002af22  jz      short loc_18002AF2A
0x18002af24  call    HcsUnregisterProcessCallback
0x18002af29  nop
0x18002af2a  test    rbx, rbx
0x18002af2d  jz      short loc_18002AF47
0x18002af2f  mov     rcx, rbx; hObject
0x18002af32  call    cs:__imp_CloseHandle
0x18002af39  nop     dword ptr [rax+rax+00h]
0x18002af3e  mov     rcx, [rsp+58h]; this
0x18002af43  test    eax, eax
0x18002af45  jz      short loc_18002AFB0
0x18002af47  mov     eax, edi
0x18002af49  jmp     short loc_18002AF4F
0x18002af4b  mov     eax, dword ptr [rsp+58h+hHandle]
0x18002af4f  mov     rcx, [rsp+58h+var_18]
0x18002af54  xor     rcx, rsp; StackCookie
0x18002af57  call    __security_check_cookie
0x18002af5c  mov     rbx, [rsp+58h+arg_10]
0x18002af61  mov     rsi, [rsp+58h+arg_18]
0x18002af66  add     rsp, 50h
0x18002af6a  pop     rdi
0x18002af6b  retn
0x18002af6d  mov     r9d, eax; char *
0x18002af70  lea     r8, aOnecoreVmCompu_10; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x18002af77  mov     edx, 255h; void *
0x18002af7c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002af81  mov     rcx, [rsp+58h]; this
0x18002af86  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002af8d  mov     edx, 0B0Fh; void *
0x18002af92  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002af98  mov     r9d, 80070102h; char *
0x18002af9e  lea     r8, aOnecoreVmCompu_10; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x18002afa5  mov     edx, 258h; void *
0x18002afaa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002afb0  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002afb7  mov     edx, 0A0Bh; void *
0x18002afbc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002afc2  mov     rcx, [rsp+58h]; this
0x18002afc7  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002afce  mov     edx, 1CC8h; void *
0x18002afd3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
