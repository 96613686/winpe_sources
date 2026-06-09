# Windows::UserMgrHelpers::GetAllSessionUserTokens(void)

- ea: `0x180050e80`
- end: `0x180050fd5`
- name: `?GetAllSessionUserTokens@UserMgrHelpers@Windows@@YA?AV?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@XZ`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180051924`

## callees

- `0x1800209fc`
- `0x18004f510`
- `0x180050e80`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050f77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050f77`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180050f92`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180050f92`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180050ec9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180050ec9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180050f2d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180050f2d`

## string_xrefs

- `0x180050fae`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`
- `0x180050fc3`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Windows::UserMgrHelpers::GetAllSessionUserTokens(_QWORD *a1)
{
  int v2; // eax
  _QWORD *v3; // rbx
  _QWORD *v4; // rsi
  int v5; // eax
  HANDLE *v6; // rdx
  char *v7; // rcx
  unsigned int v9; // [rsp+30h] [rbp-20h] BYREF
  char v10; // [rsp+34h] [rbp-1Ch]
  _QWORD *v11; // [rsp+38h] [rbp-18h] BYREF
  __int64 v12; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HANDLE hObject; // [rsp+78h] [rbp+28h] BYREF

  v11 = 0;
  v12 = 0;
  v9 = 0;
  v10 = 1;
  v2 = UMgrEnumerateSessionUsers(&v9, &v11);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
      (const char *)(unsigned int)v2,
      0);
  if ( v10 )
    v12 = v9;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v3 = v11;
  v4 = &v11[2 * v12];
  if ( v11 != v4 )
  {
    do
    {
      hObject = 0;
      v5 = UMgrQueryUserToken(*v3, &hObject);
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x69,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
          (const char *)(unsigned int)v5,
          1);
      v6 = (HANDLE *)a1[1];
      if ( v6 == (HANDLE *)a1[2] )
      {
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
          a1,
          v6,
          &hObject);
        v7 = (char *)hObject;
      }
      else
      {
        *v6 = hObject;
        v7 = 0;
        hObject = 0;
        a1[1] += 8LL;
      }
      if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v7);
      v3 += 2;
    }
    while ( v3 != v4 );
    v3 = v11;
  }
  if ( v3 )
    UMgrFreeSessionUsers(v3);
  return a1;
}

```

## disassembly

```asm
0x180050e80  mov     [rsp-18h+arg_10], rbx
0x180050e85  mov     [rsp-18h+arg_0], rcx
0x180050e8a  push    rbp
0x180050e8b  push    rsi
0x180050e8c  push    rdi
0x180050e8d  mov     rbp, rsp
0x180050e90  sub     rsp, 50h
0x180050e94  mov     rdi, rcx
0x180050e97  mov     [rbp+var_30], 0
0x180050e9e  mov     [rbp+var_18], 0
0x180050ea6  mov     [rbp+var_10], 0
0x180050eae  lea     rax, [rbp+var_18]
0x180050eb2  mov     [rbp+var_28], rax
0x180050eb6  mov     [rbp+var_20], 0
0x180050ebd  mov     [rbp+var_1C], 1
0x180050ec1  lea     rdx, [rbp+var_18]
0x180050ec5  lea     rcx, [rbp+var_20]
0x180050ec9  call    cs:__imp_UMgrEnumerateSessionUsers
0x180050ecf  mov     rcx, [rbp+18h]; this
0x180050ed3  test    eax, eax
0x180050ed5  js      loc_180050FAB
0x180050edb  cmp     [rbp+var_1C], 0
0x180050edf  jz      short loc_180050EEC
0x180050ee1  mov     ecx, [rbp+var_20]
0x180050ee4  mov     rax, [rbp+var_28]
0x180050ee8  mov     [rax+8], rcx
0x180050eec  mov     qword ptr [rdi], 0
0x180050ef3  mov     qword ptr [rdi+8], 0
0x180050efb  mov     qword ptr [rdi+10h], 0
0x180050f03  mov     [rbp+var_30], 1
0x180050f0a  mov     rbx, [rbp+var_18]
0x180050f0e  mov     rsi, [rbp+var_10]
0x180050f12  shl     rsi, 4
0x180050f16  add     rsi, rbx
0x180050f19  cmp     rbx, rsi
0x180050f1c  jz      short loc_180050F8A
0x180050f1e  mov     [rbp+hObject], 0
0x180050f26  lea     rdx, [rbp+hObject]
0x180050f2a  mov     rcx, [rbx]
0x180050f2d  call    cs:__imp_UMgrQueryUserToken
0x180050f33  mov     rcx, [rbp+18h]; this
0x180050f37  test    eax, eax
0x180050f39  js      loc_180050FC0
0x180050f3f  mov     rdx, [rdi+8]
0x180050f43  cmp     rdx, [rdi+10h]
0x180050f47  jz      short loc_180050F5D
0x180050f49  mov     rax, [rbp+hObject]
0x180050f4d  mov     [rdx], rax
0x180050f50  xor     ecx, ecx
0x180050f52  mov     [rbp+hObject], rcx
0x180050f56  add     qword ptr [rdi+8], 8
0x180050f5b  jmp     short loc_180050F6D
0x180050f5d  lea     r8, [rbp+hObject]
0x180050f61  mov     rcx, rdi
0x180050f64  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180050f69  mov     rcx, [rbp+hObject]; hObject
0x180050f6d  lea     rax, [rcx-1]
0x180050f71  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180050f75  ja      short loc_180050F7D
0x180050f77  call    cs:__imp_CloseHandle
0x180050f7d  add     rbx, 10h
0x180050f81  cmp     rbx, rsi
0x180050f84  jnz     short loc_180050F1E
0x180050f86  mov     rbx, [rbp+var_18]
0x180050f8a  test    rbx, rbx
0x180050f8d  jz      short loc_180050F98
0x180050f8f  mov     rcx, rbx
0x180050f92  call    cs:__imp_UMgrFreeSessionUsers
0x180050f98  mov     rax, rdi
0x180050f9b  mov     rbx, [rsp+50h+arg_10]
0x180050fa3  add     rsp, 50h
0x180050fa7  pop     rdi
0x180050fa8  pop     rsi
0x180050fa9  pop     rbp
0x180050faa  retn
0x180050fab  mov     r9d, eax; char *
0x180050fae  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180050fb5  mov     edx, 63h ; 'c'; void *
0x180050fba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050fc0  mov     r9d, eax; char *
0x180050fc3  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180050fca  mov     edx, 69h ; 'i'; void *
0x180050fcf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
