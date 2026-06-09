# UpdateSessionOrchestrator::IsSystemOrAdmin(void)

- ea: `0x18000dc44`
- end: `0x18000dcf1`
- name: `?IsSystemOrAdmin@UpdateSessionOrchestrator@@AEAA_NXZ`
- size: `173`
- prototype: `bool __fastcall(UpdateSessionOrchestrator *this)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000dd00`
- `0x18000de50`
- `0x18000dfd0`

## callees

- `0x18000dc44`
- `0x18000f190`
- `0x180010b8c`
- `0x1800112d0`
- `0x1800629dc`
- `0x180062a4c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcc9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000dc96`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000dc96`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000dc55`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000dc55`

## string_xrefs

- `0x18000dcde`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall UpdateSessionOrchestrator::IsSystemOrAdmin(UpdateSessionOrchestrator *this)
{
  bool v1; // bl
  HRESULT v2; // eax
  __int64 v3; // rax
  const char *v4; // r9
  bool result; // al
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HANDLE v8; // [rsp+38h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp+18h] BYREF

  v1 = 0;
  v8 = 0;
  v2 = CoImpersonateClient();
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1262,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v2,
        v6);
    v3 = wil::open_current_access_token(&hObject);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v8,
      v3);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    CoRevertToSelf();
    if ( (unsigned __int8)Windows::Trust::IsLocalSystem(&v8) || (unsigned __int8)Windows::Trust::IsAdmin(&v8) )
      v1 = 1;
    if ( (char *)v8 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v8);
    result = v1;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x23D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Orchestrator.cpp",
      v4);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000dc44  mov     [rsp+arg_0], rcx
0x18000dc49  push    rbx; int
0x18000dc4a  sub     rsp, 20h
0x18000dc4e  xor     ebx, ebx
0x18000dc50  mov     [rsp+28h+arg_8], rbx
0x18000dc55  call    cs:__imp_CoImpersonateClient
0x18000dc5b  mov     rcx, [rsp+28h]; this
0x18000dc60  test    eax, eax
0x18000dc62  js      short loc_18000DCDB
0x18000dc64  mov     byte ptr [rsp+28h+arg_0], 1
0x18000dc69  lea     rcx, [rsp+28h+hObject]
0x18000dc6e  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x18000dc73  mov     rdx, rax
0x18000dc76  lea     rcx, [rsp+28h+arg_8]
0x18000dc7b  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18000dc80  mov     rcx, [rsp+28h+hObject]; hObject
0x18000dc85  lea     rax, [rcx-1]
0x18000dc89  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000dc8d  ja      short loc_18000DC96
0x18000dc8f  call    cs:__imp_CloseHandle
0x18000dc95  nop
0x18000dc96  call    cs:__imp_CoRevertToSelf
0x18000dc9c  lea     rcx, [rsp+28h+arg_8]
0x18000dca1  call    ?IsLocalSystem@Trust@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Trust::IsLocalSystem(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x18000dca6  test    al, al
0x18000dca8  jnz     short loc_18000DCB8
0x18000dcaa  lea     rcx, [rsp+28h+arg_8]
0x18000dcaf  call    ?IsAdmin@Trust@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Trust::IsAdmin(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x18000dcb4  test    al, al
0x18000dcb6  jz      short loc_18000DCBA
0x18000dcb8  mov     bl, 1
0x18000dcba  mov     rcx, [rsp+28h+arg_8]; hObject
0x18000dcbf  lea     rdx, [rcx-1]
0x18000dcc3  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000dcc7  ja      short loc_18000DCCF
0x18000dcc9  call    cs:__imp_CloseHandle
0x18000dccf  mov     al, bl
0x18000dcd1  jmp     short loc_18000DCD5
0x18000dcd3  xor     al, al
0x18000dcd5  add     rsp, 20h
0x18000dcd9  pop     rbx
0x18000dcda  retn
0x18000dcdb  mov     r9d, eax; char *
0x18000dcde  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000dce5  mov     edx, 1262h; void *
0x18000dcea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
