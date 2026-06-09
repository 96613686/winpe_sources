# PolicyRefreshCacheHelper::GetGPActiveCache(ulong &)

- ea: `0x180022634`
- end: `0x180022780`
- name: `?GetGPActiveCache@PolicyRefreshCacheHelper@@CAJAEAK@Z`
- size: `332`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800236b8`
- `0x1800242b8`

## callees

- `0x18000aac0`
- `0x180022634`
- `0x180026c78`
- `0x18002bfcc`
- `0x18002ffd0`

## string_xrefs

- `0x1800226a6`: `WindowsUpdate`
- `0x180022662`: `ActiveCache`
- `0x1800226eb`: `ActiveCache`
- `0x18002269f`: `\UpdatePolicy\GPCache`
- `0x18002273b`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`
- `0x180022676`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`
- `0x1800226c0`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`
- `0x180022717`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`

## pseudocode

```c
__int64 __fastcall PolicyRefreshCacheHelper::GetGPActiveCache(unsigned int *a1)
{
  unsigned int DwordValue; // ebx
  int RedirectedRegistryKeyName; // eax
  int v5; // [rsp+20h] [rbp-238h]
  int v6; // [rsp+20h] [rbp-238h]
  unsigned int v7[3]; // [rsp+34h] [rbp-224h] BYREF
  wchar_t v8[256]; // [rsp+40h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v7[0] = 1;
  if ( !aActivecache[0] )
  {
    DwordValue = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
      (const char *)0x80070057LL,
      v5);
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
      (const char *)DwordValue,
      v6);
    return DwordValue;
  }
  RedirectedRegistryKeyName = PolicyRegistryHelper::GetRedirectedRegistryKeyName(
                                (wchar_t *)L"WindowsUpdate",
                                L"\\UpdatePolicy\\GPCache",
                                v8,
                                (wchar_t **)0x100);
  DwordValue = RedirectedRegistryKeyName;
  if ( RedirectedRegistryKeyName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
      (const char *)(unsigned int)RedirectedRegistryKeyName,
      v5);
    if ( DwordValue == -2147024894 )
      return DwordValue;
    goto LABEL_10;
  }
  DwordValue = RegQueryDwordValue(-2147483646, v8, L"ActiveCache", v7);
  if ( (DwordValue & 0x80000000) != 0 )
  {
    if ( DwordValue == -2147024894 )
      return (unsigned int)-2147024894;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
      (const char *)DwordValue,
      v5);
LABEL_10:
    if ( DwordValue != -2147024893 )
      goto LABEL_11;
    return DwordValue;
  }
  *a1 = v7[0];
  return 0;
}

```

## disassembly

```asm
0x180022634  mov     [rsp+arg_8], rbx
0x180022639  mov     [rsp+arg_10], rsi
0x18002263e  push    rdi
0x18002263f  sub     rsp, 250h
0x180022646  mov     rax, cs:__security_cookie
0x18002264d  xor     rax, rsp
0x180022650  mov     [rsp+258h+var_18], rax
0x180022658  xor     esi, esi
0x18002265a  mov     [rsp+258h+var_224], 1
0x180022662  cmp     word ptr cs:aActivecache, si; "ActiveCache"
0x180022669  mov     rdi, rcx
0x18002266c  jnz     short loc_180022694
0x18002266e  mov     rcx, [rsp+258h]; this
0x180022676  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18002267d  mov     ebx, 80070057h
0x180022682  mov     edx, 0A5h; void *
0x180022687  mov     r9d, ebx; char *
0x18002268a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002268f  jmp     loc_180022733
0x180022694  mov     r9d, 100h; unsigned __int64
0x18002269a  lea     r8, [rsp+258h+var_218]; wchar_t *
0x18002269f  lea     rdx, aUpdatepolicyGp; "\\UpdatePolicy\\GPCache"
0x1800226a6  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x1800226ad  call    ?GetRedirectedRegistryKeyName@PolicyRegistryHelper@@SAJPEB_W0PEA_W_K@Z; PolicyRegistryHelper::GetRedirectedRegistryKeyName(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x1800226b2  mov     ebx, eax
0x1800226b4  test    eax, eax
0x1800226b6  jns     short loc_1800226DF
0x1800226b8  mov     rcx, [rsp+258h]; this
0x1800226c0  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x1800226c7  mov     r9d, eax; char *
0x1800226ca  mov     edx, 0A8h; void *
0x1800226cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800226d4  mov     eax, 80070002h
0x1800226d9  cmp     ebx, eax
0x1800226db  jz      short loc_18002274F
0x1800226dd  jmp     short loc_18002272B
0x1800226df  lea     r9, [rsp+258h+var_224]
0x1800226e4  mov     rcx, 0FFFFFFFF80000002h
0x1800226eb  lea     r8, aActivecache; "ActiveCache"
0x1800226f2  lea     rdx, [rsp+258h+var_218]
0x1800226f7  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_W1PEAKW4RegistryHiveType@@@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *,RegistryHiveType)
0x1800226fc  mov     ebx, eax
0x1800226fe  test    eax, eax
0x180022700  jns     short loc_180022753
0x180022702  mov     eax, 80070002h
0x180022707  cmp     ebx, eax
0x180022709  jnz     short loc_18002270F
0x18002270b  mov     ebx, eax
0x18002270d  jmp     short loc_18002274F
0x18002270f  mov     rcx, [rsp+258h]; this
0x180022717  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18002271e  mov     r9d, ebx; char *
0x180022721  mov     edx, 0ABh; void *
0x180022726  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002272b  cmp     ebx, 80070003h
0x180022731  jz      short loc_18002274F
0x180022733  mov     rcx, [rsp+258h]; this
0x18002273b  lea     r8, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180022742  mov     r9d, ebx; char *
0x180022745  mov     edx, 22h ; '"'; void *
0x18002274a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002274f  mov     eax, ebx
0x180022751  jmp     short loc_18002275B
0x180022753  mov     eax, [rsp+258h+var_224]
0x180022757  mov     [rdi], eax
0x180022759  xor     eax, eax
0x18002275b  mov     rcx, [rsp+258h+var_18]
0x180022763  xor     rcx, rsp; StackCookie
0x180022766  call    __security_check_cookie
0x18002276b  lea     r11, [rsp+258h+var_8]
0x180022773  mov     rbx, [r11+18h]
0x180022777  mov     rsi, [r11+20h]
0x18002277b  mov     rsp, r11
0x18002277e  pop     rdi
0x18002277f  retn
```
