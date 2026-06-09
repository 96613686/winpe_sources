# IsSystemOrAdmin(void)

- ea: `0x180040a08`
- end: `0x180040ab1`
- name: `?IsSystemOrAdmin@@YA_NXZ`
- size: `169`
- prototype: `bool(void)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180040ac0`
- `0x180040c30`
- `0x180040d60`
- `0x180040e90`
- `0x180041040`
- `0x180041350`

## callees

- `0x18000f190`
- `0x180010b8c`
- `0x1800112d0`
- `0x180040a08`
- `0x1800629dc`
- `0x180062a4c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040a4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040a89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040a4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040a89`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180040a56`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180040a56`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180040a15`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180040a15`

## string_xrefs

- `0x180040a9e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
bool IsSystemOrAdmin(void)
{
  bool v0; // bl
  HRESULT v1; // eax
  __int64 v2; // rax
  const char *v3; // r9
  bool result; // al
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HANDLE v7; // [rsp+38h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp+18h] BYREF

  v0 = 0;
  v7 = 0;
  v1 = CoImpersonateClient();
  try
  {
    if ( v1 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1262,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v1,
        v5);
    v2 = wil::open_current_access_token(&hObject);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v7,
      v2);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    CoRevertToSelf();
    if ( (unsigned __int8)Windows::Trust::IsLocalSystem(&v7) || (unsigned __int8)Windows::Trust::IsAdmin(&v7) )
      v0 = 1;
    if ( (char *)v7 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v7);
    result = v0;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xAA,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\WindowsUpdateAdministrationImpl.cpp",
      v3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180040a08  push    rbx; int
0x180040a0a  sub     rsp, 20h
0x180040a0e  xor     ebx, ebx
0x180040a10  mov     [rsp+28h+arg_8], rbx
0x180040a15  call    cs:__imp_CoImpersonateClient
0x180040a1b  mov     rcx, [rsp+28h]; this
0x180040a20  test    eax, eax
0x180040a22  js      short loc_180040A9B
0x180040a24  mov     [rsp+28h+arg_0], 1
0x180040a29  lea     rcx, [rsp+28h+hObject]
0x180040a2e  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x180040a33  mov     rdx, rax
0x180040a36  lea     rcx, [rsp+28h+arg_8]
0x180040a3b  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180040a40  mov     rcx, [rsp+28h+hObject]; hObject
0x180040a45  lea     rax, [rcx-1]
0x180040a49  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180040a4d  ja      short loc_180040A56
0x180040a4f  call    cs:__imp_CloseHandle
0x180040a55  nop
0x180040a56  call    cs:__imp_CoRevertToSelf
0x180040a5c  lea     rcx, [rsp+28h+arg_8]
0x180040a61  call    ?IsLocalSystem@Trust@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Trust::IsLocalSystem(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x180040a66  test    al, al
0x180040a68  jnz     short loc_180040A78
0x180040a6a  lea     rcx, [rsp+28h+arg_8]
0x180040a6f  call    ?IsAdmin@Trust@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Trust::IsAdmin(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x180040a74  test    al, al
0x180040a76  jz      short loc_180040A7A
0x180040a78  mov     bl, 1
0x180040a7a  mov     rcx, [rsp+28h+arg_8]; hObject
0x180040a7f  lea     rdx, [rcx-1]
0x180040a83  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180040a87  ja      short loc_180040A8F
0x180040a89  call    cs:__imp_CloseHandle
0x180040a8f  mov     al, bl
0x180040a91  jmp     short loc_180040A95
0x180040a93  xor     al, al
0x180040a95  add     rsp, 20h
0x180040a99  pop     rbx
0x180040a9a  retn
0x180040a9b  mov     r9d, eax; char *
0x180040a9e  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180040aa5  mov     edx, 1262h; void *
0x180040aaa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
