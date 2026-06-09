# CliUtils::GetThisHandle(bool)

- ea: `0x180008390`
- end: `0x180008400`
- name: `?GetThisHandle@CliUtils@@SAPEAUHINSTANCE__@@_N@Z`
- size: `112`
- prototype: `HINSTANCE __fastcall(unsigned __int8)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180008408`
- `0x18000884c`

## callees

- `0x180008390`
- `0x18000d9fc`
- `0x180010310`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800083c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800083c9`

## string_xrefs

- `0x1800083eb`: `C:\__w\1\s\src\updatecli\libs\_inc\CliUtils.hpp`

## pseudocode

```c
HINSTANCE __fastcall CliUtils::GetThisHandle(unsigned __int8 a1)
{
  const char *v1; // r9
  HMODULE phModule; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  phModule = 0;
  if ( !GetModuleHandleExW(2 * a1 + 4, (LPCWSTR)CliUtils::GetThisHandle, &phModule) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x11,
      (unsigned int)"C:\\__w\\1\\s\\src\\updatecli\\libs\\_inc\\CliUtils.hpp",
      v1);
  return phModule;
}

```

## disassembly

```asm
0x180008390  push    rbx
0x180008392  sub     rsp, 30h
0x180008396  mov     rax, cs:__security_cookie
0x18000839d  xor     rax, rsp
0x1800083a0  mov     [rsp+38h+var_10], rax
0x1800083a5  mov     [rsp+38h+phModule], 0
0x1800083ae  mov     rbx, [rsp+38h]
0x1800083b3  movzx   ecx, cl
0x1800083b6  lea     ecx, ds:4[rcx*2]; dwFlags
0x1800083bd  lea     r8, [rsp+38h+phModule]; phModule
0x1800083c2  lea     rdx, ?GetThisHandle@CliUtils@@SAPEAUHINSTANCE__@@_N@Z; lpModuleName
0x1800083c9  call    cs:__imp_GetModuleHandleExW
0x1800083cf  test    eax, eax
0x1800083d1  jz      short loc_1800083EB
0x1800083d3  mov     rax, [rsp+38h+phModule]
0x1800083d8  mov     rcx, [rsp+38h+var_10]
0x1800083dd  xor     rcx, rsp; StackCookie
0x1800083e0  call    __security_check_cookie
0x1800083e5  add     rsp, 30h
0x1800083e9  pop     rbx
0x1800083ea  retn
0x1800083eb  lea     r8, aCW1SSrcUpdatec_0; "C:\\__w\\1\\s\\src\\updatecli\\libs\\_i"...
0x1800083f2  mov     edx, 11h; void *
0x1800083f7  mov     rcx, rbx; this
0x1800083fa  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
