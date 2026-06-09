# CreateGroupbyColumnDataFromTable(_TRACERPT_EVENT_TABLE *,_TABLE_DATA *)

- ea: `0x140029794`
- end: `0x1400298c4`
- name: `?CreateGroupbyColumnDataFromTable@@YAEPEAU_TRACERPT_EVENT_TABLE@@PEAU_TABLE_DATA@@@Z`
- size: `304`
- prototype: `unsigned __int8 __fastcall(struct _TRACERPT_EVENT_TABLE *, struct _TABLE_DATA *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400286b0`
- `0x140028cc4`

## callees

- `0x140029794`
- `0x1400400be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029817`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029817`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029828`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029828`

## pseudocode

```c
unsigned __int8 __fastcall CreateGroupbyColumnDataFromTable(struct _TRACERPT_EVENT_TABLE *a1, struct _TABLE_DATA *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rax
  int v7; // r9d
  unsigned int v8; // ebp
  __int64 v9; // rdi
  __int64 v10; // rcx
  unsigned int v11; // r8d
  __int64 v12; // r13
  HANDLE ProcessHeap; // rax
  __int64 v14; // rax
  unsigned int v15; // edx
  __int64 v16; // rbp
  __int64 v17; // r14
  void *v18; // rcx
  __int64 v19; // r12
  const void *v20; // rdx
  unsigned int i; // [rsp+78h] [rbp+10h]

  if ( !*(_DWORD *)a2 )
    return 1;
  v4 = 0;
  while ( 1 )
  {
    v5 = *((_QWORD *)a2 + 1);
    v6 = 32LL * v4;
    v7 = *(_DWORD *)(v6 + v5);
    if ( !v7 )
      return 0;
    v8 = 0;
    v9 = v6 + v5;
    if ( *((_DWORD *)a1 + 9) )
    {
      v10 = 0;
      do
      {
        v11 = v8 + *(_DWORD *)(32LL * *(unsigned int *)(*((_QWORD *)a1 + 5) + 4 * v10) + *(_QWORD *)(v9 + 8) + 16);
        if ( v11 < v8 )
          return 0;
        v10 = (unsigned int)(v10 + 1);
        v8 = v11;
      }
      while ( (unsigned int)v10 < *((_DWORD *)a1 + 9) );
    }
    v12 = 32LL * (unsigned int)(v7 - 1);
    *(_DWORD *)(*(_QWORD *)(v9 + 8) + v12 + 16) = v8;
    ProcessHeap = GetProcessHeap();
    *(_QWORD *)(*(_QWORD *)(v9 + 8) + v12 + 8) = HeapAlloc(ProcessHeap, 8u, v8);
    v14 = *(_QWORD *)(v9 + 8);
    if ( !*(_QWORD *)(v14 + v12 + 8) )
      return 0;
    v15 = 0;
    *(_BYTE *)(v14 + v12 + 24) = 1;
    v16 = 0;
    for ( i = 0; (unsigned int)v16 < *((_DWORD *)a1 + 9); i = v15 )
    {
      v17 = *(_QWORD *)(v9 + 8);
      v18 = (void *)(*(_QWORD *)(v17 + v12 + 8) + v15);
      v19 = 32LL * *(unsigned int *)(*((_QWORD *)a1 + 5) + 4 * v16);
      v20 = (const void *)(v19 + v17 + 8);
      if ( !*(_BYTE *)(v19 + v17 + 25) )
        v20 = *(const void **)(v19 + v17 + 8);
      memcpy_0(v18, v20, *(unsigned int *)(v19 + v17 + 16));
      v16 = (unsigned int)(v16 + 1);
      v15 = *(_DWORD *)(v19 + v17 + 16) + i;
    }
    if ( ++v4 >= *(_DWORD *)a2 )
      return 1;
  }
}

```

## disassembly

```asm
0x140029794  push    rbx
0x140029796  push    rbp
0x140029797  push    rsi
0x140029798  push    rdi
0x140029799  push    r12
0x14002979b  push    r13
0x14002979d  push    r14
0x14002979f  push    r15
0x1400297a1  sub     rsp, 28h
0x1400297a5  cmp     dword ptr [rdx], 0
0x1400297a8  mov     r15, rdx
0x1400297ab  mov     rsi, rcx
0x1400297ae  jbe     loc_1400298AD
0x1400297b4  xor     ebx, ebx
0x1400297b6  mov     rcx, [r15+8]
0x1400297ba  mov     eax, ebx
0x1400297bc  shl     rax, 5
0x1400297c0  mov     r9d, [rax+rcx]
0x1400297c4  cmp     r9d, 1
0x1400297c8  jb      loc_1400298C0
0x1400297ce  xor     ebp, ebp
0x1400297d0  lea     rdi, [rax+rcx]
0x1400297d4  cmp     [rsi+24h], ebp
0x1400297d7  jbe     short loc_140029806
0x1400297d9  mov     r10, [rsi+28h]
0x1400297dd  xor     ecx, ecx
0x1400297df  mov     rdx, [rdi+8]
0x1400297e3  mov     eax, [r10+rcx*4]
0x1400297e7  shl     rax, 5
0x1400297eb  mov     r8d, [rax+rdx+10h]
0x1400297f0  add     r8d, ebp
0x1400297f3  cmp     r8d, ebp
0x1400297f6  jb      loc_1400298C0
0x1400297fc  inc     ecx
0x1400297fe  mov     ebp, r8d
0x140029801  cmp     ecx, [rsi+24h]
0x140029804  jb      short loc_1400297E3
0x140029806  mov     rax, [rdi+8]
0x14002980a  lea     r13d, [r9-1]
0x14002980e  shl     r13, 5
0x140029812  mov     [rax+r13+10h], ebp
0x140029817  call    cs:__imp_GetProcessHeap
0x14002981d  mov     r8d, ebp; dwBytes
0x140029820  mov     edx, 8; dwFlags
0x140029825  mov     rcx, rax; hHeap
0x140029828  call    cs:__imp_HeapAlloc
0x14002982e  mov     rcx, rax
0x140029831  mov     rax, [rdi+8]
0x140029835  mov     [rax+r13+8], rcx
0x14002983a  mov     rax, [rdi+8]
0x14002983e  cmp     qword ptr [rax+r13+8], 0
0x140029844  jz      short loc_1400298C0
0x140029846  xor     edx, edx
0x140029848  mov     byte ptr [rax+r13+18h], 1
0x14002984e  xor     ebp, ebp
0x140029850  mov     [rsp+68h+arg_8], edx
0x140029854  cmp     [rsi+24h], edx
0x140029857  jbe     short loc_1400298A2
0x140029859  mov     r14, [rdi+8]
0x14002985d  mov     rax, [rsi+28h]
0x140029861  mov     ecx, edx
0x140029863  add     rcx, [r14+r13+8]; void *
0x140029868  mov     r12d, [rax+rbp*4]
0x14002986c  shl     r12, 5
0x140029870  cmp     byte ptr [r12+r14+19h], 0
0x140029876  lea     r9, [r12+r14]
0x14002987a  mov     r8d, [r12+r14+10h]; Size
0x14002987f  lea     rdx, [r9+8]
0x140029883  jnz     short loc_140029889
0x140029885  mov     rdx, [r9+8]; Src
0x140029889  call    memcpy_0
0x14002988e  mov     edx, [rsp+68h+arg_8]
0x140029892  inc     ebp
0x140029894  add     edx, [r12+r14+10h]
0x140029899  mov     [rsp+68h+arg_8], edx
0x14002989d  cmp     ebp, [rsi+24h]
0x1400298a0  jb      short loc_140029859
0x1400298a2  inc     ebx
0x1400298a4  cmp     ebx, [r15]
0x1400298a7  jb      loc_1400297B6
0x1400298ad  mov     al, 1
0x1400298af  add     rsp, 28h
0x1400298b3  pop     r15
0x1400298b5  pop     r14
0x1400298b7  pop     r13
0x1400298b9  pop     r12
0x1400298bb  pop     rdi
0x1400298bc  pop     rsi
0x1400298bd  pop     rbp
0x1400298be  pop     rbx
0x1400298bf  retn
0x1400298c0  xor     al, al
0x1400298c2  jmp     short loc_1400298AF
```
