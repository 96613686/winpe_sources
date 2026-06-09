# CTnMultiResNode::Deserialize(uchar * &,CTnMultiResNode * *,uchar *,long)

- ea: `0x18000b208`
- end: `0x18000b669`
- name: `?Deserialize@CTnMultiResNode@@QEAAJAEAPEAEPEAPEAV1@PEAEJ@Z`
- size: `1121`
- prototype: `__int64 __usercall@<rax>(CTnMultiResNode *__hidden this@<rcx>, unsigned __int8 **@<rdx>, struct CTnMultiResNode **@<r8>, unsigned __int8 *@<r9>, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000afe0`

## callees

- `0x180001c50`
- `0x180002ecc`
- `0x180002fb0`
- `0x180008f2c`
- `0x180008fa4`
- `0x18000959c`
- `0x180009c04`
- `0x18000b208`
- `0x18000daf4`
- `0x18000e494`
- `0x18000ea18`
- `0x18000ecd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b537`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b537`

## pseudocode

```c
__int64 __fastcall CTnMultiResNode::Deserialize(
        __int64 **this,
        unsigned __int8 **a2,
        struct CTnMultiResNode **a3,
        unsigned __int8 *a4,
        int a5)
{
  signed int v9; // ebx
  unsigned int v10; // r14d
  unsigned __int64 v11; // rax
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // r12
  unsigned int v14; // eax
  int v15; // r14d
  int v16; // r12d
  CAttribSetInResult *v17; // rax
  CAttribSetInResult *v18; // rcx
  int v19; // r13d
  int v20; // r12d
  CAgreementElement *v21; // rax
  CAgreementElement *v22; // r14
  unsigned int v23; // edx
  char v24; // al
  unsigned __int64 v25; // r14
  __int64 *v26; // rax
  unsigned __int8 *v27; // r8
  errno_t v28; // eax
  int v29; // r13d
  int i; // r12d
  __int64 v31; // rax
  __int64 *v32; // rcx
  int v34; // [rsp+70h] [rbp+48h] BYREF

  v9 = SafeMemCopyAndAdvanceInput<long>(this + 5, a2, a4);
  if ( v9 < 0 )
    return (unsigned int)v9;
  v9 = SafeMemCopyAndAdvanceInput<long>(this + 8, a2, a4);
  if ( v9 < 0 )
    return (unsigned int)v9;
  v34 = 0;
  v9 = SafeMemCopyAndAdvanceInput<long>(&v34, a2, a4);
  if ( v9 < 0 )
    return (unsigned int)v9;
  v10 = v34;
  if ( v34 <= 0 )
    return (unsigned int)-2147418113;
  v11 = 2LL * v34;
  if ( !is_mul_ok(v34, 2u) )
    v11 = -1;
  v12 = (unsigned __int16 *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v12;
  if ( !v12 )
    return (unsigned int)-2147024882;
  v9 = SafeMemCopyAndAdvanceInput<unsigned short>(v12, a2, a4, v10);
  if ( v9 < 0 )
    return (unsigned int)v9;
  v14 = v10 - 1;
  v15 = 0;
  if ( v13[v14] )
    return (unsigned int)-2147418113;
  v9 = CTnMultiResNode::SetData((CTnMultiResNode *)this, v13);
  if ( v9 < 0 )
    return (unsigned int)v9;
  CWinHeap::Free((CWinHeap *)&g_heap, v13);
  v34 = 0;
  v9 = SafeMemCopyAndAdvanceInput<long>(&v34, a2, a4);
  if ( v9 < 0 )
    return (unsigned int)v9;
  v16 = v34;
  if ( v34 > 0 )
  {
    do
    {
      v34 = 0;
      v9 = SafeMemCopyAndAdvanceInput<long>(&v34, a2, a4);
      if ( v9 < 0 )
        return (unsigned int)v9;
      if ( v34 < 0 || v34 >= a5 )
        return (unsigned int)-2147418113;
      if ( !CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::AddTail(
              this + 9,
              a3[v34]) )
        return (unsigned int)-2147024882;
    }
    while ( ++v15 < v16 );
  }
  v9 = SafeMemCopyAndAdvanceInput<long>((char *)this + 44, a2, a4);
  if ( v9 < 0 )
    return (unsigned int)v9;
  v9 = SafeMemCopyAndAdvanceInput<long>((char *)this + 68, a2, a4);
  if ( v9 < 0 )
    return (unsigned int)v9;
  v34 = 0;
  v9 = SafeMemCopyAndAdvanceInput<long>(&v34, a2, a4);
  if ( v9 < 0 )
    return (unsigned int)v9;
  if ( v34 )
  {
    v17 = (CAttribSetInResult *)operator new[](0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v18 = v17;
    if ( v17 )
    {
      *(_QWORD *)v17 = 0;
      *((_WORD *)v17 + 4) = 0;
    }
    else
    {
      v18 = 0;
    }
    this[15] = (__int64 *)v18;
    if ( !v18 )
      return (unsigned int)-2147024882;
    v9 = CAttribSetInResult::Deserialize(v18, a2, a4);
    if ( v9 < 0 )
      return (unsigned int)v9;
  }
  v34 = 0;
  v9 = SafeMemCopyAndAdvanceInput<long>(&v34, a2, a4);
  if ( v9 < 0 )
    return (unsigned int)v9;
  v19 = v34;
  v20 = 0;
  if ( v34 > 0 )
  {
    do
    {
      v21 = (CAgreementElement *)operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
      v22 = v21;
      if ( !v21 )
        return (unsigned int)-2147024882;
      *((_DWORD *)v21 + 6) = 0;
      *((_QWORD *)v21 + 4) = 0;
      *((_QWORD *)v21 + 2) = 0;
      *((_QWORD *)v21 + 1) = 0;
      *((_QWORD *)v21 + 5) = 0;
      *(_DWORD *)v21 = -1;
      *((_WORD *)v21 + 2) = -1;
      *((_DWORD *)v21 + 12) = 10;
      v9 = CAgreementElement::Deserialize(v21, a2, a4);
      if ( v9 < 0 )
        goto LABEL_55;
      if ( !CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::AddTail(this + 16, v22) )
      {
        v9 = -2147024882;
LABEL_55:
        CAgreementElement::`scalar deleting destructor'(v22, v23);
        return (unsigned int)v9;
      }
    }
    while ( ++v20 < v19 );
  }
  v34 = 0;
  v9 = SafeMemCopyAndAdvanceInput<long>(&v34, a2, a4);
  if ( v9 < 0 )
    return (unsigned int)v9;
  v24 = v34;
  *((_DWORD *)this + 58) &= ~8u;
  *((_DWORD *)this + 58) |= 8 * (v24 & 1);
  v34 = 0;
  v9 = SafeMemCopyAndAdvanceInput<long>(&v34, a2, a4);
  if ( v9 < 0 )
    return (unsigned int)v9;
  if ( v34 <= 0 )
  {
LABEL_48:
    v34 = 0;
    v9 = SafeMemCopyAndAdvanceInput<long>(&v34, a2, a4);
    if ( v9 >= 0 )
    {
      v29 = v34;
      for ( i = 0; i < v29; this[24] = (__int64 *)v31 )
      {
        v34 = 0;
        v9 = SafeMemCopyAndAdvanceInput<long>(&v34, a2, a4);
        if ( v9 < 0 )
          break;
        v31 = CSPList<long,long>::NewNode(this + 23, this[24], 0);
        if ( !v31 )
          return (unsigned int)-2147024882;
        *(_DWORD *)(v31 + 16) = v34;
        v32 = this[24];
        if ( v32 )
          *v32 = v31;
        else
          this[23] = (__int64 *)v31;
        ++i;
      }
    }
    return (unsigned int)v9;
  }
  v25 = 2LL * v34;
  v26 = (__int64 *)malloc(v25);
  this[22] = v26;
  if ( !v26 )
    return (unsigned int)-2147024882;
  v27 = *a2;
  if ( a4 <= *a2 || !v27 || !a4 || !v25 || a4 - v27 < v25 )
    return (unsigned int)-2147024809;
  v28 = memcpy_s(v26, v25, v27, v25);
  v9 = v28;
  if ( !v28 )
    goto LABEL_47;
  if ( v28 > 0 )
    v9 = (unsigned __int16)v28 | 0x80070000;
  if ( v9 >= 0 )
  {
LABEL_47:
    *a2 += v25;
    goto LABEL_48;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b208  push    rbp
0x18000b20a  push    rbx
0x18000b20b  push    rsi
0x18000b20c  push    rdi
0x18000b20d  push    r12
0x18000b20f  push    r13
0x18000b211  push    r14
0x18000b213  push    r15
0x18000b215  mov     rbp, rsp
0x18000b218  sub     rsp, 28h
0x18000b21c  mov     r13, r8
0x18000b21f  mov     r15, rcx
0x18000b222  add     rcx, 28h ; '('
0x18000b226  mov     r8, r9
0x18000b229  mov     rsi, r9
0x18000b22c  mov     rdi, rdx
0x18000b22f  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b234  xor     r12d, r12d
0x18000b237  mov     ebx, eax
0x18000b239  test    eax, eax
0x18000b23b  js      loc_18000B656
0x18000b241  lea     rcx, [r15+40h]
0x18000b245  mov     r8, rsi
0x18000b248  mov     rdx, rdi
0x18000b24b  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b250  mov     ebx, eax
0x18000b252  test    eax, eax
0x18000b254  js      loc_18000B656
0x18000b25a  mov     r8, rsi
0x18000b25d  mov     [rbp+arg_0], r12d
0x18000b261  mov     rdx, rdi
0x18000b264  lea     rcx, [rbp+arg_0]
0x18000b268  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b26d  mov     ebx, eax
0x18000b26f  test    eax, eax
0x18000b271  js      loc_18000B656
0x18000b277  movsxd  r14, [rbp+arg_0]
0x18000b27b  test    r14d, r14d
0x18000b27e  jle     loc_18000B651
0x18000b284  lea     rcx, [r12-1]
0x18000b289  lea     eax, [r12+2]
0x18000b28e  mul     r14
0x18000b291  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b298  cmovb   rax, rcx
0x18000b29c  mov     rcx, rax; unsigned __int64
0x18000b29f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b2a4  mov     r12, rax
0x18000b2a7  test    rax, rax
0x18000b2aa  jnz     short loc_18000B2B6
0x18000b2ac  mov     ebx, 8007000Eh
0x18000b2b1  jmp     loc_18000B656
0x18000b2b6  mov     r9d, r14d
0x18000b2b9  mov     r8, rsi
0x18000b2bc  mov     rdx, rdi
0x18000b2bf  mov     rcx, r12
0x18000b2c2  call    ??$SafeMemCopyAndAdvanceInput@G@@YAJPEAGAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<ushort>(ushort *,uchar * &,uchar *,long)
0x18000b2c7  mov     ebx, eax
0x18000b2c9  test    eax, eax
0x18000b2cb  js      loc_18000B656
0x18000b2d1  lea     eax, [r14-1]
0x18000b2d5  xor     r14d, r14d
0x18000b2d8  movsxd  rcx, eax
0x18000b2db  cmp     [r12+rcx*2], r14w
0x18000b2e0  jnz     loc_18000B651
0x18000b2e6  mov     rdx, r12; unsigned __int16 *
0x18000b2e9  mov     rcx, r15; this
0x18000b2ec  call    ?SetData@CTnMultiResNode@@QEAAJPEAG@Z; CTnMultiResNode::SetData(ushort *)
0x18000b2f1  mov     ebx, eax
0x18000b2f3  test    eax, eax
0x18000b2f5  js      loc_18000B656
0x18000b2fb  mov     rdx, r12; void *
0x18000b2fe  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18000b305  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18000b30a  mov     r8, rsi
0x18000b30d  mov     [rbp+arg_0], r14d
0x18000b311  mov     rdx, rdi
0x18000b314  lea     rcx, [rbp+arg_0]
0x18000b318  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b31d  mov     ebx, eax
0x18000b31f  test    eax, eax
0x18000b321  js      loc_18000B656
0x18000b327  mov     r12d, [rbp+arg_0]
0x18000b32b  xor     ebx, ebx
0x18000b32d  test    r12d, r12d
0x18000b330  jle     short loc_18000B384
0x18000b332  mov     r8, rsi
0x18000b335  mov     [rbp+arg_0], ebx
0x18000b338  mov     rdx, rdi
0x18000b33b  lea     rcx, [rbp+arg_0]
0x18000b33f  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b344  mov     ebx, eax
0x18000b346  test    eax, eax
0x18000b348  js      loc_18000B656
0x18000b34e  movsxd  rax, [rbp+arg_0]
0x18000b352  xor     ebx, ebx
0x18000b354  test    eax, eax
0x18000b356  js      loc_18000B651
0x18000b35c  cmp     eax, [rbp+arg_20]
0x18000b35f  jge     loc_18000B651
0x18000b365  mov     rdx, [r13+rax*8+0]
0x18000b36a  lea     rcx, [r15+48h]
0x18000b36e  call    ?AddTail@?$CSPList@PEAUSStrCost@CTnMultiResStringPackage@@PEAU12@@@QEAAPEAXPEAUSStrCost@CTnMultiResStringPackage@@@Z; CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::AddTail(CTnMultiResStringPackage::SStrCost *)
0x18000b373  test    rax, rax
0x18000b376  jz      loc_18000B2AC
0x18000b37c  inc     r14d
0x18000b37f  cmp     r14d, r12d
0x18000b382  jl      short loc_18000B332
0x18000b384  lea     rcx, [r15+2Ch]
0x18000b388  mov     r8, rsi
0x18000b38b  mov     rdx, rdi
0x18000b38e  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b393  xor     r14d, r14d
0x18000b396  mov     ebx, eax
0x18000b398  test    eax, eax
0x18000b39a  js      loc_18000B656
0x18000b3a0  lea     rcx, [r15+44h]
0x18000b3a4  mov     r8, rsi
0x18000b3a7  mov     rdx, rdi
0x18000b3aa  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b3af  mov     ebx, eax
0x18000b3b1  test    eax, eax
0x18000b3b3  js      loc_18000B656
0x18000b3b9  mov     r8, rsi
0x18000b3bc  mov     [rbp+arg_0], r14d
0x18000b3c0  mov     rdx, rdi
0x18000b3c3  lea     rcx, [rbp+arg_0]
0x18000b3c7  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b3cc  mov     ebx, eax
0x18000b3ce  test    eax, eax
0x18000b3d0  js      loc_18000B656
0x18000b3d6  cmp     [rbp+arg_0], r14d
0x18000b3da  jz      short loc_18000B423
0x18000b3dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b3e3  lea     ecx, [r14+10h]; unsigned __int64
0x18000b3e7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b3ec  mov     rcx, rax
0x18000b3ef  test    rax, rax
0x18000b3f2  jz      short loc_18000B3FE
0x18000b3f4  mov     [rax], r14
0x18000b3f7  mov     [rax+8], r14w
0x18000b3fc  jmp     short loc_18000B401
0x18000b3fe  mov     rcx, r14; this
0x18000b401  mov     [r15+78h], rcx
0x18000b405  test    rcx, rcx
0x18000b408  jz      loc_18000B2AC
0x18000b40e  mov     r8, rsi; unsigned __int8 *
0x18000b411  mov     rdx, rdi; unsigned __int8 **
0x18000b414  call    ?Deserialize@CAttribSetInResult@@QEAAJAEAPEAEPEAE@Z; CAttribSetInResult::Deserialize(uchar * &,uchar *)
0x18000b419  mov     ebx, eax
0x18000b41b  test    eax, eax
0x18000b41d  js      loc_18000B656
0x18000b423  mov     r8, rsi
0x18000b426  mov     [rbp+arg_0], r14d
0x18000b42a  mov     rdx, rdi
0x18000b42d  lea     rcx, [rbp+arg_0]
0x18000b431  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b436  mov     ebx, eax
0x18000b438  test    eax, eax
0x18000b43a  js      loc_18000B656
0x18000b440  mov     r13d, [rbp+arg_0]
0x18000b444  mov     r12d, r14d
0x18000b447  test    r13d, r13d
0x18000b44a  jle     loc_18000B4D0
0x18000b450  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b457  mov     ecx, 38h ; '8'; unsigned __int64
0x18000b45c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b461  xor     ecx, ecx
0x18000b463  mov     r14, rax
0x18000b466  test    rax, rax
0x18000b469  jz      loc_18000B2AC
0x18000b46f  mov     [rax+18h], ecx
0x18000b472  mov     r8, rsi; unsigned __int8 *
0x18000b475  mov     [rax+20h], rcx
0x18000b479  mov     rdx, rdi; unsigned __int8 **
0x18000b47c  mov     [rax+10h], rcx
0x18000b480  mov     [rax+8], rcx
0x18000b484  mov     [rax+28h], rcx
0x18000b488  mov     rcx, rax; this
0x18000b48b  mov     dword ptr [rax], 0FFFFFFFFh
0x18000b491  mov     word ptr [rax+4], 0FFFFh
0x18000b497  mov     dword ptr [rax+30h], 0Ah
0x18000b49e  call    ?Deserialize@CAgreementElement@@QEAAJAEAPEAEPEAE@Z; CAgreementElement::Deserialize(uchar * &,uchar *)
0x18000b4a3  mov     ebx, eax
0x18000b4a5  test    eax, eax
0x18000b4a7  js      loc_18000B62C
0x18000b4ad  lea     rcx, [r15+80h]
0x18000b4b4  mov     rdx, r14
0x18000b4b7  call    ?AddTail@?$CSPList@PEAUSStrCost@CTnMultiResStringPackage@@PEAU12@@@QEAAPEAXPEAUSStrCost@CTnMultiResStringPackage@@@Z; CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::AddTail(CTnMultiResStringPackage::SStrCost *)
0x18000b4bc  test    rax, rax
0x18000b4bf  jz      loc_18000B627
0x18000b4c5  inc     r12d
0x18000b4c8  cmp     r12d, r13d
0x18000b4cb  jl      short loc_18000B450
0x18000b4cd  xor     r14d, r14d
0x18000b4d0  mov     r8, rsi
0x18000b4d3  mov     [rbp+arg_0], r14d
0x18000b4d7  mov     rdx, rdi
0x18000b4da  lea     rcx, [rbp+arg_0]
0x18000b4de  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b4e3  mov     ebx, eax
0x18000b4e5  test    eax, eax
0x18000b4e7  js      loc_18000B656
0x18000b4ed  mov     eax, [rbp+arg_0]
0x18000b4f0  lea     rcx, [rbp+arg_0]
0x18000b4f4  and     dword ptr [r15+0E8h], 0FFFFFFF7h
0x18000b4fc  and     eax, 1
0x18000b4ff  shl     eax, 3
0x18000b502  mov     r8, rsi
0x18000b505  or      [r15+0E8h], eax
0x18000b50c  mov     rdx, rdi
0x18000b50f  mov     [rbp+arg_0], r14d
0x18000b513  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b518  mov     ebx, eax
0x18000b51a  test    eax, eax
0x18000b51c  js      loc_18000B656
0x18000b522  movsxd  rax, [rbp+arg_0]
0x18000b526  test    eax, eax
0x18000b528  jle     loc_18000B5B0
0x18000b52e  mov     r14, rax
0x18000b531  add     r14, r14
0x18000b534  mov     rcx, r14; Size
0x18000b537  call    cs:__imp_malloc
0x18000b53d  mov     [r15+0B0h], rax
0x18000b544  mov     rcx, rax; Destination
0x18000b547  test    rax, rax
0x18000b54a  jz      loc_18000B2AC
0x18000b550  mov     r8, [rdi]; Source
0x18000b553  cmp     rsi, r8
0x18000b556  jbe     loc_18000B636
0x18000b55c  test    r8, r8
0x18000b55f  jz      loc_18000B636
0x18000b565  test    rsi, rsi
0x18000b568  jz      loc_18000B636
0x18000b56e  test    r14, r14
0x18000b571  jz      loc_18000B636
0x18000b577  mov     rax, rsi
0x18000b57a  sub     rax, r8
0x18000b57d  cmp     rax, r14
0x18000b580  jb      loc_18000B636
0x18000b586  mov     r9, r14; SourceSize
0x18000b589  mov     rdx, r14; DestinationSize
0x18000b58c  call    memcpy_s
0x18000b591  mov     ebx, eax
0x18000b593  test    eax, eax
0x18000b595  jz      short loc_18000B5AA
0x18000b597  jle     short loc_18000B5A2
0x18000b599  movzx   ebx, ax
0x18000b59c  or      ebx, 80070000h
0x18000b5a2  test    ebx, ebx
0x18000b5a4  js      loc_18000B656
0x18000b5aa  add     [rdi], r14
0x18000b5ad  xor     r14d, r14d
0x18000b5b0  mov     r8, rsi
0x18000b5b3  mov     [rbp+arg_0], r14d
0x18000b5b7  mov     rdx, rdi
0x18000b5ba  lea     rcx, [rbp+arg_0]
0x18000b5be  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b5c3  mov     ebx, eax
0x18000b5c5  test    eax, eax
0x18000b5c7  js      loc_18000B656
0x18000b5cd  mov     r13d, [rbp+arg_0]
0x18000b5d1  mov     r12d, r14d
0x18000b5d4  test    r13d, r13d
0x18000b5d7  jle     short loc_18000B656
0x18000b5d9  mov     r8, rsi
0x18000b5dc  mov     [rbp+arg_0], r14d
0x18000b5e0  mov     rdx, rdi
0x18000b5e3  lea     rcx, [rbp+arg_0]
0x18000b5e7  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b5ec  mov     ebx, eax
0x18000b5ee  test    eax, eax
0x18000b5f0  js      short loc_18000B656
0x18000b5f2  lea     r14, [r15+0B8h]
0x18000b5f9  xor     r8d, r8d
0x18000b5fc  mov     rdx, [r14+8]
0x18000b600  mov     rcx, r14
0x18000b603  call    ?NewNode@?$CSPList@JJ@@IEAAPEAUCNode@1@PEAU21@0@Z; CSPList<long,long>::NewNode(CSPList<long,long>::CNode *,CSPList<long,long>::CNode *)
0x18000b608  xor     edx, edx
0x18000b60a  test    rax, rax
0x18000b60d  jz      loc_18000B2AC
0x18000b613  mov     ecx, [rbp+arg_0]
0x18000b616  mov     [rax+10h], ecx
0x18000b619  mov     rcx, [r14+8]
0x18000b61d  test    rcx, rcx
0x18000b620  jz      short loc_18000B63D
0x18000b622  mov     [rcx], rax
0x18000b625  jmp     short loc_18000B640
0x18000b627  mov     ebx, 8007000Eh
0x18000b62c  mov     rcx, r14; this
0x18000b62f  call    ??_GCAgreementElement@@QEAAPEAXI@Z; CAgreementElement::`scalar deleting destructor'(uint)
0x18000b634  jmp     short loc_18000B656
0x18000b636  mov     ebx, 80070057h
0x18000b63b  jmp     short loc_18000B656
0x18000b63d  mov     [r14], rax
0x18000b640  inc     r12d
0x18000b643  mov     [r14+8], rax
0x18000b647  mov     r14, rdx
0x18000b64a  cmp     r12d, r13d
0x18000b64d  jl      short loc_18000B5D9
0x18000b64f  jmp     short loc_18000B656
  ... truncated ...
```
