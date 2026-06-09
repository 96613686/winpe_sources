# _RevertImpersonationToken(void *)

- ea: `0x180016f7c`
- end: `0x180016fa4`
- name: `?_RevertImpersonationToken@@YAXPEAX@Z`
- size: `40`
- prototype: `void __fastcall(HANDLE hObject)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016fac`

## callees

- `0x180016f7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180016f8a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180016f8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016f98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016f98`

## pseudocode

```c
void __fastcall _RevertImpersonationToken(HANDLE hObject)
{
  SetThreadToken(0, hObject);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x180016f7c  push    rbx
0x180016f7e  sub     rsp, 20h
0x180016f82  mov     rbx, rcx
0x180016f85  mov     rdx, rcx; Token
0x180016f88  xor     ecx, ecx; Thread
0x180016f8a  call    cs:__imp_SetThreadToken
0x180016f90  test    rbx, rbx
0x180016f93  jz      short loc_180016F9E
0x180016f95  mov     rcx, rbx; hObject
0x180016f98  call    cs:__imp_CloseHandle
0x180016f9e  add     rsp, 20h
0x180016fa2  pop     rbx
0x180016fa3  retn
```
