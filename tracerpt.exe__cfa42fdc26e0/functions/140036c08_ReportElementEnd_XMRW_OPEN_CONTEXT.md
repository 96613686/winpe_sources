# ReportElementEnd(_XMRW_OPEN_CONTEXT *)

- ea: `0x140036c08`
- end: `0x140036cd7`
- name: `?ReportElementEnd@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14003290c`

## callees

- `0x140036c08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140036c2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140036c2b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140036c3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140036c3d`

## pseudocode

```c
__int64 __fastcall ReportElementEnd(struct _XMRW_OPEN_CONTEXT *a1)
{
  __int64 v1; // rbx
  HANDLE ProcessHeap; // rax
  char *v3; // rax
  _QWORD *v4; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  _WORD *v8; // r9
  _WORD *v9; // rax
  _WORD *v10; // rcx
  _QWORD *v11; // rcx

  v1 = *((_QWORD *)a1 + 8);
  if ( v1 && !*((_BYTE *)a1 + 120) )
  {
    ProcessHeap = GetProcessHeap();
    v3 = (char *)HeapAlloc(ProcessHeap, 8u, 0x218u);
    v4 = v3;
    if ( !v3 )
      return 8;
    v6 = 2147483646;
    v7 = 260;
    v8 = (_WORD *)*((_QWORD *)g_TraceContext + 774);
    v9 = v3 + 16;
    do
    {
      if ( !v6 )
        break;
      if ( !*v8 )
        break;
      *v9++ = *v8++;
      --v6;
      --v7;
    }
    while ( v7 );
    v10 = v9 - 1;
    if ( v7 )
      v10 = v9;
    *v10 = 0;
    if ( !v7 )
      return 1359;
    v11 = *(_QWORD **)(v1 + 40);
    if ( *v11 != v1 + 32 )
      __fastfail(3u);
    *v4 = v1 + 32;
    v4[1] = v11;
    *v11 = v4;
    *(_QWORD *)(v1 + 40) = v4;
  }
  return 0;
}

```

## disassembly

```asm
0x140036c08  mov     [rsp+arg_0], rbx
0x140036c0d  push    rdi
0x140036c0e  sub     rsp, 20h
0x140036c12  mov     rbx, [rcx+40h]
0x140036c16  xor     edi, edi
0x140036c18  test    rbx, rbx
0x140036c1b  jz      loc_140036CCA
0x140036c21  cmp     [rcx+78h], dil
0x140036c25  jnz     loc_140036CCA
0x140036c2b  call    cs:__imp_GetProcessHeap
0x140036c31  lea     edx, [rdi+8]; dwFlags
0x140036c34  mov     r8d, 218h; dwBytes
0x140036c3a  mov     rcx, rax; hHeap
0x140036c3d  call    cs:__imp_HeapAlloc
0x140036c43  mov     rdx, rax
0x140036c46  test    rax, rax
0x140036c49  jnz     short loc_140036C50
0x140036c4b  lea     eax, [rdi+8]
0x140036c4e  jmp     short loc_140036CCC
0x140036c50  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140036c57  mov     ecx, 7FFFFFFEh
0x140036c5c  mov     r8d, 104h
0x140036c62  mov     r9, [rax+1830h]
0x140036c69  lea     rax, [rdx+10h]
0x140036c6d  test    rcx, rcx
0x140036c70  jz      short loc_140036C91
0x140036c72  movzx   r10d, word ptr [r9]
0x140036c76  test    r10w, r10w
0x140036c7a  jz      short loc_140036C91
0x140036c7c  mov     [rax], r10w
0x140036c80  add     r9, 2
0x140036c84  add     rax, 2
0x140036c88  dec     rcx
0x140036c8b  sub     r8, 1
0x140036c8f  jnz     short loc_140036C6D
0x140036c91  test    r8, r8
0x140036c94  lea     rcx, [rax-2]
0x140036c98  cmovnz  rcx, rax
0x140036c9c  mov     [rcx], di
0x140036c9f  jnz     short loc_140036CA8
0x140036ca1  mov     eax, 54Fh
0x140036ca6  jmp     short loc_140036CCC
0x140036ca8  lea     rax, [rbx+20h]
0x140036cac  mov     rcx, [rax+8]
0x140036cb0  cmp     [rcx], rax
0x140036cb3  jz      short loc_140036CBC
0x140036cb5  mov     ecx, 3
0x140036cba  int     29h; Win8: RtlFailFast(ecx)
0x140036cbc  mov     [rdx], rax
0x140036cbf  mov     [rdx+8], rcx
0x140036cc3  mov     [rcx], rdx
0x140036cc6  mov     [rax+8], rdx
0x140036cca  xor     eax, eax
0x140036ccc  mov     rbx, [rsp+28h+arg_0]
0x140036cd1  add     rsp, 20h
0x140036cd5  pop     rdi
0x140036cd6  retn
```
