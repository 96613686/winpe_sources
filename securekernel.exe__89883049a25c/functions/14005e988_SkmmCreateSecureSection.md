# SkmmCreateSecureSection

- ea: `0x14005e988`
- end: `0x14005ec07`
- name: `SkmmCreateSecureSection`
- size: `639`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x14005bd70`
- `0x1400b86ec`
- `0x1400b8ad4`

## callees

- `0x140002ef0`
- `0x140003780`
- `0x14002b534`
- `0x14003492c`
- `0x140050b48`
- `0x14005cf30`
- `0x14005e988`
- `0x140081290`
- `0x1400a18a0`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmmCreateSecureSection(
        unsigned __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned int a4,
        __int64 *a5)
{
  _BYTE *StackBase; // rcx
  __int64 result; // rax
  __int64 v11; // r14
  __int64 v12; // rbp
  int SectionProtoPtes; // ebx
  __int64 v14; // rsi
  char ProtectionMask; // al
  int v16; // r8d
  _QWORD *v17; // rdi
  unsigned __int64 v18; // rbx
  __int64 PteTrace; // rax
  __int64 v20; // r13
  PVOID *v21; // r15
  PVOID v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  unsigned __int64 v25; // rax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r8
  int v29; // edx
  ULONG BackTraceHash; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v31[10]; // [rsp+38h] [rbp-50h] BYREF
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+0h]

  StackBase = KeGetPcr()->NtTib.StackBase;
  v31[0] = 0;
  result = SkobCreateObjectEx(StackBase[96], (__int64)&SkmiSectionType, a1, v31);
  if ( (int)result >= 0 )
  {
    v11 = v31[0];
    *(_OWORD *)v31[0] = 0;
    *(_OWORD *)(v11 + 16) = 0;
    *(_QWORD *)(v11 + 32) = 0;
    v12 = (unsigned int)(a3 >> 12) + ((a3 & 0xFFF) != 0);
    if ( a3 > (unsigned __int64)(unsigned int)v12 << 12 )
    {
      SectionProtoPtes = -1073741583;
      goto LABEL_31;
    }
    SectionProtoPtes = SkmiAllocateSectionProtoPtes(v11, (unsigned int)v12);
    if ( SectionProtoPtes < 0 )
    {
LABEL_31:
      SkobDereferenceObject(v11);
      return (unsigned int)SectionProtoPtes;
    }
    else
    {
      v14 = *(_QWORD *)(v11 + 8);
      ProtectionMask = SkmiMakeProtectionMask(a4);
      *(_DWORD *)v11 = v16 ^ ((unsigned __int8)v16 ^ (unsigned __int8)(2 * ProtectionMask)) & 0x1E;
      if ( a2 )
      {
        v17 = (_QWORD *)(((a2 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL);
      }
      else
      {
        memset_0((void *)v14, 0, 8 * v12);
        v17 = 0;
      }
      v18 = 2049;
      for ( v31[0] = 2049; (_DWORD)v12; LODWORD(v12) = v12 - 1 )
      {
        if ( v17 )
        {
          v18 = *v17 & 0xFFFFFFFFFF000LL | v18 & 0xFFF0000000000FFFuLL;
          v31[0] = v18;
          ++v17;
        }
        else
        {
          if ( !(unsigned int)SkmiAllocateZeroedPage(0, v31) )
          {
            SectionProtoPtes = -1073741801;
            goto LABEL_31;
          }
          v18 = v31[0];
        }
        PteTrace = SkmiGetPteTrace(0, v14, 0, v18, *(_QWORD *)v14);
        v20 = PteTrace;
        if ( PteTrace )
        {
          v21 = (PVOID *)(PteTrace + 32);
          memset_0((void *)(PteTrace + 32), 0, 0x40u);
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            v22 = KeGetPcr()->NtTib.StackBase;
            if ( v22 )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)v22, 8u, v21, &BackTraceHash) )
              {
                *(_QWORD *)(v20 + 40) = retaddr;
                *v21 = (PVOID)SkmiGetInstructionPointer(v24, v23);
              }
            }
          }
        }
        v25 = v18;
        if ( (unsigned __int64)v14 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v14 < 0xFFFFF6FB7DBED800uLL )
        {
          v26 = KeGetPcr()->NtTib.StackBase;
          if ( v26 )
            v27 = v26[10];
          else
            v27 = 0;
          v28 = *(_QWORD *)(v27 + 232);
          if ( v28 )
          {
            v29 = SkiKvaShadowMode;
            *(_QWORD *)(v28 + 8 * ((v14 >> 3) & 0x1FF)) = v18;
            if ( v29 != 2 && (v18 & 1) != 0 )
              v25 = v18 | 0x8000000000000000uLL;
          }
        }
        *(_QWORD *)v14 = v25;
        v14 += 8;
      }
      *a5 = v11;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14005e988  push    rbx
0x14005e98a  push    rbp
0x14005e98b  push    rsi
0x14005e98c  push    rdi
0x14005e98d  push    r12
0x14005e98f  push    r13
0x14005e991  push    r14
0x14005e993  push    r15
0x14005e995  sub     rsp, 48h
0x14005e999  mov     rbx, r8
0x14005e99c  mov     r12d, r9d
0x14005e99f  mov     r8, rcx
0x14005e9a2  lea     r9, [rsp+88h+var_50]
0x14005e9a7  mov     rcx, gs:8
0x14005e9b0  mov     rdi, rdx
0x14005e9b3  xor     r13d, r13d
0x14005e9b6  lea     rdx, SkmiSectionType
0x14005e9bd  mov     [rsp+88h+var_50], r13
0x14005e9c2  mov     cl, [rcx+60h]
0x14005e9c5  call    SkobCreateObjectEx
0x14005e9ca  test    eax, eax
0x14005e9cc  js      loc_14005EBE4
0x14005e9d2  mov     r14, [rsp+88h+var_50]
0x14005e9d7  xor     eax, eax
0x14005e9d9  xorps   xmm0, xmm0
0x14005e9dc  test    rbx, 0FFFh
0x14005e9e3  mov     ebp, r13d
0x14005e9e6  setnz   bpl
0x14005e9ea  movups  xmmword ptr [r14], xmm0
0x14005e9ee  movups  xmmword ptr [r14+10h], xmm0
0x14005e9f3  mov     [r14+20h], rax
0x14005e9f7  mov     rax, rbx
0x14005e9fa  shr     rax, 0Ch
0x14005e9fe  add     ebp, eax
0x14005ea00  mov     eax, ebp
0x14005ea02  shl     rax, 0Ch
0x14005ea06  cmp     rbx, rax
0x14005ea09  jbe     short loc_14005EA15
0x14005ea0b  mov     ebx, 0C00000F1h
0x14005ea10  jmp     loc_14005EBFB
0x14005ea15  mov     edx, ebp
0x14005ea17  mov     rcx, r14
0x14005ea1a  call    SkmiAllocateSectionProtoPtes
0x14005ea1f  mov     ebx, eax
0x14005ea21  test    eax, eax
0x14005ea23  js      loc_14005EBFB
0x14005ea29  mov     rsi, [r14+8]
0x14005ea2d  mov     ecx, r12d
0x14005ea30  mov     r8d, [r14]
0x14005ea33  call    SkmiMakeProtectionMask
0x14005ea38  add     eax, eax
0x14005ea3a  xor     eax, r8d
0x14005ea3d  and     eax, 1Eh
0x14005ea40  xor     eax, r8d
0x14005ea43  mov     [r14], eax
0x14005ea46  test    rdi, rdi
0x14005ea49  jnz     short loc_14005EA62
0x14005ea4b  lea     r8, ds:0[rbp*8]; Size
0x14005ea53  xor     edx, edx; Val
0x14005ea55  mov     rcx, rsi; void *
0x14005ea58  call    memset_0
0x14005ea5d  mov     rdi, r13
0x14005ea60  jmp     short loc_14005EA80
0x14005ea62  shr     rdi, 9
0x14005ea66  mov     rax, 7FFFFFFFF8h
0x14005ea70  and     rdi, rax
0x14005ea73  mov     rax, 0FFFFF68000000000h
0x14005ea7d  add     rdi, rax
0x14005ea80  mov     ebx, 801h
0x14005ea85  mov     [rsp+88h+var_50], rbx
0x14005ea8a  test    ebp, ebp
0x14005ea8c  jz      loc_14005EBD7
0x14005ea92  test    rdi, rdi
0x14005ea95  jz      short loc_14005EAC2
0x14005ea97  mov     rax, 0FFF0000000000FFFh
0x14005eaa1  mov     rcx, 0FFFFFFFFFF000h
0x14005eaab  and     rbx, rax
0x14005eaae  mov     rax, [rdi]
0x14005eab1  and     rax, rcx
0x14005eab4  or      rbx, rax
0x14005eab7  mov     [rsp+88h+var_50], rbx
0x14005eabc  add     rdi, 8
0x14005eac0  jmp     short loc_14005EADB
0x14005eac2  lea     rdx, [rsp+88h+var_50]
0x14005eac7  xor     ecx, ecx
0x14005eac9  call    SkmiAllocateZeroedPage
0x14005eace  test    eax, eax
0x14005ead0  jz      loc_14005EBF6
0x14005ead6  mov     rbx, [rsp+88h+var_50]
0x14005eadb  mov     rax, [rsi]
0x14005eade  mov     r9, rbx
0x14005eae1  xor     r8d, r8d
0x14005eae4  mov     [rsp+88h+var_68], rax
0x14005eae9  mov     rdx, rsi
0x14005eaec  xor     ecx, ecx
0x14005eaee  call    SkmiGetPteTrace
0x14005eaf3  mov     r13, rax
0x14005eaf6  test    rax, rax
0x14005eaf9  jz      short loc_14005EB52
0x14005eafb  xor     edx, edx; Val
0x14005eafd  lea     r15, [rax+20h]
0x14005eb01  mov     rcx, r15; void *
0x14005eb04  lea     r8d, [rdx+40h]; Size
0x14005eb08  call    memset_0
0x14005eb0d  test    cs:SkmiFlags, 400000h
0x14005eb17  jz      short loc_14005EB52
0x14005eb19  mov     rcx, gs:8; FramesToSkip
0x14005eb22  test    rcx, rcx
0x14005eb25  jz      short loc_14005EB52
0x14005eb27  lea     r9, [rsp+88h+BackTraceHash]; BackTraceHash
0x14005eb2c  mov     r8, r15; BackTrace
0x14005eb2f  mov     edx, 8; FramesToCapture
0x14005eb34  call    RtlCaptureStackBackTrace
0x14005eb39  test    ax, ax
0x14005eb3c  jnz     short loc_14005EB52
0x14005eb3e  mov     rax, [rsp+88h]
0x14005eb46  mov     [r13+28h], rax
0x14005eb4a  call    SkmiGetInstructionPointer
0x14005eb4f  mov     [r15], rax
0x14005eb52  mov     rax, rbx
0x14005eb55  mov     rcx, 0FFFFF6FB7DBED000h
0x14005eb5f  cmp     rsi, rcx
0x14005eb62  jb      short loc_14005EBC7
0x14005eb64  mov     rcx, 0FFFFF6FB7DBED800h
0x14005eb6e  cmp     rsi, rcx
0x14005eb71  jnb     short loc_14005EBC7
0x14005eb73  mov     rcx, gs:8
0x14005eb7c  xor     r13d, r13d
0x14005eb7f  test    rcx, rcx
0x14005eb82  jz      short loc_14005EB8A
0x14005eb84  mov     rdx, [rcx+50h]
0x14005eb88  jmp     short loc_14005EB8D
0x14005eb8a  mov     rdx, r13
0x14005eb8d  mov     r8, [rdx+0E8h]
0x14005eb94  test    r8, r8
0x14005eb97  jz      short loc_14005EBC7
0x14005eb99  mov     edx, cs:SkiKvaShadowMode
0x14005eb9f  mov     rcx, rsi
0x14005eba2  sar     rcx, 3
0x14005eba6  and     ecx, 1FFh
0x14005ebac  mov     [r8+rcx*8], rbx
0x14005ebb0  cmp     edx, 2
0x14005ebb3  jz      short loc_14005EBC7
0x14005ebb5  test    bl, 1
0x14005ebb8  jz      short loc_14005EBC7
0x14005ebba  mov     rcx, 8000000000000000h
0x14005ebc4  or      rax, rcx
0x14005ebc7  mov     [rsi], rax
0x14005ebca  add     rsi, 8
0x14005ebce  add     ebp, 0FFFFFFFFh
0x14005ebd1  jnz     loc_14005EA92
0x14005ebd7  mov     rax, [rsp+88h+arg_20]
0x14005ebdf  mov     [rax], r14
0x14005ebe2  xor     eax, eax
0x14005ebe4  add     rsp, 48h
0x14005ebe8  pop     r15
0x14005ebea  pop     r14
0x14005ebec  pop     r13
0x14005ebee  pop     r12
0x14005ebf0  pop     rdi
0x14005ebf1  pop     rsi
0x14005ebf2  pop     rbp
0x14005ebf3  pop     rbx
0x14005ebf4  retn
0x14005ebf6  mov     ebx, 0C0000017h
0x14005ebfb  mov     rcx, r14
0x14005ebfe  call    SkobDereferenceObject
0x14005ec03  mov     eax, ebx
0x14005ec05  jmp     short loc_14005EBE4
```
