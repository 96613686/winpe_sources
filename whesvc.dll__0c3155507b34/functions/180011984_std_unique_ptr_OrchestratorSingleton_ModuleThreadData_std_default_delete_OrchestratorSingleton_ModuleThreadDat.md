# std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>::~unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>(void)

- ea: `0x180011984`
- end: `0x1800119df`
- name: `??1?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800274d3`
- `0x18002754c`

## callees

- `0x180003304`
- `0x180011984`
- `0x180011bf8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800119a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800119a4`

## pseudocode

```c
void __fastcall std::unique_ptr<OrchestratorSingleton::ModuleThreadData>::~unique_ptr<OrchestratorSingleton::ModuleThreadData>(
        __int64 *a1)
{
  __int64 v1; // rbx
  char *v2; // rcx
  ModuleHandler *v3; // rdi

  v1 = *a1;
  if ( *a1 )
  {
    v2 = *(char **)(v1 + 8);
    if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v2);
    v3 = *(ModuleHandler **)v1;
    if ( *(_QWORD *)v1 )
    {
      ModuleHandler::~ModuleHandler(*(ModuleHandler **)v1);
      operator delete(v3, 0x178u);
    }
    operator delete((void *)v1, 0x10u);
  }
}

```

## disassembly

```asm
0x180011984  mov     [rsp+arg_0], rbx
0x180011989  push    rdi
0x18001198a  sub     rsp, 20h
0x18001198e  mov     rbx, [rcx]
0x180011991  test    rbx, rbx
0x180011994  jz      short loc_1800119D4
0x180011996  mov     rcx, [rbx+8]; hObject
0x18001199a  lea     rax, [rcx-1]
0x18001199e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800119a2  ja      short loc_1800119AA
0x1800119a4  call    cs:__imp_CloseHandle
0x1800119aa  mov     rdi, [rbx]
0x1800119ad  test    rdi, rdi
0x1800119b0  jz      short loc_1800119C7
0x1800119b2  mov     rcx, rdi; this
0x1800119b5  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x1800119ba  mov     edx, 178h; unsigned __int64
0x1800119bf  mov     rcx, rdi; void *
0x1800119c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800119c7  mov     edx, 10h; unsigned __int64
0x1800119cc  mov     rcx, rbx; void *
0x1800119cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800119d4  mov     rbx, [rsp+28h+arg_0]
0x1800119d9  add     rsp, 20h
0x1800119dd  pop     rdi
0x1800119de  retn
```
