# __report_rangecheckfailure

- ea: `0x1400014d0`
- end: `0x1400014d7`
- name: `__report_rangecheckfailure`
- size: `7`
- prototype: `void __noreturn()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400030b8`
- `0x14000550c`
- `0x140005834`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  __fastfail(8u);
}

```

## disassembly

```asm
0x1400014d0  mov     ecx, 8
0x1400014d5  int     29h; Win8: RtlFailFast(ecx)
```
