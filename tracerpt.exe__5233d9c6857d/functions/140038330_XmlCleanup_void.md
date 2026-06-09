# XmlCleanup(void *)

- ea: `0x140038330`
- end: `0x140038401`
- name: `?XmlCleanup@@YAXPEAX@Z`
- size: `209`
- prototype: `void __fastcall(void *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140017398`
- `0x14001db34`
- `0x14002e418`
- `0x140038330`

## callees

- `0x14003252c`
- `0x1400328a4`
- `0x140037ddc`
- `0x140038330`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003836e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400383e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003836e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400383e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140038360`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400383d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140038360`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400383d6`

## pseudocode

```c
void __fastcall XmlCleanup(char *a1)
{
  _QWORD *v2; // rdi
  HANDLE ProcessHeap; // rax
  struct _TRACERPT_STRING *v4; // rdi
  struct _TRACERPT_STRING *v5; // rax
  struct _TRACERPT_STRING **v6; // rdx
  struct _TRACERPT_STRING *v7; // rcx
  __int64 v8; // rax
  HANDLE v9; // rax

  if ( a1 )
  {
    DeleteTracerptReport((struct _XMRW_OPEN_CONTEXT *)a1);
    while ( 1 )
    {
      v2 = (_QWORD *)*((_QWORD *)a1 + 7);
      if ( !v2 )
        break;
      *((_QWORD *)a1 + 7) = *v2;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    if ( a1[144] )
    {
      v4 = (struct _TRACERPT_STRING *)*((_QWORD *)a1 + 16);
      while ( a1 + 128 != (char *)v4 )
      {
        v5 = *(struct _TRACERPT_STRING **)v4;
        if ( *(struct _TRACERPT_STRING **)(*(_QWORD *)v4 + 8LL) != v4
          || (v6 = (struct _TRACERPT_STRING **)*((_QWORD *)v4 + 1), *v6 != v4) )
        {
          __fastfail(3u);
        }
        v7 = v4;
        *v6 = v5;
        v4 = v5;
        *((_QWORD *)v5 + 1) = v6;
        DeleteTracerptString(v7);
      }
    }
    v8 = *((_QWORD *)a1 + 14);
    if ( v8 )
    {
      *(_QWORD *)(v8 + 64) = 0;
      XmlCleanup(*((void **)a1 + 14));
    }
    XmRWCloseFile(a1);
    v9 = GetProcessHeap();
    HeapFree(v9, 0, a1);
  }
}

```

## disassembly

```asm
0x140038330  test    rcx, rcx
0x140038333  jz      locret_1400383F9
0x140038339  mov     [rsp+arg_0], rbx
0x14003833e  mov     [rsp+arg_8], rsi
0x140038343  push    rdi
0x140038344  sub     rsp, 20h
0x140038348  mov     rbx, rcx
0x14003834b  call    ?DeleteTracerptReport@@YAXPEAU_XMRW_OPEN_CONTEXT@@@Z; DeleteTracerptReport(_XMRW_OPEN_CONTEXT *)
0x140038350  mov     rdi, [rbx+38h]
0x140038354  test    rdi, rdi
0x140038357  jz      short loc_140038376
0x140038359  mov     rax, [rdi]
0x14003835c  mov     [rbx+38h], rax
0x140038360  call    cs:__imp_GetProcessHeap
0x140038366  mov     r8, rdi; lpMem
0x140038369  xor     edx, edx; dwFlags
0x14003836b  mov     rcx, rax; hHeap
0x14003836e  call    cs:__imp_HeapFree
0x140038374  jmp     short loc_140038350
0x140038376  cmp     byte ptr [rbx+90h], 0
0x14003837d  jz      short loc_1400383B4
0x14003837f  lea     rsi, [rbx+80h]
0x140038386  mov     rdi, [rsi]
0x140038389  jmp     short loc_1400383AF
0x14003838b  mov     rax, [rdi]
0x14003838e  cmp     [rax+8], rdi
0x140038392  jnz     short loc_1400383FA
0x140038394  mov     rdx, [rdi+8]
0x140038398  cmp     [rdx], rdi
0x14003839b  jnz     short loc_1400383FA
0x14003839d  mov     rcx, rdi; Block
0x1400383a0  mov     [rdx], rax
0x1400383a3  mov     rdi, rax
0x1400383a6  mov     [rax+8], rdx
0x1400383aa  call    ?DeleteTracerptString@@YAXPEAU_TRACERPT_STRING@@@Z; DeleteTracerptString(_TRACERPT_STRING *)
0x1400383af  cmp     rsi, rdi
0x1400383b2  jnz     short loc_14003838B
0x1400383b4  mov     rax, [rbx+70h]
0x1400383b8  test    rax, rax
0x1400383bb  jz      short loc_1400383CE
0x1400383bd  mov     qword ptr [rax+40h], 0
0x1400383c5  mov     rcx, [rbx+70h]; void *
0x1400383c9  call    ?XmlCleanup@@YAXPEAX@Z; XmlCleanup(void *)
0x1400383ce  mov     rcx, rbx
0x1400383d1  call    XmRWCloseFile
0x1400383d6  call    cs:__imp_GetProcessHeap
0x1400383dc  mov     r8, rbx; lpMem
0x1400383df  xor     edx, edx; dwFlags
0x1400383e1  mov     rcx, rax; hHeap
0x1400383e4  call    cs:__imp_HeapFree
0x1400383ea  mov     rbx, [rsp+28h+arg_0]
0x1400383ef  mov     rsi, [rsp+28h+arg_8]
0x1400383f4  add     rsp, 20h
0x1400383f8  pop     rdi
0x1400383f9  retn
0x1400383fa  mov     ecx, 3
0x1400383ff  int     29h; Win8: RtlFailFast(ecx)
```
