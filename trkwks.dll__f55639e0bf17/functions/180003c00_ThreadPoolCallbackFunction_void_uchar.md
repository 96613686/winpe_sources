# ThreadPoolCallbackFunction(void *,uchar)

- ea: `0x180003c00`
- end: `0x180003c7a`
- name: `?ThreadPoolCallbackFunction@@YAXPEAXE@Z`
- size: `122`
- prototype: `void __fastcall(void (__fastcall ***)(_QWORD))`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003c00`
- `0x180003c80`
- `0x1800047b0`
- `0x180012010`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x180003c69`
- `ntdll!RtlSetThreadErrorMode` at `0x180003c69`

## pseudocode

```c
void __fastcall ThreadPoolCallbackFunction(void (__fastcall ***a1)(_QWORD))
{
  ULONG v2; // ebx
  CActiveThreadList *v3; // rcx

  _InterlockedIncrement((volatile signed __int32 *)&g_cThreadPoolThreads);
  if ( g_cThreadPoolThreads > g_cThreadPoolMaxThreads )
    g_cThreadPoolMaxThreads = g_cThreadPoolThreads;
  v2 = InitializeThreadFromPool();
  (**a1)(a1);
  _InterlockedDecrement((volatile signed __int32 *)&g_cThreadPoolThreads);
  if ( g_pActiveThreadList )
    CActiveThreadList::RemoveCurrent(v3);
  RtlSetThreadErrorMode(v2, 0);
}

```

## disassembly

```asm
0x180003c00  mov     [rsp+arg_0], rbx
0x180003c05  push    rdi
0x180003c06  sub     rsp, 30h
0x180003c0a  mov     rdi, rcx
0x180003c0d  mov     [rsp+38h+var_18], 0
0x180003c15  lock inc cs:?g_cThreadPoolThreads@@3KA; ulong g_cThreadPoolThreads
0x180003c1c  mov     eax, cs:?g_cThreadPoolThreads@@3KA; ulong g_cThreadPoolThreads
0x180003c22  cmp     eax, cs:?g_cThreadPoolMaxThreads@@3KA; ulong g_cThreadPoolMaxThreads
0x180003c28  jbe     short loc_180003C30
0x180003c2a  mov     cs:?g_cThreadPoolMaxThreads@@3KA, eax; ulong g_cThreadPoolMaxThreads
0x180003c30  call    ?InitializeThreadFromPool@@YA?AUSThreadFromPoolState@@XZ; InitializeThreadFromPool(void)
0x180003c35  mov     ebx, eax
0x180003c37  mov     [rsp+38h+var_18], eax
0x180003c3b  mov     rax, [rdi]
0x180003c3e  mov     rcx, rdi
0x180003c41  mov     rax, [rax]
0x180003c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c49  jmp     short loc_180003C4F
0x180003c4b  mov     ebx, [rsp+38h+var_18]
0x180003c4f  lock dec cs:?g_cThreadPoolThreads@@3KA; ulong g_cThreadPoolThreads
0x180003c56  cmp     cs:g_pActiveThreadList, 0
0x180003c5e  jz      short loc_180003C65
0x180003c60  call    ?RemoveCurrent@CActiveThreadList@@QEAAJXZ; CActiveThreadList::RemoveCurrent(void)
0x180003c65  xor     edx, edx; OldMode
0x180003c67  mov     ecx, ebx; NewMode
0x180003c69  call    cs:__imp_RtlSetThreadErrorMode
0x180003c6f  mov     rbx, [rsp+38h+arg_0]
0x180003c74  add     rsp, 30h
0x180003c78  pop     rdi
0x180003c79  retn
0x1800112f0  push    rbp
0x1800112f2  sub     rsp, 20h
0x1800112f6  mov     rbp, rdx
0x1800112f9  mov     eax, 1
0x1800112fe  add     rsp, 20h
0x180011302  pop     rbp
0x180011303  retn
```
