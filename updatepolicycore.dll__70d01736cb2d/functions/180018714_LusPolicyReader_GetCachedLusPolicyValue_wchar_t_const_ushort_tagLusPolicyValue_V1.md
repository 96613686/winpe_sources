# LusPolicyReader::GetCachedLusPolicyValue(wchar_t const *,ushort,tagLusPolicyValue_V1 *)

- ea: `0x180018714`
- end: `0x1800188ca`
- name: `?GetCachedLusPolicyValue@LusPolicyReader@@SAJPEB_WGPEAUtagLusPolicyValue_V1@@@Z`
- size: `438`
- prototype: `__int64 __fastcall(const wchar_t *, VARTYPE, struct tagLusPolicyValue_V1 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180011f80`
- `0x18001d978`

## callees

- `0x18000aac0`
- `0x180018714`
- `0x180027058`
- `0x180027144`
- `0x18002d264`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180018810`
- `OLEAUT32!__imp_SysAllocString` at `0x180018810`
- `OLEAUT32!__imp_VariantInit` at `0x1800187f4`
- `OLEAUT32!__imp_VariantInit` at `0x1800187fe`
- `OLEAUT32!__imp_VariantInit` at `0x1800187f4`
- `OLEAUT32!__imp_VariantInit` at `0x1800187fe`
- `OLEAUT32!__imp_VariantClear` at `0x18001887b`
- `OLEAUT32!__imp_VariantClear` at `0x18001889d`
- `OLEAUT32!__imp_VariantClear` at `0x18001887b`
- `OLEAUT32!__imp_VariantClear` at `0x18001889d`
- `OLEAUT32!__imp_VariantCopy` at `0x180018853`
- `OLEAUT32!__imp_VariantCopy` at `0x180018853`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018838`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018838`

## string_xrefs

- `0x18001874e`: `C:\__w\1\s\src\Client\policy\src\Lus\PolicyReader.cpp`
- `0x1800187da`: `C:\__w\1\s\src\Client\policy\src\Lus\PolicyReader.cpp`
- `0x18001886b`: `C:\__w\1\s\src\Client\policy\src\Lus\PolicyReader.cpp`
- `0x180018784`: `UpdateOrchestratorCurrentVersionRoot`
- `0x1800187bd`: `UpdateOrchestratorCurrentVersionRoot`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LusPolicyReader::GetCachedLusPolicyValue(
        const wchar_t *a1,
        VARTYPE a2,
        struct tagLusPolicyValue_V1 *a3)
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
    v6 = 10;
LABEL_3:
    v7 = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Lus\\PolicyReader.cpp",
      (const char *)(unsigned int)v7,
      v13);
    return (unsigned int)v7;
  }
  if ( !a3 )
  {
    v6 = 11;
    goto LABEL_3;
  }
  *(_DWORD *)a3 = 0;
  LOBYTE(v13) = 0;
  v7 = PolicyRegistryHelper::HKLMValueExists(L"UpdateOrchestratorCurrentVersionRoot", L"\\Lus", a1, (bool *)&v13);
  if ( v7 < 0 )
  {
    v6 = 17;
    goto LABEL_4;
  }
  if ( !(_BYTE)v13 )
    return 0;
  psz = 0;
  HKLMValue = PolicyRegistryHelper::GetHKLMValue(L"UpdateOrchestratorCurrentVersionRoot", L"\\Lus", a1, &psz);
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
      v12 = 33;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Lus\\PolicyReader.cpp",
        (const char *)(unsigned int)v10,
        v13);
      VariantClear(&pvarg);
      goto LABEL_19;
    }
    v10 = VariantChangeType(&pvarg, &pvarg, 0, a2);
    if ( v10 < 0 )
    {
      v12 = 38;
      goto LABEL_18;
    }
    v10 = VariantCopy((VARIANTARG *)((char *)a3 + 8), &pvarg);
    if ( v10 < 0 )
    {
      v12 = 39;
      goto LABEL_18;
    }
    *(_DWORD *)a3 = 1;
    VariantClear(&pvarg);
    if ( v11 )
      SusFree(v11);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Lus\\PolicyReader.cpp",
    (const char *)(unsigned int)HKLMValue,
    v13);
LABEL_19:
  if ( v11 )
    SusFree(v11);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180018714  push    rbp
0x180018716  push    rbx
0x180018717  push    rsi
0x180018718  push    rdi
0x180018719  push    r14
0x18001871b  mov     rbp, rsp
0x18001871e  sub     rsp, 50h
0x180018722  mov     rax, cs:__security_cookie
0x180018729  xor     rax, rsp
0x18001872c  mov     [rbp+var_8], rax
0x180018730  mov     rsi, r8
0x180018733  movzx   r14d, dx
0x180018737  mov     rdi, rcx
0x18001873a  test    rcx, rcx
0x18001873d  jnz     short loc_180018761
0x18001873f  lea     edx, [rcx+0Ah]; void *
0x180018742  mov     ebx, 80004003h
0x180018747  mov     rcx, [rbp+28h]; this
0x18001874b  mov     r9d, ebx; char *
0x18001874e  lea     r8, aCW1SSrcClientP_3; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180018755  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001875a  mov     eax, ebx
0x18001875c  jmp     loc_1800188B3
0x180018761  test    rsi, rsi
0x180018764  jnz     short loc_18001876B
0x180018766  lea     edx, [rsi+0Bh]
0x180018769  jmp     short loc_180018742
0x18001876b  mov     dword ptr [r8], 0
0x180018772  mov     byte ptr [rbp+var_30], 0
0x180018776  lea     r9, [rbp+var_30]; bool *
0x18001877a  mov     r8, rdi; wchar_t *
0x18001877d  lea     rdx, aLus; "\\Lus"
0x180018784  lea     rcx, aUpdateorchestr_1; "UpdateOrchestratorCurrentVersionRoot"
0x18001878b  call    ?HKLMValueExists@PolicyRegistryHelper@@SAJPEB_W00AEA_N@Z; PolicyRegistryHelper::HKLMValueExists(wchar_t const *,wchar_t const *,wchar_t const *,bool &)
0x180018790  mov     ebx, eax
0x180018792  test    eax, eax
0x180018794  jns     short loc_18001879D
0x180018796  mov     edx, 11h
0x18001879b  jmp     short loc_180018747
0x18001879d  cmp     byte ptr [rbp+var_30], 0
0x1800187a1  jz      loc_1800188B1
0x1800187a7  mov     [rbp+psz], 0
0x1800187af  lea     r9, [rbp+psz]; wchar_t **
0x1800187b3  mov     r8, rdi; wchar_t *
0x1800187b6  lea     rdx, aLus; "\\Lus"
0x1800187bd  lea     rcx, aUpdateorchestr_1; "UpdateOrchestratorCurrentVersionRoot"
0x1800187c4  call    ?GetHKLMValue@PolicyRegistryHelper@@SAJPEB_W00PEAPEA_W@Z; PolicyRegistryHelper::GetHKLMValue(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x1800187c9  mov     edi, eax
0x1800187cb  mov     rbx, [rbp+psz]
0x1800187cf  test    eax, eax
0x1800187d1  jns     short loc_1800187F0
0x1800187d3  mov     rcx, [rbp+28h]; this
0x1800187d7  mov     r9d, eax; char *
0x1800187da  lea     r8, aCW1SSrcClientP_3; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x1800187e1  mov     edx, 19h; void *
0x1800187e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800187eb  jmp     loc_180018882
0x1800187f0  lea     rcx, [rbp+pvarg]; pvarg
0x1800187f4  call    cs:__imp_VariantInit
0x1800187fa  lea     rcx, [rbp+pvarg]; pvarg
0x1800187fe  call    cs:__imp_VariantInit
0x180018804  mov     eax, 8
0x180018809  mov     word ptr [rbp+pvarg], ax
0x18001880d  mov     rcx, rbx; psz
0x180018810  call    cs:__imp_SysAllocString
0x180018816  mov     qword ptr [rbp+pvarg+8], rax
0x18001881a  test    rax, rax
0x18001881d  jnz     short loc_180018829
0x18001881f  mov     edi, 8007000Eh
0x180018824  lea     edx, [rax+21h]
0x180018827  jmp     short loc_180018864
0x180018829  xor     r8d, r8d; wFlags
0x18001882c  movzx   r9d, r14w; vt
0x180018830  lea     rdx, [rbp+pvarg]; pvarSrc
0x180018834  lea     rcx, [rbp+pvarg]; pvargDest
0x180018838  call    cs:__imp_VariantChangeType
0x18001883e  mov     edi, eax
0x180018840  test    eax, eax
0x180018842  jns     short loc_18001884B
0x180018844  mov     edx, 26h ; '&'
0x180018849  jmp     short loc_180018864
0x18001884b  lea     rcx, [rsi+8]; pvargDest
0x18001884f  lea     rdx, [rbp+pvarg]; pvargSrc
0x180018853  call    cs:__imp_VariantCopy
0x180018859  mov     edi, eax
0x18001885b  test    eax, eax
0x18001885d  jns     short loc_180018893
0x18001885f  mov     edx, 27h ; '''; void *
0x180018864  mov     rcx, [rbp+28h]; this
0x180018868  mov     r9d, edi; char *
0x18001886b  lea     r8, aCW1SSrcClientP_3; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180018872  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018877  lea     rcx, [rbp+pvarg]; pvarg
0x18001887b  call    cs:__imp_VariantClear
0x180018881  nop
0x180018882  test    rbx, rbx
0x180018885  jz      short loc_18001888F
0x180018887  mov     rcx, rbx; lpMem
0x18001888a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18001888f  mov     eax, edi
0x180018891  jmp     short loc_1800188B3
0x180018893  mov     dword ptr [rsi], 1
0x180018899  lea     rcx, [rbp+pvarg]; pvarg
0x18001889d  call    cs:__imp_VariantClear
0x1800188a3  nop
0x1800188a4  test    rbx, rbx
0x1800188a7  jz      short loc_1800188B1
0x1800188a9  mov     rcx, rbx; lpMem
0x1800188ac  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800188b1  xor     eax, eax
0x1800188b3  mov     rcx, [rbp+var_8]
0x1800188b7  xor     rcx, rsp; StackCookie
0x1800188ba  call    __security_check_cookie
0x1800188bf  add     rsp, 50h
0x1800188c3  pop     r14
0x1800188c5  pop     rdi
0x1800188c6  pop     rsi
0x1800188c7  pop     rbx
0x1800188c8  pop     rbp
0x1800188c9  retn
```
