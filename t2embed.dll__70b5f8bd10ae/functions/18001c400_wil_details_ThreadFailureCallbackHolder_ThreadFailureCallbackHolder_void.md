# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18001c400`
- end: `0x18001c414`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c044`
- `0x18001c190`

## callees

- `0x18001c400`
- `0x180026a34`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  if ( *((_DWORD *)this + 6) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(this);
}

```

## disassembly

```asm
0x18001c400  sub     rsp, 28h
0x18001c404  cmp     dword ptr [rcx+18h], 0
0x18001c408  jz      short loc_18001C40F
0x18001c40a  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001c40f  add     rsp, 28h
0x18001c413  retn
```
