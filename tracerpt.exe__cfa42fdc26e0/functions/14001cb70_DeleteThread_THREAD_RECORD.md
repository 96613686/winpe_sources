# DeleteThread(_THREAD_RECORD *)

- ea: `0x14001cb70`
- end: `0x14001cc7f`
- name: `?DeleteThread@@YAEPEAU_THREAD_RECORD@@@Z`
- size: `271`
- prototype: `unsigned __int8 __fastcall(struct _THREAD_RECORD ***lpMem)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140004778`
- `0x140017398`
- `0x14001c85c`

## callees

- `0x14001bd40`
- `0x14001cb70`
- `0x14001cc88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cbf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cc39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cc6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cbf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cc39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cc6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cbea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cc2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cc5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cbea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cc2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cc5d`

## pseudocode

```c
unsigned __int8 __fastcall DeleteThread(struct _THREAD_RECORD ***lpMem)
{
  struct _THREAD_RECORD **v3; // rax
  struct _THREAD_RECORD **v4; // rcx
  struct _THREAD_RECORD *v5; // rsi
  __int64 v6; // rax
  struct _THREAD_RECORD **v7; // rcx
  struct _THREAD_RECORD *v8; // rbx
  HANDLE ProcessHeap; // rax
  struct _THREAD_RECORD *v10; // rsi
  __int64 v11; // rax
  struct _THREAD_RECORD **v12; // rcx
  struct _THREAD_RECORD *v13; // rbx
  HANDLE v14; // rax
  struct _THREAD_RECORD *v15; // rbx
  struct _THREAD_RECORD *v16; // rcx
  HANDLE v17; // rax

  if ( !lpMem )
    return 0;
  v3 = *lpMem;
  if ( (*lpMem)[1] != (struct _THREAD_RECORD *)lpMem || (v4 = lpMem[1], *v4 != (struct _THREAD_RECORD *)lpMem) )
LABEL_19:
    __fastfail(3u);
  *v4 = (struct _THREAD_RECORD *)v3;
  v3[1] = (struct _THREAD_RECORD *)v4;
  DeleteTransList((struct _LIST_ENTRY *)lpMem + 2, 0);
  v5 = (struct _THREAD_RECORD *)lpMem[6];
  while ( v5 != (struct _THREAD_RECORD *)(lpMem + 6) )
  {
    v6 = *(_QWORD *)v5;
    if ( *(struct _THREAD_RECORD **)(*(_QWORD *)v5 + 8LL) != v5 )
      goto LABEL_19;
    v7 = (struct _THREAD_RECORD **)*((_QWORD *)v5 + 1);
    if ( *v7 != v5 )
      goto LABEL_19;
    *v7 = (struct _THREAD_RECORD *)v6;
    v8 = v5;
    v5 = (struct _THREAD_RECORD *)v6;
    *(_QWORD *)(v6 + 8) = v7;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  v10 = (struct _THREAD_RECORD *)lpMem[8];
  while ( v10 != (struct _THREAD_RECORD *)(lpMem + 8) )
  {
    v11 = *(_QWORD *)v10;
    if ( *(struct _THREAD_RECORD **)(*(_QWORD *)v10 + 8LL) != v10 )
      goto LABEL_19;
    v12 = (struct _THREAD_RECORD **)*((_QWORD *)v10 + 1);
    if ( *v12 != v10 )
      goto LABEL_19;
    *v12 = (struct _THREAD_RECORD *)v11;
    v13 = v10;
    v10 = (struct _THREAD_RECORD *)v11;
    *(_QWORD *)(v11 + 8) = v12;
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v13);
  }
  v15 = (struct _THREAD_RECORD *)lpMem[2];
  while ( v15 != (struct _THREAD_RECORD *)(lpMem + 2) )
  {
    v16 = v15;
    v15 = *(struct _THREAD_RECORD **)v15;
    DeleteDisk(v16);
  }
  v17 = GetProcessHeap();
  HeapFree(v17, 0, lpMem);
  return 1;
}

```

## disassembly

```asm
0x14001cb70  push    rbx
0x14001cb72  push    rsi
0x14001cb73  push    rdi
0x14001cb74  push    r14
0x14001cb76  sub     rsp, 28h
0x14001cb7a  mov     rdi, rcx
0x14001cb7d  test    rcx, rcx
0x14001cb80  jnz     short loc_14001CB8E
0x14001cb82  xor     al, al
0x14001cb84  add     rsp, 28h
0x14001cb88  pop     r14
0x14001cb8a  pop     rdi
0x14001cb8b  pop     rsi
0x14001cb8c  pop     rbx
0x14001cb8d  retn
0x14001cb8e  mov     rax, [rcx]
0x14001cb91  cmp     [rax+8], rdi
0x14001cb95  jnz     loc_14001CC78
0x14001cb9b  mov     rcx, [rcx+8]
0x14001cb9f  cmp     [rcx], rdi
0x14001cba2  jnz     loc_14001CC78
0x14001cba8  mov     [rcx], rax
0x14001cbab  xor     edx, edx; unsigned int
0x14001cbad  mov     [rax+8], rcx
0x14001cbb1  lea     rcx, [rdi+20h]; struct _LIST_ENTRY *
0x14001cbb5  call    ?DeleteTransList@@YAEPEAU_LIST_ENTRY@@K@Z; DeleteTransList(_LIST_ENTRY *,ulong)
0x14001cbba  lea     r14, [rdi+30h]
0x14001cbbe  mov     rsi, [r14]
0x14001cbc1  jmp     short loc_14001CBFE
0x14001cbc3  mov     rax, [rsi]
0x14001cbc6  cmp     [rax+8], rsi
0x14001cbca  jnz     loc_14001CC78
0x14001cbd0  mov     rcx, [rsi+8]
0x14001cbd4  cmp     [rcx], rsi
0x14001cbd7  jnz     loc_14001CC78
0x14001cbdd  mov     [rcx], rax
0x14001cbe0  mov     rbx, rsi
0x14001cbe3  mov     rsi, rax
0x14001cbe6  mov     [rax+8], rcx
0x14001cbea  call    cs:__imp_GetProcessHeap
0x14001cbf0  mov     r8, rbx; lpMem
0x14001cbf3  xor     edx, edx; dwFlags
0x14001cbf5  mov     rcx, rax; hHeap
0x14001cbf8  call    cs:__imp_HeapFree
0x14001cbfe  cmp     rsi, r14
0x14001cc01  jnz     short loc_14001CBC3
0x14001cc03  lea     r14, [rdi+40h]
0x14001cc07  mov     rsi, [r14]
0x14001cc0a  jmp     short loc_14001CC3F
0x14001cc0c  mov     rax, [rsi]
0x14001cc0f  cmp     [rax+8], rsi
0x14001cc13  jnz     short loc_14001CC78
0x14001cc15  mov     rcx, [rsi+8]
0x14001cc19  cmp     [rcx], rsi
0x14001cc1c  jnz     short loc_14001CC78
0x14001cc1e  mov     [rcx], rax
0x14001cc21  mov     rbx, rsi
0x14001cc24  mov     rsi, rax
0x14001cc27  mov     [rax+8], rcx
0x14001cc2b  call    cs:__imp_GetProcessHeap
0x14001cc31  mov     r8, rbx; lpMem
0x14001cc34  xor     edx, edx; dwFlags
0x14001cc36  mov     rcx, rax; hHeap
0x14001cc39  call    cs:__imp_HeapFree
0x14001cc3f  cmp     rsi, r14
0x14001cc42  jnz     short loc_14001CC0C
0x14001cc44  lea     rsi, [rdi+10h]
0x14001cc48  mov     rbx, [rsi]
0x14001cc4b  jmp     short loc_14001CC58
0x14001cc4d  mov     rcx, rbx; lpMem
0x14001cc50  mov     rbx, [rbx]
0x14001cc53  call    DeleteDisk
0x14001cc58  cmp     rbx, rsi
0x14001cc5b  jnz     short loc_14001CC4D
0x14001cc5d  call    cs:__imp_GetProcessHeap
0x14001cc63  mov     r8, rdi; lpMem
0x14001cc66  xor     edx, edx; dwFlags
0x14001cc68  mov     rcx, rax; hHeap
0x14001cc6b  call    cs:__imp_HeapFree
0x14001cc71  mov     al, 1
0x14001cc73  jmp     loc_14001CB84
0x14001cc78  mov     ecx, 3
0x14001cc7d  int     29h; Win8: RtlFailFast(ecx)
```
