# WinHvpTeardownLpIndexCache

- ea: `0x140021864`
- end: `0x14002188f`
- name: `WinHvpTeardownLpIndexCache`
- size: `43`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001e5ec`
- `0x140021680`
- `0x14002a804`

## callees

- `0x14000b040`
- `0x140021864`

## pseudocode

```c
__int64 WinHvpTeardownLpIndexCache()
{
  __int64 result; // rax

  if ( WinHvpProcessorToLpIndex )
  {
    result = WinHvpFreePoolWithTag(WinHvpProcessorToLpIndex, 1433815127);
    WinHvpProcessorToLpIndex = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140021864  sub     rsp, 28h
0x140021868  mov     rcx, cs:WinHvpProcessorToLpIndex
0x14002186f  test    rcx, rcx
0x140021872  jz      short loc_140021889
0x140021874  mov     edx, 55764857h
0x140021879  call    WinHvpFreePoolWithTag
0x14002187e  mov     cs:WinHvpProcessorToLpIndex, 0
0x140021889  add     rsp, 28h
0x14002188d  retn
```
