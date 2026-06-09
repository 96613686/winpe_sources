# PolicyRegistryHelper::HKLMValueExists(wchar_t const *,wchar_t const *,wchar_t const *,bool &)

- ea: `0x180027058`
- end: `0x18002713e`
- name: `?HKLMValueExists@PolicyRegistryHelper@@SAJPEB_W00AEA_N@Z`
- size: `230`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const wchar_t *, bool *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018714`
- `0x1800188fc`
- `0x18001f560`

## callees

- `0x18000aac0`
- `0x180026c78`
- `0x180027058`
- `0x18002c77c`
- `0x18002ffd0`

## string_xrefs

- `0x1800270b1`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`
- `0x180027111`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`

## pseudocode

```c
__int64 __fastcall PolicyRegistryHelper::HKLMValueExists(wchar_t *a1, const wchar_t *a2, const wchar_t *a3, bool *a4)
{
  int RedirectedRegistryKeyName; // eax
  __int64 v7; // rcx
  unsigned int v8; // edi
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  int v13[128]; // [rsp+20h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  if ( !a1 || !*a1 )
  {
    v12 = 121;
    goto LABEL_15;
  }
  if ( !a3 || !*a3 )
  {
    v12 = 122;
LABEL_15:
    v11 = -2147024809;
    goto LABEL_16;
  }
  RedirectedRegistryKeyName = PolicyRegistryHelper::GetRedirectedRegistryKeyName(
                                a1,
                                a2,
                                (wchar_t *)v13,
                                (wchar_t **)0x100);
  v8 = RedirectedRegistryKeyName;
  if ( RedirectedRegistryKeyName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
      (const char *)(unsigned int)RedirectedRegistryKeyName,
      v13[0]);
    return v8;
  }
  v10 = RegValueExists(v7, v13, a3);
  v11 = v10;
  if ( (unsigned int)(v10 + 2147024894) <= 1 )
  {
    *a4 = 0;
    return 0;
  }
  if ( v10 >= 0 )
  {
    *a4 = 1;
    return 0;
  }
  v12 = 135;
LABEL_16:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
    (const char *)v11,
    v13[0]);
  return v11;
}

```

## disassembly

```asm
0x180027058  push    rbx
0x18002705a  push    rbp
0x18002705b  push    rsi
0x18002705c  push    rdi
0x18002705d  sub     rsp, 238h
0x180027064  mov     rax, cs:__security_cookie
0x18002706b  xor     rax, rsp
0x18002706e  mov     [rsp+258h+var_38], rax
0x180027076  xor     ebp, ebp
0x180027078  mov     rsi, r9
0x18002707b  mov     rbx, r8
0x18002707e  test    rcx, rcx
0x180027081  jz      short loc_1800270FF
0x180027083  cmp     [rcx], bp
0x180027086  jz      short loc_1800270FF
0x180027088  test    rbx, rbx
0x18002708b  jz      short loc_1800270F8
0x18002708d  cmp     [r8], bp
0x180027091  jz      short loc_1800270F8
0x180027093  mov     r9d, 100h; unsigned __int64
0x180027099  lea     r8, [rsp+258h+var_238]; wchar_t *
0x18002709e  call    ?GetRedirectedRegistryKeyName@PolicyRegistryHelper@@SAJPEB_W0PEA_W_K@Z; PolicyRegistryHelper::GetRedirectedRegistryKeyName(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x1800270a3  mov     edi, eax
0x1800270a5  test    eax, eax
0x1800270a7  jns     short loc_1800270C7
0x1800270a9  mov     rcx, [rsp+258h]; this
0x1800270b1  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x1800270b8  mov     r9d, eax; char *
0x1800270bb  lea     edx, [rbp+7Dh]; void *
0x1800270be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800270c3  mov     eax, edi
0x1800270c5  jmp     short loc_180027122
0x1800270c7  mov     r8, rbx
0x1800270ca  lea     rdx, [rsp+258h+var_238]
0x1800270cf  call    ?RegValueExists@@YAJPEAUHKEY__@@PEB_W1W4RegistryHiveType@@@Z; RegValueExists(HKEY__ *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x1800270d4  mov     ebx, eax
0x1800270d6  lea     ecx, [rax+7FF8FFFEh]
0x1800270dc  cmp     ecx, 1
0x1800270df  jbe     short loc_1800270F3
0x1800270e1  test    eax, eax
0x1800270e3  jns     short loc_1800270EC
0x1800270e5  mov     edx, 87h
0x1800270ea  jmp     short loc_180027109
0x1800270ec  mov     byte ptr [rsi], 1
0x1800270ef  xor     eax, eax
0x1800270f1  jmp     short loc_180027122
0x1800270f3  mov     [rsi], bpl
0x1800270f6  jmp     short loc_1800270EF
0x1800270f8  mov     edx, 7Ah ; 'z'
0x1800270fd  jmp     short loc_180027104
0x1800270ff  mov     edx, 79h ; 'y'; void *
0x180027104  mov     ebx, 80070057h
0x180027109  mov     rcx, [rsp+258h]; this
0x180027111  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180027118  mov     r9d, ebx; char *
0x18002711b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027120  mov     eax, ebx
0x180027122  mov     rcx, [rsp+258h+var_38]
0x18002712a  xor     rcx, rsp; StackCookie
0x18002712d  call    __security_check_cookie
0x180027132  add     rsp, 238h
0x180027139  pop     rdi
0x18002713a  pop     rsi
0x18002713b  pop     rbp
0x18002713c  pop     rbx
0x18002713d  retn
```
