# UpdatePolicyReader::ReadLusPolicy(wchar_t const *,tagVARIANT *,ulong *)

- ea: `0x18001d978`
- end: `0x18001da66`
- name: `?ReadLusPolicy@UpdatePolicyReader@@CAJPEB_WPEAUtagVARIANT@@PEAK@Z`
- size: `238`
- prototype: `__int64 __fastcall(const wchar_t *, VARIANTARG *pvargDest, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18001d884`

## callees

- `0x18000aac0`
- `0x180018714`
- `0x18001d978`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001d9a2`
- `OLEAUT32!__imp_VariantInit` at `0x18001d9a2`
- `OLEAUT32!__imp_VariantClear` at `0x18001da42`
- `OLEAUT32!__imp_VariantClear` at `0x18001da42`
- `OLEAUT32!__imp_VariantCopy` at `0x18001da11`
- `OLEAUT32!__imp_VariantCopy` at `0x18001da11`

## string_xrefs

- `0x18001da29`: `C:\__w\1\s\src\Client\policy\src\Update\PolicyReader.cpp`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadLusPolicy(const wchar_t *a1, VARIANTARG *pvargDest, unsigned int *a3)
{
  __int64 v6; // rdx
  int CachedLusPolicyValue; // ebx
  __int64 v9; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG pvargSrc; // [rsp+28h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  VariantInit(&pvarg);
  v9 = 0;
  pvargSrc = pvarg;
  if ( !pvargDest )
  {
    v6 = 2643;
LABEL_7:
    CachedLusPolicyValue = -2147467261;
    goto LABEL_12;
  }
  if ( !a1 )
  {
    v6 = 2644;
    goto LABEL_7;
  }
  if ( !a3 )
  {
    v6 = 2645;
    goto LABEL_7;
  }
  CachedLusPolicyValue = LusPolicyReader::GetCachedLusPolicyValue(a1, 0x13u, (struct tagLusPolicyValue_V1 *)&v9);
  if ( CachedLusPolicyValue >= 0 )
  {
    CachedLusPolicyValue = VariantCopy(pvargDest, &pvargSrc);
    if ( CachedLusPolicyValue >= 0 )
    {
      *a3 = v9;
      CachedLusPolicyValue = 0;
      goto LABEL_14;
    }
    v6 = 2649;
  }
  else
  {
    v6 = 2647;
  }
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Update\\PolicyReader.cpp",
    (const char *)(unsigned int)CachedLusPolicyValue,
    v9);
LABEL_14:
  VariantClear(&pvarg);
  return (unsigned int)CachedLusPolicyValue;
}

```

## disassembly

```asm
0x18001d978  mov     [rsp-18h+arg_18], rbx
0x18001d97d  push    rbp
0x18001d97e  push    rsi
0x18001d97f  push    rdi
0x18001d980  mov     rbp, rsp
0x18001d983  sub     rsp, 60h
0x18001d987  mov     rax, cs:__security_cookie
0x18001d98e  xor     rax, rsp
0x18001d991  mov     [rbp+var_8], rax
0x18001d995  mov     rdi, r8
0x18001d998  mov     rsi, rdx
0x18001d99b  mov     rbx, rcx
0x18001d99e  lea     rcx, [rbp+pvarg]; pvarg
0x18001d9a2  call    cs:__imp_VariantInit
0x18001d9a8  nop
0x18001d9a9  mov     [rbp+var_40], 0
0x18001d9b1  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001d9b5  movups  xmmword ptr [rbp+pvargSrc], xmm0
0x18001d9b9  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18001d9be  movsd   qword ptr [rbp+pvargSrc+10h], xmm1
0x18001d9c3  test    rsi, rsi
0x18001d9c6  jnz     short loc_18001D9CF
0x18001d9c8  mov     edx, 0A53h
0x18001d9cd  jmp     short loc_18001D9E5
0x18001d9cf  test    rbx, rbx
0x18001d9d2  jnz     short loc_18001D9DB
0x18001d9d4  mov     edx, 0A54h
0x18001d9d9  jmp     short loc_18001D9E5
0x18001d9db  test    rdi, rdi
0x18001d9de  jnz     short loc_18001D9EC
0x18001d9e0  mov     edx, 0A55h
0x18001d9e5  mov     ebx, 80004003h
0x18001d9ea  jmp     short loc_18001DA22
0x18001d9ec  mov     edx, 13h; unsigned __int16
0x18001d9f1  lea     r8, [rbp+var_40]; struct tagLusPolicyValue_V1 *
0x18001d9f5  mov     rcx, rbx; wchar_t *
0x18001d9f8  call    ?GetCachedLusPolicyValue@LusPolicyReader@@SAJPEB_WGPEAUtagLusPolicyValue_V1@@@Z; LusPolicyReader::GetCachedLusPolicyValue(wchar_t const *,ushort,tagLusPolicyValue_V1 *)
0x18001d9fd  mov     ebx, eax
0x18001d9ff  test    eax, eax
0x18001da01  jns     short loc_18001DA0A
0x18001da03  mov     edx, 0A57h
0x18001da08  jmp     short loc_18001DA22
0x18001da0a  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x18001da0e  mov     rcx, rsi; pvargDest
0x18001da11  call    cs:__imp_VariantCopy
0x18001da17  mov     ebx, eax
0x18001da19  test    eax, eax
0x18001da1b  jns     short loc_18001DA37
0x18001da1d  mov     edx, 0A59h; void *
0x18001da22  mov     rcx, [rbp+18h]; this
0x18001da26  mov     r9d, ebx; char *
0x18001da29  lea     r8, aCW1SSrcClientP_9; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18001da30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da35  jmp     short loc_18001DA3E
0x18001da37  mov     eax, dword ptr [rbp+var_40]
0x18001da3a  mov     [rdi], eax
0x18001da3c  xor     ebx, ebx
0x18001da3e  lea     rcx, [rbp+pvarg]; pvarg
0x18001da42  call    cs:__imp_VariantClear
0x18001da48  mov     eax, ebx
0x18001da4a  mov     rcx, [rbp+var_8]
0x18001da4e  xor     rcx, rsp; StackCookie
0x18001da51  call    __security_check_cookie
0x18001da56  mov     rbx, [rsp+60h+arg_18]
0x18001da5e  add     rsp, 60h
0x18001da62  pop     rdi
0x18001da63  pop     rsi
0x18001da64  pop     rbp
0x18001da65  retn
```
