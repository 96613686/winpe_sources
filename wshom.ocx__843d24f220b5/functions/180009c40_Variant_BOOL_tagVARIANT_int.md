# Variant_BOOL(tagVARIANT *,int *)

- ea: `0x180009c40`
- end: `0x180009c80`
- name: `?Variant_BOOL@@YAJPEAUtagVARIANT@@PEAH@Z`
- size: `64`
- prototype: `__int64 __fastcall(VARIANTARG *pvarSrc, int *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003750`
- `0x1800038c0`
- `0x180008600`
- `0x180008ef4`

## callees

- `0x180009c40`

## import_xrefs

- `OLEAUT32!__imp_VariantChangeType` at `0x180009c67`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009c67`

## pseudocode

```c
HRESULT __fastcall Variant_BOOL(VARIANTARG *pvarSrc, int *a2)
{
  HRESULT result; // eax
  VARIANTARG pvargDest; // [rsp+20h] [rbp-28h] BYREF

  memset(&pvargDest, 0, sizeof(pvargDest));
  result = VariantChangeType(&pvargDest, pvarSrc, 0, 0xBu);
  if ( result >= 0 )
  {
    *a2 = pvargDest.iVal;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009c40  push    rbx
0x180009c42  sub     rsp, 40h
0x180009c46  xor     eax, eax
0x180009c48  mov     rbx, rdx
0x180009c4b  xorps   xmm0, xmm0
0x180009c4e  mov     qword ptr [rsp+48h+pvargDest+10h], rax
0x180009c53  mov     rdx, rcx; pvarSrc
0x180009c56  xor     r8d, r8d; wFlags
0x180009c59  lea     rcx, [rsp+48h+pvargDest]; pvargDest
0x180009c5e  lea     r9d, [rax+0Bh]; vt
0x180009c62  movups  xmmword ptr [rsp+48h+pvargDest], xmm0
0x180009c67  call    cs:__imp_VariantChangeType
0x180009c6d  test    eax, eax
0x180009c6f  js      short loc_180009C7A
0x180009c71  movsx   eax, word ptr [rsp+48h+pvargDest+8]
0x180009c76  mov     [rbx], eax
0x180009c78  xor     eax, eax
0x180009c7a  add     rsp, 40h
0x180009c7e  pop     rbx
0x180009c7f  retn
```
