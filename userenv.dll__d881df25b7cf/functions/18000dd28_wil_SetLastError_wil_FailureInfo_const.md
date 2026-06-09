# wil::SetLastError(wil::FailureInfo const &)

- ea: `0x18000dd28`
- end: `0x18000dd8e`
- name: `?SetLastError@wil@@YAXAEBUFailureInfo@1@@Z`
- size: `102`
- prototype: `void __fastcall(wil *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a550`

## callees

- `0x18000dd28`
- `0x18001198c`
- `0x1800122f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dd31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dd31`

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
0x18000dd28  push    rbx
0x18000dd2a  sub     rsp, 20h
0x18000dd2e  mov     rbx, rcx
0x18000dd31  call    cs:__imp_GetCurrentThreadId
0x18000dd38  nop     dword ptr [rax+rax+00h]
0x18000dd3d  mov     edx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000dd43  cmp     edx, eax
0x18000dd45  jz      short loc_18000DD87
0x18000dd47  mov     edx, 1
0x18000dd4c  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, edx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000dd54  inc     edx; bool
0x18000dd56  cmp     edx, 4
0x18000dd59  jge     short loc_18000DD80
0x18000dd5b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000dd61  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000dd66  test    rax, rax
0x18000dd69  jz      short loc_18000DD76
0x18000dd6b  mov     rdx, rbx; struct wil::FailureInfo *
0x18000dd6e  mov     rcx, rax; this
0x18000dd71  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000dd76  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000dd80  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000dd87  add     rsp, 20h
0x18000dd8b  pop     rbx
0x18000dd8c  retn
```
