# std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(void)

- ea: `0x180005a30`
- end: `0x180005a47`
- name: `??1?$shared_ptr@$$CBVMiSession@mi@@@std@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(__int64)`
- caller_count: `36`
- callee_count: `2`
- tags: ``

## callers

- `0x180029f00`
- `0x180029f24`
- `0x180029fb5`
- `0x180029fc7`
- `0x18002a4cc`
- `0x18002a4de`
- `0x18002a6bd`
- `0x18002a6cf`
- `0x18002a76f`
- `0x18002a781`
- `0x18002a7ca`
- `0x18002ab0d`
- `0x18002ab1f`
- `0x18002ab6b`
- `0x18002ab8f`
- `0x18002ad98`
- `0x18002adaa`
- `0x18002adc0`
- `0x18002add6`
- `0x18002adfe`
- `0x18002ae64`
- `0x18002b089`
- `0x18002b09b`
- `0x18002b1de`
- `0x18002b214`
- `0x18002b226`
- `0x18002b715`
- `0x18002b7d1`
- `0x18002b8bb`
- `0x18002b927`
- `0x18002b95d`
- `0x18002bde8`
- `0x18002be26`
- `0x18002be75`
- `0x18002c08b`
- `0x18002c0b7`

## callees

- `0x180005a30`
- `0x1800065ec`

## pseudocode

```c
void __fastcall std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(__int64 a1)
{
  std::_Ref_count_base *v1; // rcx

  v1 = *(std::_Ref_count_base **)(a1 + 8);
  if ( v1 )
    std::_Ref_count_base::_Decref(v1);
}

```

## disassembly

```asm
0x180005a30  sub     rsp, 28h
0x180005a34  mov     rcx, [rcx+8]; this
0x180005a38  test    rcx, rcx
0x180005a3b  jz      short loc_180005A42
0x180005a3d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ
0x180005a42  add     rsp, 28h
0x180005a46  retn
```
