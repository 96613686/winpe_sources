# wil::details::RecordReturn(long)

- ea: `0x140005350`
- end: `0x140005366`
- name: `?RecordReturn@details@wil@@YAHJ@Z`
- size: `22`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140003368`
- `0x140004da4`

## pseudocode

```c
__int64 __fastcall wil::details::RecordReturn(wil::details *this)
{
  `wil::details::RecordReturn'::`2'::s_hrErrorLast = (int)this;
  return (unsigned int)_InterlockedIncrement(&`wil::details::RecordReturn'::`2'::s_cErrorCount);
}

```

## disassembly

```asm
0x140005350  mov     cs:?s_hrErrorLast@?1??RecordReturn@details@wil@@YAHJ@Z@4JC, ecx; long volatile `wil::details::RecordReturn(long)'::`2'::s_hrErrorLast
0x140005356  mov     eax, 1
0x14000535b  lock xadd cs:?s_cErrorCount@?1??RecordReturn@details@wil@@YAHJ@Z@4JC, eax; long volatile `wil::details::RecordReturn(long)'::`2'::s_cErrorCount
0x140005363  inc     eax
0x140005365  retn
```
