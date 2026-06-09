# EnterprisePolicyReader::ReadTestHookPolicy(wchar_t const *,ushort,tagVARIANT *,ulong *)

- ea: `0x18001222c`
- end: `0x1800122e0`
- name: `?ReadTestHookPolicy@EnterprisePolicyReader@@CAJPEB_WGPEAUtagVARIANT@@PEAK@Z`
- size: `180`
- prototype: `static int(const wchar_t *, unsigned __int16, struct tagVARIANT *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001203c`
- `0x180012138`

## callees

- `0x18001222c`
- `0x1800188fc`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180012255`
- `OLEAUT32!__imp_VariantInit` at `0x180012255`
- `OLEAUT32!__imp_VariantClear` at `0x1800122c2`
- `OLEAUT32!__imp_VariantClear` at `0x1800122c2`
- `OLEAUT32!__imp_VariantCopy` at `0x1800122ae`
- `OLEAUT32!__imp_VariantCopy` at `0x1800122ae`

## pseudocode

```c
__int64 __fastcall EnterprisePolicyReader::ReadTestHookPolicy(
        const wchar_t *a1,
        VARTYPE a2,
        struct tagVARIANT *a3,
        unsigned int *a4)
{
  int PolicyValue; // ebx
  __int64 v10; // [rsp+20h] [rbp-68h] BYREF
  VARIANTARG pvargSrc; // [rsp+28h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-48h] BYREF

  VariantInit(&pvarg);
  v10 = 0;
  pvargSrc = pvarg;
  if ( a3 && a1 && a4 )
  {
    PolicyValue = TestHookPolicyReader::GetPolicyValue(a1, a2, (struct tagTestHookPolicyValue_V1 *)&v10);
    if ( PolicyValue >= 0 )
    {
      *a4 = v10;
      PolicyValue = VariantCopy(a3, &pvargSrc);
    }
  }
  else
  {
    PolicyValue = -2147467261;
  }
  VariantClear(&pvarg);
  return (unsigned int)PolicyValue;
}

```

## disassembly

```asm
0x18001222c  push    rbx
0x18001222e  push    rbp
0x18001222f  push    rsi
0x180012230  push    rdi
0x180012231  sub     rsp, 68h
0x180012235  mov     rax, cs:__security_cookie
0x18001223c  xor     rax, rsp
0x18001223f  mov     [rsp+88h+var_30], rax
0x180012244  mov     rdi, r9
0x180012247  mov     rsi, r8
0x18001224a  movzx   ebp, dx
0x18001224d  mov     rbx, rcx
0x180012250  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180012255  call    cs:__imp_VariantInit
0x18001225b  nop
0x18001225c  mov     [rsp+88h+var_68], 0
0x180012265  movups  xmm0, xmmword ptr [rsp+88h+pvarg]
0x18001226a  movups  xmmword ptr [rsp+88h+pvargSrc], xmm0
0x18001226f  movsd   xmm1, qword ptr [rsp+88h+pvarg+10h]
0x180012275  movsd   qword ptr [rsp+88h+pvargSrc+10h], xmm1
0x18001227b  test    rsi, rsi
0x18001227e  jz      short loc_1800122B8
0x180012280  test    rbx, rbx
0x180012283  jz      short loc_1800122B8
0x180012285  test    rdi, rdi
0x180012288  jz      short loc_1800122B8
0x18001228a  lea     r8, [rsp+88h+var_68]; struct tagTestHookPolicyValue_V1 *
0x18001228f  movzx   edx, bp; unsigned __int16
0x180012292  mov     rcx, rbx; wchar_t *
0x180012295  call    ?GetPolicyValue@TestHookPolicyReader@@SAJPEB_WGPEAUtagTestHookPolicyValue_V1@@@Z; TestHookPolicyReader::GetPolicyValue(wchar_t const *,ushort,tagTestHookPolicyValue_V1 *)
0x18001229a  mov     ebx, eax
0x18001229c  test    eax, eax
0x18001229e  js      short loc_1800122BD
0x1800122a0  mov     eax, dword ptr [rsp+88h+var_68]
0x1800122a4  mov     [rdi], eax
0x1800122a6  lea     rdx, [rsp+88h+pvargSrc]; pvargSrc
0x1800122ab  mov     rcx, rsi; pvargDest
0x1800122ae  call    cs:__imp_VariantCopy
0x1800122b4  mov     ebx, eax
0x1800122b6  jmp     short loc_1800122BD
0x1800122b8  mov     ebx, 80004003h
0x1800122bd  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1800122c2  call    cs:__imp_VariantClear
0x1800122c8  mov     eax, ebx
0x1800122ca  mov     rcx, [rsp+88h+var_30]
0x1800122cf  xor     rcx, rsp; StackCookie
0x1800122d2  call    __security_check_cookie
0x1800122d7  add     rsp, 68h
0x1800122db  pop     rdi
0x1800122dc  pop     rsi
0x1800122dd  pop     rbp
0x1800122de  pop     rbx
0x1800122df  retn
```
