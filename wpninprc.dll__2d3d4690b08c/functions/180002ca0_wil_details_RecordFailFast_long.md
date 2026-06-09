# wil::details::RecordFailFast(long)

- ea: `0x180002ca0`
- end: `0x180002cac`
- name: `?RecordFailFast@details@wil@@YAHJ@Z`
- size: `12`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800039c0`
- `0x180004d2c`

## pseudocode

```c
__int64 __fastcall wil::details::RecordFailFast(wil::details *this)
{
  `wil::details::RecordFailFast'::`2'::s_hrErrorLast = (int)this;
  return 1;
}

```

## disassembly

```asm
0x180002ca0  mov     cs:?s_hrErrorLast@?1??RecordFailFast@details@wil@@YAHJ@Z@4JC, ecx; long volatile `wil::details::RecordFailFast(long)'::`2'::s_hrErrorLast
0x180002ca6  mov     eax, 1
0x180002cab  retn
```
