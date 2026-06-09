# CLogConfigurableFilter::Process(ILogContext *)

- ea: `0x1800260a0`
- end: `0x18002610a`
- name: `?Process@CLogConfigurableFilter@@UEAA?AW4tagLOGRESULT@@PEAVILogContext@@@Z`
- size: `106`
- prototype: `enum tagLOGRESULT __high(struct ILogContext *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18001f81c`
- `0x180025b34`
- `0x1800260a0`

## pseudocode

```c
__int64 __fastcall CLogConfigurableFilter::Process(__int64 a1, struct ILogContext *a2)
{
  int v2; // edi
  __int64 v3; // rbp
  struct tagLOG_FILTER_CLAUSE *v5; // rax
  CLogConfigurableFilter *v6; // rcx
  int v7; // eax
  __int64 v8; // rax
  int *v9; // rbx

  v2 = *(_DWORD *)(a1 + 40);
  v3 = a1 + 8;
  *(_DWORD *)(a1 + 20) = 0;
LABEL_5:
  v8 = CPtrList<tagLOG_OUTPUT_STACK *>::Next(v3);
  v9 = (int *)v8;
  if ( v8 )
  {
    *(_DWORD *)(v8 + 20) = 0;
    while ( 1 )
    {
      v5 = (struct tagLOG_FILTER_CLAUSE *)CPtrList<tagLOG_OUTPUT_STACK *>::Next(v9 + 2);
      if ( !v5 )
        break;
      LOBYTE(v7) = CLogConfigurableFilter::MatchClause(v6, a2, v5);
      if ( !v7 )
        goto LABEL_5;
    }
    v2 = *v9;
  }
  return (unsigned int)(v2 != 0) + 1;
}

```

## disassembly

```asm
0x1800260a0  push    rbx
0x1800260a2  push    rbp
0x1800260a3  push    rsi
0x1800260a4  push    rdi
0x1800260a5  push    r14
0x1800260a7  sub     rsp, 20h
0x1800260ab  mov     edi, [rcx+28h]
0x1800260ae  lea     rbp, [rcx+8]
0x1800260b2  mov     dword ptr [rbp+0Ch], 0
0x1800260b9  mov     r14, rdx
0x1800260bc  jmp     short loc_1800260E2
0x1800260be  mov     dword ptr [rbx+14h], 0
0x1800260c5  lea     rcx, [rbx+8]
0x1800260c9  call    ?Next@?$CPtrList@PEAUtagLOG_OUTPUT_STACK@@@@QEAAPEAUtagLOG_OUTPUT_STACK@@XZ; CPtrList<tagLOG_OUTPUT_STACK *>::Next(void)
0x1800260ce  test    rax, rax
0x1800260d1  jz      short loc_1800260F4
0x1800260d3  mov     r8, rax; struct tagLOG_FILTER_CLAUSE *
0x1800260d6  mov     rdx, r14; struct ILogContext *
0x1800260d9  call    ?MatchClause@CLogConfigurableFilter@@IEAAHPEAVILogContext@@PEAUtagLOG_FILTER_CLAUSE@@@Z; CLogConfigurableFilter::MatchClause(ILogContext *,tagLOG_FILTER_CLAUSE *)
0x1800260de  test    eax, eax
0x1800260e0  jnz     short loc_1800260C5
0x1800260e2  mov     rcx, rbp
0x1800260e5  call    ?Next@?$CPtrList@PEAUtagLOG_OUTPUT_STACK@@@@QEAAPEAUtagLOG_OUTPUT_STACK@@XZ; CPtrList<tagLOG_OUTPUT_STACK *>::Next(void)
0x1800260ea  mov     rbx, rax
0x1800260ed  test    rax, rax
0x1800260f0  jnz     short loc_1800260BE
0x1800260f2  jmp     short loc_1800260F6
0x1800260f4  mov     edi, [rbx]
0x1800260f6  neg     edi
0x1800260f8  sbb     eax, eax
0x1800260fa  neg     eax
0x1800260fc  inc     eax
0x1800260fe  add     rsp, 20h
0x180026102  pop     r14
0x180026104  pop     rdi
0x180026105  pop     rsi
0x180026106  pop     rbp
0x180026107  pop     rbx
0x180026108  retn
```
