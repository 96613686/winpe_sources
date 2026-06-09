# VsmmVaGpaCoreAccessTrackingControl

- ea: `0x1400e4f58`
- end: `0x1400e55b4`
- name: `VsmmVaGpaCoreAccessTrackingControl`
- size: `1628`
- prototype: `__int64 __fastcall(char *, char *, unsigned __int64, void *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1400d2a74`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002f524`
- `0x140034554`
- `0x140034584`
- `0x140038630`
- `0x140078f20`
- `0x1400e4f58`
- `0x1400ebc70`

## import_xrefs

- `ntoskrnl!PsIsThreadTerminating` at `0x1400e5159`
- `ntoskrnl!PsIsThreadTerminating` at `0x1400e5159`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400e5320`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400e5320`
- `winhvr!WinHvGetGpaPagesAccessState` at `0x1400e51c6`
- `winhvr!WinHvGetGpaPagesAccessState` at `0x1400e51c6`

## string_xrefs

- `0x1400e4fed`: `VsmmVaGpaCoreAccessTrackingControl`
- `0x1400e5091`: `VsmmVaGpaCoreAccessTrackingControl`
- `0x1400e5205`: `VsmmVaGpaCoreAccessTrackingControl`
- `0x1400e536f`: `VsmmVaGpaCoreAccessTrackingControl`
- `0x1400e53ce`: `VsmmVaGpaCoreAccessTrackingControl`
- `0x1400e5410`: `VsmmVaGpaCoreAccessTrackingControl`

## pseudocode

```c
__int64 __fastcall VsmmVaGpaCoreAccessTrackingControl(char *a1, char *a2, unsigned __int64 a3, void *a4, int a5)
{
  unsigned __int64 v5; // r14
  char v8; // di
  int GpaPagesAccessState; // r14d
  __int64 Range; // rax
  __int64 v11; // rdi
  char *v12; // rdx
  char *v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  unsigned __int64 i; // r8
  size_t v17; // r8
  char *v18; // r14
  __int64 v19; // r8
  int v21; // [rsp+20h] [rbp-2A8h]
  unsigned __int64 v22; // [rsp+38h] [rbp-290h] BYREF
  void *v23; // [rsp+40h] [rbp-288h] BYREF
  char *v24; // [rsp+48h] [rbp-280h] BYREF
  char *v25; // [rsp+50h] [rbp-278h] BYREF
  unsigned __int64 v26; // [rsp+58h] [rbp-270h] BYREF
  char *v27; // [rsp+60h] [rbp-268h] BYREF
  __int128 v28; // [rsp+68h] [rbp-260h] BYREF
  _QWORD v29[3]; // [rsp+78h] [rbp-250h] BYREF
  _BYTE v30[32]; // [rsp+90h] [rbp-238h] BYREF
  _BYTE v31[16]; // [rsp+B0h] [rbp-218h] BYREF
  _BYTE v32[16]; // [rsp+C0h] [rbp-208h] BYREF
  char **v33; // [rsp+D0h] [rbp-1F8h]
  __int64 v34; // [rsp+D8h] [rbp-1F0h]
  void **v35; // [rsp+E0h] [rbp-1E8h]
  __int64 v36; // [rsp+E8h] [rbp-1E0h]
  char *v37; // [rsp+F0h] [rbp-1D8h]
  __int64 v38; // [rsp+F8h] [rbp-1D0h]
  char **v39; // [rsp+100h] [rbp-1C8h]
  __int64 v40; // [rsp+108h] [rbp-1C0h]
  __int64 v41; // [rsp+110h] [rbp-1B8h]
  _DWORD v42[2]; // [rsp+118h] [rbp-1B0h] BYREF
  _QWORD *v43; // [rsp+120h] [rbp-1A8h]
  __int64 v44; // [rsp+128h] [rbp-1A0h]
  char **v45; // [rsp+130h] [rbp-198h]
  __int64 v46; // [rsp+138h] [rbp-190h]
  __int128 *v47; // [rsp+140h] [rbp-188h]
  __int64 v48; // [rsp+148h] [rbp-180h]
  unsigned __int64 *v49; // [rsp+150h] [rbp-178h]
  __int64 v50; // [rsp+158h] [rbp-170h]
  _OWORD Src[2]; // [rsp+160h] [rbp-168h] BYREF
  _BYTE v52[256]; // [rsp+180h] [rbp-148h] BYREF

  v23 = a4;
  v5 = a3;
  v22 = a3;
  v27 = a1;
  v25 = a2;
  v29[0] = a3;
  v26 = 0;
  v24 = 0;
  v28 = 0;
  v8 = 0;
  if ( !a5 || (a5 & 0xC) == 0xC )
  {
    GpaPagesAccessState = -1073741811;
    VidTraceErrorInternal0("VsmmVaGpaCoreAccessTrackingControl", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpacore.c", 4957);
  }
  else if ( (a5 & 1) != 0 )
  {
    VidObjectLockAcquireShared(a1 + 10784);
    v24 = a2;
    if ( (unsigned __int64)a2 > v5 )
    {
LABEL_9:
      if ( (a5 & 4) != 0 )
      {
        v11 = 4;
      }
      else
      {
        v11 = 0;
        if ( (a5 & 8) != 0 )
          v11 = 8;
      }
      v24 = a2;
      v13 = a2;
      while ( 1 )
      {
        if ( (unsigned __int64)v13 > v5 )
        {
          GpaPagesAccessState = 0;
          goto LABEL_15;
        }
        if ( PsIsThreadTerminating(KeGetCurrentThread()) )
        {
          GpaPagesAccessState = -1073741749;
          v8 = 1;
          goto LABEL_41;
        }
        v14 = 256;
        if ( v5 - (unsigned __int64)v24 + 1 < 0x100 )
          v14 = v5 - (_QWORD)v24 + 1;
        *(_QWORD *)&v28 = v14;
        v26 = 0;
        GpaPagesAccessState = WinHvGetGpaPagesAccessState(*((_QWORD *)a1 + 81), v11, v24, v14, v52, &v26);
        if ( GpaPagesAccessState < 0 )
          break;
        if ( (a5 & 2) != 0 )
        {
          memset(Src, 0, sizeof(Src));
          v15 = 0;
          for ( i = v26; v15 < i; ++v15 )
          {
            if ( (v52[v15] & 2) != 0 )
              _bittestandset64((signed __int64 *)Src, v15);
          }
          v17 = 8 * ((i + 63) >> 6);
          v18 = (char *)v23;
          if ( v17 && ((unsigned __int8)v23 & 7) != 0 )
            ExRaiseDatatypeMisalignment();
          RtlCopyToUser(v23, Src, v17);
          v23 = (char *)v23 + 8 * ((v26 + 63) >> 6);
          v29[1] = &v18[8 * ((v26 + 63) >> 6)];
        }
        v13 = &v24[v26];
        v24 += v26;
        v5 = v22;
      }
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v31, "VsmmVaGpaCoreAccessTrackingControl");
        tlgCreate1Sz_char(v32, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpacore.c");
        LODWORD(v25) = 5029;
        v33 = &v25;
        v23 = v24;
        v35 = &v23;
        v37 = (char *)&v28;
        v38 = 8;
        v27 = (char *)v26;
        v39 = &v27;
        v40 = 8;
        v21 = 8;
        v12 = byte_14005B633;
        goto LABEL_14;
      }
    }
    else
    {
      while ( 1 )
      {
        Range = VsmmVaGpaCorepFindRange(a1, &v24, &v28);
        if ( !Range || (*(_DWORD *)(Range + 96) & 4) == 0 )
          break;
        v24 = (char *)(*(_QWORD *)(Range + 64) + 1LL);
        if ( (unsigned __int64)v24 > v5 )
          goto LABEL_9;
      }
      GpaPagesAccessState = -1073741436;
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v31, "VsmmVaGpaCoreAccessTrackingControl");
        tlgCreate1Sz_char(v32, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpacore.c");
        LODWORD(v25) = 4983;
        v33 = &v25;
        v23 = v24;
        v35 = &v23;
        v21 = 6;
        v12 = byte_14005B5ED;
LABEL_14:
        v36 = 8;
        v34 = 4;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v12, 0, 0, v21, v30);
      }
    }
LABEL_15:
    v8 = 1;
  }
  else
  {
    GpaPagesAccessState = -1073741822;
    VidTraceErrorStatusInternal0(
      "VsmmVaGpaCoreAccessTrackingControl",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpacore.c",
      4964);
  }
  if ( GpaPagesAccessState < 0 )
  {
LABEL_41:
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v31, "VsmmVaGpaCoreAccessTrackingControl");
      tlgCreate1Sz_char(v32, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpacore.c");
      LODWORD(v25) = 5083;
      v33 = &v25;
      v34 = 4;
      LODWORD(v23) = GpaPagesAccessState;
      v35 = &v23;
      v36 = 4;
      v37 = a1 + 656;
      v38 = 16;
      v39 = (char **)v42;
      v40 = 2;
      v41 = *((_QWORD *)a1 + 16);
      v42[0] = *((unsigned __int16 *)a1 + 60);
      v42[1] = 0;
      v29[0] = *((_QWORD *)a1 + 81);
      v43 = v29;
      v44 = 8;
      v27 = a2;
      v45 = &v27;
      v46 = 8;
      *(_QWORD *)&v28 = v19;
      v47 = &v28;
      v48 = 8;
      LODWORD(v22) = a5;
      v49 = &v22;
      v50 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &word_14005B6A6, 0, 0, 13, v30);
    }
  }
  if ( v8 )
    VidObjectLockRelease(a1 + 10784);
  return (unsigned int)GpaPagesAccessState;
}

```

## disassembly

```asm
0x1400e4f58  push    rbx
0x1400e4f5a  push    rsi
0x1400e4f5b  push    rdi
0x1400e4f5c  push    r12
0x1400e4f5e  push    r13
0x1400e4f60  push    r14
0x1400e4f62  push    r15
0x1400e4f64  sub     rsp, 290h
0x1400e4f6b  mov     rax, cs:__security_cookie
0x1400e4f72  xor     rax, rsp
0x1400e4f75  mov     [rsp+2C8h+var_48], rax
0x1400e4f7d  mov     [rsp+2C8h+var_288], r9
0x1400e4f82  mov     r14, r8
0x1400e4f85  mov     [rsp+2C8h+var_290], r8
0x1400e4f8a  mov     r12, rdx
0x1400e4f8d  mov     r13, rcx
0x1400e4f90  mov     [rsp+2C8h+var_268], rcx
0x1400e4f95  mov     [rsp+2C8h+var_278], rdx
0x1400e4f9a  mov     [rsp+2C8h+var_250], r8
0x1400e4f9f  xor     esi, esi
0x1400e4fa1  mov     [rsp+2C8h+var_270], rsi
0x1400e4fa6  mov     [rsp+2C8h+var_280], rsi
0x1400e4fab  xorps   xmm0, xmm0
0x1400e4fae  movups  [rsp+2C8h+var_260], xmm0
0x1400e4fb3  mov     dil, sil
0x1400e4fb6  mov     ebx, [rsp+2C8h+arg_20]
0x1400e4fbd  test    ebx, ebx
0x1400e4fbf  jz      loc_1400E53BB
0x1400e4fc5  mov     eax, ebx
0x1400e4fc7  and     eax, 0Ch
0x1400e4fca  cmp     al, 0Ch
0x1400e4fcc  jz      loc_1400E53BB
0x1400e4fd2  test    bl, 1
0x1400e4fd5  jnz     short loc_1400E4FFE
0x1400e4fd7  mov     r14d, 0C0000002h
0x1400e4fdd  mov     r9d, r14d
0x1400e4fe0  mov     r8d, 1364h
0x1400e4fe6  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e4fed  lea     rcx, aVsmmvagpacorea; "VsmmVaGpaCoreAccessTrackingControl"
0x1400e4ff4  call    VidTraceErrorStatusInternal0
0x1400e4ff9  jmp     loc_1400E53DA
0x1400e4ffe  mov     [rsp+2C8h+var_298], 1
0x1400e5003  add     rcx, 2A20h
0x1400e500a  call    VidObjectLockAcquireShared
0x1400e500f  mov     [rsp+2C8h+var_280], r12
0x1400e5014  cmp     r12, r14
0x1400e5017  ja      short loc_1400E504B
0x1400e5019  lea     r8, [rsp+2C8h+var_260]
0x1400e501e  lea     rdx, [rsp+2C8h+var_280]
0x1400e5023  mov     rcx, r13
0x1400e5026  call    VsmmVaGpaCorepFindRange
0x1400e502b  mov     rcx, rax
0x1400e502e  test    rax, rax
0x1400e5031  jz      short loc_1400E5063
0x1400e5033  mov     eax, [rax+60h]
0x1400e5036  test    al, 4
0x1400e5038  jz      short loc_1400E5063
0x1400e503a  mov     rax, [rcx+40h]
0x1400e503e  inc     rax
0x1400e5041  mov     [rsp+2C8h+var_280], rax
0x1400e5046  cmp     rax, r14
0x1400e5049  jbe     short loc_1400E5019
0x1400e504b  mov     r15d, 8
0x1400e5051  test    bl, 4
0x1400e5054  jz      loc_1400E5135
0x1400e505a  lea     edi, [r15-4]
0x1400e505e  jmp     loc_1400E513F
0x1400e5063  mov     r14d, 0C0000184h
0x1400e5069  mov     eax, cs:dword_140064110
0x1400e506f  cmp     eax, 2
0x1400e5072  jbe     loc_1400E512B
0x1400e5078  mov     edx, 100h
0x1400e507d  lea     rcx, dword_140064110
0x1400e5084  call    _tlgKeywordOn
0x1400e5089  test    al, al
0x1400e508b  jz      loc_1400E512B
0x1400e5091  lea     rdx, aVsmmvagpacorea; "VsmmVaGpaCoreAccessTrackingControl"
0x1400e5098  lea     rcx, [rsp+2C8h+var_218]
0x1400e50a0  call    _tlgCreate1Sz_char
0x1400e50a5  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e50ac  lea     rcx, [rsp+2C8h+var_208]
0x1400e50b4  call    _tlgCreate1Sz_char
0x1400e50b9  mov     dword ptr [rsp+2C8h+var_278], 1377h
0x1400e50c1  lea     rax, [rsp+2C8h+var_278]
0x1400e50c6  mov     [rsp+2C8h+var_1F8], rax
0x1400e50ce  mov     rax, [rsp+2C8h+var_280]
0x1400e50d3  mov     [rsp+2C8h+var_288], rax
0x1400e50d8  lea     rax, [rsp+2C8h+var_288]
0x1400e50dd  mov     [rsp+2C8h+var_1E8], rax
0x1400e50e5  lea     rax, [rsp+2C8h+var_238]
0x1400e50ed  mov     [rsp+2C8h+var_2A0], rax
0x1400e50f2  mov     dword ptr [rsp+2C8h+var_2A8], 6
0x1400e50fa  lea     rdx, byte_14005B5ED
0x1400e5101  xor     r9d, r9d
0x1400e5104  xor     r8d, r8d
0x1400e5107  mov     [rsp+2C8h+var_1E0], 8
0x1400e5113  mov     [rsp+2C8h+var_1F0], 4
0x1400e511f  lea     rcx, dword_140064110
0x1400e5126  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400e512b  mov     dil, [rsp+2C8h+var_298]
0x1400e5130  jmp     loc_1400E53DA
0x1400e5135  mov     rdi, rsi
0x1400e5138  test    r15b, bl
0x1400e513b  cmovnz  rdi, r15
0x1400e513f  mov     [rsp+2C8h+var_280], r12
0x1400e5144  mov     rax, r12
0x1400e5147  cmp     rax, r14
0x1400e514a  ja      loc_1400E53B3
0x1400e5150  mov     rcx, gs:188h; Thread
0x1400e5159  call    cs:__imp_PsIsThreadTerminating
0x1400e5160  nop     dword ptr [rax+rax+00h]
0x1400e5165  test    al, al
0x1400e5167  jz      short loc_1400E517E
0x1400e5169  mov     r14d, 0C000004Bh
0x1400e516f  mov     r8, [rsp+2C8h+var_290]
0x1400e5174  mov     dil, [rsp+2C8h+var_298]
0x1400e5179  jmp     loc_1400E53E8
0x1400e517e  mov     rax, r14
0x1400e5181  mov     r8, [rsp+2C8h+var_280]
0x1400e5186  sub     rax, r8
0x1400e5189  inc     rax
0x1400e518c  mov     ecx, 100h
0x1400e5191  cmp     rax, rcx
0x1400e5194  cmovb   rcx, rax
0x1400e5198  mov     qword ptr [rsp+2C8h+var_260], rcx
0x1400e519d  mov     [rsp+2C8h+var_270], rsi
0x1400e51a2  lea     rax, [rsp+2C8h+var_270]
0x1400e51a7  mov     [rsp+2C8h+var_2A0], rax
0x1400e51ac  lea     rax, [rsp+2C8h+var_148]
0x1400e51b4  mov     [rsp+2C8h+var_2A8], rax
0x1400e51b9  mov     r9, rcx
0x1400e51bc  mov     rdx, rdi
0x1400e51bf  mov     rcx, [r13+288h]
0x1400e51c6  call    cs:__imp_WinHvGetGpaPagesAccessState
0x1400e51cd  nop     dword ptr [rax+rax+00h]
0x1400e51d2  mov     r14d, eax
0x1400e51d5  test    eax, eax
0x1400e51d7  jns     loc_1400E52BD
0x1400e51dd  mov     ecx, cs:dword_140064110
0x1400e51e3  cmp     ecx, 2
0x1400e51e6  jbe     loc_1400E512B
0x1400e51ec  mov     edx, 100h
0x1400e51f1  lea     rcx, dword_140064110
0x1400e51f8  call    _tlgKeywordOn
0x1400e51fd  test    al, al
0x1400e51ff  jz      loc_1400E512B
0x1400e5205  lea     rdx, aVsmmvagpacorea; "VsmmVaGpaCoreAccessTrackingControl"
0x1400e520c  lea     rcx, [rsp+2C8h+var_218]
0x1400e5214  call    _tlgCreate1Sz_char
0x1400e5219  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e5220  lea     rcx, [rsp+2C8h+var_208]
0x1400e5228  call    _tlgCreate1Sz_char
0x1400e522d  mov     dword ptr [rsp+2C8h+var_278], 13A5h
0x1400e5235  lea     rax, [rsp+2C8h+var_278]
0x1400e523a  mov     [rsp+2C8h+var_1F8], rax
0x1400e5242  mov     rax, [rsp+2C8h+var_280]
0x1400e5247  mov     [rsp+2C8h+var_288], rax
0x1400e524c  lea     rax, [rsp+2C8h+var_288]
0x1400e5251  mov     [rsp+2C8h+var_1E8], rax
0x1400e5259  mov     rax, qword ptr [rsp+2C8h+var_260]
0x1400e525e  mov     qword ptr [rsp+2C8h+var_260], rax
0x1400e5263  lea     rax, [rsp+2C8h+var_260]
0x1400e5268  mov     [rsp+2C8h+var_1D8], rax
0x1400e5270  mov     [rsp+2C8h+var_1D0], 8
0x1400e527c  mov     rax, [rsp+2C8h+var_270]
0x1400e5281  mov     [rsp+2C8h+var_268], rax
0x1400e5286  lea     rax, [rsp+2C8h+var_268]
0x1400e528b  mov     [rsp+2C8h+var_1C8], rax
0x1400e5293  mov     [rsp+2C8h+var_1C0], 8
0x1400e529f  lea     rax, [rsp+2C8h+var_238]
0x1400e52a7  mov     [rsp+2C8h+var_2A0], rax
0x1400e52ac  mov     dword ptr [rsp+2C8h+var_2A8], r15d
0x1400e52b1  lea     rdx, byte_14005B633
0x1400e52b8  jmp     loc_1400E5101
0x1400e52bd  test    bl, 2
0x1400e52c0  jz      loc_1400E539A
0x1400e52c6  xorps   xmm0, xmm0
0x1400e52c9  movups  [rsp+2C8h+Src], xmm0
0x1400e52d1  movups  [rsp+2C8h+var_158], xmm0
0x1400e52d9  mov     rcx, rsi
0x1400e52dc  mov     r8, [rsp+2C8h+var_270]
0x1400e52e1  test    r8, r8
0x1400e52e4  jz      short loc_1400E5304
0x1400e52e6  test    [rsp+rcx+2C8h+var_148], 2
0x1400e52ee  jz      short loc_1400E52FC
0x1400e52f0  lea     rax, [rsp+2C8h+Src]
0x1400e52f8  bts     [rax], rcx
0x1400e52fc  inc     rcx
0x1400e52ff  cmp     rcx, r8
0x1400e5302  jb      short loc_1400E52E6
0x1400e5304  add     r8, 3Fh ; '?'
0x1400e5308  shr     r8, 6
0x1400e530c  shl     r8, 3
0x1400e5310  mov     r14, [rsp+2C8h+var_288]
0x1400e5315  test    r8, r8
0x1400e5318  jz      short loc_1400E532C
0x1400e531a  test    r14b, 7
0x1400e531e  jz      short loc_1400E532C
0x1400e5320  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400e5327  nop     dword ptr [rax+rax+00h]
0x1400e532c  lea     rdx, [rsp+2C8h+Src]; Src
0x1400e5334  mov     rcx, r14; void *
0x1400e5337  call    RtlCopyToUser
0x1400e533c  mov     rax, [rsp+2C8h+var_270]
0x1400e5341  add     rax, 3Fh ; '?'
0x1400e5345  shr     rax, 6
0x1400e5349  lea     r14, [r14+rax*8]
0x1400e534d  mov     [rsp+2C8h+var_288], r14
0x1400e5352  mov     [rsp+2C8h+var_248], r14
0x1400e535a  jmp     short loc_1400E539A
0x1400e535c  mov     r14d, eax
0x1400e535f  mov     r9d, eax
0x1400e5362  mov     r8d, 13CAh
0x1400e5368  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e536f  lea     rcx, aVsmmvagpacorea; "VsmmVaGpaCoreAccessTrackingControl"
0x1400e5376  call    VidTraceErrorStatusInternal0
0x1400e537b  xor     esi, esi
0x1400e537d  mov     ebx, [rsp+2C8h+arg_20]
0x1400e5384  mov     dil, [rsp+2C8h+var_298]
0x1400e5389  mov     r13, [rsp+2C8h+var_268]
0x1400e538e  mov     r12, [rsp+2C8h+var_278]
0x1400e5393  mov     r8, [rsp+2C8h+var_250]
0x1400e5398  jmp     short loc_1400E53DF
0x1400e539a  mov     rax, [rsp+2C8h+var_280]
0x1400e539f  add     rax, [rsp+2C8h+var_270]
0x1400e53a4  mov     [rsp+2C8h+var_280], rax
0x1400e53a9  mov     r14, [rsp+2C8h+var_290]
0x1400e53ae  jmp     loc_1400E5147
0x1400e53b3  mov     r14d, esi
0x1400e53b6  jmp     loc_1400E512B
0x1400e53bb  mov     r14d, 0C000000Dh
0x1400e53c1  mov     r8d, 135Dh
0x1400e53c7  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e53ce  lea     rcx, aVsmmvagpacorea; "VsmmVaGpaCoreAccessTrackingControl"
0x1400e53d5  call    VidTraceErrorInternal0
0x1400e53da  mov     r8, [rsp+2C8h+var_290]
0x1400e53df  test    r14d, r14d
0x1400e53e2  jns     loc_1400E557C
0x1400e53e8  mov     eax, cs:dword_140064110
0x1400e53ee  cmp     eax, 2
0x1400e53f1  jbe     loc_1400E557C
0x1400e53f7  mov     edx, 100h
0x1400e53fc  lea     rcx, dword_140064110
0x1400e5403  call    _tlgKeywordOn
0x1400e5408  test    al, al
0x1400e540a  jz      loc_1400E557C
0x1400e5410  lea     rdx, aVsmmvagpacorea; "VsmmVaGpaCoreAccessTrackingControl"
0x1400e5417  lea     rcx, [rsp+2C8h+var_218]
0x1400e541f  call    _tlgCreate1Sz_char
0x1400e5424  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e542b  lea     rcx, [rsp+2C8h+var_208]
0x1400e5433  call    _tlgCreate1Sz_char
0x1400e5438  mov     dword ptr [rsp+2C8h+var_278], 13DBh
0x1400e5440  lea     rax, [rsp+2C8h+var_278]
0x1400e5445  mov     [rsp+2C8h+var_1F8], rax
0x1400e544d  mov     [rsp+2C8h+var_1F0], 4
0x1400e5459  mov     dword ptr [rsp+2C8h+var_288], r14d
0x1400e545e  lea     rax, [rsp+2C8h+var_288]
0x1400e5463  mov     [rsp+2C8h+var_1E8], rax
0x1400e546b  mov     [rsp+2C8h+var_1E0], 4
0x1400e5477  lea     rax, [r13+290h]
0x1400e547e  mov     [rsp+2C8h+var_1D8], rax
0x1400e5486  mov     [rsp+2C8h+var_1D0], 10h
0x1400e5492  lea     rax, [rsp+2C8h+var_1B0]
0x1400e549a  mov     [rsp+2C8h+var_1C8], rax
0x1400e54a2  mov     [rsp+2C8h+var_1C0], 2
0x1400e54ae  mov     rax, [r13+80h]
0x1400e54b5  mov     [rsp+2C8h+var_1B8], rax
0x1400e54bd  movzx   eax, word ptr [r13+78h]
0x1400e54c2  mov     [rsp+2C8h+var_1B0], eax
0x1400e54c9  mov     [rsp+2C8h+var_1AC], esi
0x1400e54d0  mov     rax, [r13+288h]
0x1400e54d7  mov     [rsp+2C8h+var_250], rax
0x1400e54dc  lea     rax, [rsp+2C8h+var_250]
0x1400e54e1  mov     [rsp+2C8h+var_1A8], rax
0x1400e54e9  mov     [rsp+2C8h+var_1A0], 8
0x1400e54f5  mov     [rsp+2C8h+var_268], r12
0x1400e54fa  lea     rax, [rsp+2C8h+var_268]
0x1400e54ff  mov     [rsp+2C8h+var_198], rax
0x1400e5507  mov     [rsp+2C8h+var_190], 8
0x1400e5513  mov     qword ptr [rsp+2C8h+var_260], r8
0x1400e5518  lea     rax, [rsp+2C8h+var_260]
0x1400e551d  mov     [rsp+2C8h+var_188], rax
0x1400e5525  mov     [rsp+2C8h+var_180], 8
0x1400e5531  mov     dword ptr [rsp+2C8h+var_290], ebx
0x1400e5535  lea     rax, [rsp+2C8h+var_290]
0x1400e553a  mov     [rsp+2C8h+var_178], rax
0x1400e5542  mov     [rsp+2C8h+var_170], 4
0x1400e554e  lea     rax, [rsp+2C8h+var_238]
0x1400e5556  mov     [rsp+2C8h+var_2A0], rax
0x1400e555b  mov     dword ptr [rsp+2C8h+var_2A8], 0Dh
0x1400e5563  xor     r9d, r9d
0x1400e5566  xor     r8d, r8d
0x1400e5569  lea     rdx, word_14005B6A6
0x1400e5570  lea     rcx, dword_140064110
0x1400e5577  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400e557c  test    dil, dil
0x1400e557f  jz      short loc_1400E558D
0x1400e5581  lea     rcx, [r13+2A20h]
0x1400e5588  call    VidObjectLockRelease
  ... truncated ...
```
