# std::vector<std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>>,std::allocator<std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>>>>::~vector<std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>>,std::allocator<std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>>>>(void)

- ea: `0x180004a88`
- end: `0x180004b07`
- name: `??1?$vector@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@V?$allocator@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004cf8`
- `0x18000fa18`

## callees

- `0x180004a88`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004acf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004ae1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004acf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004ae1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ac6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ac6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180004ab3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180004ab3`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<SharedMemory>>::~vector<std::unique_ptr<SharedMemory>>(__int64 a1)
{
  __int64 *v1; // rdi
  __int64 *v3; // rbp
  __int64 v4; // rsi
  const void *v5; // rcx

  v1 = *(__int64 **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(__int64 **)(a1 + 8);
    while ( v1 != v3 )
    {
      v4 = *v1;
      if ( *v1 )
      {
        v5 = *(const void **)(v4 + 8);
        if ( v5 )
          UnmapViewOfFile(v5);
        if ( (unsigned __int64)(*(_QWORD *)v4 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(*(HANDLE *)v4);
        operator delete((void *)v4);
      }
      ++v1;
    }
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180004a88  push    rbx
0x180004a8a  push    rbp
0x180004a8b  push    rsi
0x180004a8c  push    rdi
0x180004a8d  sub     rsp, 28h
0x180004a91  mov     rdi, [rcx]
0x180004a94  mov     rbx, rcx
0x180004a97  test    rdi, rdi
0x180004a9a  jz      short loc_180004AFE
0x180004a9c  mov     rbp, [rcx+8]
0x180004aa0  jmp     short loc_180004AD9
0x180004aa2  mov     rsi, [rdi]
0x180004aa5  test    rsi, rsi
0x180004aa8  jz      short loc_180004AD5
0x180004aaa  mov     rcx, [rsi+8]; lpBaseAddress
0x180004aae  test    rcx, rcx
0x180004ab1  jz      short loc_180004AB9
0x180004ab3  call    cs:__imp_UnmapViewOfFile
0x180004ab9  mov     rcx, [rsi]; hObject
0x180004abc  lea     rax, [rcx-1]
0x180004ac0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180004ac4  ja      short loc_180004ACC
0x180004ac6  call    cs:__imp_CloseHandle
0x180004acc  mov     rcx, rsi
0x180004acf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004ad5  add     rdi, 8
0x180004ad9  cmp     rdi, rbp
0x180004adc  jnz     short loc_180004AA2
0x180004ade  mov     rcx, [rbx]
0x180004ae1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004ae7  mov     qword ptr [rbx], 0
0x180004aee  mov     qword ptr [rbx+8], 0
0x180004af6  mov     qword ptr [rbx+10h], 0
0x180004afe  add     rsp, 28h
0x180004b02  pop     rdi
0x180004b03  pop     rsi
0x180004b04  pop     rbp
0x180004b05  pop     rbx
0x180004b06  retn
```
