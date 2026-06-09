# ReadDATE(ISubscriptionItem *,ushort const *,double *)

- ea: `0x18001d8d0`
- end: `0x18001d93d`
- name: `?ReadDATE@@YAJPEAUISubscriptionItem@@PEBGPEAN@Z`
- size: `109`
- prototype: `__int64 __fastcall(struct ISubscriptionItem *, const unsigned __int16 *, double *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800115e0`
- `0x18001a178`

## callees

- `0x18001d8d0`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001d92c`
- `OLEAUT32!__imp_VariantClear` at `0x18001d92c`

## string_xrefs

- `0x18001d8d8`: `CompletionTime`

## pseudocode

```c
__int64 __fastcall ReadDATE(struct ISubscriptionItem *a1, const unsigned __int16 *a2, double *a3)
{
  __int64 result; // rax
  const unsigned __int16 *v5; // [rsp+30h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-20h] BYREF

  v5 = L"CompletionTime";
  memset(&pvarg, 0, sizeof(pvarg));
  if ( ((int (__fastcall *)(struct ISubscriptionItem *, __int64, const unsigned __int16 **, VARIANTARG *))a1->lpVtbl->ReadProperties)(
         a1,
         1,
         &v5,
         &pvarg) >= 0
    && pvarg.vt == 7 )
  {
    result = 0;
    *a3 = pvarg.dblVal;
  }
  else
  {
    VariantClear(&pvarg);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001d8d0  mov     r11, rsp
0x18001d8d3  push    rbx
0x18001d8d4  sub     rsp, 50h
0x18001d8d8  lea     rax, ?c_szPropCompletionTime@@3QBGB; "CompletionTime"
0x18001d8df  xorps   xmm0, xmm0
0x18001d8e2  mov     [r11-28h], rax
0x18001d8e6  lea     r9, [r11-20h]
0x18001d8ea  xor     eax, eax
0x18001d8ec  mov     rbx, r8
0x18001d8ef  movups  xmmword ptr [rsp+58h+pvarg], xmm0
0x18001d8f4  mov     [r11-10h], rax
0x18001d8f8  lea     r8, [r11-28h]
0x18001d8fc  mov     rax, [rcx]
0x18001d8ff  mov     edx, 1
0x18001d904  mov     rax, [rax+30h]
0x18001d908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d90d  test    eax, eax
0x18001d90f  js      short loc_18001D927
0x18001d911  cmp     word ptr [rsp+58h+pvarg], 7
0x18001d917  jnz     short loc_18001D927
0x18001d919  movsd   xmm0, qword ptr [rsp+58h+pvarg+8]
0x18001d91f  xor     eax, eax
0x18001d921  movsd   qword ptr [rbx], xmm0
0x18001d925  jmp     short loc_18001D937
0x18001d927  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18001d92c  call    cs:__imp_VariantClear
0x18001d932  mov     eax, 80070057h
0x18001d937  add     rsp, 50h
0x18001d93b  pop     rbx
0x18001d93c  retn
```
