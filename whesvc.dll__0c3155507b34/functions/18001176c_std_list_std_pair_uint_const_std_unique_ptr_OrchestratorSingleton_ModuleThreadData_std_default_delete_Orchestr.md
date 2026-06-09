# std::list<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>,std::allocator<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>>>::~list<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>,std::allocator<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>>>(void)

- ea: `0x18001176c`
- end: `0x180011806`
- name: `??1?$list@U?$pair@$$CBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@std@@V?$allocator@U?$pair@$$CBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `154`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180011a44`
- `0x180011c90`
- `0x1800272a7`

## callees

- `0x180003304`
- `0x18001176c`
- `0x180011bf8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800117aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800117aa`

## pseudocode

```c
void __fastcall std::list<std::pair<unsigned int const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>>::~list<std::pair<unsigned int const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>>(
        void **a1)
{
  _QWORD **v1; // rdx
  _QWORD *v3; // rbx
  __int64 v4; // rdi
  _QWORD *v5; // rbp
  char *v6; // rcx
  ModuleHandler *v7; // rsi

  v1 = (_QWORD **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = *v1;
  if ( *v1 )
  {
    do
    {
      v4 = v3[3];
      v5 = (_QWORD *)*v3;
      if ( v4 )
      {
        v6 = *(char **)(v4 + 8);
        if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v6);
        v7 = *(ModuleHandler **)v4;
        if ( *(_QWORD *)v4 )
        {
          ModuleHandler::~ModuleHandler(*(ModuleHandler **)v4);
          operator delete(v7, 0x178u);
        }
        operator delete((void *)v4, 0x10u);
      }
      operator delete(v3, 0x20u);
      v3 = v5;
    }
    while ( v5 );
  }
  operator delete(*a1, 0x20u);
}

```

## disassembly

```asm
0x18001176c  push    rbx
0x18001176e  push    rbp
0x18001176f  push    rsi
0x180011770  push    rdi
0x180011771  push    r14
0x180011773  sub     rsp, 20h
0x180011777  mov     rdx, [rcx]
0x18001177a  mov     r14, rcx
0x18001177d  mov     rax, [rdx+8]
0x180011781  mov     qword ptr [rax], 0
0x180011788  mov     rbx, [rdx]
0x18001178b  test    rbx, rbx
0x18001178e  jz      short loc_1800117EF
0x180011790  mov     rdi, [rbx+18h]
0x180011794  mov     rbp, [rbx]
0x180011797  test    rdi, rdi
0x18001179a  jz      short loc_1800117DA
0x18001179c  mov     rcx, [rdi+8]; hObject
0x1800117a0  lea     rax, [rcx-1]
0x1800117a4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800117a8  ja      short loc_1800117B0
0x1800117aa  call    cs:__imp_CloseHandle
0x1800117b0  mov     rsi, [rdi]
0x1800117b3  test    rsi, rsi
0x1800117b6  jz      short loc_1800117CD
0x1800117b8  mov     rcx, rsi; this
0x1800117bb  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x1800117c0  mov     edx, 178h; unsigned __int64
0x1800117c5  mov     rcx, rsi; void *
0x1800117c8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800117cd  mov     edx, 10h; unsigned __int64
0x1800117d2  mov     rcx, rdi; void *
0x1800117d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800117da  mov     edx, 20h ; ' '; unsigned __int64
0x1800117df  mov     rcx, rbx; void *
0x1800117e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800117e7  mov     rbx, rbp
0x1800117ea  test    rbp, rbp
0x1800117ed  jnz     short loc_180011790
0x1800117ef  mov     rcx, [r14]; void *
0x1800117f2  mov     edx, 20h ; ' '; unsigned __int64
0x1800117f7  add     rsp, 20h
0x1800117fb  pop     r14
0x1800117fd  pop     rdi
0x1800117fe  pop     rsi
0x1800117ff  pop     rbp
0x180011800  pop     rbx
0x180011801  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
