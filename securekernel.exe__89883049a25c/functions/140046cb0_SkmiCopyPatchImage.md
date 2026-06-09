# SkmiCopyPatchImage

- ea: `0x140046cb0`
- end: `0x140047041`
- name: `SkmiCopyPatchImage`
- size: `913`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140045e4c`
- `0x140047048`

## callees

- `0x140003780`
- `0x14000e460`
- `0x140014740`
- `0x14001ca04`
- `0x14001e2c4`
- `0x14002b534`
- `0x140046628`
- `0x140046cb0`
- `0x140047f4c`
- `0x140060ad4`
- `0x140081290`
- `0x1400d7280`
- `0x1400f9780`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCopyPatchImage(int a1, unsigned __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  char *v6; // r13
  unsigned int v7; // edi
  __int64 v8; // rsi
  _QWORD *v9; // rdx
  unsigned int v10; // r12d
  unsigned int *v11; // r15
  unsigned __int64 v12; // rbx
  __int64 PteTrace; // rax
  PVOID *v14; // r12
  PVOID StackBase; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  _QWORD *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  int v21; // ecx
  __int64 v22; // rsi
  int v23; // ebx
  _DWORD *v24; // r14
  char *v25; // r15
  char *v26; // r12
  unsigned int i; // ebx
  __int64 v28; // r15
  int v29; // ecx
  __int64 v30; // r15
  _DWORD *v31; // rbx
  unsigned int *v32; // r14
  int v34; // [rsp+30h] [rbp-98h]
  _QWORD *v35; // [rsp+38h] [rbp-90h] BYREF
  void *Src; // [rsp+40h] [rbp-88h] BYREF
  unsigned int v37; // [rsp+48h] [rbp-80h]
  unsigned int *v38; // [rsp+50h] [rbp-78h]
  __int64 v39; // [rsp+58h] [rbp-70h]
  unsigned __int64 v40; // [rsp+60h] [rbp-68h] BYREF
  ULONG BackTraceHash; // [rsp+68h] [rbp-60h] BYREF
  _DWORD *v42; // [rsp+70h] [rbp-58h]
  char *v43; // [rsp+78h] [rbp-50h]
  char *v44; // [rsp+80h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+C8h] [rbp+0h]
  int v47; // [rsp+D0h] [rbp+8h]

  v6 = (char *)a2;
  v7 = 0;
  Src = 0;
  v8 = ((a2 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
  v9 = *(_QWORD **)(a3 + 8);
  v40 = ((unsigned __int8)word_140156D90 << 8) & 0x100 ^ 0x8000000000000063uLL;
  v10 = 0;
  v34 = 0;
  v11 = (unsigned int *)(a3 + 4);
  v38 = (unsigned int *)(a3 + 4);
  while ( 1 )
  {
    v35 = v9;
    if ( v10 >= *v11 )
      break;
    if ( (*v9 & 0xE0) != 0 )
    {
      if ( !(unsigned int)SkmiAllocateSinglePage(0, &v40) )
      {
        v22 = 0;
        v23 = -1073741670;
LABEL_36:
        if ( v22 )
          SkiAttachProcess(v22);
        SkmiFreeSecureImagePages(v6, *v11);
        return (unsigned int)v23;
      }
      v12 = v40;
      PteTrace = SkmiGetPteTrace(0, v8, 0, v40, *(_QWORD *)v8);
      v39 = PteTrace;
      if ( PteTrace )
      {
        v14 = (PVOID *)(PteTrace + 32);
        memset_0((void *)(PteTrace + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          StackBase = KeGetPcr()->NtTib.StackBase;
          if ( StackBase )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v14, &BackTraceHash) )
            {
              v17 = v39;
              *(_QWORD *)(v39 + 40) = retaddr;
              *v14 = (PVOID)SkmiGetInstructionPointer(v17, v16);
            }
          }
        }
        v10 = v34;
      }
      if ( (unsigned __int64)v8 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v8 < 0xFFFFF6FB7DBED800uLL )
      {
        v18 = KeGetPcr()->NtTib.StackBase;
        if ( v18 )
          v19 = v18[10];
        else
          v19 = 0;
        v20 = *(_QWORD *)(v19 + 232);
        if ( v20 )
        {
          v21 = SkiKvaShadowMode;
          *(_QWORD *)(v20 + 8 * ((v8 >> 3) & 0x1FF)) = v12;
          if ( v21 != 2 && (v12 & 1) != 0 )
            v12 |= 0x8000000000000000uLL;
        }
      }
      *(_QWORD *)v8 = v12;
      v9 = v35;
    }
    v8 += 8;
    ++v9;
    v34 = ++v10;
  }
  v22 = SkiAttachProcess(PsIumSystemProcess);
  v39 = v22;
  v23 = SkmiMapViewOfDriver(a3, a4, &Src);
  if ( v23 < 0 )
    goto LABEL_36;
  if ( a5 )
  {
    v35 = 0;
    RtlImageNtHeaderEx(1, (unsigned __int64)Src, 0, &v35);
    v23 = SkmiCaptureDriverIdentity(
            a5,
            v35,
            *(unsigned int *)(a3 + 204),
            *(unsigned int *)(a3 + 200),
            *(_QWORD *)(a3 + 192));
    if ( v23 < 0 )
      goto LABEL_36;
  }
  v24 = *(_DWORD **)(a3 + 8);
  v25 = (char *)Src;
  v26 = v6;
  for ( i = 0; ; ++i )
  {
    v37 = i;
    if ( i >= *v38 )
      break;
    if ( (*v24 & 0x800LL) != 0 )
      memmove(v26, v25, 0x1000u);
    v24 += 2;
    v42 = v24;
    v25 += 4096;
    v43 = v25;
    v26 += 4096;
    v44 = v26;
  }
  SkmiUnmapViewOfSection(Src, 0, 1);
  SkiAttachProcess(v22);
  v28 = *(_QWORD *)(a3 + 48);
  v29 = a1 - v28;
  v47 = a1 - v28;
  v30 = v28 - *(_QWORD *)(a3 + 40);
  v31 = *(_DWORD **)(a3 + 8);
  v32 = v38;
  if ( *v38 )
  {
    do
    {
      if ( (*v31 & 0x800LL) != 0 )
      {
        SkmiApplyRelocations(a3, v7, (_DWORD)v6, v29, v30, 10);
        v29 = v47;
      }
      LODWORD(v6) = (_DWORD)v6 + 4096;
      v31 += 2;
      ++v7;
    }
    while ( v7 < *v32 );
  }
  return 0;
}

```

## disassembly

```asm
0x140046cb0  mov     r11, rsp
0x140046cb3  mov     [r11+20h], r9
0x140046cb7  mov     [r11+18h], r8
0x140046cbb  mov     [r11+10h], rdx
0x140046cbf  mov     [r11+8], rcx
0x140046cc3  push    rbx
0x140046cc4  push    rsi
0x140046cc5  push    rdi
0x140046cc6  push    r12
0x140046cc8  push    r13
0x140046cca  push    r14
0x140046ccc  push    r15
0x140046cce  sub     rsp, 90h
0x140046cd5  mov     r14, r8
0x140046cd8  mov     r13, rdx
0x140046cdb  xor     edi, edi
0x140046cdd  mov     [rsp+0C8h+Src], rdi
0x140046ce2  mov     rsi, rdx
0x140046ce5  shr     rsi, 9
0x140046ce9  mov     rax, 7FFFFFFFF8h
0x140046cf3  and     rsi, rax
0x140046cf6  mov     rax, 0FFFFF68000000000h
0x140046d00  add     rsi, rax
0x140046d03  mov     rdx, [r8+8]
0x140046d07  movzx   ecx, byte ptr cs:word_140156D90
0x140046d0e  shl     rcx, 8
0x140046d12  and     ecx, 100h
0x140046d18  mov     rax, 8000000000000063h
0x140046d22  xor     rcx, rax
0x140046d25  mov     [r11-68h], rcx
0x140046d29  mov     r12d, edi
0x140046d2c  mov     [rsp+0C8h+var_98], edi
0x140046d30  lea     r15, [r8+4]
0x140046d34  mov     [rsp+0C8h+var_78], r15
0x140046d39  mov     [rsp+0C8h+var_90], rdx
0x140046d3e  cmp     r12d, [r15]
0x140046d41  jnb     loc_140046E87
0x140046d47  mov     rax, [rdx]
0x140046d4a  test    al, 0E0h
0x140046d4c  jz      loc_140046E65
0x140046d52  lea     rdx, [rsp+0C8h+var_68]
0x140046d57  xor     ecx, ecx
0x140046d59  call    SkmiAllocateSinglePage
0x140046d5e  test    eax, eax
0x140046d60  jz      loc_140046E7A
0x140046d66  mov     rbx, [rsp+0C8h+var_68]
0x140046d6b  mov     rax, [rsi]
0x140046d6e  mov     [rsp+0C8h+var_A8], rax
0x140046d73  mov     r9, rbx
0x140046d76  xor     r8d, r8d
0x140046d79  mov     rdx, rsi
0x140046d7c  xor     ecx, ecx
0x140046d7e  call    SkmiGetPteTrace
0x140046d83  mov     [rsp+0C8h+var_70], rax
0x140046d88  test    rax, rax
0x140046d8b  jz      short loc_140046DEF
0x140046d8d  lea     r12, [rax+20h]
0x140046d91  xor     edx, edx; Val
0x140046d93  lea     r8d, [rdx+40h]; Size
0x140046d97  mov     rcx, r12; void *
0x140046d9a  call    memset_0
0x140046d9f  test    cs:SkmiFlags, 400000h
0x140046da9  jz      short loc_140046DEA
0x140046dab  mov     rcx, gs:8; FramesToSkip
0x140046db4  test    rcx, rcx
0x140046db7  jz      short loc_140046DEA
0x140046db9  lea     r9, [rsp+0C8h+BackTraceHash]; BackTraceHash
0x140046dbe  mov     r8, r12; BackTrace
0x140046dc1  mov     edx, 8; FramesToCapture
0x140046dc6  call    RtlCaptureStackBackTrace
0x140046dcb  test    ax, ax
0x140046dce  jnz     short loc_140046DEA
0x140046dd0  mov     rax, [rsp+0C8h]
0x140046dd8  mov     rcx, [rsp+0C8h+var_70]
0x140046ddd  mov     [rcx+28h], rax
0x140046de1  call    SkmiGetInstructionPointer
0x140046de6  mov     [r12], rax
0x140046dea  mov     r12d, [rsp+0C8h+var_98]
0x140046def  mov     rax, 0FFFFF6FB7DBED000h
0x140046df9  cmp     rsi, rax
0x140046dfc  jb      short loc_140046E5D
0x140046dfe  mov     rax, 0FFFFF6FB7DBED800h
0x140046e08  cmp     rsi, rax
0x140046e0b  jnb     short loc_140046E5D
0x140046e0d  mov     rax, gs:8
0x140046e16  test    rax, rax
0x140046e19  jz      short loc_140046E21
0x140046e1b  mov     rcx, [rax+50h]
0x140046e1f  jmp     short loc_140046E24
0x140046e21  mov     rcx, rdi
0x140046e24  mov     rdx, [rcx+0E8h]
0x140046e2b  test    rdx, rdx
0x140046e2e  jz      short loc_140046E5D
0x140046e30  mov     ecx, cs:SkiKvaShadowMode
0x140046e36  mov     rax, rsi
0x140046e39  sar     rax, 3
0x140046e3d  and     eax, 1FFh
0x140046e42  mov     [rdx+rax*8], rbx
0x140046e46  cmp     ecx, 2
0x140046e49  jz      short loc_140046E5D
0x140046e4b  test    bl, 1
0x140046e4e  jz      short loc_140046E5D
0x140046e50  mov     rax, 8000000000000000h
0x140046e5a  or      rbx, rax
0x140046e5d  mov     [rsi], rbx
0x140046e60  mov     rdx, [rsp+0C8h+var_90]
0x140046e65  add     rsi, 8
0x140046e69  add     rdx, 8
0x140046e6d  inc     r12d
0x140046e70  mov     [rsp+0C8h+var_98], r12d
0x140046e75  jmp     loc_140046D39
0x140046e7a  mov     rsi, rdi
0x140046e7d  mov     ebx, 0C000009Ah
0x140046e82  jmp     loc_140047013
0x140046e87  mov     rcx, cs:PsIumSystemProcess
0x140046e8e  call    SkiAttachProcess
0x140046e93  mov     rsi, rax
0x140046e96  mov     [rsp+0C8h+var_70], rax
0x140046e9b  lea     r8, [rsp+0C8h+Src]
0x140046ea0  mov     rdx, [rsp+0C8h+arg_18]
0x140046ea8  mov     rcx, r14
0x140046eab  call    SkmiMapViewOfDriver
0x140046eb0  mov     ebx, eax
0x140046eb2  test    eax, eax
0x140046eb4  js      loc_140047013
0x140046eba  cmp     [rsp+0C8h+arg_20], rdi
0x140046ec2  jz      short loc_140046F15
0x140046ec4  mov     [rsp+0C8h+var_90], rdi
0x140046ec9  lea     r9, [rsp+0C8h+var_90]
0x140046ece  xor     r8d, r8d
0x140046ed1  mov     rdx, [rsp+0C8h+Src]
0x140046ed6  lea     ecx, [r8+1]
0x140046eda  call    RtlImageNtHeaderEx
0x140046edf  mov     rax, [r14+0C0h]
0x140046ee6  mov     [rsp+0C8h+var_A8], rax
0x140046eeb  mov     r9d, [r14+0C8h]
0x140046ef2  mov     r8d, [r14+0CCh]
0x140046ef9  mov     rdx, [rsp+0C8h+var_90]
0x140046efe  mov     rcx, [rsp+0C8h+arg_20]
0x140046f06  call    SkmiCaptureDriverIdentity
0x140046f0b  mov     ebx, eax
0x140046f0d  test    eax, eax
0x140046f0f  js      loc_140047013
0x140046f15  mov     r14, [r14+8]
0x140046f19  mov     r15, [rsp+0C8h+Src]
0x140046f1e  mov     r12, r13
0x140046f21  mov     ebx, edi
0x140046f23  mov     ecx, 1000h
0x140046f28  mov     [rsp+0C8h+var_80], ebx
0x140046f2c  mov     rax, [rsp+0C8h+var_78]
0x140046f31  cmp     ebx, [rax]
0x140046f33  jnb     short loc_140046F72
0x140046f35  mov     eax, [r14]
0x140046f38  bt      rax, 0Bh
0x140046f3d  jnb     short loc_140046F52
0x140046f3f  mov     r8, rcx; Size
0x140046f42  mov     rdx, r15; Src
0x140046f45  mov     rcx, r12; void *
0x140046f48  call    memmove
0x140046f4d  mov     ecx, 1000h
0x140046f52  add     r14, 8
0x140046f56  mov     [rsp+0C8h+var_58], r14
0x140046f5b  add     r15, rcx
0x140046f5e  mov     [rsp+0C8h+var_50], r15
0x140046f63  add     r12, rcx
0x140046f66  mov     [rsp+0C8h+var_48], r12
0x140046f6e  inc     ebx
0x140046f70  jmp     short loc_140046F28
0x140046f72  xor     edx, edx
0x140046f74  lea     r8d, [rdx+1]
0x140046f78  mov     rcx, [rsp+0C8h+Src]
0x140046f7d  call    SkmiUnmapViewOfSection
0x140046f82  mov     rcx, rsi
0x140046f85  call    SkiAttachProcess
0x140046f8a  mov     rsi, [rsp+0C8h+arg_10]
0x140046f92  mov     r15, [rsi+30h]
0x140046f96  mov     rcx, [rsp+0C8h+arg_0]
0x140046f9e  sub     rcx, r15
0x140046fa1  mov     [rsp+0C8h+arg_0], rcx
0x140046fa9  sub     r15, [rsi+28h]
0x140046fad  mov     rbx, [rsi+8]
0x140046fb1  mov     r14, [rsp+0C8h+var_78]
0x140046fb6  cmp     [r14], edi
0x140046fb9  jbe     short loc_140046FFB
0x140046fbb  mov     eax, [rbx]
0x140046fbd  bt      rax, 0Bh
0x140046fc2  jnb     short loc_140046FE9
0x140046fc4  mov     [rsp+0C8h+var_A0], 0Ah
0x140046fcc  mov     [rsp+0C8h+var_A8], r15
0x140046fd1  mov     r9, rcx
0x140046fd4  mov     r8, r13
0x140046fd7  mov     edx, edi
0x140046fd9  mov     rcx, rsi
0x140046fdc  call    SkmiApplyRelocations
0x140046fe1  mov     rcx, [rsp+0C8h+arg_0]
0x140046fe9  add     r13, 1000h
0x140046ff0  add     rbx, 8
0x140046ff4  inc     edi
0x140046ff6  cmp     edi, [r14]
0x140046ff9  jb      short loc_140046FBB
0x140046ffb  xor     eax, eax
0x140046ffd  jmp     short loc_14004702D
0x140046fff  mov     ebx, eax
0x140047001  mov     r13, [rsp+0C8h+arg_8]
0x140047009  mov     rsi, [rsp+0C8h+var_70]
0x14004700e  mov     r15, [rsp+0C8h+var_78]
0x140047013  test    rsi, rsi
0x140047016  jz      short loc_140047020
0x140047018  mov     rcx, rsi
0x14004701b  call    SkiAttachProcess
0x140047020  mov     edx, [r15]
0x140047023  mov     rcx, r13
0x140047026  call    SkmiFreeSecureImagePages
0x14004702b  mov     eax, ebx
0x14004702d  add     rsp, 90h
0x140047034  pop     r15
0x140047036  pop     r14
0x140047038  pop     r13
0x14004703a  pop     r12
0x14004703c  pop     rdi
0x14004703d  pop     rsi
0x14004703e  pop     rbx
0x14004703f  retn
```
