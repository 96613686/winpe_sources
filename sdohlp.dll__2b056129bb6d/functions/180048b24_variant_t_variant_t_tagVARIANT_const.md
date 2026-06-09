# _variant_t::_variant_t(tagVARIANT const &)

- ea: `0x180048b24`
- end: `0x180048b60`
- name: `??0_variant_t@@QEAA@AEBUtagVARIANT@@@Z`
- size: `60`
- prototype: `_variant_t *__fastcall(VARIANTARG *pvargDest, VARIANTARG *pvargSrc)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180049500`
- `0x18004a0c8`
- `0x18004bdbc`

## callees

- `0x180041148`
- `0x180048b24`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180048b34`
- `OLEAUT32!__imp_VariantInit` at `0x180048b34`
- `OLEAUT32!__imp_VariantCopy` at `0x180048b40`
- `OLEAUT32!__imp_VariantCopy` at `0x180048b40`

## pseudocode

```c
VARIANTARG *__fastcall _variant_t::_variant_t(VARIANTARG *pvargDest, VARIANTARG *pvargSrc)
{
  HRESULT v4; // eax

  VariantInit(pvargDest);
  v4 = VariantCopy(pvargDest, pvargSrc);
  if ( v4 < 0 )
    _com_issue_error(v4);
  return pvargDest;
}

```

## disassembly

```asm
0x180048b24  mov     [rsp+arg_0], rbx
0x180048b29  push    rdi
0x180048b2a  sub     rsp, 20h
0x180048b2e  mov     rbx, rdx
0x180048b31  mov     rdi, rcx
0x180048b34  call    cs:__imp_VariantInit
0x180048b3a  mov     rdx, rbx; pvargSrc
0x180048b3d  mov     rcx, rdi; pvargDest
0x180048b40  call    cs:__imp_VariantCopy
0x180048b46  test    eax, eax
0x180048b48  jns     short loc_180048B52
0x180048b4a  mov     ecx, eax; int
0x180048b4c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180048b52  mov     rbx, [rsp+28h+arg_0]
0x180048b57  mov     rax, rdi
0x180048b5a  add     rsp, 20h
0x180048b5e  pop     rdi
0x180048b5f  retn
```
