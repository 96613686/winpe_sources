# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800430a0`
- end: `0x1800430c8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800430a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800430ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800430ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800430bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800430bd`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180062C98);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x1800430a0  sub     rsp, 28h
0x1800430a4  lea     rcx, stru_180062C98; lpCriticalSection
0x1800430ab  call    cs:__imp_DeleteCriticalSection
0x1800430b1  mov     rcx, cs:hHandle; hObject
0x1800430b8  test    rcx, rcx
0x1800430bb  jz      short loc_1800430C3
0x1800430bd  call    cs:__imp_CloseHandle
0x1800430c3  add     rsp, 28h
0x1800430c7  retn
```
