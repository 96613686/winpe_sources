# CDecoder::SendFinalSimulationResult(void)

- ea: `0x18006c3a8`
- end: `0x18006c5b6`
- name: `?SendFinalSimulationResult@CDecoder@@AEAAJXZ`
- size: `526`
- prototype: `__int64 __fastcall(CDecoder *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800131c4`

## callees

- `0x180002470`
- `0x1800040b8`
- `0x1800062a0`
- `0x180006dbc`
- `0x18006c3a8`
- `0x180079fd8`
- `0x180086468`
- `0x180086578`
- `0x180086740`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c549`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c549`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006c48f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006c48f`

## pseudocode

```c
__int64 __fastcall CDecoder::SendFinalSimulationResult(CDecoder *this)
{
  __int64 v1; // rbx
  __int64 v4; // r15
  struct SPRECORESULTINFO *v5; // rax
  struct SPRECORESULTINFO *v6; // rdi
  _QWORD *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // r14
  struct tagSPPHRASEALT *v10; // rax
  int v11; // ebp
  SPPHRASEALT *aPhraseAlts; // rcx
  unsigned int v13; // edx
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 959);
  if ( !v1 )
    return 0;
  if ( !*(_QWORD *)(v1 + 80) )
  {
    CPhraseStatContainer::Flush(*((CPhraseStatContainer **)this + 959));
    return 0;
  }
  if ( !*(_BYTE *)(v1 + 92) )
    CPhraseStatContainer::SortEntry(*((CPhraseStatContainer **)this + 959));
  v4 = *(unsigned int *)(v1 + 88);
  v5 = (struct SPRECORESULTINFO *)CWinHeap::Alloc(&g_heap, 0x58u, 0);
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  memset_0(&v5->fHypothesis, 0, sizeof(struct SPRECORESULTINFO));
  v6->cbSize = 88;
  v6->eResultType = 32;
  v7 = CAllocOnSpecificHeapBase::operator_new(0x58u, *((struct CHeap **)this + 9), 0);
  if ( !v7 )
  {
    v7 = 0;
    v9 = 64;
    goto LABEL_17;
  }
  v8 = *((_QWORD *)this + 9);
  v9 = (__int64)(v7 + 8);
  v7[10] = 0;
  *v7 = v8;
  v10 = 0;
  v7[3] = 0;
  v7[4] = 0;
  v7[5] = 0;
  v7[6] = 0;
  *((_WORD *)v7 + 28) = 0;
  *((_DWORD *)v7 + 18) = 0;
  v7[1] = 0;
  v7[2] = 0;
  v7[8] = v6;
  if ( (_DWORD)v4 )
  {
    v10 = (struct tagSPPHRASEALT *)CoTaskMemAlloc(40 * v4);
    if ( !v10 )
    {
LABEL_17:
      FreeRecoResult(v6);
      if ( v7 )
      {
        *(_QWORD *)v9 = 0;
        CRecentReco::`scalar deleting destructor'((CRecentReco *)v7, v13);
      }
      return 2147942414LL;
    }
  }
  *(_QWORD *)&v6->ulNumAlts = v10;
  v6[1].cbSize = v4;
  v11 = 0;
  CPhraseStatContainer::CopyAlternates(*((CPhraseStatContainer **)this + 959), v10, v4);
  v6->aPhraseAlts = *(SPPHRASEALT **)(*((_QWORD *)this + 959) + 80LL);
  *(_QWORD *)(*((_QWORD *)this + 959) + 80LL) = 0;
  v6->eResultType = *(_DWORD *)(*((_QWORD *)this + 959) + 100LL);
  *(_QWORD *)&v6->ulSizeEngineData = *(_QWORD *)(*((_QWORD *)this + 959) + 104LL);
  pv = 0;
  aPhraseAlts = v6->aPhraseAlts;
  if ( aPhraseAlts )
  {
    v11 = ((__int64 (__fastcall *)(SPPHRASEALT *, LPVOID *))aPhraseAlts->pPhrase[3].lpVtbl)(aPhraseAlts, &pv);
    if ( pv )
    {
      if ( v11 >= 0 )
      {
        *((_QWORD *)pv + 3) = 0;
        *((_DWORD *)pv + 8) = 0;
        v11 = ((__int64 (__fastcall *)(SPPHRASEALT *, LPVOID))v6->aPhraseAlts->pPhrase[7].lpVtbl)(v6->aPhraseAlts, pv);
        CoTaskMemFree(pv);
      }
    }
  }
  (*(void (__fastcall **)(_QWORD, _QWORD *, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 10) + 16LL) + 40LL))(
    *(_QWORD *)(*((_QWORD *)this + 10) + 16LL),
    v7,
    0);
  CPhraseStatContainer::Flush(*((CPhraseStatContainer **)this + 959));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18006c3a8  mov     [rsp+arg_8], rbx
0x18006c3ad  mov     [rsp+arg_10], rbp
0x18006c3b2  push    rsi
0x18006c3b3  push    rdi
0x18006c3b4  push    r12
0x18006c3b6  push    r14
0x18006c3b8  push    r15
0x18006c3ba  sub     rsp, 20h
0x18006c3be  mov     rbx, [rcx+1DF8h]
0x18006c3c5  xor     r12d, r12d
0x18006c3c8  mov     rsi, rcx
0x18006c3cb  test    rbx, rbx
0x18006c3ce  jnz     short loc_18006C3D7
0x18006c3d0  xor     eax, eax
0x18006c3d2  jmp     loc_18006C59F
0x18006c3d7  cmp     [rbx+50h], r12
0x18006c3db  jnz     short loc_18006C3E7
0x18006c3dd  mov     rcx, rbx; this
0x18006c3e0  call    ?Flush@CPhraseStatContainer@@QEAAXXZ; CPhraseStatContainer::Flush(void)
0x18006c3e5  jmp     short loc_18006C3D0
0x18006c3e7  cmp     [rbx+5Ch], r12b
0x18006c3eb  jnz     short loc_18006C3F5
0x18006c3ed  mov     rcx, rbx; this
0x18006c3f0  call    ?SortEntry@CPhraseStatContainer@@AEAAXXZ; CPhraseStatContainer::SortEntry(void)
0x18006c3f5  mov     r15d, [rbx+58h]
0x18006c3f9  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18006c400  xor     r8d, r8d; bool
0x18006c403  lea     ebx, [r8+58h]
0x18006c407  mov     edx, ebx; unsigned __int64
0x18006c409  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x18006c40e  mov     rdi, rax
0x18006c411  test    rax, rax
0x18006c414  jz      loc_18006C59A
0x18006c41a  lea     rcx, [rax+8]; void *
0x18006c41e  xor     edx, edx; Val
0x18006c420  lea     r8d, [rbx-8]; Size
0x18006c424  call    memset_0
0x18006c429  mov     [rdi], ebx
0x18006c42b  xor     r8d, r8d; bool
0x18006c42e  mov     dword ptr [rdi+4], 20h ; ' '
0x18006c435  mov     ecx, ebx; unsigned __int64
0x18006c437  mov     rdx, [rsi+48h]; struct CHeap *
0x18006c43b  call    ?operator_new@CAllocOnSpecificHeapBase@@SAPEAX_KPEAVCHeap@@_N@Z; CAllocOnSpecificHeapBase::operator_new(unsigned __int64,CHeap *,bool)
0x18006c440  mov     rbx, rax
0x18006c443  test    rax, rax
0x18006c446  jz      loc_18006C579
0x18006c44c  mov     rax, [rsi+48h]
0x18006c450  lea     r14, [rbx+40h]
0x18006c454  mov     [rbx+50h], r12
0x18006c458  mov     [rbx], rax
0x18006c45b  mov     rax, r12
0x18006c45e  mov     [rbx+18h], r12
0x18006c462  mov     [rbx+20h], r12
0x18006c466  mov     [rbx+28h], r12
0x18006c46a  mov     [rbx+30h], r12
0x18006c46e  mov     [rbx+38h], r12w
0x18006c473  mov     [rbx+48h], r12d
0x18006c477  mov     [rbx+8], r12
0x18006c47b  mov     [rbx+10h], r12
0x18006c47f  mov     [r14], rdi
0x18006c482  test    r15d, r15d
0x18006c485  jz      short loc_18006C49E
0x18006c487  lea     rcx, [r15+r15*4]
0x18006c48b  shl     rcx, 3; cb
0x18006c48f  call    cs:__imp_CoTaskMemAlloc
0x18006c495  test    rax, rax
0x18006c498  jz      loc_18006C582
0x18006c49e  mov     [rdi+48h], rax
0x18006c4a2  mov     r8d, r15d; unsigned int
0x18006c4a5  mov     [rdi+50h], r15d
0x18006c4a9  mov     rdx, rax; struct tagSPPHRASEALT *
0x18006c4ac  mov     rcx, [rsi+1DF8h]; this
0x18006c4b3  mov     ebp, r12d
0x18006c4b6  call    ?CopyAlternates@CPhraseStatContainer@@QEAAXPEAUtagSPPHRASEALT@@K@Z; CPhraseStatContainer::CopyAlternates(tagSPPHRASEALT *,ulong)
0x18006c4bb  mov     rax, [rsi+1DF8h]
0x18006c4c2  mov     rcx, [rax+50h]
0x18006c4c6  mov     [rdi+40h], rcx
0x18006c4ca  mov     rax, [rsi+1DF8h]
0x18006c4d1  mov     [rax+50h], r12
0x18006c4d5  mov     rax, [rsi+1DF8h]
0x18006c4dc  mov     ecx, [rax+64h]
0x18006c4df  mov     [rdi+4], ecx
0x18006c4e2  mov     rax, [rsi+1DF8h]
0x18006c4e9  mov     rcx, [rax+68h]
0x18006c4ed  mov     [rdi+28h], rcx
0x18006c4f1  mov     [rsp+48h+pv], r12
0x18006c4f6  mov     rcx, [rdi+40h]
0x18006c4fa  test    rcx, rcx
0x18006c4fd  jz      short loc_18006C54F
0x18006c4ff  mov     rax, [rcx]
0x18006c502  lea     rdx, [rsp+48h+pv]
0x18006c507  mov     rax, [rax+18h]
0x18006c50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c510  mov     ebp, eax
0x18006c512  mov     rax, [rsp+48h+pv]
0x18006c517  test    rax, rax
0x18006c51a  jz      short loc_18006C54F
0x18006c51c  test    ebp, ebp
0x18006c51e  js      short loc_18006C54F
0x18006c520  mov     [rax+18h], r12
0x18006c524  mov     rax, [rsp+48h+pv]
0x18006c529  mov     [rax+20h], r12d
0x18006c52d  mov     rcx, [rdi+40h]
0x18006c531  mov     rdx, [rsp+48h+pv]
0x18006c536  mov     rax, [rcx]
0x18006c539  mov     rax, [rax+38h]
0x18006c53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c542  mov     rcx, [rsp+48h+pv]; pv
0x18006c547  mov     ebp, eax
0x18006c549  call    cs:__imp_CoTaskMemFree
0x18006c54f  mov     rax, [rsi+50h]
0x18006c553  xor     r8d, r8d
0x18006c556  mov     rdx, rbx
0x18006c559  mov     rcx, [rax+10h]
0x18006c55d  mov     rax, [rcx]
0x18006c560  mov     rax, [rax+28h]
0x18006c564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c569  mov     rcx, [rsi+1DF8h]; this
0x18006c570  call    ?Flush@CPhraseStatContainer@@QEAAXXZ; CPhraseStatContainer::Flush(void)
0x18006c575  mov     eax, ebp
0x18006c577  jmp     short loc_18006C59F
0x18006c579  mov     rbx, r12
0x18006c57c  mov     r14d, 40h ; '@'
0x18006c582  mov     rcx, rdi; struct SPRECORESULTINFO *
0x18006c585  call    ?FreeRecoResult@@YAXPEAUSPRECORESULTINFO@@@Z; FreeRecoResult(SPRECORESULTINFO *)
0x18006c58a  test    rbx, rbx
0x18006c58d  jz      short loc_18006C59A
0x18006c58f  mov     rcx, rbx; this
0x18006c592  mov     [r14], r12
0x18006c595  call    ??_GCRecentReco@@QEAAPEAXI@Z; CRecentReco::`scalar deleting destructor'(uint)
0x18006c59a  mov     eax, 8007000Eh
0x18006c59f  mov     rbx, [rsp+48h+arg_8]
0x18006c5a4  mov     rbp, [rsp+48h+arg_10]
0x18006c5a9  add     rsp, 20h
0x18006c5ad  pop     r15
0x18006c5af  pop     r14
0x18006c5b1  pop     r12
0x18006c5b3  pop     rdi
0x18006c5b4  pop     rsi
0x18006c5b5  retn
```
