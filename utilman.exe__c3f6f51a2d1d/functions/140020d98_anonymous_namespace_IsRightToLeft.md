# _anonymous_namespace_::IsRightToLeft

- ea: `0x140020d98`
- end: `0x140020e9f`
- name: `_anonymous_namespace_::IsRightToLeft`
- size: `263`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14001f948`
- `0x1400212ec`

## callees

- `0x14000347c`
- `0x14001f3ec`
- `0x140020d98`
- `0x140022dcc`

## import_xrefs

- `KERNEL32!GetThreadPreferredUILanguages` at `0x140020dc7`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x140020e21`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x140020dc7`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x140020e21`
- `KERNEL32!GetLocaleInfoEx` at `0x140020e5d`
- `KERNEL32!GetLocaleInfoEx` at `0x140020e5d`

## string_xrefs

- `0x140020ddc`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`
- `0x140020e36`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`
- `0x140020e6d`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool anonymous_namespace_::IsRightToLeft()
{
  BOOL ThreadPreferredUILanguages; // eax
  const char *v1; // r9
  WCHAR *v2; // rbx
  const char *v3; // r9
  const char *v4; // r9
  bool v5; // bl
  const char *v6; // r9
  bool result; // al
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  ULONG pcchLanguagesBuffer; // [rsp+40h] [rbp+8h] BYREF
  ULONG pulNumLanguages; // [rsp+48h] [rbp+10h] BYREF
  int LCData; // [rsp+50h] [rbp+18h] BYREF
  WCHAR *v12; // [rsp+58h] [rbp+20h] BYREF

  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  LCData = 0;
  ThreadPreferredUILanguages = GetThreadPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer);
  try
  {
    if ( !ThreadPreferredUILanguages )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x72,
        (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
        v1);
    v2 = (WCHAR *)operator new[](saturated_mul(pcchLanguagesBuffer, 2u));
    v12 = v2;
    if ( !GetThreadPreferredUILanguages(8u, &pulNumLanguages, v2, &pcchLanguagesBuffer) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x78,
        (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
        v3);
    if ( !GetLocaleInfoEx(v2, 0x20000070u, (LPWSTR)&LCData, 2) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x7F,
        (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
        v4);
    v5 = LCData == 1;
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v12);
    result = v5;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x85,
      (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
      v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140020d98  mov     rax, rsp
0x140020d9b  push    rbx
0x140020d9c  push    rdi
0x140020d9d  sub     rsp, 28h
0x140020da1  mov     dword ptr [rax+10h], 0
0x140020da8  mov     dword ptr [rax+8], 0
0x140020daf  mov     dword ptr [rax+18h], 0
0x140020db6  lea     r9, [rax+8]; pcchLanguagesBuffer
0x140020dba  xor     r8d, r8d; pwszLanguagesBuffer
0x140020dbd  lea     rdx, [rax+10h]; pulNumLanguages
0x140020dc1  lea     edi, [r8+8]
0x140020dc5  mov     ecx, edi; dwFlags
0x140020dc7  call    cs:__imp_GetThreadPreferredUILanguages
0x140020dce  nop     dword ptr [rax+rax+00h]
0x140020dd3  mov     rcx, [rsp+38h]; this
0x140020dd8  test    eax, eax
0x140020dda  jnz     short loc_140020DEB
0x140020ddc  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x140020de3  lea     edx, [rdi+6Ah]; void *
0x140020de6  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140020deb  mov     ecx, [rsp+38h+pcchLanguagesBuffer]
0x140020def  mov     eax, 2
0x140020df4  mul     rcx
0x140020df7  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x140020dfe  cmovb   rax, rdx
0x140020e02  mov     rcx, rax; unsigned __int64
0x140020e05  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140020e0a  mov     rbx, rax
0x140020e0d  mov     [rsp+38h+arg_18], rax
0x140020e12  lea     r9, [rsp+38h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x140020e17  mov     r8, rax; pwszLanguagesBuffer
0x140020e1a  lea     rdx, [rsp+38h+pulNumLanguages]; pulNumLanguages
0x140020e1f  mov     ecx, edi; dwFlags
0x140020e21  call    cs:__imp_GetThreadPreferredUILanguages
0x140020e28  nop     dword ptr [rax+rax+00h]
0x140020e2d  mov     rcx, [rsp+38h]; this
0x140020e32  test    eax, eax
0x140020e34  jnz     short loc_140020E45
0x140020e36  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x140020e3d  lea     edx, [rax+78h]; void *
0x140020e40  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140020e45  mov     rdi, [rsp+38h]
0x140020e4a  mov     r9d, 2; cchData
0x140020e50  lea     r8, [rsp+38h+LCData]; lpLCData
0x140020e55  mov     edx, 20000070h; LCType
0x140020e5a  mov     rcx, rbx; lpLocaleName
0x140020e5d  call    cs:__imp_GetLocaleInfoEx
0x140020e64  nop     dword ptr [rax+rax+00h]
0x140020e69  test    eax, eax
0x140020e6b  jnz     short loc_140020E7F
0x140020e6d  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x140020e74  lea     edx, [rax+7Fh]; void *
0x140020e77  mov     rcx, rdi; this
0x140020e7a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140020e7f  cmp     [rsp+38h+LCData], 1
0x140020e84  setz    bl
0x140020e87  lea     rcx, [rsp+38h+arg_18]
0x140020e8c  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x140020e91  mov     al, bl
0x140020e93  jmp     short loc_140020E97
0x140020e95  xor     al, al
0x140020e97  add     rsp, 28h
0x140020e9b  pop     rdi
0x140020e9c  pop     rbx
0x140020e9d  retn
```
