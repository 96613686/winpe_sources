# Variant_BSTR(tagVARIANT *,ushort * *)

- ea: `0x180005730`
- end: `0x180005771`
- name: `?Variant_BSTR@@YAJPEAUtagVARIANT@@PEAPEAG@Z`
- size: `65`
- prototype: `__int64 __fastcall(VARIANTARG *pvarSrc, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003af0`
- `0x180008ef4`
- `0x180009cf0`
- `0x18000d3d0`

## callees

- `0x180005730`

## import_xrefs

- `OLEAUT32!__imp_VariantChangeType` at `0x180005757`
- `OLEAUT32!__imp_VariantChangeType` at `0x180005757`

## pseudocode

```c
HRESULT __fastcall Variant_BSTR(VARIANTARG *pvarSrc, unsigned __int16 **a2)
{
  HRESULT result; // eax
  VARIANTARG pvargDest; // [rsp+20h] [rbp-28h] BYREF

  memset(&pvargDest, 0, sizeof(pvargDest));
  result = VariantChangeType(&pvargDest, pvarSrc, 0, 8u);
  if ( result >= 0 )
  {
    *a2 = pvargDest.bstrVal;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005730  push    rbx
0x180005732  sub     rsp, 40h
0x180005736  xor     eax, eax
0x180005738  mov     rbx, rdx
0x18000573b  xorps   xmm0, xmm0
0x18000573e  mov     qword ptr [rsp+48h+pvargDest+10h], rax
0x180005743  mov     rdx, rcx; pvarSrc
0x180005746  xor     r8d, r8d; wFlags
0x180005749  lea     rcx, [rsp+48h+pvargDest]; pvargDest
0x18000574e  lea     r9d, [rax+8]; vt
0x180005752  movups  xmmword ptr [rsp+48h+pvargDest], xmm0
0x180005757  call    cs:__imp_VariantChangeType
0x18000575d  test    eax, eax
0x18000575f  js      short loc_18000576B
0x180005761  mov     rax, qword ptr [rsp+48h+pvargDest+8]
0x180005766  mov     [rbx], rax
0x180005769  xor     eax, eax
0x18000576b  add     rsp, 40h
0x18000576f  pop     rbx
0x180005770  retn
```
