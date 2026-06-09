# __scrt_uninitialize_thread_safe_statics

- ea: `0x14000fc10`
- end: `0x14000fc38`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000fc10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000fc1b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000fc1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fc2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fc2d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_140082FB0);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x14000fc10  sub     rsp, 28h
0x14000fc14  lea     rcx, stru_140082FB0; lpCriticalSection
0x14000fc1b  call    cs:__imp_DeleteCriticalSection
0x14000fc21  mov     rcx, cs:hHandle; hObject
0x14000fc28  test    rcx, rcx
0x14000fc2b  jz      short loc_14000FC33
0x14000fc2d  call    cs:__imp_CloseHandle
0x14000fc33  add     rsp, 28h
0x14000fc37  retn
```
