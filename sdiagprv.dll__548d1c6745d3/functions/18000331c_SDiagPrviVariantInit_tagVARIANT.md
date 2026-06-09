# SDiagPrviVariantInit(tagVARIANT *)

- ea: `0x18000331c`
- end: `0x180003347`
- name: `?SDiagPrviVariantInit@@YAJPEAUtagVARIANT@@@Z`
- size: `43`
- prototype: `__int64 __fastcall(struct tagVARIANT *)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f24`
- `0x1800031d8`
- `0x1800046b0`
- `0x180004a30`
- `0x180005e30`
- `0x180008f00`
- `0x18000d418`
- `0x18000d748`
- `0x18000e7f4`
- `0x180010938`
- `0x180010e88`
- `0x18001114c`
- `0x1800125e8`
- `0x1800166e4`
- `0x1800169d0`

## callees

- `0x18000331c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180003331`
- `OLEAUT32!__imp_VariantInit` at `0x180003331`

## pseudocode

```c
__int64 __fastcall SDiagPrviVariantInit(struct tagVARIANT *a1)
{
  __int64 result; // rax

  if ( !a1 )
    return 2147942487LL;
  VariantInit(a1);
  result = 0;
  a1->llVal = 0;
  return result;
}

```

## disassembly

```asm
0x18000331c  push    rbx
0x18000331e  sub     rsp, 20h
0x180003322  mov     rbx, rcx
0x180003325  test    rcx, rcx
0x180003328  jnz     short loc_180003331
0x18000332a  mov     eax, 80070057h
0x18000332f  jmp     short loc_180003341
0x180003331  call    cs:__imp_VariantInit
0x180003337  xor     eax, eax
0x180003339  mov     qword ptr [rbx+8], 0
0x180003341  add     rsp, 20h
0x180003345  pop     rbx
0x180003346  retn
```
