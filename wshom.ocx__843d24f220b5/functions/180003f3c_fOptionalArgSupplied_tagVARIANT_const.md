# fOptionalArgSupplied(tagVARIANT const *)

- ea: `0x180003f3c`
- end: `0x180003f50`
- name: `?fOptionalArgSupplied@@YA_NPEBUtagVARIANT@@@Z`
- size: `20`
- prototype: `bool __fastcall(const struct tagVARIANT *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003750`
- `0x1800038c0`
- `0x180003dbc`
- `0x180005bbc`
- `0x180008600`
- `0x180008ef4`
- `0x18000d3d0`

## callees

- `0x180003f3c`

## pseudocode

```c
bool __fastcall fOptionalArgSupplied(const struct tagVARIANT *a1)
{
  return a1->vt != 10 || a1->lVal != -2147352572;
}

```

## disassembly

```asm
0x180003f3c  cmp     word ptr [rcx], 0Ah
0x180003f40  jnz     short loc_180003F4D
0x180003f42  cmp     dword ptr [rcx+8], 80020004h
0x180003f49  setnz   al
0x180003f4c  retn
0x180003f4d  mov     al, 1
0x180003f4f  retn
```
