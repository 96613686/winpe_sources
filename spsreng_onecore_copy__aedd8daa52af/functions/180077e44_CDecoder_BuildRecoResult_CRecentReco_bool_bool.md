# CDecoder::BuildRecoResult(CRecentReco * *,bool,bool)

- ea: `0x180077e44`
- end: `0x18007835f`
- name: `?BuildRecoResult@CDecoder@@QEAAJPEAPEAVCRecentReco@@_N1@Z`
- size: `1307`
- prototype: `__int64 __fastcall(CDecoder *__hidden this, struct CRecentReco **, bool, bool)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18006d9a0`
- `0x18006dae0`

## callees

- `0x180002470`
- `0x1800040b8`
- `0x180004312`
- `0x1800062a0`
- `0x180006dbc`
- `0x180075878`
- `0x18007590c`
- `0x180077e44`
- `0x180079fd8`
- `0x18007afec`
- `0x180083e88`
- `0x180084764`
- `0x1800883c8`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800780ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800780ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180077fe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180077fe6`

## pseudocode

```c
__int64 __fastcall CDecoder::BuildRecoResult(
        CDecoder *this,
        struct CRecentReco **a2,
        unsigned __int8 a3,
        unsigned __int8 a4)
{
  int v4; // r15d
  int v5; // r12d
  struct CRecentReco **v6; // rsi
  int updated; // ebp
  __int64 v9; // r14
  __int64 v10; // rbp
  struct SPRECORESULTINFO *v11; // rax
  struct SPRECORESULTINFO *v12; // rsi
  char *v13; // rdi
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // ecx
  SPGRAMMARHANDLE v17; // rcx
  ULONGLONG v18; // rax
  struct CLatticeWrapper *v19; // rdx
  bool v20; // al
  __int64 v21; // rax
  ISpPhraseBuilder *v22; // rax
  LPVOID *v23; // r15
  unsigned int v24; // eax
  CLatticeWrapper *v25; // rcx
  struct tagSPPHRASEALT *v26; // rax
  SPPHRASEALT **v27; // r15
  char *v28; // r13
  __int64 v29; // rdx
  __int64 v30; // r9
  unsigned int v31; // edx
  float v32; // xmm1_4
  unsigned int v34[4]; // [rsp+40h] [rbp-68h] BYREF
  struct _GUID v35; // [rsp+50h] [rbp-58h] BYREF

  v4 = a4;
  v5 = a3;
  v6 = a2;
  if ( !a2 )
    return (unsigned int)-2147024809;
  *a2 = 0;
  if ( !*((_QWORD *)this + 66) )
  {
    v13 = 0;
    updated = 0;
    v9 = 0;
LABEL_63:
    if ( *((_BYTE *)this + 6400) && !(_BYTE)v5 && !*((_BYTE *)this + 2594) && !*((_BYTE *)this + 2595) )
    {
      v32 = *((float *)this + 1606) - *((float *)this + 1607);
      if ( *((_QWORD *)this + 66) && v9 && *(_DWORD *)(v9 + 816) )
      {
        if ( v32 < 4.5 && v32 > 0.001 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 10) + 16LL) + 48LL))(
            *(_QWORD *)(*((_QWORD *)this + 10) + 16LL),
            *((_QWORD *)this + 801)
          + *((_QWORD *)this + 802) * (unsigned int)(*((_DWORD *)this + 749) + *((_DWORD *)this + 1601)));
          *((_DWORD *)this + 1606) = -831624408;
          *((_DWORD *)this + 1607) = 1315859240;
        }
      }
      else if ( v32 > 0.001 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 10) + 16LL) + 56LL))(
          *(_QWORD *)(*((_QWORD *)this + 10) + 16LL),
          *((_QWORD *)this + 801)
        + *((_QWORD *)this + 802) * (unsigned int)(*((_DWORD *)this + 749) + *((_DWORD *)this + 1601)));
      }
    }
    *v6 = (struct CRecentReco *)v13;
    return (unsigned int)updated;
  }
  v9 = *(_QWORD *)(*((_QWORD *)this + 65) + 928LL);
  v10 = *(_QWORD *)(v9 + 16);
  v11 = (struct SPRECORESULTINFO *)CWinHeap::Alloc((CWinHeap *)&g_heap, 0x58u, 0);
  v12 = v11;
  if ( !v11 )
    return (unsigned int)-2147024882;
  memset_0(v11, 0, 0x58u);
  v13 = (char *)CAllocOnSpecificHeapBase::operator_new(0x58u, *((struct CHeap **)this + 9), 0);
  if ( !v13 )
  {
    v13 = 0;
    goto LABEL_59;
  }
  v15 = *((_QWORD *)this + 9);
  *((_QWORD *)v13 + 10) = 0;
  *(_QWORD *)v13 = v15;
  *((_QWORD *)v13 + 3) = 0;
  *((_QWORD *)v13 + 4) = 0;
  *((_QWORD *)v13 + 5) = 0;
  *((_QWORD *)v13 + 6) = 0;
  *((_WORD *)v13 + 28) = 0;
  *((_DWORD *)v13 + 18) = 0;
  *((_QWORD *)v13 + 1) = 0;
  *((_QWORD *)v13 + 2) = 0;
  *((_QWORD *)v13 + 8) = v12;
  v12->cbSize = 88;
  v16 = *(_DWORD *)(*((_QWORD *)this + 66) + 60LL) & 0x1F;
  v12->eResultType = v16;
  if ( *((_BYTE *)this + 2595) )
    v12->eResultType = v16 | 0x20;
  v12->fHypothesis = v5;
  v12->fProprietaryAutoPause = v4;
  LODWORD(v12->ullStreamPosStart) = 0;
  if ( *((_BYTE *)this + 2594) )
  {
    v12->ullStreamPosEnd = 0;
    v17 = 0;
  }
  else
  {
    v18 = *(_QWORD *)(v10 + 24);
    v12->ullStreamPosEnd = v18;
    v17 = (SPGRAMMARHANDLE)(v18 + *(unsigned int *)(v10 + 32));
  }
  v12->hGrammar = v17;
  *(_QWORD *)&v12->ulSizeEngineData = *(unsigned int *)(*((_QWORD *)this + 66) + 72LL);
  if ( !(_BYTE)v5
    && !*((_BYTE *)this + 2594)
    && !*((_BYTE *)this + 2595)
    && ((v19 = (struct CLatticeWrapper *)*((_QWORD *)this + 65), (*(_BYTE *)(*((_QWORD *)this + 66) + 64LL) & 1) == 0)
      ? (v20 = CDecoder::AcceptSLMPhrase(this, v19))
      : (v20 = CDecoder::AcceptCFGPhrase(this, v19)),
        !v20)
    || *((_BYTE *)this + 7685) )
  {
    v12->eResultType |= 4u;
  }
  if ( (_BYTE)v5 || (v21 = *((_QWORD *)this + 66), (*(_BYTE *)(v21 + 64) & 1) != 0) && *((_DWORD *)this + 137) )
  {
    v12->pPhrase = 0;
    LODWORD(v12->pvEngineData) = 0;
    goto LABEL_27;
  }
  v22 = (ISpPhraseBuilder *)CoTaskMemAlloc(*(unsigned int *)(v21 + 36));
  v12->pPhrase = v22;
  if ( !v22 )
  {
LABEL_59:
    updated = -2147024882;
    goto LABEL_60;
  }
  memcpy_0(v22, *((const void **)this + 66), *(unsigned int *)(*((_QWORD *)this + 66) + 36LL));
  LODWORD(v12->pvEngineData) = *(_DWORD *)(*((_QWORD *)this + 66) + 36LL);
  *(_OWORD *)(v13 + 8) = *(_OWORD *)(*((_QWORD *)this + 66) + 16LL);
LABEL_27:
  if ( *((_DWORD *)this + 134) && !(_BYTE)v5 )
  {
    *(_QWORD *)(v10 + 152) = *((_QWORD *)this + 66);
    *(_DWORD *)(v10 + 144) = *(_DWORD *)(*((_QWORD *)this + 66) + 36LL);
  }
  if ( *((_BYTE *)this + 540) && !(_BYTE)v5 && *(_BYTE *)(v9 + 3108) )
  {
    v23 = (LPVOID *)(v10 + 184);
    v35 = *(struct _GUID *)(*(_QWORD *)(*((_QWORD *)this + 10) + 88LL) + 1064LL);
    if ( (int)CPredictorSet::ConvertToSapiVersion(
                (CPredictorSet *)(v9 + 1584),
                (struct SPPREDICTORSET **)(v10 + 184),
                v14,
                &v35) < 0 )
    {
      CoTaskMemFree(*v23);
      *v23 = 0;
    }
  }
  else
  {
    *(_QWORD *)(v10 + 184) = 0;
  }
  if ( (*(_BYTE *)(*((_QWORD *)this + 66) + 64LL) & 1) != 0 || *((_BYTE *)this + 2595) )
  {
    v24 = *((_DWORD *)this + 137);
    v25 = (CLatticeWrapper *)*((_QWORD *)this + 65);
    if ( v24 >= *((_DWORD *)v25 + 240) )
      v24 = *((_DWORD *)v25 + 240);
    v34[0] = v24;
    v26 = CLatticeWrapper::PackageAlternates(v25, v34);
    *(_QWORD *)&v12->ulNumAlts = v26;
    v12[1].cbSize = v26 != 0 ? v34[0] : 0;
  }
  else
  {
    *(_QWORD *)&v12->ulNumAlts = 0;
    v12[1].cbSize = 0;
    *(_BYTE *)(v10 + 92) = 0;
  }
  if ( (*(_BYTE *)(*((_QWORD *)this + 66) + 64LL) & 1) != 0 && !*((_BYTE *)this + 518) || (_BYTE)v5 )
  {
    updated = CPhrase::UpdatePhraseBuilder((CPhrase *)v9);
    if ( updated >= 0 )
    {
      v27 = (SPPHRASEALT **)(v9 + 24);
      v28 = (char *)this + 80;
LABEL_53:
      v12->aPhraseAlts = *v27;
      *v27 = 0;
      if ( !(_BYTE)v5 && !*((_BYTE *)this + 2594) )
        *((_DWORD *)this + 136) = CPhrase::CheckTalkingSpeed(
                                    (CPhrase *)v9,
                                    *(_DWORD *)(*((_QWORD *)this + 12) + 200LL),
                                    *(float *)(*(_QWORD *)v28 + 500LL));
      v6 = a2;
      goto LABEL_63;
    }
  }
  else
  {
    v29 = *((_QWORD *)this + 65);
    v34[0] = 0;
    if ( (*(_DWORD *)(v29 + 1048) & 0x7FFFFFFF) != 0 )
      v30 = *(_QWORD *)(v29 + 1040);
    else
      v30 = 0;
    v28 = (char *)this + 80;
    v27 = (SPPHRASEALT **)(v9 + 24);
    updated = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _DWORD, _DWORD, unsigned int *))(**(_QWORD **)(*((_QWORD *)this + 10) + 16LL) + 112LL))(
                *(_QWORD *)(*((_QWORD *)this + 10) + 16LL),
                v10,
                *(_QWORD *)(v9 + 24),
                v30,
                *(_DWORD *)(v29 + 1104),
                *(_DWORD *)(v29 + 1108),
                v34);
    if ( updated >= 0 )
    {
      if ( v34[0] )
        v12->eResultType |= 4u;
      goto LABEL_53;
    }
  }
LABEL_60:
  FreeRecoResult(v12);
  if ( v13 )
  {
    *((_QWORD *)v13 + 8) = 0;
    CRecentReco::`scalar deleting destructor'((CRecentReco *)v13, v31);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180077e44  mov     [rsp+arg_8], rdx
0x180077e49  push    rbx
0x180077e4a  push    rbp
0x180077e4b  push    rsi
0x180077e4c  push    rdi
0x180077e4d  push    r12
0x180077e4f  push    r13
0x180077e51  push    r14
0x180077e53  push    r15
0x180077e55  sub     rsp, 68h
0x180077e59  xor     r13d, r13d
0x180077e5c  movzx   r15d, r9b
0x180077e60  movzx   r12d, r8b
0x180077e64  mov     rsi, rdx
0x180077e67  mov     rbx, rcx
0x180077e6a  test    rdx, rdx
0x180077e6d  jnz     short loc_180077E79
0x180077e6f  mov     ebp, 80070057h
0x180077e74  jmp     loc_18007834C
0x180077e79  mov     [rdx], r13
0x180077e7c  cmp     [rcx+210h], r13
0x180077e83  jz      loc_180078245
0x180077e89  mov     rax, [rcx+208h]
0x180077e90  xor     r8d, r8d; bool
0x180077e93  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180077e9a  mov     r14, [rax+3A0h]
0x180077ea1  lea     edi, [r8+58h]
0x180077ea5  mov     edx, edi; unsigned __int64
0x180077ea7  mov     rbp, [r14+10h]
0x180077eab  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x180077eb0  mov     rsi, rax
0x180077eb3  test    rax, rax
0x180077eb6  jnz     short loc_180077EC2
0x180077eb8  mov     ebp, 8007000Eh
0x180077ebd  jmp     loc_18007834C
0x180077ec2  mov     r8, rdi; Size
0x180077ec5  xor     edx, edx; Val
0x180077ec7  mov     rcx, rsi; void *
0x180077eca  call    memset_0
0x180077ecf  mov     rdx, [rbx+48h]; struct CHeap *
0x180077ed3  xor     r8d, r8d; bool
0x180077ed6  mov     rcx, rdi; unsigned __int64
0x180077ed9  call    ?operator_new@CAllocOnSpecificHeapBase@@SAPEAX_KPEAVCHeap@@_N@Z; CAllocOnSpecificHeapBase::operator_new(unsigned __int64,CHeap *,bool)
0x180077ede  mov     rdi, rax
0x180077ee1  test    rax, rax
0x180077ee4  jz      loc_18007821B
0x180077eea  mov     rax, [rbx+48h]
0x180077eee  mov     [rdi+50h], r13
0x180077ef2  mov     [rdi], rax
0x180077ef5  mov     [rdi+18h], r13
0x180077ef9  mov     [rdi+20h], r13
0x180077efd  mov     [rdi+28h], r13
0x180077f01  mov     [rdi+30h], r13
0x180077f05  mov     [rdi+38h], r13w
0x180077f0a  mov     [rdi+48h], r13d
0x180077f0e  mov     [rdi+8], r13
0x180077f12  mov     [rdi+10h], r13
0x180077f16  mov     [rdi+40h], rsi
0x180077f1a  mov     dword ptr [rsi], 58h ; 'X'
0x180077f20  mov     rax, [rbx+210h]
0x180077f27  mov     ecx, [rax+3Ch]
0x180077f2a  and     ecx, 1Fh
0x180077f2d  mov     [rsi+4], ecx
0x180077f30  cmp     [rbx+0A23h], r13b
0x180077f37  jz      short loc_180077F3F
0x180077f39  or      ecx, 20h
0x180077f3c  mov     [rsi+4], ecx
0x180077f3f  mov     [rsi+8], r12d
0x180077f43  mov     [rsi+0Ch], r15d
0x180077f47  mov     [rsi+10h], r13d
0x180077f4b  cmp     [rbx+0A22h], r13b
0x180077f52  jz      short loc_180077F5D
0x180077f54  mov     [rsi+18h], r13
0x180077f58  mov     rcx, r13
0x180077f5b  jmp     short loc_180077F6B
0x180077f5d  mov     rax, [rbp+18h]
0x180077f61  mov     [rsi+18h], rax
0x180077f65  mov     ecx, [rbp+20h]
0x180077f68  add     rcx, rax
0x180077f6b  mov     [rsi+20h], rcx
0x180077f6f  mov     rax, [rbx+210h]
0x180077f76  mov     ecx, [rax+48h]
0x180077f79  mov     [rsi+28h], rcx
0x180077f7d  test    r12b, r12b
0x180077f80  jnz     short loc_180077FBB
0x180077f82  cmp     [rbx+0A22h], r13b
0x180077f89  jnz     short loc_180077FBB
0x180077f8b  cmp     [rbx+0A23h], r13b
0x180077f92  jnz     short loc_180077FBB
0x180077f94  mov     rax, [rbx+210h]
0x180077f9b  mov     rcx, rbx; this
0x180077f9e  mov     rdx, [rbx+208h]; struct CLatticeWrapper *
0x180077fa5  test    byte ptr [rax+40h], 1
0x180077fa9  jz      short loc_180077FB2
0x180077fab  call    ?AcceptCFGPhrase@CDecoder@@AEAA_NPEAVCLatticeWrapper@@@Z; CDecoder::AcceptCFGPhrase(CLatticeWrapper *)
0x180077fb0  jmp     short loc_180077FB7
0x180077fb2  call    ?AcceptSLMPhrase@CDecoder@@AEAA_NPEAVCLatticeWrapper@@@Z; CDecoder::AcceptSLMPhrase(CLatticeWrapper *)
0x180077fb7  test    al, al
0x180077fb9  jz      short loc_180077FC4
0x180077fbb  cmp     [rbx+1E05h], r13b
0x180077fc2  jz      short loc_180077FC8
0x180077fc4  or      dword ptr [rsi+4], 4
0x180077fc8  test    r12b, r12b
0x180077fcb  jnz     short loc_18007802B
0x180077fcd  mov     rax, [rbx+210h]
0x180077fd4  test    byte ptr [rax+40h], 1
0x180077fd8  jz      short loc_180077FE3
0x180077fda  cmp     [rbx+224h], r13d
0x180077fe1  jnz     short loc_18007802B
0x180077fe3  mov     ecx, [rax+24h]; cb
0x180077fe6  call    cs:__imp_CoTaskMemAlloc
0x180077fec  mov     [rsi+38h], rax
0x180077ff0  test    rax, rax
0x180077ff3  jz      loc_18007821E
0x180077ff9  mov     rdx, [rbx+210h]; Src
0x180078000  mov     rcx, rax; void *
0x180078003  mov     r8d, [rdx+24h]; Size
0x180078007  call    memcpy_0
0x18007800c  mov     rax, [rbx+210h]
0x180078013  mov     ecx, [rax+24h]
0x180078016  mov     [rsi+30h], ecx
0x180078019  mov     rax, [rbx+210h]
0x180078020  movups  xmm0, xmmword ptr [rax+10h]
0x180078024  movdqu  xmmword ptr [rdi+8], xmm0
0x180078029  jmp     short loc_180078033
0x18007802b  mov     [rsi+38h], r13
0x18007802f  mov     [rsi+30h], r13d
0x180078033  cmp     [rbx+218h], r13d
0x18007803a  jz      short loc_18007805F
0x18007803c  test    r12b, r12b
0x18007803f  jnz     short loc_18007805F
0x180078041  mov     rax, [rbx+210h]
0x180078048  mov     [rbp+98h], rax
0x18007804f  mov     rax, [rbx+210h]
0x180078056  mov     ecx, [rax+24h]
0x180078059  mov     [rbp+90h], ecx
0x18007805f  cmp     [rbx+21Ch], r13b
0x180078066  jz      short loc_1800780B8
0x180078068  test    r12b, r12b
0x18007806b  jnz     short loc_1800780B8
0x18007806d  cmp     [r14+0C24h], r13b
0x180078074  jz      short loc_1800780B8
0x180078076  mov     rax, [rbx+50h]
0x18007807a  lea     r15, [rbp+0B8h]
0x180078081  lea     r9, [rsp+0A8h+var_58]; struct _GUID
0x180078086  mov     rdx, r15; struct SPPREDICTORSET **
0x180078089  mov     rcx, [rax+58h]
0x18007808d  movups  xmm0, xmmword ptr [rcx+428h]
0x180078094  lea     rcx, [r14+630h]; this
0x18007809b  movdqu  xmmword ptr [rsp+0A8h+var_58.Data1], xmm0
0x1800780a1  call    ?ConvertToSapiVersion@CPredictorSet@@QEAAJPEAPEAUSPPREDICTORSET@@IU_GUID@@@Z; CPredictorSet::ConvertToSapiVersion(SPPREDICTORSET * *,uint,_GUID)
0x1800780a6  test    eax, eax
0x1800780a8  jns     short loc_1800780BF
0x1800780aa  mov     rcx, [r15]; pv
0x1800780ad  call    cs:__imp_CoTaskMemFree
0x1800780b3  mov     [r15], r13
0x1800780b6  jmp     short loc_1800780BF
0x1800780b8  mov     [rbp+0B8h], r13
0x1800780bf  mov     rax, [rbx+210h]
0x1800780c6  test    byte ptr [rax+40h], 1
0x1800780ca  jnz     short loc_1800780E3
0x1800780cc  cmp     [rbx+0A23h], r13b
0x1800780d3  jnz     short loc_1800780E3
0x1800780d5  mov     [rsi+48h], r13
0x1800780d9  mov     [rsi+50h], r13d
0x1800780dd  mov     [rbp+5Ch], r13b
0x1800780e1  jmp     short loc_180078119
0x1800780e3  mov     eax, [rbx+224h]
0x1800780e9  mov     rcx, [rbx+208h]; this
0x1800780f0  mov     edx, [rcx+3C0h]
0x1800780f6  cmp     eax, edx
0x1800780f8  cmovnb  eax, edx
0x1800780fb  lea     rdx, [rsp+0A8h+var_68]; unsigned int *
0x180078100  mov     [rsp+0A8h+var_68], eax
0x180078104  call    ?PackageAlternates@CLatticeWrapper@@IEAAPEAUtagSPPHRASEALT@@PEAK@Z; CLatticeWrapper::PackageAlternates(ulong *)
0x180078109  mov     [rsi+48h], rax
0x18007810d  neg     rax
0x180078110  sbb     ecx, ecx
0x180078112  and     ecx, [rsp+0A8h+var_68]
0x180078116  mov     [rsi+50h], ecx
0x180078119  mov     rax, [rbx+210h]
0x180078120  test    byte ptr [rax+40h], 1
0x180078124  jz      short loc_18007812F
0x180078126  cmp     [rbx+206h], r13b
0x18007812d  jz      short loc_180078134
0x18007812f  test    r12b, r12b
0x180078132  jz      short loc_180078150
0x180078134  mov     rcx, r14; this
0x180078137  call    ?UpdatePhraseBuilder@CPhrase@@QEAAJXZ; CPhrase::UpdatePhraseBuilder(void)
0x18007813c  mov     ebp, eax
0x18007813e  test    eax, eax
0x180078140  js      loc_180078223
0x180078146  lea     r15, [r14+18h]
0x18007814a  lea     r13, [rbx+50h]
0x18007814e  jmp     short loc_1800781C9
0x180078150  mov     rdx, [rbx+208h]
0x180078157  mov     [rsp+0A8h+var_68], r13d
0x18007815c  test    dword ptr [rdx+418h], 7FFFFFFFh
0x180078166  jz      short loc_180078171
0x180078168  mov     r9, [rdx+410h]
0x18007816f  jmp     short loc_180078174
0x180078171  mov     r9, r13
0x180078174  lea     r8, [rsp+0A8h+var_68]
0x180078179  mov     [rsp+0A8h+var_78], r8
0x18007817e  lea     r13, [rbx+50h]
0x180078182  mov     r8d, [rdx+454h]
0x180078189  lea     r15, [r14+18h]
0x18007818d  mov     rax, [r13+0]
0x180078191  mov     [rsp+0A8h+var_80], r8d
0x180078196  mov     r8d, [rdx+450h]
0x18007819d  mov     rdx, rbp
0x1800781a0  mov     [rsp+0A8h+var_88], r8d
0x1800781a5  mov     rcx, [rax+10h]
0x1800781a9  mov     r8, [r15]
0x1800781ac  mov     rax, [rcx]
0x1800781af  mov     rax, [rax+70h]
0x1800781b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800781b8  mov     ebp, eax
0x1800781ba  test    eax, eax
0x1800781bc  js      short loc_180078216
0x1800781be  cmp     [rsp+0A8h+var_68], 0
0x1800781c3  jz      short loc_1800781C9
0x1800781c5  or      dword ptr [rsi+4], 4
0x1800781c9  mov     rax, [r15]
0x1800781cc  mov     [rsi+40h], rax
0x1800781d0  mov     qword ptr [r15], 0
0x1800781d7  test    r12b, r12b
0x1800781da  jnz     short loc_180078209
0x1800781dc  cmp     [rbx+0A22h], r12b
0x1800781e3  jnz     short loc_180078209
0x1800781e5  mov     rax, [r13+0]
0x1800781e9  mov     rcx, r14; this
0x1800781ec  mov     rdx, [rbx+60h]
0x1800781f0  movss   xmm2, dword ptr [rax+1F4h]; float
0x1800781f8  mov     edx, [rdx+0C8h]; unsigned int
0x1800781fe  call    ?CheckTalkingSpeed@CPhrase@@QEAA?AW4SPINTERFERENCE@@KM@Z; CPhrase::CheckTalkingSpeed(ulong,float)
0x180078203  mov     [rbx+220h], eax
0x180078209  mov     rsi, [rsp+0A8h+arg_8]
0x180078211  xor     r13d, r13d
0x180078214  jmp     short loc_18007824E
0x180078216  xor     r13d, r13d
0x180078219  jmp     short loc_180078223
0x18007821b  mov     rdi, r13
0x18007821e  mov     ebp, 8007000Eh
0x180078223  mov     rcx, rsi; struct SPRECORESULTINFO *
0x180078226  call    ?FreeRecoResult@@YAXPEAUSPRECORESULTINFO@@@Z; FreeRecoResult(SPRECORESULTINFO *)
0x18007822b  test    rdi, rdi
0x18007822e  jz      loc_18007834C
0x180078234  mov     rcx, rdi; this
0x180078237  mov     [rdi+40h], r13
0x18007823b  call    ??_GCRecentReco@@QEAAPEAXI@Z; CRecentReco::`scalar deleting destructor'(uint)
0x180078240  jmp     loc_18007834C
0x180078245  mov     rdi, r13
0x180078248  mov     ebp, r13d
0x18007824b  mov     r14, r13
0x18007824e  cmp     [rbx+1900h], r13b
0x180078255  jz      loc_180078349
0x18007825b  test    r12b, r12b
0x18007825e  jnz     loc_180078349
0x180078264  cmp     [rbx+0A22h], r13b
0x18007826b  jnz     loc_180078349
0x180078271  cmp     [rbx+0A23h], r13b
0x180078278  jnz     loc_180078349
0x18007827e  movss   xmm1, dword ptr [rbx+1918h]
0x180078286  subss   xmm1, dword ptr [rbx+191Ch]
0x18007828e  cmp     [rbx+210h], r13
0x180078295  jz      short loc_18007830D
0x180078297  test    r14, r14
0x18007829a  jz      short loc_18007830D
0x18007829c  cmp     dword ptr [r14+330h], 1
0x1800782a4  jb      short loc_18007830D
0x1800782a6  movss   xmm0, cs:__real@40900000
0x1800782ae  comiss  xmm0, xmm1
0x1800782b1  jbe     loc_180078349
0x1800782b7  cvtps2pd xmm0, xmm1
0x1800782ba  comisd  xmm0, cs:__real@3f50624dd2f1a9fc
0x1800782c2  jbe     loc_180078349
0x1800782c8  mov     edx, [rbx+1904h]
0x1800782ce  mov     rax, [rbx+50h]
0x1800782d2  add     edx, [rbx+0BB4h]
0x1800782d8  imul    rdx, [rbx+1910h]
0x1800782e0  mov     rcx, [rax+10h]
0x1800782e4  add     rdx, [rbx+1908h]
0x1800782eb  mov     r8, [rcx]
0x1800782ee  mov     rax, [r8+30h]
0x1800782f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800782f7  mov     dword ptr [rbx+1918h], 0CE6E6B28h
0x180078301  mov     dword ptr [rbx+191Ch], 4E6E6B28h
0x18007830b  jmp     short loc_180078349
0x18007830d  cvtps2pd xmm0, xmm1
0x180078310  comisd  xmm0, cs:__real@3f50624dd2f1a9fc
0x180078318  jbe     short loc_180078349
0x18007831a  mov     edx, [rbx+1904h]
0x180078320  mov     rax, [rbx+50h]
0x180078324  add     edx, [rbx+0BB4h]
0x18007832a  imul    rdx, [rbx+1910h]
0x180078332  mov     rcx, [rax+10h]
0x180078336  add     rdx, [rbx+1908h]
0x18007833d  mov     r8, [rcx]
0x180078340  mov     rax, [r8+38h]
  ... truncated ...
```
