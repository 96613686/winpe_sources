# IsLogPathOnInstance(_FLT_INSTANCE * const)

- ea: `0x140002628`
- end: `0x14000263d`
- name: `?IsLogPathOnInstance@@YAEQEAU_FLT_INSTANCE@@@Z`
- size: `21`
- prototype: `unsigned __int8 __fastcall(struct _FLT_INSTANCE *const)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001fab0`

## callees

- `0x140002628`

## pseudocode

```c
unsigned __int8 __fastcall IsLogPathOnInstance(struct _FLT_INSTANCE *const a1)
{
  unsigned __int8 result; // al

  result = (unsigned __int8)Instance;
  if ( Instance )
    return a1 == Instance;
  return result;
}

```

## disassembly

```asm
0x140002628  mov     rax, cs:Instance
0x14000262f  test    rax, rax
0x140002632  jnz     short loc_140002636
0x140002634  retn
0x140002636  cmp     rcx, rax
0x140002639  setz    al
0x14000263c  retn
```
