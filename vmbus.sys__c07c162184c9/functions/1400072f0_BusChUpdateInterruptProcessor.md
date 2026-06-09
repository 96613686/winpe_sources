# BusChUpdateInterruptProcessor

- ea: `0x1400072f0`
- end: `0x140007302`
- name: `BusChUpdateInterruptProcessor`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14002dc40`

## pseudocode

```c
__int64 __fastcall BusChUpdateInterruptProcessor(_QWORD *a1)
{
  return ChClientModifyChannel(*a1);
}

```

## disassembly

```asm
0x1400072f0  sub     rsp, 28h
0x1400072f4  mov     rcx, [rcx]
0x1400072f7  call    ChClientModifyChannel
0x1400072fc  add     rsp, 28h
0x140007300  retn
```
