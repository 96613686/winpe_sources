# _guard_dispatch_icall

- ea: `0x1800148e0`
- end: `0x1800148e6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `92`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001010`
- `0x1800023a4`
- `0x1800024e0`
- `0x1800028c0`
- `0x180002fc4`
- `0x180003020`
- `0x180003248`
- `0x18000345c`
- `0x180003584`
- `0x180003948`
- `0x180003aa8`
- `0x180003bd0`
- `0x180003d20`
- `0x1800040e0`
- `0x180004230`
- `0x18000426c`
- `0x180004298`
- `0x180004724`
- `0x180004cf0`
- `0x180005798`
- `0x1800057b8`
- `0x180005960`
- `0x180005a50`
- `0x180006730`
- `0x1800069c0`
- `0x180006a30`
- `0x180006b60`
- `0x180006cf4`
- `0x18000739c`
- `0x180007850`
- `0x180007dec`
- `0x18000820c`
- `0x180008910`
- `0x180008f30`
- `0x180008f78`
- `0x18000917c`
- `0x180009320`
- `0x180009534`
- `0x18000957c`
- `0x18000960c`
- `0x1800096f4`
- `0x180009888`
- `0x1800099b0`
- `0x1800099e0`
- `0x180009c54`
- `0x18000a190`
- `0x18000a36c`
- `0x18000a4d0`
- `0x18000a580`
- `0x18000acb4`

## callees

- `0x180014900`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x1800148e0  jmp     cs:__guard_dispatch_icall_fptr
```
