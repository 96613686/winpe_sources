# ReadBSTR(ISubscriptionItem *,ushort const *,ushort * *)

- ea: `0x18001d7c8`
- end: `0x18001d833`
- name: `?ReadBSTR@@YAJPEAUISubscriptionItem@@PEBGPEAPEAG@Z`
- size: `107`
- prototype: `__int64 __fastcall(struct ISubscriptionItem *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800115e0`
- `0x180011bf0`
- `0x18001da30`
- `0x18001f4b4`
- `0x1800222e0`

## callees

- `0x18001d7c8`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001d81b`
- `OLEAUT32!__imp_VariantClear` at `0x18001d81b`

## pseudocode

```c
__int64 __fastcall ReadBSTR(struct ISubscriptionItem *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 result; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF
  const unsigned __int16 *v6; // [rsp+68h] [rbp+10h] BYREF

  v6 = a2;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( ((int (__fastcall *)(struct ISubscriptionItem *, __int64, const unsigned __int16 **, VARIANTARG *))a1->lpVtbl->ReadProperties)(
         a1,
         1,
         &v6,
         &pvarg) >= 0
    && pvarg.vt == 8 )
  {
    *a3 = pvarg.bstrVal;
    return 0;
  }
  else
  {
    VariantClear(&pvarg);
    result = 2147942487LL;
    *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001d7c8  mov     r11, rsp
0x18001d7cb  mov     [r11+10h], rdx
0x18001d7cf  push    rbx
0x18001d7d0  sub     rsp, 50h
0x18001d7d4  xor     eax, eax
0x18001d7d6  lea     r9, [r11-28h]
0x18001d7da  xorps   xmm0, xmm0
0x18001d7dd  mov     rbx, r8
0x18001d7e0  movups  xmmword ptr [rsp+58h+pvarg], xmm0
0x18001d7e5  mov     [r11-18h], rax
0x18001d7e9  lea     r8, [r11+10h]
0x18001d7ed  mov     rax, [rcx]
0x18001d7f0  mov     edx, 1
0x18001d7f5  mov     rax, [rax+30h]
0x18001d7f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7fe  test    eax, eax
0x18001d800  js      short loc_18001D816
0x18001d802  cmp     word ptr [rsp+58h+pvarg], 8
0x18001d808  jnz     short loc_18001D816
0x18001d80a  mov     rax, qword ptr [rsp+58h+pvarg+8]
0x18001d80f  mov     [rbx], rax
0x18001d812  xor     eax, eax
0x18001d814  jmp     short loc_18001D82D
0x18001d816  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18001d81b  call    cs:__imp_VariantClear
0x18001d821  mov     eax, 80070057h
0x18001d826  mov     qword ptr [rbx], 0
0x18001d82d  add     rsp, 50h
0x18001d831  pop     rbx
0x18001d832  retn
```
