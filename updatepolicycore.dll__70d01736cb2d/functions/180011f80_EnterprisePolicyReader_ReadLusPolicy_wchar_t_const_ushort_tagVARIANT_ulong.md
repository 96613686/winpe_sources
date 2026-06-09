# EnterprisePolicyReader::ReadLusPolicy(wchar_t const *,ushort,tagVARIANT *,ulong *)

- ea: `0x180011f80`
- end: `0x180012034`
- name: `?ReadLusPolicy@EnterprisePolicyReader@@CAJPEB_WGPEAUtagVARIANT@@PEAK@Z`
- size: `180`
- prototype: `__int64 __fastcall(const wchar_t *, VARTYPE, struct tagVARIANT *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011d90`
- `0x180011e8c`

## callees

- `0x180011f80`
- `0x180018714`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180011fa9`
- `OLEAUT32!__imp_VariantInit` at `0x180011fa9`
- `OLEAUT32!__imp_VariantClear` at `0x180012016`
- `OLEAUT32!__imp_VariantClear` at `0x180012016`
- `OLEAUT32!__imp_VariantCopy` at `0x180012002`
- `OLEAUT32!__imp_VariantCopy` at `0x180012002`

## pseudocode

```c
__int64 __fastcall EnterprisePolicyReader::ReadLusPolicy(
        const wchar_t *a1,
        VARTYPE a2,
        struct tagVARIANT *a3,
        unsigned int *a4)
{
  int CachedLusPolicyValue; // ebx
  __int64 v10; // [rsp+20h] [rbp-68h] BYREF
  VARIANTARG pvargSrc; // [rsp+28h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-48h] BYREF

  VariantInit(&pvarg);
  v10 = 0;
  pvargSrc = pvarg;
  if ( a3 && a1 && a4 )
  {
    CachedLusPolicyValue = LusPolicyReader::GetCachedLusPolicyValue(a1, a2, (struct tagLusPolicyValue_V1 *)&v10);
    if ( CachedLusPolicyValue >= 0 )
    {
      *a4 = v10;
      CachedLusPolicyValue = VariantCopy(a3, &pvargSrc);
    }
  }
  else
  {
    CachedLusPolicyValue = -2147467261;
  }
  VariantClear(&pvarg);
  return (unsigned int)CachedLusPolicyValue;
}

```

## disassembly

```asm
0x180011f80  push    rbx
0x180011f82  push    rbp
0x180011f83  push    rsi
0x180011f84  push    rdi
0x180011f85  sub     rsp, 68h
0x180011f89  mov     rax, cs:__security_cookie
0x180011f90  xor     rax, rsp
0x180011f93  mov     [rsp+88h+var_30], rax
0x180011f98  mov     rdi, r9
0x180011f9b  mov     rsi, r8
0x180011f9e  movzx   ebp, dx
0x180011fa1  mov     rbx, rcx
0x180011fa4  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180011fa9  call    cs:__imp_VariantInit
0x180011faf  nop
0x180011fb0  mov     [rsp+88h+var_68], 0
0x180011fb9  movups  xmm0, xmmword ptr [rsp+88h+pvarg]
0x180011fbe  movups  xmmword ptr [rsp+88h+pvargSrc], xmm0
0x180011fc3  movsd   xmm1, qword ptr [rsp+88h+pvarg+10h]
0x180011fc9  movsd   qword ptr [rsp+88h+pvargSrc+10h], xmm1
0x180011fcf  test    rsi, rsi
0x180011fd2  jz      short loc_18001200C
0x180011fd4  test    rbx, rbx
0x180011fd7  jz      short loc_18001200C
0x180011fd9  test    rdi, rdi
0x180011fdc  jz      short loc_18001200C
0x180011fde  lea     r8, [rsp+88h+var_68]; struct tagLusPolicyValue_V1 *
0x180011fe3  movzx   edx, bp; unsigned __int16
0x180011fe6  mov     rcx, rbx; wchar_t *
0x180011fe9  call    ?GetCachedLusPolicyValue@LusPolicyReader@@SAJPEB_WGPEAUtagLusPolicyValue_V1@@@Z; LusPolicyReader::GetCachedLusPolicyValue(wchar_t const *,ushort,tagLusPolicyValue_V1 *)
0x180011fee  mov     ebx, eax
0x180011ff0  test    eax, eax
0x180011ff2  js      short loc_180012011
0x180011ff4  mov     eax, dword ptr [rsp+88h+var_68]
0x180011ff8  mov     [rdi], eax
0x180011ffa  lea     rdx, [rsp+88h+pvargSrc]; pvargSrc
0x180011fff  mov     rcx, rsi; pvargDest
0x180012002  call    cs:__imp_VariantCopy
0x180012008  mov     ebx, eax
0x18001200a  jmp     short loc_180012011
0x18001200c  mov     ebx, 80004003h
0x180012011  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180012016  call    cs:__imp_VariantClear
0x18001201c  mov     eax, ebx
0x18001201e  mov     rcx, [rsp+88h+var_30]
0x180012023  xor     rcx, rsp; StackCookie
0x180012026  call    __security_check_cookie
0x18001202b  add     rsp, 68h
0x18001202f  pop     rdi
0x180012030  pop     rsi
0x180012031  pop     rbp
0x180012032  pop     rbx
0x180012033  retn
```
