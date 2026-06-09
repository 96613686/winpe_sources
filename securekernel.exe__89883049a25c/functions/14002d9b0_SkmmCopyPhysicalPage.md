# SkmmCopyPhysicalPage

- ea: `0x14002d9b0`
- end: `0x14002dca0`
- name: `SkmmCopyPhysicalPage`
- size: `752`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400b93e0`
- `0x1400bc75c`

## callees

- `0x140003780`
- `0x1400290f8`
- `0x14002b534`
- `0x14002d9b0`
- `0x14002e70c`
- `0x14002f3f8`
- `0x140081290`
- `0x1400f2fc0`
- `0x1400f3000`
- `0x1400f9a80`

## pseudocode

```c
void *__fastcall SkmmCopyPhysicalPage(unsigned __int64 a1, void *a2, unsigned __int64 a3)
{
  unsigned __int64 v5; // rdx
  __int64 v7; // rdi
  unsigned __int64 v8; // rsi
  __int64 PteTrace; // rax
  __int64 v10; // r8
  __int64 v11; // r14
  PVOID *v12; // rbx
  ULONG v13; // ecx
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *StackBase; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rbp
  PVOID *v25; // r14
  PVOID v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  int v32; // ecx
  unsigned __int8 CurrentIrql; // bl
  unsigned __int64 v34; // rdx
  __int64 v35; // rcx
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]
  __int64 BackTraceHash; // [rsp+80h] [rbp+8h] BYREF

  if ( a1 > 0xFFFFFFFFFFLL )
    __fastfail(0x3Fu);
  v5 = *(_QWORD *)(8 * a1 - 0x180000000000LL);
  if ( v5 >> 61 == 6 && (v5 & 0x4000) != 0 )
    return memset_0(a2, 0, 0x1000u);
  if ( a3 )
  {
    v7 = ((a3 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
    v8 = (((16 * (a1 & 0xFFFFFFFFFFLL)) | word_140156D90 & 1) << 8) | 0x8000000000000021uLL;
    PteTrace = SkmiGetPteTrace(
                 0,
                 (unsigned int)(a3 >> 9) & 0xFFFFFFF8,
                 0,
                 (((16 * (_DWORD)a1) | word_140156D90 & 1) << 8) | 0x21u,
                 *(_QWORD *)v7);
    v11 = PteTrace;
    if ( PteTrace )
    {
      v12 = (PVOID *)(PteTrace + 32);
      memset_0((void *)(PteTrace + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0
        && KeGetPcr()->NtTib.StackBase
        && !RtlCaptureStackBackTrace(v13, 8u, v12, (PULONG)&BackTraceHash) )
      {
        *(_QWORD *)(v11 + 40) = retaddr;
        *v12 = (PVOID)SkmiGetInstructionPointer(v15, v14);
      }
    }
    if ( (unsigned __int64)v7 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v7 < 0xFFFFF6FB7DBED800uLL )
    {
      StackBase = KeGetPcr()->NtTib.StackBase;
      v17 = StackBase ? StackBase[10] : 0LL;
      v18 = *(_QWORD *)(v17 + 232);
      if ( v18 )
        *(_QWORD *)(v18 + 8 * ((v7 >> 3) & 0x1FF)) = v8;
    }
    *(_QWORD *)v7 = v8;
    SkeCopyPage(a2, a3, v10);
    BackTraceHash = 2;
    SKMI_SWIZZLE_INVALID_PTE(&BackTraceHash, v19, v20, v21);
    v22 = BackTraceHash;
    v23 = SkmiGetPteTrace(0, (unsigned int)(a3 >> 9) & 0xFFFFFFF8, 0, BackTraceHash, *(_QWORD *)v7);
    v24 = v23;
    if ( v23 )
    {
      v25 = (PVOID *)(v23 + 32);
      memset_0((void *)(v23 + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v26 = KeGetPcr()->NtTib.StackBase;
        if ( v26 )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)v26, 8u, v25, (PULONG)&BackTraceHash) )
          {
            *(_QWORD *)(v24 + 40) = retaddr;
            *v25 = (PVOID)SkmiGetInstructionPointer(v28, v27);
          }
        }
      }
    }
    if ( (unsigned __int64)v7 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v7 < 0xFFFFF6FB7DBED800uLL )
    {
      v29 = KeGetPcr()->NtTib.StackBase;
      if ( v29 )
        v30 = v29[10];
      else
        v30 = 0;
      v31 = *(_QWORD *)(v30 + 232);
      if ( v31 )
      {
        v32 = SkiKvaShadowMode;
        *(_QWORD *)(v31 + 8 * ((v7 >> 3) & 0x1FF)) = v22;
        if ( v32 != 2 && (v22 & 1) != 0 )
          v22 |= 0x8000000000000000uLL;
      }
    }
    *(_QWORD *)v7 = v22;
    return (void *)SkeFlushSingleCurrentTb(a3);
  }
  else
  {
    CurrentIrql = KeGetCurrentIrql();
    v34 = 15;
    if ( KeGetCurrentIrql() <= 2u )
      v34 = 2;
    __writecr8(v34);
    SkmiCopyPage(a1, a2);
    LOBYTE(v35) = CurrentIrql;
    return (void *)SkeLowerIrql(v35);
  }
}

```

## disassembly

```asm
0x14002d9b0  push    rbx
0x14002d9b2  push    rbp
0x14002d9b3  push    rsi
0x14002d9b4  push    rdi
0x14002d9b5  push    r12
0x14002d9b7  push    r13
0x14002d9b9  push    r14
0x14002d9bb  push    r15
0x14002d9bd  sub     rsp, 38h
0x14002d9c1  mov     r15, r8
0x14002d9c4  mov     rbp, rdx
0x14002d9c7  mov     r9, 0FFFFEFFFFFFFFFFFh
0x14002d9d1  mov     rdx, 0FFFFE80000000000h
0x14002d9db  mov     rax, rdx
0x14002d9de  sub     r9, rax
0x14002d9e1  sar     r9, 3
0x14002d9e5  cmp     rcx, r9
0x14002d9e8  jbe     short loc_14002D9F1
0x14002d9ea  mov     ecx, 3Fh ; '?'
0x14002d9ef  int     29h; Win8: RtlFailFast(ecx)
0x14002d9f1  mov     rax, rdx
0x14002d9f4  mov     rdx, [rax+rcx*8]
0x14002d9f8  mov     rax, rdx
0x14002d9fb  shr     rax, 3Dh
0x14002d9ff  cmp     al, 6
0x14002da01  jnz     short loc_14002DA1F
0x14002da03  bt      rdx, 0Eh
0x14002da08  jnb     short loc_14002DA1F
0x14002da0a  xor     edx, edx; Val
0x14002da0c  mov     r8d, 1000h; Size
0x14002da12  mov     rcx, rbp; void *
0x14002da15  call    memset_0
0x14002da1a  jmp     loc_14002DC8E
0x14002da1f  xor     r12d, r12d
0x14002da22  test    r15, r15
0x14002da25  jz      loc_14002DC65
0x14002da2b  mov     rdi, r15
0x14002da2e  mov     rdx, 7FFFFFFFF8h
0x14002da38  shr     rdi, 9
0x14002da3c  and     rdi, rdx
0x14002da3f  mov     rdx, 0FFFFF68000000000h
0x14002da49  movzx   esi, byte ptr cs:word_140156D90
0x14002da50  add     rdi, rdx
0x14002da53  and     esi, 1
0x14002da56  mov     rax, 0FFFFFFFFFFh
0x14002da60  and     rcx, rax
0x14002da63  xor     r8d, r8d
0x14002da66  shl     rcx, 4
0x14002da6a  mov     rax, 8000000000000021h
0x14002da74  or      rsi, rcx
0x14002da77  mov     rdx, rdi
0x14002da7a  shl     rsi, 8
0x14002da7e  xor     ecx, ecx
0x14002da80  or      rsi, rax
0x14002da83  mov     rax, [rdi]
0x14002da86  mov     r9, rsi
0x14002da89  mov     [rsp+78h+var_58], rax
0x14002da8e  call    SkmiGetPteTrace
0x14002da93  mov     r14, rax
0x14002da96  test    rax, rax
0x14002da99  jz      short loc_14002DAF3
0x14002da9b  lea     rbx, [rax+20h]
0x14002da9f  xor     edx, edx; Val
0x14002daa1  mov     rcx, rbx; void *
0x14002daa4  lea     r8d, [r12+40h]; Size
0x14002daa9  call    memset_0
0x14002daae  test    cs:SkmiFlags, 400000h
0x14002dab8  jz      short loc_14002DAF3
0x14002daba  mov     rax, gs:8
0x14002dac3  test    rax, rax
0x14002dac6  jz      short loc_14002DAF3
0x14002dac8  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x14002dad0  mov     r8, rbx; BackTrace
0x14002dad3  lea     edx, [r12+8]; FramesToCapture
0x14002dad8  call    RtlCaptureStackBackTrace
0x14002dadd  test    ax, ax
0x14002dae0  jnz     short loc_14002DAF3
0x14002dae2  mov     rax, [rsp+78h]
0x14002dae7  mov     [r14+28h], rax
0x14002daeb  call    SkmiGetInstructionPointer
0x14002daf0  mov     [rbx], rax
0x14002daf3  mov     rax, 0FFFFF6FB7DBED000h
0x14002dafd  mov     rax, rax
0x14002db00  mov     r13, 0FFFFF6FB7DBED800h
0x14002db0a  cmp     rdi, rax
0x14002db0d  jb      short loc_14002DB4A
0x14002db0f  mov     rax, r13
0x14002db12  cmp     rdi, rax
0x14002db15  jnb     short loc_14002DB4A
0x14002db17  mov     rax, gs:8
0x14002db20  test    rax, rax
0x14002db23  jz      short loc_14002DB2B
0x14002db25  mov     rcx, [rax+50h]
0x14002db29  jmp     short loc_14002DB2E
0x14002db2b  mov     rcx, r12
0x14002db2e  mov     rdx, [rcx+0E8h]
0x14002db35  test    rdx, rdx
0x14002db38  jz      short loc_14002DB4A
0x14002db3a  mov     rax, rdi
0x14002db3d  sar     rax, 3
0x14002db41  and     eax, 1FFh
0x14002db46  mov     [rdx+rax*8], rsi
0x14002db4a  mov     rdx, r15
0x14002db4d  mov     [rdi], rsi
0x14002db50  mov     rcx, rbp
0x14002db53  call    SkeCopyPage
0x14002db58  mov     esi, 2
0x14002db5d  lea     rcx, [rsp+78h+BackTraceHash]
0x14002db65  mov     [rsp+78h+BackTraceHash], rsi
0x14002db6d  call    SKMI_SWIZZLE_INVALID_PTE
0x14002db72  mov     rax, [rdi]
0x14002db75  xor     r8d, r8d
0x14002db78  mov     rbx, [rsp+78h+BackTraceHash]
0x14002db80  mov     rdx, rdi
0x14002db83  mov     r9, rbx
0x14002db86  mov     [rsp+78h+var_58], rax
0x14002db8b  xor     ecx, ecx
0x14002db8d  call    SkmiGetPteTrace
0x14002db92  mov     rbp, rax
0x14002db95  test    rax, rax
0x14002db98  jz      short loc_14002DBEF
0x14002db9a  lea     r14, [rax+20h]
0x14002db9e  xor     edx, edx; Val
0x14002dba0  mov     rcx, r14; void *
0x14002dba3  lea     r8d, [rsi+3Eh]; Size
0x14002dba7  call    memset_0
0x14002dbac  test    cs:SkmiFlags, 400000h
0x14002dbb6  jz      short loc_14002DBEF
0x14002dbb8  mov     rcx, gs:8; FramesToSkip
0x14002dbc1  test    rcx, rcx
0x14002dbc4  jz      short loc_14002DBEF
0x14002dbc6  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x14002dbce  mov     r8, r14; BackTrace
0x14002dbd1  lea     edx, [rsi+6]; FramesToCapture
0x14002dbd4  call    RtlCaptureStackBackTrace
0x14002dbd9  test    ax, ax
0x14002dbdc  jnz     short loc_14002DBEF
0x14002dbde  mov     rax, [rsp+78h]
0x14002dbe3  mov     [rbp+28h], rax
0x14002dbe7  call    SkmiGetInstructionPointer
0x14002dbec  mov     [r14], rax
0x14002dbef  mov     rax, 0FFFFF6FB7DBED000h
0x14002dbf9  mov     rax, rax
0x14002dbfc  cmp     rdi, rax
0x14002dbff  jb      short loc_14002DC58
0x14002dc01  mov     rax, r13
0x14002dc04  cmp     rdi, rax
0x14002dc07  jnb     short loc_14002DC58
0x14002dc09  mov     rax, gs:8
0x14002dc12  test    rax, rax
0x14002dc15  jz      short loc_14002DC1D
0x14002dc17  mov     rcx, [rax+50h]
0x14002dc1b  jmp     short loc_14002DC20
0x14002dc1d  mov     rcx, r12
0x14002dc20  mov     rdx, [rcx+0E8h]
0x14002dc27  test    rdx, rdx
0x14002dc2a  jz      short loc_14002DC58
0x14002dc2c  mov     ecx, cs:SkiKvaShadowMode
0x14002dc32  mov     rax, rdi
0x14002dc35  sar     rax, 3
0x14002dc39  and     eax, 1FFh
0x14002dc3e  mov     [rdx+rax*8], rbx
0x14002dc42  cmp     ecx, esi
0x14002dc44  jz      short loc_14002DC58
0x14002dc46  test    bl, 1
0x14002dc49  jz      short loc_14002DC58
0x14002dc4b  mov     rax, 8000000000000000h
0x14002dc55  or      rbx, rax
0x14002dc58  mov     rcx, r15
0x14002dc5b  mov     [rdi], rbx
0x14002dc5e  call    SkeFlushSingleCurrentTb
0x14002dc63  jmp     short loc_14002DC8E
0x14002dc65  mov     rbx, cr8
0x14002dc69  mov     rax, cr8
0x14002dc6d  mov     edx, 0Fh
0x14002dc72  lea     esi, [rdx-0Dh]
0x14002dc75  cmp     al, sil
0x14002dc78  cmovbe  edx, esi
0x14002dc7b  mov     cr8, rdx
0x14002dc7f  mov     rdx, rbp
0x14002dc82  call    SkmiCopyPage
0x14002dc87  mov     cl, bl
0x14002dc89  call    SkeLowerIrql
0x14002dc8e  add     rsp, 38h
0x14002dc92  pop     r15
0x14002dc94  pop     r14
0x14002dc96  pop     r13
0x14002dc98  pop     r12
0x14002dc9a  pop     rdi
0x14002dc9b  pop     rsi
0x14002dc9c  pop     rbp
0x14002dc9d  pop     rbx
0x14002dc9e  retn
```
