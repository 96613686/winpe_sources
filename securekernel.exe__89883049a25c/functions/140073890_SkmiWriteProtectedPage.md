# SkmiWriteProtectedPage

- ea: `0x140073890`
- end: `0x140073d16`
- name: `SkmiWriteProtectedPage`
- size: `1158`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x140003780`
- `0x140009940`
- `0x14000b980`
- `0x14000c8d0`
- `0x140014c80`
- `0x14002aeac`
- `0x14002b534`
- `0x14005f16c`
- `0x140071f44`
- `0x140073890`
- `0x140081290`
- `0x1400f9780`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiWriteProtectedPage(__int64 *a1)
{
  _QWORD *v1; // rdx
  bool v2; // zf
  __int64 v4; // rcx
  __int64 result; // rax
  ULONG_PTR v6; // rbp
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 HyperspacePte; // rsi
  unsigned __int64 v12; // rbx
  __int64 PteTrace; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r9
  __int64 v17; // r15
  PVOID *v18; // rdi
  _QWORD *StackBase; // rax
  __int64 v20; // rdi
  unsigned __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // r13
  PVOID *v24; // r15
  PVOID v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  _QWORD *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rdx
  int v31; // ecx
  __int64 v32; // rax
  int v33; // r9d
  __int64 v34; // r14
  PVOID *v35; // rbx
  PVOID v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  _QWORD *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rax
  int v43; // r9d
  __int64 v44; // r14
  PVOID *v45; // rbx
  PVOID v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  _QWORD *v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rdx
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]
  ULONG BackTraceHash; // [rsp+80h] [rbp+8h] BYREF

  v1 = a1 + 1;
  v2 = a1[2] == 0;
  v4 = *a1;
  if ( v2 )
    LODWORD(result) = SkmiCanWriteProtectedNormalKernelPage(v4, *v1);
  else
    LODWORD(result) = SkmiCanWriteImagePage(v4, v1);
  if ( (int)result < 0 )
    return (int)result;
  v6 = (unsigned __int64)a1[4] >> 12;
  if ( (unsigned int)SkmiIncrementSharedPageReferenceCount(v6) )
  {
    HyperspacePte = SkmiGetHyperspacePte(v8, v7, v9, v10);
    v12 = (v6 << 12) & 0xFFFFFFFFFF000LL ^ 0x8000000000000021uLL;
    PteTrace = SkmiGetPteTrace(0, HyperspacePte, 0, ((_DWORD)v6 << 12) ^ 0x21u, *(_QWORD *)HyperspacePte);
    v17 = PteTrace;
    if ( PteTrace )
    {
      v18 = (PVOID *)(PteTrace + 32);
      memset_0((void *)(PteTrace + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0
        && KeGetPcr()->NtTib.StackBase
        && !RtlCaptureStackBackTrace(v15, 8u, v18, &BackTraceHash) )
      {
        *(_QWORD *)(v17 + 40) = retaddr;
        *v18 = (PVOID)SkmiGetInstructionPointer(v15, v14);
      }
    }
    if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
      && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
    {
      StackBase = KeGetPcr()->NtTib.StackBase;
      v15 = StackBase ? StackBase[10] : 0LL;
      v14 = *(_QWORD *)(v15 + 232);
      if ( v14 )
      {
        v15 = (unsigned int)SkiKvaShadowMode;
        *(_QWORD *)(v14 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v12;
        if ( (_DWORD)v15 != 2 )
          v12 |= 0x8000000000000000uLL;
      }
    }
    *(_QWORD *)HyperspacePte = v12;
    v20 = SkmiGetHyperspacePte(v15, v14, 0x8000000000000000uLL, v16);
    v21 = (*a1 << 12) & 0xFFFFFFFFFF000LL ^ 0x8000000000000063uLL;
    v22 = SkmiGetPteTrace(0, v20, 0, (*(_DWORD *)a1 << 12) ^ 0x63u, *(_QWORD *)v20);
    v23 = v22;
    if ( v22 )
    {
      v24 = (PVOID *)(v22 + 32);
      memset_0((void *)(v22 + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v25 = KeGetPcr()->NtTib.StackBase;
        if ( v25 )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)v25, 8u, v24, &BackTraceHash) )
          {
            *(_QWORD *)(v23 + 40) = retaddr;
            *v24 = (PVOID)SkmiGetInstructionPointer(v27, v26);
          }
        }
      }
    }
    if ( (unsigned __int64)v20 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v20 < 0xFFFFF6FB7DBED800uLL )
    {
      v28 = KeGetPcr()->NtTib.StackBase;
      v29 = v28 ? v28[10] : 0LL;
      v30 = *(_QWORD *)(v29 + 232);
      if ( v30 )
      {
        v31 = SkiKvaShadowMode;
        *(_QWORD *)(v30 + 8 * ((v20 >> 3) & 0x1FF)) = v21;
        if ( v31 != 2 && (v21 & 1) != 0 )
          v21 |= 0x8000000000000000uLL;
      }
    }
    *(_QWORD *)v20 = v21;
    memmove(
      (void *)(*((unsigned int *)a1 + 6) + (v20 << 25 >> 16)),
      (const void *)((a1[4] & 0xFFF) + (HyperspacePte << 25 >> 16)),
      *((unsigned int *)a1 + 7));
    v32 = SkmiGetPteTrace(0, HyperspacePte, 0, 0, *(_QWORD *)HyperspacePte);
    v34 = v32;
    if ( v32 )
    {
      v35 = (PVOID *)(v32 + 32);
      memset_0((void *)(v32 + 32), 0, (unsigned int)(v33 + 64));
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v36 = KeGetPcr()->NtTib.StackBase;
        if ( v36 )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)v36, 8u, v35, &BackTraceHash) )
          {
            *(_QWORD *)(v34 + 40) = retaddr;
            *v35 = (PVOID)SkmiGetInstructionPointer(v38, v37);
          }
        }
      }
    }
    if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
      && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
    {
      v39 = KeGetPcr()->NtTib.StackBase;
      v40 = v39 ? v39[10] : 0LL;
      v41 = *(_QWORD *)(v40 + 232);
      if ( v41 )
        *(_QWORD *)(v41 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = 0;
    }
    *(_QWORD *)HyperspacePte = 0;
    v42 = SkmiGetPteTrace(0, v20, 0, 0, *(_QWORD *)v20);
    v44 = v42;
    if ( v42 )
    {
      v45 = (PVOID *)(v42 + 32);
      memset_0((void *)(v42 + 32), 0, (unsigned int)(v43 + 64));
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v46 = KeGetPcr()->NtTib.StackBase;
        if ( v46 )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)v46, 8u, v45, &BackTraceHash) )
          {
            *(_QWORD *)(v44 + 40) = retaddr;
            *v45 = (PVOID)SkmiGetInstructionPointer(v48, v47);
          }
        }
      }
    }
    if ( (unsigned __int64)v20 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v20 < 0xFFFFF6FB7DBED800uLL )
    {
      v49 = KeGetPcr()->NtTib.StackBase;
      if ( v49 )
        v50 = v49[10];
      else
        v50 = 0;
      v51 = *(_QWORD *)(v50 + 232);
      if ( v51 )
        *(_QWORD *)(v51 + 8 * ((v20 >> 3) & 0x1FF)) = 0;
    }
    *(_QWORD *)v20 = 0;
    SkmiReleaseHyperspacePte(HyperspacePte);
    SkmiReleaseHyperspacePte(v20);
    SkmiDecrementPageReferenceCount(v6);
    return 0;
  }
  else
  {
    SKMI_PAGE_SECURITY(304, v6, 0, 0);
    return -1073741819;
  }
}

```

## disassembly

```asm
0x140073890  push    rbx
0x140073892  push    rbp
0x140073893  push    rsi
0x140073894  push    rdi
0x140073895  push    r12
0x140073897  push    r13
0x140073899  push    r14
0x14007389b  push    r15
0x14007389d  sub     rsp, 38h
0x1400738a1  xor     r12d, r12d
0x1400738a4  lea     rdx, [rcx+8]
0x1400738a8  cmp     [rcx+10h], r12
0x1400738ac  mov     r14, rcx
0x1400738af  mov     rcx, [rcx]
0x1400738b2  jnz     short loc_1400738BE
0x1400738b4  mov     rdx, [rdx]
0x1400738b7  call    SkmiCanWriteProtectedNormalKernelPage
0x1400738bc  jmp     short loc_1400738C3
0x1400738be  call    SkmiCanWriteImagePage
0x1400738c3  test    eax, eax
0x1400738c5  jns     short loc_1400738CE
0x1400738c7  cdqe
0x1400738c9  jmp     loc_140073D04
0x1400738ce  mov     rbp, [r14+20h]
0x1400738d2  mov     edx, 1
0x1400738d7  shr     rbp, 0Ch
0x1400738db  mov     rcx, rbp; BugCheckParameter3
0x1400738de  call    SkmiIncrementSharedPageReferenceCount
0x1400738e3  test    eax, eax
0x1400738e5  jnz     short loc_140073906
0x1400738e7  xor     r9d, r9d
0x1400738ea  xor     r8d, r8d
0x1400738ed  mov     rdx, rbp
0x1400738f0  mov     ecx, 130h
0x1400738f5  call    SKMI_PAGE_SECURITY
0x1400738fa  mov     rax, 0FFFFFFFFC0000005h
0x140073901  jmp     loc_140073D04
0x140073906  call    SkmiGetHyperspacePte
0x14007390b  mov     rsi, rax
0x14007390e  mov     rbx, rbp
0x140073911  shl     rbx, 0Ch
0x140073915  mov     rax, 8000000000000021h
0x14007391f  mov     r13, 0FFFFFFFFFF000h
0x140073929  xor     r8d, r8d
0x14007392c  and     rbx, r13
0x14007392f  mov     rdx, rsi
0x140073932  mov     rcx, [rsi]
0x140073935  xor     rbx, rax
0x140073938  mov     [rsp+78h+var_58], rcx
0x14007393d  mov     r9, rbx
0x140073940  xor     ecx, ecx
0x140073942  call    SkmiGetPteTrace
0x140073947  mov     r15, rax
0x14007394a  test    rax, rax
0x14007394d  jz      short loc_1400739A6
0x14007394f  xor     edx, edx; Val
0x140073951  lea     rdi, [rax+20h]
0x140073955  mov     rcx, rdi; void *
0x140073958  lea     r8d, [rdx+40h]; Size
0x14007395c  call    memset_0
0x140073961  test    cs:SkmiFlags, 400000h
0x14007396b  jz      short loc_1400739A6
0x14007396d  mov     rax, gs:8
0x140073976  test    rax, rax
0x140073979  jz      short loc_1400739A6
0x14007397b  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x140073983  mov     r8, rdi; BackTrace
0x140073986  mov     edx, 8; FramesToCapture
0x14007398b  call    RtlCaptureStackBackTrace
0x140073990  test    ax, ax
0x140073993  jnz     short loc_1400739A6
0x140073995  mov     rax, [rsp+78h]
0x14007399a  mov     [r15+28h], rax
0x14007399e  call    SkmiGetInstructionPointer
0x1400739a3  mov     [rdi], rax
0x1400739a6  mov     rax, 0FFFFF6FB7DBED000h
0x1400739b0  mov     rax, rax
0x1400739b3  mov     r15, 0FFFFF6FB7DBED800h
0x1400739bd  mov     r8, 8000000000000000h
0x1400739c7  cmp     rsi, rax
0x1400739ca  jb      short loc_140073A1A
0x1400739cc  mov     rax, r15
0x1400739cf  cmp     rsi, rax
0x1400739d2  jnb     short loc_140073A1A
0x1400739d4  mov     rax, gs:8
0x1400739dd  test    rax, rax
0x1400739e0  jz      short loc_1400739E8
0x1400739e2  mov     rcx, [rax+50h]
0x1400739e6  jmp     short loc_1400739EB
0x1400739e8  mov     rcx, r12
0x1400739eb  mov     rdx, [rcx+0E8h]
0x1400739f2  test    rdx, rdx
0x1400739f5  jz      short loc_140073A1A
0x1400739f7  mov     ecx, cs:SkiKvaShadowMode
0x1400739fd  mov     rax, rsi
0x140073a00  sar     rax, 3
0x140073a04  and     eax, 1FFh
0x140073a09  mov     [rdx+rax*8], rbx
0x140073a0d  cmp     ecx, 2
0x140073a10  jz      short loc_140073A1A
0x140073a12  test    bl, 1
0x140073a15  jz      short loc_140073A1A
0x140073a17  or      rbx, r8
0x140073a1a  mov     [rsi], rbx
0x140073a1d  call    SkmiGetHyperspacePte
0x140073a22  mov     rbx, [r14]
0x140073a25  mov     rdi, rax
0x140073a28  shl     rbx, 0Ch
0x140073a2c  mov     rax, 8000000000000063h
0x140073a36  and     rbx, r13
0x140073a39  xor     r8d, r8d
0x140073a3c  xor     rbx, rax
0x140073a3f  mov     rdx, rdi
0x140073a42  mov     rcx, [rdi]
0x140073a45  mov     r9, rbx
0x140073a48  mov     [rsp+78h+var_58], rcx
0x140073a4d  xor     ecx, ecx
0x140073a4f  call    SkmiGetPteTrace
0x140073a54  mov     r13, rax
0x140073a57  test    rax, rax
0x140073a5a  jz      short loc_140073ABD
0x140073a5c  xor     edx, edx; Val
0x140073a5e  lea     r15, [rax+20h]
0x140073a62  mov     rcx, r15; void *
0x140073a65  lea     r8d, [rdx+40h]; Size
0x140073a69  call    memset_0
0x140073a6e  test    cs:SkmiFlags, 400000h
0x140073a78  jz      short loc_140073AB3
0x140073a7a  mov     rcx, gs:8; FramesToSkip
0x140073a83  test    rcx, rcx
0x140073a86  jz      short loc_140073AB3
0x140073a88  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x140073a90  mov     r8, r15; BackTrace
0x140073a93  mov     edx, 8; FramesToCapture
0x140073a98  call    RtlCaptureStackBackTrace
0x140073a9d  test    ax, ax
0x140073aa0  jnz     short loc_140073AB3
0x140073aa2  mov     rax, [rsp+78h]
0x140073aa7  mov     [r13+28h], rax
0x140073aab  call    SkmiGetInstructionPointer
0x140073ab0  mov     [r15], rax
0x140073ab3  mov     r15, 0FFFFF6FB7DBED800h
0x140073abd  mov     r13, 0FFFFF6FB7DBED000h
0x140073ac7  mov     rax, r13
0x140073aca  cmp     rdi, rax
0x140073acd  jb      short loc_140073B27
0x140073acf  mov     rax, r15
0x140073ad2  cmp     rdi, rax
0x140073ad5  jnb     short loc_140073B27
0x140073ad7  mov     rax, gs:8
0x140073ae0  test    rax, rax
0x140073ae3  jz      short loc_140073AEB
0x140073ae5  mov     rcx, [rax+50h]
0x140073ae9  jmp     short loc_140073AEE
0x140073aeb  mov     rcx, r12
0x140073aee  mov     rdx, [rcx+0E8h]
0x140073af5  test    rdx, rdx
0x140073af8  jz      short loc_140073B27
0x140073afa  mov     ecx, cs:SkiKvaShadowMode
0x140073b00  mov     rax, rdi
0x140073b03  sar     rax, 3
0x140073b07  and     eax, 1FFh
0x140073b0c  mov     [rdx+rax*8], rbx
0x140073b10  cmp     ecx, 2
0x140073b13  jz      short loc_140073B27
0x140073b15  test    bl, 1
0x140073b18  jz      short loc_140073B27
0x140073b1a  mov     rax, 8000000000000000h
0x140073b24  or      rbx, rax
0x140073b27  mov     [rdi], rbx
0x140073b2a  mov     r9, 0FFFFF68000000000h
0x140073b34  mov     eax, [r14+20h]
0x140073b38  mov     rdx, rsi
0x140073b3b  mov     r8d, [r14+1Ch]; Size
0x140073b3f  and     eax, 0FFFh
0x140073b44  shl     rdx, 19h
0x140073b48  mov     rcx, rdi
0x140073b4b  shl     rcx, 19h
0x140073b4f  shl     r9, 19h
0x140073b53  sub     rdx, r9
0x140073b56  sub     rcx, r9
0x140073b59  sar     rdx, 10h
0x140073b5d  add     rdx, rax; Src
0x140073b60  sar     rcx, 10h
0x140073b64  mov     eax, [r14+18h]
0x140073b68  add     rcx, rax; void *
0x140073b6b  call    memmove
0x140073b70  mov     rax, [rsi]
0x140073b73  xor     r9d, r9d
0x140073b76  xor     r8d, r8d
0x140073b79  mov     [rsp+78h+var_58], rax
0x140073b7e  mov     rdx, rsi
0x140073b81  xor     ecx, ecx
0x140073b83  call    SkmiGetPteTrace
0x140073b88  mov     r14, rax
0x140073b8b  test    rax, rax
0x140073b8e  jz      short loc_140073BE7
0x140073b90  lea     rbx, [rax+20h]
0x140073b94  xor     edx, edx; Val
0x140073b96  mov     rcx, rbx; void *
0x140073b99  lea     r8d, [r9+40h]; Size
0x140073b9d  call    memset_0
0x140073ba2  test    cs:SkmiFlags, 400000h
0x140073bac  jz      short loc_140073BE7
0x140073bae  mov     rcx, gs:8; FramesToSkip
0x140073bb7  test    rcx, rcx
0x140073bba  jz      short loc_140073BE7
0x140073bbc  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x140073bc4  mov     r8, rbx; BackTrace
0x140073bc7  mov     edx, 8; FramesToCapture
0x140073bcc  call    RtlCaptureStackBackTrace
0x140073bd1  test    ax, ax
0x140073bd4  jnz     short loc_140073BE7
0x140073bd6  mov     rax, [rsp+78h]
0x140073bdb  mov     [r14+28h], rax
0x140073bdf  call    SkmiGetInstructionPointer
0x140073be4  mov     [rbx], rax
0x140073be7  mov     rax, r13
0x140073bea  cmp     rsi, rax
0x140073bed  jb      short loc_140073C2A
0x140073bef  mov     rax, r15
0x140073bf2  cmp     rsi, rax
0x140073bf5  jnb     short loc_140073C2A
0x140073bf7  mov     rax, gs:8
0x140073c00  test    rax, rax
0x140073c03  jz      short loc_140073C0B
0x140073c05  mov     rcx, [rax+50h]
0x140073c09  jmp     short loc_140073C0E
0x140073c0b  mov     rcx, r12
0x140073c0e  mov     rdx, [rcx+0E8h]
0x140073c15  test    rdx, rdx
0x140073c18  jz      short loc_140073C2A
0x140073c1a  mov     rax, rsi
0x140073c1d  sar     rax, 3
0x140073c21  and     eax, 1FFh
0x140073c26  mov     [rdx+rax*8], r12
0x140073c2a  mov     [rsi], r12
0x140073c2d  xor     r9d, r9d
0x140073c30  mov     rax, [rdi]
0x140073c33  xor     r8d, r8d
0x140073c36  mov     rdx, rdi
0x140073c39  mov     [rsp+78h+var_58], rax
0x140073c3e  xor     ecx, ecx
0x140073c40  call    SkmiGetPteTrace
0x140073c45  mov     r14, rax
0x140073c48  test    rax, rax
0x140073c4b  jz      short loc_140073CA4
0x140073c4d  lea     rbx, [rax+20h]
0x140073c51  xor     edx, edx; Val
0x140073c53  mov     rcx, rbx; void *
0x140073c56  lea     r8d, [r9+40h]; Size
0x140073c5a  call    memset_0
0x140073c5f  test    cs:SkmiFlags, 400000h
0x140073c69  jz      short loc_140073CA4
0x140073c6b  mov     rcx, gs:8; FramesToSkip
0x140073c74  test    rcx, rcx
0x140073c77  jz      short loc_140073CA4
0x140073c79  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x140073c81  mov     r8, rbx; BackTrace
0x140073c84  mov     edx, 8; FramesToCapture
0x140073c89  call    RtlCaptureStackBackTrace
0x140073c8e  test    ax, ax
0x140073c91  jnz     short loc_140073CA4
0x140073c93  mov     rax, [rsp+78h]
0x140073c98  mov     [r14+28h], rax
0x140073c9c  call    SkmiGetInstructionPointer
0x140073ca1  mov     [rbx], rax
0x140073ca4  mov     rax, r13
0x140073ca7  cmp     rdi, rax
0x140073caa  jb      short loc_140073CE7
0x140073cac  mov     rax, r15
0x140073caf  cmp     rdi, rax
0x140073cb2  jnb     short loc_140073CE7
0x140073cb4  mov     rax, gs:8
0x140073cbd  test    rax, rax
0x140073cc0  jz      short loc_140073CC8
0x140073cc2  mov     rcx, [rax+50h]
0x140073cc6  jmp     short loc_140073CCB
0x140073cc8  mov     rcx, r12
0x140073ccb  mov     rdx, [rcx+0E8h]
0x140073cd2  test    rdx, rdx
0x140073cd5  jz      short loc_140073CE7
0x140073cd7  mov     rax, rdi
0x140073cda  sar     rax, 3
0x140073cde  and     eax, 1FFh
0x140073ce3  mov     [rdx+rax*8], r12
0x140073ce7  mov     rcx, rsi
0x140073cea  mov     [rdi], r12
0x140073ced  call    SkmiReleaseHyperspacePte
0x140073cf2  mov     rcx, rdi
0x140073cf5  call    SkmiReleaseHyperspacePte
0x140073cfa  mov     rcx, rbp; BugCheckParameter3
0x140073cfd  call    SkmiDecrementPageReferenceCount
0x140073d02  xor     eax, eax
0x140073d04  add     rsp, 38h
0x140073d08  pop     r15
0x140073d0a  pop     r14
0x140073d0c  pop     r13
0x140073d0e  pop     r12
0x140073d10  pop     rdi
  ... truncated ...
```
