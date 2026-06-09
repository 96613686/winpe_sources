# CWord::Init(void)

- ea: `0x1800b30f8`
- end: `0x1800b3422`
- name: `?Init@CWord@@QEAAJXZ`
- size: `810`
- prototype: `__int64 __fastcall(CWord *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800b26e0`

## callees

- `0x180002470`
- `0x1800034b0`
- `0x1800040b8`
- `0x18000614c`
- `0x1800062a0`
- `0x1800ac894`
- `0x1800b002c`
- `0x1800b30a4`
- `0x1800b30d0`
- `0x1800b30f8`
- `0x1800b3470`
- `0x1800fb844`
- `0x1800ff490`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b33ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b33ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b339c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b339c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b327a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b327a`

## pseudocode

```c
__int64 __fastcall CWord::Init(CWord *this)
{
  const unsigned __int16 *v1; // rdx
  int PronunciationsFromCPPT; // edi
  __int64 v4; // rcx
  SPWORDPRONUNCIATION *pFirstWordPronunciation; // rcx
  unsigned int v6; // eax
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // kr00_8
  void *v9; // rax
  size_t v10; // r8
  SPWORDPRONUNCIATION *v11; // r15
  unsigned int v12; // r13d
  DICTREC *v13; // rax
  DICTREC *v14; // rsi
  _QWORD *v15; // rax
  _QWORD *v16; // rdx
  unsigned int v17; // edx
  CPronunciation *v18; // rcx
  signed int LastError; // eax
  struct SPWORDPRONUNCIATIONLIST pv; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v22; // [rsp+58h] [rbp-A8h]
  CHAR MultiByteStr[384]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v24[3080]; // [rsp+1E0h] [rbp+E0h] BYREF

  v1 = (const unsigned __int16 *)*((_QWORD *)this + 1);
  if ( v1 )
  {
    v4 = *((_QWORD *)this + 3);
    memset(&pv, 0, sizeof(pv));
    PronunciationsFromCPPT = CEngine::GetPronunciationsFromCPPT(*(CEngine **)(v4 + 24), v1, &pv);
    if ( PronunciationsFromCPPT < 0 )
      PronunciationsFromCPPT = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct SPWORDPRONUNCIATIONLIST *, int))(**(_QWORD **)(*((_QWORD *)this + 3) + 56LL) + 64LL))(
                                 *(_QWORD *)(*((_QWORD *)this + 3) + 56LL),
                                 *((_QWORD *)this + 1),
                                 *(unsigned int *)(*((_QWORD *)this + 3) + 52LL),
                                 &pv,
                                 1);
    if ( PronunciationsFromCPPT < 0 )
    {
      *((_DWORD *)this + 4) = -1;
      return (unsigned int)PronunciationsFromCPPT;
    }
    pFirstWordPronunciation = pv.pFirstWordPronunciation;
    v6 = 0;
    *((_DWORD *)this + 4) = 0;
    while ( pFirstWordPronunciation )
    {
      pFirstWordPronunciation = pFirstWordPronunciation->pNextWordPronunciation;
      ++v6;
    }
    *((_DWORD *)this + 5) = v6;
    if ( !v6 )
    {
      TraceTag(
        (struct CDebugTag *)&g_tagWord,
        L"Number of pronunciation for this word (%s) is zero",
        *((_QWORD *)this + 1));
      return (unsigned int)-2147467259;
    }
    v8 = v6;
    v7 = 8LL * v6;
    if ( !is_mul_ok(v8, 8u) )
      v7 = -1;
    v9 = CWinHeap::Alloc((CWinHeap *)&g_heap, v7, 0);
    v10 = 8LL * *((unsigned int *)this + 5);
    *(_QWORD *)this = v9;
    memset_0(v9, 0, v10);
    v11 = pv.pFirstWordPronunciation;
    v12 = 0;
    while ( 1 )
    {
      if ( !v11 )
      {
        CoTaskMemFree(pv.pvBuffer);
        return (unsigned int)PronunciationsFromCPPT;
      }
      v13 = (DICTREC *)CAllocOnSpecificHeapBase::operator_new(0x38u, (struct CHeap *)&g_heap, 1);
      v14 = v13;
      if ( v13 )
        *((_BYTE *)v13 + 48) = 1;
      else
        v14 = 0;
      if ( WideCharToMultiByte(0, 0x400u, *((LPCWCH *)this + 1), -1, MultiByteStr, 384, 0, 0) )
      {
        PronunciationsFromCPPT = (*(__int64 (__fastcall **)(_QWORD, _QWORD, SPPHONEID *, unsigned __int16 *))(**(_QWORD **)(*((_QWORD *)this + 3) + 56LL) + 160LL))(
                                   *(_QWORD *)(*((_QWORD *)this + 3) + 56LL),
                                   (unsigned int)v11->eLexiconType,
                                   v11->szPronunciation,
                                   v24);
        if ( PronunciationsFromCPPT < 0 )
          goto LABEL_35;
        PronunciationsFromCPPT = DICTREC::Init(v14, MultiByteStr, v24);
        if ( PronunciationsFromCPPT < 0 )
          goto LABEL_35;
        *((_BYTE *)v14 + 33) &= 1u;
        *((_BYTE *)v14 + 33) |= 2u;
        CCrossWord::GenSSIDs(*(CCrossWord **)(*((_QWORD *)this + 3) + 32LL), v14, 0);
        v15 = CWinHeap::Alloc((CWinHeap *)&g_heap, 0x28u, 0);
        v22 = v15;
        v16 = v15;
        if ( v15 )
        {
          v15[3] = *((_QWORD *)this + 3);
          *v15 = 0;
          v15[1] = 0;
          *((_DWORD *)v15 + 4) = 0;
          *((_DWORD *)v15 + 8) = 0;
        }
        else
        {
          v16 = 0;
        }
        *(_QWORD *)(*(_QWORD *)this + 8LL * v12) = v16;
        PronunciationsFromCPPT = CPronunciation::Init(*(CPronunciation **)(*(_QWORD *)this + 8LL * v12), v14);
        if ( PronunciationsFromCPPT < 0 )
        {
          v18 = *(CPronunciation **)(*(_QWORD *)this + 8LL * v12);
          if ( v18 )
            CPronunciation::`scalar deleting destructor'(v18, v17);
LABEL_35:
          TraceTag((struct CDebugTag *)&g_tagWord, L"Wrong pronunciation for: %s", *((_QWORD *)this + 1));
          --*((_DWORD *)this + 5);
          goto LABEL_36;
        }
        if ( (v11->eLexiconType & 0x2000) != 0 )
        {
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL * v12) + 32LL) = 1;
        }
        else if ( (v11->eLexiconType & 0x1000) != 0 )
        {
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL * v12) + 32LL) = 0;
        }
        ++v12;
      }
      else
      {
        LastError = GetLastError();
        PronunciationsFromCPPT = LastError;
        if ( LastError > 0 )
          PronunciationsFromCPPT = (unsigned __int16)LastError | 0x80070000;
        if ( PronunciationsFromCPPT < 0 )
          goto LABEL_35;
      }
LABEL_36:
      if ( v14 )
        DICTREC::`scalar deleting destructor'(v14, v17);
      MultiByteStr[0] = 0;
      v11 = v11->pNextWordPronunciation;
    }
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x1800b30f8  push    rbp
0x1800b30fa  push    rbx
0x1800b30fb  push    rsi
0x1800b30fc  push    rdi
0x1800b30fd  push    r12
0x1800b30ff  push    r13
0x1800b3101  push    r14
0x1800b3103  push    r15
0x1800b3105  lea     rbp, [rsp-1908h]
0x1800b310d  mov     eax, 1A08h
0x1800b3112  call    _alloca_probe
0x1800b3117  sub     rsp, rax
0x1800b311a  mov     rax, cs:__security_cookie
0x1800b3121  xor     rax, rsp
0x1800b3124  mov     [rbp+1940h+var_50], rax
0x1800b312b  mov     rdx, [rcx+8]; unsigned __int16 *
0x1800b312f  xor     r14d, r14d
0x1800b3132  mov     rbx, rcx
0x1800b3135  test    rdx, rdx
0x1800b3138  jnz     short loc_1800B3144
0x1800b313a  mov     edi, 8007000Eh
0x1800b313f  jmp     loc_1800B33FD
0x1800b3144  mov     rcx, [rcx+18h]
0x1800b3148  lea     r8, [rsp+1A40h+pv]; struct SPWORDPRONUNCIATIONLIST *
0x1800b314d  xorps   xmm0, xmm0
0x1800b3150  xor     eax, eax
0x1800b3152  movups  xmmword ptr [rsp+1A40h+pv], xmm0
0x1800b3157  mov     [rsp+1A40h+var_19F0], rax
0x1800b315c  mov     rcx, [rcx+18h]; this
0x1800b3160  call    ?GetPronunciationsFromCPPT@CEngine@@QEAAJPEBGPEAUSPWORDPRONUNCIATIONLIST@@@Z; CEngine::GetPronunciationsFromCPPT(ushort const *,SPWORDPRONUNCIATIONLIST *)
0x1800b3165  mov     edi, eax
0x1800b3167  test    eax, eax
0x1800b3169  jns     short loc_1800B3196
0x1800b316b  mov     r8, [rbx+18h]
0x1800b316f  lea     r9, [rsp+1A40h+pv]
0x1800b3174  mov     rdx, [rbx+8]
0x1800b3178  mov     dword ptr [rsp+1A40h+lpMultiByteStr], 1
0x1800b3180  mov     rcx, [r8+38h]
0x1800b3184  mov     r8d, [r8+34h]
0x1800b3188  mov     rax, [rcx]
0x1800b318b  mov     rax, [rax+40h]
0x1800b318f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3194  mov     edi, eax
0x1800b3196  test    edi, edi
0x1800b3198  js      loc_1800B33F6
0x1800b319e  mov     rcx, [rsp+1A40h+var_19F0]
0x1800b31a3  mov     eax, r14d
0x1800b31a6  mov     [rbx+10h], r14d
0x1800b31aa  jmp     short loc_1800B31B1
0x1800b31ac  mov     rcx, [rcx]
0x1800b31af  inc     eax
0x1800b31b1  test    rcx, rcx
0x1800b31b4  jnz     short loc_1800B31AC
0x1800b31b6  mov     [rbx+14h], eax
0x1800b31b9  test    eax, eax
0x1800b31bb  jnz     short loc_1800B31DE
0x1800b31bd  mov     r8, [rbx+8]
0x1800b31c1  lea     rdx, aNumberOfPronun; "Number of pronunciation for this word ("...
0x1800b31c8  lea     rcx, ?g_tagWord@@3VCDebugTag@@A; struct CDebugTag *
0x1800b31cf  call    ?TraceTag@@YAXPEAVCDebugTag@@PEBGZZ; TraceTag(CDebugTag *,ushort const *,...)
0x1800b31d4  mov     edi, 80004005h
0x1800b31d9  jmp     loc_1800B33FD
0x1800b31de  mov     ecx, eax
0x1800b31e0  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800b31e7  mov     eax, 8
0x1800b31ec  mul     rcx
0x1800b31ef  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800b31f6  cmovb   rax, r12
0x1800b31fa  xor     r8d, r8d; bool
0x1800b31fd  mov     rdx, rax; unsigned __int64
0x1800b3200  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800b3205  mov     r8d, [rbx+14h]
0x1800b3209  xor     edx, edx; Val
0x1800b320b  shl     r8, 3; Size
0x1800b320f  mov     rcx, rax; void *
0x1800b3212  mov     [rbx], rax
0x1800b3215  call    memset_0
0x1800b321a  mov     r15, [rsp+1A40h+var_19F0]
0x1800b321f  mov     r13d, r14d
0x1800b3222  test    r15, r15
0x1800b3225  jz      loc_1800B33E9
0x1800b322b  mov     r8b, 1; bool
0x1800b322e  lea     rdx, ?g_heap@@3VCHeap@@A; struct CHeap *
0x1800b3235  mov     ecx, 38h ; '8'; unsigned __int64
0x1800b323a  call    ?operator_new@CAllocOnSpecificHeapBase@@SAPEAX_KPEAVCHeap@@_N@Z; CAllocOnSpecificHeapBase::operator_new(unsigned __int64,CHeap *,bool)
0x1800b323f  mov     rsi, rax
0x1800b3242  test    rax, rax
0x1800b3245  jz      short loc_1800B324D
0x1800b3247  mov     byte ptr [rax+30h], 1
0x1800b324b  jmp     short loc_1800B3250
0x1800b324d  mov     rsi, r14
0x1800b3250  mov     r8, [rbx+8]; lpWideCharStr
0x1800b3254  lea     rax, [rsp+1A40h+MultiByteStr]
0x1800b3259  mov     [rsp+1A40h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x1800b325e  mov     r9d, r12d; cchWideChar
0x1800b3261  mov     [rsp+1A40h+lpDefaultChar], r14; lpDefaultChar
0x1800b3266  mov     edx, 400h; dwFlags
0x1800b326b  mov     [rsp+1A40h+cbMultiByte], 180h; cbMultiByte
0x1800b3273  xor     ecx, ecx; CodePage
0x1800b3275  mov     [rsp+1A40h+lpMultiByteStr], rax; lpMultiByteStr
0x1800b327a  call    cs:__imp_WideCharToMultiByte
0x1800b3280  test    eax, eax
0x1800b3282  jz      loc_1800B339C
0x1800b3288  mov     rax, [rbx+18h]
0x1800b328c  lea     r8, [r15+14h]
0x1800b3290  mov     edx, [r15+8]
0x1800b3294  lea     r9, [rbp+1940h+var_1860]
0x1800b329b  mov     rcx, [rax+38h]
0x1800b329f  mov     rax, [rcx]
0x1800b32a2  mov     rax, [rax+0A0h]
0x1800b32a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b32ae  mov     edi, eax
0x1800b32b0  test    eax, eax
0x1800b32b2  js      loc_1800B33B5
0x1800b32b8  lea     r8, [rbp+1940h+var_1860]; unsigned __int16 *
0x1800b32bf  mov     rcx, rsi; this
0x1800b32c2  lea     rdx, [rsp+1A40h+MultiByteStr]; char *
0x1800b32c7  call    ?Init@DICTREC@@QEAAJPEBDPEBG@Z; DICTREC::Init(char const *,ushort const *)
0x1800b32cc  mov     edi, eax
0x1800b32ce  test    eax, eax
0x1800b32d0  js      loc_1800B33B5
0x1800b32d6  and     byte ptr [rsi+21h], 1
0x1800b32da  xor     r8d, r8d; bool
0x1800b32dd  or      byte ptr [rsi+21h], 2
0x1800b32e1  mov     rdx, rsi; struct DICTREC *
0x1800b32e4  mov     rcx, [rbx+18h]
0x1800b32e8  mov     rcx, [rcx+20h]; this
0x1800b32ec  call    ?GenSSIDs@CCrossWord@@QEBA_NPEAVDICTREC@@_N@Z; CCrossWord::GenSSIDs(DICTREC *,bool)
0x1800b32f1  xor     r8d, r8d; bool
0x1800b32f4  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800b32fb  lea     edx, [r8+28h]; unsigned __int64
0x1800b32ff  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800b3304  mov     [rsp+1A40h+var_19E8], rax
0x1800b3309  mov     rdx, rax
0x1800b330c  test    rax, rax
0x1800b330f  jz      short loc_1800B332A
0x1800b3311  mov     rcx, [rbx+18h]
0x1800b3315  mov     [rax+18h], rcx
0x1800b3319  mov     [rax], r14
0x1800b331c  mov     [rax+8], r14
0x1800b3320  mov     [rax+10h], r14d
0x1800b3324  mov     [rax+20h], r14d
0x1800b3328  jmp     short loc_1800B332D
0x1800b332a  mov     rdx, r14
0x1800b332d  mov     rax, [rbx]
0x1800b3330  mov     r14d, r13d
0x1800b3333  mov     [rax+r14*8], rdx
0x1800b3337  mov     rdx, rsi; struct DICTREC *
0x1800b333a  mov     rcx, [rbx]
0x1800b333d  mov     rcx, [rcx+r14*8]; this
0x1800b3341  call    ?Init@CPronunciation@@QEAAJPEAVDICTREC@@@Z; CPronunciation::Init(DICTREC *)
0x1800b3346  mov     edi, eax
0x1800b3348  test    eax, eax
0x1800b334a  js      short loc_1800B3386
0x1800b334c  test    dword ptr [r15+8], 2000h
0x1800b3354  jz      short loc_1800B3366
0x1800b3356  mov     rax, [rbx]
0x1800b3359  mov     rcx, [rax+r14*8]
0x1800b335d  mov     dword ptr [rcx+20h], 1
0x1800b3364  jmp     short loc_1800B337E
0x1800b3366  test    dword ptr [r15+8], 1000h
0x1800b336e  jz      short loc_1800B337E
0x1800b3370  mov     rax, [rbx]
0x1800b3373  mov     rcx, [rax+r14*8]
0x1800b3377  mov     dword ptr [rcx+20h], 0
0x1800b337e  inc     r13d
0x1800b3381  xor     r14d, r14d
0x1800b3384  jmp     short loc_1800B33CF
0x1800b3386  mov     rax, [rbx]
0x1800b3389  mov     rcx, [rax+r14*8]; this
0x1800b338d  xor     r14d, r14d
0x1800b3390  test    rcx, rcx
0x1800b3393  jz      short loc_1800B33B5
0x1800b3395  call    ??_GCPronunciation@@QEAAPEAXI@Z; CPronunciation::`scalar deleting destructor'(uint)
0x1800b339a  jmp     short loc_1800B33B5
0x1800b339c  call    cs:__imp_GetLastError
0x1800b33a2  mov     edi, eax
0x1800b33a4  test    eax, eax
0x1800b33a6  jle     short loc_1800B33B1
0x1800b33a8  movzx   edi, ax
0x1800b33ab  or      edi, 80070000h
0x1800b33b1  test    edi, edi
0x1800b33b3  jns     short loc_1800B33CF
0x1800b33b5  mov     r8, [rbx+8]
0x1800b33b9  lea     rdx, aWrongPronuncia; "Wrong pronunciation for: %s"
0x1800b33c0  lea     rcx, ?g_tagWord@@3VCDebugTag@@A; struct CDebugTag *
0x1800b33c7  call    ?TraceTag@@YAXPEAVCDebugTag@@PEBGZZ; TraceTag(CDebugTag *,ushort const *,...)
0x1800b33cc  dec     dword ptr [rbx+14h]
0x1800b33cf  test    rsi, rsi
0x1800b33d2  jz      short loc_1800B33DC
0x1800b33d4  mov     rcx, rsi; this
0x1800b33d7  call    ??_GDICTREC@@QEAAPEAXI@Z; DICTREC::`scalar deleting destructor'(uint)
0x1800b33dc  mov     [rsp+1A40h+MultiByteStr], r14b
0x1800b33e1  mov     r15, [r15]
0x1800b33e4  jmp     loc_1800B3222
0x1800b33e9  mov     rcx, [rsp+1A40h+pv+8]; pv
0x1800b33ee  call    cs:__imp_CoTaskMemFree
0x1800b33f4  jmp     short loc_1800B33FD
0x1800b33f6  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x1800b33fd  mov     eax, edi
0x1800b33ff  mov     rcx, [rbp+1940h+var_50]
0x1800b3406  xor     rcx, rsp; StackCookie
0x1800b3409  call    __security_check_cookie
0x1800b340e  add     rsp, 1A08h
0x1800b3415  pop     r15
0x1800b3417  pop     r14
0x1800b3419  pop     r13
0x1800b341b  pop     r12
0x1800b341d  pop     rdi
0x1800b341e  pop     rsi
0x1800b341f  pop     rbx
0x1800b3420  pop     rbp
0x1800b3421  retn
```
