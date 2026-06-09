# EapHost::XmlHelperModern::VariantConvert(wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &,ushort)

- ea: `0x18004d344`
- end: `0x18004d391`
- name: `?VariantConvert@XmlHelperModern@EapHost@@YAJAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@G@Z`
- size: `77`
- prototype: `__int64 __fastcall(VARIANTARG *pvarSrc, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18004c160`

## callees

- `0x18001830c`
- `0x18004d344`

## import_xrefs

- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18004d360`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18004d360`

## string_xrefs

- `0x18004d371`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`

## pseudocode

```c
__int64 __fastcall EapHost::XmlHelperModern::VariantConvert(VARIANTARG *pvarSrc, VARTYPE a2)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  int vt; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( pvarSrc->vt == a2 )
    return 0;
  v2 = VariantChangeTypeEx(pvarSrc, pvarSrc, 0x400u, 0, a2);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x15,
    (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
    (const char *)(unsigned int)v2,
    vt);
  return v3;
}

```

## disassembly

```asm
0x18004d344  push    rbx
0x18004d346  sub     rsp, 30h
0x18004d34a  cmp     [rcx], dx
0x18004d34d  jz      short loc_18004D389
0x18004d34f  mov     word ptr [rsp+38h+vt], dx; int
0x18004d354  xor     r9d, r9d; wFlags
0x18004d357  mov     rdx, rcx; pvarSrc
0x18004d35a  mov     r8d, 400h; lcid
0x18004d360  call    cs:__imp_VariantChangeTypeEx
0x18004d366  mov     ebx, eax
0x18004d368  test    eax, eax
0x18004d36a  jns     short loc_18004D389
0x18004d36c  mov     rcx, [rsp+38h]; this
0x18004d371  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x18004d378  mov     r9d, eax; char *
0x18004d37b  mov     edx, 15h; void *
0x18004d380  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d385  mov     eax, ebx
0x18004d387  jmp     short loc_18004D38B
0x18004d389  xor     eax, eax
0x18004d38b  add     rsp, 30h
0x18004d38f  pop     rbx
0x18004d390  retn
```
