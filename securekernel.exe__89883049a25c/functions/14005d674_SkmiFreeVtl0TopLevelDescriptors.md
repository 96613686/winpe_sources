# SkmiFreeVtl0TopLevelDescriptors

- ea: `0x14005d674`
- end: `0x14005d8ed`
- name: `SkmiFreeVtl0TopLevelDescriptors`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14005e098`

## callees

- `0x140003780`
- `0x140009940`
- `0x14000c8d0`
- `0x140024724`
- `0x14002b534`
- `0x14005d674`
- `0x140081290`
- `0x1400f2fc0`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiFreeVtl0TopLevelDescriptors(ULONG_PTR a1, __int64 a2, __int64 a3, __int64 a4)
{
  ULONG_PTR v4; // r14
  __int64 CurrentIrql; // r12
  __int64 HyperspacePte; // rdi
  unsigned __int64 v7; // rbx
  __int64 PteTrace; // rax
  __int64 v9; // rbp
  PVOID *v10; // rsi
  PVOID StackBase; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // ecx
  ULONG_PTR v18; // rbp
  __int64 v19; // rax
  int v20; // r9d
  __int64 v21; // rsi
  PVOID *v22; // rbx
  PVOID v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  _QWORD *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  int v29; // r8d
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h]
  ULONG BackTraceHash; // [rsp+70h] [rbp+8h] BYREF
  __int64 v33; // [rsp+78h] [rbp+10h]

  v4 = a1;
  CurrentIrql = KeGetCurrentIrql();
  v33 = CurrentIrql;
  __writecr8(2u);
  if ( a1 != -1 )
  {
    do
    {
      HyperspacePte = SkmiGetHyperspacePte(a1, a2, a3, a4);
      v7 = (v4 << 12) & 0xFFFFFFFFFF000LL ^ 0x8000000000000063uLL;
      PteTrace = SkmiGetPteTrace(0, HyperspacePte, 0, ((_DWORD)v4 << 12) ^ 0x63u, *(_QWORD *)HyperspacePte);
      v9 = PteTrace;
      if ( PteTrace )
      {
        v10 = (PVOID *)(PteTrace + 32);
        memset_0((void *)(PteTrace + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          StackBase = KeGetPcr()->NtTib.StackBase;
          if ( StackBase )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v10, &BackTraceHash) )
            {
              *(_QWORD *)(v9 + 40) = retaddr;
              *v10 = (PVOID)SkmiGetInstructionPointer(v13, v12);
            }
          }
        }
      }
      if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
        && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
      {
        v14 = KeGetPcr()->NtTib.StackBase;
        v15 = v14 ? v14[10] : 0LL;
        v16 = *(_QWORD *)(v15 + 232);
        if ( v16 )
        {
          v17 = SkiKvaShadowMode;
          *(_QWORD *)(v16 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v7;
          if ( v17 != 2 )
            v7 |= 0x8000000000000000uLL;
        }
      }
      *(_QWORD *)HyperspacePte = v7;
      v18 = *(_QWORD *)(HyperspacePte << 25 >> 16);
      v19 = SkmiGetPteTrace(0, HyperspacePte, 0, 0, v7);
      v21 = v19;
      if ( v19 )
      {
        v22 = (PVOID *)(v19 + 32);
        memset_0((void *)(v19 + 32), 0, (unsigned int)(v20 + 64));
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          v23 = KeGetPcr()->NtTib.StackBase;
          if ( v23 )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)v23, 8u, v22, &BackTraceHash) )
            {
              *(_QWORD *)(v21 + 40) = retaddr;
              *v22 = (PVOID)SkmiGetInstructionPointer(v25, v24);
            }
          }
        }
      }
      if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
        && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
      {
        v26 = KeGetPcr()->NtTib.StackBase;
        if ( v26 )
          v27 = v26[10];
        else
          v27 = 0;
        v28 = *(_QWORD *)(v27 + 232);
        if ( v28 )
          *(_QWORD *)(v28 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = 0;
      }
      *(_QWORD *)HyperspacePte = 0;
      SkmiReleaseHyperspacePte(HyperspacePte);
      SkmiFreePhysicalPage(0, v4, v29);
      v4 = v18;
    }
    while ( v18 != -1 );
    LOBYTE(CurrentIrql) = v33;
  }
  LOBYTE(a1) = CurrentIrql;
  return SkeLowerIrql(a1);
}

```

## disassembly

```asm
0x14005d674  mov     [rsp+arg_10], rbx
0x14005d679  push    rbp
0x14005d67a  push    rsi
0x14005d67b  push    rdi
0x14005d67c  push    r12
0x14005d67e  push    r13
0x14005d680  push    r14
0x14005d682  push    r15
0x14005d684  sub     rsp, 30h
0x14005d688  mov     r14, rcx
0x14005d68b  mov     r12, cr8
0x14005d68f  mov     [rsp+68h+arg_8], r12
0x14005d694  mov     eax, 2
0x14005d699  mov     cr8, rax
0x14005d69d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14005d6a1  jz      loc_14005D8CC
0x14005d6a7  mov     r15, 0FFFFF68000000000h
0x14005d6b1  shl     r15, 19h
0x14005d6b5  xor     r13d, r13d
0x14005d6b8  mov     r12, 0FFFFF6FB7DBED000h
0x14005d6c2  mov     rsi, 0FFFFF6FB7DBED800h
0x14005d6cc  call    SkmiGetHyperspacePte
0x14005d6d1  mov     rdi, rax
0x14005d6d4  mov     rbx, r14
0x14005d6d7  shl     rbx, 0Ch
0x14005d6db  mov     rax, 0FFFFFFFFFF000h
0x14005d6e5  and     rbx, rax
0x14005d6e8  xor     r8d, r8d
0x14005d6eb  mov     rax, 8000000000000063h
0x14005d6f5  mov     rdx, rdi
0x14005d6f8  mov     rcx, [rdi]
0x14005d6fb  xor     rbx, rax
0x14005d6fe  mov     [rsp+68h+var_48], rcx
0x14005d703  mov     r9, rbx
0x14005d706  xor     ecx, ecx
0x14005d708  call    SkmiGetPteTrace
0x14005d70d  mov     rbp, rax
0x14005d710  test    rax, rax
0x14005d713  jz      short loc_14005D773
0x14005d715  xor     edx, edx; Val
0x14005d717  lea     rsi, [rax+20h]
0x14005d71b  mov     rcx, rsi; void *
0x14005d71e  lea     r8d, [rdx+40h]; Size
0x14005d722  call    memset_0
0x14005d727  test    cs:SkmiFlags, 400000h
0x14005d731  jz      short loc_14005D769
0x14005d733  mov     rcx, gs:8; FramesToSkip
0x14005d73c  test    rcx, rcx
0x14005d73f  jz      short loc_14005D769
0x14005d741  lea     r9, [rsp+68h+BackTraceHash]; BackTraceHash
0x14005d746  mov     r8, rsi; BackTrace
0x14005d749  mov     edx, 8; FramesToCapture
0x14005d74e  call    RtlCaptureStackBackTrace
0x14005d753  test    ax, ax
0x14005d756  jnz     short loc_14005D769
0x14005d758  mov     rax, [rsp+68h]
0x14005d75d  mov     [rbp+28h], rax
0x14005d761  call    SkmiGetInstructionPointer
0x14005d766  mov     [rsi], rax
0x14005d769  mov     rsi, 0FFFFF6FB7DBED800h
0x14005d773  mov     rax, r12
0x14005d776  cmp     rdi, rax
0x14005d779  jb      short loc_14005D7D3
0x14005d77b  mov     rax, rsi
0x14005d77e  cmp     rdi, rax
0x14005d781  jnb     short loc_14005D7D3
0x14005d783  mov     rax, gs:8
0x14005d78c  test    rax, rax
0x14005d78f  jz      short loc_14005D797
0x14005d791  mov     rcx, [rax+50h]
0x14005d795  jmp     short loc_14005D79A
0x14005d797  mov     rcx, r13
0x14005d79a  mov     rdx, [rcx+0E8h]
0x14005d7a1  test    rdx, rdx
0x14005d7a4  jz      short loc_14005D7D3
0x14005d7a6  mov     ecx, cs:SkiKvaShadowMode
0x14005d7ac  mov     rax, rdi
0x14005d7af  sar     rax, 3
0x14005d7b3  and     eax, 1FFh
0x14005d7b8  mov     [rdx+rax*8], rbx
0x14005d7bc  cmp     ecx, 2
0x14005d7bf  jz      short loc_14005D7D3
0x14005d7c1  test    bl, 1
0x14005d7c4  jz      short loc_14005D7D3
0x14005d7c6  mov     rax, 8000000000000000h
0x14005d7d0  or      rbx, rax
0x14005d7d3  mov     [rdi], rbx
0x14005d7d6  mov     rax, rdi
0x14005d7d9  shl     rax, 19h
0x14005d7dd  xor     r9d, r9d
0x14005d7e0  sub     rax, r15
0x14005d7e3  mov     [rsp+68h+var_48], rbx
0x14005d7e8  sar     rax, 10h
0x14005d7ec  xor     r8d, r8d
0x14005d7ef  mov     rdx, rdi
0x14005d7f2  xor     ecx, ecx
0x14005d7f4  mov     rbp, [rax]
0x14005d7f7  call    SkmiGetPteTrace
0x14005d7fc  mov     rsi, rax
0x14005d7ff  test    rax, rax
0x14005d802  jz      short loc_14005D858
0x14005d804  lea     rbx, [rax+20h]
0x14005d808  xor     edx, edx; Val
0x14005d80a  mov     rcx, rbx; void *
0x14005d80d  lea     r8d, [r9+40h]; Size
0x14005d811  call    memset_0
0x14005d816  test    cs:SkmiFlags, 400000h
0x14005d820  jz      short loc_14005D858
0x14005d822  mov     rcx, gs:8; FramesToSkip
0x14005d82b  test    rcx, rcx
0x14005d82e  jz      short loc_14005D858
0x14005d830  lea     r9, [rsp+68h+BackTraceHash]; BackTraceHash
0x14005d835  mov     r8, rbx; BackTrace
0x14005d838  mov     edx, 8; FramesToCapture
0x14005d83d  call    RtlCaptureStackBackTrace
0x14005d842  test    ax, ax
0x14005d845  jnz     short loc_14005D858
0x14005d847  mov     rax, [rsp+68h]
0x14005d84c  mov     [rsi+28h], rax
0x14005d850  call    SkmiGetInstructionPointer
0x14005d855  mov     [rbx], rax
0x14005d858  mov     rax, r12
0x14005d85b  mov     rsi, 0FFFFF6FB7DBED800h
0x14005d865  cmp     rdi, rax
0x14005d868  jb      short loc_14005D8A5
0x14005d86a  mov     rax, rsi
0x14005d86d  cmp     rdi, rax
0x14005d870  jnb     short loc_14005D8A5
0x14005d872  mov     rax, gs:8
0x14005d87b  test    rax, rax
0x14005d87e  jz      short loc_14005D886
0x14005d880  mov     rcx, [rax+50h]
0x14005d884  jmp     short loc_14005D889
0x14005d886  mov     rcx, r13
0x14005d889  mov     r8, [rcx+0E8h]
0x14005d890  test    r8, r8
0x14005d893  jz      short loc_14005D8A5
0x14005d895  mov     rax, rdi
0x14005d898  sar     rax, 3
0x14005d89c  and     eax, 1FFh
0x14005d8a1  mov     [r8+rax*8], r13
0x14005d8a5  mov     rcx, rdi
0x14005d8a8  mov     [rdi], r13
0x14005d8ab  call    SkmiReleaseHyperspacePte
0x14005d8b0  mov     rdx, r14
0x14005d8b3  xor     ecx, ecx
0x14005d8b5  call    SkmiFreePhysicalPage
0x14005d8ba  mov     r14, rbp
0x14005d8bd  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14005d8c1  jnz     loc_14005D6CC
0x14005d8c7  mov     r12, [rsp+68h+arg_8]
0x14005d8cc  mov     cl, r12b
0x14005d8cf  call    SkeLowerIrql
0x14005d8d4  mov     rbx, [rsp+68h+arg_10]
0x14005d8dc  add     rsp, 30h
0x14005d8e0  pop     r15
0x14005d8e2  pop     r14
0x14005d8e4  pop     r13
0x14005d8e6  pop     r12
0x14005d8e8  pop     rdi
0x14005d8e9  pop     rsi
0x14005d8ea  pop     rbp
0x14005d8eb  retn
```
