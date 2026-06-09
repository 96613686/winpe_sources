# Variant_I4(tagVARIANT *,ulong *)

- ea: `0x180005938`
- end: `0x180005977`
- name: `?Variant_I4@@YAJPEAUtagVARIANT@@PEAK@Z`
- size: `63`
- prototype: `__int64 __fastcall(VARIANTARG *pvarSrc, unsigned int *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800038c0`
- `0x180003af0`
- `0x180007390`
- `0x180009cf0`
- `0x18000d3d0`

## callees

- `0x180005938`

## import_xrefs

- `OLEAUT32!__imp_VariantChangeType` at `0x18000595f`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000595f`

## pseudocode

```c
HRESULT __fastcall Variant_I4(VARIANTARG *pvarSrc, unsigned int *a2)
{
  HRESULT result; // eax
  VARIANTARG pvargDest; // [rsp+20h] [rbp-28h] BYREF

  memset(&pvargDest, 0, sizeof(pvargDest));
  result = VariantChangeType(&pvargDest, pvarSrc, 0, 3u);
  if ( result >= 0 )
  {
    *a2 = pvargDest.cyVal.Lo;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005938  push    rbx
0x18000593a  sub     rsp, 40h
0x18000593e  xor     eax, eax
0x180005940  mov     rbx, rdx
0x180005943  xorps   xmm0, xmm0
0x180005946  mov     qword ptr [rsp+48h+pvargDest+10h], rax
0x18000594b  mov     rdx, rcx; pvarSrc
0x18000594e  xor     r8d, r8d; wFlags
0x180005951  lea     rcx, [rsp+48h+pvargDest]; pvargDest
0x180005956  lea     r9d, [rax+3]; vt
0x18000595a  movups  xmmword ptr [rsp+48h+pvargDest], xmm0
0x18000595f  call    cs:__imp_VariantChangeType
0x180005965  test    eax, eax
0x180005967  js      short loc_180005971
0x180005969  mov     eax, dword ptr [rsp+48h+pvargDest+8]
0x18000596d  mov     [rbx], eax
0x18000596f  xor     eax, eax
0x180005971  add     rsp, 40h
0x180005975  pop     rbx
0x180005976  retn
```
