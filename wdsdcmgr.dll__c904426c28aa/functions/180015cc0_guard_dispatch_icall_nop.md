# _guard_dispatch_icall_nop

- ea: `0x180015cc0`
- end: `0x180015cc2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `53`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001230`
- `0x1800013d0`
- `0x1800014c4`
- `0x180001ac0`
- `0x180001be0`
- `0x180001cf8`
- `0x1800026ac`
- `0x18000294c`
- `0x180003508`
- `0x1800036dc`
- `0x180003acc`
- `0x1800042f4`
- `0x180005430`
- `0x18000563c`
- `0x180005818`
- `0x18000600c`
- `0x1800063b4`
- `0x180006bec`
- `0x180006c98`
- `0x180006dfc`
- `0x180007798`
- `0x1800078b0`
- `0x180007960`
- `0x180007ad0`
- `0x180007f90`
- `0x1800084a0`
- `0x180008700`
- `0x180008810`
- `0x180008840`
- `0x180008920`
- `0x18000af78`
- `0x18000d540`
- `0x18000d7bc`
- `0x18000d954`
- `0x18000e194`
- `0x18000e310`
- `0x18000e504`
- `0x18000e750`
- `0x18000e8f0`
- `0x18000ef20`
- `0x18000f060`
- `0x1800112f0`
- `0x180011854`
- `0x180012540`
- `0x1800149a8`
- `0x180014d58`
- `0x180014e1c`
- `0x180014f28`
- `0x18001517c`
- `0x180015404`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x180015cc0  jmp     rax
```
