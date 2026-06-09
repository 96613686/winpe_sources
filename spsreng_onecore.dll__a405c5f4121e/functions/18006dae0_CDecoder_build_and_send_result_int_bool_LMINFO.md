# CDecoder::build_and_send_result(int *,bool,LMINFO *)

- ea: `0x18006dae0`
- end: `0x18006ddb7`
- name: `?build_and_send_result@CDecoder@@AEAAJPEAH_NPEAULMINFO@@@Z`
- size: `727`
- prototype: `__int64 __fastcall(CDecoder *__hidden this, int *, bool, struct LMINFO *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180070fa4`

## callees

- `0x180006684`
- `0x180006dbc`
- `0x180067518`
- `0x180067560`
- `0x18006b854`
- `0x18006dae0`
- `0x1800777d4`
- `0x180077e44`
- `0x18007c6a0`
- `0x180083578`
- `0x1800862cc`
- `0x18008683c`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006dcbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006dcce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006dcbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006dcce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dd7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dd7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006db1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006db1a`

## pseudocode

```c
__int64 __fastcall CDecoder::build_and_send_result(CDecoder *this, int *a2, char a3, struct LMINFO *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  CRecentReco *v6; // rdi
  int *v8; // r12
  int v9; // r15d
  int v10; // esi
  CUgtFilter *v11; // rcx
  int v12; // eax
  __int64 i; // rcx
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r14
  struct tagSPPHRASEALT *v19; // r12
  ISpPhraseBuilder *pPhrase; // rcx
  __int64 v21; // rcx
  __int64 result; // rax
  _BYTE v23[16]; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int16 *v24; // [rsp+70h] [rbp+40h] BYREF
  int *v25; // [rsp+78h] [rbp+48h]
  LPVOID pv; // [rsp+88h] [rbp+58h] BYREF

  v25 = a2;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 600);
  v6 = 0;
  pv = 0;
  v8 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 15);
  v9 = 1;
  v10 = CDecoder::BuildLattice(this, *((_DWORD *)this + 724), *((_DWORD *)this + 725), a3);
  if ( v10 || !*((_BYTE *)this + 2594) && !CDecoder::PhraseStartConditionHasBeenMet(this, 0) )
    goto LABEL_38;
  if ( !a3 )
  {
    if ( *((_BYTE *)this + 2549) )
    {
      v11 = (CUgtFilter *)*((_QWORD *)this + 407);
      if ( *((_BYTE *)v11 + 28) )
      {
        v10 = CUgtFilter::initialize(v11, this);
        if ( v10 < 0 )
          goto LABEL_38;
      }
    }
  }
  v12 = CDecoder::BuildRecoResult(this, (struct CRecentReco **)&pv, a3, 0);
  v6 = (CRecentReco *)pv;
  v10 = v12;
  if ( v12 < 0 || !pv )
    goto LABEL_38;
  if ( *((_BYTE *)this + 2594) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 596); i = (unsigned int)(i + 1) )
    {
      v14 = *((_QWORD *)this + 293);
      v15 = *(_DWORD *)(v14 + 48 * i) & 3;
      if ( v15 != 1 )
      {
        if ( v15 )
          continue;
        v16 = *(_QWORD *)(v14 + 48 * i + 24);
        if ( v16 )
        {
          if ( *(char *)(v16 + 40) >= 0 )
            continue;
        }
      }
      *(_DWORD *)(*((_QWORD *)pv + 8) + 4LL) |= 0x10u;
      break;
    }
  }
  else
  {
    v10 = CDecoder::DoAutoDetection(this, *((struct SPRECORESULTINFO **)pv + 8));
    if ( v10 < 0 )
      goto LABEL_38;
  }
  if ( *((_BYTE *)this + 2595) && *((_QWORD *)this + 959) )
  {
    v24 = 0;
    v17 = *((_QWORD *)v6 + 8);
    if ( *(_DWORD *)(v17 + 80) )
    {
      v18 = 0;
      do
      {
        v19 = (struct tagSPPHRASEALT *)(*(_QWORD *)(v17 + 72) + 40 * v18);
        ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(v23, v19->pPhrase);
        if ( (int)GetText(v23, 1, &v24) >= 0 )
        {
          pPhrase = v19->pPhrase;
          pv = 0;
          ((void (__fastcall *)(ISpPhraseBuilder *, LPVOID *))pPhrase->lpVtbl->GetPhrase)(pPhrase, &pv);
          if ( pv )
          {
            CPhraseStatContainer::AddEntry(*((CPhraseStatContainer **)this + 959), v19, v24, *((float *)pv + 22));
            CoTaskMemFree(pv);
          }
          if ( v24 )
            CoTaskMemFree(v24);
        }
        v17 = *((_QWORD *)v6 + 8);
        v18 = (unsigned int)(v18 + 1);
      }
      while ( (unsigned int)v18 < *(_DWORD *)(v17 + 80) );
      v8 = v25;
      v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 600);
    }
    v21 = *((_QWORD *)this + 959);
    if ( !*(_QWORD *)(v21 + 80) )
    {
      *(_QWORD *)(v21 + 80) = *(_QWORD *)(v17 + 64);
      *(_QWORD *)(*((_QWORD *)v6 + 8) + 64LL) = 0;
      *(_DWORD *)(*((_QWORD *)this + 959) + 100LL) = *(_DWORD *)(*((_QWORD *)v6 + 8) + 4LL);
      v17 = *((_QWORD *)this + 959);
      *(_QWORD *)(v17 + 104) = *(_QWORD *)(*((_QWORD *)v6 + 8) + 40LL);
    }
    if ( v6 )
      CRecentReco::`scalar deleting destructor'(v6, v17);
    v6 = 0;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, CRecentReco *, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 10) + 16LL) + 40LL))(
      *(_QWORD *)(*((_QWORD *)this + 10) + 16LL),
      v6,
      0);
  }
LABEL_38:
  CLatticeWrapper::ResetLatIndexesInBPTable(*((CLatticeWrapper **)this + 65), *((struct PATH_ENTRY **)this + 910));
  CDecoder::DiscardLattice(this);
  LeaveCriticalSection(v4);
  if ( !v6 || !*((_QWORD *)v6 + 8) || a3 )
    v9 = 0;
  result = (unsigned int)v10;
  *v8 = v9;
  return result;
}

```

## disassembly

```asm
0x18006dae0  mov     [rsp-38h+arg_10], rbx
0x18006dae5  mov     [rsp-38h+pv], r9
0x18006daea  mov     [rsp-38h+arg_8], rdx
0x18006daef  push    rbp
0x18006daf0  push    rsi
0x18006daf1  push    rdi
0x18006daf2  push    r12
0x18006daf4  push    r13
0x18006daf6  push    r14
0x18006daf8  push    r15
0x18006dafa  mov     rbp, rsp
0x18006dafd  sub     rsp, 30h
0x18006db01  lea     r14, [rcx+258h]
0x18006db08  mov     rbx, rcx
0x18006db0b  xor     edi, edi
0x18006db0d  mov     rcx, r14; lpCriticalSection
0x18006db10  mov     r13b, r8b
0x18006db13  mov     [rbp+pv], rdi
0x18006db17  mov     r12, rdx
0x18006db1a  call    cs:__imp_EnterCriticalSection
0x18006db20  mov     r8d, [rbx+0B54h]; int
0x18006db27  mov     r9b, r13b; bool
0x18006db2a  mov     edx, [rbx+0B50h]; unsigned int
0x18006db30  mov     rcx, rbx; this
0x18006db33  call    ?BuildLattice@CDecoder@@QEAAJIH_N@Z; CDecoder::BuildLattice(uint,int,bool)
0x18006db38  lea     r15d, [rdi+1]
0x18006db3c  mov     esi, eax
0x18006db3e  test    eax, eax
0x18006db40  jnz     loc_18006DD61
0x18006db46  cmp     [rbx+0A22h], dil
0x18006db4d  jnz     short loc_18006DB61
0x18006db4f  xor     edx, edx; bool
0x18006db51  mov     rcx, rbx; this
0x18006db54  call    ?PhraseStartConditionHasBeenMet@CDecoder@@QEAA_N_N@Z; CDecoder::PhraseStartConditionHasBeenMet(bool)
0x18006db59  test    al, al
0x18006db5b  jz      loc_18006DD61
0x18006db61  test    r13b, r13b
0x18006db64  jnz     short loc_18006DB8E
0x18006db66  cmp     [rbx+9F5h], dil
0x18006db6d  jz      short loc_18006DB8E
0x18006db6f  mov     rcx, [rbx+0CB8h]; this
0x18006db76  cmp     [rcx+1Ch], dil
0x18006db7a  jz      short loc_18006DB8E
0x18006db7c  mov     rdx, rbx; struct CDecoder *
0x18006db7f  call    ?initialize@CUgtFilter@@QEAAJPEAVCDecoder@@@Z; CUgtFilter::initialize(CDecoder *)
0x18006db84  mov     esi, eax
0x18006db86  test    eax, eax
0x18006db88  js      loc_18006DD61
0x18006db8e  xor     r9d, r9d; bool
0x18006db91  lea     rdx, [rbp+pv]; struct CRecentReco **
0x18006db95  mov     r8b, r13b; bool
0x18006db98  mov     rcx, rbx; this
0x18006db9b  call    ?BuildRecoResult@CDecoder@@QEAAJPEAPEAVCRecentReco@@_N1@Z; CDecoder::BuildRecoResult(CRecentReco * *,bool,bool)
0x18006dba0  mov     rdi, [rbp+pv]
0x18006dba4  mov     esi, eax
0x18006dba6  test    eax, eax
0x18006dba8  js      loc_18006DD61
0x18006dbae  test    rdi, rdi
0x18006dbb1  jz      loc_18006DD61
0x18006dbb7  cmp     byte ptr [rbx+0A22h], 0
0x18006dbbe  jnz     short loc_18006DBD8
0x18006dbc0  mov     rdx, [rdi+40h]; struct SPRECORESULTINFO *
0x18006dbc4  mov     rcx, rbx; this
0x18006dbc7  call    ?DoAutoDetection@CDecoder@@QEAAJPEAUSPRECORESULTINFO@@@Z; CDecoder::DoAutoDetection(SPRECORESULTINFO *)
0x18006dbcc  mov     esi, eax
0x18006dbce  test    eax, eax
0x18006dbd0  js      loc_18006DD61
0x18006dbd6  jmp     short loc_18006DC1D
0x18006dbd8  xor     ecx, ecx
0x18006dbda  cmp     ecx, [rbx+950h]
0x18006dbe0  jnb     short loc_18006DC1D
0x18006dbe2  mov     r8, [rbx+928h]
0x18006dbe9  lea     rdx, [rcx+rcx*2]
0x18006dbed  add     rdx, rdx
0x18006dbf0  mov     eax, [r8+rdx*8]
0x18006dbf4  and     eax, 3
0x18006dbf7  cmp     eax, r15d
0x18006dbfa  jz      short loc_18006DC15
0x18006dbfc  test    eax, eax
0x18006dbfe  jnz     short loc_18006DC10
0x18006dc00  mov     rax, [r8+rdx*8+18h]
0x18006dc05  test    rax, rax
0x18006dc08  jz      short loc_18006DC15
0x18006dc0a  test    byte ptr [rax+28h], 80h
0x18006dc0e  jnz     short loc_18006DC15
0x18006dc10  add     ecx, r15d
0x18006dc13  jmp     short loc_18006DBDA
0x18006dc15  mov     rax, [rdi+40h]
0x18006dc19  or      dword ptr [rax+4], 10h
0x18006dc1d  cmp     byte ptr [rbx+0A23h], 0
0x18006dc24  jz      loc_18006DD47
0x18006dc2a  cmp     qword ptr [rbx+1DF8h], 0
0x18006dc32  jz      loc_18006DD47
0x18006dc38  mov     [rbp+arg_0], 0
0x18006dc40  mov     rdx, [rdi+40h]
0x18006dc44  cmp     dword ptr [rdx+50h], 0
0x18006dc48  jbe     loc_18006DCF0
0x18006dc4e  xor     r14d, r14d
0x18006dc51  mov     rax, [rdx+48h]
0x18006dc55  lea     rcx, [r14+r14*4]
0x18006dc59  lea     r12, [rax+rcx*8]
0x18006dc5d  mov     rdx, [r12]
0x18006dc61  lea     rcx, [rbp+var_10]
0x18006dc65  call    ??0?$CComPtrBase@UIMSASRLocaleHandler@@@ATL@@IEAA@PEAUIMSASRLocaleHandler@@@Z; ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(IMSASRLocaleHandler *)
0x18006dc6a  lea     r8, [rbp+arg_0]
0x18006dc6e  mov     edx, r15d
0x18006dc71  lea     rcx, [rbp+var_10]
0x18006dc75  call    ?GetText@@YAJV?$CComPtr@UISpPhraseBuilder@@@ATL@@HPEAPEAG@Z; GetText(ATL::CComPtr<ISpPhraseBuilder>,int,ushort * *)
0x18006dc7a  test    eax, eax
0x18006dc7c  js      short loc_18006DCD4
0x18006dc7e  mov     rcx, [r12]
0x18006dc82  lea     rdx, [rbp+pv]
0x18006dc86  mov     [rbp+pv], 0
0x18006dc8e  mov     rax, [rcx]
0x18006dc91  mov     rax, [rax+18h]
0x18006dc95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dc9a  mov     rax, [rbp+pv]
0x18006dc9e  test    rax, rax
0x18006dca1  jz      short loc_18006DCC5
0x18006dca3  movss   xmm3, dword ptr [rax+58h]; float
0x18006dca8  mov     rdx, r12; struct tagSPPHRASEALT *
0x18006dcab  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x18006dcaf  mov     rcx, [rbx+1DF8h]; this
0x18006dcb6  call    ?AddEntry@CPhraseStatContainer@@QEAAJPEAUtagSPPHRASEALT@@PEBGM@Z; CPhraseStatContainer::AddEntry(tagSPPHRASEALT *,ushort const *,float)
0x18006dcbb  mov     rcx, [rbp+pv]; pv
0x18006dcbf  call    cs:__imp_CoTaskMemFree
0x18006dcc5  mov     rcx, [rbp+arg_0]; pv
0x18006dcc9  test    rcx, rcx
0x18006dccc  jz      short loc_18006DCD4
0x18006dcce  call    cs:__imp_CoTaskMemFree
0x18006dcd4  mov     rdx, [rdi+40h]
0x18006dcd8  add     r14d, r15d
0x18006dcdb  cmp     r14d, [rdx+50h]
0x18006dcdf  jb      loc_18006DC51
0x18006dce5  mov     r12, [rbp+arg_8]
0x18006dce9  lea     r14, [rbx+258h]
0x18006dcf0  mov     rcx, [rbx+1DF8h]
0x18006dcf7  cmp     qword ptr [rcx+50h], 0
0x18006dcfc  jnz     short loc_18006DD36
0x18006dcfe  mov     rax, [rdx+40h]
0x18006dd02  mov     [rcx+50h], rax
0x18006dd06  mov     rax, [rdi+40h]
0x18006dd0a  mov     qword ptr [rax+40h], 0
0x18006dd12  mov     rax, [rdi+40h]
0x18006dd16  mov     rdx, [rbx+1DF8h]
0x18006dd1d  mov     eax, [rax+4]
0x18006dd20  mov     [rdx+64h], eax
0x18006dd23  mov     rax, [rdi+40h]
0x18006dd27  mov     rdx, [rbx+1DF8h]; unsigned int
0x18006dd2e  mov     rax, [rax+28h]
0x18006dd32  mov     [rdx+68h], rax
0x18006dd36  test    rdi, rdi
0x18006dd39  jz      short loc_18006DD43
0x18006dd3b  mov     rcx, rdi; this
0x18006dd3e  call    ??_GCRecentReco@@QEAAPEAXI@Z; CRecentReco::`scalar deleting destructor'(uint)
0x18006dd43  xor     edi, edi
0x18006dd45  jmp     short loc_18006DD61
0x18006dd47  mov     rax, [rbx+50h]
0x18006dd4b  xor     r8d, r8d
0x18006dd4e  mov     rdx, rdi
0x18006dd51  mov     rcx, [rax+10h]
0x18006dd55  mov     rax, [rcx]
0x18006dd58  mov     rax, [rax+28h]
0x18006dd5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd61  mov     rdx, [rbx+1C70h]; struct PATH_ENTRY *
0x18006dd68  mov     rcx, [rbx+208h]; this
0x18006dd6f  call    ?ResetLatIndexesInBPTable@CLatticeWrapper@@IEAAXPEAUPATH_ENTRY@@@Z; CLatticeWrapper::ResetLatIndexesInBPTable(PATH_ENTRY *)
0x18006dd74  mov     rcx, rbx; this
0x18006dd77  call    ?DiscardLattice@CDecoder@@QEAAXXZ; CDecoder::DiscardLattice(void)
0x18006dd7c  mov     rcx, r14; lpCriticalSection
0x18006dd7f  call    cs:__imp_LeaveCriticalSection
0x18006dd85  test    rdi, rdi
0x18006dd88  jz      short loc_18006DD96
0x18006dd8a  cmp     qword ptr [rdi+40h], 0
0x18006dd8f  jz      short loc_18006DD96
0x18006dd91  test    r13b, r13b
0x18006dd94  jz      short loc_18006DD99
0x18006dd96  xor     r15d, r15d
0x18006dd99  mov     rbx, [rsp+30h+arg_10]
0x18006dda1  mov     eax, esi
0x18006dda3  mov     [r12], r15d
0x18006dda7  add     rsp, 30h
0x18006ddab  pop     r15
0x18006ddad  pop     r14
0x18006ddaf  pop     r13
0x18006ddb1  pop     r12
0x18006ddb3  pop     rdi
0x18006ddb4  pop     rsi
0x18006ddb5  pop     rbp
0x18006ddb6  retn
```
