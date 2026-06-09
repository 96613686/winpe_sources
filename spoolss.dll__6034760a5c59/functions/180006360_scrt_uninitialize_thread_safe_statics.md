# __scrt_uninitialize_thread_safe_statics

- ea: `0x180006360`
- end: `0x180006388`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000636b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000636b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000637d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000637d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x180006360  sub     rsp, 28h
0x180006364  lea     rcx, CriticalSection; lpCriticalSection
0x18000636b  call    cs:__imp_DeleteCriticalSection
0x180006371  mov     rcx, cs:hObject; hObject
0x180006378  test    rcx, rcx
0x18000637b  jz      short loc_180006383
0x18000637d  call    cs:__imp_CloseHandle
0x180006383  add     rsp, 28h
0x180006387  retn
```
