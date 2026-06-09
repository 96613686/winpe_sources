# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800204d0`
- end: `0x1800204f8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800204d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800204db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800204db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800204ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800204ed`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180044448);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x1800204d0  sub     rsp, 28h
0x1800204d4  lea     rcx, stru_180044448; lpCriticalSection
0x1800204db  call    cs:__imp_DeleteCriticalSection
0x1800204e1  mov     rcx, cs:hHandle; hObject
0x1800204e8  test    rcx, rcx
0x1800204eb  jz      short loc_1800204F3
0x1800204ed  call    cs:__imp_CloseHandle
0x1800204f3  add     rsp, 28h
0x1800204f7  retn
```
