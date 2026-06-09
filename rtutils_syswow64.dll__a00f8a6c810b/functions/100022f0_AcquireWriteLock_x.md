# AcquireWriteLock(x)

- ea: `0x100022f0`
- end: `0x1000230c`
- name: `_AcquireWriteLock@4`
- size: `28`
- prototype: `int __thiscall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x10002160`
- `0x10002320`
- `0x10002470`
- `0x100030b0`
- `0x100066c0`
- `0x100077c0`
- `0x100081de`
- `0x10009b20`

## callees

- `0x100022f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x100054b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x100054b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100022f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100022f6`

## pseudocode

```c
int __thiscall AcquireWriteLock(LPCRITICAL_SECTION lpCriticalSection)
{
  int result; // eax

  EnterCriticalSection(lpCriticalSection);
  result = _InterlockedExchangeAdd((volatile signed __int32 *)&lpCriticalSection[1], 0xFFFFFFFF);
  if ( result >= 0 )
    return WaitForSingleObject((HANDLE)lpCriticalSection[1].LockCount, 0xFFFFFFFF);
  return result;
}

```

## disassembly

```asm
0x100022f0  mov     edi, edi
0x100022f2  push    esi
0x100022f3  mov     esi, ecx
0x100022f5  push    esi; lpCriticalSection
0x100022f6  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100022fc  or      eax, 0FFFFFFFFh
0x100022ff  lock xadd [esi+18h], eax
0x10002304  jns     loc_100054AD
0x1000230a  pop     esi
0x1000230b  retn
0x100054ad  push    0FFFFFFFFh; dwMilliseconds
0x100054af  push    dword ptr [esi+1Ch]; hHandle
0x100054b2  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x100054b8  pop     esi
0x100054b9  retn
```
