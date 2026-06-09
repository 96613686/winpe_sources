# CInternalMerger::GetOwnInstance(ushort const *,IWbemClassObject * *)

- ea: `0x180032340`
- end: `0x180032880`
- name: `?GetOwnInstance@CInternalMerger@@IEAAJPEBGPEAPEAUIWbemClassObject@@@Z`
- size: `1344`
- prototype: `int(CInternalMerger *__hidden this, const unsigned __int16 *, struct IWbemClassObject **)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180031dc4`

## callees

- `0x18000b140`
- `0x18000b46c`
- `0x18000e8c0`
- `0x18002ca8c`
- `0x180030580`
- `0x180032340`
- `0x180037ebc`
- `0x18003cfe0`
- `0x18003f4d0`
- `0x180075dcc`
- `0x18008658c`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?Length@WString@@QEBAHXZ` at `0x1800323c6`
- `wbemcomn!?Length@WString@@QEBAHXZ` at `0x1800323c6`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18003243d`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18003243d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800323e5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800323e5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003242c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003242c`
- `wbemcomn!GetMemLogObject` at `0x180032552`
- `wbemcomn!GetMemLogObject` at `0x180032635`
- `wbemcomn!GetMemLogObject` at `0x1800326aa`
- `wbemcomn!GetMemLogObject` at `0x180032709`
- `wbemcomn!GetMemLogObject` at `0x1800327a9`
- `wbemcomn!GetMemLogObject` at `0x180032837`
- `wbemcomn!GetMemLogObject` at `0x180032552`
- `wbemcomn!GetMemLogObject` at `0x180032635`
- `wbemcomn!GetMemLogObject` at `0x1800326aa`
- `wbemcomn!GetMemLogObject` at `0x180032709`
- `wbemcomn!GetMemLogObject` at `0x1800327a9`
- `wbemcomn!GetMemLogObject` at `0x180032837`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032560`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032640`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800326b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032714`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800327b4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032843`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032560`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032640`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800326b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032714`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800327b4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032843`
- `FastProx!?IsDynamic@CWbemClass@@QEAAHXZ` at `0x180032383`
- `FastProx!?IsDynamic@CWbemClass@@QEAAHXZ` at `0x180032383`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800325b0`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800325fc`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800325b0`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800325fc`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180032480`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180032480`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall CInternalMerger::GetOwnInstance(
        CInternalMerger *this,
        const unsigned __int16 *a2,
        struct IWbemClassObject **a3)
{
  int result; // eax
  int SingleInstance; // r14d
  __int64 v7; // rbx
  __int64 v8; // rdi
  unsigned __int64 v9; // rdi
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // r13
  int v12; // edi
  __int64 v13; // rax
  int v14; // ebx
  HRESULT v15; // eax
  void *v16; // rbx
  void *v17; // rcx
  int v18; // r12d
  CMemoryLog *v19; // rax
  CClientCnt *v20; // rcx
  IUnknown *v21; // rdi
  IUnknown *v22; // rsi
  CMemoryLog *v23; // rax
  __int64 v24; // rdx
  CMemoryLog *v25; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v27; // rax
  int ObjectW; // eax
  CMemoryLog *v29; // rax
  IUnknown *ppOldObject; // [rsp+30h] [rbp-40h] BYREF
  IUnknown *v31; // [rsp+38h] [rbp-38h] BYREF
  IUnknown *v32; // [rsp+40h] [rbp-30h]
  void *v33[5]; // [rsp+48h] [rbp-28h] BYREF
  void *ppInterface; // [rsp+B0h] [rbp+40h] BYREF
  struct IWbemClassObject **v35; // [rsp+C0h] [rbp+50h]
  void *v36; // [rsp+C8h] [rbp+58h] BYREF

  v35 = a3;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids);
  }
  result = CWbemClass::IsDynamic(*((CWbemClass **)this + 4));
  SingleInstance = 0;
  if ( result )
  {
    if ( a2 )
    {
      v7 = -1;
      v8 = -1;
      do
        ++v8;
      while ( a2[v8] );
      v9 = (int)WString::Length((CInternalMerger *)((char *)this + 88)) + 2LL + v8;
      v10 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v9, 2u));
      v11 = v10;
      if ( v10 )
      {
        v33[0] = v10;
        v33[1] = 0;
        do
          ++v7;
        while ( a2[v7] );
        if ( !v7 )
        {
LABEL_11:
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              48,
              WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids,
              (unsigned int)SingleInstance);
          }
          v12 = SingleInstance;
          goto LABEL_13;
        }
        v13 = WString::operator unsigned short *((char *)this + 88);
        v14 = StringCchPrintfW(v11, v9, L"%s.%s", v13, a2);
        if ( v14 < 0 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, v14);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              45,
              WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids,
              (unsigned int)v14);
          }
        }
        ppInterface = 0;
        v15 = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
        v16 = ppInterface;
        v36 = ppInterface;
        v12 = 0;
        if ( v15 != -2147417833 )
          v12 = v15;
        if ( v12 < 0 )
        {
          v23 = GetMemLogObject();
          CMemoryLog::Write(v23, v12);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              46,
              WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids,
              (unsigned int)v12);
          }
          if ( v16 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
        }
        else
        {
          v17 = ppInterface;
          if ( ppInterface )
          {
            v18 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface);
            v17 = ppInterface;
          }
          else
          {
            v18 = 0;
          }
          if ( v17 )
          {
            if ( v18 )
            {
              v12 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v17 + 40LL))(v17);
              if ( v12 < 0 )
              {
                v27 = GetMemLogObject();
                CMemoryLog::Write(v27, v12);
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    47,
                    WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids,
                    (unsigned int)v12);
                }
                CReleaseMe::release((CReleaseMe *)&v36);
                CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v33);
                return v12;
              }
            }
          }
          ppOldObject = 0;
          SingleInstance = CWmiMerger::CreateMergingSink(
                             *(_QWORD *)(*((_QWORD *)this + 7) + 24LL),
                             3,
                             0,
                             this,
                             &ppOldObject);
          if ( SingleInstance >= 0 )
          {
            v21 = ppOldObject;
            CInternalMerger::CMemberSink::AddRef((CInternalMerger::CMemberSink *)ppOldObject);
            v32 = v21;
            SingleInstance = CInternalMerger::COwnInstanceSink::SetInstancePath(
                               (CInternalMerger::COwnInstanceSink *)v21,
                               a2);
            if ( SingleInstance >= 0 )
            {
              ppOldObject = 0;
              SingleInstance = CoSwitchCallContext(*((IUnknown **)this + 13), &ppOldObject);
              if ( SingleInstance >= 0 )
              {
                v31 = 0;
                v22 = ppOldObject;
                v33[2] = ppOldObject;
                v33[3] = &v31;
                SingleInstance = CWbemNamespace::DynAux_GetSingleInstance(
                                   *((CWbemNamespace **)this + 5),
                                   *((struct CWbemClass **)this + 4),
                                   0,
                                   v11,
                                   *((struct IWbemContext **)this + 6),
                                   (struct CBasicObjectSink *)v21);
                CoSwitchCallContext(v22, &v31);
                if ( SingleInstance >= 0 )
                {
                  ObjectW = CInternalMerger::COwnInstanceSink::GetObjectW((CInternalMerger::COwnInstanceSink *)v21, v35);
                  SingleInstance = 0;
                  if ( ObjectW != 1 )
                    SingleInstance = ObjectW;
                }
                else if ( SingleInstance == -2147217406 )
                {
                  SingleInstance = 0;
                }
              }
            }
            if ( v21 )
              ((void (__fastcall *)(IUnknown *))v21->lpVtbl->Release)(v21);
            v32 = 0;
          }
          if ( !v18
            || !ppInterface
            || (v12 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface), v12 >= 0) )
          {
            CReleaseMe::release((CReleaseMe *)&v36);
            if ( SingleInstance < 0 )
            {
              v29 = GetMemLogObject();
              CMemoryLog::Write(v29, SingleInstance);
            }
            goto LABEL_11;
          }
          if ( v16 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
        }
        v36 = 0;
LABEL_13:
        CWin32DefaultArena::WbemMemFree(v11);
        return v12;
      }
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, -2147217402);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return -2147217402;
      }
      v24 = 44;
    }
    else
    {
      v19 = GetMemLogObject();
      CMemoryLog::Write(v19, -2147217402);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return -2147217402;
      }
      v24 = 43;
    }
    WPP_SF_d(*((_QWORD *)v20 + 2), v24, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids, 2147749894LL);
    return -2147217402;
  }
  return result;
}

```

## disassembly

```asm
0x180032340  mov     [rsp-38h+arg_8], rbx
0x180032345  mov     [rsp-38h+arg_10], r8
0x18003234a  push    rbp
0x18003234b  push    rsi
0x18003234c  push    rdi
0x18003234d  push    r12
0x18003234f  push    r13
0x180032351  push    r14
0x180032353  push    r15
0x180032355  mov     rbp, rsp
0x180032358  sub     rsp, 70h
0x18003235c  mov     rsi, rdx
0x18003235f  mov     r15, rcx
0x180032362  lea     rbx, WPP_GLOBAL_Control
0x180032369  mov     rcx, cs:WPP_GLOBAL_Control
0x180032370  cmp     rcx, rbx
0x180032373  jz      short loc_18003237F
0x180032375  test    byte ptr [rcx+1Ch], 1
0x180032379  jnz     loc_18003266B
0x18003237f  mov     rcx, [r15+20h]
0x180032383  call    cs:__imp_?IsDynamic@CWbemClass@@QEAAHXZ; CWbemClass::IsDynamic(void)
0x180032389  xor     r14d, r14d
0x18003238c  test    eax, eax
0x18003238e  jnz     short loc_1800323A8
0x180032390  mov     rbx, [rsp+70h+arg_8]
0x180032398  add     rsp, 70h
0x18003239c  pop     r15
0x18003239e  pop     r14
0x1800323a0  pop     r13
0x1800323a2  pop     r12
0x1800323a4  pop     rdi
0x1800323a5  pop     rsi
0x1800323a6  pop     rbp
0x1800323a7  retn
0x1800323a8  test    rsi, rsi
0x1800323ab  jz      loc_180032552
0x1800323b1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800323b5  mov     rdi, rbx
0x1800323b8  inc     rdi
0x1800323bb  cmp     [rsi+rdi*2], r14w
0x1800323c0  jnz     short loc_1800323B8
0x1800323c2  lea     rcx, [r15+58h]
0x1800323c6  call    cs:__imp_?Length@WString@@QEBAHXZ; WString::Length(void)
0x1800323cc  movsxd  rcx, eax
0x1800323cf  add     rcx, 2
0x1800323d3  add     rdi, rcx
0x1800323d6  mov     eax, 2
0x1800323db  mul     rdi
0x1800323de  cmovb   rax, rbx
0x1800323e2  mov     rcx, rax
0x1800323e5  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800323eb  mov     r13, rax
0x1800323ee  test    rax, rax
0x1800323f1  jz      loc_1800326AA
0x1800323f7  mov     [rbp+var_28], rax
0x1800323fb  xor     eax, eax
0x1800323fd  mov     [rbp+var_20], rax
0x180032401  inc     rbx
0x180032404  cmp     [rsi+rbx*2], ax
0x180032408  jnz     short loc_180032401
0x18003240a  test    rbx, rbx
0x18003240d  jnz     short loc_180032439
0x18003240f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032416  lea     rax, WPP_GLOBAL_Control
0x18003241d  cmp     rcx, rax
0x180032420  jnz     loc_18003284E
0x180032426  mov     edi, r14d
0x180032429  mov     rcx, r13
0x18003242c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180032432  mov     eax, edi
0x180032434  jmp     loc_180032390
0x180032439  lea     rcx, [r15+58h]
0x18003243d  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x180032443  mov     r9, rax
0x180032446  mov     [rsp+70h+var_50], rsi
0x18003244b  lea     r8, aSS; "%s.%s"
0x180032452  mov     rdx, rdi; unsigned __int64
0x180032455  mov     rcx, r13; unsigned __int16 *
0x180032458  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003245d  mov     ebx, eax
0x18003245f  xor     r14d, r14d
0x180032462  test    eax, eax
0x180032464  js      loc_180032709
0x18003246a  lea     r12, WPP_GLOBAL_Control
0x180032471  mov     [rbp+ppInterface], r14
0x180032475  lea     rdx, [rbp+ppInterface]; ppInterface
0x180032479  lea     rcx, IID_IServerSecurity; riid
0x180032480  call    cs:__imp_CoGetCallContext
0x180032486  mov     rbx, [rbp+ppInterface]
0x18003248a  mov     [rbp+arg_18], rbx
0x18003248e  mov     edi, r14d
0x180032491  cmp     eax, 80010117h
0x180032496  cmovnz  edi, eax
0x180032499  test    edi, edi
0x18003249b  js      loc_180032635
0x1800324a1  mov     rcx, [rbp+ppInterface]
0x1800324a5  test    rcx, rcx
0x1800324a8  jz      loc_18003254A
0x1800324ae  mov     rax, [rcx]
0x1800324b1  mov     rax, [rax+30h]
0x1800324b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324ba  mov     r12d, eax
0x1800324bd  mov     rcx, [rbp+ppInterface]
0x1800324c1  test    rcx, rcx
0x1800324c4  jz      short loc_1800324CF
0x1800324c6  test    r12d, r12d
0x1800324c9  jnz     loc_180032793
0x1800324cf  mov     [rbp+ppOldObject], r14
0x1800324d3  mov     rcx, [r15+38h]
0x1800324d7  lea     rax, [rbp+ppOldObject]
0x1800324db  mov     [rsp+70h+var_50], rax
0x1800324e0  mov     r9, r15
0x1800324e3  xor     r8d, r8d
0x1800324e6  lea     edx, [r8+3]
0x1800324ea  mov     rcx, [rcx+18h]
0x1800324ee  call    ?CreateMergingSink@CWmiMerger@@QEAAJW4MergerSinkType@@PEAUIWbemObjectSink@@PEAVCInternalMerger@@PEAPEAVCMergerSink@@@Z; CWmiMerger::CreateMergingSink(MergerSinkType,IWbemObjectSink *,CInternalMerger *,CMergerSink * *)
0x1800324f3  mov     r14d, eax
0x1800324f6  test    eax, eax
0x1800324f8  jns     loc_180032580
0x1800324fe  test    r12d, r12d
0x180032501  jz      loc_180032825
0x180032507  mov     rcx, [rbp+ppInterface]
0x18003250b  test    rcx, rcx
0x18003250e  jz      loc_180032825
0x180032514  mov     rax, [rcx]
0x180032517  mov     rax, [rax+20h]
0x18003251b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032520  mov     edi, eax
0x180032522  test    eax, eax
0x180032524  jns     loc_180032825
0x18003252a  xor     r14d, r14d
0x18003252d  test    rbx, rbx
0x180032530  jz      short loc_180032541
0x180032532  mov     rcx, [rbx]
0x180032535  mov     rax, [rcx+10h]
0x180032539  mov     rcx, rbx
0x18003253c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032541  mov     [rbp+arg_18], r14
0x180032545  jmp     loc_180032429
0x18003254a  mov     r12d, r14d
0x18003254d  jmp     loc_1800324C1
0x180032552  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180032558  mov     edx, 80041006h
0x18003255d  mov     rcx, rax
0x180032560  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180032566  mov     rcx, cs:WPP_GLOBAL_Control
0x18003256d  cmp     rcx, rbx
0x180032570  jnz     loc_18003268F
0x180032576  mov     eax, 80041006h
0x18003257b  jmp     loc_180032390
0x180032580  mov     rdi, [rbp+ppOldObject]
0x180032584  mov     rcx, rdi; this
0x180032587  call    ?AddRef@CMemberSink@CInternalMerger@@UEAAKXZ; CInternalMerger::CMemberSink::AddRef(void)
0x18003258c  mov     [rbp+var_30], rdi
0x180032590  mov     rdx, rsi; unsigned __int16 *
0x180032593  mov     rcx, rdi; this
0x180032596  call    ?SetInstancePath@COwnInstanceSink@CInternalMerger@@QEAAJPEBG@Z; CInternalMerger::COwnInstanceSink::SetInstancePath(ushort const *)
0x18003259b  mov     r14d, eax
0x18003259e  xor     esi, esi
0x1800325a0  test    eax, eax
0x1800325a2  js      short loc_180032618
0x1800325a4  mov     [rbp+ppOldObject], rsi
0x1800325a8  lea     rdx, [rbp+ppOldObject]; ppOldObject
0x1800325ac  mov     rcx, [r15+68h]; pNewObject
0x1800325b0  call    cs:__imp_CoSwitchCallContext
0x1800325b6  mov     r14d, eax
0x1800325b9  test    eax, eax
0x1800325bb  js      short loc_180032618
0x1800325bd  mov     [rbp+var_38], rsi
0x1800325c1  mov     rsi, [rbp+ppOldObject]
0x1800325c5  mov     [rbp+var_18], rsi
0x1800325c9  lea     rax, [rbp+var_38]
0x1800325cd  mov     [rbp+var_10], rax
0x1800325d1  mov     [rsp+70h+var_48], rdi; struct CBasicObjectSink *
0x1800325d6  mov     rax, [r15+30h]
0x1800325da  mov     [rsp+70h+var_50], rax; struct IWbemContext *
0x1800325df  mov     r9, r13; unsigned __int16 *
0x1800325e2  xor     r8d, r8d; int
0x1800325e5  mov     rdx, [r15+20h]; struct CWbemClass *
0x1800325e9  mov     rcx, [r15+28h]; this
0x1800325ed  call    ?DynAux_GetSingleInstance@CWbemNamespace@@QEAAJPEAVCWbemClass@@JPEBGPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CWbemNamespace::DynAux_GetSingleInstance(CWbemClass *,long,ushort const *,IWbemContext *,CBasicObjectSink *)
0x1800325f2  mov     r14d, eax
0x1800325f5  lea     rdx, [rbp+var_38]; ppOldObject
0x1800325f9  mov     rcx, rsi; pNewObject
0x1800325fc  call    cs:__imp_CoSwitchCallContext
0x180032602  xor     esi, esi
0x180032604  test    r14d, r14d
0x180032607  jns     loc_18003280A
0x18003260d  cmp     r14d, 80041002h
0x180032614  cmovz   r14d, esi
0x180032618  test    rdi, rdi
0x18003261b  jz      short loc_18003262C
0x18003261d  mov     rax, [rdi]
0x180032620  mov     rcx, rdi
0x180032623  mov     rax, [rax+10h]
0x180032627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003262c  mov     [rbp+var_30], rsi
0x180032630  jmp     loc_1800324FE
0x180032635  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003263b  mov     edx, edi
0x18003263d  mov     rcx, rax
0x180032640  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180032646  mov     rcx, cs:WPP_GLOBAL_Control
0x18003264d  cmp     rcx, r12
0x180032650  jnz     loc_180032762
0x180032656  test    rbx, rbx
0x180032659  jz      loc_180032541
0x18003265f  mov     rax, [rbx]
0x180032662  mov     rax, [rax+10h]
0x180032666  jmp     loc_180032539
0x18003266b  cmp     byte ptr [rcx+19h], 5
0x18003266f  jb      loc_18003237F
0x180032675  mov     edx, 2Ah ; '*'
0x18003267a  lea     r8, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids
0x180032681  mov     rcx, [rcx+10h]
0x180032685  call    WPP_SF_
0x18003268a  jmp     loc_18003237F
0x18003268f  test    byte ptr [rcx+1Ch], 1
0x180032693  jz      loc_180032576
0x180032699  cmp     byte ptr [rcx+19h], 2
0x18003269d  jb      loc_180032576
0x1800326a3  mov     edx, 2Bh ; '+'
0x1800326a8  jmp     short loc_1800326EE
0x1800326aa  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800326b0  mov     edx, 80041006h
0x1800326b5  mov     rcx, rax
0x1800326b8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800326be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326c5  lea     rax, WPP_GLOBAL_Control
0x1800326cc  cmp     rcx, rax
0x1800326cf  jz      loc_180032576
0x1800326d5  test    byte ptr [rcx+1Ch], 1
0x1800326d9  jz      loc_180032576
0x1800326df  cmp     byte ptr [rcx+19h], 2
0x1800326e3  jb      loc_180032576
0x1800326e9  mov     edx, 2Ch ; ','
0x1800326ee  mov     r9d, 80041006h
0x1800326f4  lea     r8, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids
0x1800326fb  mov     rcx, [rcx+10h]
0x1800326ff  call    WPP_SF_d
0x180032704  jmp     loc_180032576
0x180032709  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003270f  mov     edx, ebx
0x180032711  mov     rcx, rax
0x180032714  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003271a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032721  lea     r12, WPP_GLOBAL_Control
0x180032728  cmp     rcx, r12
0x18003272b  jz      loc_180032471
0x180032731  test    byte ptr [rcx+1Ch], 1
0x180032735  jz      loc_180032471
0x18003273b  cmp     byte ptr [rcx+19h], 2
0x18003273f  jb      loc_180032471
0x180032745  mov     edx, 2Dh ; '-'
0x18003274a  mov     r9d, ebx
0x18003274d  lea     r8, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids
0x180032754  mov     rcx, [rcx+10h]
0x180032758  call    WPP_SF_d
0x18003275d  jmp     loc_180032471
0x180032762  test    byte ptr [rcx+1Ch], 1
0x180032766  jz      loc_180032656
0x18003276c  cmp     byte ptr [rcx+19h], 2
0x180032770  jb      loc_180032656
0x180032776  mov     edx, 2Eh ; '.'
0x18003277b  mov     r9d, edi
0x18003277e  lea     r8, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids
0x180032785  mov     rcx, [rcx+10h]
0x180032789  call    WPP_SF_d
0x18003278e  jmp     loc_180032656
0x180032793  mov     rax, [rcx]
0x180032796  mov     rax, [rax+28h]
0x18003279a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003279f  mov     edi, eax
0x1800327a1  test    eax, eax
0x1800327a3  jns     loc_1800324CF
0x1800327a9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800327af  mov     edx, edi
0x1800327b1  mov     rcx, rax
0x1800327b4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800327ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327c1  lea     rax, WPP_GLOBAL_Control
0x1800327c8  cmp     rcx, rax
0x1800327cb  jz      short loc_1800327F2
0x1800327cd  test    byte ptr [rcx+1Ch], 1
0x1800327d1  jz      short loc_1800327F2
0x1800327d3  cmp     byte ptr [rcx+19h], 2
0x1800327d7  jb      short loc_1800327F2
0x1800327d9  mov     edx, 2Fh ; '/'
0x1800327de  mov     r9d, edi
0x1800327e1  lea     r8, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids
0x1800327e8  mov     rcx, [rcx+10h]
0x1800327ec  call    WPP_SF_d
0x1800327f1  nop
0x1800327f2  lea     rcx, [rbp+arg_18]; this
0x1800327f6  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800327fb  nop
0x1800327fc  lea     rcx, [rbp+var_28]
0x180032800  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180032805  jmp     loc_180032432
0x18003280a  mov     rdx, [rbp+arg_10]; struct IWbemClassObject **
  ... truncated ...
```
