# std::default_delete<SharedMemory>::operator()(SharedMemory *)

- ea: `0x180005550`
- end: `0x18000558e`
- name: `??R?$default_delete@VSharedMemory@@@std@@QEBAXPEAVSharedMemory@@@Z`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000f994`

## callees

- `0x180005550`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005582`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005582`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005579`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005579`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180005566`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180005566`

## pseudocode

```c
void __fastcall std::default_delete<SharedMemory>::operator()(__int64 a1, __int64 a2)
{
  const void *v2; // rcx

  if ( a2 )
  {
    v2 = *(const void **)(a2 + 8);
    if ( v2 )
      UnmapViewOfFile(v2);
    if ( (unsigned __int64)(*(_QWORD *)a2 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(*(HANDLE *)a2);
    operator delete((void *)a2);
  }
}

```

## disassembly

```asm
0x180005550  test    rdx, rdx
0x180005553  jz      short locret_18000558D
0x180005555  push    rbx
0x180005556  sub     rsp, 20h
0x18000555a  mov     rcx, [rdx+8]; lpBaseAddress
0x18000555e  mov     rbx, rdx
0x180005561  test    rcx, rcx
0x180005564  jz      short loc_18000556C
0x180005566  call    cs:__imp_UnmapViewOfFile
0x18000556c  mov     rcx, [rbx]; hObject
0x18000556f  lea     rax, [rcx-1]
0x180005573  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005577  ja      short loc_18000557F
0x180005579  call    cs:__imp_CloseHandle
0x18000557f  mov     rcx, rbx
0x180005582  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005588  add     rsp, 20h
0x18000558c  pop     rbx
0x18000558d  retn
```
