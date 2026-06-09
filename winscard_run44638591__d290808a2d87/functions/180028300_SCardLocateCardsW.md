# SCardLocateCardsW

- ea: `0x180028300`
- end: `0x18002878a`
- name: `SCardLocateCardsW`
- size: `1162`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCWSTR mszCards, LPSCARD_READERSTATEW rgReaderStates, DWORD cReaders)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000bcf0`
- `0x18000bd10`
- `0x18000e3d0`
- `0x1800126f0`
- `0x1800131dc`
- `0x180014b00`
- `0x18001b9b8`
- `0x18001ba04`
- `0x180024f04`
- `0x180026fb0`
- `0x180028160`
- `0x180028300`
- `0x18002a02c`
- `0x18002a7d8`
- `0x18002d5bc`
- `0x18002ef20`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800283a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800283a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800283ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800283ec`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800284cf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18002851a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800284cf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18002851a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LONG __stdcall SCardLocateCardsW(
        SCARDCONTEXT hContext,
        LPCWSTR mszCards,
        LPSCARD_READERSTATEW rgReaderStates,
        DWORD cReaders)
{
  struct _SCARD_ATRMASK *v6; // rsi
  int v7; // r12d
  CHandleList *v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // r14
  struct CHandleList::HandlePtr *HandlePtr; // rax
  unsigned __int64 v11; // rax
  char *v12; // r14
  unsigned int v13; // ebx
  const unsigned __int16 *i; // rax
  const unsigned __int16 *v15; // r15
  __int64 v16; // r11
  __int64 v17; // r11
  __int64 v18; // rbx
  unsigned __int8 *v19; // rax
  size_t v20; // r8
  unsigned __int8 *v21; // rax
  size_t v22; // r8
  __int64 v23; // r12
  DWORD v24; // r15d
  size_t v25; // rbx
  __int64 v26; // rcx
  LONG CardsByATRW; // [rsp+30h] [rbp-D8h]
  int v29; // [rsp+34h] [rbp-D4h]
  unsigned int v30; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int64 v31; // [rsp+40h] [rbp-C8h] BYREF
  char *v32; // [rsp+48h] [rbp-C0h]
  ulong pExceptionObject; // [rsp+50h] [rbp-B8h] BYREF
  ulong v34; // [rsp+54h] [rbp-B4h] BYREF
  ulong v35; // [rsp+58h] [rbp-B0h] BYREF
  ulong v36; // [rsp+5Ch] [rbp-ACh] BYREF
  ulong v37[2]; // [rsp+60h] [rbp-A8h] BYREF
  ulong v38; // [rsp+68h] [rbp-A0h] BYREF
  ulong v39; // [rsp+6Ch] [rbp-9Ch] BYREF
  ulong v40; // [rsp+70h] [rbp-98h] BYREF
  struct _SCARD_ATRMASK *v41; // [rsp+78h] [rbp-90h]
  void *Src; // [rsp+80h] [rbp-88h] BYREF
  unsigned int v43[2]; // [rsp+88h] [rbp-80h]
  LONG v44; // [rsp+90h] [rbp-78h] BYREF
  __int64 v45; // [rsp+98h] [rbp-70h]
  _QWORD v46[2]; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v47; // [rsp+B0h] [rbp-58h]
  _QWORD v48[10]; // [rsp+B8h] [rbp-50h] BYREF

  CardsByATRW = 0;
  v6 = 0;
  v41 = 0;
  v31 = 0;
  v32 = 0;
  Src = 0;
  v30 = 0;
  v7 = 0;
  try
  {
    if ( !rgReaderStates )
    {
      pExceptionObject = -2146435068;
      throw &pExceptionObject;
    }
    CBuffer::CBuffer((CBuffer *)v46, 0x24u);
    CBuffer::CBuffer((CBuffer *)v48, 0x24u);
    v8 = g_phlContexts;
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    *(_QWORD *)v43 = (char *)g_phlContexts + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    HandlePtr = CHandleList::GetHandlePtr(v8, hContext);
    if ( !HandlePtr )
    {
      v34 = 6;
      throw &v34;
    }
    v45 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v9);
    if ( *(_DWORD *)(v45 + 16) )
    {
      v35 = -2146435042;
      throw &v35;
    }
    if ( !*mszCards )
    {
      v36 = -2146435055;
      throw &v36;
    }
    v43[0] = *(_DWORD *)(v45 + 28);
    v11 = saturated_mul(MStringCount(mszCards), 0x4Cu);
    v12 = (char *)operator new[](v11);
    v32 = v12;
    if ( !v12 )
    {
      v37[0] = -2146435066;
      throw v37;
    }
    v13 = 0;
    v29 = 0;
    for ( i = FirstString(mszCards); ; i = NextString(v15) )
    {
      v15 = i;
      if ( !i )
        break;
      if ( ((unsigned int)StringCchLengthW(i, 0x27u, &v31)
         || v16 != v31 + 1
         || lstrcmpW(v15, L"Identity Device (NIST SP 800-73 [PIV])"))
        && ((unsigned int)StringCchLengthW(v15, 0x2Cu, &v31)
         || v17 != v31 + 1
         || lstrcmpW(v15, L"Identity Device (Microsoft Generic Profile)")) )
      {
        if ( !GetCardInfo(v43[0], v15, (struct CBuffer *)v46, (struct CBuffer *)v48, 0, 0) )
        {
          v38 = -2146435059;
          throw &v38;
        }
        if ( v47 > 0x21 )
        {
          v39 = -2146435068;
          throw &v39;
        }
        v18 = 76LL * v13;
        *(_DWORD *)&v12[v18] = v47;
        v19 = CBuffer::Access((CBuffer *)v46, 0);
        memcpy_0(&v12[v18 + 4], v19, v20);
        v21 = CBuffer::Access((CBuffer *)v48, 0);
        memcpy_0(&v12[v18 + 40], v21, v22);
        v13 = ++v29;
      }
      else
      {
        v7 = 1;
        v37[1] = 1;
      }
    }
    if ( v7 == 1 )
      LocateCLMDDevicesW(hContext, rgReaderStates, cReaders, (struct _SCARD_ATRMASK **)&Src, &v30);
    v23 = v30;
    v24 = v13 + v30;
    if ( v13 + v30 )
    {
      v6 = (struct _SCARD_ATRMASK *)operator new[](saturated_mul(v24, 0x4Cu));
      v41 = v6;
      if ( !v6 )
      {
        v40 = -2146435066;
        throw &v40;
      }
      v25 = v13;
      memcpy_0(v6, v12, v25 * 76);
      memcpy_0(&v6[v25], Src, 76 * v23);
    }
    if ( v6 )
    {
      CardsByATRW = SCardLocateCardsByATRW(hContext, v6, v24, rgReaderStates, cReaders);
      if ( CardsByATRW == 120 )
      {
        v26 = *(_QWORD *)(v45 + 128);
        if ( v26 )
          CardsByATRW = RedirectedSCardLocateCardsW(v26, mszCards, rgReaderStates, cReaders);
      }
    }
    v48[0] = &CBuffer::`vftable';
    CBuffer::Clear((CBuffer *)v48);
    v46[0] = &CBuffer::`vftable';
    CBuffer::Clear((CBuffer *)v46);
  }
  catch ( ulong v44 )
  {
    CardsByATRW = v44;
    v12 = v32;
    v6 = v41;
  }
  catch ( ... )
  {
    CardsByATRW = -2146435068;
    v12 = v32;
    v6 = v41;
  }
  if ( v6 )
  {
    try
    {
      operator delete(v6);
    }
    catch ( ... )
    {
      v12 = v32;
    }
  }
  if ( v12 )
  {
    try
    {
      operator delete(v12);
    }
    catch ( ... )
    {
    }
  }
  if ( Src )
  {
    try
    {
      operator delete(Src);
    }
    catch ( ... )
    {
    }
  }
  return CardsByATRW;
}

```

## disassembly

```asm
0x180028300  mov     rax, rsp
0x180028303  mov     [rax+20h], r9d
0x180028307  mov     [rax+10h], rdx
0x18002830b  mov     [rax+8], rcx
0x18002830f  push    rbx
0x180028310  push    rsi
0x180028311  push    rdi
0x180028312  push    r12
0x180028314  push    r13
0x180028316  push    r14
0x180028318  push    r15
0x18002831a  sub     rsp, 0D0h
0x180028321  mov     r13, r8
0x180028324  mov     r15, rdx
0x180028327  xor     edi, edi
0x180028329  mov     [rsp+108h+var_D8], edi
0x18002832d  mov     esi, edi
0x18002832f  mov     [rsp+108h+var_90], rdi
0x180028334  mov     [rsp+108h+var_C8], rdi
0x180028339  mov     [rsp+108h+var_C0], rdi
0x18002833e  mov     [rax-88h], rdi
0x180028345  mov     [rsp+108h+var_D0], edi
0x180028349  mov     r12d, edi
0x18002834c  test    r8, r8
0x18002834f  jnz     short loc_18002836A
0x180028351  mov     [rsp+108h+pExceptionObject], 80100004h
0x180028359  lea     rdx, _TI1K; pThrowInfo
0x180028360  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180028365  call    _CxxThrowException_0
0x18002836a  mov     [rsp+108h+var_D4], edi
0x18002836e  mov     ebx, 24h ; '$'
0x180028373  mov     edx, ebx; unsigned int
0x180028375  lea     rcx, [rsp+108h+var_68]; this
0x18002837d  call    ??0CBuffer@@QEAA@K@Z; CBuffer::CBuffer(ulong)
0x180028382  nop
0x180028383  mov     edx, ebx; unsigned int
0x180028385  lea     rcx, [rsp+108h+var_50]; this
0x18002838d  call    ??0CBuffer@@QEAA@K@Z; CBuffer::CBuffer(ulong)
0x180028392  nop
0x180028393  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x18002839a  lea     r14, [rbx+20h]
0x18002839e  mov     qword ptr [rsp+108h+var_80], r14
0x1800283a6  mov     rcx, r14; lpCriticalSection
0x1800283a9  call    cs:__imp_EnterCriticalSection
0x1800283af  nop
0x1800283b0  mov     rdx, [rsp+108h+hContext]; unsigned __int64
0x1800283b8  mov     rcx, rbx; this
0x1800283bb  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x1800283c0  test    rax, rax
0x1800283c3  jnz     short loc_1800283DE
0x1800283c5  mov     [rsp+108h+var_B4], 6
0x1800283cd  lea     rdx, _TI1K; pThrowInfo
0x1800283d4  lea     rcx, [rsp+108h+var_B4]; pExceptionObject
0x1800283d9  call    _CxxThrowException_0
0x1800283de  mov     rbx, [rax]
0x1800283e1  mov     [rsp+108h+var_70], rbx
0x1800283e9  mov     rcx, r14; lpCriticalSection
0x1800283ec  call    cs:__imp_LeaveCriticalSection
0x1800283f2  cmp     [rbx+10h], edi
0x1800283f5  jz      short loc_180028410
0x1800283f7  mov     [rsp+108h+var_B0], 8010001Eh
0x1800283ff  lea     rdx, _TI1K; pThrowInfo
0x180028406  lea     rcx, [rsp+108h+var_B0]; pExceptionObject
0x18002840b  call    _CxxThrowException_0
0x180028410  cmp     di, [r15]
0x180028414  jnz     short loc_18002842F
0x180028416  mov     [rsp+108h+var_AC], 80100011h
0x18002841e  lea     rdx, _TI1K; pThrowInfo
0x180028425  lea     rcx, [rsp+108h+var_AC]; pExceptionObject
0x18002842a  call    _CxxThrowException_0
0x18002842f  mov     eax, [rbx+1Ch]
0x180028432  mov     [rsp+108h+var_80], eax
0x180028439  mov     rcx, r15; unsigned __int16 *
0x18002843c  call    ?MStringCount@@YAKPEBG@Z; MStringCount(ushort const *)
0x180028441  mov     ecx, eax
0x180028443  mov     eax, 4Ch ; 'L'
0x180028448  mul     rcx
0x18002844b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180028452  cmovb   rax, rcx
0x180028456  mov     rcx, rax; unsigned __int64
0x180028459  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002845e  mov     r14, rax
0x180028461  mov     [rsp+108h+var_C0], rax
0x180028466  test    rax, rax
0x180028469  jnz     short loc_180028484
0x18002846b  mov     [rsp+108h+var_A8], 80100006h
0x180028473  lea     rdx, _TI1K; pThrowInfo
0x18002847a  lea     rcx, [rsp+108h+var_A8]; pExceptionObject
0x18002847f  call    _CxxThrowException_0
0x180028484  mov     ebx, edi
0x180028486  mov     [rsp+108h+var_D4], ebx
0x18002848a  mov     rcx, r15; unsigned __int16 *
0x18002848d  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x180028492  mov     r15, rax
0x180028495  test    rax, rax
0x180028498  jz      loc_1800285F3
0x18002849e  lea     r8, [rsp+108h+var_C8]; unsigned __int64 *
0x1800284a3  mov     r11d, 27h ; '''
0x1800284a9  mov     edx, r11d; unsigned __int64
0x1800284ac  mov     rcx, rax; unsigned __int16 *
0x1800284af  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800284b4  test    eax, eax
0x1800284b6  jnz     short loc_1800284E9
0x1800284b8  mov     rax, [rsp+108h+var_C8]
0x1800284bd  inc     rax
0x1800284c0  cmp     r11, rax
0x1800284c3  jnz     short loc_1800284E9
0x1800284c5  lea     rdx, String2; "Identity Device (NIST SP 800-73 [PIV])"
0x1800284cc  mov     rcx, r15; lpString1
0x1800284cf  call    cs:__imp_lstrcmpW
0x1800284d5  test    eax, eax
0x1800284d7  jnz     short loc_1800284E9
0x1800284d9  mov     r12d, 1
0x1800284df  mov     [rsp+108h+var_A4], r12d
0x1800284e4  jmp     loc_1800285E6
0x1800284e9  lea     r8, [rsp+108h+var_C8]; unsigned __int64 *
0x1800284ee  mov     r11d, 2Ch ; ','
0x1800284f4  mov     edx, r11d; unsigned __int64
0x1800284f7  mov     rcx, r15; unsigned __int16 *
0x1800284fa  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800284ff  test    eax, eax
0x180028501  jnz     short loc_180028524
0x180028503  mov     rax, [rsp+108h+var_C8]
0x180028508  inc     rax
0x18002850b  cmp     r11, rax
0x18002850e  jnz     short loc_180028524
0x180028510  lea     rdx, aIdentityDevice; "Identity Device (Microsoft Generic Prof"...
0x180028517  mov     rcx, r15; lpString1
0x18002851a  call    cs:__imp_lstrcmpW
0x180028520  test    eax, eax
0x180028522  jz      short loc_1800284D9
0x180028524  mov     [rsp+108h+var_E0], rdi; struct CBuffer *
0x180028529  mov     qword ptr [rsp+108h+cReaders], rdi; struct CBuffer *
0x18002852e  lea     r9, [rsp+108h+var_50]; struct CBuffer *
0x180028536  lea     r8, [rsp+108h+var_68]; struct CBuffer *
0x18002853e  mov     rdx, r15; unsigned __int16 *
0x180028541  mov     ecx, [rsp+108h+var_80]; unsigned int
0x180028548  call    ?GetCardInfo@@YAHKPEBGPEAVCBuffer@@111@Z; GetCardInfo(ulong,ushort const *,CBuffer *,CBuffer *,CBuffer *,CBuffer *)
0x18002854d  test    eax, eax
0x18002854f  jnz     short loc_18002856A
0x180028551  mov     [rsp+108h+var_A0], 8010000Dh
0x180028559  lea     rdx, _TI1K; pThrowInfo
0x180028560  lea     rcx, [rsp+108h+var_A0]; pExceptionObject
0x180028565  call    _CxxThrowException_0
0x18002856a  mov     ecx, [rsp+108h+var_58]
0x180028571  cmp     ecx, 21h ; '!'
0x180028574  jbe     short loc_18002858F
0x180028576  mov     [rsp+108h+var_9C], 80100004h
0x18002857e  lea     rdx, _TI1K; pThrowInfo
0x180028585  lea     rcx, [rsp+108h+var_9C]; pExceptionObject
0x18002858a  call    _CxxThrowException_0
0x18002858f  mov     eax, ebx
0x180028591  imul    rbx, rax, 4Ch ; 'L'
0x180028595  mov     [rbx+r14], ecx
0x180028599  mov     r8, rcx
0x18002859c  xor     edx, edx; unsigned int
0x18002859e  lea     rcx, [rsp+108h+var_68]; this
0x1800285a6  call    ?Access@CBuffer@@QEBAPEAEK@Z; CBuffer::Access(ulong)
0x1800285ab  mov     rdx, rax; Src
0x1800285ae  lea     rcx, [r14+4]
0x1800285b2  add     rcx, rbx; void *
0x1800285b5  call    memcpy_0
0x1800285ba  mov     r8d, [rbx+r14]
0x1800285be  xor     edx, edx; unsigned int
0x1800285c0  lea     rcx, [rsp+108h+var_50]; this
0x1800285c8  call    ?Access@CBuffer@@QEBAPEAEK@Z; CBuffer::Access(ulong)
0x1800285cd  mov     rdx, rax; Src
0x1800285d0  lea     rcx, [r14+28h]
0x1800285d4  add     rcx, rbx; void *
0x1800285d7  call    memcpy_0
0x1800285dc  mov     ebx, [rsp+108h+var_D4]
0x1800285e0  inc     ebx
0x1800285e2  mov     [rsp+108h+var_D4], ebx
0x1800285e6  mov     rcx, r15; unsigned __int16 *
0x1800285e9  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x1800285ee  jmp     loc_180028492
0x1800285f3  cmp     r12d, 1
0x1800285f7  jnz     short loc_180028623
0x1800285f9  lea     rcx, [rsp+108h+var_D0]
0x1800285fe  mov     qword ptr [rsp+108h+cReaders], rcx; unsigned int *
0x180028603  lea     r9, [rsp+108h+Src]; struct _SCARD_ATRMASK **
0x18002860b  mov     r8d, [rsp+108h+arg_18]; unsigned int
0x180028613  mov     rdx, r13; struct SCARD_READERSTATEW *
0x180028616  mov     rcx, [rsp+108h+hContext]; unsigned __int64
0x18002861e  call    ?LocateCLMDDevicesW@@YAX_KPEAUSCARD_READERSTATEW@@KPEAPEAU_SCARD_ATRMASK@@PEAK@Z; LocateCLMDDevicesW(unsigned __int64,SCARD_READERSTATEW *,ulong,_SCARD_ATRMASK * *,ulong *)
0x180028623  mov     r12d, [rsp+108h+var_D0]
0x180028628  lea     r15d, [rbx+r12]
0x18002862c  test    r15d, r15d
0x18002862f  jz      short loc_18002869E
0x180028631  mov     ecx, r15d
0x180028634  mov     eax, 4Ch ; 'L'
0x180028639  mul     rcx
0x18002863c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180028643  cmovb   rax, rcx
0x180028647  mov     rcx, rax; unsigned __int64
0x18002864a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002864f  mov     rsi, rax
0x180028652  mov     [rsp+108h+var_90], rax
0x180028657  test    rax, rax
0x18002865a  jnz     short loc_180028675
0x18002865c  mov     [rsp+108h+var_98], 80100006h
0x180028664  lea     rdx, _TI1K; pThrowInfo
0x18002866b  lea     rcx, [rsp+108h+var_98]; pExceptionObject
0x180028670  call    _CxxThrowException_0
0x180028675  mov     eax, ebx
0x180028677  imul    rbx, rax, 4Ch ; 'L'
0x18002867b  mov     r8, rbx; Size
0x18002867e  mov     rdx, r14; Src
0x180028681  mov     rcx, rsi; void *
0x180028684  call    memcpy_0
0x180028689  imul    r8, r12, 4Ch ; 'L'; Size
0x18002868d  lea     rcx, [rbx+rsi]; void *
0x180028691  mov     rdx, [rsp+108h+Src]; Src
0x180028699  call    memcpy_0
0x18002869e  test    rsi, rsi
0x1800286a1  jz      short loc_1800286F8
0x1800286a3  mov     ebx, [rsp+108h+arg_18]
0x1800286aa  mov     [rsp+108h+cReaders], ebx; cReaders
0x1800286ae  mov     r9, r13; rgReaderStates
0x1800286b1  mov     r8d, r15d; cAtrs
0x1800286b4  mov     rdx, rsi; rgAtrMasks
0x1800286b7  mov     rcx, [rsp+108h+hContext]; hContext
0x1800286bf  call    SCardLocateCardsByATRW
0x1800286c4  mov     [rsp+108h+var_D8], eax
0x1800286c8  cmp     eax, 78h ; 'x'
0x1800286cb  jnz     short loc_1800286F8
0x1800286cd  mov     rcx, [rsp+108h+var_70]
0x1800286d5  mov     rcx, [rcx+80h]; unsigned __int64
0x1800286dc  test    rcx, rcx
0x1800286df  jz      short loc_1800286F8
0x1800286e1  mov     r9d, ebx; unsigned int
0x1800286e4  mov     r8, r13; struct SCARD_READERSTATEW *
0x1800286e7  mov     rdx, [rsp+108h+arg_8]; unsigned __int16 *
0x1800286ef  call    ?RedirectedSCardLocateCardsW@@YAJ_KPEBGPEAUSCARD_READERSTATEW@@K@Z; RedirectedSCardLocateCardsW(unsigned __int64,ushort const *,SCARD_READERSTATEW *,ulong)
0x1800286f4  mov     [rsp+108h+var_D8], eax
0x1800286f8  lea     rbx, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800286ff  mov     [rsp+108h+var_50], rbx
0x180028707  lea     rcx, [rsp+108h+var_50]; this
0x18002870f  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180028714  nop
0x180028715  mov     [rsp+108h+var_68], rbx
0x18002871d  lea     rcx, [rsp+108h+var_68]; this
0x180028725  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002872a  nop
0x18002872b  jmp     short loc_180028739
0x18002872d  jmp     short $+2
0x18002872f  mov     r14, [rsp+108h+var_C0]
0x180028734  mov     rsi, [rsp+108h+var_90]
0x180028739  test    rsi, rsi
0x18002873c  jz      short loc_18002874E
0x18002873e  mov     rcx, rsi; void *
0x180028741  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028746  nop
0x180028747  jmp     short loc_18002874E
0x180028749  mov     r14, [rsp+108h+var_C0]
0x18002874e  test    r14, r14
0x180028751  jz      short loc_18002875E
0x180028753  mov     rcx, r14; void *
0x180028756  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002875b  nop
0x18002875c  jmp     short $+2
0x18002875e  mov     rcx, [rsp+108h+Src]; void *
0x180028766  test    rcx, rcx
0x180028769  jz      short loc_180028773
0x18002876b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028770  nop
0x180028771  jmp     short $+2
0x180028773  mov     eax, [rsp+108h+var_D8]
0x180028777  add     rsp, 0D0h
0x18002877e  pop     r15
0x180028780  pop     r14
0x180028782  pop     r13
0x180028784  pop     r12
0x180028786  pop     rdi
0x180028787  pop     rsi
0x180028788  pop     rbx
0x180028789  retn
```
