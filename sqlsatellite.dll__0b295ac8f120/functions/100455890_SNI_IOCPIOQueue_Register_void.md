# SNI_IOCPIOQueue::Register(void *)

- ea: `0x100455890`
- end: `0x10045598e`
- name: `?Register@SNI_IOCPIOQueue@@UEAAKPEAX@Z`
- size: `254`
- prototype: `unsigned int(SNI_IOCPIOQueue *__hidden this, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x100455890`

## import_xrefs

- `KERNEL32!CreateIoCompletionPort` at `0x100455951`
- `KERNEL32!CreateIoCompletionPort` at `0x100455951`
- `KERNEL32!GetLastError` at `0x10045595c`
- `KERNEL32!GetLastError` at `0x10045595c`
- `sqldk!SystemThread_TlsIndex` at `0x1004558ab`
- `sqldk!SystemThread_TlsIndex` at `0x1004558fe`
- `sqldk!SystemThread_TlsOffset` at `0x1004558b8`
- `sqldk!SystemThread_TlsOffset` at `0x100455907`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004558d3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100455922`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004558d3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100455922`

## pseudocode

```c
DWORD __fastcall SNI_IOCPIOQueue::Register(SNI_IOCPIOQueue *this, void *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  void *v6; // rbx
  __int64 v7; // rdi
  __int64 v8; // rax
  DWORD result; // eax

  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  v6 = *(void **)(*(_QWORD *)(*(_QWORD *)(v5 + 992) + 936LL) + 8LL * *((unsigned int *)this + 2));
  v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v8 = *(_QWORD *)(v7 + 256);
  if ( !v8 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v8 = *(_QWORD *)(v7 + 256);
  }
  if ( !v6 )
    v6 = **(void ***)(*(_QWORD *)(v8 + 992) + 936LL);
  if ( CreateIoCompletionPort(a2, v6, 0, 0) )
    return 0;
  result = GetLastError();
  if ( !result )
    return -1;
  return result;
}

```

## disassembly

```asm
0x100455890  mov     [rsp+arg_0], rbx
0x100455895  mov     [rsp+arg_8], rsi
0x10045589a  push    rdi
0x10045589b  sub     rsp, 20h
0x10045589f  mov     r9, gs:58h
0x1004558a8  mov     rsi, rdx
0x1004558ab  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004558b2  mov     rdi, rcx
0x1004558b5  mov     r8d, [rax]
0x1004558b8  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004558bf  mov     ebx, [rax]
0x1004558c1  add     rbx, [r9+r8*8]
0x1004558c5  mov     rax, [rbx+100h]
0x1004558cc  test    rax, rax
0x1004558cf  jnz     short loc_1004558E0
0x1004558d1  xor     ecx, ecx
0x1004558d3  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004558d9  mov     rax, [rbx+100h]
0x1004558e0  mov     rax, [rax+3E0h]
0x1004558e7  mov     edx, [rdi+8]
0x1004558ea  mov     rcx, [rax+3A8h]
0x1004558f1  mov     rbx, [rcx+rdx*8]
0x1004558f5  mov     rdx, gs:58h
0x1004558fe  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100455905  mov     ecx, [rax]
0x100455907  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045590e  mov     edi, [rax]
0x100455910  add     rdi, [rdx+rcx*8]
0x100455914  mov     rax, [rdi+100h]
0x10045591b  test    rax, rax
0x10045591e  jnz     short loc_10045592F
0x100455920  xor     ecx, ecx
0x100455922  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100455928  mov     rax, [rdi+100h]
0x10045592f  test    rbx, rbx
0x100455932  jnz     short loc_100455945
0x100455934  mov     rax, [rax+3E0h]
0x10045593b  mov     rcx, [rax+3A8h]
0x100455942  mov     rbx, [rcx]
0x100455945  xor     r9d, r9d; NumberOfConcurrentThreads
0x100455948  xor     r8d, r8d; CompletionKey
0x10045594b  mov     rdx, rbx; ExistingCompletionPort
0x10045594e  mov     rcx, rsi; FileHandle
0x100455951  call    cs:__imp_CreateIoCompletionPort
0x100455957  test    rax, rax
0x10045595a  jnz     short loc_10045597C
0x10045595c  call    cs:__imp_GetLastError
0x100455962  test    eax, eax
0x100455964  mov     ecx, 0FFFFFFFFh
0x100455969  cmovz   eax, ecx
0x10045596c  mov     rbx, [rsp+28h+arg_0]
0x100455971  mov     rsi, [rsp+28h+arg_8]
0x100455976  add     rsp, 20h
0x10045597a  pop     rdi
0x10045597b  retn
0x10045597c  mov     rbx, [rsp+28h+arg_0]
0x100455981  xor     eax, eax
0x100455983  mov     rsi, [rsp+28h+arg_8]
0x100455988  add     rsp, 20h
0x10045598c  pop     rdi
0x10045598d  retn
```
