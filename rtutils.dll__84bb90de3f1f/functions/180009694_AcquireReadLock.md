# AcquireReadLock

- ea: `0x180009694`
- end: `0x1800096b6`
- name: `AcquireReadLock`
- size: `34`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x1800017c0`
- `0x1800030d0`
- `0x180004610`
- `0x1800046c0`
- `0x180004cc0`
- `0x180005140`
- `0x18000570c`
- `0x180006794`
- `0x1800078b0`
- `0x180009a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800096af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000969d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000969d`

## pseudocode

```c
void __fastcall AcquireReadLock(__int64 a1)
{
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 40));
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
}

```

## disassembly

```asm
0x180009694  push    rbx
0x180009696  sub     rsp, 20h
0x18000969a  mov     rbx, rcx
0x18000969d  call    cs:__imp_EnterCriticalSection
0x1800096a3  lock inc dword ptr [rbx+28h]
0x1800096a7  mov     rcx, rbx
0x1800096aa  add     rsp, 20h
0x1800096ae  pop     rbx
0x1800096af  jmp     cs:__imp_LeaveCriticalSection
```
