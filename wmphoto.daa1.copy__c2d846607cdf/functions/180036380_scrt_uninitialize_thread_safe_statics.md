# __scrt_uninitialize_thread_safe_statics

- ea: `0x180036380`
- end: `0x1800363a8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180036380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003638b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003638b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003639d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003639d`

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
0x180036380  sub     rsp, 28h
0x180036384  lea     rcx, CriticalSection; lpCriticalSection
0x18003638b  call    cs:__imp_DeleteCriticalSection
0x180036391  mov     rcx, cs:hHandle; hObject
0x180036398  test    rcx, rcx
0x18003639b  jz      short loc_1800363A3
0x18003639d  call    cs:__imp_CloseHandle
0x1800363a3  add     rsp, 28h
0x1800363a7  retn
```
