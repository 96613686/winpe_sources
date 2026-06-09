# WinHvpTeardownVpIndexCache

- ea: `0x14001e244`
- end: `0x14001e26f`
- name: `WinHvpTeardownVpIndexCache`
- size: `43`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001e11c`
- `0x14001e5ec`
- `0x14002a804`

## callees

- `0x14000b040`
- `0x14001e244`

## pseudocode

```c
__int64 WinHvpTeardownVpIndexCache()
{
  __int64 result; // rax

  if ( WinHvpProcessorToVpIndex )
  {
    result = WinHvpFreePoolWithTag(WinHvpProcessorToVpIndex, 1433815127);
    WinHvpProcessorToVpIndex = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001e244  sub     rsp, 28h
0x14001e248  mov     rcx, cs:WinHvpProcessorToVpIndex
0x14001e24f  test    rcx, rcx
0x14001e252  jz      short loc_14001E269
0x14001e254  mov     edx, 55764857h
0x14001e259  call    WinHvpFreePoolWithTag
0x14001e25e  mov     cs:WinHvpProcessorToVpIndex, 0
0x14001e269  add     rsp, 28h
0x14001e26d  retn
```
