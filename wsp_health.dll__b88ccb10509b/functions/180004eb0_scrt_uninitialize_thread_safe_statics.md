# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004eb0`
- end: `0x180004ed8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004eb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004ebb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004ebb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ecd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ecd`

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
0x180004eb0  sub     rsp, 28h
0x180004eb4  lea     rcx, CriticalSection; lpCriticalSection
0x180004ebb  call    cs:__imp_DeleteCriticalSection
0x180004ec1  mov     rcx, cs:hHandle; hObject
0x180004ec8  test    rcx, rcx
0x180004ecb  jz      short loc_180004ED3
0x180004ecd  call    cs:__imp_CloseHandle
0x180004ed3  add     rsp, 28h
0x180004ed7  retn
```
