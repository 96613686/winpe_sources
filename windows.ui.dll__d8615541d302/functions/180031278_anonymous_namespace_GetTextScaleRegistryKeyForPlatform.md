# _anonymous_namespace_::GetTextScaleRegistryKeyForPlatform

- ea: `0x180031278`
- end: `0x180031361`
- name: `_anonymous_namespace_::GetTextScaleRegistryKeyForPlatform`
- size: `233`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180031190`

## callees

- `0x180031278`
- `0x180031368`
- `0x1800313b8`
- `0x180031430`
- `0x1800315a4`
- `0x180033610`
- `0x180033634`
- `0x18004ed78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800312c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800312c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003134b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003134b`

## string_xrefs

- `0x1800312b6`: `Software\Microsoft\Accessibility`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PHKEY __fastcall anonymous_namespace_::GetTextScaleRegistryKeyForPlatform(PHKEY phkResult)
{
  HKEY v2; // rdi
  int v3; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  int OneCoreRegistryKey; // eax
  int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v10; // [rsp+40h] [rbp+8h] BYREF

  *phkResult = 0;
  if ( (unsigned __int8)anonymous_namespace_::IsDesktop() )
  {
    v2 = *phkResult;
    if ( *phkResult )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
      RegCloseKey(v2);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
    }
    *phkResult = 0;
    v3 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Accessibility", 0, 0x20019u, phkResult);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
      (const char *)(unsigned int)v3,
      1,
      2);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      phkResult,
      0);
    OneCoreRegistryKey = anonymous_namespace_::GetOneCoreRegistryKey(phkResult, v5, v6);
    if ( OneCoreRegistryKey < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x262,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
        (const char *)(unsigned int)OneCoreRegistryKey,
        phkResulta);
  }
  return phkResult;
}

```

## disassembly

```asm
0x180031278  mov     [rsp+arg_8], rbx
0x18003127d  push    rdi
0x18003127e  sub     rsp, 30h
0x180031282  mov     rbx, rcx
0x180031285  mov     qword ptr [rcx], 0
0x18003128c  call    _anonymous_namespace___IsDesktop
0x180031291  test    al, al
0x180031293  jz      short loc_18003130D
0x180031295  mov     rdi, [rbx]
0x180031298  test    rdi, rdi
0x18003129b  jnz     loc_18003133E
0x1800312a1  mov     qword ptr [rbx], 0
0x1800312a8  mov     [rsp+38h+phkResult], rbx; phkResult
0x1800312ad  mov     r9d, 20019h; samDesired
0x1800312b3  xor     r8d, r8d; ulOptions
0x1800312b6  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Accessibility"
0x1800312bd  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800312c4  call    cs:__imp_RegOpenKeyExW
0x1800312ca  test    eax, eax
0x1800312cc  jle     short loc_1800312D6
0x1800312ce  movzx   eax, ax
0x1800312d1  or      eax, 80070000h
0x1800312d6  mov     rcx, [rsp+38h]; this
0x1800312db  mov     dword ptr [rsp+38h+var_10], 80070002h; char
0x1800312e3  mov     dword ptr [rsp+38h+phkResult], 1; int
0x1800312eb  mov     r9d, eax; char *
0x1800312ee  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x1800312f5  mov     edx, 24Fh; void *
0x1800312fa  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x1800312ff  mov     rax, rbx
0x180031302  mov     rbx, [rsp+38h+arg_8]
0x180031307  add     rsp, 30h
0x18003130b  pop     rdi
0x18003130c  retn
0x18003130d  xor     edx, edx
0x18003130f  mov     rcx, rbx
0x180031312  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180031317  mov     rcx, rbx
0x18003131a  call    _anonymous_namespace___GetOneCoreRegistryKey
0x18003131f  test    eax, eax
0x180031321  jns     short loc_1800312FF
0x180031323  mov     rcx, [rsp+38h]; this
0x180031328  mov     r9d, eax; char *
0x18003132b  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x180031332  mov     edx, 262h; void *
0x180031337  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003133c  jmp     short loc_1800312FF
0x18003133e  lea     rcx, [rsp+38h+arg_0]; this
0x180031343  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180031348  mov     rcx, rdi; hKey
0x18003134b  call    cs:__imp_RegCloseKey
0x180031351  lea     rcx, [rsp+38h+arg_0]; this
0x180031356  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003135b  nop
0x18003135c  jmp     loc_1800312A1
```
