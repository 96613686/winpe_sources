# SkmiCompleteFaultChain

- ea: `0x14003a790`
- end: `0x14003a8bf`
- name: `SkmiCompleteFaultChain`
- size: `303`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140002a04`
- `0x14003a10c`
- `0x140072884`
- `0x140072fc4`
- `0x14008451c`

## callees

- `0x140003780`
- `0x14002b534`
- `0x14003a790`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
unsigned __int64 __fastcall SkmiCompleteFaultChain(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // r9
  _QWORD *v4; // r8
  __int64 v5; // rbx
  __int64 PteTrace; // rax
  __int64 v7; // rbp
  PVOID *v8; // rsi
  PVOID StackBase; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int64 result; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v15; // ecx
  _UNKNOWN *retaddr; // [rsp+48h] [rbp+0h]
  ULONG BackTraceHash; // [rsp+50h] [rbp+8h] BYREF

  v2 = (_QWORD *)*a2;
  while ( v2 != a2 )
  {
    v4 = v2;
    v2 = (_QWORD *)*v2;
    *((_DWORD *)v4 + 8) |= 2u;
  }
  v5 = a2[2];
  PteTrace = SkmiGetPteTrace(0, a1, 0, v5, *(_QWORD *)a1);
  v7 = PteTrace;
  if ( PteTrace )
  {
    v8 = (PVOID *)(PteTrace + 32);
    memset_0((void *)(PteTrace + 32), 0, 0x40u);
    if ( (SkmiFlags & 0x400000) != 0 )
    {
      StackBase = KeGetPcr()->NtTib.StackBase;
      if ( StackBase )
      {
        if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v8, &BackTraceHash) )
        {
          *(_QWORD *)(v7 + 40) = retaddr;
          *v8 = (PVOID)SkmiGetInstructionPointer(v11, v10);
        }
      }
    }
  }
  result = 0xFFFFF6FB7DBED000uLL;
  if ( (unsigned __int64)a1 >= 0xFFFFF6FB7DBED000uLL )
  {
    result = 0xFFFFF6FB7DBED800uLL;
    if ( (unsigned __int64)a1 < 0xFFFFF6FB7DBED800uLL )
    {
      result = (unsigned __int64)KeGetPcr()->NtTib.StackBase;
      if ( result )
        v13 = *(_QWORD *)(result + 80);
      else
        v13 = 0;
      v14 = *(_QWORD *)(v13 + 232);
      if ( v14 )
      {
        v15 = SkiKvaShadowMode;
        result = (a1 >> 3) & 0x1FF;
        *(_QWORD *)(v14 + 8 * result) = v5;
        if ( v15 != 2 && (v5 & 1) != 0 )
        {
          result = 0x8000000000000000uLL;
          v5 |= 0x8000000000000000uLL;
        }
      }
    }
  }
  *(_QWORD *)a1 = v5;
  return result;
}

```

## disassembly

```asm
0x14003a790  mov     [rsp+arg_8], rbx
0x14003a795  mov     [rsp+arg_10], rbp
0x14003a79a  push    rsi
0x14003a79b  push    rdi
0x14003a79c  push    r14
0x14003a79e  sub     rsp, 30h
0x14003a7a2  mov     r9, [rdx]
0x14003a7a5  mov     rdi, rcx
0x14003a7a8  jmp     short loc_14003A7BB
0x14003a7aa  lea     r8, [r9]
0x14003a7ad  mov     r9, [r9]
0x14003a7b0  mov     eax, [r8+20h]
0x14003a7b4  or      eax, 2
0x14003a7b7  mov     [r8+20h], eax
0x14003a7bb  cmp     r9, rdx
0x14003a7be  jnz     short loc_14003A7AA
0x14003a7c0  mov     rbx, [rdx+10h]
0x14003a7c4  xor     r8d, r8d
0x14003a7c7  mov     rax, [rcx]
0x14003a7ca  mov     r9, rbx
0x14003a7cd  mov     rdx, rdi
0x14003a7d0  mov     [rsp+48h+var_28], rax
0x14003a7d5  xor     ecx, ecx
0x14003a7d7  call    SkmiGetPteTrace
0x14003a7dc  xor     r14d, r14d
0x14003a7df  mov     rbp, rax
0x14003a7e2  test    rax, rax
0x14003a7e5  jz      short loc_14003A83A
0x14003a7e7  lea     rsi, [rax+20h]
0x14003a7eb  xor     edx, edx; Val
0x14003a7ed  mov     rcx, rsi; void *
0x14003a7f0  lea     r8d, [r14+40h]; Size
0x14003a7f4  call    memset_0
0x14003a7f9  test    cs:SkmiFlags, 400000h
0x14003a803  jz      short loc_14003A83A
0x14003a805  mov     rcx, gs:8; FramesToSkip
0x14003a80e  test    rcx, rcx
0x14003a811  jz      short loc_14003A83A
0x14003a813  lea     r9, [rsp+48h+BackTraceHash]; BackTraceHash
0x14003a818  mov     r8, rsi; BackTrace
0x14003a81b  lea     edx, [r14+8]; FramesToCapture
0x14003a81f  call    RtlCaptureStackBackTrace
0x14003a824  test    ax, ax
0x14003a827  jnz     short loc_14003A83A
0x14003a829  mov     rax, [rsp+48h]
0x14003a82e  mov     [rbp+28h], rax
0x14003a832  call    SkmiGetInstructionPointer
0x14003a837  mov     [rsi], rax
0x14003a83a  mov     rax, 0FFFFF6FB7DBED000h
0x14003a844  cmp     rdi, rax
0x14003a847  jb      short loc_14003A8A8
0x14003a849  mov     rax, 0FFFFF6FB7DBED800h
0x14003a853  cmp     rdi, rax
0x14003a856  jnb     short loc_14003A8A8
0x14003a858  mov     rax, gs:8
0x14003a861  test    rax, rax
0x14003a864  jz      short loc_14003A86C
0x14003a866  mov     rcx, [rax+50h]
0x14003a86a  jmp     short loc_14003A86F
0x14003a86c  mov     rcx, r14
0x14003a86f  mov     rdx, [rcx+0E8h]
0x14003a876  test    rdx, rdx
0x14003a879  jz      short loc_14003A8A8
0x14003a87b  mov     ecx, cs:SkiKvaShadowMode
0x14003a881  mov     rax, rdi
0x14003a884  sar     rax, 3
0x14003a888  and     eax, 1FFh
0x14003a88d  mov     [rdx+rax*8], rbx
0x14003a891  cmp     ecx, 2
0x14003a894  jz      short loc_14003A8A8
0x14003a896  test    bl, 1
0x14003a899  jz      short loc_14003A8A8
0x14003a89b  mov     rax, 8000000000000000h
0x14003a8a5  or      rbx, rax
0x14003a8a8  mov     rbp, [rsp+48h+arg_10]
0x14003a8ad  mov     [rdi], rbx
0x14003a8b0  mov     rbx, [rsp+48h+arg_8]
0x14003a8b5  add     rsp, 30h
0x14003a8b9  pop     r14
0x14003a8bb  pop     rdi
0x14003a8bc  pop     rsi
0x14003a8bd  retn
```
