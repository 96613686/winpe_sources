# __scrt_uninitialize_thread_safe_statics

- ea: `0x180036950`
- end: `0x180036978`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180036950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003695b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003695b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003696d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003696d`

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
0x180036950  sub     rsp, 28h
0x180036954  lea     rcx, CriticalSection; lpCriticalSection
0x18003695b  call    cs:__imp_DeleteCriticalSection
0x180036961  mov     rcx, cs:hHandle; hObject
0x180036968  test    rcx, rcx
0x18003696b  jz      short loc_180036973
0x18003696d  call    cs:__imp_CloseHandle
0x180036973  add     rsp, 28h
0x180036977  retn
```
