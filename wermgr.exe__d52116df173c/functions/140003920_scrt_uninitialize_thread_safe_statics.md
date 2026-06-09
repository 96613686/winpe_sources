# __scrt_uninitialize_thread_safe_statics

- ea: `0x140003920`
- end: `0x140003948`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003920`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000393d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000393d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000392b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000392b`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_14002C5E8);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x140003920  sub     rsp, 28h
0x140003924  lea     rcx, stru_14002C5E8; lpCriticalSection
0x14000392b  call    cs:__imp_DeleteCriticalSection
0x140003931  mov     rcx, cs:hObject; hObject
0x140003938  test    rcx, rcx
0x14000393b  jz      short loc_140003943
0x14000393d  call    cs:__imp_CloseHandle
0x140003943  add     rsp, 28h
0x140003947  retn
```
