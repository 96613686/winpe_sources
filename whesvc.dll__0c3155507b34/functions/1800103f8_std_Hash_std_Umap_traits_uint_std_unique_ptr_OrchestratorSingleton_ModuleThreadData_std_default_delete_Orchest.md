# std::_Hash<std::_Umap_traits<uint,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>>>>)

- ea: `0x1800103f8`
- end: `0x1800104ef`
- name: `??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@IV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@std@@@std@@@std@@@1@V21@@Z`
- size: `247`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180015c20`

## callees

- `0x180003304`
- `0x1800103f8`
- `0x180011bf8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800104a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800104a1`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<unsigned int,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>>>>,0>(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v6; // r9
  unsigned __int64 i; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rbp
  __int64 v13; // rdi
  char *v14; // rcx
  ModuleHandler *v15; // rsi
  _QWORD *result; // rax

  v6 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
  {
    v8 = *((unsigned __int8 *)a3 + i + 16);
    v6 = 0x100000001B3LL * (v8 ^ v6);
  }
  v9 = a1[3];
  v10 = 2 * (v6 & a1[6]);
  if ( *(_QWORD **)(v9 + 16 * (v6 & a1[6]) + 8) == a3 )
  {
    if ( *(_QWORD **)(v9 + 16 * (v6 & a1[6])) == a3 )
    {
      v11 = a1[1];
      *(_QWORD *)(v9 + 16 * (v6 & a1[6])) = v11;
    }
    else
    {
      v11 = a3[1];
    }
    *(_QWORD *)(v9 + 8 * v10 + 8) = v11;
  }
  else if ( *(_QWORD **)(v9 + 16 * (v6 & a1[6])) == a3 )
  {
    *(_QWORD *)(v9 + 16 * (v6 & a1[6])) = *a3;
  }
  v12 = *a3;
  --a1[2];
  *(_QWORD *)a3[1] = v12;
  *(_QWORD *)(v12 + 8) = a3[1];
  v13 = a3[3];
  if ( v13 )
  {
    v14 = *(char **)(v13 + 8);
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v14);
    v15 = *(ModuleHandler **)v13;
    if ( *(_QWORD *)v13 )
    {
      ModuleHandler::~ModuleHandler(*(ModuleHandler **)v13);
      operator delete(v15, 0x178u);
    }
    operator delete((void *)v13, 0x10u);
  }
  operator delete(a3, 0x20u);
  result = a2;
  *a2 = v12;
  return result;
}

```

## disassembly

```asm
0x1800103f8  push    rbx
0x1800103fa  push    rbp
0x1800103fb  push    rsi
0x1800103fc  push    rdi
0x1800103fd  push    r14
0x1800103ff  sub     rsp, 20h
0x180010403  mov     rbx, r8
0x180010406  mov     r14, rdx
0x180010409  mov     r8, rcx
0x18001040c  mov     r9, 0CBF29CE484222325h
0x180010416  xor     ecx, ecx
0x180010418  movzx   eax, byte ptr [rbx+rcx+10h]
0x18001041d  mov     rdx, 100000001B3h
0x180010427  xor     r9, rax
0x18001042a  inc     rcx
0x18001042d  imul    r9, rdx
0x180010431  cmp     rcx, 4
0x180010435  jb      short loc_180010418
0x180010437  mov     rcx, [r8+30h]
0x18001043b  mov     rdx, [r8+18h]
0x18001043f  and     rcx, r9
0x180010442  add     rcx, rcx
0x180010445  cmp     [rdx+rcx*8+8], rbx
0x18001044a  jnz     short loc_180010467
0x18001044c  cmp     [rdx+rcx*8], rbx
0x180010450  jnz     short loc_18001045C
0x180010452  mov     rax, [r8+8]
0x180010456  mov     [rdx+rcx*8], rax
0x18001045a  jmp     short loc_180010460
0x18001045c  mov     rax, [rbx+8]
0x180010460  mov     [rdx+rcx*8+8], rax
0x180010465  jmp     short loc_180010474
0x180010467  cmp     [rdx+rcx*8], rbx
0x18001046b  jnz     short loc_180010474
0x18001046d  mov     rax, [rbx]
0x180010470  mov     [rdx+rcx*8], rax
0x180010474  mov     rbp, [rbx]
0x180010477  dec     qword ptr [r8+10h]
0x18001047b  mov     rax, [rbx+8]
0x18001047f  mov     [rax], rbp
0x180010482  mov     rax, [rbx+8]
0x180010486  mov     [rbp+8], rax
0x18001048a  mov     rdi, [rbx+18h]
0x18001048e  test    rdi, rdi
0x180010491  jz      short loc_1800104D1
0x180010493  mov     rcx, [rdi+8]; hObject
0x180010497  lea     rax, [rcx-1]
0x18001049b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001049f  ja      short loc_1800104A7
0x1800104a1  call    cs:__imp_CloseHandle
0x1800104a7  mov     rsi, [rdi]
0x1800104aa  test    rsi, rsi
0x1800104ad  jz      short loc_1800104C4
0x1800104af  mov     rcx, rsi; this
0x1800104b2  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x1800104b7  mov     edx, 178h; unsigned __int64
0x1800104bc  mov     rcx, rsi; void *
0x1800104bf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800104c4  mov     edx, 10h; unsigned __int64
0x1800104c9  mov     rcx, rdi; void *
0x1800104cc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800104d1  mov     edx, 20h ; ' '; unsigned __int64
0x1800104d6  mov     rcx, rbx; void *
0x1800104d9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800104de  mov     rax, r14
0x1800104e1  mov     [r14], rbp
0x1800104e4  add     rsp, 20h
0x1800104e8  pop     r14
0x1800104ea  pop     rdi
0x1800104eb  pop     rsi
0x1800104ec  pop     rbp
0x1800104ed  pop     rbx
0x1800104ee  retn
```
