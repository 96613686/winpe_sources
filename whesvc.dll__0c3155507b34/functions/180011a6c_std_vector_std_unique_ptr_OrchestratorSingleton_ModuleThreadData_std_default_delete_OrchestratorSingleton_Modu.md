# std::vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>,std::allocator<std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>>::~vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>,std::allocator<std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>>(void)

- ea: `0x180011a6c`
- end: `0x180011b45`
- name: `??1?$vector@V?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@V?$allocator@V?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `217`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180011c90`
- `0x180012434`
- `0x18002725c`

## callees

- `0x180003304`
- `0x180011a6c`
- `0x180011bf8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011aa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011aa2`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>::~vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>(
        __int64 a1)
{
  char *v1; // rbx
  char *v3; // r14
  __int64 v4; // rsi
  char *v5; // rcx
  ModuleHandler *v6; // rbp
  char *v7; // rcx
  unsigned __int64 v8; // rdx
  char *v9; // rax

  v1 = *(char **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(char **)(a1 + 8);
    while ( v1 != v3 )
    {
      v4 = *(_QWORD *)v1;
      if ( *(_QWORD *)v1 )
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
      v1 += 8;
    }
    v7 = *(char **)a1;
    v8 = 8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3);
    if ( v8 < 0x1000 )
    {
      v9 = *(char **)a1;
    }
    else
    {
      v9 = (char *)*((_QWORD *)v7 - 1);
      if ( (unsigned __int64)(v7 - v9 - 8) > 0x1F )
        __fastfail(5u);
      v8 += 39LL;
    }
    operator delete(v9, v8);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180011a6c  push    rbx
0x180011a6e  push    rbp
0x180011a6f  push    rsi
0x180011a70  push    rdi
0x180011a71  push    r14
0x180011a73  sub     rsp, 20h
0x180011a77  mov     rbx, [rcx]
0x180011a7a  mov     rdi, rcx
0x180011a7d  test    rbx, rbx
0x180011a80  jz      loc_180011B3A
0x180011a86  mov     r14, [rcx+8]
0x180011a8a  jmp     short loc_180011AD6
0x180011a8c  mov     rsi, [rbx]
0x180011a8f  test    rsi, rsi
0x180011a92  jz      short loc_180011AD2
0x180011a94  mov     rcx, [rsi+8]; hObject
0x180011a98  lea     rax, [rcx-1]
0x180011a9c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011aa0  ja      short loc_180011AA8
0x180011aa2  call    cs:__imp_CloseHandle
0x180011aa8  mov     rbp, [rsi]
0x180011aab  test    rbp, rbp
0x180011aae  jz      short loc_180011AC5
0x180011ab0  mov     rcx, rbp; this
0x180011ab3  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x180011ab8  mov     edx, 178h; unsigned __int64
0x180011abd  mov     rcx, rbp; void *
0x180011ac0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011ac5  mov     edx, 10h; unsigned __int64
0x180011aca  mov     rcx, rsi; void *
0x180011acd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011ad2  add     rbx, 8
0x180011ad6  cmp     rbx, r14
0x180011ad9  jnz     short loc_180011A8C
0x180011adb  mov     rcx, [rdi]
0x180011ade  mov     rax, [rdi+10h]
0x180011ae2  sub     rax, rcx
0x180011ae5  sar     rax, 3
0x180011ae9  lea     rdx, ds:0[rax*8]; unsigned __int64
0x180011af1  cmp     rdx, 1000h
0x180011af8  jb      short loc_180011B18
0x180011afa  mov     rax, [rcx-8]
0x180011afe  sub     rcx, rax
0x180011b01  sub     rcx, 8
0x180011b05  cmp     rcx, 1Fh
0x180011b09  ja      short loc_180011B11
0x180011b0b  add     rdx, 27h ; '''
0x180011b0f  jmp     short loc_180011B1B
0x180011b11  mov     ecx, 5
0x180011b16  int     29h; Win8: RtlFailFast(ecx)
0x180011b18  mov     rax, rcx
0x180011b1b  mov     rcx, rax; void *
0x180011b1e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011b23  mov     qword ptr [rdi], 0
0x180011b2a  mov     qword ptr [rdi+8], 0
0x180011b32  mov     qword ptr [rdi+10h], 0
0x180011b3a  add     rsp, 20h
0x180011b3e  pop     r14
0x180011b40  pop     rdi
0x180011b41  pop     rsi
0x180011b42  pop     rbp
0x180011b43  pop     rbx
0x180011b44  retn
```
