# TestHookPolicyReader::GetPolicyValue(wchar_t const *,ushort,tagTestHookPolicyValue_V1 *)

- ea: `0x1800188fc`
- end: `0x180018abf`
- name: `?GetPolicyValue@TestHookPolicyReader@@SAJPEB_WGPEAUtagTestHookPolicyValue_V1@@@Z`
- size: `451`
- prototype: `__int64 __fastcall(const wchar_t *, VARTYPE, struct tagTestHookPolicyValue_V1 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001222c`
- `0x18001da6c`
- `0x18001e168`

## callees

- `0x18000aac0`
- `0x1800188fc`
- `0x180018ac8`
- `0x180027058`
- `0x180027144`
- `0x18002d264`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180018a05`
- `OLEAUT32!__imp_SysAllocString` at `0x180018a05`
- `OLEAUT32!__imp_VariantInit` at `0x1800189e9`
- `OLEAUT32!__imp_VariantInit` at `0x1800189f3`
- `OLEAUT32!__imp_VariantInit` at `0x1800189e9`
- `OLEAUT32!__imp_VariantInit` at `0x1800189f3`
- `OLEAUT32!__imp_VariantClear` at `0x180018a70`
- `OLEAUT32!__imp_VariantClear` at `0x180018a92`
- `OLEAUT32!__imp_VariantClear` at `0x180018a70`
- `OLEAUT32!__imp_VariantClear` at `0x180018a92`
- `OLEAUT32!__imp_VariantCopy` at `0x180018a48`
- `OLEAUT32!__imp_VariantCopy` at `0x180018a48`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018a2d`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018a2d`

## string_xrefs

- `0x180018936`: `C:\__w\1\s\src\Client\policy\src\TestHooks\PolicyReader.cpp`
- `0x1800189cf`: `C:\__w\1\s\src\Client\policy\src\TestHooks\PolicyReader.cpp`
- `0x180018a60`: `C:\__w\1\s\src\Client\policy\src\TestHooks\PolicyReader.cpp`

## pseudocode

```c
__int64 __fastcall TestHookPolicyReader::GetPolicyValue(
        const wchar_t *a1,
        VARTYPE a2,
        struct tagTestHookPolicyValue_V1 *a3)
{
  __int64 v6; // rdx
  int v7; // ebx
  int HKLMValue; // eax
  HRESULT v10; // edi
  OLECHAR *v11; // rbx
  __int64 v12; // rdx
  int v13; // [rsp+20h] [rbp-30h] BYREF
  OLECHAR *psz; // [rsp+28h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  if ( !a1 )
  {
    v6 = 14;
LABEL_3:
    v7 = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\TestHooks\\PolicyReader.cpp",
      (const char *)(unsigned int)v7,
      v13);
    return (unsigned int)v7;
  }
  if ( !a3 )
  {
    v6 = 15;
    goto LABEL_3;
  }
  *(_DWORD *)a3 = 0;
  if ( !TestHookPolicyReader::AreTestHooksEnabled() )
    return 0;
  LOBYTE(v13) = 0;
  v7 = PolicyRegistryHelper::HKLMValueExists(L"WUCurrentVersion", L"\\PolicyTestHooks", a1, (bool *)&v13);
  if ( v7 < 0 )
  {
    v6 = 29;
    goto LABEL_4;
  }
  if ( !(_BYTE)v13 )
    return 0;
  psz = 0;
  HKLMValue = PolicyRegistryHelper::GetHKLMValue(L"WUCurrentVersion", L"\\PolicyTestHooks", a1, &psz);
  v10 = HKLMValue;
  v11 = psz;
  if ( HKLMValue >= 0 )
  {
    VariantInit(&pvarg);
    VariantInit(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(v11);
    if ( !pvarg.llVal )
    {
      v10 = -2147024882;
      v12 = 45;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\TestHooks\\PolicyReader.cpp",
        (const char *)(unsigned int)v10,
        v13);
      VariantClear(&pvarg);
      goto LABEL_20;
    }
    v10 = VariantChangeType(&pvarg, &pvarg, 0, a2);
    if ( v10 < 0 )
    {
      v12 = 47;
      goto LABEL_19;
    }
    v10 = VariantCopy((VARIANTARG *)((char *)a3 + 8), &pvarg);
    if ( v10 < 0 )
    {
      v12 = 48;
      goto LABEL_19;
    }
    *(_DWORD *)a3 = 1;
    VariantClear(&pvarg);
    if ( v11 )
      SusFree(v11);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x25,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\TestHooks\\PolicyReader.cpp",
    (const char *)(unsigned int)HKLMValue,
    v13);
LABEL_20:
  if ( v11 )
    SusFree(v11);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800188fc  push    rbp
0x1800188fe  push    rbx
0x1800188ff  push    rsi
0x180018900  push    rdi
0x180018901  push    r14
0x180018903  mov     rbp, rsp
0x180018906  sub     rsp, 50h
0x18001890a  mov     rax, cs:__security_cookie
0x180018911  xor     rax, rsp
0x180018914  mov     [rbp+var_8], rax
0x180018918  mov     rsi, r8
0x18001891b  movzx   r14d, dx
0x18001891f  mov     rdi, rcx
0x180018922  test    rcx, rcx
0x180018925  jnz     short loc_180018949
0x180018927  lea     edx, [rcx+0Eh]; void *
0x18001892a  mov     ebx, 80004003h
0x18001892f  mov     rcx, [rbp+28h]; this
0x180018933  mov     r9d, ebx; char *
0x180018936  lea     r8, aCW1SSrcClientP_2; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18001893d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018942  mov     eax, ebx
0x180018944  jmp     loc_180018AA8
0x180018949  test    rsi, rsi
0x18001894c  jnz     short loc_180018953
0x18001894e  lea     edx, [rsi+0Fh]
0x180018951  jmp     short loc_18001892A
0x180018953  mov     dword ptr [r8], 0
0x18001895a  call    ?AreTestHooksEnabled@TestHookPolicyReader@@SA_NXZ; TestHookPolicyReader::AreTestHooksEnabled(void)
0x18001895f  test    al, al
0x180018961  jz      loc_180018AA6
0x180018967  mov     byte ptr [rbp+var_30], 0
0x18001896b  lea     r9, [rbp+var_30]; bool *
0x18001896f  mov     r8, rdi; wchar_t *
0x180018972  lea     rdx, aPolicytesthook; "\\PolicyTestHooks"
0x180018979  lea     rcx, aWucurrentversi; "WUCurrentVersion"
0x180018980  call    ?HKLMValueExists@PolicyRegistryHelper@@SAJPEB_W00AEA_N@Z; PolicyRegistryHelper::HKLMValueExists(wchar_t const *,wchar_t const *,wchar_t const *,bool &)
0x180018985  mov     ebx, eax
0x180018987  test    eax, eax
0x180018989  jns     short loc_180018992
0x18001898b  mov     edx, 1Dh
0x180018990  jmp     short loc_18001892F
0x180018992  cmp     byte ptr [rbp+var_30], 0
0x180018996  jz      loc_180018AA6
0x18001899c  mov     [rbp+psz], 0
0x1800189a4  lea     r9, [rbp+psz]; wchar_t **
0x1800189a8  mov     r8, rdi; wchar_t *
0x1800189ab  lea     rdx, aPolicytesthook; "\\PolicyTestHooks"
0x1800189b2  lea     rcx, aWucurrentversi; "WUCurrentVersion"
0x1800189b9  call    ?GetHKLMValue@PolicyRegistryHelper@@SAJPEB_W00PEAPEA_W@Z; PolicyRegistryHelper::GetHKLMValue(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x1800189be  mov     edi, eax
0x1800189c0  mov     rbx, [rbp+psz]
0x1800189c4  test    eax, eax
0x1800189c6  jns     short loc_1800189E5
0x1800189c8  mov     rcx, [rbp+28h]; this
0x1800189cc  mov     r9d, eax; char *
0x1800189cf  lea     r8, aCW1SSrcClientP_2; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x1800189d6  mov     edx, 25h ; '%'; void *
0x1800189db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800189e0  jmp     loc_180018A77
0x1800189e5  lea     rcx, [rbp+pvarg]; pvarg
0x1800189e9  call    cs:__imp_VariantInit
0x1800189ef  lea     rcx, [rbp+pvarg]; pvarg
0x1800189f3  call    cs:__imp_VariantInit
0x1800189f9  mov     eax, 8
0x1800189fe  mov     word ptr [rbp+pvarg], ax
0x180018a02  mov     rcx, rbx; psz
0x180018a05  call    cs:__imp_SysAllocString
0x180018a0b  mov     qword ptr [rbp+pvarg+8], rax
0x180018a0f  test    rax, rax
0x180018a12  jnz     short loc_180018A1E
0x180018a14  mov     edi, 8007000Eh
0x180018a19  lea     edx, [rax+2Dh]
0x180018a1c  jmp     short loc_180018A59
0x180018a1e  xor     r8d, r8d; wFlags
0x180018a21  movzx   r9d, r14w; vt
0x180018a25  lea     rdx, [rbp+pvarg]; pvarSrc
0x180018a29  lea     rcx, [rbp+pvarg]; pvargDest
0x180018a2d  call    cs:__imp_VariantChangeType
0x180018a33  mov     edi, eax
0x180018a35  test    eax, eax
0x180018a37  jns     short loc_180018A40
0x180018a39  mov     edx, 2Fh ; '/'
0x180018a3e  jmp     short loc_180018A59
0x180018a40  lea     rcx, [rsi+8]; pvargDest
0x180018a44  lea     rdx, [rbp+pvarg]; pvargSrc
0x180018a48  call    cs:__imp_VariantCopy
0x180018a4e  mov     edi, eax
0x180018a50  test    eax, eax
0x180018a52  jns     short loc_180018A88
0x180018a54  mov     edx, 30h ; '0'; void *
0x180018a59  mov     rcx, [rbp+28h]; this
0x180018a5d  mov     r9d, edi; char *
0x180018a60  lea     r8, aCW1SSrcClientP_2; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180018a67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018a6c  lea     rcx, [rbp+pvarg]; pvarg
0x180018a70  call    cs:__imp_VariantClear
0x180018a76  nop
0x180018a77  test    rbx, rbx
0x180018a7a  jz      short loc_180018A84
0x180018a7c  mov     rcx, rbx; lpMem
0x180018a7f  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180018a84  mov     eax, edi
0x180018a86  jmp     short loc_180018AA8
0x180018a88  mov     dword ptr [rsi], 1
0x180018a8e  lea     rcx, [rbp+pvarg]; pvarg
0x180018a92  call    cs:__imp_VariantClear
0x180018a98  nop
0x180018a99  test    rbx, rbx
0x180018a9c  jz      short loc_180018AA6
0x180018a9e  mov     rcx, rbx; lpMem
0x180018aa1  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180018aa6  xor     eax, eax
0x180018aa8  mov     rcx, [rbp+var_8]
0x180018aac  xor     rcx, rsp; StackCookie
0x180018aaf  call    __security_check_cookie
0x180018ab4  add     rsp, 50h
0x180018ab8  pop     r14
0x180018aba  pop     rdi
0x180018abb  pop     rsi
0x180018abc  pop     rbx
0x180018abd  pop     rbp
0x180018abe  retn
```
