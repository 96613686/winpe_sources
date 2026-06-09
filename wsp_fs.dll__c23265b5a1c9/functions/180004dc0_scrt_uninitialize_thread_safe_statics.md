# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004dc0`
- end: `0x180004de8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004dc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004dcb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004dcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ddd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ddd`

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
0x180004dc0  sub     rsp, 28h
0x180004dc4  lea     rcx, CriticalSection; lpCriticalSection
0x180004dcb  call    cs:__imp_DeleteCriticalSection
0x180004dd1  mov     rcx, cs:hHandle; hObject
0x180004dd8  test    rcx, rcx
0x180004ddb  jz      short loc_180004DE3
0x180004ddd  call    cs:__imp_CloseHandle
0x180004de3  add     rsp, 28h
0x180004de7  retn
```
