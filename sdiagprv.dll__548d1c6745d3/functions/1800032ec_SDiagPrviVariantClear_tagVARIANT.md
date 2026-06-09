# SDiagPrviVariantClear(tagVARIANT *)

- ea: `0x1800032ec`
- end: `0x180003315`
- name: `?SDiagPrviVariantClear@@YAJPEAUtagVARIANT@@@Z`
- size: `41`
- prototype: `HRESULT __fastcall(struct tagVARIANT *)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f24`
- `0x1800031d8`
- `0x1800046b0`
- `0x180004a30`
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

- `0x1800032ec`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180003301`
- `OLEAUT32!__imp_VariantClear` at `0x180003301`

## pseudocode

```c
HRESULT __fastcall SDiagPrviVariantClear(struct tagVARIANT *a1)
{
  HRESULT result; // eax

  if ( !a1 )
    return -2147024809;
  result = VariantClear(a1);
  a1->llVal = 0;
  return result;
}

```

## disassembly

```asm
0x1800032ec  push    rbx
0x1800032ee  sub     rsp, 20h
0x1800032f2  mov     rbx, rcx
0x1800032f5  test    rcx, rcx
0x1800032f8  jnz     short loc_180003301
0x1800032fa  mov     eax, 80070057h
0x1800032ff  jmp     short loc_18000330F
0x180003301  call    cs:__imp_VariantClear
0x180003307  mov     qword ptr [rbx+8], 0
0x18000330f  add     rsp, 20h
0x180003313  pop     rbx
0x180003314  retn
```
