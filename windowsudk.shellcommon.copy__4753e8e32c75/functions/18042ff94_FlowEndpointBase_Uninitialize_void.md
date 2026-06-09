# FlowEndpointBase::Uninitialize(void)

- ea: `0x18042ff94`
- end: `0x18043000f`
- name: `?Uninitialize@FlowEndpointBase@@QEAAXXZ`
- size: `123`
- prototype: `void __fastcall(FlowEndpointBase *__hidden this)`
- caller_count: `13`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800cf4b0`
- `0x180424c84`
- `0x180424cd4`
- `0x180425114`
- `0x1804253e0`
- `0x180426f2c`
- `0x18042b4c0`
- `0x18042dab0`
- `0x18042e0f0`
- `0x18042eb04`
- `0x18042f270`
- `0x18042f7e4`
- `0x18042f980`

## callees

- `0x180086f44`
- `0x18008d854`
- `0x1800e3810`
- `0x18042ff94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18042ffd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18042ffd9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18042ffd1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18042ffd1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x18042fffe`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x18042fffe`

## string_xrefs

- `0x18042ffe8`: `shellcommon\internal\shell\inc\ValueSetChannel.h`

## pseudocode

```c
void __fastcall FlowEndpointBase::Uninitialize(FlowEndpointBase *this)
{
  HWND v2; // rcx
  DWORD WindowThreadProcessId; // ebx
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    (char *)this + 64,
    0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 56,
    0);
  v2 = (HWND)*((_QWORD *)this + 1);
  *((_DWORD *)this + 28) = 3;
  *((_QWORD *)this + 10) = 0;
  if ( v2 )
  {
    WindowThreadProcessId = GetWindowThreadProcessId(v2, 0);
    if ( WindowThreadProcessId != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x73,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\ValueSetChannel.h",
        v4);
    DestroyWindow(*((HWND *)this + 1));
  }
}

```

## disassembly

```asm
0x18042ff94  mov     [rsp+arg_0], rbx
0x18042ff99  push    rdi
0x18042ff9a  sub     rsp, 20h
0x18042ff9e  mov     rdi, rcx
0x18042ffa1  xor     edx, edx
0x18042ffa3  add     rcx, 40h ; '@'
0x18042ffa7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18042ffac  lea     rcx, [rdi+38h]
0x18042ffb0  xor     edx, edx
0x18042ffb2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18042ffb7  mov     rcx, [rdi+8]; hWnd
0x18042ffbb  mov     dword ptr [rdi+70h], 3
0x18042ffc2  mov     qword ptr [rdi+50h], 0
0x18042ffca  test    rcx, rcx
0x18042ffcd  jz      short loc_180430004
0x18042ffcf  xor     edx, edx; lpdwProcessId
0x18042ffd1  call    cs:__imp_GetWindowThreadProcessId
0x18042ffd7  mov     ebx, eax
0x18042ffd9  call    cs:__imp_GetCurrentThreadId
0x18042ffdf  cmp     ebx, eax
0x18042ffe1  jz      short loc_18042FFFA
0x18042ffe3  mov     rcx, [rsp+28h]; this
0x18042ffe8  lea     r8, aShellcommonInt_12; "shellcommon\\internal\\shell\\inc\\Valu"...
0x18042ffef  mov     edx, 73h ; 's'; void *
0x18042fff4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18042fffa  mov     rcx, [rdi+8]; hWnd
0x18042fffe  call    cs:__imp_DestroyWindow
0x180430004  mov     rbx, [rsp+28h+arg_0]
0x180430009  add     rsp, 20h
0x18043000d  pop     rdi
0x18043000e  retn
```
