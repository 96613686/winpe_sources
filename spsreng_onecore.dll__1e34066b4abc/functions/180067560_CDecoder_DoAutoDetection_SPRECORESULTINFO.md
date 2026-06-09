# CDecoder::DoAutoDetection(SPRECORESULTINFO *)

- ea: `0x180067560`
- end: `0x180067763`
- name: `?DoAutoDetection@CDecoder@@QEAAJPEAUSPRECORESULTINFO@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(CDecoder *__hidden this, struct SPRECORESULTINFO *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006dae0`

## callees

- `0x180002aac`
- `0x180067560`
- `0x180070c24`
- `0x18007e420`
- `0x18007eb3c`
- `0x1800aa344`
- `0x1800aa564`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067749`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067749`

## pseudocode

```c
__int64 __fastcall CDecoder::DoAutoDetection(CDecoder *this, struct SPRECORESULTINFO *a2)
{
  int v3; // edi
  __int64 v4; // rcx
  const struct SPPHRASEELEMENT *v5; // r14
  int v6; // r15d
  SPPHRASEALT *aPhraseAlts; // rcx
  int v8; // esi
  struct CHeap *v9; // rdx
  CStreamPair *v10; // rcx
  int v11; // r8d
  __int64 v12; // rcx
  int v13; // esi
  unsigned int v15; // [rsp+50h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-31h] BYREF
  unsigned int *v17; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v18; // [rsp+F0h] [rbp+67h] BYREF
  int i; // [rsp+100h] [rbp+77h] BYREF
  int v20; // [rsp+108h] [rbp+7Fh] BYREF

  v3 = 0;
  pv = 0;
  if ( !*((_BYTE *)this + 2594) )
  {
    v4 = *(_QWORD *)(*((_QWORD *)this + 10) + 80LL);
    if ( *(_BYTE *)(v4 + 24) )
    {
      if ( *(_BYTE *)(v4 + 96) )
      {
        v5 = 0;
        v6 = 0;
        if ( !*(_DWORD *)(*((_QWORD *)this + 859)
                        + 48LL
                        * (unsigned int)_mm_extract_epi16(
                                          *(__m128i *)(*((_QWORD *)this + 910)
                                                     + 72LL * *((unsigned int *)this + 724)
                                                     + 48),
                                          7)
                        + 16)
          && !*((_BYTE *)this + 2987) )
        {
          if ( a2 )
          {
            aPhraseAlts = a2->aPhraseAlts;
            if ( aPhraseAlts )
            {
              if ( ((int (__fastcall *)(SPPHRASEALT *, LPVOID *))aPhraseAlts->pPhrase[3].lpVtbl)(aPhraseAlts, &pv) >= 0 )
              {
                v5 = (const struct SPPHRASEELEMENT *)*((_QWORD *)pv + 13);
                v6 = *((_DWORD *)pv + 16);
              }
            }
          }
        }
        v3 = CStreamPair::Rewind(*(CStreamPair **)(*((_QWORD *)this + 10) + 152LL));
        if ( v3 >= 0 )
        {
          v8 = 0;
          v20 = 0;
          for ( i = 0; ; v8 += i - v20 )
          {
            v9 = (struct CHeap *)*((_QWORD *)this + 9);
            v10 = *(CStreamPair **)(*((_QWORD *)this + 10) + 152LL);
            LOBYTE(v18) = 0;
            v15 = 0;
            v17 = 0;
            v3 = CStreamPair::ReadUnit(v10, v9, 0, (bool *)&v18, &v20, &i, &v15, &v17, 0, 0);
            if ( v3 < 0 )
              break;
            CWinHeap::Free(*((CWinHeap **)this + 9), v17);
            if ( v3 )
            {
              v3 = 0;
              CAutoDetect::SegmentPhones(*(CAutoDetect **)(*((_QWORD *)this + 10) + 80LL), v5, v8, v6);
              v11 = *((_DWORD *)this + 1604) * (*((_DWORD *)this + 750) + *((_DWORD *)this + 1601));
              v12 = *((_QWORD *)this + 10);
              v18 = -1;
              if ( !CAutoDetect::ChooseModel(*(CAutoDetect **)(v12 + 80), (int *)&v18, *((_DWORD *)this + 1602) + v11) )
              {
                v13 = v18;
                if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 10) + 16LL) + 72LL))(
                       *(_QWORD *)(*((_QWORD *)this + 10) + 16LL),
                       v18) == 1 )
                  CDecoder::search_activate_model(this, v13);
                *((_BYTE *)this + 2554) = v13 + 1;
              }
              break;
            }
          }
        }
        if ( pv )
          CoTaskMemFree(pv);
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180067560  push    rbp
0x180067562  push    rbx
0x180067563  push    rsi
0x180067564  push    rdi
0x180067565  push    r12
0x180067567  push    r14
0x180067569  push    r15
0x18006756b  lea     rbp, [rsp-27h]
0x180067570  sub     rsp, 0B0h
0x180067577  xor     r12d, r12d
0x18006757a  mov     r8, rdx
0x18006757d  mov     rbx, rcx
0x180067580  mov     edi, r12d
0x180067583  mov     [rbp+57h+pv], r12
0x180067587  cmp     [rcx+0A22h], r12b
0x18006758e  jnz     loc_18006774F
0x180067594  mov     rax, [rcx+50h]
0x180067598  mov     rcx, [rax+50h]
0x18006759c  cmp     [rcx+18h], r12b
0x1800675a0  jz      loc_18006774F
0x1800675a6  cmp     [rcx+60h], r12b
0x1800675aa  jz      loc_18006774F
0x1800675b0  mov     eax, [rbx+0B50h]
0x1800675b6  mov     r14d, r12d
0x1800675b9  mov     r15d, r12d
0x1800675bc  lea     rcx, [rax+rax*8]
0x1800675c0  mov     rax, [rbx+1C70h]
0x1800675c7  movups  xmm1, xmmword ptr [rax+rcx*8+30h]
0x1800675cc  mov     rax, [rbx+1AD8h]
0x1800675d3  pextrw  ecx, xmm1, 7
0x1800675d8  lea     rdx, [rcx+rcx*2]
0x1800675dc  add     rdx, rdx
0x1800675df  cmp     [rax+rdx*8+10h], r12d
0x1800675e4  jnz     short loc_18006761D
0x1800675e6  cmp     [rbx+0BABh], r12b
0x1800675ed  jnz     short loc_18006761D
0x1800675ef  test    r8, r8
0x1800675f2  jz      short loc_18006761D
0x1800675f4  mov     rcx, [r8+40h]
0x1800675f8  test    rcx, rcx
0x1800675fb  jz      short loc_18006761D
0x1800675fd  mov     rax, [rcx]
0x180067600  lea     rdx, [rbp+57h+pv]
0x180067604  mov     rax, [rax+18h]
0x180067608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006760d  test    eax, eax
0x18006760f  js      short loc_18006761D
0x180067611  mov     rax, [rbp+57h+pv]
0x180067615  mov     r14, [rax+68h]
0x180067619  mov     r15d, [rax+40h]
0x18006761d  mov     rcx, [rbx+50h]
0x180067621  mov     rcx, [rcx+98h]; this
0x180067628  call    ?Rewind@CStreamPair@@QEAAJXZ; CStreamPair::Rewind(void)
0x18006762d  mov     edi, eax
0x18006762f  test    eax, eax
0x180067631  js      loc_180067740
0x180067637  mov     esi, r12d
0x18006763a  mov     [rbp+57h+arg_18], r12d
0x18006763e  mov     [rbp+57h+arg_10], r12d
0x180067642  mov     rcx, [rbx+50h]
0x180067646  lea     rax, [rbp+57h+var_80]
0x18006764a  mov     rdx, [rbx+48h]; struct CHeap *
0x18006764e  lea     r9, [rbp+57h+arg_0]; bool *
0x180067652  mov     [rsp+0E0h+var_98], r12; bool *
0x180067657  xor     r8d, r8d; bool *
0x18006765a  mov     [rsp+0E0h+var_A0], r12; unsigned __int16 **
0x18006765f  mov     rcx, [rcx+98h]; this
0x180067666  mov     [rsp+0E0h+var_A8], rax; unsigned int **
0x18006766b  lea     rax, [rbp+57h+var_90]
0x18006766f  mov     [rsp+0E0h+var_B0], rax; unsigned int *
0x180067674  lea     rax, [rbp+57h+arg_10]
0x180067678  mov     [rsp+0E0h+var_B8], rax; int *
0x18006767d  lea     rax, [rbp+57h+arg_18]
0x180067681  mov     [rsp+0E0h+var_C0], rax; int *
0x180067686  mov     byte ptr [rbp+57h+arg_0], r12b
0x18006768a  mov     [rbp+57h+var_90], r12d
0x18006768e  mov     [rbp+57h+var_80], r12
0x180067692  call    ?ReadUnit@CStreamPair@@QEAAJPEAVCHeap@@PEA_N1PEAH2PEAIPEAPEAIPEAPEAG1@Z; CStreamPair::ReadUnit(CHeap *,bool *,bool *,int *,int *,uint *,uint * *,ushort * *,bool *)
0x180067697  mov     edi, eax
0x180067699  test    eax, eax
0x18006769b  js      loc_180067740
0x1800676a1  mov     rdx, [rbp+57h+var_80]; void *
0x1800676a5  mov     rcx, [rbx+48h]; this
0x1800676a9  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800676ae  test    edi, edi
0x1800676b0  jnz     short loc_1800676BC
0x1800676b2  mov     eax, [rbp+57h+arg_10]
0x1800676b5  sub     eax, [rbp+57h+arg_18]
0x1800676b8  add     esi, eax
0x1800676ba  jmp     short loc_180067642
0x1800676bc  mov     rcx, [rbx+50h]
0x1800676c0  mov     r9d, r15d; int
0x1800676c3  mov     r8d, esi; int
0x1800676c6  mov     rdx, r14; struct SPPHRASEELEMENT *
0x1800676c9  mov     edi, r12d
0x1800676cc  mov     rcx, [rcx+50h]; this
0x1800676d0  call    ?SegmentPhones@CAutoDetect@@QEAAJPEBUSPPHRASEELEMENT@@HH@Z; CAutoDetect::SegmentPhones(SPPHRASEELEMENT const *,int,int)
0x1800676d5  mov     r8d, [rbx+1904h]
0x1800676dc  lea     rdx, [rbp+57h+arg_0]; int *
0x1800676e0  add     r8d, [rbx+0BB8h]
0x1800676e7  imul    r8d, [rbx+1910h]
0x1800676ef  mov     rcx, [rbx+50h]
0x1800676f3  mov     [rbp+57h+arg_0], 0FFFFFFFFh
0x1800676fa  add     r8d, [rbx+1908h]; int
0x180067701  mov     rcx, [rcx+50h]; this
0x180067705  call    ?ChooseModel@CAutoDetect@@QEAA_NPEAHH@Z; CAutoDetect::ChooseModel(int *,int)
0x18006770a  test    al, al
0x18006770c  jnz     short loc_180067740
0x18006770e  mov     rax, [rbx+50h]
0x180067712  mov     esi, [rbp+57h+arg_0]
0x180067715  mov     edx, esi
0x180067717  mov     rcx, [rax+10h]
0x18006771b  mov     rax, [rcx]
0x18006771e  mov     rax, [rax+48h]
0x180067722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067727  cmp     eax, 1
0x18006772a  jnz     short loc_180067736
0x18006772c  mov     edx, esi; int
0x18006772e  mov     rcx, rbx; this
0x180067731  call    ?search_activate_model@CDecoder@@QEAAXH@Z; CDecoder::search_activate_model(int)
0x180067736  inc     sil
0x180067739  mov     [rbx+9FAh], sil
0x180067740  mov     rcx, [rbp+57h+pv]; pv
0x180067744  test    rcx, rcx
0x180067747  jz      short loc_18006774F
0x180067749  call    cs:__imp_CoTaskMemFree
0x18006774f  mov     eax, edi
0x180067751  add     rsp, 0B0h
0x180067758  pop     r15
0x18006775a  pop     r14
0x18006775c  pop     r12
0x18006775e  pop     rdi
0x18006775f  pop     rsi
0x180067760  pop     rbx
0x180067761  pop     rbp
0x180067762  retn
```
