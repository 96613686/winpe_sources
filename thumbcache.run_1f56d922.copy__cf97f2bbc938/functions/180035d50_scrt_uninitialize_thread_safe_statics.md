# __scrt_uninitialize_thread_safe_statics

- ea: `0x180035d50`
- end: `0x180035d78`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180035d50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035d6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035d6d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035d5b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035d5b`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hEvent )
    CloseHandle(hEvent);
}

```

## disassembly

```asm
0x180035d50  sub     rsp, 28h
0x180035d54  lea     rcx, CriticalSection; lpCriticalSection
0x180035d5b  call    cs:__imp_DeleteCriticalSection
0x180035d61  mov     rcx, cs:hEvent; hObject
0x180035d68  test    rcx, rcx
0x180035d6b  jz      short loc_180035D73
0x180035d6d  call    cs:__imp_CloseHandle
0x180035d73  add     rsp, 28h
0x180035d77  retn
```
