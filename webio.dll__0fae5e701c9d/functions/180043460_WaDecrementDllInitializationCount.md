# WaDecrementDllInitializationCount

- ea: `0x180043460`
- end: `0x1800434b8`
- name: `WaDecrementDllInitializationCount`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001fac8`
- `0x18001fc90`

## callees

- `0x180043460`
- `0x1800434c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043482`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043482`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004346b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004346b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800434ac`

## pseudocode

```c
void WaDecrementDllInitializationCount()
{
  int v0; // eax

  AcquireSRWLockExclusive(&WaDllInitializationLock);
  v0 = WaDllInitializationCount;
  if ( WaDllInitializationCount == 1 )
  {
    GetCurrentThreadId();
    WapTerminateDll();
    v0 = WaDllInitializationCount;
  }
  WaDllInitializationCount = v0 - 1;
  ReleaseSRWLockExclusive(&WaDllInitializationLock);
}

```

## disassembly

```asm
0x180043460  sub     rsp, 28h
0x180043464  lea     rcx, WaDllInitializationLock; SRWLock
0x18004346b  call    cs:__imp_AcquireSRWLockExclusive
0x180043472  nop     dword ptr [rax+rax+00h]
0x180043477  mov     eax, cs:WaDllInitializationCount
0x18004347d  cmp     eax, 1
0x180043480  jnz     short loc_180043499
0x180043482  call    cs:__imp_GetCurrentThreadId
0x180043489  nop     dword ptr [rax+rax+00h]
0x18004348e  call    WapTerminateDll
0x180043493  mov     eax, cs:WaDllInitializationCount
0x180043499  dec     eax
0x18004349b  lea     rcx, WaDllInitializationLock
0x1800434a2  mov     cs:WaDllInitializationCount, eax
0x1800434a8  add     rsp, 28h
0x1800434ac  jmp     cs:__imp_ReleaseSRWLockExclusive
```
