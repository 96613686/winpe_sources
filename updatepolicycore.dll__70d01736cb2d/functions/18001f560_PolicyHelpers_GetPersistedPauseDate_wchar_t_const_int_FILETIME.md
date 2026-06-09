# PolicyHelpers::GetPersistedPauseDate(wchar_t const *,int *,_FILETIME *)

- ea: `0x18001f560`
- end: `0x18001f6bf`
- name: `?GetPersistedPauseDate@PolicyHelpers@@SAJPEB_WPEAHPEAU_FILETIME@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(const wchar_t *, int *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180017014`

## callees

- `0x18000aac0`
- `0x18001f560`
- `0x180026c78`
- `0x180027058`
- `0x18002c288`
- `0x18002ffd0`

## string_xrefs

- `0x18001f5be`: `\UpdatePolicy\Settings`
- `0x18001f5f7`: `\UpdatePolicy\Settings`
- `0x18001f5b7`: `WindowsUpdate`
- `0x18001f5fe`: `WindowsUpdate`
- `0x18001f643`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`
- `0x18001f674`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`

## pseudocode

```c
__int64 __fastcall PolicyHelpers::GetPersistedPauseDate(const wchar_t *a1, int *a2, struct _FILETIME *a3)
{
  bool v6; // di
  int v7; // eax
  unsigned int v8; // ebx
  int RedirectedRegistryKeyName; // eax
  __int64 v10; // rcx
  __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // esi
  int v16; // [rsp+20h] [rbp-258h]
  bool v17; // [rsp+30h] [rbp-248h] BYREF
  struct _FILETIME v18; // [rsp+38h] [rbp-240h] BYREF
  wchar_t v19[256]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v17 = 0;
  v18 = 0;
  v6 = 0;
  if ( !a3 || !a2 )
  {
    v8 = -2147467261;
    goto LABEL_16;
  }
  v7 = PolicyRegistryHelper::HKLMValueExists(L"WindowsUpdate", L"\\UpdatePolicy\\Settings", a1, &v17);
  v6 = v17;
  v8 = v7;
  if ( v7 >= 0 && v17 )
  {
    if ( !a1 || !*a1 )
    {
      v8 = -2147024809;
      v12 = 148;
      v11 = 2147942487LL;
      goto LABEL_14;
    }
    RedirectedRegistryKeyName = PolicyRegistryHelper::GetRedirectedRegistryKeyName(
                                  (wchar_t *)L"WindowsUpdate",
                                  L"\\UpdatePolicy\\Settings",
                                  v19,
                                  (wchar_t **)0x100);
    v8 = RedirectedRegistryKeyName;
    if ( RedirectedRegistryKeyName < 0 )
    {
      v11 = (unsigned int)RedirectedRegistryKeyName;
      v12 = 151;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
        (const char *)v11,
        v16);
      goto LABEL_16;
    }
    v13 = RegQueryFileTimeValue(v10, v19, a1, &v18);
    v14 = v13;
    if ( v13 >= 0 )
    {
      v8 = 0;
    }
    else
    {
      v8 = -2147024894;
      if ( v13 != -2147024894 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9A,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
          (const char *)(unsigned int)v13,
          v16);
        v8 = v14;
      }
    }
  }
LABEL_16:
  *a3 = v18;
  *a2 = v6;
  return v8;
}

```

## disassembly

```asm
0x18001f560  mov     [rsp+arg_18], rbx
0x18001f565  push    rbp
0x18001f566  push    rsi
0x18001f567  push    rdi
0x18001f568  push    r14
0x18001f56a  push    r15
0x18001f56c  sub     rsp, 250h
0x18001f573  mov     rax, cs:__security_cookie
0x18001f57a  xor     rax, rsp
0x18001f57d  mov     [rsp+278h+var_38], rax
0x18001f585  xor     ebp, ebp
0x18001f587  mov     r15, r8
0x18001f58a  mov     [rsp+278h+var_248], bpl
0x18001f58f  mov     r14, rdx
0x18001f592  mov     [rsp+278h+var_240], rbp
0x18001f597  mov     rsi, rcx
0x18001f59a  mov     dil, bpl
0x18001f59d  test    r8, r8
0x18001f5a0  jz      loc_18001F682
0x18001f5a6  test    rdx, rdx
0x18001f5a9  jz      loc_18001F682
0x18001f5af  mov     r8, rcx; wchar_t *
0x18001f5b2  lea     r9, [rsp+278h+var_248]; bool *
0x18001f5b7  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x18001f5be  lea     rdx, aUpdatepolicySe; "\\UpdatePolicy\\Settings"
0x18001f5c5  call    ?HKLMValueExists@PolicyRegistryHelper@@SAJPEB_W00AEA_N@Z; PolicyRegistryHelper::HKLMValueExists(wchar_t const *,wchar_t const *,wchar_t const *,bool &)
0x18001f5ca  mov     dil, [rsp+278h+var_248]
0x18001f5cf  mov     ebx, eax
0x18001f5d1  test    eax, eax
0x18001f5d3  js      loc_18001F687
0x18001f5d9  test    dil, dil
0x18001f5dc  jz      loc_18001F687
0x18001f5e2  test    rsi, rsi
0x18001f5e5  jz      short loc_18001F65F
0x18001f5e7  cmp     [rsi], bp
0x18001f5ea  jz      short loc_18001F65F
0x18001f5ec  mov     r9d, 100h; unsigned __int64
0x18001f5f2  lea     r8, [rsp+278h+var_238]; wchar_t *
0x18001f5f7  lea     rdx, aUpdatepolicySe; "\\UpdatePolicy\\Settings"
0x18001f5fe  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x18001f605  call    ?GetRedirectedRegistryKeyName@PolicyRegistryHelper@@SAJPEB_W0PEA_W_K@Z; PolicyRegistryHelper::GetRedirectedRegistryKeyName(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x18001f60a  mov     ebx, eax
0x18001f60c  test    eax, eax
0x18001f60e  jns     short loc_18001F61A
0x18001f610  mov     r9d, eax
0x18001f613  mov     edx, 97h
0x18001f618  jmp     short loc_18001F66C
0x18001f61a  lea     r9, [rsp+278h+var_240]
0x18001f61f  mov     r8, rsi
0x18001f622  lea     rdx, [rsp+278h+var_238]
0x18001f627  call    ?RegQueryFileTimeValue@@YAJPEAUHKEY__@@PEB_W1PEAU_FILETIME@@W4RegistryHiveType@@@Z; RegQueryFileTimeValue(HKEY__ *,wchar_t const *,wchar_t const *,_FILETIME *,RegistryHiveType)
0x18001f62c  mov     esi, eax
0x18001f62e  test    eax, eax
0x18001f630  jns     short loc_18001F65B
0x18001f632  mov     ebx, 80070002h
0x18001f637  cmp     eax, ebx
0x18001f639  jz      short loc_18001F687
0x18001f63b  mov     rcx, [rsp+278h]; this
0x18001f643  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18001f64a  mov     r9d, eax; char *
0x18001f64d  mov     edx, 9Ah; void *
0x18001f652  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f657  mov     ebx, esi
0x18001f659  jmp     short loc_18001F687
0x18001f65b  mov     ebx, ebp
0x18001f65d  jmp     short loc_18001F687
0x18001f65f  mov     ebx, 80070057h
0x18001f664  mov     edx, 94h; void *
0x18001f669  mov     r9d, ebx; char *
0x18001f66c  mov     rcx, [rsp+278h]; this
0x18001f674  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18001f67b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f680  jmp     short loc_18001F687
0x18001f682  mov     ebx, 80004003h
0x18001f687  mov     rax, [rsp+278h+var_240]
0x18001f68c  mov     [r15], rax
0x18001f68f  movzx   eax, dil
0x18001f693  mov     [r14], eax
0x18001f696  mov     eax, ebx
0x18001f698  mov     rcx, [rsp+278h+var_38]
0x18001f6a0  xor     rcx, rsp; StackCookie
0x18001f6a3  call    __security_check_cookie
0x18001f6a8  mov     rbx, [rsp+278h+arg_18]
0x18001f6b0  add     rsp, 250h
0x18001f6b7  pop     r15
0x18001f6b9  pop     r14
0x18001f6bb  pop     rdi
0x18001f6bc  pop     rsi
0x18001f6bd  pop     rbp
0x18001f6be  retn
```
