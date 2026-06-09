# wil::SetLastError(wil::FailureInfo const &)

- ea: `0x18000d0b8`
- end: `0x18000d117`
- name: `?SetLastError@wil@@YAXAEBUFailureInfo@1@@Z`
- size: `95`
- prototype: `void __fastcall(wil *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009bd0`

## callees

- `0x18000d0b8`
- `0x180010acc`
- `0x1800113bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0c1`

## pseudocode

```c
void __fastcall wil::SetLastError(wil *this, const struct wil::FailureInfo *a2)
{
  DWORD CurrentThreadId; // eax
  wil::details_abi *v4; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  CurrentThreadId = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != CurrentThreadId )
  {
    if ( _InterlockedIncrement(&`wil::SetLastError'::`5'::depth) < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = CurrentThreadId;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v4);
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, this);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x18000d0b8  push    rbx
0x18000d0ba  sub     rsp, 20h
0x18000d0be  mov     rbx, rcx
0x18000d0c1  call    cs:__imp_GetCurrentThreadId
0x18000d0c7  mov     edx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d0cd  cmp     edx, eax
0x18000d0cf  jz      short loc_18000D111
0x18000d0d1  mov     edx, 1
0x18000d0d6  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, edx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000d0de  inc     edx; bool
0x18000d0e0  cmp     edx, 4
0x18000d0e3  jge     short loc_18000D10A
0x18000d0e5  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d0eb  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000d0f0  test    rax, rax
0x18000d0f3  jz      short loc_18000D100
0x18000d0f5  mov     rdx, rbx; struct wil::FailureInfo *
0x18000d0f8  mov     rcx, rax; this
0x18000d0fb  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000d100  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d10a  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000d111  add     rsp, 20h
0x18000d115  pop     rbx
0x18000d116  retn
```
