# std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>,void *>>>(void)

- ea: `0x18001147c`
- end: `0x180011501`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800101f4`
- `0x18002718c`

## callees

- `0x180003304`
- `0x18001147c`
- `0x180011bf8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800114ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800114ae`

## pseudocode

```c
void __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned int const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned int const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rbx
  char *v4; // rcx
  ModuleHandler *v5; // rdi
  void *v6; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = *(_QWORD *)(v1 + 24);
    if ( v3 )
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
  v6 = *(void **)(a1 + 8);
  if ( v6 )
    operator delete(v6, 0x20u);
}

```

## disassembly

```asm
0x18001147c  mov     [rsp+arg_0], rbx
0x180011481  mov     [rsp+arg_8], rsi
0x180011486  push    rdi
0x180011487  sub     rsp, 20h
0x18001148b  mov     rbx, [rcx+8]
0x18001148f  mov     rsi, rcx
0x180011492  test    rbx, rbx
0x180011495  jz      short loc_1800114DE
0x180011497  mov     rbx, [rbx+18h]
0x18001149b  test    rbx, rbx
0x18001149e  jz      short loc_1800114DE
0x1800114a0  mov     rcx, [rbx+8]; hObject
0x1800114a4  lea     rax, [rcx-1]
0x1800114a8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800114ac  ja      short loc_1800114B4
0x1800114ae  call    cs:__imp_CloseHandle
0x1800114b4  mov     rdi, [rbx]
0x1800114b7  test    rdi, rdi
0x1800114ba  jz      short loc_1800114D1
0x1800114bc  mov     rcx, rdi; this
0x1800114bf  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x1800114c4  mov     edx, 178h; unsigned __int64
0x1800114c9  mov     rcx, rdi; void *
0x1800114cc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800114d1  mov     edx, 10h; unsigned __int64
0x1800114d6  mov     rcx, rbx; void *
0x1800114d9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800114de  mov     rcx, [rsi+8]; void *
0x1800114e2  test    rcx, rcx
0x1800114e5  jz      short loc_1800114F1
0x1800114e7  mov     edx, 20h ; ' '; unsigned __int64
0x1800114ec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800114f1  mov     rbx, [rsp+28h+arg_0]
0x1800114f6  mov     rsi, [rsp+28h+arg_8]
0x1800114fb  add     rsp, 20h
0x1800114ff  pop     rdi
0x180011500  retn
```
