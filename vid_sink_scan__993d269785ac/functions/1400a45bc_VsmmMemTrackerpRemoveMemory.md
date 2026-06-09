# VsmmMemTrackerpRemoveMemory

- ea: `0x1400a45bc`
- end: `0x1400a4b98`
- name: `VsmmMemTrackerpRemoveMemory`
- size: `1500`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400a3c80`
- `0x1400a4ba0`
- `0x1400a4c68`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x140007200`
- `0x140007234`
- `0x1400087b8`
- `0x14000a4e0`
- `0x140021650`
- `0x1400a42e8`
- `0x1400a45bc`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x1400a48d2`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400a48d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a48e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a48e6`
- `HAL!KeQueryPerformanceCounter` at `0x1400a4625`
- `HAL!KeQueryPerformanceCounter` at `0x1400a4b44`
- `HAL!KeQueryPerformanceCounter` at `0x1400a4625`
- `HAL!KeQueryPerformanceCounter` at `0x1400a4b44`

## string_xrefs

- `0x1400a4711`: `VsmmMemTrackerpRemoveMemory`
- `0x1400a4919`: `VsmmMemTrackerpRemoveMemory`
- `0x1400a4a3e`: `VsmmMemTrackerpRemoveMemory`

## pseudocode

```c
LONGLONG __fastcall VsmmMemTrackerpRemoveMemory(__int64 a1, int a2, int a3, char a4, char a5, unsigned __int64 a6)
{
  __int64 v8; // rdx
  __int64 v9; // r9
  signed __int64 v10; // r8
  unsigned __int64 v11; // rbx
  int v12; // esi
  int v13; // eax
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // r14
  char v16; // cl
  signed __int64 v17; // rsi
  bool v18; // zf
  signed __int64 v19; // rax
  __int64 v20; // r14
  unsigned __int64 *v21; // rdi
  unsigned __int64 v22; // rbx
  int v23; // esi
  int v24; // eax
  unsigned __int64 v25; // rax
  LARGE_INTEGER v26; // rax
  __int64 v27; // rcx
  LONGLONG result; // rax
  char v29; // [rsp+30h] [rbp-D0h] BYREF
  char v30; // [rsp+31h] [rbp-CFh] BYREF
  char v31; // [rsp+32h] [rbp-CEh] BYREF
  char v32; // [rsp+33h] [rbp-CDh] BYREF
  char v33; // [rsp+34h] [rbp-CCh]
  int v34; // [rsp+38h] [rbp-C8h] BYREF
  int v35; // [rsp+3Ch] [rbp-C4h]
  int v36; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v38[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v39; // [rsp+58h] [rbp-A8h]
  char v40; // [rsp+59h] [rbp-A7h]
  __int16 v41; // [rsp+5Ah] [rbp-A6h]
  __int128 v42; // [rsp+60h] [rbp-A0h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v44[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v45[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v46[16]; // [rsp+B0h] [rbp-50h] BYREF
  int *v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  __int64 v49; // [rsp+D0h] [rbp-30h]
  __int64 v50; // [rsp+D8h] [rbp-28h]
  char *v51; // [rsp+E0h] [rbp-20h]
  __int64 v52; // [rsp+E8h] [rbp-18h]
  char *v53; // [rsp+F0h] [rbp-10h]
  __int64 v54; // [rsp+F8h] [rbp-8h]
  char *v55; // [rsp+100h] [rbp+0h]
  __int64 v56; // [rsp+108h] [rbp+8h]
  char *v57; // [rsp+110h] [rbp+10h]
  __int64 v58; // [rsp+118h] [rbp+18h]
  unsigned __int64 *v59; // [rsp+120h] [rbp+20h]
  __int64 v60; // [rsp+128h] [rbp+28h]

  v33 = a4;
  PerformanceFrequency.QuadPart = 0;
  v41 = 0;
  v39 = a5;
  v36 = a3;
  v35 = a2;
  v42 = 0;
  v38[0] = a2;
  v38[1] = a3;
  v40 = a4;
  *(LARGE_INTEGER *)&v42 = KeQueryPerformanceCounter(0);
  VidPushLockAcquireShared(a1 + 11920);
  v10 = 0;
  if ( *(_BYTE *)(a1 + 11944) )
  {
LABEL_53:
    v20 = a1 + 11920;
LABEL_54:
    VidPushLockRelease(v20, v8, v10, v9);
    goto LABEL_55;
  }
  v11 = *(_QWORD *)(a1 + 11928);
  v9 = 1;
  if ( (*(_BYTE *)(a1 + 11936) & 1) != 0 )
  {
    if ( v11 )
      v11 ^= a1 + 11928;
    else
      v11 = 0;
  }
  v12 = *(_BYTE *)(a1 + 11936) & 1;
  if ( !v11 )
    goto LABEL_58;
  do
  {
    v13 = VsmmMemTrackerpCompareTreeNodes(v38, v11);
    v10 = 0;
    if ( v13 >= 0 )
    {
      if ( v13 <= 0 )
        break;
      v14 = *(_QWORD *)(v11 + 8);
    }
    else
    {
      v14 = *(_QWORD *)v11;
    }
    if ( v12 && v14 )
      v11 ^= v14;
    else
      v11 = v14;
  }
  while ( v11 );
  if ( !v11 )
  {
LABEL_58:
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v45, "VsmmMemTrackerpRemoveMemory");
      tlgCreate1Sz_char(v46, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemtracker.c");
      v34 = 1131;
      v47 = &v34;
      v48 = 4;
      v49 = a1 + 656;
      v32 = v35;
      v50 = 16;
      v51 = &v32;
      v31 = v36;
      v53 = &v31;
      v55 = &v30;
      v29 = a5;
      v57 = &v29;
      v37 = a6;
      v59 = &v37;
      v52 = 1;
      v54 = 1;
      v30 = a4;
      v56 = 1;
      v58 = 1;
      v60 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_14004B5AA, 0, 0, 11, v44);
    }
    goto LABEL_53;
  }
  v15 = *(_QWORD *)(v11 + 40);
  v16 = 0;
  do
  {
    if ( a6 <= v15 )
    {
      v17 = v15 - a6;
    }
    else
    {
      if ( !v16 )
      {
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v45, "VsmmMemTrackerpRemoveMemory");
          tlgCreate1Sz_char(v46, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemtracker.c");
          v34 = 1167;
          v47 = &v34;
          v48 = 4;
          v49 = a1 + 656;
          v29 = v35;
          v50 = 16;
          v51 = &v29;
          v30 = v36;
          v53 = &v30;
          v31 = v33;
          v55 = &v31;
          v32 = a5;
          v57 = &v32;
          v59 = &v37;
          v52 = 1;
          v54 = 1;
          v56 = 1;
          v58 = 1;
          v37 = a6;
          v60 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &byte_14004B517, 0, 0, 11, v44);
          v10 = 0;
        }
        v16 = 1;
      }
      v17 = v10;
    }
    v19 = _InterlockedCompareExchange64((volatile signed __int64 *)(v11 + 40), v17, v15);
    v18 = v15 == v19;
    v15 = v19;
  }
  while ( !v18 );
  v20 = a1 + 11920;
  VidPushLockRelease(a1 + 11920, v8, v10, v9);
  v21 = (unsigned __int64 *)(a1 + 11928);
  if ( !v17 )
  {
    VidPushLockAcquireExclusive(a1 + 11920);
    v10 = 0;
    if ( !*(_BYTE *)(a1 + 11944) )
    {
      v9 = 1;
      if ( (*(_BYTE *)(a1 + 11936) & 1) != 0 )
      {
        if ( *v21 )
          v22 = *v21 ^ (unsigned __int64)v21;
        else
          v22 = 0;
      }
      else
      {
        v22 = *v21;
      }
      v23 = *(_BYTE *)(a1 + 11936) & 1;
      if ( !v22 )
        goto LABEL_59;
      do
      {
        v24 = VsmmMemTrackerpCompareTreeNodes(v38, v22);
        v10 = 0;
        if ( v24 >= 0 )
        {
          if ( v24 <= 0 )
            break;
          v25 = *(_QWORD *)(v22 + 8);
        }
        else
        {
          v25 = *(_QWORD *)v22;
        }
        if ( v23 && v25 )
          v22 ^= v25;
        else
          v22 = v25;
      }
      while ( v22 );
      if ( v22 )
      {
        if ( !*(_QWORD *)(v22 + 40) )
        {
          RtlRbRemoveNode(a1 + 11928, v22);
          ExFreePoolWithTag((PVOID)v22, 0x744D6456u);
        }
      }
      else
      {
LABEL_59:
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v45, "VsmmMemTrackerpRemoveMemory");
          tlgCreate1Sz_char(v46, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemtracker.c");
          v34 = 1247;
          v47 = &v34;
          v48 = 4;
          v49 = a1 + 656;
          v32 = v35;
          v50 = 16;
          v51 = &v32;
          v31 = v36;
          v53 = &v31;
          v30 = v33;
          v55 = &v30;
          v29 = a5;
          v57 = &v29;
          v37 = a6;
          v59 = &v37;
          v52 = 1;
          v54 = 1;
          v56 = 1;
          v58 = 1;
          v60 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004B63D, 0, 0, 11, v44);
        }
      }
    }
    goto LABEL_54;
  }
LABEL_55:
  v26 = KeQueryPerformanceCounter(&PerformanceFrequency);
  v27 = *(_QWORD *)(a1 + 1528);
  *((LARGE_INTEGER *)&v42 + 1) = v26;
  result = 1000000 * (v26.QuadPart - (__int64)v42) / PerformanceFrequency.QuadPart;
  _InterlockedAdd64((volatile signed __int64 *)(v27 + 2328), result);
  return result;
}

```

## disassembly

```asm
0x1400a45bc  push    rbp
0x1400a45be  push    rbx
0x1400a45bf  push    rsi
0x1400a45c0  push    rdi
0x1400a45c1  push    r12
0x1400a45c3  push    r13
0x1400a45c5  push    r14
0x1400a45c7  push    r15
0x1400a45c9  lea     rbp, [rsp-48h]
0x1400a45ce  sub     rsp, 148h
0x1400a45d5  mov     rax, cs:__security_cookie
0x1400a45dc  xor     rax, rsp
0x1400a45df  mov     [rbp+80h+var_50], rax
0x1400a45e3  xor     eax, eax
0x1400a45e5  mov     [rsp+180h+var_14C], r9b
0x1400a45ea  mov     qword ptr [rsp+180h+PerformanceFrequency], rax
0x1400a45ef  mov     r13, rcx
0x1400a45f2  mov     [rsp+180h+var_126], ax
0x1400a45f7  xorps   xmm0, xmm0
0x1400a45fa  mov     al, [rbp+80h+arg_20]
0x1400a4600  xor     ecx, ecx; PerformanceFrequency
0x1400a4602  mov     [rsp+180h+var_128], al
0x1400a4606  mov     r14b, r9b
0x1400a4609  mov     [rsp+180h+var_140], r8d
0x1400a460e  mov     [rsp+180h+var_144], edx
0x1400a4612  movups  [rsp+180h+var_120], xmm0
0x1400a4617  mov     [rsp+180h+var_130], edx
0x1400a461b  mov     [rsp+180h+var_12C], r8d
0x1400a4620  mov     [rsp+180h+var_127], r9b
0x1400a4625  call    cs:__imp_KeQueryPerformanceCounter
0x1400a462c  nop     dword ptr [rax+rax+00h]
0x1400a4631  lea     rcx, [r13+2E90h]
0x1400a4638  mov     qword ptr [rsp+180h+var_120], rax
0x1400a463d  call    VidPushLockAcquireShared
0x1400a4642  mov     al, [r13+2EA8h]
0x1400a4649  xor     r8d, r8d
0x1400a464c  test    al, al
0x1400a464e  jnz     loc_1400A4B30
0x1400a4654  lea     rdi, [r13+2E98h]
0x1400a465b  mov     rbx, [rdi]
0x1400a465e  lea     r9d, [r8+1]
0x1400a4662  test    [rdi+8], r9b
0x1400a4666  jz      short loc_1400A4675
0x1400a4668  test    rbx, rbx
0x1400a466b  jz      short loc_1400A4672
0x1400a466d  xor     rbx, rdi
0x1400a4670  jmp     short loc_1400A4675
0x1400a4672  mov     rbx, r8
0x1400a4675  movzx   esi, byte ptr [rdi+8]
0x1400a4679  and     esi, r9d
0x1400a467c  test    rbx, rbx
0x1400a467f  jz      loc_1400A4A13
0x1400a4685  mov     rdx, rbx
0x1400a4688  lea     rcx, [rsp+180h+var_130]
0x1400a468d  call    VsmmMemTrackerpCompareTreeNodes
0x1400a4692  xor     r8d, r8d
0x1400a4695  test    eax, eax
0x1400a4697  jns     short loc_1400A469E
0x1400a4699  mov     rax, [rbx]
0x1400a469c  jmp     short loc_1400A46A4
0x1400a469e  jle     short loc_1400A46BA
0x1400a46a0  mov     rax, [rbx+8]
0x1400a46a4  test    esi, esi
0x1400a46a6  jz      short loc_1400A46B2
0x1400a46a8  test    rax, rax
0x1400a46ab  jz      short loc_1400A46B2
0x1400a46ad  xor     rbx, rax
0x1400a46b0  jmp     short loc_1400A46B5
0x1400a46b2  mov     rbx, rax
0x1400a46b5  test    rbx, rbx
0x1400a46b8  jnz     short loc_1400A4685
0x1400a46ba  test    rbx, rbx
0x1400a46bd  jz      loc_1400A4A13
0x1400a46c3  mov     r14, [rbx+28h]
0x1400a46c7  lea     r15, dword_140064110
0x1400a46ce  mov     rdi, [rbp+80h+arg_28]
0x1400a46d5  mov     cl, r8b
0x1400a46d8  mov     r12d, 100h
0x1400a46de  cmp     rdi, r14
0x1400a46e1  jbe     loc_1400A4809
0x1400a46e7  test    cl, cl
0x1400a46e9  jnz     loc_1400A4804
0x1400a46ef  mov     eax, cs:dword_140064110
0x1400a46f5  cmp     eax, 2
0x1400a46f8  jbe     loc_1400A4802
0x1400a46fe  mov     rdx, r12
0x1400a4701  mov     rcx, r15
0x1400a4704  call    _tlgKeywordOn
0x1400a4709  test    al, al
0x1400a470b  jz      loc_1400A4802
0x1400a4711  lea     rdx, aVsmmmemtracker_5; "VsmmMemTrackerpRemoveMemory"
0x1400a4718  lea     rcx, [rbp+80h+var_E0]
0x1400a471c  call    _tlgCreate1Sz_char
0x1400a4721  lea     rdx, aOnecoreVmVidSy_15; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemtra"...
0x1400a4728  lea     rcx, [rbp+80h+var_D0]
0x1400a472c  call    _tlgCreate1Sz_char
0x1400a4731  lea     rax, [rsp+180h+var_148]
0x1400a4736  mov     [rsp+180h+var_148], 48Fh
0x1400a473e  mov     [rbp+80h+var_C0], rax
0x1400a4742  lea     rdx, byte_14004B517
0x1400a4749  lea     rax, [r13+290h]
0x1400a4750  mov     [rbp+80h+var_B8], 4
0x1400a4758  mov     [rbp+80h+var_B0], rax
0x1400a475c  xor     r9d, r9d
0x1400a475f  mov     eax, [rsp+180h+var_144]
0x1400a4763  xor     r8d, r8d
0x1400a4766  mov     [rsp+180h+var_150], al
0x1400a476a  mov     rcx, r15
0x1400a476d  lea     rax, [rsp+180h+var_150]
0x1400a4772  mov     [rbp+80h+var_A8], 10h
0x1400a477a  mov     [rbp+80h+var_A0], rax
0x1400a477e  mov     eax, [rsp+180h+var_140]
0x1400a4782  mov     [rsp+180h+var_14F], al
0x1400a4786  lea     rax, [rsp+180h+var_14F]
0x1400a478b  mov     [rbp+80h+var_90], rax
0x1400a478f  mov     al, [rsp+180h+var_14C]
0x1400a4793  mov     [rsp+180h+var_14E], al
0x1400a4797  lea     rax, [rsp+180h+var_14E]
0x1400a479c  mov     [rbp+80h+var_80], rax
0x1400a47a0  mov     al, [rbp+80h+arg_20]
0x1400a47a6  mov     [rsp+180h+var_14D], al
0x1400a47aa  lea     rax, [rsp+180h+var_14D]
0x1400a47af  mov     [rbp+80h+var_70], rax
0x1400a47b3  lea     rax, [rsp+180h+var_138]
0x1400a47b8  mov     [rbp+80h+var_60], rax
0x1400a47bc  lea     rax, [rbp+80h+var_100]
0x1400a47c0  mov     [rsp+180h+var_158], rax
0x1400a47c5  mov     [rsp+180h+var_160], 0Bh
0x1400a47cd  mov     [rbp+80h+var_98], 1
0x1400a47d5  mov     [rbp+80h+var_88], 1
0x1400a47dd  mov     [rbp+80h+var_78], 1
0x1400a47e5  mov     [rbp+80h+var_68], 1
0x1400a47ed  mov     [rsp+180h+var_138], rdi
0x1400a47f2  mov     [rbp+80h+var_58], 8
0x1400a47fa  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400a47ff  xor     r8d, r8d
0x1400a4802  mov     cl, 1
0x1400a4804  mov     rsi, r8
0x1400a4807  jmp     short loc_1400A480F
0x1400a4809  mov     rsi, r14
0x1400a480c  sub     rsi, rdi
0x1400a480f  mov     rax, r14
0x1400a4812  lock cmpxchg [rbx+28h], rsi
0x1400a4818  mov     r14, rax
0x1400a481b  jnz     loc_1400A46DE
0x1400a4821  lea     r14, [r13+2E90h]
0x1400a4828  mov     rcx, r14
0x1400a482b  call    VidPushLockRelease
0x1400a4830  lea     rdi, [r13+2E98h]
0x1400a4837  test    rsi, rsi
0x1400a483a  jnz     loc_1400A4B3F
0x1400a4840  mov     rcx, r14
0x1400a4843  call    VidPushLockAcquireExclusive
0x1400a4848  mov     al, [r13+2EA8h]
0x1400a484f  xor     r8d, r8d
0x1400a4852  test    al, al
0x1400a4854  jnz     loc_1400A4B37
0x1400a485a  lea     r9d, [r8+1]
0x1400a485e  test    [rdi+8], r9b
0x1400a4862  jz      short loc_1400A4879
0x1400a4864  mov     rax, [rdi]
0x1400a4867  test    rax, rax
0x1400a486a  jz      short loc_1400A4874
0x1400a486c  mov     rbx, rdi
0x1400a486f  xor     rbx, rax
0x1400a4872  jmp     short loc_1400A487C
0x1400a4874  mov     rbx, r8
0x1400a4877  jmp     short loc_1400A487C
0x1400a4879  mov     rbx, [rdi]
0x1400a487c  movzx   esi, byte ptr [rdi+8]
0x1400a4880  and     esi, r9d
0x1400a4883  test    rbx, rbx
0x1400a4886  jz      short loc_1400A48F7
0x1400a4888  mov     rdx, rbx
0x1400a488b  lea     rcx, [rsp+180h+var_130]
0x1400a4890  call    VsmmMemTrackerpCompareTreeNodes
0x1400a4895  xor     r8d, r8d
0x1400a4898  test    eax, eax
0x1400a489a  jns     short loc_1400A48A1
0x1400a489c  mov     rax, [rbx]
0x1400a489f  jmp     short loc_1400A48A7
0x1400a48a1  jle     short loc_1400A48BD
0x1400a48a3  mov     rax, [rbx+8]
0x1400a48a7  test    esi, esi
0x1400a48a9  jz      short loc_1400A48B5
0x1400a48ab  test    rax, rax
0x1400a48ae  jz      short loc_1400A48B5
0x1400a48b0  xor     rbx, rax
0x1400a48b3  jmp     short loc_1400A48B8
0x1400a48b5  mov     rbx, rax
0x1400a48b8  test    rbx, rbx
0x1400a48bb  jnz     short loc_1400A4888
0x1400a48bd  test    rbx, rbx
0x1400a48c0  jz      short loc_1400A48F7
0x1400a48c2  cmp     [rbx+28h], r8
0x1400a48c6  jnz     loc_1400A4B37
0x1400a48cc  mov     rdx, rbx
0x1400a48cf  mov     rcx, rdi
0x1400a48d2  call    cs:__imp_RtlRbRemoveNode
0x1400a48d9  nop     dword ptr [rax+rax+00h]
0x1400a48de  mov     edx, 744D6456h; Tag
0x1400a48e3  mov     rcx, rbx; P
0x1400a48e6  call    cs:__imp_ExFreePoolWithTag
0x1400a48ed  nop     dword ptr [rax+rax+00h]
0x1400a48f2  jmp     loc_1400A4B37
0x1400a48f7  mov     eax, cs:dword_140064110
0x1400a48fd  cmp     eax, 2
0x1400a4900  jbe     loc_1400A4B37
0x1400a4906  mov     rdx, r12
0x1400a4909  mov     rcx, r15
0x1400a490c  call    _tlgKeywordOn
0x1400a4911  test    al, al
0x1400a4913  jz      loc_1400A4B37
0x1400a4919  lea     rdx, aVsmmmemtracker_5; "VsmmMemTrackerpRemoveMemory"
0x1400a4920  lea     rcx, [rbp+80h+var_E0]
0x1400a4924  call    _tlgCreate1Sz_char
0x1400a4929  lea     rdx, aOnecoreVmVidSy_15; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemtra"...
0x1400a4930  lea     rcx, [rbp+80h+var_D0]
0x1400a4934  call    _tlgCreate1Sz_char
0x1400a4939  lea     rax, [rsp+180h+var_148]
0x1400a493e  mov     [rsp+180h+var_148], 4DFh
0x1400a4946  mov     [rbp+80h+var_C0], rax
0x1400a494a  lea     rdx, byte_14004B63D
0x1400a4951  lea     rax, [r13+290h]
0x1400a4958  mov     [rbp+80h+var_B8], 4
0x1400a4960  mov     [rbp+80h+var_B0], rax
0x1400a4964  xor     r9d, r9d
0x1400a4967  mov     eax, [rsp+180h+var_144]
0x1400a496b  xor     r8d, r8d
0x1400a496e  mov     [rsp+180h+var_14D], al
0x1400a4972  mov     rcx, r15
0x1400a4975  lea     rax, [rsp+180h+var_14D]
0x1400a497a  mov     [rbp+80h+var_A8], 10h
0x1400a4982  mov     [rbp+80h+var_A0], rax
0x1400a4986  mov     eax, [rsp+180h+var_140]
0x1400a498a  mov     [rsp+180h+var_14E], al
0x1400a498e  lea     rax, [rsp+180h+var_14E]
0x1400a4993  mov     [rbp+80h+var_90], rax
0x1400a4997  mov     al, [rsp+180h+var_14C]
0x1400a499b  mov     [rsp+180h+var_14F], al
0x1400a499f  lea     rax, [rsp+180h+var_14F]
0x1400a49a4  mov     [rbp+80h+var_80], rax
0x1400a49a8  mov     al, [rbp+80h+arg_20]
0x1400a49ae  mov     [rsp+180h+var_150], al
0x1400a49b2  lea     rax, [rsp+180h+var_150]
0x1400a49b7  mov     [rbp+80h+var_70], rax
0x1400a49bb  mov     rax, [rbp+80h+arg_28]
0x1400a49c2  mov     [rsp+180h+var_138], rax
0x1400a49c7  lea     rax, [rsp+180h+var_138]
0x1400a49cc  mov     [rbp+80h+var_60], rax
0x1400a49d0  lea     rax, [rbp+80h+var_100]
0x1400a49d4  mov     [rsp+180h+var_158], rax
0x1400a49d9  mov     [rsp+180h+var_160], 0Bh
0x1400a49e1  mov     [rbp+80h+var_98], 1
0x1400a49e9  mov     [rbp+80h+var_88], 1
0x1400a49f1  mov     [rbp+80h+var_78], 1
0x1400a49f9  mov     [rbp+80h+var_68], 1
0x1400a4a01  mov     [rbp+80h+var_58], 8
0x1400a4a09  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400a4a0e  jmp     loc_1400A4B37
0x1400a4a13  mov     eax, cs:dword_140064110
0x1400a4a19  cmp     eax, 2
0x1400a4a1c  jbe     loc_1400A4B30
0x1400a4a22  lea     r15, dword_140064110
0x1400a4a29  mov     edx, 100h
0x1400a4a2e  mov     rcx, r15
0x1400a4a31  call    _tlgKeywordOn
0x1400a4a36  test    al, al
0x1400a4a38  jz      loc_1400A4B30
0x1400a4a3e  lea     rdx, aVsmmmemtracker_5; "VsmmMemTrackerpRemoveMemory"
0x1400a4a45  lea     rcx, [rbp+80h+var_E0]
0x1400a4a49  call    _tlgCreate1Sz_char
0x1400a4a4e  lea     rdx, aOnecoreVmVidSy_15; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemtra"...
0x1400a4a55  lea     rcx, [rbp+80h+var_D0]
0x1400a4a59  call    _tlgCreate1Sz_char
0x1400a4a5e  lea     rax, [rsp+180h+var_148]
0x1400a4a63  mov     [rsp+180h+var_148], 46Bh
0x1400a4a6b  mov     [rbp+80h+var_C0], rax
0x1400a4a6f  lea     rdx, word_14004B5AA
0x1400a4a76  lea     rax, [r13+290h]
0x1400a4a7d  mov     [rbp+80h+var_B8], 4
0x1400a4a85  mov     [rbp+80h+var_B0], rax
0x1400a4a89  xor     r9d, r9d
0x1400a4a8c  mov     eax, [rsp+180h+var_144]
0x1400a4a90  xor     r8d, r8d
0x1400a4a93  mov     [rsp+180h+var_14D], al
0x1400a4a97  mov     rcx, r15
0x1400a4a9a  lea     rax, [rsp+180h+var_14D]
0x1400a4a9f  mov     [rbp+80h+var_A8], 10h
0x1400a4aa7  mov     [rbp+80h+var_A0], rax
0x1400a4aab  mov     eax, [rsp+180h+var_140]
0x1400a4aaf  mov     [rsp+180h+var_14E], al
0x1400a4ab3  lea     rax, [rsp+180h+var_14E]
0x1400a4ab8  mov     [rbp+80h+var_90], rax
0x1400a4abc  lea     rax, [rsp+180h+var_14F]
0x1400a4ac1  mov     [rbp+80h+var_80], rax
0x1400a4ac5  mov     al, [rbp+80h+arg_20]
0x1400a4acb  mov     [rsp+180h+var_150], al
0x1400a4acf  lea     rax, [rsp+180h+var_150]
0x1400a4ad4  mov     [rbp+80h+var_70], rax
  ... truncated ...
```
