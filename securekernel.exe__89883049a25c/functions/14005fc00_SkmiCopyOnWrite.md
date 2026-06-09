# SkmiCopyOnWrite

- ea: `0x14005fc00`
- end: `0x140060043`
- name: `SkmiCopyOnWrite`
- size: `1091`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG_PTR BugCheckParameter3, __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1400720b8`
- `0x140072884`

## callees

- `0x140003780`
- `0x140008ec4`
- `0x140009940`
- `0x14000c8d0`
- `0x14001ca04`
- `0x1400295a8`
- `0x14002b514`
- `0x14002b534`
- `0x14002c5b0`
- `0x14003213c`
- `0x140050ba4`
- `0x14005fc00`
- `0x140060370`
- `0x14007c95c`
- `0x14007c9b8`
- `0x140081290`
- `0x1400f3000`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCopyOnWrite(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        ULONG_PTR BugCheckParameter3,
        unsigned __int64 a6)
{
  __int64 result; // rax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdx
  unsigned int v16; // r8d
  __int64 v17; // r15
  __int64 v18; // rsi
  unsigned __int64 v19; // rbx
  __int64 PteTrace; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r14
  PVOID *v24; // rsi
  ULONG v25; // ecx
  USHORT v26; // ax
  __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  _QWORD *StackBase; // rax
  __int64 HyperspacePte; // r14
  ULONG_PTR v31; // rbx
  __int64 v32; // rax
  __int64 v33; // r10
  __int64 v34; // r8
  PVOID *v35; // rsi
  PVOID v36; // rcx
  USHORT v37; // ax
  __int64 v38; // rdx
  __int64 v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rdx
  int v43; // ecx
  __int64 v44; // rdx
  __int64 v45; // r11
  __int64 v46; // rsi
  _QWORD *v47; // rbx
  __int64 v48; // rax
  unsigned int v49; // edx
  unsigned int v50; // [rsp+30h] [rbp-68h] BYREF
  ULONG BackTraceHash; // [rsp+34h] [rbp-64h] BYREF
  __int64 v52; // [rsp+38h] [rbp-60h] BYREF
  __int64 v53; // [rsp+40h] [rbp-58h]
  __int64 v54; // [rsp+48h] [rbp-50h]
  _UNKNOWN *retaddr; // [rsp+98h] [rbp+0h]

  v50 = 0;
  result = SkmiLockImageShared(a1);
  if ( (int)result >= 0 )
  {
    SkmiPushDataTraceState(a1, &v50);
    v12 = SkmiLockImagePage(v11, (unsigned int)a2, a3, 1);
    v15 = (unsigned int)v12;
    if ( v12 >= 0 )
    {
      v52 = BugCheckParameter3;
      v16 = 3;
      if ( !a4 )
        v16 = 5;
      SkmiClaimPhysicalPages((ULONG_PTR)&v52, 1, v16);
      v17 = ((__int64 (*)(void))SkmiGetHyperspacePte)();
      v18 = 0;
      v54 = v17 << 25 >> 16;
      v52 = 0;
      v19 = (a3 << 12) & 0xFFFFFFFFFF000LL ^ 0x8000000000000021uLL;
      PteTrace = SkmiGetPteTrace(0, v17, 0, ((_DWORD)a3 << 12) ^ 0x21u, *(_QWORD *)v17);
      v22 = 0;
      v23 = PteTrace;
      if ( PteTrace )
      {
        v24 = (PVOID *)(PteTrace + 32);
        memset_0((void *)(PteTrace + 32), 0, 0x40u);
        v22 = 0;
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          if ( KeGetPcr()->NtTib.StackBase )
          {
            v26 = RtlCaptureStackBackTrace(v25, 8u, v24, &BackTraceHash);
            v22 = 0;
            if ( !v26 )
            {
              *(_QWORD *)(v23 + 40) = retaddr;
              *v24 = (PVOID)SkmiGetInstructionPointer(v27, v21);
            }
          }
        }
        v18 = v52;
      }
      v28 = 0xFFFFF6FB7DBED800uLL;
      if ( (unsigned __int64)v17 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v17 < 0xFFFFF6FB7DBED800uLL )
      {
        StackBase = KeGetPcr()->NtTib.StackBase;
        v28 = StackBase ? StackBase[10] : v22;
        v21 = *(_QWORD *)(v28 + 232);
        if ( v21 )
        {
          v28 = (unsigned int)SkiKvaShadowMode;
          *(_QWORD *)(v21 + 8 * ((v17 >> 3) & 0x1FF)) = v19;
          if ( (_DWORD)v28 != 2 )
            v19 |= 0x8000000000000000uLL;
        }
      }
      *(_QWORD *)v17 = v19;
      HyperspacePte = SkmiGetHyperspacePte(v28, v21, v22, 0x8000000000000000uLL);
      v52 = ((HyperspacePte << 25) - v18) >> 16;
      v31 = (BugCheckParameter3 << 12) & 0xFFFFFFFFFF000LL ^ 0x8000000000000063uLL;
      v32 = SkmiGetPteTrace(0, HyperspacePte, 0, ((_DWORD)BugCheckParameter3 << 12) ^ 0x63u, *(_QWORD *)HyperspacePte);
      v34 = 0;
      v53 = v32;
      if ( v32 )
      {
        v35 = (PVOID *)(v32 + 32);
        memset_0((void *)(v32 + 32), 0, 0x40u);
        v34 = 0;
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          v36 = KeGetPcr()->NtTib.StackBase;
          if ( v36 )
          {
            v37 = RtlCaptureStackBackTrace((ULONG)v36, 8u, v35, &BackTraceHash);
            v34 = 0;
            if ( !v37 )
            {
              v39 = v53;
              *(_QWORD *)(v53 + 40) = retaddr;
              *v35 = (PVOID)SkmiGetInstructionPointer(v39, v38);
            }
          }
        }
        v33 = v52;
      }
      if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
        && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
      {
        v40 = KeGetPcr()->NtTib.StackBase;
        v41 = v40 ? v40[10] : v34;
        v42 = *(_QWORD *)(v41 + 232);
        if ( v42 )
        {
          v43 = SkiKvaShadowMode;
          *(_QWORD *)(v42 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v31;
          if ( v43 != 2 )
            v31 |= 0x8000000000000000uLL;
        }
      }
      v44 = v54;
      *(_QWORD *)HyperspacePte = v31;
      SkeCopyPage(v33, v44, v34);
      if ( a3 > 0xFFFFFFFFFFLL )
        __fastfail(0x3Fu);
      v45 = *(_QWORD *)(a1 + 48);
      v46 = v45 - *(_QWORD *)(a1 + 40);
      v47 = (_QWORD *)(8 * a3 - 0x180000000000LL);
      if ( (*v47 & 0x1000000000000LL) != 0 )
      {
        v48 = SkmiLockImageIndex((*v47 >> 20) & 0xFFFFFFFLL);
        if ( (*(_DWORD *)v48 & 0x100000) != 0 )
          v46 = *(_QWORD *)(v48 + 32);
        SkmiUnlockImageIndex((*v47 >> 20) & 0xFFFFFFFLL);
      }
      else
      {
        v47 = 0;
      }
      if ( a6 != v45 )
        SkmiApplyRelocations(a1, a2, v52, a6 - v45, v46, a6 < 0xFFFF800000000000uLL ? 2 : 10);
      SkmiReleaseHyperspacePte(v17);
      SkmiReleaseHyperspacePte(HyperspacePte);
      if ( !a4 && (SkmiFlags & 0x10) != 0 && (*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * a2) & 0x40) != 0 )
        SkmiProtectSinglePage(BugCheckParameter3);
      SkmiUnlockImagePage(a1, (unsigned int)a2, v47);
      v15 = 0;
    }
    SkmiPopDataTraceState(v50, v15, v13, v14);
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 136));
    return v49;
  }
  return result;
}

```

## disassembly

```asm
0x14005fc00  mov     [rsp+arg_18], r9
0x14005fc05  push    rbx
0x14005fc06  push    rbp
0x14005fc07  push    rsi
0x14005fc08  push    rdi
0x14005fc09  push    r12
0x14005fc0b  push    r13
0x14005fc0d  push    r14
0x14005fc0f  push    r15
0x14005fc11  sub     rsp, 58h
0x14005fc15  xor     esi, esi
0x14005fc17  mov     rbx, r9
0x14005fc1a  mov     [rsp+98h+var_68], esi
0x14005fc1e  mov     r13, r8
0x14005fc21  mov     r12, rdx
0x14005fc24  mov     rdi, rcx
0x14005fc27  call    SkmiLockImageShared
0x14005fc2c  test    eax, eax
0x14005fc2e  js      loc_140060031
0x14005fc34  lea     rdx, [rsp+98h+var_68]
0x14005fc39  mov     rcx, rdi
0x14005fc3c  call    SkmiPushDataTraceState
0x14005fc41  lea     r14d, [rsi+1]
0x14005fc45  mov     r8, r13
0x14005fc48  mov     r9d, r14d
0x14005fc4b  mov     edx, r12d
0x14005fc4e  call    SkmiLockImagePage
0x14005fc53  mov     edx, eax
0x14005fc55  test    eax, eax
0x14005fc57  js      loc_14006001F
0x14005fc5d  mov     rbp, [rsp+98h+BugCheckParameter3]
0x14005fc65  mov     edx, r14d
0x14005fc68  mov     [rsp+98h+var_60], rbp
0x14005fc6d  lea     rcx, [rsp+98h+var_60]
0x14005fc72  lea     r8d, [rsi+3]
0x14005fc76  test    rbx, rbx
0x14005fc79  jnz     short loc_14005FC7F
0x14005fc7b  lea     r8d, [rsi+5]
0x14005fc7f  call    SkmiClaimPhysicalPages
0x14005fc84  call    SkmiGetHyperspacePte
0x14005fc89  mov     r15, rax
0x14005fc8c  mov     rsi, 0FFFFF68000000000h
0x14005fc96  shl     rax, 19h
0x14005fc9a  mov     rbx, r13
0x14005fc9d  shl     rsi, 19h
0x14005fca1  xor     r8d, r8d
0x14005fca4  sub     rax, rsi
0x14005fca7  shl     rbx, 0Ch
0x14005fcab  sar     rax, 10h
0x14005fcaf  mov     rdx, r15
0x14005fcb2  mov     [rsp+98h+var_50], rax
0x14005fcb7  xor     ecx, ecx
0x14005fcb9  mov     rax, 0FFFFFFFFFF000h
0x14005fcc3  mov     [rsp+98h+var_60], rsi
0x14005fcc8  and     rbx, rax
0x14005fccb  mov     rax, 8000000000000021h
0x14005fcd5  xor     rbx, rax
0x14005fcd8  mov     rax, [r15]
0x14005fcdb  mov     r9, rbx
0x14005fcde  mov     [rsp+98h+var_78], rax
0x14005fce3  call    SkmiGetPteTrace
0x14005fce8  xor     r8d, r8d
0x14005fceb  mov     r14, rax
0x14005fcee  test    rax, rax
0x14005fcf1  jz      short loc_14005FD55
0x14005fcf3  xor     edx, edx; Val
0x14005fcf5  lea     rsi, [rax+20h]
0x14005fcf9  mov     rcx, rsi; void *
0x14005fcfc  lea     r8d, [rdx+40h]; Size
0x14005fd00  call    memset_0
0x14005fd05  xor     r8d, r8d
0x14005fd08  test    cs:SkmiFlags, 400000h
0x14005fd12  jz      short loc_14005FD50
0x14005fd14  mov     rax, gs:8
0x14005fd1d  test    rax, rax
0x14005fd20  jz      short loc_14005FD50
0x14005fd22  lea     r9, [rsp+98h+BackTraceHash]; BackTraceHash
0x14005fd27  mov     r8, rsi; BackTrace
0x14005fd2a  mov     edx, 8; FramesToCapture
0x14005fd2f  call    RtlCaptureStackBackTrace
0x14005fd34  xor     r8d, r8d
0x14005fd37  test    ax, ax
0x14005fd3a  jnz     short loc_14005FD50
0x14005fd3c  mov     rax, [rsp+98h]
0x14005fd44  mov     [r14+28h], rax
0x14005fd48  call    SkmiGetInstructionPointer
0x14005fd4d  mov     [rsi], rax
0x14005fd50  mov     rsi, [rsp+98h+var_60]
0x14005fd55  mov     rax, 0FFFFF6FB7DBED000h
0x14005fd5f  mov     rax, rax
0x14005fd62  mov     rcx, 0FFFFF6FB7DBED800h
0x14005fd6c  mov     r9, 8000000000000000h
0x14005fd76  cmp     r15, rax
0x14005fd79  jb      short loc_14005FDC9
0x14005fd7b  mov     rax, rcx
0x14005fd7e  cmp     r15, rax
0x14005fd81  jnb     short loc_14005FDC9
0x14005fd83  mov     rax, gs:8
0x14005fd8c  test    rax, rax
0x14005fd8f  jz      short loc_14005FD97
0x14005fd91  mov     rcx, [rax+50h]
0x14005fd95  jmp     short loc_14005FD9A
0x14005fd97  mov     rcx, r8
0x14005fd9a  mov     rdx, [rcx+0E8h]
0x14005fda1  test    rdx, rdx
0x14005fda4  jz      short loc_14005FDC9
0x14005fda6  mov     ecx, cs:SkiKvaShadowMode
0x14005fdac  mov     rax, r15
0x14005fdaf  sar     rax, 3
0x14005fdb3  and     eax, 1FFh
0x14005fdb8  mov     [rdx+rax*8], rbx
0x14005fdbc  cmp     ecx, 2
0x14005fdbf  jz      short loc_14005FDC9
0x14005fdc1  test    bl, 1
0x14005fdc4  jz      short loc_14005FDC9
0x14005fdc6  or      rbx, r9
0x14005fdc9  mov     [r15], rbx
0x14005fdcc  call    SkmiGetHyperspacePte
0x14005fdd1  mov     r14, rax
0x14005fdd4  mov     r10, rax
0x14005fdd7  mov     rax, 0FFFFFFFFFF000h
0x14005fde1  shl     r10, 19h
0x14005fde5  mov     rbx, rbp
0x14005fde8  sub     r10, rsi
0x14005fdeb  shl     rbx, 0Ch
0x14005fdef  xor     r8d, r8d
0x14005fdf2  and     rbx, rax
0x14005fdf5  sar     r10, 10h
0x14005fdf9  mov     rax, 8000000000000063h
0x14005fe03  mov     [rsp+98h+var_60], r10
0x14005fe08  xor     rbx, rax
0x14005fe0b  mov     rdx, r14
0x14005fe0e  mov     rax, [r14]
0x14005fe11  mov     r9, rbx
0x14005fe14  xor     ecx, ecx
0x14005fe16  mov     [rsp+98h+var_78], rax
0x14005fe1b  call    SkmiGetPteTrace
0x14005fe20  xor     r8d, r8d
0x14005fe23  mov     [rsp+98h+var_58], rax
0x14005fe28  test    rax, rax
0x14005fe2b  jz      short loc_14005FE94
0x14005fe2d  xor     edx, edx; Val
0x14005fe2f  lea     rsi, [rax+20h]
0x14005fe33  mov     rcx, rsi; void *
0x14005fe36  lea     r8d, [rdx+40h]; Size
0x14005fe3a  call    memset_0
0x14005fe3f  xor     r8d, r8d
0x14005fe42  test    cs:SkmiFlags, 400000h
0x14005fe4c  jz      short loc_14005FE8F
0x14005fe4e  mov     rcx, gs:8; FramesToSkip
0x14005fe57  test    rcx, rcx
0x14005fe5a  jz      short loc_14005FE8F
0x14005fe5c  lea     r9, [rsp+98h+BackTraceHash]; BackTraceHash
0x14005fe61  mov     r8, rsi; BackTrace
0x14005fe64  mov     edx, 8; FramesToCapture
0x14005fe69  call    RtlCaptureStackBackTrace
0x14005fe6e  xor     r8d, r8d
0x14005fe71  test    ax, ax
0x14005fe74  jnz     short loc_14005FE8F
0x14005fe76  mov     rax, [rsp+98h]
0x14005fe7e  mov     rcx, [rsp+98h+var_58]
0x14005fe83  mov     [rcx+28h], rax
0x14005fe87  call    SkmiGetInstructionPointer
0x14005fe8c  mov     [rsi], rax
0x14005fe8f  mov     r10, [rsp+98h+var_60]
0x14005fe94  mov     rax, 0FFFFF6FB7DBED000h
0x14005fe9e  mov     rax, rax
0x14005fea1  cmp     r14, rax
0x14005fea4  jb      short loc_14005FF08
0x14005fea6  mov     rax, 0FFFFF6FB7DBED800h
0x14005feb0  mov     rax, rax
0x14005feb3  cmp     r14, rax
0x14005feb6  jnb     short loc_14005FF08
0x14005feb8  mov     rax, gs:8
0x14005fec1  test    rax, rax
0x14005fec4  jz      short loc_14005FECC
0x14005fec6  mov     rcx, [rax+50h]
0x14005feca  jmp     short loc_14005FECF
0x14005fecc  mov     rcx, r8
0x14005fecf  mov     rdx, [rcx+0E8h]
0x14005fed6  test    rdx, rdx
0x14005fed9  jz      short loc_14005FF08
0x14005fedb  mov     ecx, cs:SkiKvaShadowMode
0x14005fee1  mov     rax, r14
0x14005fee4  sar     rax, 3
0x14005fee8  and     eax, 1FFh
0x14005feed  mov     [rdx+rax*8], rbx
0x14005fef1  cmp     ecx, 2
0x14005fef4  jz      short loc_14005FF08
0x14005fef6  test    bl, 1
0x14005fef9  jz      short loc_14005FF08
0x14005fefb  mov     rax, 8000000000000000h
0x14005ff05  or      rbx, rax
0x14005ff08  mov     rdx, [rsp+98h+var_50]
0x14005ff0d  mov     rcx, r10
0x14005ff10  mov     [r14], rbx
0x14005ff13  call    SkeCopyPage
0x14005ff18  mov     rcx, 0FFFFEFFFFFFFFFFFh
0x14005ff22  mov     rdx, 0FFFFE80000000000h
0x14005ff2c  mov     rax, rdx
0x14005ff2f  sub     rcx, rax
0x14005ff32  sar     rcx, 3
0x14005ff36  cmp     r13, rcx
0x14005ff39  jbe     short loc_14005FF42
0x14005ff3b  mov     ecx, 3Fh ; '?'
0x14005ff40  int     29h; Win8: RtlFailFast(ecx)
0x14005ff42  mov     r11, [rdi+30h]
0x14005ff46  mov     rsi, r11
0x14005ff49  sub     rsi, [rdi+28h]
0x14005ff4d  mov     rax, rdx
0x14005ff50  lea     rbx, [rax+r13*8]
0x14005ff54  mov     rcx, [rbx]
0x14005ff57  bt      rcx, 30h ; '0'
0x14005ff5c  jnb     short loc_14005FF91
0x14005ff5e  shr     rcx, 14h
0x14005ff62  mov     r13d, 0FFFFFFFh
0x14005ff68  and     ecx, r13d
0x14005ff6b  call    SkmiLockImageIndex
0x14005ff70  test    dword ptr [rax], 100000h
0x14005ff76  jz      short loc_14005FF80
0x14005ff78  mov     r11, [rax+18h]
0x14005ff7c  mov     rsi, [rax+20h]
0x14005ff80  mov     rcx, [rbx]
0x14005ff83  shr     rcx, 14h
0x14005ff87  and     ecx, r13d
0x14005ff8a  call    SkmiUnlockImageIndex
0x14005ff8f  jmp     short loc_14005FF93
0x14005ff91  xor     ebx, ebx
0x14005ff93  mov     r9, [rsp+98h+arg_28]
0x14005ff9b  cmp     r9, r11
0x14005ff9e  jz      short loc_14005FFD1
0x14005ffa0  mov     r8, [rsp+98h+var_60]
0x14005ffa5  mov     rax, 0FFFF800000000000h
0x14005ffaf  cmp     r9, rax
0x14005ffb2  mov     edx, r12d
0x14005ffb5  mov     rcx, rdi
0x14005ffb8  sbb     eax, eax
0x14005ffba  sub     r9, r11
0x14005ffbd  and     eax, 0FFFFFFF8h
0x14005ffc0  add     eax, 0Ah
0x14005ffc3  mov     [rsp+98h+var_70], eax
0x14005ffc7  mov     [rsp+98h+var_78], rsi
0x14005ffcc  call    SkmiApplyRelocations
0x14005ffd1  mov     rcx, r15
0x14005ffd4  call    SkmiReleaseHyperspacePte
0x14005ffd9  mov     rcx, r14
0x14005ffdc  call    SkmiReleaseHyperspacePte
0x14005ffe1  cmp     [rsp+98h+arg_18], 0
0x14005ffea  jnz     short loc_14006000F
0x14005ffec  mov     eax, cs:SkmiFlags
0x14005fff2  test    al, 10h
0x14005fff4  jz      short loc_14006000F
0x14005fff6  mov     rax, [rdi+8]
0x14005fffa  mov     rax, [rax+r12*8]
0x14005fffe  test    al, 40h
0x140060000  jz      short loc_14006000F
0x140060002  mov     edx, 2
0x140060007  mov     rcx, rbp; BugCheckParameter3
0x14006000a  call    SkmiProtectSinglePage
0x14006000f  mov     r8, rbx
0x140060012  mov     edx, r12d
0x140060015  mov     rcx, rdi
0x140060018  call    SkmiUnlockImagePage
0x14006001d  xor     edx, edx
0x14006001f  mov     ecx, [rsp+98h+var_68]
0x140060023  call    SkmiPopDataTraceState
0x140060028  lock dec dword ptr [rdi+88h]
0x14006002f  mov     eax, edx
0x140060031  add     rsp, 58h
0x140060035  pop     r15
0x140060037  pop     r14
0x140060039  pop     r13
0x14006003b  pop     r12
0x14006003d  pop     rdi
0x14006003e  pop     rsi
0x14006003f  pop     rbp
0x140060040  pop     rbx
0x140060041  retn
```
