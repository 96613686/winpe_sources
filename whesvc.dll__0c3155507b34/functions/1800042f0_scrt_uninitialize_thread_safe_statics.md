# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800042f0`
- end: `0x180004318`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800042f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800042fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800042fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000430d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000430d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180034808);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x1800042f0  sub     rsp, 28h
0x1800042f4  lea     rcx, stru_180034808; lpCriticalSection
0x1800042fb  call    cs:__imp_DeleteCriticalSection
0x180004301  mov     rcx, cs:hHandle; hObject
0x180004308  test    rcx, rcx
0x18000430b  jz      short loc_180004313
0x18000430d  call    cs:__imp_CloseHandle
0x180004313  add     rsp, 28h
0x180004317  retn
```
