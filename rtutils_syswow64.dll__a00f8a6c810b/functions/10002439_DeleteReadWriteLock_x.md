# DeleteReadWriteLock(x)

- ea: `0x10002439`
- end: `0x10002468`
- name: `_DeleteReadWriteLock@4`
- size: `47`
- prototype: `int __thiscall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x100023a6`
- `0x10002e60`
- `0x10007af9`
- `0x1000983c`

## callees

- `0x10002439`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10002452`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10002452`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000244b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000244b`

## pseudocode

```c
void __thiscall DeleteReadWriteLock(LPCRITICAL_SECTION lpCriticalSection)
{
  if ( lpCriticalSection )
  {
    if ( lpCriticalSection[1].LockCount )
    {
      CloseHandle((HANDLE)lpCriticalSection[1].LockCount);
      DeleteCriticalSection(lpCriticalSection);
    }
    lpCriticalSection[1].LockCount = 0;
    lpCriticalSection[1].DebugInfo = 0;
  }
}

```

## disassembly

```asm
0x10002439  mov     edi, edi
0x1000243b  push    esi
0x1000243c  mov     esi, ecx
0x1000243e  test    esi, esi
0x10002440  jz      short loc_10002466
0x10002442  cmp     dword ptr [esi+1Ch], 0
0x10002446  jz      short loc_10002458
0x10002448  push    dword ptr [esi+1Ch]; hObject
0x1000244b  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10002451  push    esi; lpCriticalSection
0x10002452  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10002458  mov     dword ptr [esi+1Ch], 0
0x1000245f  mov     dword ptr [esi+18h], 0
0x10002466  pop     esi
0x10002467  retn
```
