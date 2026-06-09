# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800066d0`
- end: `0x1800066f8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800066d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800066db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800066db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066ed`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x1800066d0  sub     rsp, 28h
0x1800066d4  lea     rcx, CriticalSection; lpCriticalSection
0x1800066db  call    cs:__imp_DeleteCriticalSection
0x1800066e1  mov     rcx, cs:hObject; hObject
0x1800066e8  test    rcx, rcx
0x1800066eb  jz      short loc_1800066F3
0x1800066ed  call    cs:__imp_CloseHandle
0x1800066f3  add     rsp, 28h
0x1800066f7  retn
```
