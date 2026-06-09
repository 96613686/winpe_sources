# wil::details::ThreadFailureCallbackHolder::IsWatching(void)

- ea: `0x18000ca40`
- end: `0x18000ca48`
- name: `?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ`
- size: `8`
- prototype: `bool __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ca18`

## pseudocode

```c
bool __fastcall wil::details::ThreadFailureCallbackHolder::IsWatching(wil::details::ThreadFailureCallbackHolder *this)
{
  return *((_DWORD *)this + 6) != 0;
}

```

## disassembly

```asm
0x18000ca40  cmp     dword ptr [rcx+18h], 0
0x18000ca44  setnz   al
0x18000ca47  retn
```
