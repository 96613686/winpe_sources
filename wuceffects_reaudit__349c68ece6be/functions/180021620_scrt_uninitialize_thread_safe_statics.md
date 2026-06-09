# __scrt_uninitialize_thread_safe_statics

- ea: `0x180021620`
- end: `0x180021648`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180021620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002162b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002162b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002163d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002163d`

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
0x180021620  sub     rsp, 28h
0x180021624  lea     rcx, CriticalSection; lpCriticalSection
0x18002162b  call    cs:__imp_DeleteCriticalSection
0x180021631  mov     rcx, cs:hHandle; hObject
0x180021638  test    rcx, rcx
0x18002163b  jz      short loc_180021643
0x18002163d  call    cs:__imp_CloseHandle
0x180021643  add     rsp, 28h
0x180021647  retn
```
