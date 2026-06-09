# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004f50`
- end: `0x180004f78`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004f50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004f5b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004f5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f6d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180004f50  sub     rsp, 28h
0x180004f54  lea     rcx, CriticalSection; lpCriticalSection
0x180004f5b  call    cs:__imp_DeleteCriticalSection
0x180004f61  mov     rcx, cs:hHandle; hObject
0x180004f68  test    rcx, rcx
0x180004f6b  jz      short loc_180004F73
0x180004f6d  call    cs:__imp_CloseHandle
0x180004f73  add     rsp, 28h
0x180004f77  retn
```
