# ReleaseReadLock

- ea: `0x180009810`
- end: `0x180009830`
- name: `ReleaseReadLock`
- size: `32`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `1`
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

## callees

- `0x180009810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009825`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009825`

## pseudocode

```c
signed __int32 __fastcall ReleaseReadLock(__int64 a1)
{
  signed __int32 result; // eax

  result = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 40), 0xFFFFFFFF);
  if ( result - 1 < 0 )
    return SetEvent(*(HANDLE *)(a1 + 48));
  return result;
}

```

## disassembly

```asm
0x180009810  sub     rsp, 28h
0x180009814  or      eax, 0FFFFFFFFh
0x180009817  lock xadd [rcx+28h], eax
0x18000981c  cmp     eax, 1
0x18000981f  jns     short loc_18000982B
0x180009821  mov     rcx, [rcx+30h]; hEvent
0x180009825  call    cs:__imp_SetEvent
0x18000982b  add     rsp, 28h
0x18000982f  retn
```
