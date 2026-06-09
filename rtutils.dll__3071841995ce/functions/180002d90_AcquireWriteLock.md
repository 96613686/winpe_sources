# AcquireWriteLock

- ea: `0x180002d90`
- end: `0x180002dc9`
- name: `AcquireWriteLock`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c20`
- `0x180004c10`
- `0x180005450`
- `0x180006794`
- `0x1800078b0`
- `0x180009a30`

## callees

- `0x180002d90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002dbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d99`

## pseudocode

```c
DWORD __fastcall AcquireWriteLock(__int64 a1)
{
  DWORD result; // eax

  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  result = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 40), 0xFFFFFFFF);
  if ( (int)(result - 1) >= 0 )
    return WaitForSingleObject(*(HANDLE *)(a1 + 48), 0xFFFFFFFF);
  return result;
}

```

## disassembly

```asm
0x180002d90  push    rbx
0x180002d92  sub     rsp, 20h
0x180002d96  mov     rbx, rcx
0x180002d99  call    cs:__imp_EnterCriticalSection
0x180002d9f  mov     eax, 0FFFFFFFFh
0x180002da4  lock xadd [rbx+28h], eax
0x180002da9  cmp     eax, 1
0x180002dac  js      short loc_180002DC3
0x180002dae  mov     rcx, [rbx+30h]
0x180002db2  mov     edx, 0FFFFFFFFh
0x180002db7  add     rsp, 20h
0x180002dbb  pop     rbx
0x180002dbc  jmp     cs:__imp_WaitForSingleObject
0x180002dc3  add     rsp, 20h
0x180002dc7  pop     rbx
0x180002dc8  retn
```
