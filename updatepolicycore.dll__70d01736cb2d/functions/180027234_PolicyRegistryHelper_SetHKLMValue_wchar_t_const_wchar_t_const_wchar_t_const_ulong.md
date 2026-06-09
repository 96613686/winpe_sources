# PolicyRegistryHelper::SetHKLMValue(wchar_t const *,wchar_t const *,wchar_t const *,ulong)

- ea: `0x180027234`
- end: `0x1800272f3`
- name: `?SetHKLMValue@PolicyRegistryHelper@@SAJPEB_W00K@Z`
- size: `191`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18001f818`
- `0x1800236b8`

## callees

- `0x18000aac0`
- `0x180026c78`
- `0x180027234`
- `0x18002c504`
- `0x18002ffd0`

## string_xrefs

- `0x180027273`: `WindowsUpdate`
- `0x1800272bf`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`

## pseudocode

```c
__int64 __fastcall PolicyRegistryHelper::SetHKLMValue(
        const wchar_t *a1,
        const wchar_t *a2,
        const wchar_t *a3,
        unsigned int a4)
{
  __int64 v6; // rcx
  int RedirectedRegistryKeyName; // ebx
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-238h]
  wchar_t v11[256]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  if ( a3 && *a3 )
  {
    RedirectedRegistryKeyName = PolicyRegistryHelper::GetRedirectedRegistryKeyName(
                                  (wchar_t *)L"WindowsUpdate",
                                  a2,
                                  v11,
                                  (wchar_t **)0x100);
    if ( RedirectedRegistryKeyName >= 0 )
    {
      RedirectedRegistryKeyName = RegSetDwordValue(v6, v11, a3, a4);
      if ( RedirectedRegistryKeyName >= 0 )
        return 0;
      v8 = 204;
    }
    else
    {
      v8 = 202;
    }
  }
  else
  {
    RedirectedRegistryKeyName = -2147024809;
    v8 = 199;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
    (const char *)(unsigned int)RedirectedRegistryKeyName,
    v10);
  return (unsigned int)RedirectedRegistryKeyName;
}

```

## disassembly

```asm
0x180027234  mov     [rsp+arg_0], rbx
0x180027239  push    rbp
0x18002723a  push    rsi
0x18002723b  push    rdi
0x18002723c  sub     rsp, 240h
0x180027243  mov     rax, cs:__security_cookie
0x18002724a  xor     rax, rsp
0x18002724d  mov     [rsp+258h+var_28], rax
0x180027255  xor     ebp, ebp
0x180027257  mov     esi, r9d
0x18002725a  mov     rdi, r8
0x18002725d  test    r8, r8
0x180027260  jz      short loc_1800272AD
0x180027262  cmp     [r8], bp
0x180027266  jz      short loc_1800272AD
0x180027268  mov     r9d, 100h; unsigned __int64
0x18002726e  lea     r8, [rsp+258h+var_228]; wchar_t *
0x180027273  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x18002727a  call    ?GetRedirectedRegistryKeyName@PolicyRegistryHelper@@SAJPEB_W0PEA_W_K@Z; PolicyRegistryHelper::GetRedirectedRegistryKeyName(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x18002727f  mov     ebx, eax
0x180027281  test    eax, eax
0x180027283  jns     short loc_18002728C
0x180027285  mov     edx, 0CAh
0x18002728a  jmp     short loc_1800272B7
0x18002728c  mov     r9d, esi
0x18002728f  lea     rdx, [rsp+258h+var_228]
0x180027294  mov     r8, rdi
0x180027297  call    ?RegSetDwordValue@@YAJPEAUHKEY__@@PEB_W1KW4RegistryHiveType@@@Z; RegSetDwordValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong,RegistryHiveType)
0x18002729c  mov     ebx, eax
0x18002729e  test    eax, eax
0x1800272a0  jns     short loc_1800272A9
0x1800272a2  mov     edx, 0CCh
0x1800272a7  jmp     short loc_1800272B7
0x1800272a9  xor     eax, eax
0x1800272ab  jmp     short loc_1800272D0
0x1800272ad  mov     ebx, 80070057h
0x1800272b2  mov     edx, 0C7h; void *
0x1800272b7  mov     rcx, [rsp+258h]; this
0x1800272bf  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x1800272c6  mov     r9d, ebx; char *
0x1800272c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800272ce  mov     eax, ebx
0x1800272d0  mov     rcx, [rsp+258h+var_28]
0x1800272d8  xor     rcx, rsp; StackCookie
0x1800272db  call    __security_check_cookie
0x1800272e0  mov     rbx, [rsp+258h+arg_0]
0x1800272e8  add     rsp, 240h
0x1800272ef  pop     rdi
0x1800272f0  pop     rsi
0x1800272f1  pop     rbp
0x1800272f2  retn
```
