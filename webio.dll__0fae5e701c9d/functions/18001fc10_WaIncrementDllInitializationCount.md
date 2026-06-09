# WaIncrementDllInitializationCount

- ea: `0x18001fc10`
- end: `0x18001fc8a`
- name: `WaIncrementDllInitializationCount`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001fac8`

## callees

- `0x18001fc10`
- `0x180041758`
- `0x1800434c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fc5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fc71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fc5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fc71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fc1d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fc1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fc45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fc45`

## pseudocode

```c
__int64 WaIncrementDllInitializationCount()
{
  unsigned int v0; // ebx

  AcquireSRWLockExclusive(&WaDllInitializationLock);
  if ( ++WaDllInitializationCount == 1 )
  {
    GetCurrentThreadId();
    v0 = WapInitializeDll();
    if ( v0 )
    {
      GetCurrentThreadId();
      WapTerminateDll();
      --WaDllInitializationCount;
    }
  }
  else
  {
    v0 = 0;
  }
  ReleaseSRWLockExclusive(&WaDllInitializationLock);
  return v0;
}

```

## disassembly

```asm
0x18001fc10  push    rbx
0x18001fc12  sub     rsp, 20h
0x18001fc16  lea     rcx, WaDllInitializationLock; SRWLock
0x18001fc1d  call    cs:__imp_AcquireSRWLockExclusive
0x18001fc24  nop     dword ptr [rax+rax+00h]
0x18001fc29  mov     eax, cs:WaDllInitializationCount
0x18001fc2f  inc     eax
0x18001fc31  mov     cs:WaDllInitializationCount, eax
0x18001fc37  cmp     eax, 1
0x18001fc3a  jz      short loc_18001FC5A
0x18001fc3c  xor     ebx, ebx
0x18001fc3e  lea     rcx, WaDllInitializationLock; SRWLock
0x18001fc45  call    cs:__imp_ReleaseSRWLockExclusive
0x18001fc4c  nop     dword ptr [rax+rax+00h]
0x18001fc51  mov     eax, ebx
0x18001fc53  add     rsp, 20h
0x18001fc57  pop     rbx
0x18001fc58  retn
0x18001fc5a  call    cs:__imp_GetCurrentThreadId
0x18001fc61  nop     dword ptr [rax+rax+00h]
0x18001fc66  call    WapInitializeDll
0x18001fc6b  mov     ebx, eax
0x18001fc6d  test    eax, eax
0x18001fc6f  jz      short loc_18001FC3E
0x18001fc71  call    cs:__imp_GetCurrentThreadId
0x18001fc78  nop     dword ptr [rax+rax+00h]
0x18001fc7d  call    WapTerminateDll
0x18001fc82  dec     cs:WaDllInitializationCount
0x18001fc88  jmp     short loc_18001FC3E
```
