# __scrt_uninitialize_thread_safe_statics

- ea: `0x180095c20`
- end: `0x180095c48`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180095c20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180095c2b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180095c2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095c3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095c3d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180184E80);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180095c20  sub     rsp, 28h
0x180095c24  lea     rcx, stru_180184E80; lpCriticalSection
0x180095c2b  call    cs:__imp_DeleteCriticalSection
0x180095c31  mov     rcx, cs:hHandle; hObject
0x180095c38  test    rcx, rcx
0x180095c3b  jz      short loc_180095C43
0x180095c3d  call    cs:__imp_CloseHandle
0x180095c43  add     rsp, 28h
0x180095c47  retn
```
