# __scrt_uninitialize_thread_safe_statics

- ea: `0x140003370`
- end: `0x140003398`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003370`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000338d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000338d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000337b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000337b`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_14001A450);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x140003370  sub     rsp, 28h
0x140003374  lea     rcx, stru_14001A450; lpCriticalSection
0x14000337b  call    cs:__imp_DeleteCriticalSection
0x140003381  mov     rcx, cs:hObject; hObject
0x140003388  test    rcx, rcx
0x14000338b  jz      short loc_140003393
0x14000338d  call    cs:__imp_CloseHandle
0x140003393  add     rsp, 28h
0x140003397  retn
```
