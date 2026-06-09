# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800053a0`
- end: `0x1800053c8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800053a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800053ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800053ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053bd`

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
0x1800053a0  sub     rsp, 28h
0x1800053a4  lea     rcx, CriticalSection; lpCriticalSection
0x1800053ab  call    cs:__imp_DeleteCriticalSection
0x1800053b1  mov     rcx, cs:hHandle; hObject
0x1800053b8  test    rcx, rcx
0x1800053bb  jz      short loc_1800053C3
0x1800053bd  call    cs:__imp_CloseHandle
0x1800053c3  add     rsp, 28h
0x1800053c7  retn
```
