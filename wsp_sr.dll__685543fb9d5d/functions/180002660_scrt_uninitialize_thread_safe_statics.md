# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002660`
- end: `0x180002688`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000266b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000266b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000267d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000267d`

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
0x180002660  sub     rsp, 28h
0x180002664  lea     rcx, CriticalSection; lpCriticalSection
0x18000266b  call    cs:__imp_DeleteCriticalSection
0x180002671  mov     rcx, cs:hHandle; hObject
0x180002678  test    rcx, rcx
0x18000267b  jz      short loc_180002683
0x18000267d  call    cs:__imp_CloseHandle
0x180002683  add     rsp, 28h
0x180002687  retn
```
