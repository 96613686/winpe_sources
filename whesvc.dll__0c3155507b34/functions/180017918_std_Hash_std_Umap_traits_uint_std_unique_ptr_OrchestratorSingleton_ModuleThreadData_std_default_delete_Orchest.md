# std::_Hash<std::_Umap_traits<uint,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>>,0>>::erase(uint const &)

- ea: `0x180017918`
- end: `0x180017a4c`
- name: `?erase@?$_Hash@V?$_Umap_traits@IV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBI@Z`
- size: `308`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180016208`

## callees

- `0x180003304`
- `0x180011bf8`
- `0x180017918`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800179fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800179fd`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned int,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>>,0>>::erase(
        _QWORD *a1,
        _DWORD *a2)
{
  unsigned __int64 v2; // r9
  __int64 v5; // r8
  __int64 v6; // r14
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  _QWORD *v10; // r9
  _QWORD *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdi
  char *v15; // rcx
  ModuleHandler *v16; // rsi

  v2 = 0;
  v5 = 0xCBF29CE484222325uLL;
  v6 = 1;
  do
  {
    v7 = *((unsigned __int8 *)a2 + v2++);
    v5 = 0x100000001B3LL * (v7 ^ v5);
  }
  while ( v2 < 4 );
  v8 = a1[6] & v5;
  v9 = a1[3];
  v10 = (_QWORD *)a1[1];
  v11 = *(_QWORD **)(v9 + 16 * v8 + 8);
  if ( v11 == v10 )
  {
LABEL_7:
    v11 = 0;
  }
  else
  {
    while ( *a2 != *((_DWORD *)v11 + 4) )
    {
      if ( v11 == *(_QWORD **)(v9 + 16 * v8) )
        goto LABEL_7;
      v11 = (_QWORD *)v11[1];
    }
  }
  if ( !v11 )
    return 0;
  v12 = 16 * v8;
  if ( *(_QWORD **)(v9 + 16 * v8 + 8) == v11 )
  {
    if ( *(_QWORD **)(v12 + v9) == v11 )
      *(_QWORD *)(v12 + v9) = v10;
    else
      v10 = (_QWORD *)v11[1];
    *(_QWORD *)(v9 + 16 * v8 + 8) = v10;
  }
  else if ( *(_QWORD **)(v12 + v9) == v11 )
  {
    *(_QWORD *)(v12 + v9) = *v11;
  }
  v13 = *v11;
  --a1[2];
  *(_QWORD *)v11[1] = v13;
  *(_QWORD *)(v13 + 8) = v11[1];
  v14 = v11[3];
  if ( v14 )
  {
    v15 = *(char **)(v14 + 8);
    if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v15);
    v16 = *(ModuleHandler **)v14;
    if ( *(_QWORD *)v14 )
    {
      ModuleHandler::~ModuleHandler(*(ModuleHandler **)v14);
      operator delete(v16);
    }
    operator delete((void *)v14);
  }
  operator delete(v11);
  return v6;
}

```

## disassembly

```asm
0x180017918  push    rbx
0x18001791a  push    rsi
0x18001791b  push    rdi
0x18001791c  push    r14
0x18001791e  sub     rsp, 28h
0x180017922  xor     r9d, r9d
0x180017925  mov     r10, rdx
0x180017928  mov     r11, rcx
0x18001792b  mov     r8, 0CBF29CE484222325h
0x180017935  lea     r14d, [r9+1]
0x180017939  movzx   eax, byte ptr [rdx+r9]
0x18001793e  mov     rcx, 100000001B3h
0x180017948  xor     r8, rax
0x18001794b  add     r9, r14
0x18001794e  imul    r8, rcx
0x180017952  cmp     r9, 4
0x180017956  jb      short loc_180017939
0x180017958  and     r8, [r11+30h]
0x18001795c  mov     rdx, [r11+18h]
0x180017960  mov     rdi, r8
0x180017963  mov     r9, [r11+8]
0x180017967  add     rdi, rdi
0x18001796a  mov     rbx, [rdx+rdi*8+8]
0x18001796f  cmp     rbx, r9
0x180017972  jz      short loc_180017991
0x180017974  mov     rax, r8
0x180017977  add     rax, rax
0x18001797a  mov     rcx, [rdx+rax*8]
0x18001797e  mov     eax, [r10]
0x180017981  cmp     eax, [rbx+10h]
0x180017984  jz      short loc_180017993
0x180017986  cmp     rbx, rcx
0x180017989  jz      short loc_180017991
0x18001798b  mov     rbx, [rbx+8]
0x18001798f  jmp     short loc_180017981
0x180017991  xor     ebx, ebx
0x180017993  mov     ecx, 10h
0x180017998  test    rbx, rbx
0x18001799b  jz      loc_180017A3C
0x1800179a1  imul    rcx, r8
0x1800179a5  cmp     [rdx+rdi*8+8], rbx
0x1800179aa  jnz     short loc_1800179C3
0x1800179ac  cmp     [rcx+rdx], rbx
0x1800179b0  jnz     short loc_1800179B8
0x1800179b2  mov     [rcx+rdx], r9
0x1800179b6  jmp     short loc_1800179BC
0x1800179b8  mov     r9, [rbx+8]
0x1800179bc  mov     [rdx+rdi*8+8], r9
0x1800179c1  jmp     short loc_1800179D0
0x1800179c3  cmp     [rcx+rdx], rbx
0x1800179c7  jnz     short loc_1800179D0
0x1800179c9  mov     rax, [rbx]
0x1800179cc  mov     [rcx+rdx], rax
0x1800179d0  mov     rcx, [rbx]
0x1800179d3  dec     qword ptr [r11+10h]
0x1800179d7  mov     rax, [rbx+8]
0x1800179db  mov     [rax], rcx
0x1800179de  mov     rax, [rbx+8]
0x1800179e2  mov     [rcx+8], rax
0x1800179e6  mov     rdi, [rbx+18h]
0x1800179ea  test    rdi, rdi
0x1800179ed  jz      short loc_180017A2D
0x1800179ef  mov     rcx, [rdi+8]; hObject
0x1800179f3  lea     rax, [rcx-1]
0x1800179f7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800179fb  ja      short loc_180017A03
0x1800179fd  call    cs:__imp_CloseHandle
0x180017a03  mov     rsi, [rdi]
0x180017a06  test    rsi, rsi
0x180017a09  jz      short loc_180017A20
0x180017a0b  mov     rcx, rsi; this
0x180017a0e  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x180017a13  mov     edx, 178h; unsigned __int64
0x180017a18  mov     rcx, rsi; void *
0x180017a1b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017a20  mov     edx, 10h; unsigned __int64
0x180017a25  mov     rcx, rdi; void *
0x180017a28  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017a2d  mov     edx, 20h ; ' '; unsigned __int64
0x180017a32  mov     rcx, rbx; void *
0x180017a35  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017a3a  jmp     short loc_180017A3F
0x180017a3c  xor     r14d, r14d
0x180017a3f  mov     rax, r14
0x180017a42  add     rsp, 28h
0x180017a46  pop     r14
0x180017a48  pop     rdi
0x180017a49  pop     rsi
0x180017a4a  pop     rbx
0x180017a4b  retn
```
