# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800022b0`
- end: `0x1800022d8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800022b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800022bb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800022bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022cd`

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
0x1800022b0  sub     rsp, 28h
0x1800022b4  lea     rcx, CriticalSection; lpCriticalSection
0x1800022bb  call    cs:__imp_DeleteCriticalSection
0x1800022c1  mov     rcx, cs:hHandle; hObject
0x1800022c8  test    rcx, rcx
0x1800022cb  jz      short loc_1800022D3
0x1800022cd  call    cs:__imp_CloseHandle
0x1800022d3  add     rsp, 28h
0x1800022d7  retn
```
