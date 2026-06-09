# FlowEndpointBase::Uninitialize(void)

- ea: `0x14005beb0`
- end: `0x14005bf4d`
- name: `?Uninitialize@FlowEndpointBase@@QEAAXXZ`
- size: `157`
- prototype: `void __fastcall(FlowEndpointBase *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140006ab0`
- `0x140052de4`
- `0x14005bd30`

## callees

- `0x14000a7b0`
- `0x14000a834`
- `0x140046a30`
- `0x1400551c4`
- `0x14005beb0`
- `0x14005eafc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005bf17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005bf17`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x14005bf3c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x14005bf3c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14005bf0f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14005bf0f`

## string_xrefs

- `0x14005bf26`: `shellcommon\internal\shell\inc\ValueSetChannel.h`

## pseudocode

```c
void __fastcall FlowEndpointBase::Uninitialize(FlowEndpointBase *this)
{
  struct _TP_WAIT *v1; // rbx
  HWND v3; // rcx
  DWORD WindowThreadProcessId; // ebx
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v7; // [rsp+30h] [rbp+8h] BYREF

  v1 = (struct _TP_WAIT *)*((_QWORD *)this + 8);
  if ( v1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v1);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
  }
  *((_QWORD *)this + 8) = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 56,
    0);
  v3 = (HWND)*((_QWORD *)this + 1);
  *((_DWORD *)this + 28) = 3;
  *((_QWORD *)this + 10) = 0;
  if ( v3 )
  {
    WindowThreadProcessId = GetWindowThreadProcessId(v3, 0);
    if ( WindowThreadProcessId != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x73,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\ValueSetChannel.h",
        v5);
    DestroyWindow(*((HWND *)this + 1));
  }
}

```

## disassembly

```asm
0x14005beb0  mov     [rsp+arg_8], rbx
0x14005beb5  push    rdi
0x14005beb6  sub     rsp, 20h
0x14005beba  mov     rbx, [rcx+40h]
0x14005bebe  mov     rdi, rcx
0x14005bec1  test    rbx, rbx
0x14005bec4  jz      short loc_14005BEE2
0x14005bec6  lea     rcx, [rsp+28h+arg_0]; this
0x14005becb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14005bed0  mov     rcx, rbx; pwa
0x14005bed3  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x14005bed8  lea     rcx, [rsp+28h+arg_0]; this
0x14005bedd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14005bee2  lea     rcx, [rdi+38h]
0x14005bee6  mov     qword ptr [rdi+40h], 0
0x14005beee  xor     edx, edx
0x14005bef0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14005bef5  mov     rcx, [rdi+8]; hWnd
0x14005bef9  mov     dword ptr [rdi+70h], 3
0x14005bf00  mov     qword ptr [rdi+50h], 0
0x14005bf08  test    rcx, rcx
0x14005bf0b  jz      short loc_14005BF42
0x14005bf0d  xor     edx, edx; lpdwProcessId
0x14005bf0f  call    cs:__imp_GetWindowThreadProcessId
0x14005bf15  mov     ebx, eax
0x14005bf17  call    cs:__imp_GetCurrentThreadId
0x14005bf1d  cmp     ebx, eax
0x14005bf1f  jz      short loc_14005BF38
0x14005bf21  mov     rcx, [rsp+28h]; this
0x14005bf26  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\Valu"...
0x14005bf2d  mov     edx, 73h ; 's'; void *
0x14005bf32  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14005bf38  mov     rcx, [rdi+8]; hWnd
0x14005bf3c  call    cs:__imp_DestroyWindow
0x14005bf42  mov     rbx, [rsp+28h+arg_8]
0x14005bf47  add     rsp, 20h
0x14005bf4b  pop     rdi
0x14005bf4c  retn
```
