# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004030`
- end: `0x180004058`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004030`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000403b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000403b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000404d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000404d`

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
0x180004030  sub     rsp, 28h
0x180004034  lea     rcx, CriticalSection; lpCriticalSection
0x18000403b  call    cs:__imp_DeleteCriticalSection
0x180004041  mov     rcx, cs:hHandle; hObject
0x180004048  test    rcx, rcx
0x18000404b  jz      short loc_180004053
0x18000404d  call    cs:__imp_CloseHandle
0x180004053  add     rsp, 28h
0x180004057  retn
```
