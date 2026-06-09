# std::vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>,std::allocator<std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>>::_Change_array(std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>> * const,unsigned __int64,unsigned __int64)

- ea: `0x180016c54`
- end: `0x180016d3e`
- name: `?_Change_array@?$vector@V?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@V?$allocator@V?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@2@@std@@AEAAXQEAV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@2@_K1@Z`
- size: `234`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18000fa50`
- `0x180017a54`

## callees

- `0x180003304`
- `0x180011bf8`
- `0x180016c54`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016c99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016c99`

## pseudocode

```c
__int64 __fastcall std::vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>::_Change_array(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char *v4; // rdi
  char *v9; // r15
  __int64 v10; // rsi
  char *v11; // rcx
  ModuleHandler *v12; // rbp
  char *v13; // rcx
  char *v14; // rax
  __int64 result; // rax

  v4 = *(char **)a1;
  if ( *(_QWORD *)a1 )
  {
    v9 = *(char **)(a1 + 8);
    while ( v4 != v9 )
    {
      v10 = *(_QWORD *)v4;
      if ( *(_QWORD *)v4 )
      {
        v11 = *(char **)(v10 + 8);
        if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v11);
        v12 = *(ModuleHandler **)v10;
        if ( *(_QWORD *)v10 )
        {
          ModuleHandler::~ModuleHandler(*(ModuleHandler **)v10);
          operator delete(v12);
        }
        operator delete((void *)v10);
      }
      v4 += 8;
    }
    v13 = *(char **)a1;
    if ( (unsigned __int64)(8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3)) < 0x1000 )
    {
      v14 = *(char **)a1;
    }
    else
    {
      v14 = (char *)*((_QWORD *)v13 - 1);
      if ( (unsigned __int64)(v13 - v14 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v14);
  }
  *(_QWORD *)a1 = a2;
  *(_QWORD *)(a1 + 8) = a2 + 8 * a3;
  result = a2 + 8 * a4;
  *(_QWORD *)(a1 + 16) = result;
  return result;
}

```

## disassembly

```asm
0x180016c54  push    rbx
0x180016c56  push    rbp
0x180016c57  push    rsi
0x180016c58  push    rdi
0x180016c59  push    r12
0x180016c5b  push    r13
0x180016c5d  push    r14
0x180016c5f  push    r15
0x180016c61  sub     rsp, 28h
0x180016c65  mov     rdi, [rcx]
0x180016c68  mov     r12, r9
0x180016c6b  mov     r13, r8
0x180016c6e  mov     r14, rdx
0x180016c71  mov     rbx, rcx
0x180016c74  test    rdi, rdi
0x180016c77  jz      loc_180016D1A
0x180016c7d  mov     r15, [rcx+8]
0x180016c81  jmp     short loc_180016CCD
0x180016c83  mov     rsi, [rdi]
0x180016c86  test    rsi, rsi
0x180016c89  jz      short loc_180016CC9
0x180016c8b  mov     rcx, [rsi+8]; hObject
0x180016c8f  lea     rax, [rcx-1]
0x180016c93  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016c97  ja      short loc_180016C9F
0x180016c99  call    cs:__imp_CloseHandle
0x180016c9f  mov     rbp, [rsi]
0x180016ca2  test    rbp, rbp
0x180016ca5  jz      short loc_180016CBC
0x180016ca7  mov     rcx, rbp; this
0x180016caa  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x180016caf  mov     edx, 178h; unsigned __int64
0x180016cb4  mov     rcx, rbp; void *
0x180016cb7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016cbc  mov     edx, 10h; unsigned __int64
0x180016cc1  mov     rcx, rsi; void *
0x180016cc4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016cc9  add     rdi, 8
0x180016ccd  cmp     rdi, r15
0x180016cd0  jnz     short loc_180016C83
0x180016cd2  mov     rcx, [rbx]
0x180016cd5  mov     rax, [rbx+10h]
0x180016cd9  sub     rax, rcx
0x180016cdc  sar     rax, 3
0x180016ce0  lea     rdx, ds:0[rax*8]; unsigned __int64
0x180016ce8  cmp     rdx, 1000h
0x180016cef  jb      short loc_180016D0F
0x180016cf1  mov     rax, [rcx-8]
0x180016cf5  sub     rcx, rax
0x180016cf8  sub     rcx, 8
0x180016cfc  cmp     rcx, 1Fh
0x180016d00  ja      short loc_180016D08
0x180016d02  add     rdx, 27h ; '''
0x180016d06  jmp     short loc_180016D12
0x180016d08  mov     ecx, 5
0x180016d0d  int     29h; Win8: RtlFailFast(ecx)
0x180016d0f  mov     rax, rcx
0x180016d12  mov     rcx, rax; void *
0x180016d15  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016d1a  lea     rax, [r14+r13*8]
0x180016d1e  mov     [rbx], r14
0x180016d21  mov     [rbx+8], rax
0x180016d25  lea     rax, [r14+r12*8]
0x180016d29  mov     [rbx+10h], rax
0x180016d2d  add     rsp, 28h
0x180016d31  pop     r15
0x180016d33  pop     r14
0x180016d35  pop     r13
0x180016d37  pop     r12
0x180016d39  pop     rdi
0x180016d3a  pop     rsi
0x180016d3b  pop     rbp
0x180016d3c  pop     rbx
0x180016d3d  retn
```
