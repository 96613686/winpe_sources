# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002630`
- end: `0x180002658`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000263b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000263b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000264d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000264d`

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
0x180002630  sub     rsp, 28h
0x180002634  lea     rcx, CriticalSection; lpCriticalSection
0x18000263b  call    cs:__imp_DeleteCriticalSection
0x180002641  mov     rcx, cs:hHandle; hObject
0x180002648  test    rcx, rcx
0x18000264b  jz      short loc_180002653
0x18000264d  call    cs:__imp_CloseHandle
0x180002653  add     rsp, 28h
0x180002657  retn
```
