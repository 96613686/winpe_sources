# std::vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>,std::allocator<std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x180011df8`
- end: `0x180011eb7`
- name: `??1_Reallocation_guard@?$vector@V?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@V?$allocator@V?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `191`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18000fa50`

## callees

- `0x180003304`
- `0x180011bf8`
- `0x180011df8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e31`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  __int64 *v2; // r14
  __int64 *i; // rdi
  __int64 v4; // rsi
  char *v5; // rcx
  ModuleHandler *v6; // rbp
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  void *v9; // rax

  if ( a1[1] )
  {
    v2 = (__int64 *)a1[4];
    for ( i = (__int64 *)a1[3]; i != v2; ++i )
    {
      v4 = *i;
      if ( *i )
      {
        v5 = *(char **)(v4 + 8);
        if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v5);
        v6 = *(ModuleHandler **)v4;
        if ( *(_QWORD *)v4 )
        {
          ModuleHandler::~ModuleHandler(*(ModuleHandler **)v4);
          operator delete(v6, 0x178u);
        }
        operator delete((void *)v4, 0x10u);
      }
    }
    v7 = a1[1];
    v8 = 8LL * a1[2];
    if ( v8 < 0x1000 )
    {
      v9 = (void *)a1[1];
    }
    else
    {
      v9 = *(void **)(v7 - 8);
      if ( (unsigned __int64)(v7 - (_QWORD)v9 - 8) > 0x1F )
        __fastfail(5u);
      v8 += 39LL;
    }
    operator delete(v9, v8);
  }
}

```

## disassembly

```asm
0x180011df8  push    rbx
0x180011dfa  push    rbp
0x180011dfb  push    rsi
0x180011dfc  push    rdi
0x180011dfd  push    r14
0x180011dff  sub     rsp, 20h
0x180011e03  cmp     qword ptr [rcx+8], 0
0x180011e08  mov     rbx, rcx
0x180011e0b  jz      loc_180011EAC
0x180011e11  mov     r14, [rcx+20h]
0x180011e15  mov     rdi, [rcx+18h]
0x180011e19  jmp     short loc_180011E65
0x180011e1b  mov     rsi, [rdi]
0x180011e1e  test    rsi, rsi
0x180011e21  jz      short loc_180011E61
0x180011e23  mov     rcx, [rsi+8]; hObject
0x180011e27  lea     rax, [rcx-1]
0x180011e2b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011e2f  ja      short loc_180011E37
0x180011e31  call    cs:__imp_CloseHandle
0x180011e37  mov     rbp, [rsi]
0x180011e3a  test    rbp, rbp
0x180011e3d  jz      short loc_180011E54
0x180011e3f  mov     rcx, rbp; this
0x180011e42  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x180011e47  mov     edx, 178h; unsigned __int64
0x180011e4c  mov     rcx, rbp; void *
0x180011e4f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011e54  mov     edx, 10h; unsigned __int64
0x180011e59  mov     rcx, rsi; void *
0x180011e5c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011e61  add     rdi, 8
0x180011e65  cmp     rdi, r14
0x180011e68  jnz     short loc_180011E1B
0x180011e6a  mov     rax, [rbx+10h]
0x180011e6e  mov     rcx, [rbx+8]
0x180011e72  lea     rdx, ds:0[rax*8]; unsigned __int64
0x180011e7a  cmp     rdx, 1000h
0x180011e81  jb      short loc_180011EA1
0x180011e83  mov     rax, [rcx-8]
0x180011e87  sub     rcx, rax
0x180011e8a  sub     rcx, 8
0x180011e8e  cmp     rcx, 1Fh
0x180011e92  ja      short loc_180011E9A
0x180011e94  add     rdx, 27h ; '''
0x180011e98  jmp     short loc_180011EA4
0x180011e9a  mov     ecx, 5
0x180011e9f  int     29h; Win8: RtlFailFast(ecx)
0x180011ea1  mov     rax, rcx
0x180011ea4  mov     rcx, rax; void *
0x180011ea7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011eac  add     rsp, 20h
0x180011eb0  pop     r14
0x180011eb2  pop     rdi
0x180011eb3  pop     rsi
0x180011eb4  pop     rbp
0x180011eb5  pop     rbx
0x180011eb6  retn
```
