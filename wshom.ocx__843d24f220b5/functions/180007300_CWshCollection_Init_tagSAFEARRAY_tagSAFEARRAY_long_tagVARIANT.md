# CWshCollection::Init(tagSAFEARRAY *,tagSAFEARRAY *,long,tagVARIANT *)

- ea: `0x180007300`
- end: `0x180007375`
- name: `?Init@CWshCollection@@QEAAJPEAUtagSAFEARRAY@@0JPEAUtagVARIANT@@@Z`
- size: `117`
- prototype: `int(CWshCollection *__hidden this, struct tagSAFEARRAY *, struct tagSAFEARRAY *, int, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007f90`
- `0x180008080`
- `0x18000ca00`

## callees

- `0x180007300`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180007364`
- `OLEAUT32!__imp_VariantCopy` at `0x180007364`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180007333`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180007349`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180007333`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180007349`

## pseudocode

```c
int __fastcall CWshCollection::Init(
        CWshCollection *this,
        struct tagSAFEARRAY *a2,
        struct tagSAFEARRAY *a3,
        __int64 a4,
        struct tagVARIANT *pvargSrc)
{
  int result; // eax

  if ( !a2 )
    return -2147467261;
  if ( *((_QWORD *)this + 9) )
    return -2147418113;
  result = SafeArrayCopy(a2, (SAFEARRAY **)this + 9);
  if ( result >= 0 && a3 )
  {
    result = SafeArrayCopy(a3, (SAFEARRAY **)this + 10);
    *((_DWORD *)this + 22) = 0;
    if ( pvargSrc )
      return VariantCopy((VARIANTARG *)this + 4, pvargSrc);
  }
  return result;
}

```

## disassembly

```asm
0x180007300  mov     [rsp+arg_0], rbx
0x180007305  push    rdi
0x180007306  sub     rsp, 20h
0x18000730a  mov     rdi, r8
0x18000730d  mov     rax, rdx
0x180007310  mov     rbx, rcx
0x180007313  test    rdx, rdx
0x180007316  jnz     short loc_18000731F
0x180007318  mov     eax, 80004003h
0x18000731d  jmp     short loc_18000736A
0x18000731f  lea     rdx, [rcx+48h]; ppsaOut
0x180007323  cmp     qword ptr [rdx], 0
0x180007327  jz      short loc_180007330
0x180007329  mov     eax, 8000FFFFh
0x18000732e  jmp     short loc_18000736A
0x180007330  mov     rcx, rax; psa
0x180007333  call    cs:__imp_SafeArrayCopy
0x180007339  test    eax, eax
0x18000733b  js      short loc_18000736A
0x18000733d  test    rdi, rdi
0x180007340  jz      short loc_18000736A
0x180007342  lea     rdx, [rbx+50h]; ppsaOut
0x180007346  mov     rcx, rdi; psa
0x180007349  call    cs:__imp_SafeArrayCopy
0x18000734f  mov     rdx, [rsp+28h+pvargSrc]; pvargSrc
0x180007354  mov     dword ptr [rbx+58h], 0
0x18000735b  test    rdx, rdx
0x18000735e  jz      short loc_18000736A
0x180007360  lea     rcx, [rbx+60h]; pvargDest
0x180007364  call    cs:__imp_VariantCopy
0x18000736a  mov     rbx, [rsp+28h+arg_0]
0x18000736f  add     rsp, 20h
0x180007373  pop     rdi
0x180007374  retn
```
