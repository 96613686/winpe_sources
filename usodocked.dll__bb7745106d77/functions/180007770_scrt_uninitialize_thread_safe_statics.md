# __scrt_uninitialize_thread_safe_statics

- ea: `0x180007770`
- end: `0x180007798`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000777b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000777b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000778d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000778d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180095428);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180007770  sub     rsp, 28h
0x180007774  lea     rcx, stru_180095428; lpCriticalSection
0x18000777b  call    cs:__imp_DeleteCriticalSection
0x180007781  mov     rcx, cs:hHandle; hObject
0x180007788  test    rcx, rcx
0x18000778b  jz      short loc_180007793
0x18000778d  call    cs:__imp_CloseHandle
0x180007793  add     rsp, 28h
0x180007797  retn
```
