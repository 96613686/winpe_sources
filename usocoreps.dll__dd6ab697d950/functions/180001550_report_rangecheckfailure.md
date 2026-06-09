# __report_rangecheckfailure

- ea: `0x180001550`
- end: `0x180001557`
- name: `__report_rangecheckfailure`
- size: `7`
- prototype: `void __noreturn()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800043ec`
- `0x180004714`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  __fastfail(8u);
}

```

## disassembly

```asm
0x180001550  mov     ecx, 8
0x180001555  int     29h; Win8: RtlFailFast(ecx)
```
