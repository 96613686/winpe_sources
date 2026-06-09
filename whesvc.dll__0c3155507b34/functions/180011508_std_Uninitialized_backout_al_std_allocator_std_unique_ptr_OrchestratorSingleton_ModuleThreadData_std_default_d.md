# std::_Uninitialized_backout_al<std::allocator<std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>>::~_Uninitialized_backout_al<std::allocator<std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>>(void)

- ea: `0x180011508`
- end: `0x180011572`
- name: `??1?$_Uninitialized_backout_al@V?$allocator@V?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@std@@@std@@QEAA@XZ`
- size: `106`
- prototype: `void __fastcall(__int64 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18000fa50`
- `0x180017a54`

## callees

- `0x180003304`
- `0x180011508`
- `0x180011bf8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011530`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011530`

## pseudocode

```c
void __fastcall std::_Uninitialized_backout_al<std::allocator<std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>>::~_Uninitialized_backout_al<std::allocator<std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>>(
        __int64 **a1)
{
  __int64 *v1; // rbp
  __int64 *i; // rbx
  __int64 v3; // rdi
  char *v4; // rcx
  ModuleHandler *v5; // rsi

  v1 = a1[1];
  for ( i = *a1; i != v1; ++i )
  {
    v3 = *i;
    if ( *i )
    {
      v4 = *(char **)(v3 + 8);
      if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v4);
      v5 = *(ModuleHandler **)v3;
      if ( *(_QWORD *)v3 )
      {
        ModuleHandler::~ModuleHandler(*(ModuleHandler **)v3);
        operator delete(v5, 0x178u);
      }
      operator delete((void *)v3, 0x10u);
    }
  }
}

```

## disassembly

```asm
0x180011508  push    rbx
0x18001150a  push    rbp
0x18001150b  push    rsi
0x18001150c  push    rdi
0x18001150d  sub     rsp, 28h
0x180011511  mov     rbp, [rcx+8]
0x180011515  mov     rbx, [rcx]
0x180011518  jmp     short loc_180011564
0x18001151a  mov     rdi, [rbx]
0x18001151d  test    rdi, rdi
0x180011520  jz      short loc_180011560
0x180011522  mov     rcx, [rdi+8]; hObject
0x180011526  lea     rax, [rcx-1]
0x18001152a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001152e  ja      short loc_180011536
0x180011530  call    cs:__imp_CloseHandle
0x180011536  mov     rsi, [rdi]
0x180011539  test    rsi, rsi
0x18001153c  jz      short loc_180011553
0x18001153e  mov     rcx, rsi; this
0x180011541  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x180011546  mov     edx, 178h; unsigned __int64
0x18001154b  mov     rcx, rsi; void *
0x18001154e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011553  mov     edx, 10h; unsigned __int64
0x180011558  mov     rcx, rdi; void *
0x18001155b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011560  add     rbx, 8
0x180011564  cmp     rbx, rbp
0x180011567  jnz     short loc_18001151A
0x180011569  add     rsp, 28h
0x18001156d  pop     rdi
0x18001156e  pop     rsi
0x18001156f  pop     rbp
0x180011570  pop     rbx
0x180011571  retn
```
