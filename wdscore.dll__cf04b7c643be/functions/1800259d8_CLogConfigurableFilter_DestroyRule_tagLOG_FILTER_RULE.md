# CLogConfigurableFilter::DestroyRule(tagLOG_FILTER_RULE *)

- ea: `0x1800259d8`
- end: `0x180025a46`
- name: `?DestroyRule@CLogConfigurableFilter@@IEAAXPEAUtagLOG_FILTER_RULE@@@Z`
- size: `110`
- prototype: `void(CLogConfigurableFilter *__hidden this, struct tagLOG_FILTER_RULE *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180025a4c`
- `0x180025ce8`

## callees

- `0x180001184`
- `0x18001e224`
- `0x18001f81c`
- `0x180025978`
- `0x1800259d8`
- `0x1800274de`

## pseudocode

```c
void __fastcall CLogConfigurableFilter::DestroyRule(CLogConfigurableFilter *this, struct tagLOG_FILTER_RULE *a2)
{
  char *v2; // rbx
  struct tagLOG_FILTER_CLAUSE *v4; // rax
  CLogConfigurableFilter *v5; // rcx

  v2 = (char *)a2 + 8;
  *((_DWORD *)a2 + 5) = 0;
  while ( 1 )
  {
    v4 = (struct tagLOG_FILTER_CLAUSE *)CPtrList<tagLOG_OUTPUT_STACK *>::Next(v2);
    if ( !v4 )
      break;
    CLogConfigurableFilter::DestroyClause(v5, v4);
  }
  if ( *(_QWORD *)v2 )
  {
    memset_0(*(void **)v2, 0, 8LL * *((unsigned int *)v2 + 2));
    *((_DWORD *)v2 + 2) = 0;
  }
  if ( a2 )
  {
    CPtrList<tagLOG_FILTER_CLAUSE *>::~CPtrList<tagLOG_FILTER_CLAUSE *>(v2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x1800259d8  mov     [rsp+arg_0], rbx
0x1800259dd  push    rdi
0x1800259de  sub     rsp, 20h
0x1800259e2  lea     rbx, [rdx+8]
0x1800259e6  mov     rdi, rdx
0x1800259e9  mov     dword ptr [rbx+0Ch], 0
0x1800259f0  jmp     short loc_1800259FA
0x1800259f2  mov     rdx, rax; struct tagLOG_FILTER_CLAUSE *
0x1800259f5  call    ?DestroyClause@CLogConfigurableFilter@@IEAAXPEAUtagLOG_FILTER_CLAUSE@@@Z; CLogConfigurableFilter::DestroyClause(tagLOG_FILTER_CLAUSE *)
0x1800259fa  mov     rcx, rbx
0x1800259fd  call    ?Next@?$CPtrList@PEAUtagLOG_OUTPUT_STACK@@@@QEAAPEAUtagLOG_OUTPUT_STACK@@XZ; CPtrList<tagLOG_OUTPUT_STACK *>::Next(void)
0x180025a02  test    rax, rax
0x180025a05  jnz     short loc_1800259F2
0x180025a07  mov     rcx, [rbx]; void *
0x180025a0a  test    rcx, rcx
0x180025a0d  jz      short loc_180025A25
0x180025a0f  mov     r8d, [rbx+8]
0x180025a13  xor     edx, edx; Val
0x180025a15  shl     r8, 3; Size
0x180025a19  call    memset_0
0x180025a1e  mov     dword ptr [rbx+8], 0
0x180025a25  test    rdi, rdi
0x180025a28  jz      short loc_180025A3A
0x180025a2a  mov     rcx, rbx
0x180025a2d  call    ??1?$CPtrList@PEAUtagLOG_FILTER_CLAUSE@@@@QEAA@XZ; CPtrList<tagLOG_FILTER_CLAUSE *>::~CPtrList<tagLOG_FILTER_CLAUSE *>(void)
0x180025a32  mov     rcx, rdi; Block
0x180025a35  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025a3a  mov     rbx, [rsp+28h+arg_0]
0x180025a3f  add     rsp, 20h
0x180025a43  pop     rdi
0x180025a44  retn
```
