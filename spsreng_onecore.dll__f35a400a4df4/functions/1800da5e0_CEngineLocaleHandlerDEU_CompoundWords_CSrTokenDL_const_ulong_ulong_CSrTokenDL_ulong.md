# CEngineLocaleHandlerDEU::CompoundWords(CSrTokenDL const *,ulong,ulong,CSrTokenDL *,ulong *)

- ea: `0x1800da5e0`
- end: `0x1800daa3b`
- name: `?CompoundWords@CEngineLocaleHandlerDEU@@MEAAJPEBVCSrTokenDL@@KKPEAV2@PEAK@Z`
- size: `1115`
- prototype: `__int64 __fastcall(CEngineLocaleHandlerDEU *__hidden this, const struct CSrTokenDL *, unsigned int, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002470`
- `0x180002db8`
- `0x1800034b0`
- `0x1800061d0`
- `0x1800979b0`
- `0x180097db0`
- `0x1800b36c4`
- `0x1800c681c`
- `0x1800c68e8`
- `0x1800c6938`
- `0x1800da5e0`
- `0x1800daaac`
- `0x1800dab14`
- `0x1800dad14`
- `0x1800e3c18`
- `0x1800f6bc8`
- `0x1800ff490`
- `0x180102010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800da745`
- `OLEAUT32!__imp_SysFreeString` at `0x1800da745`

## string_xrefs

- `0x1800da662`: `Compound`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CEngineLocaleHandlerDEU::CompoundWords(
        CEngineLocaleHandlerDEU *this,
        const struct CSrTokenDL *a2,
        unsigned int a3,
        int a4,
        unsigned __int16 **a5,
        unsigned int *a6)
{
  __int64 v6; // r15
  int NextCompoundElement; // ebx
  _QWORD *v10; // rax
  int v11; // r8d
  CatLex *v12; // r13
  unsigned __int16 v13; // r12
  unsigned __int16 v14; // r13
  unsigned __int16 v15; // ax
  unsigned int v16; // r12d
  CEngineLocaleHandlerDEU *v17; // rcx
  const struct CSrTokenDL *v18; // r9
  __int64 v19; // r13
  unsigned __int16 *v20; // r12
  int v21; // r13d
  unsigned __int16 *v22; // rbx
  unsigned __int64 v23; // r8
  CEngineLocaleHandlerDEU *v24; // rcx
  CEngineLocaleHandlerDEU *v25; // rcx
  int v26; // esi
  CSrTokenDL *v27; // rcx
  CSrTokenDL *v28; // rcx
  unsigned int v29; // edx
  CSrTokenDL *v30; // rcx
  CSrTokenDL *v31; // rcx
  unsigned int *v33; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v34; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v35; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v36; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v37; // [rsp+62h] [rbp-9Eh]
  unsigned __int16 v38; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 *v39; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+70h] [rbp-90h]
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  unsigned int *v42; // [rsp+80h] [rbp-80h]
  _QWORD v43[3]; // [rsp+88h] [rbp-78h] BYREF
  int v44; // [rsp+A0h] [rbp-60h]
  __int64 v45; // [rsp+A8h] [rbp-58h]
  _QWORD *v46; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v47[1000]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v48[1000]; // [rsp+890h] [rbp+790h] BYREF

  v40 = a4;
  v6 = a3;
  v42 = a6;
  NextCompoundElement = 0;
  *a6 = 0;
  if ( *((_QWORD *)this + 45) )
    goto LABEL_30;
  v35 = 0;
  v39 = 0;
  NextCompoundElement = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int16 **))(**((_QWORD **)this + 4)
                                                                                                + 72LL))(
                          *((_QWORD *)this + 4),
                          L"Compound",
                          &v35);
  if ( NextCompoundElement >= 0 )
  {
    NextCompoundElement = (*(__int64 (__fastcall **)(unsigned __int16 *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v35 + 48LL))(
                            v35,
                            L"DataFile",
                            &v39);
    if ( NextCompoundElement >= 0 )
    {
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v39);
      v43[1] = 0;
      v43[2] = 0;
      v44 = 0;
      v43[0] = &CSequentialReadFile::`vftable';
      v45 = 0;
      v10 = CWinHeap::Alloc((CWinHeap *)&g_heap, 0x10u, 0);
      v46 = v10;
      if ( v10 )
      {
        *(_DWORD *)v10 = 0;
        v10[1] = 0;
        *((_QWORD *)this + 45) = v10;
        NextCompoundElement = CSequentialReadFile::Open((CSequentialReadFile *)v43, v39, v11);
        if ( NextCompoundElement >= 0 )
        {
          NextCompoundElement = CatLex::Deserial(*((CatLex **)this + 45), (struct CSequentialRead *)v43);
          CSequentialReadFile::Close((CSequentialReadFile *)v43);
        }
      }
      else
      {
        *((_QWORD *)this + 45) = 0;
        NextCompoundElement = -2147024882;
      }
      CSequentialReadFile::~CSequentialReadFile((CSequentialReadFile *)v43);
      SysFreeString(bstrString);
    }
  }
  CSpDynamicString::_free((LPVOID *)&v39);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v35);
  if ( NextCompoundElement >= 0 )
  {
LABEL_30:
    v12 = (CatLex *)*((_QWORD *)this + 45);
    v34 = CatLex::Name2ID(v12, L"Preposition");
    v13 = CatLex::Name2ID(v12, L"SegBound");
    v38 = v13;
    v14 = CatLex::Name2ID(v12, L"StandaloneNoFinal");
    v37 = v14;
    v15 = CatLex::Name2ID(*((CatLex **)this + 45), L"Standalone");
    v36 = v15;
    if ( v34 == 0xFFFF || v13 == 0xFFFF || v14 == 0xFFFF || v15 == 0xFFFF )
      NextCompoundElement = -2147467259;
    if ( NextCompoundElement >= 0 )
    {
      LODWORD(bstrString) = 0;
      LODWORD(v35) = 0;
      LODWORD(v39) = 0;
      v16 = v6 + v40;
      NextCompoundElement = CEngineLocaleHandlerDEU::GetNextCompoundElement(
                              (CEngineLocaleHandlerDEU *)0xFFFF,
                              v6,
                              (int)v6 + v40,
                              a2,
                              (unsigned int *)&bstrString);
      if ( !NextCompoundElement )
      {
        v19 = (unsigned int)bstrString;
        NextCompoundElement = CEngineLocaleHandlerDEU::GetNextCompoundElement(
                                v17,
                                (int)bstrString + 1,
                                v16,
                                v18,
                                (unsigned int *)&v35);
        if ( !NextCompoundElement )
        {
          v20 = (unsigned __int16 *)*((_QWORD *)a2 + 5 * v19);
          v21 = (int)v35;
          v22 = (unsigned __int16 *)*((_QWORD *)a2 + 5 * (unsigned int)v35);
          v35 = v22;
          v23 = -1;
          do
            ++v23;
          while ( v20[v23] );
          if ( CatEntry::fExist((CatEntry *)(*(_QWORD *)(*((_QWORD *)this + 45) + 8LL) + 40LL * v34), v20, v23, 1) )
          {
            NextCompoundElement = CEngineLocaleHandlerDEU::GetNextCompoundElement(
                                    v24,
                                    v21 + 1,
                                    (int)v6 + v40,
                                    a2,
                                    (unsigned int *)&v39);
            if ( !NextCompoundElement )
            {
              v26 = (int)v39;
              NextCompoundElement = CEngineLocaleHandlerDEU::TryPrepZuWordCombination(
                                      v25,
                                      v20,
                                      v35,
                                      *((const unsigned __int16 **)a2 + 5 * (unsigned int)v39),
                                      v47,
                                      (unsigned __int64)v33);
              if ( !NextCompoundElement )
              {
                CSrTokenDL::SetAnyViaCopy(v27, a5, v47, 1u, 1u, 0);
                *((_DWORD *)a5 + 9) = 0;
                CSrTokenDL::SetAnyViaCopy(v28, a5 + 1, v47, 1u, 1u, (unsigned int *)a5 + 9);
                v29 = v26 - v6 + 1;
LABEL_26:
                *((_DWORD *)a5 + 5) = v6;
                *((_DWORD *)a5 + 6) = v29;
                *((_BYTE *)a5 + 16) = *((_BYTE *)a2 + 40 * v6 + 16);
                *((_DWORD *)a5 + 7) = *((_DWORD *)a2 + 10 * v6 + 7);
                *v42 = v29;
              }
            }
          }
          else
          {
            NextCompoundElement = CEngineLocaleHandlerDEU::TryCompounding(
                                    v24,
                                    v20,
                                    v22,
                                    v47,
                                    v48,
                                    (unsigned __int64)v33,
                                    *((struct CatLex **)this + 45),
                                    v38,
                                    v37,
                                    v36);
            if ( !NextCompoundElement )
            {
              CSrTokenDL::SetAnyViaCopy(v30, a5, v47, 1u, 1u, 0);
              *((_DWORD *)a5 + 9) = 0;
              CSrTokenDL::SetAnyViaCopy(v31, a5 + 1, v47, 1u, 1u, (unsigned int *)a5 + 9);
              v29 = v21 - v6 + 1;
              goto LABEL_26;
            }
          }
        }
      }
    }
  }
  return (unsigned int)NextCompoundElement;
}

```

## disassembly

```asm
0x1800da5e0  mov     [rsp-8+arg_18], rbx
0x1800da5e5  push    rbp
0x1800da5e6  push    rsi
0x1800da5e7  push    rdi
0x1800da5e8  push    r12
0x1800da5ea  push    r13
0x1800da5ec  push    r14
0x1800da5ee  push    r15
0x1800da5f0  lea     rbp, [rsp-0F70h]
0x1800da5f8  mov     eax, 1070h
0x1800da5fd  call    _alloca_probe
0x1800da602  sub     rsp, rax
0x1800da605  mov     rax, cs:__security_cookie
0x1800da60c  xor     rax, rsp
0x1800da60f  mov     [rbp+0FA0h+var_40], rax
0x1800da616  mov     [rsp+10A0h+var_1030], r9d
0x1800da61b  mov     r15d, r8d
0x1800da61e  mov     r14, rdx
0x1800da621  mov     rsi, rcx
0x1800da624  mov     rdi, [rbp+0FA0h+arg_20]
0x1800da62b  mov     rax, [rbp+0FA0h+arg_28]
0x1800da632  mov     [rbp+0FA0h+var_1020], rax
0x1800da636  xor     r12d, r12d
0x1800da639  mov     ebx, r12d
0x1800da63c  mov     [rax], r12d
0x1800da63f  cmp     [rcx+168h], r12
0x1800da646  jnz     loc_1800DA769
0x1800da64c  mov     [rsp+10A0h+var_1048], r12
0x1800da651  mov     [rsp+10A0h+var_1038], r12
0x1800da656  mov     rcx, [rcx+20h]
0x1800da65a  mov     rax, [rcx]
0x1800da65d  lea     r8, [rsp+10A0h+var_1048]
0x1800da662  lea     rdx, aCompound; "Compound"
0x1800da669  mov     rax, [rax+48h]
0x1800da66d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da672  mov     ebx, eax
0x1800da674  test    eax, eax
0x1800da676  js      loc_1800DA74C
0x1800da67c  mov     rcx, [rsp+10A0h+var_1048]
0x1800da681  mov     rax, [rcx]
0x1800da684  lea     r8, [rsp+10A0h+var_1038]
0x1800da689  lea     rdx, aDatafile; "DataFile"
0x1800da690  mov     rax, [rax+30h]
0x1800da694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da699  mov     ebx, eax
0x1800da69b  test    eax, eax
0x1800da69d  js      loc_1800DA74C
0x1800da6a3  mov     rdx, [rsp+10A0h+var_1038]; unsigned __int16 *
0x1800da6a8  lea     rcx, [rsp+10A0h+bstrString]; this
0x1800da6ad  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800da6b2  nop
0x1800da6b3  mov     [rbp+0FA0h+var_1010], r12
0x1800da6b7  mov     [rbp+0FA0h+var_1008], r12
0x1800da6bb  mov     [rbp+0FA0h+var_1000], r12d
0x1800da6bf  lea     rax, ??_7CSequentialReadFile@@6B@; const CSequentialReadFile::`vftable'
0x1800da6c6  mov     [rbp+0FA0h+var_1018], rax
0x1800da6ca  mov     [rbp+0FA0h+var_FF8], r12
0x1800da6ce  xor     r8d, r8d; bool
0x1800da6d1  lea     edx, [r12+10h]; unsigned __int64
0x1800da6d6  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800da6dd  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800da6e2  mov     [rbp+0FA0h+var_FF0], rax
0x1800da6e6  test    rax, rax
0x1800da6e9  jz      short loc_1800DA72A
0x1800da6eb  mov     [rax], r12d
0x1800da6ee  mov     [rax+8], r12
0x1800da6f2  mov     [rsi+168h], rax
0x1800da6f9  mov     rdx, [rsp+10A0h+var_1038]; unsigned __int16 *
0x1800da6fe  lea     rcx, [rbp+0FA0h+var_1018]; this
0x1800da702  call    ?Open@CSequentialReadFile@@QEAAJPEBGH@Z; CSequentialReadFile::Open(ushort const *,int)
0x1800da707  mov     ebx, eax
0x1800da709  test    eax, eax
0x1800da70b  js      short loc_1800DA736
0x1800da70d  lea     rdx, [rbp+0FA0h+var_1018]; struct CSequentialRead *
0x1800da711  mov     rcx, [rsi+168h]; this
0x1800da718  call    ?Deserial@CatLex@@QEAAJPEAVCSequentialRead@@@Z; CatLex::Deserial(CSequentialRead *)
0x1800da71d  mov     ebx, eax
0x1800da71f  lea     rcx, [rbp+0FA0h+var_1018]; this
0x1800da723  call    ?Close@CSequentialReadFile@@UEAAXXZ; CSequentialReadFile::Close(void)
0x1800da728  jmp     short loc_1800DA736
0x1800da72a  mov     [rsi+168h], r12
0x1800da731  mov     ebx, 8007000Eh
0x1800da736  lea     rcx, [rbp+0FA0h+var_1018]; this
0x1800da73a  call    ??1CSequentialReadFile@@UEAA@XZ; CSequentialReadFile::~CSequentialReadFile(void)
0x1800da73f  nop
0x1800da740  mov     rcx, [rsp+10A0h+bstrString]; bstrString
0x1800da745  call    cs:__imp_SysFreeString
0x1800da74b  nop
0x1800da74c  lea     rcx, [rsp+10A0h+var_1038]; this
0x1800da751  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x1800da756  nop
0x1800da757  lea     rcx, [rsp+10A0h+var_1048]
0x1800da75c  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800da761  test    ebx, ebx
0x1800da763  js      loc_1800DAA0F
0x1800da769  mov     r13, [rsi+168h]
0x1800da770  lea     rdx, aPreposition; "Preposition"
0x1800da777  mov     rcx, r13; this
0x1800da77a  call    ?Name2ID@CatLex@@QEBAGPEBG@Z; CatLex::Name2ID(ushort const *)
0x1800da77f  mov     [rsp+10A0h+var_1050], ax
0x1800da784  lea     rdx, aSegbound; "SegBound"
0x1800da78b  mov     rcx, r13; this
0x1800da78e  call    ?Name2ID@CatLex@@QEBAGPEBG@Z; CatLex::Name2ID(ushort const *)
0x1800da793  movzx   r12d, ax
0x1800da797  mov     [rsp+10A0h+var_103C], ax
0x1800da79c  lea     rdx, aStandalonenofi; "StandaloneNoFinal"
0x1800da7a3  mov     rcx, r13; this
0x1800da7a6  call    ?Name2ID@CatLex@@QEBAGPEBG@Z; CatLex::Name2ID(ushort const *)
0x1800da7ab  movzx   r13d, ax
0x1800da7af  mov     [rsp+10A0h+var_103E], ax
0x1800da7b4  lea     rdx, aStandalone; "Standalone"
0x1800da7bb  mov     rcx, [rsi+168h]; this
0x1800da7c2  call    ?Name2ID@CatLex@@QEBAGPEBG@Z; CatLex::Name2ID(ushort const *)
0x1800da7c7  mov     [rsp+10A0h+var_1040], ax
0x1800da7cc  mov     ecx, 0FFFFh; this
0x1800da7d1  cmp     cx, [rsp+10A0h+var_1050]
0x1800da7d6  jz      short loc_1800DA7E9
0x1800da7d8  cmp     cx, r12w
0x1800da7dc  jz      short loc_1800DA7E9
0x1800da7de  cmp     cx, r13w
0x1800da7e2  jz      short loc_1800DA7E9
0x1800da7e4  cmp     cx, ax
0x1800da7e7  jnz     short loc_1800DA7EE
0x1800da7e9  mov     ebx, 80004005h
0x1800da7ee  xor     r13d, r13d
0x1800da7f1  test    ebx, ebx
0x1800da7f3  js      loc_1800DAA0F
0x1800da7f9  mov     dword ptr [rsp+10A0h+bstrString], r13d
0x1800da7fe  mov     dword ptr [rsp+10A0h+var_1048], r13d
0x1800da803  mov     dword ptr [rsp+10A0h+var_1038], r13d
0x1800da808  mov     r12d, [rsp+10A0h+var_1030]
0x1800da80d  add     r12d, r15d
0x1800da810  lea     rax, [rsp+10A0h+bstrString]
0x1800da815  mov     [rsp+10A0h+var_1080], rax; unsigned int *
0x1800da81a  mov     r9, r14; struct CSrTokenDL *
0x1800da81d  mov     r8d, r12d; unsigned int
0x1800da820  mov     edx, r15d; unsigned int
0x1800da823  call    ?GetNextCompoundElement@CEngineLocaleHandlerDEU@@IEAAJKKPEBVCSrTokenDL@@PEAK@Z; CEngineLocaleHandlerDEU::GetNextCompoundElement(ulong,ulong,CSrTokenDL const *,ulong *)
0x1800da828  mov     ebx, eax
0x1800da82a  test    eax, eax
0x1800da82c  jnz     loc_1800DAA0F
0x1800da832  mov     r13d, dword ptr [rsp+10A0h+bstrString]
0x1800da837  lea     edx, [r13+1]; unsigned int
0x1800da83b  lea     rax, [rsp+10A0h+var_1048]
0x1800da840  mov     [rsp+10A0h+var_1080], rax; unsigned int *
0x1800da845  mov     r8d, r12d; unsigned int
0x1800da848  call    ?GetNextCompoundElement@CEngineLocaleHandlerDEU@@IEAAJKKPEBVCSrTokenDL@@PEAK@Z; CEngineLocaleHandlerDEU::GetNextCompoundElement(ulong,ulong,CSrTokenDL const *,ulong *)
0x1800da84d  mov     ebx, eax
0x1800da84f  xor     edx, edx
0x1800da851  test    eax, eax
0x1800da853  jnz     loc_1800DAA0F
0x1800da859  lea     rcx, ds:0[r13*4]
0x1800da861  add     rcx, r13
0x1800da864  mov     r12, [r14+rcx*8]
0x1800da868  mov     r13d, dword ptr [rsp+10A0h+var_1048]
0x1800da86d  lea     rcx, ds:0[r13*4]
0x1800da875  add     rcx, r13
0x1800da878  mov     rbx, [r14+rcx*8]
0x1800da87c  mov     [rsp+10A0h+var_1048], rbx
0x1800da881  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800da885  inc     r8; unsigned __int64
0x1800da888  cmp     [r12+r8*2], dx
0x1800da88d  jnz     short loc_1800DA885
0x1800da88f  movzx   eax, [rsp+10A0h+var_1050]
0x1800da894  lea     rcx, [rax+rax*4]
0x1800da898  mov     rax, [rsi+168h]
0x1800da89f  mov     rax, [rax+8]
0x1800da8a3  lea     rcx, [rax+rcx*8]; this
0x1800da8a7  mov     r9d, 1; int
0x1800da8ad  mov     rdx, r12; unsigned __int16 *
0x1800da8b0  call    ?fExist@CatEntry@@QEBAHPEBG_KH@Z; CatEntry::fExist(ushort const *,unsigned __int64,int)
0x1800da8b5  test    eax, eax
0x1800da8b7  jz      loc_1800DA95D
0x1800da8bd  lea     edx, [r13+1]; unsigned int
0x1800da8c1  lea     rax, [rsp+10A0h+var_1038]
0x1800da8c6  mov     [rsp+10A0h+var_1080], rax; unsigned int *
0x1800da8cb  mov     r9, r14; struct CSrTokenDL *
0x1800da8ce  mov     r8d, [rsp+10A0h+var_1030]
0x1800da8d3  add     r8d, r15d; unsigned int
0x1800da8d6  call    ?GetNextCompoundElement@CEngineLocaleHandlerDEU@@IEAAJKKPEBVCSrTokenDL@@PEAK@Z; CEngineLocaleHandlerDEU::GetNextCompoundElement(ulong,ulong,CSrTokenDL const *,ulong *)
0x1800da8db  mov     ebx, eax
0x1800da8dd  xor     r13d, r13d
0x1800da8e0  test    eax, eax
0x1800da8e2  jnz     loc_1800DAA0F
0x1800da8e8  mov     esi, dword ptr [rsp+10A0h+var_1038]
0x1800da8ec  lea     r9, [rsi+rsi*4]
0x1800da8f0  lea     rax, [rbp+0FA0h+var_FE0]
0x1800da8f4  mov     [rsp+10A0h+var_1080], rax; unsigned __int16 *
0x1800da8f9  mov     r9, [r14+r9*8]; unsigned __int16 *
0x1800da8fd  mov     r8, [rsp+10A0h+var_1048]; unsigned __int16 *
0x1800da902  mov     rdx, r12; unsigned __int16 *
0x1800da905  call    ?TryPrepZuWordCombination@CEngineLocaleHandlerDEU@@IEAAJPEBG00PEAG_K@Z; CEngineLocaleHandlerDEU::TryPrepZuWordCombination(ushort const *,ushort const *,ushort const *,ushort *,unsigned __int64)
0x1800da90a  mov     ebx, eax
0x1800da90c  test    eax, eax
0x1800da90e  jnz     loc_1800DAA0F
0x1800da914  mov     [rsp+10A0h+var_1078], r13; unsigned int *
0x1800da919  lea     r12d, [r13+1]
0x1800da91d  mov     dword ptr [rsp+10A0h+var_1080], r12d; unsigned int
0x1800da922  mov     r9d, r12d; unsigned int
0x1800da925  lea     r8, [rbp+0FA0h+var_FE0]; unsigned __int16 *
0x1800da929  mov     rdx, rdi; unsigned __int16 **
0x1800da92c  call    ?SetAnyViaCopy@CSrTokenDL@@QEAAJPEAPEAGPEBGKKPEAK@Z; CSrTokenDL::SetAnyViaCopy(ushort * *,ushort const *,ulong,ulong,ulong *)
0x1800da931  lea     rax, [rdi+24h]
0x1800da935  mov     [rax], r13d
0x1800da938  lea     rdx, [rdi+8]; unsigned __int16 **
0x1800da93c  mov     [rsp+10A0h+var_1078], rax; unsigned int *
0x1800da941  mov     dword ptr [rsp+10A0h+var_1080], r12d; unsigned int
0x1800da946  mov     r9d, r12d; unsigned int
0x1800da949  lea     r8, [rbp+0FA0h+var_FE0]; unsigned __int16 *
0x1800da94d  call    ?SetAnyViaCopy@CSrTokenDL@@QEAAJPEAPEAGPEBGKKPEAK@Z; CSrTokenDL::SetAnyViaCopy(ushort * *,ushort const *,ulong,ulong,ulong *)
0x1800da952  sub     esi, r15d
0x1800da955  lea     edx, [rsi+1]
0x1800da958  jmp     loc_1800DA9EE
0x1800da95d  movzx   eax, [rsp+10A0h+var_1040]
0x1800da962  mov     [rsp+10A0h+var_1058], ax; unsigned __int16
0x1800da967  movzx   eax, [rsp+10A0h+var_103E]
0x1800da96c  mov     [rsp+10A0h+var_1060], ax; unsigned __int16
0x1800da971  movzx   eax, [rsp+10A0h+var_103C]
0x1800da976  mov     [rsp+10A0h+var_1068], ax; unsigned __int16
0x1800da97b  mov     rax, [rsi+168h]
0x1800da982  mov     [rsp+10A0h+var_1070], rax; struct CatLex *
0x1800da987  lea     rax, [rbp+0FA0h+var_810]
0x1800da98e  mov     [rsp+10A0h+var_1080], rax; unsigned __int16 *
0x1800da993  lea     r9, [rbp+0FA0h+var_FE0]; unsigned __int16 *
0x1800da997  mov     r8, rbx; unsigned __int16 *
0x1800da99a  mov     rdx, r12; unsigned __int16 *
0x1800da99d  call    ?TryCompounding@CEngineLocaleHandlerDEU@@IEAAJPEAG000_KPEAVCatLex@@GGG@Z; CEngineLocaleHandlerDEU::TryCompounding(ushort *,ushort *,ushort *,ushort *,unsigned __int64,CatLex *,ushort,ushort,ushort)
0x1800da9a2  mov     ebx, eax
0x1800da9a4  xor     esi, esi
0x1800da9a6  test    eax, eax
0x1800da9a8  jnz     short loc_1800DAA0F
0x1800da9aa  mov     [rsp+10A0h+var_1078], rsi; unsigned int *
0x1800da9af  lea     r12d, [rax+1]
0x1800da9b3  mov     dword ptr [rsp+10A0h+var_1080], r12d; unsigned int
0x1800da9b8  mov     r9d, r12d; unsigned int
0x1800da9bb  lea     r8, [rbp+0FA0h+var_FE0]; unsigned __int16 *
0x1800da9bf  mov     rdx, rdi; unsigned __int16 **
0x1800da9c2  call    ?SetAnyViaCopy@CSrTokenDL@@QEAAJPEAPEAGPEBGKKPEAK@Z; CSrTokenDL::SetAnyViaCopy(ushort * *,ushort const *,ulong,ulong,ulong *)
0x1800da9c7  lea     rax, [rdi+24h]
0x1800da9cb  mov     [rax], esi
0x1800da9cd  lea     rdx, [rdi+8]; unsigned __int16 **
0x1800da9d1  mov     [rsp+10A0h+var_1078], rax; unsigned int *
0x1800da9d6  mov     dword ptr [rsp+10A0h+var_1080], r12d; unsigned int
0x1800da9db  mov     r9d, r12d; unsigned int
0x1800da9de  lea     r8, [rbp+0FA0h+var_FE0]; unsigned __int16 *
0x1800da9e2  call    ?SetAnyViaCopy@CSrTokenDL@@QEAAJPEAPEAGPEBGKKPEAK@Z; CSrTokenDL::SetAnyViaCopy(ushort * *,ushort const *,ulong,ulong,ulong *)
0x1800da9e7  sub     r13d, r15d
0x1800da9ea  lea     edx, [r13+1]
0x1800da9ee  lea     rcx, [r15+r15*4]
0x1800da9f2  mov     [rdi+14h], r15d
0x1800da9f6  mov     [rdi+18h], edx
0x1800da9f9  mov     al, [r14+rcx*8+10h]
0x1800da9fe  mov     [rdi+10h], al
0x1800daa01  mov     eax, [r14+rcx*8+1Ch]
0x1800daa06  mov     [rdi+1Ch], eax
0x1800daa09  mov     rax, [rbp+0FA0h+var_1020]
0x1800daa0d  mov     [rax], edx
0x1800daa0f  mov     eax, ebx
0x1800daa11  mov     rcx, [rbp+0FA0h+var_40]
0x1800daa18  xor     rcx, rsp; StackCookie
0x1800daa1b  call    __security_check_cookie
0x1800daa20  mov     rbx, [rsp+10A0h+arg_18]
0x1800daa28  add     rsp, 1070h
0x1800daa2f  pop     r15
0x1800daa31  pop     r14
0x1800daa33  pop     r13
0x1800daa35  pop     r12
0x1800daa37  pop     rdi
0x1800daa38  pop     rsi
0x1800daa39  pop     rbp
0x1800daa3a  retn
```
