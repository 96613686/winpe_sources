# std::_Wrap_alloc<std::allocator<std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>>>>::destroy<std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>>>(std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>> *)

- ea: `0x180004204`
- end: `0x180004243`
- name: `??$destroy@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@@?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@@std@@@std@@QEAAXPEAV?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@1@@Z`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000f9ba`

## callees

- `0x180004204`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004237`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004237`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000422e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000422e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000421b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000421b`

## pseudocode

```c
void __fastcall std::_Wrap_alloc<std::allocator<std::unique_ptr<SharedMemory>>>::destroy<std::unique_ptr<SharedMemory>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v2; // rbx
  const void *v3; // rcx

  v2 = *a2;
  if ( *a2 )
  {
    v3 = *(const void **)(v2 + 8);
    if ( v3 )
      UnmapViewOfFile(v3);
    if ( (unsigned __int64)(*(_QWORD *)v2 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(*(HANDLE *)v2);
    operator delete((void *)v2);
  }
}

```

## disassembly

```asm
0x180004204  push    rbx
0x180004206  sub     rsp, 20h
0x18000420a  mov     rbx, [rdx]
0x18000420d  test    rbx, rbx
0x180004210  jz      short loc_18000423D
0x180004212  mov     rcx, [rbx+8]; lpBaseAddress
0x180004216  test    rcx, rcx
0x180004219  jz      short loc_180004221
0x18000421b  call    cs:__imp_UnmapViewOfFile
0x180004221  mov     rcx, [rbx]; hObject
0x180004224  lea     rax, [rcx-1]
0x180004228  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000422c  ja      short loc_180004234
0x18000422e  call    cs:__imp_CloseHandle
0x180004234  mov     rcx, rbx
0x180004237  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000423d  add     rsp, 20h
0x180004241  pop     rbx
0x180004242  retn
```
