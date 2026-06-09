# winrt::WindowsUdk::Storage::implementation::GetThreadImpersonationToken

- ea: `0x180148ab0`
- end: `0x180148b45`
- name: `winrt::WindowsUdk::Storage::implementation::GetThreadImpersonationToken`
- size: `149`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800bda20`
- `0x1800bde50`
- `0x1800be690`
- `0x1801489e8`
- `0x18030d310`
- `0x18030d9e0`
- `0x18030f680`

## callees

- `0x1800e4df4`
- `0x180148ab0`
- `0x1801588c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148b14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180148ae8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180148ae8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180148afe`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180148afe`

## string_xrefs

- `0x180148b26`: `shellcommon\undockeddevkit\libs\windowsudk.storage\cloudstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::WindowsUdk::Storage::implementation::GetThreadImpersonationToken(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  BOOL v3; // ebx
  const char *v4; // r9
  _QWORD *v6; // [rsp+28h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+30h] [rbp-18h] BYREF
  char v8; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  v6 = a1;
  TokenHandle = 0;
  v8 = 1;
  CurrentThread = GetCurrentThread();
  v3 = OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v6);
  if ( !v3 && GetLastError() != 1008 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2D,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.storage\\cloudstore.cpp",
      v4);
  return a1;
}

```

## disassembly

```asm
0x180148ab0  mov     rax, rsp
0x180148ab3  mov     [rax+10h], rbx
0x180148ab7  mov     [rax+8], rcx
0x180148abb  push    rdi
0x180148abc  sub     rsp, 40h
0x180148ac0  mov     rdi, rcx
0x180148ac3  mov     dword ptr [rax-28h], 0
0x180148aca  mov     qword ptr [rcx], 0
0x180148ad1  mov     ebx, 1
0x180148ad6  mov     [rax-28h], ebx
0x180148ad9  mov     [rax-20h], rcx
0x180148add  mov     qword ptr [rax-18h], 0
0x180148ae5  mov     [rax-10h], bl
0x180148ae8  call    cs:__imp_GetCurrentThread
0x180148aee  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180148af3  mov     r8d, ebx; OpenAsSelf
0x180148af6  mov     edx, 0F01FFh; DesiredAccess
0x180148afb  mov     rcx, rax; ThreadHandle
0x180148afe  call    cs:__imp_OpenThreadToken
0x180148b04  mov     ebx, eax
0x180148b06  lea     rcx, [rsp+48h+var_20]
0x180148b0b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180148b10  test    ebx, ebx
0x180148b12  jnz     short loc_180148B36
0x180148b14  call    cs:__imp_GetLastError
0x180148b1a  cmp     eax, 3F0h
0x180148b1f  jz      short loc_180148B36
0x180148b21  mov     rcx, [rsp+48h]; this
0x180148b26  lea     r8, aShellcommonUnd_50; "shellcommon\\undockeddevkit\\libs\\wind"...
0x180148b2d  lea     edx, [rbx+2Dh]; void *
0x180148b30  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180148b36  mov     rax, rdi
0x180148b39  mov     rbx, [rsp+48h+arg_8]
0x180148b3e  add     rsp, 40h
0x180148b42  pop     rdi
0x180148b43  retn
```
