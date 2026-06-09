# Windows::DockedHelpers::_anonymous_namespace_::GetDockedComponentFunc

- ea: `0x180063a54`
- end: `0x180063af8`
- name: `Windows::DockedHelpers::_anonymous_namespace_::GetDockedComponentFunc`
- size: `164`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180063b00`
- `0x180063c38`
- `0x180063d70`
- `0x180063ea8`

## callees

- `0x180043f2c`
- `0x180063968`
- `0x180063a54`
- `0x1800dd768`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063ab3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063ab3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180063a85`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180063a85`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180063ac8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180063ac8`

## string_xrefs

- `0x180063aac`: `GetDockedComponent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::DockedHelpers::_anonymous_namespace_::GetDockedComponentFunc()
{
  HMODULE UsoDockedModule; // rax
  __int64 v1; // rdx
  __int64 v2; // rcx
  WINBOOL fPending; // [rsp+30h] [rbp-18h] BYREF

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&stru_180150268, 0, &fPending, 0) )
    abort();
  if ( fPending )
  {
    UsoDockedModule = Windows::DockedHelpers::_anonymous_namespace_::GetUsoDockedModule();
    qword_180150260 = (__int64)GetProcAddress(UsoDockedModule, "GetDockedComponent");
    if ( !InitOnceComplete(&stru_180150268, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v2, v1);
  }
  return qword_180150260;
}

```

## disassembly

```asm
0x180063a54  push    rbx
0x180063a56  sub     rsp, 40h
0x180063a5a  mov     rax, cs:__security_cookie
0x180063a61  xor     rax, rsp
0x180063a64  mov     [rsp+48h+var_10], rax
0x180063a69  mov     [rsp+48h+fPending], 0
0x180063a71  xor     r9d, r9d; lpContext
0x180063a74  lea     r8, [rsp+48h+fPending]; fPending
0x180063a79  xor     edx, edx; dwFlags
0x180063a7b  lea     rbx, stru_180150268
0x180063a82  mov     rcx, rbx; lpInitOnce
0x180063a85  call    cs:__imp___std_init_once_begin_initialize
0x180063a8b  test    eax, eax
0x180063a8d  jz      short loc_180063AF2
0x180063a8f  cmp     [rsp+48h+fPending], 0
0x180063a94  jz      short loc_180063AD2
0x180063a96  mov     [rsp+48h+var_28], rbx
0x180063a9b  mov     [rsp+48h+var_20], 4
0x180063aa4  call    Windows__DockedHelpers___anonymous_namespace___GetUsoDockedModule
0x180063aa9  mov     rcx, rax; hModule
0x180063aac  lea     rdx, aGetdockedcompo; "GetDockedComponent"
0x180063ab3  call    cs:__imp_GetProcAddress
0x180063ab9  mov     cs:qword_180150260, rax
0x180063ac0  xor     r8d, r8d; lpContext
0x180063ac3  xor     edx, edx; dwFlags
0x180063ac5  mov     rcx, rbx; lpInitOnce
0x180063ac8  call    cs:__imp_InitOnceComplete
0x180063ace  test    eax, eax
0x180063ad0  jz      short loc_180063AEC
0x180063ad2  mov     rax, cs:qword_180150260
0x180063ad9  mov     rcx, [rsp+48h+var_10]
0x180063ade  xor     rcx, rsp; StackCookie
0x180063ae1  call    __security_check_cookie
0x180063ae6  add     rsp, 40h
0x180063aea  pop     rbx
0x180063aeb  retn
0x180063aec  call    __std_init_once_link_alternate_names_and_abort
0x180063af2  call    abort
```
