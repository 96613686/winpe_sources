# std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(void)

- ea: `0x180005a70`
- end: `0x180005a88`
- name: `??1?$shared_ptr@$$CBVMiSession@mi@@@std@@QEAA@XZ`
- size: `24`
- prototype: ``
- caller_count: `36`
- callee_count: `2`
- tags: ``

## callers

- `0x18002a3b0`
- `0x18002a3d4`
- `0x18002a465`
- `0x18002a477`
- `0x18002a999`
- `0x18002a9ab`
- `0x18002ab8a`
- `0x18002ab9c`
- `0x18002ac3c`
- `0x18002ac4e`
- `0x18002ac97`
- `0x18002afdb`
- `0x18002afed`
- `0x18002b039`
- `0x18002b05d`
- `0x18002b269`
- `0x18002b27b`
- `0x18002b291`
- `0x18002b2a7`
- `0x18002b2cf`
- `0x18002b336`
- `0x18002b55f`
- `0x18002b571`
- `0x18002b6b8`
- `0x18002b6ee`
- `0x18002b700`
- `0x18002bbfc`
- `0x18002bcb9`
- `0x18002bda3`
- `0x18002be0f`
- `0x18002be45`
- `0x18002c2dc`
- `0x18002c31a`
- `0x18002c36b`
- `0x18002c582`
- `0x18002c5af`

## callees

- `0x180005a70`
- `0x180006630`

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
0x180005a70  sub     rsp, 28h
0x180005a74  mov     rcx, [rcx+8]; this
0x180005a78  test    rcx, rcx
0x180005a7b  jz      short loc_180005A82
0x180005a7d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ
0x180005a82  add     rsp, 28h
0x180005a86  retn
```
