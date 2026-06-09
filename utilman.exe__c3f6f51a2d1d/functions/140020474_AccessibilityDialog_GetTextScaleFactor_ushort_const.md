# AccessibilityDialog::GetTextScaleFactor(ushort const *)

- ea: `0x140020474`
- end: `0x14002059f`
- name: `?GetTextScaleFactor@AccessibilityDialog@@AEAAHPEBG@Z`
- size: `299`
- prototype: `__int64 __fastcall(AccessibilityDialog *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400206e8`

## callees

- `0x140002480`
- `0x140002fa0`
- `0x140013d0c`
- `0x14001cadc`
- `0x140020474`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140020508`
- `ADVAPI32!RegOpenKeyExW` at `0x140020508`
- `ADVAPI32!RegQueryValueExW` at `0x14002054a`
- `ADVAPI32!RegQueryValueExW` at `0x14002054a`

## string_xrefs

- `0x1400204b9`: `\AnyoneRead\Accessibility`
- `0x1400204c3`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData\`

## pseudocode

```c
__int64 __fastcall AccessibilityDialog::GetTextScaleFactor(AccessibilityDialog *this, const unsigned __int16 *a2)
{
  unsigned int v3; // edi
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-C0h] BYREF

  v3 = 100;
  memset_0(SubKey, 0, 0x208u);
  swprintf_s<260>(
    SubKey,
    L"%ls%ls%ls",
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData\\",
    a2,
    L"\\AnyoneRead\\Accessibility");
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"TextScaleFactor", 0, 0, Data, &cbData) && *(int *)Data > 100 )
    {
      v3 = *(_DWORD *)Data;
      if ( *(int *)Data >= 225 )
        v3 = 225;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v3;
}

```

## disassembly

```asm
0x140020474  mov     [rsp-8+arg_0], rbx
0x140020479  mov     [rsp-8+arg_10], rdi
0x14002047e  push    rbp
0x14002047f  lea     rbp, [rsp-160h]
0x140020487  sub     rsp, 260h
0x14002048e  mov     rax, cs:__security_cookie
0x140020495  xor     rax, rsp
0x140020498  mov     [rbp+160h+var_10], rax
0x14002049f  mov     rbx, rdx
0x1400204a2  lea     rcx, [rsp+260h+SubKey]; void *
0x1400204a7  xor     edx, edx; Val
0x1400204a9  mov     r8d, 208h; Size
0x1400204af  mov     edi, 64h ; 'd'
0x1400204b4  call    memset_0
0x1400204b9  lea     rax, aAnyonereadAcce; "\\AnyoneRead\\Accessibility"
0x1400204c0  mov     r9, rbx
0x1400204c3  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400204ca  mov     [rsp+260h+phkResult], rax
0x1400204cf  lea     rdx, aLsLsLs; "%ls%ls%ls"
0x1400204d6  lea     rcx, [rsp+260h+SubKey]
0x1400204db  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@GPEBGZZ; swprintf_s<260>(ushort (&)[260],ushort const *,...)
0x1400204e0  lea     rax, [rsp+260h+hKey]
0x1400204e5  mov     [rsp+260h+hKey], 0
0x1400204ee  mov     r9d, 20019h; samDesired
0x1400204f4  mov     [rsp+260h+phkResult], rax; phkResult
0x1400204f9  xor     r8d, r8d; ulOptions
0x1400204fc  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x140020501  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140020508  call    cs:__imp_RegOpenKeyExW
0x14002050f  nop     dword ptr [rax+rax+00h]
0x140020514  test    eax, eax
0x140020516  jnz     short loc_14002056E
0x140020518  mov     rcx, [rsp+260h+hKey]; hKey
0x14002051d  lea     rdx, aTextscalefacto; "TextScaleFactor"
0x140020524  mov     dword ptr [rsp+260h+Data], eax
0x140020528  xor     r9d, r9d; lpType
0x14002052b  lea     rax, [rsp+260h+cbData]
0x140020530  mov     [rsp+260h+cbData], 4
0x140020538  mov     [rsp+260h+lpcbData], rax; lpcbData
0x14002053d  xor     r8d, r8d; lpReserved
0x140020540  lea     rax, [rsp+260h+Data]
0x140020545  mov     [rsp+260h+phkResult], rax; lpData
0x14002054a  call    cs:__imp_RegQueryValueExW
0x140020551  nop     dword ptr [rax+rax+00h]
0x140020556  test    eax, eax
0x140020558  jnz     short loc_14002056E
0x14002055a  cmp     dword ptr [rsp+260h+Data], edi
0x14002055e  jle     short loc_14002056E
0x140020560  mov     edi, dword ptr [rsp+260h+Data]
0x140020564  mov     eax, 0E1h
0x140020569  cmp     edi, eax
0x14002056b  cmovge  edi, eax
0x14002056e  lea     rcx, [rsp+260h+hKey]
0x140020573  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140020578  mov     eax, edi
0x14002057a  mov     rcx, [rbp+160h+var_10]
0x140020581  xor     rcx, rsp; StackCookie
0x140020584  call    __security_check_cookie
0x140020589  lea     r11, [rsp+260h+var_s0]
0x140020591  mov     rbx, [r11+10h]
0x140020595  mov     rdi, [r11+20h]
0x140020599  mov     rsp, r11
0x14002059c  pop     rbp
0x14002059d  retn
```
