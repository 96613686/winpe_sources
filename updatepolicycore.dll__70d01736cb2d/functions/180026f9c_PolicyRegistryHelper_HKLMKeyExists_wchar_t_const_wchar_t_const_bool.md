# PolicyRegistryHelper::HKLMKeyExists(wchar_t const *,wchar_t const *,bool &)

- ea: `0x180026f9c`
- end: `0x18002704f`
- name: `?HKLMKeyExists@PolicyRegistryHelper@@SAJPEB_W0AEA_N@Z`
- size: `179`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018ac8`

## callees

- `0x18000aac0`
- `0x180026c78`
- `0x180026f9c`
- `0x18002c6dc`
- `0x18002ffd0`

## string_xrefs

- `0x180026fef`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`

## pseudocode

```c
__int64 __fastcall PolicyRegistryHelper::HKLMKeyExists(const wchar_t *a1, const wchar_t *a2, bool *a3)
{
  __int64 v4; // rcx
  int RedirectedRegistryKeyName; // ebx
  __int64 v6; // rdx
  int v8; // eax
  int v9[128]; // [rsp+20h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  RedirectedRegistryKeyName = PolicyRegistryHelper::GetRedirectedRegistryKeyName(
                                (wchar_t *)L"WUCurrentVersion",
                                L"\\PolicyTestHooks",
                                (wchar_t *)v9,
                                (wchar_t **)0x100);
  if ( RedirectedRegistryKeyName < 0 )
  {
    v6 = 99;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
      (const char *)(unsigned int)RedirectedRegistryKeyName,
      v9[0]);
    return (unsigned int)RedirectedRegistryKeyName;
  }
  v8 = RegKeyExists(v4, v9);
  RedirectedRegistryKeyName = v8;
  if ( (unsigned int)(v8 + 2147024894) <= 1 )
  {
    *a3 = 0;
  }
  else
  {
    if ( v8 < 0 )
    {
      v6 = 109;
      goto LABEL_3;
    }
    *a3 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180026f9c  mov     [rsp+arg_0], rbx
0x180026fa1  push    rdi
0x180026fa2  sub     rsp, 230h
0x180026fa9  mov     rax, cs:__security_cookie
0x180026fb0  xor     rax, rsp
0x180026fb3  mov     [rsp+238h+var_18], rax
0x180026fbb  mov     rdi, r8
0x180026fbe  lea     rdx, aPolicytesthook; "\\PolicyTestHooks"
0x180026fc5  lea     r8, [rsp+238h+var_218]; wchar_t *
0x180026fca  mov     r9d, 100h; unsigned __int64
0x180026fd0  lea     rcx, aWucurrentversi; "WUCurrentVersion"
0x180026fd7  call    ?GetRedirectedRegistryKeyName@PolicyRegistryHelper@@SAJPEB_W0PEA_W_K@Z; PolicyRegistryHelper::GetRedirectedRegistryKeyName(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x180026fdc  mov     ebx, eax
0x180026fde  test    eax, eax
0x180026fe0  jns     short loc_180027002
0x180026fe2  mov     edx, 63h ; 'c'; void *
0x180026fe7  mov     rcx, [rsp+238h]; this
0x180026fef  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180026ff6  mov     r9d, ebx; char *
0x180026ff9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026ffe  mov     eax, ebx
0x180027000  jmp     short loc_18002702E
0x180027002  lea     rdx, [rsp+238h+var_218]
0x180027007  call    ?RegKeyExists@@YAJPEAUHKEY__@@PEB_WW4RegistryHiveType@@@Z; RegKeyExists(HKEY__ *,wchar_t const *,RegistryHiveType)
0x18002700c  mov     ebx, eax
0x18002700e  lea     ecx, [rax+7FF8FFFEh]
0x180027014  cmp     ecx, 1
0x180027017  jbe     short loc_180027029
0x180027019  test    eax, eax
0x18002701b  jns     short loc_180027024
0x18002701d  mov     edx, 6Dh ; 'm'
0x180027022  jmp     short loc_180026FE7
0x180027024  mov     byte ptr [rdi], 1
0x180027027  jmp     short loc_18002702C
0x180027029  mov     byte ptr [rdi], 0
0x18002702c  xor     eax, eax
0x18002702e  mov     rcx, [rsp+238h+var_18]
0x180027036  xor     rcx, rsp; StackCookie
0x180027039  call    __security_check_cookie
0x18002703e  mov     rbx, [rsp+238h+arg_0]
0x180027046  add     rsp, 230h
0x18002704d  pop     rdi
0x18002704e  retn
```
