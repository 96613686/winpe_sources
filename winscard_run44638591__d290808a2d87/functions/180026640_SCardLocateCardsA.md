# SCardLocateCardsA

- ea: `0x180026640`
- end: `0x180026b9f`
- name: `SCardLocateCardsA`
- size: `1375`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCSTR mszCards, LPSCARD_READERSTATEA rgReaderStates, DWORD cReaders)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000bcf0`
- `0x18000bd10`
- `0x18000dbd0`
- `0x18000e3d0`
- `0x18000e680`
- `0x180011b0c`
- `0x1800126f0`
- `0x1800131dc`
- `0x180014b00`
- `0x18001b9b8`
- `0x18001ba04`
- `0x180024b4c`
- `0x180024f04`
- `0x180026640`
- `0x180026bb0`
- `0x18002a02c`
- `0x18002a7d8`
- `0x18002cc68`
- `0x18002ef20`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026775`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026775`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800267b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800267b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800268c8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180026913`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800268c8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180026913`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
LONG __stdcall SCardLocateCardsA(
        SCARDCONTEXT hContext,
        LPCSTR mszCards,
        LPSCARD_READERSTATEA rgReaderStates,
        DWORD cReaders)
{
  struct _SCARD_ATRMASK *v6; // rsi
  int v7; // r12d
  CHandleList *v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // r14
  struct CHandleList::HandlePtr *HandlePtr; // rax
  const unsigned __int16 *v11; // rax
  unsigned __int64 v12; // rax
  char *v13; // r14
  unsigned int v14; // ebx
  const unsigned __int16 *v15; // rax
  const unsigned __int16 *i; // rax
  const unsigned __int16 *v17; // r15
  __int64 v18; // r11
  __int64 v19; // r11
  __int64 v20; // rbx
  unsigned __int8 *v21; // rax
  size_t v22; // r8
  unsigned __int8 *v23; // rax
  size_t v24; // r8
  __int64 v25; // r12
  DWORD v26; // r15d
  size_t v27; // rbx
  __int64 v28; // rcx
  _BYTE *v29; // rdx
  _BYTE v31[32]; // [rsp+0h] [rbp-148h] BYREF
  LONG CardsByATRA; // [rsp+30h] [rbp-118h]
  int v33; // [rsp+34h] [rbp-114h]
  unsigned int v34; // [rsp+38h] [rbp-110h] BYREF
  unsigned __int64 v35; // [rsp+40h] [rbp-108h] BYREF
  char *v36; // [rsp+48h] [rbp-100h]
  ulong pExceptionObject; // [rsp+50h] [rbp-F8h] BYREF
  ulong v38; // [rsp+54h] [rbp-F4h] BYREF
  ulong v39; // [rsp+58h] [rbp-F0h] BYREF
  ulong v40; // [rsp+5Ch] [rbp-ECh] BYREF
  ulong v41[2]; // [rsp+60h] [rbp-E8h] BYREF
  ulong v42; // [rsp+68h] [rbp-E0h] BYREF
  ulong v43; // [rsp+6Ch] [rbp-DCh] BYREF
  ulong v44; // [rsp+70h] [rbp-D8h] BYREF
  struct _SCARD_ATRMASK *v45; // [rsp+78h] [rbp-D0h]
  void *Src; // [rsp+80h] [rbp-C8h] BYREF
  unsigned int v47[2]; // [rsp+88h] [rbp-C0h]
  LONG v48; // [rsp+90h] [rbp-B8h] BYREF
  __int64 v49; // [rsp+98h] [rbp-B0h]
  _QWORD v50[2]; // [rsp+A0h] [rbp-A8h] BYREF
  unsigned int v51; // [rsp+B0h] [rbp-98h]
  void **v52; // [rsp+C0h] [rbp-88h] BYREF
  int v53; // [rsp+C8h] [rbp-80h]
  const int *v54; // [rsp+D0h] [rbp-78h]
  __int64 v55; // [rsp+D8h] [rbp-70h]
  int v56; // [rsp+E0h] [rbp-68h]
  int v57; // [rsp+E4h] [rbp-64h]
  const int *v58; // [rsp+E8h] [rbp-60h]
  __int64 v59; // [rsp+F0h] [rbp-58h]
  int v60; // [rsp+F8h] [rbp-50h]
  int v61; // [rsp+FCh] [rbp-4Ch]
  _QWORD v62[9]; // [rsp+100h] [rbp-48h] BYREF

  CardsByATRA = 0;
  v6 = 0;
  v45 = 0;
  v35 = 0;
  v36 = 0;
  Src = 0;
  v34 = 0;
  v7 = 0;
  try
  {
    if ( !rgReaderStates )
    {
      pExceptionObject = -2146435068;
      throw &pExceptionObject;
    }
    v54 = &CBuffer::`vftable';
    v55 = 0;
    v56 = 0;
    v57 = 0;
    v58 = &CBuffer::`vftable';
    v59 = 0;
    v60 = 0;
    v61 = 0;
    v53 = 3;
    v52 = &CTextMultistring::`vftable';
    v33 = 0;
    CBuffer::CBuffer((CBuffer *)v50, 0x24u);
    CBuffer::CBuffer((CBuffer *)v62, 0x24u);
    v8 = g_phlContexts;
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    *(_QWORD *)v47 = (char *)g_phlContexts + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    HandlePtr = CHandleList::GetHandlePtr(v8, hContext);
    if ( !HandlePtr )
    {
      v38 = 6;
      throw &v38;
    }
    v49 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v9);
    if ( *(_DWORD *)(v49 + 16) )
    {
      v39 = -2146435042;
      throw &v39;
    }
    if ( !*mszCards )
    {
      v40 = -2146435055;
      throw &v40;
    }
    v47[0] = *(_DWORD *)(v49 + 28);
    CTextString::operator=(&v52, mszCards);
    v11 = CTextString::Unicode((CTextString *)&v52);
    v12 = saturated_mul(MStringCount(v11), 0x4Cu);
    v13 = (char *)operator new[](v12);
    v36 = v13;
    if ( !v13 )
    {
      v41[0] = -2146435066;
      throw v41;
    }
    v14 = 0;
    v33 = 0;
    v15 = CTextString::Unicode((CTextString *)&v52);
    for ( i = FirstString(v15); ; i = NextString(v17) )
    {
      v17 = i;
      if ( !i )
        break;
      if ( ((unsigned int)StringCchLengthW(i, 0x27u, &v35)
         || v18 != v35 + 1
         || lstrcmpW(v17, L"Identity Device (NIST SP 800-73 [PIV])"))
        && ((unsigned int)StringCchLengthW(v17, 0x2Cu, &v35)
         || v19 != v35 + 1
         || lstrcmpW(v17, L"Identity Device (Microsoft Generic Profile)")) )
      {
        if ( !GetCardInfo(v47[0], v17, (struct CBuffer *)v50, (struct CBuffer *)v62, 0, 0) )
        {
          v42 = -2146435059;
          throw &v42;
        }
        if ( v51 > 0x21 )
        {
          v43 = -2146435068;
          throw &v43;
        }
        v20 = 76LL * v14;
        *(_DWORD *)&v13[v20] = v51;
        v21 = CBuffer::Access((CBuffer *)v50, 0);
        memcpy_0(&v13[v20 + 4], v21, v22);
        v23 = CBuffer::Access((CBuffer *)v62, 0);
        memcpy_0(&v13[v20 + 40], v23, v24);
        v14 = ++v33;
      }
      else
      {
        v7 = 1;
        v41[1] = 1;
      }
    }
    if ( v7 == 1 )
      LocateCLMDDevicesA(hContext, rgReaderStates, cReaders, (struct _SCARD_ATRMASK **)&Src, &v34);
    v25 = v34;
    v26 = v14 + v34;
    if ( v14 + v34 )
    {
      v6 = (struct _SCARD_ATRMASK *)operator new[](saturated_mul(v26, 0x4Cu));
      v45 = v6;
      if ( !v6 )
      {
        v44 = -2146435066;
        throw &v44;
      }
      v27 = v14;
      memcpy_0(v6, v13, v27 * 76);
      memcpy_0(&v6[v27], Src, 76 * v25);
    }
    if ( v6 )
    {
      CardsByATRA = SCardLocateCardsByATRA(hContext, v6, v26, rgReaderStates, cReaders);
      if ( CardsByATRA == 120 )
      {
        v28 = *(_QWORD *)(v49 + 128);
        if ( v28 )
          CardsByATRA = RedirectedSCardLocateCardsA(
                          v28,
                          mszCards,
                          (struct SCARD_READERSTATEW *)rgReaderStates,
                          cReaders);
      }
    }
    v62[0] = &CBuffer::`vftable';
    CBuffer::Clear((CBuffer *)v62);
    v50[0] = &CBuffer::`vftable';
    CBuffer::Clear((CBuffer *)v50);
    CTextMultistring::~CTextMultistring((CTextMultistring *)&v52);
  }
  catch ( ulong v48 )
  {
    v29 = v31;
    CardsByATRA = v48;
    v13 = v36;
    v6 = v45;
  }
  catch ( ... )
  {
    v29 = v31;
    CardsByATRA = -2146435068;
    v13 = v36;
    v6 = v45;
  }
  if ( v6 )
  {
    try
    {
      operator delete(v6, (unsigned __int64)v29);
    }
    catch ( ... )
    {
      v29 = v31;
      v13 = v36;
    }
  }
  if ( v13 )
  {
    try
    {
      operator delete(v13, (unsigned __int64)v29);
    }
    catch ( ... )
    {
      v29 = v31;
    }
  }
  if ( Src )
  {
    try
    {
      operator delete(Src, (unsigned __int64)v29);
    }
    catch ( ... )
    {
    }
  }
  return CardsByATRA;
}

```

## disassembly

```asm
0x180026640  mov     rax, rsp
0x180026643  mov     [rax+18h], rbx
0x180026647  mov     [rax+20h], r9d
0x18002664b  mov     [rax+10h], rdx
0x18002664f  mov     [rax+8], rcx
0x180026653  push    rsi
0x180026654  push    r12
0x180026656  push    r13
0x180026658  push    r14
0x18002665a  push    r15
0x18002665c  sub     rsp, 120h
0x180026663  mov     r13, r8
0x180026666  mov     r15, rcx
0x180026669  mov     [rsp+148h+var_118], 0
0x180026671  xor     esi, esi
0x180026673  mov     [rsp+148h+var_D0], rsi
0x180026678  mov     [rsp+148h+var_108], rsi
0x18002667d  mov     [rsp+148h+var_100], rsi
0x180026682  mov     [rax-0C8h], rsi
0x180026689  mov     [rsp+148h+var_110], esi
0x18002668d  xor     r12d, r12d
0x180026690  test    r8, r8
0x180026693  jnz     short loc_1800266AE
0x180026695  mov     [rsp+148h+pExceptionObject], 80100004h
0x18002669d  lea     rdx, _TI1K; pThrowInfo
0x1800266a4  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x1800266a9  call    _CxxThrowException_0
0x1800266ae  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x1800266b5  mov     [rsp+148h+var_88], rax
0x1800266bd  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800266c4  mov     [rsp+148h+var_78], rax
0x1800266cc  mov     [rsp+148h+var_70], 0
0x1800266d8  mov     [rsp+148h+var_68], 0
0x1800266e3  mov     [rsp+148h+var_64], 0
0x1800266ee  mov     [rsp+148h+var_60], rax
0x1800266f6  mov     [rsp+148h+var_58], 0
0x180026702  mov     [rsp+148h+var_50], 0
0x18002670d  mov     [rsp+148h+var_4C], 0
0x180026718  mov     [rsp+148h+var_80], 3
0x180026723  lea     rax, ??_7CTextMultistring@@6B@; const CTextMultistring::`vftable'
0x18002672a  mov     [rsp+148h+var_88], rax
0x180026732  mov     [rsp+148h+var_114], 0
0x18002673a  mov     ebx, 24h ; '$'
0x18002673f  mov     edx, ebx; unsigned int
0x180026741  lea     rcx, [rsp+148h+var_A8]; this
0x180026749  call    ??0CBuffer@@QEAA@K@Z; CBuffer::CBuffer(ulong)
0x18002674e  nop
0x18002674f  mov     edx, ebx; unsigned int
0x180026751  lea     rcx, [rsp+148h+var_48]; this
0x180026759  call    ??0CBuffer@@QEAA@K@Z; CBuffer::CBuffer(ulong)
0x18002675e  nop
0x18002675f  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180026766  lea     r14, [rbx+20h]
0x18002676a  mov     qword ptr [rsp+148h+var_C0], r14
0x180026772  mov     rcx, r14; lpCriticalSection
0x180026775  call    cs:__imp_EnterCriticalSection
0x18002677b  nop
0x18002677c  mov     rdx, r15; unsigned __int64
0x18002677f  mov     rcx, rbx; this
0x180026782  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x180026787  test    rax, rax
0x18002678a  jnz     short loc_1800267A5
0x18002678c  mov     [rsp+148h+var_F4], 6
0x180026794  lea     rdx, _TI1K; pThrowInfo
0x18002679b  lea     rcx, [rsp+148h+var_F4]; pExceptionObject
0x1800267a0  call    _CxxThrowException_0
0x1800267a5  mov     rbx, [rax]
0x1800267a8  mov     [rsp+148h+var_B0], rbx
0x1800267b0  mov     rcx, r14; lpCriticalSection
0x1800267b3  call    cs:__imp_LeaveCriticalSection
0x1800267b9  cmp     dword ptr [rbx+10h], 0
0x1800267bd  jz      short loc_1800267D8
0x1800267bf  mov     [rsp+148h+var_F0], 8010001Eh
0x1800267c7  lea     rdx, _TI1K; pThrowInfo
0x1800267ce  lea     rcx, [rsp+148h+var_F0]; pExceptionObject
0x1800267d3  call    _CxxThrowException_0
0x1800267d8  mov     rax, [rsp+148h+arg_8]
0x1800267e0  cmp     byte ptr [rax], 0
0x1800267e3  jnz     short loc_1800267FE
0x1800267e5  mov     [rsp+148h+var_EC], 80100011h
0x1800267ed  lea     rdx, _TI1K; pThrowInfo
0x1800267f4  lea     rcx, [rsp+148h+var_EC]; pExceptionObject
0x1800267f9  call    _CxxThrowException_0
0x1800267fe  mov     ecx, [rbx+1Ch]
0x180026801  mov     [rsp+148h+var_C0], ecx
0x180026808  mov     rdx, rax
0x18002680b  lea     rcx, [rsp+148h+var_88]
0x180026813  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x180026818  lea     rcx, [rsp+148h+var_88]; this
0x180026820  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180026825  mov     rcx, rax; unsigned __int16 *
0x180026828  call    ?MStringCount@@YAKPEBG@Z; MStringCount(ushort const *)
0x18002682d  mov     ecx, eax
0x18002682f  mov     eax, 4Ch ; 'L'
0x180026834  mul     rcx
0x180026837  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002683e  cmovb   rax, rcx
0x180026842  mov     rcx, rax; unsigned __int64
0x180026845  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002684a  mov     r14, rax
0x18002684d  mov     [rsp+148h+var_100], rax
0x180026852  test    rax, rax
0x180026855  jnz     short loc_180026870
0x180026857  mov     [rsp+148h+var_E8], 80100006h
0x18002685f  lea     rdx, _TI1K; pThrowInfo
0x180026866  lea     rcx, [rsp+148h+var_E8]; pExceptionObject
0x18002686b  call    _CxxThrowException_0
0x180026870  xor     ebx, ebx
0x180026872  mov     [rsp+148h+var_114], ebx
0x180026876  lea     rcx, [rsp+148h+var_88]; this
0x18002687e  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180026883  mov     rcx, rax; unsigned __int16 *
0x180026886  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x18002688b  mov     r15, rax
0x18002688e  test    rax, rax
0x180026891  jz      loc_1800269F4
0x180026897  lea     r8, [rsp+148h+var_108]; unsigned __int64 *
0x18002689c  mov     r11d, 27h ; '''
0x1800268a2  mov     edx, r11d; unsigned __int64
0x1800268a5  mov     rcx, rax; unsigned __int16 *
0x1800268a8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800268ad  test    eax, eax
0x1800268af  jnz     short loc_1800268E2
0x1800268b1  mov     rax, [rsp+148h+var_108]
0x1800268b6  inc     rax
0x1800268b9  cmp     r11, rax
0x1800268bc  jnz     short loc_1800268E2
0x1800268be  lea     rdx, String2; "Identity Device (NIST SP 800-73 [PIV])"
0x1800268c5  mov     rcx, r15; lpString1
0x1800268c8  call    cs:__imp_lstrcmpW
0x1800268ce  test    eax, eax
0x1800268d0  jnz     short loc_1800268E2
0x1800268d2  mov     r12d, 1
0x1800268d8  mov     [rsp+148h+var_E4], r12d
0x1800268dd  jmp     loc_1800269E7
0x1800268e2  lea     r8, [rsp+148h+var_108]; unsigned __int64 *
0x1800268e7  mov     r11d, 2Ch ; ','
0x1800268ed  mov     edx, r11d; unsigned __int64
0x1800268f0  mov     rcx, r15; unsigned __int16 *
0x1800268f3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800268f8  test    eax, eax
0x1800268fa  jnz     short loc_18002691D
0x1800268fc  mov     rax, [rsp+148h+var_108]
0x180026901  inc     rax
0x180026904  cmp     r11, rax
0x180026907  jnz     short loc_18002691D
0x180026909  lea     rdx, aIdentityDevice; "Identity Device (Microsoft Generic Prof"...
0x180026910  mov     rcx, r15; lpString1
0x180026913  call    cs:__imp_lstrcmpW
0x180026919  test    eax, eax
0x18002691b  jz      short loc_1800268D2
0x18002691d  mov     [rsp+148h+var_120], 0; struct CBuffer *
0x180026926  mov     qword ptr [rsp+148h+cReaders], 0; struct CBuffer *
0x18002692f  lea     r9, [rsp+148h+var_48]; struct CBuffer *
0x180026937  lea     r8, [rsp+148h+var_A8]; struct CBuffer *
0x18002693f  mov     rdx, r15; unsigned __int16 *
0x180026942  mov     ecx, [rsp+148h+var_C0]; unsigned int
0x180026949  call    ?GetCardInfo@@YAHKPEBGPEAVCBuffer@@111@Z; GetCardInfo(ulong,ushort const *,CBuffer *,CBuffer *,CBuffer *,CBuffer *)
0x18002694e  test    eax, eax
0x180026950  jnz     short loc_18002696B
0x180026952  mov     [rsp+148h+var_E0], 8010000Dh
0x18002695a  lea     rdx, _TI1K; pThrowInfo
0x180026961  lea     rcx, [rsp+148h+var_E0]; pExceptionObject
0x180026966  call    _CxxThrowException_0
0x18002696b  mov     ecx, [rsp+148h+var_98]
0x180026972  cmp     ecx, 21h ; '!'
0x180026975  jbe     short loc_180026990
0x180026977  mov     [rsp+148h+var_DC], 80100004h
0x18002697f  lea     rdx, _TI1K; pThrowInfo
0x180026986  lea     rcx, [rsp+148h+var_DC]; pExceptionObject
0x18002698b  call    _CxxThrowException_0
0x180026990  mov     eax, ebx
0x180026992  imul    rbx, rax, 4Ch ; 'L'
0x180026996  mov     [rbx+r14], ecx
0x18002699a  mov     r8, rcx
0x18002699d  xor     edx, edx; unsigned int
0x18002699f  lea     rcx, [rsp+148h+var_A8]; this
0x1800269a7  call    ?Access@CBuffer@@QEBAPEAEK@Z; CBuffer::Access(ulong)
0x1800269ac  mov     rdx, rax; Src
0x1800269af  lea     rcx, [r14+4]
0x1800269b3  add     rcx, rbx; void *
0x1800269b6  call    memcpy_0
0x1800269bb  mov     r8d, [rbx+r14]
0x1800269bf  xor     edx, edx; unsigned int
0x1800269c1  lea     rcx, [rsp+148h+var_48]; this
0x1800269c9  call    ?Access@CBuffer@@QEBAPEAEK@Z; CBuffer::Access(ulong)
0x1800269ce  mov     rdx, rax; Src
0x1800269d1  lea     rcx, [r14+28h]
0x1800269d5  add     rcx, rbx; void *
0x1800269d8  call    memcpy_0
0x1800269dd  mov     ebx, [rsp+148h+var_114]
0x1800269e1  inc     ebx
0x1800269e3  mov     [rsp+148h+var_114], ebx
0x1800269e7  mov     rcx, r15; unsigned __int16 *
0x1800269ea  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x1800269ef  jmp     loc_18002688B
0x1800269f4  cmp     r12d, 1
0x1800269f8  jnz     short loc_180026A24
0x1800269fa  lea     rcx, [rsp+148h+var_110]
0x1800269ff  mov     qword ptr [rsp+148h+cReaders], rcx; unsigned int *
0x180026a04  lea     r9, [rsp+148h+Src]; struct _SCARD_ATRMASK **
0x180026a0c  mov     r8d, [rsp+148h+arg_18]; unsigned int
0x180026a14  mov     rdx, r13; struct SCARD_READERSTATEA *
0x180026a17  mov     rcx, [rsp+148h+hContext]; unsigned __int64
0x180026a1f  call    ?LocateCLMDDevicesA@@YAX_KPEAUSCARD_READERSTATEA@@KPEAPEAU_SCARD_ATRMASK@@PEAK@Z; LocateCLMDDevicesA(unsigned __int64,SCARD_READERSTATEA *,ulong,_SCARD_ATRMASK * *,ulong *)
0x180026a24  mov     r12d, [rsp+148h+var_110]
0x180026a29  lea     r15d, [rbx+r12]
0x180026a2d  test    r15d, r15d
0x180026a30  jz      short loc_180026A9F
0x180026a32  mov     ecx, r15d
0x180026a35  mov     eax, 4Ch ; 'L'
0x180026a3a  mul     rcx
0x180026a3d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180026a44  cmovb   rax, rcx
0x180026a48  mov     rcx, rax; unsigned __int64
0x180026a4b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180026a50  mov     rsi, rax
0x180026a53  mov     [rsp+148h+var_D0], rax
0x180026a58  test    rax, rax
0x180026a5b  jnz     short loc_180026A76
0x180026a5d  mov     [rsp+148h+var_D8], 80100006h
0x180026a65  lea     rdx, _TI1K; pThrowInfo
0x180026a6c  lea     rcx, [rsp+148h+var_D8]; pExceptionObject
0x180026a71  call    _CxxThrowException_0
0x180026a76  mov     eax, ebx
0x180026a78  imul    rbx, rax, 4Ch ; 'L'
0x180026a7c  mov     r8, rbx; Size
0x180026a7f  mov     rdx, r14; Src
0x180026a82  mov     rcx, rsi; void *
0x180026a85  call    memcpy_0
0x180026a8a  imul    r8, r12, 4Ch ; 'L'; Size
0x180026a8e  lea     rcx, [rbx+rsi]; void *
0x180026a92  mov     rdx, [rsp+148h+Src]; Src
0x180026a9a  call    memcpy_0
0x180026a9f  test    rsi, rsi
0x180026aa2  jz      short loc_180026AF9
0x180026aa4  mov     ebx, [rsp+148h+arg_18]
0x180026aab  mov     [rsp+148h+cReaders], ebx; cReaders
0x180026aaf  mov     r9, r13; rgReaderStates
0x180026ab2  mov     r8d, r15d; cAtrs
0x180026ab5  mov     rdx, rsi; rgAtrMasks
0x180026ab8  mov     rcx, [rsp+148h+hContext]; hContext
0x180026ac0  call    SCardLocateCardsByATRA
0x180026ac5  mov     [rsp+148h+var_118], eax
0x180026ac9  cmp     eax, 78h ; 'x'
0x180026acc  jnz     short loc_180026AF9
0x180026ace  mov     rcx, [rsp+148h+var_B0]
0x180026ad6  mov     rcx, [rcx+80h]; unsigned __int64
0x180026add  test    rcx, rcx
0x180026ae0  jz      short loc_180026AF9
0x180026ae2  mov     r9d, ebx; unsigned int
0x180026ae5  mov     r8, r13; struct SCARD_READERSTATEA *
0x180026ae8  mov     rdx, [rsp+148h+arg_8]; char *
0x180026af0  call    ?RedirectedSCardLocateCardsA@@YAJ_KPEBDPEAUSCARD_READERSTATEA@@K@Z; RedirectedSCardLocateCardsA(unsigned __int64,char const *,SCARD_READERSTATEA *,ulong)
0x180026af5  mov     [rsp+148h+var_118], eax
0x180026af9  lea     rbx, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180026b00  mov     [rsp+148h+var_48], rbx
0x180026b08  lea     rcx, [rsp+148h+var_48]; this
0x180026b10  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180026b15  nop
0x180026b16  mov     [rsp+148h+var_A8], rbx
0x180026b1e  lea     rcx, [rsp+148h+var_A8]; this
0x180026b26  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180026b2b  nop
0x180026b2c  lea     rcx, [rsp+148h+var_88]; this
0x180026b34  call    ??1CTextMultistring@@UEAA@XZ; CTextMultistring::~CTextMultistring(void)
0x180026b39  nop
0x180026b3a  jmp     short loc_180026B48
0x180026b3c  jmp     short $+2
0x180026b3e  mov     r14, [rsp+148h+var_100]
0x180026b43  mov     rsi, [rsp+148h+var_D0]
0x180026b48  test    rsi, rsi
0x180026b4b  jz      short loc_180026B5D
0x180026b4d  mov     rcx, rsi; void *
0x180026b50  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026b55  nop
0x180026b56  jmp     short loc_180026B5D
0x180026b58  mov     r14, [rsp+148h+var_100]
0x180026b5d  test    r14, r14
0x180026b60  jz      short loc_180026B6D
0x180026b62  mov     rcx, r14; void *
0x180026b65  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026b6a  nop
0x180026b6b  jmp     short $+2
0x180026b6d  mov     rcx, [rsp+148h+Src]; void *
0x180026b75  test    rcx, rcx
0x180026b78  jz      short loc_180026B82
0x180026b7a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026b7f  nop
0x180026b80  jmp     short $+2
0x180026b82  mov     eax, [rsp+148h+var_118]
0x180026b86  mov     rbx, [rsp+148h+arg_10]
0x180026b8e  add     rsp, 120h
0x180026b95  pop     r15
0x180026b97  pop     r14
0x180026b99  pop     r13
0x180026b9b  pop     r12
0x180026b9d  pop     rsi
0x180026b9e  retn
```
