# __scrt_uninitialize_thread_safe_statics

- ea: `0x180008840`
- end: `0x180008868`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000884b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000884b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000885d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000885d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180038628);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180008840  sub     rsp, 28h
0x180008844  lea     rcx, stru_180038628; lpCriticalSection
0x18000884b  call    cs:__imp_DeleteCriticalSection
0x180008851  mov     rcx, cs:hHandle; hObject
0x180008858  test    rcx, rcx
0x18000885b  jz      short loc_180008863
0x18000885d  call    cs:__imp_CloseHandle
0x180008863  add     rsp, 28h
0x180008867  retn
```
