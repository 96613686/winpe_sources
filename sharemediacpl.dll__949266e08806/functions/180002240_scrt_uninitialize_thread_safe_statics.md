# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002240`
- end: `0x180002268`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002240`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000225d`
- `KERNEL32!CloseHandle` at `0x18000225d`
- `KERNEL32!DeleteCriticalSection` at `0x18000224b`
- `KERNEL32!DeleteCriticalSection` at `0x18000224b`

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
0x180002240  sub     rsp, 28h
0x180002244  lea     rcx, CriticalSection; lpCriticalSection
0x18000224b  call    cs:__imp_DeleteCriticalSection
0x180002251  mov     rcx, cs:hHandle; hObject
0x180002258  test    rcx, rcx
0x18000225b  jz      short loc_180002263
0x18000225d  call    cs:__imp_CloseHandle
0x180002263  add     rsp, 28h
0x180002267  retn
```
