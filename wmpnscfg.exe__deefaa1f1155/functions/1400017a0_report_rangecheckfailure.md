# __report_rangecheckfailure

- ea: `0x1400017a0`
- end: `0x1400017a7`
- name: `__report_rangecheckfailure`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140004d0c`
- `0x140005034`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  __fastfail(8u);
}

```

## disassembly

```asm
0x1400017a0  mov     ecx, 8
0x1400017a5  int     29h; Win8: RtlFailFast(ecx)
```
