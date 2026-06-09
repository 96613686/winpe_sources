# DeleteReadWriteLock

- ea: `0x180003000`
- end: `0x180003034`
- name: `DeleteReadWriteLock`
- size: `52`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001100`
- `0x180002ae0`
- `0x180002c80`
- `0x180002e90`
- `0x180003450`
- `0x180006fc4`

## callees

- `0x180003000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000301f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000301f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003016`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003016`

## pseudocode

```c
__int64 __fastcall DeleteReadWriteLock(LPCRITICAL_SECTION lpCriticalSection)
{
  void *v2; // rcx
  __int64 result; // rax

  if ( lpCriticalSection )
  {
    v2 = *(void **)&lpCriticalSection[1].LockCount;
    if ( v2 )
    {
      CloseHandle(v2);
      DeleteCriticalSection(lpCriticalSection);
    }
    result = 0;
    *(_QWORD *)&lpCriticalSection[1].LockCount = 0;
    LODWORD(lpCriticalSection[1].DebugInfo) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003000  test    rcx, rcx
0x180003003  jz      short locret_180003033
0x180003005  push    rbx
0x180003006  sub     rsp, 20h
0x18000300a  mov     rbx, rcx
0x18000300d  mov     rcx, [rcx+30h]; hObject
0x180003011  test    rcx, rcx
0x180003014  jz      short loc_180003025
0x180003016  call    cs:__imp_CloseHandle
0x18000301c  mov     rcx, rbx; lpCriticalSection
0x18000301f  call    cs:__imp_DeleteCriticalSection
0x180003025  xor     eax, eax
0x180003027  mov     [rbx+30h], rax
0x18000302b  mov     [rbx+28h], eax
0x18000302e  add     rsp, 20h
0x180003032  pop     rbx
0x180003033  retn
```
