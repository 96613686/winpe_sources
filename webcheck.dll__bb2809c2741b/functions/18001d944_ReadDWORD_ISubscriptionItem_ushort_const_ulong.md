# ReadDWORD(ISubscriptionItem *,ushort const *,ulong *)

- ea: `0x18001d944`
- end: `0x18001d9b5`
- name: `?ReadDWORD@@YAJPEAUISubscriptionItem@@PEBGPEAK@Z`
- size: `113`
- prototype: `__int64 __fastcall(struct ISubscriptionItem *, const unsigned __int16 *, unsigned int *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800048f0`
- `0x18000501c`
- `0x1800057d0`
- `0x18000c424`
- `0x18000ce34`
- `0x1800106d0`
- `0x180016ce4`
- `0x1800222e0`

## callees

- `0x18001d944`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001d9a4`
- `OLEAUT32!__imp_VariantClear` at `0x18001d9a4`

## pseudocode

```c
__int64 __fastcall ReadDWORD(struct ISubscriptionItem *a1, const unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int Lo; // eax
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF
  const unsigned __int16 *v7; // [rsp+68h] [rbp+10h] BYREF

  v7 = a2;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( ((int (__fastcall *)(struct ISubscriptionItem *, __int64, const unsigned __int16 **, VARIANTARG *))a1->lpVtbl->ReadProperties)(
         a1,
         1,
         &v7,
         &pvarg) >= 0 )
  {
    if ( pvarg.vt == 3 )
    {
      Lo = pvarg.cyVal.Lo;
      goto LABEL_6;
    }
    if ( pvarg.vt == 2 )
    {
      Lo = pvarg.iVal;
LABEL_6:
      *a3 = Lo;
      return 0;
    }
  }
  VariantClear(&pvarg);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001d944  mov     r11, rsp
0x18001d947  mov     [r11+10h], rdx
0x18001d94b  push    rbx
0x18001d94c  sub     rsp, 50h
0x18001d950  xor     eax, eax
0x18001d952  lea     r9, [r11-28h]
0x18001d956  xorps   xmm0, xmm0
0x18001d959  mov     rbx, r8
0x18001d95c  movups  xmmword ptr [rsp+58h+pvarg], xmm0
0x18001d961  mov     [r11-18h], rax
0x18001d965  lea     r8, [r11+10h]
0x18001d969  mov     rax, [rcx]
0x18001d96c  mov     edx, 1
0x18001d971  mov     rax, [rax+30h]
0x18001d975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d97a  test    eax, eax
0x18001d97c  js      short loc_18001D99F
0x18001d97e  cmp     word ptr [rsp+58h+pvarg], 3
0x18001d984  jz      short loc_18001D995
0x18001d986  cmp     word ptr [rsp+58h+pvarg], 2
0x18001d98c  jnz     short loc_18001D99F
0x18001d98e  movsx   eax, word ptr [rsp+58h+pvarg+8]
0x18001d993  jmp     short loc_18001D999
0x18001d995  mov     eax, dword ptr [rsp+58h+pvarg+8]
0x18001d999  mov     [rbx], eax
0x18001d99b  xor     eax, eax
0x18001d99d  jmp     short loc_18001D9AF
0x18001d99f  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18001d9a4  call    cs:__imp_VariantClear
0x18001d9aa  mov     eax, 80070057h
0x18001d9af  add     rsp, 50h
0x18001d9b3  pop     rbx
0x18001d9b4  retn
```
