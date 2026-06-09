# __scrt_uninitialize_thread_safe_statics

- ea: `0x180030840`
- end: `0x180030868`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180030840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003084b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003084b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003085d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003085d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_18004E958);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x180030840  sub     rsp, 28h
0x180030844  lea     rcx, stru_18004E958; lpCriticalSection
0x18003084b  call    cs:__imp_DeleteCriticalSection
0x180030851  mov     rcx, cs:hObject; hObject
0x180030858  test    rcx, rcx
0x18003085b  jz      short loc_180030863
0x18003085d  call    cs:__imp_CloseHandle
0x180030863  add     rsp, 28h
0x180030867  retn
```
