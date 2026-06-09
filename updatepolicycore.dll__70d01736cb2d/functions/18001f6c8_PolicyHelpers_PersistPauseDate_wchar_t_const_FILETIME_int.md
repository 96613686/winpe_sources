# PolicyHelpers::PersistPauseDate(wchar_t const *,_FILETIME,int)

- ea: `0x18001f6c8`
- end: `0x18001f80f`
- name: `?PersistPauseDate@PolicyHelpers@@SAJPEB_WU_FILETIME@@H@Z`
- size: `327`
- prototype: `__int64 __fastcall(const wchar_t *, struct _FILETIME, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180017014`
- `0x1800176d4`

## callees

- `0x18000aac0`
- `0x18001f6c8`
- `0x180026c78`
- `0x18002c594`
- `0x18002c610`
- `0x18002ffd0`

## string_xrefs

- `0x18001f710`: `\UpdatePolicy\Settings`
- `0x18001f780`: `\UpdatePolicy\Settings`
- `0x18001f717`: `WindowsUpdate`
- `0x18001f787`: `WindowsUpdate`
- `0x18001f7dc`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`

## pseudocode

```c
__int64 __fastcall PolicyHelpers::PersistPauseDate(const wchar_t *a1, struct _FILETIME a2, int a3)
{
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  int v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  int RedirectedRegistryKeyName; // eax
  __int64 v12; // rcx
  struct _FILETIME *v14; // [rsp+20h] [rbp-238h]
  struct _FILETIME v15; // [rsp+30h] [rbp-228h] BYREF
  wchar_t v16[256]; // [rsp+40h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  if ( !a3 )
  {
    if ( a1 && *a1 )
    {
      RedirectedRegistryKeyName = PolicyRegistryHelper::GetRedirectedRegistryKeyName(
                                    (wchar_t *)L"WindowsUpdate",
                                    L"\\UpdatePolicy\\Settings",
                                    v16,
                                    (wchar_t **)0x100);
      v7 = RedirectedRegistryKeyName;
      if ( RedirectedRegistryKeyName < 0 )
      {
        v8 = (unsigned int)RedirectedRegistryKeyName;
        v9 = 247;
        goto LABEL_20;
      }
      v7 = RegDelValue(v12, v16, a1);
      if ( (unsigned int)(v7 + 2147024894) <= 1 || v7 >= 0 )
        return 0;
      v9 = 257;
LABEL_19:
      v8 = (unsigned int)v7;
      goto LABEL_20;
    }
    v9 = 244;
LABEL_18:
    v7 = -2147024809;
    goto LABEL_19;
  }
  v15 = a2;
  if ( !a1 || !*a1 )
  {
    v9 = 215;
    goto LABEL_18;
  }
  v4 = PolicyRegistryHelper::GetRedirectedRegistryKeyName(
         (wchar_t *)L"WindowsUpdate",
         L"\\UpdatePolicy\\Settings",
         v16,
         (wchar_t **)0x100);
  v7 = v4;
  if ( v4 < 0 )
  {
    v8 = (unsigned int)v4;
    v9 = 218;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
      (const char *)v8,
      (int)v14);
    return (unsigned int)v7;
  }
  v14 = &v15;
  v10 = RegSetFileTimeValue_Helper(v5, v16, v6, a1);
  v7 = v10;
  if ( v10 < 0 )
  {
    v8 = (unsigned int)v10;
    v9 = 220;
    goto LABEL_20;
  }
  return 0;
}

```

## disassembly

```asm
0x18001f6c8  mov     [rsp+arg_10], rbx
0x18001f6cd  mov     [rsp+arg_18], rsi
0x18001f6d2  push    rdi
0x18001f6d3  sub     rsp, 250h
0x18001f6da  mov     rax, cs:__security_cookie
0x18001f6e1  xor     rax, rsp
0x18001f6e4  mov     [rsp+258h+var_18], rax
0x18001f6ec  xor     esi, esi
0x18001f6ee  mov     rdi, rcx
0x18001f6f1  test    r8d, r8d
0x18001f6f4  jz      short loc_18001F76B
0x18001f6f6  mov     [rsp+258h+var_228], rdx
0x18001f6fb  test    rcx, rcx
0x18001f6fe  jz      short loc_18001F764
0x18001f700  cmp     [rcx], si
0x18001f703  jz      short loc_18001F764
0x18001f705  mov     r9d, 100h; unsigned __int64
0x18001f70b  lea     r8, [rsp+258h+var_218]; wchar_t *
0x18001f710  lea     rdx, aUpdatepolicySe; "\\UpdatePolicy\\Settings"
0x18001f717  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x18001f71e  call    ?GetRedirectedRegistryKeyName@PolicyRegistryHelper@@SAJPEB_W0PEA_W_K@Z; PolicyRegistryHelper::GetRedirectedRegistryKeyName(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x18001f723  mov     ebx, eax
0x18001f725  test    eax, eax
0x18001f727  jns     short loc_18001F736
0x18001f729  mov     r9d, eax
0x18001f72c  mov     edx, 0DAh
0x18001f731  jmp     loc_18001F7D4
0x18001f736  lea     rax, [rsp+258h+var_228]
0x18001f73b  mov     r9, rdi
0x18001f73e  lea     rdx, [rsp+258h+var_218]
0x18001f743  mov     [rsp+258h+var_238], rax
0x18001f748  call    ?RegSetFileTimeValue_Helper@@YAJPEAUHKEY__@@PEB_W11AEBU_FILETIME@@W4RegistryHiveType@@@Z; RegSetFileTimeValue_Helper(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,_FILETIME const &,RegistryHiveType)
0x18001f74d  mov     ebx, eax
0x18001f74f  test    eax, eax
0x18001f751  jns     short loc_18001F75D
0x18001f753  mov     r9d, eax
0x18001f756  mov     edx, 0DCh
0x18001f75b  jmp     short loc_18001F7D4
0x18001f75d  mov     ebx, esi
0x18001f75f  jmp     loc_18001F7E8
0x18001f764  mov     edx, 0D7h
0x18001f769  jmp     short loc_18001F7CC
0x18001f76b  test    rdi, rdi
0x18001f76e  jz      short loc_18001F7C7
0x18001f770  cmp     [rcx], si
0x18001f773  jz      short loc_18001F7C7
0x18001f775  mov     r9d, 100h; unsigned __int64
0x18001f77b  lea     r8, [rsp+258h+var_218]; wchar_t *
0x18001f780  lea     rdx, aUpdatepolicySe; "\\UpdatePolicy\\Settings"
0x18001f787  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x18001f78e  call    ?GetRedirectedRegistryKeyName@PolicyRegistryHelper@@SAJPEB_W0PEA_W_K@Z; PolicyRegistryHelper::GetRedirectedRegistryKeyName(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x18001f793  mov     ebx, eax
0x18001f795  test    eax, eax
0x18001f797  jns     short loc_18001F7A3
0x18001f799  mov     r9d, eax
0x18001f79c  mov     edx, 0F7h
0x18001f7a1  jmp     short loc_18001F7D4
0x18001f7a3  mov     r8, rdi
0x18001f7a6  lea     rdx, [rsp+258h+var_218]
0x18001f7ab  call    ?RegDelValue@@YAJPEAUHKEY__@@PEB_W1W4RegistryHiveType@@@Z; RegDelValue(HKEY__ *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x18001f7b0  mov     ebx, eax
0x18001f7b2  add     eax, 7FF8FFFEh
0x18001f7b7  cmp     eax, 1
0x18001f7ba  jbe     short loc_18001F75D
0x18001f7bc  test    ebx, ebx
0x18001f7be  jns     short loc_18001F75D
0x18001f7c0  mov     edx, 101h
0x18001f7c5  jmp     short loc_18001F7D1
0x18001f7c7  mov     edx, 0F4h; void *
0x18001f7cc  mov     ebx, 80070057h
0x18001f7d1  mov     r9d, ebx; char *
0x18001f7d4  mov     rcx, [rsp+258h]; this
0x18001f7dc  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18001f7e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f7e8  mov     eax, ebx
0x18001f7ea  mov     rcx, [rsp+258h+var_18]
0x18001f7f2  xor     rcx, rsp; StackCookie
0x18001f7f5  call    __security_check_cookie
0x18001f7fa  lea     r11, [rsp+258h+var_8]
0x18001f802  mov     rbx, [r11+20h]
0x18001f806  mov     rsi, [r11+28h]
0x18001f80a  mov     rsp, r11
0x18001f80d  pop     rdi
0x18001f80e  retn
```
