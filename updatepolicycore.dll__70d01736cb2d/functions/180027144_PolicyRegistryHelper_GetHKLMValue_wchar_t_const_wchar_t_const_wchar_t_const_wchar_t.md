# PolicyRegistryHelper::GetHKLMValue(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x180027144`
- end: `0x18002722c`
- name: `?GetHKLMValue@PolicyRegistryHelper@@SAJPEB_W00PEAPEA_W@Z`
- size: `232`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018714`
- `0x1800188fc`
- `0x1800236b8`

## callees

- `0x18000aac0`
- `0x180026c78`
- `0x180027144`
- `0x18002c120`
- `0x18002ffd0`

## string_xrefs

- `0x18002719d`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`
- `0x1800271ff`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`

## pseudocode

```c
__int64 __fastcall PolicyRegistryHelper::GetHKLMValue(wchar_t *a1, const wchar_t *a2, const wchar_t *a3, wchar_t **a4)
{
  int RedirectedRegistryKeyName; // eax
  unsigned int v7; // edi
  __int64 result; // rax
  int StringValue; // ebx
  __int64 v10; // rdx
  int v11; // [rsp+20h] [rbp-248h]
  wchar_t v12[256]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  if ( !a1 || !*a1 )
  {
    v10 = 181;
    goto LABEL_13;
  }
  if ( !a3 || !*a3 )
  {
    v10 = 182;
LABEL_13:
    StringValue = -2147024809;
    goto LABEL_14;
  }
  RedirectedRegistryKeyName = PolicyRegistryHelper::GetRedirectedRegistryKeyName(a1, a2, v12, (wchar_t **)0x100);
  v7 = RedirectedRegistryKeyName;
  if ( RedirectedRegistryKeyName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
      (const char *)(unsigned int)RedirectedRegistryKeyName,
      v11);
    return v7;
  }
  StringValue = RegQueryStringValue(-2147483646, v12, a3, a4);
  if ( StringValue >= 0 )
    return 0;
  result = 2147942402LL;
  if ( StringValue == -2147024894 )
    return result;
  v10 = 188;
LABEL_14:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
    (const char *)(unsigned int)StringValue,
    v11);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x180027144  push    rbx
0x180027146  push    rbp
0x180027147  push    rsi
0x180027148  push    rdi
0x180027149  sub     rsp, 248h
0x180027150  mov     rax, cs:__security_cookie
0x180027157  xor     rax, rsp
0x18002715a  mov     [rsp+268h+var_38], rax
0x180027162  xor     ebp, ebp
0x180027164  mov     rsi, r9
0x180027167  mov     rbx, r8
0x18002716a  test    rcx, rcx
0x18002716d  jz      short loc_1800271ED
0x18002716f  cmp     [rcx], bp
0x180027172  jz      short loc_1800271ED
0x180027174  test    rbx, rbx
0x180027177  jz      short loc_1800271E6
0x180027179  cmp     [r8], bp
0x18002717d  jz      short loc_1800271E6
0x18002717f  mov     r9d, 100h; unsigned __int64
0x180027185  lea     r8, [rsp+268h+var_238]; wchar_t *
0x18002718a  call    ?GetRedirectedRegistryKeyName@PolicyRegistryHelper@@SAJPEB_W0PEA_W_K@Z; PolicyRegistryHelper::GetRedirectedRegistryKeyName(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x18002718f  mov     edi, eax
0x180027191  test    eax, eax
0x180027193  jns     short loc_1800271B5
0x180027195  mov     rcx, [rsp+268h]; this
0x18002719d  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x1800271a4  mov     r9d, eax; char *
0x1800271a7  mov     edx, 0B9h; void *
0x1800271ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800271b1  mov     eax, edi
0x1800271b3  jmp     short loc_180027210
0x1800271b5  mov     r9, rsi
0x1800271b8  lea     rdx, [rsp+268h+var_238]
0x1800271bd  mov     r8, rbx
0x1800271c0  mov     rcx, 0FFFFFFFF80000002h
0x1800271c7  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEAPEA_WW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,RegistryHiveType)
0x1800271cc  mov     ebx, eax
0x1800271ce  test    eax, eax
0x1800271d0  jns     short loc_1800271E2
0x1800271d2  mov     eax, 80070002h
0x1800271d7  cmp     ebx, eax
0x1800271d9  jz      short loc_180027210
0x1800271db  mov     edx, 0BCh
0x1800271e0  jmp     short loc_1800271F7
0x1800271e2  xor     eax, eax
0x1800271e4  jmp     short loc_180027210
0x1800271e6  mov     edx, 0B6h
0x1800271eb  jmp     short loc_1800271F2
0x1800271ed  mov     edx, 0B5h; void *
0x1800271f2  mov     ebx, 80070057h
0x1800271f7  mov     rcx, [rsp+268h]; this
0x1800271ff  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180027206  mov     r9d, ebx; char *
0x180027209  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002720e  mov     eax, ebx
0x180027210  mov     rcx, [rsp+268h+var_38]
0x180027218  xor     rcx, rsp; StackCookie
0x18002721b  call    __security_check_cookie
0x180027220  add     rsp, 248h
0x180027227  pop     rdi
0x180027228  pop     rsi
0x180027229  pop     rbp
0x18002722a  pop     rbx
0x18002722b  retn
```
