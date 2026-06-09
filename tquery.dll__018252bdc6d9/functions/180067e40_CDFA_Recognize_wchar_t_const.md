# CDFA::Recognize(wchar_t const *)

- ea: `0x180067e40`
- end: `0x1800681b0`
- name: `?Recognize@CDFA@@QEAAEPEB_W@Z`
- size: `880`
- prototype: `unsigned __int8 __fastcall(CDFA *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops`

## callers

- `0x180115b80`

## callees

- `0x180067d88`
- `0x180067e40`
- `0x180068a74`
- `0x180068af4`
- `0x180068b14`
- `0x1800699a0`
- `0x180072768`
- `0x1800eb364`
- `0x1801590bc`
- `0x180188d90`
- `0x180189280`
- `0x18028d6f0`
- `0x18028d838`
- `0x18028db08`
- `0x18028ddb8`
- `0x18028dec8`
- `0x18028eec8`
- `0x18028efe8`
- `0x18028f190`
- `0x18028f1f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180067fa0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068011`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068026`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006806e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800680d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068117`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180067fa0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068011`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068026`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006806e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800680d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068117`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067fc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006803f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068094`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006809e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800680ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068109`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067fc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006803f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068094`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006809e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800680ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068109`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006801a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006801a`

## string_xrefs

- `0x180067ee8`: `[Regex] DFA move[ %u, %u ] = %u\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall CDFA::Recognize(CDFA *this, const wchar_t *a2)
{
  __int64 v3; // r12
  char v4; // r13
  unsigned __int16 v5; // di
  char *v6; // rbx
  unsigned int v7; // r14d
  volatile signed __int32 *v8; // rsi
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  unsigned int v10; // ebx
  int v12; // r14d
  CEventSem *v13; // rsi
  unsigned int v14; // esi
  unsigned int v15; // eax
  CNFAState *v16; // rax
  unsigned int v17; // esi
  unsigned int v18; // eax
  unsigned __int8 IsFinal; // al
  __int64 v20; // [rsp+20h] [rbp-E0h]
  __int64 v21; // [rsp+28h] [rbp-D8h]
  unsigned int v22; // [rsp+30h] [rbp-D0h]
  __int16 v23; // [rsp+34h] [rbp-CCh]
  _BYTE v25[48]; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+80h] [rbp-80h]
  unsigned int v27[12]; // [rsp+90h] [rbp-70h] BYREF
  void *v28; // [rsp+C0h] [rbp-40h]
  unsigned int v29[12]; // [rsp+D0h] [rbp-30h] BYREF
  void *v30; // [rsp+100h] [rbp+0h]

  v3 = *((unsigned int *)this + 24);
  v4 = *(_BYTE *)(v3 + *((_QWORD *)this + 15));
  v5 = 2;
  v23 = 2;
  while ( !v4 )
  {
    v6 = (char *)this + 136;
    CSyncReadWrite::GetReadAccess((CDFA *)((char *)this + 136));
    v22 = v5;
    v7 = *(_DWORD *)(*((_QWORD *)this + 13) + 4LL * ((_DWORD)v3 * (*((_DWORD *)this + 8) + 7) + (unsigned int)v5));
    v8 = (volatile signed __int32 *)((char *)this + 144);
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 200);
    if ( *((_DWORD *)this + 34) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
      _InterlockedDecrement(v8);
    }
    else
    {
      _InterlockedDecrement(v8);
      if ( !*(_DWORD *)v6 )
        goto LABEL_5;
      EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
    }
    if ( !*v8 )
    {
      CSyncReadWrite::LokInitWriteEvent((CDFA *)((char *)this + 136));
      CEventSem::Set((CDFA *)((char *)this + 256));
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 5);
LABEL_5:
    LODWORD(v21) = v7;
    LODWORD(v20) = v22;
    SearchIndexerDebug::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\xpr\\fa.cxx",
      (const wchar_t *)0x435,
      (unsigned int)L"[Regex] DFA move[ %u, %u ] = %u\n",
      (const wchar_t *)(unsigned int)v3,
      v20,
      v21);
    if ( v7 != -1 )
      goto LABEL_6;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    _InterlockedIncrement((volatile signed __int32 *)v6);
    *((_DWORD *)this + 35) = GetCurrentThreadId();
    EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
    if ( *v8 )
    {
      CSyncReadWrite::LokInitWriteEvent((CDFA *)((char *)this + 136));
      v13 = (CDFA *)((char *)this + 256);
      CEventSem::Reset((CDFA *)((char *)this + 256));
      v12 = 1;
    }
    else
    {
      v12 = 0;
      v13 = (CDFA *)((char *)this + 256);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 5);
    if ( v12 )
      CEventSem::Wait(v13, 0xFFFFFFFF, 0);
    if ( *(_DWORD *)(*((_QWORD *)this + 13) + 4LL * (v22 + (_DWORD)v3 * (*((_DWORD *)this + 8) + 7))) == -1 )
    {
      CStateSet::CStateSet((CStateSet *)v29);
      CStateSet::CStateSet((CStateSet *)v27);
      CStateSet::CStateSet((CStateSet *)v25);
      CXlatState::XlatToMany((CDFA *)((char *)this + 72), v3, (struct CStateSet *)v29);
      v14 = v29[0];
      if ( v29[0] )
      {
        do
        {
          v15 = CStateSet::State((CStateSet *)v29, v14);
          v16 = CNFA::Get((CDFA *)((char *)this + 16), v15);
          CNFAState::Move(v16, (struct CStateSet *)v27, v22);
          --v14;
        }
        while ( v14 );
        v6 = (char *)this + 136;
      }
      v17 = v27[0];
      if ( v27[0] )
      {
        do
        {
          v18 = CStateSet::State((CStateSet *)v27, v17);
          CNFA::EpsClosure((CDFA *)((char *)this + 16), v18, (struct CStateSet *)v25);
          --v17;
        }
        while ( v17 );
        v6 = (char *)this + 136;
        v7 = CXlatState::XlatToOne((CDFA *)((char *)this + 72), (const struct CStateSet *)v25);
        if ( v7 > *((_DWORD *)this + 25)
          || *(_DWORD *)(*((_QWORD *)this + 13) + 4LL * v7 * (*((_DWORD *)this + 8) + 7)) == -2 )
        {
          IsFinal = CNFA::IsFinal((CDFA *)((char *)this + 16), (struct CStateSet *)v25);
          CDFA::Add(this, v7, IsFinal);
        }
        *(_DWORD *)(*((_QWORD *)this + 13) + 4LL * (v22 + (_DWORD)v3 * (*((_DWORD *)this + 8) + 7))) = v7;
        LODWORD(v21) = v7;
        LODWORD(v20) = v22;
        SearchIndexerDebug::Verbose(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\xpr\\fa.cxx",
          (const wchar_t *)0x47B,
          (unsigned int)L"[Regex] Adding transition from %u on %u to %u\n",
          (const wchar_t *)(unsigned int)v3,
          v20,
          v21);
      }
      else
      {
        v7 = -2;
        *(_DWORD *)(*((_QWORD *)this + 13) + 4LL * (v22 + (_DWORD)v3 * (*((_DWORD *)this + 8) + 7))) = -2;
        LODWORD(v20) = v22;
        SearchIndexerDebug::Verbose(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\xpr\\fa.cxx",
          (const wchar_t *)0x45E,
          (unsigned int)L"[Regex] Undefined transition from %u on %u\n",
          (const wchar_t *)(unsigned int)v3,
          v20);
      }
      operator delete(Block);
      operator delete(v28);
      operator delete(v30);
      EnterCriticalSection(v9);
      if ( *(_DWORD *)v6 == 1 )
        *((_DWORD *)v6 + 1) = 0;
      _InterlockedDecrement((volatile signed __int32 *)v6);
      CSyncReadWrite::LokInitReadEvent((CSyncReadWrite *)v6);
      CEventSem::Set((CEventSem *)(v6 + 112));
      LeaveCriticalSection(v9);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 16));
LABEL_6:
      if ( v7 == -2 )
        return 0;
      v4 = *(_BYTE *)(v7 + *((_QWORD *)this + 15));
      v5 = v23;
      if ( v23 == 3 )
      {
        if ( (_DWORD)v3 == v7 )
          return v4;
      }
      else
      {
        v10 = *a2++;
        if ( (_WORD)v10 )
        {
          SearchIndexerDebug::Verbose(
            (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\xpr\\fa.cxx",
            (const wchar_t *)0x4B2,
            (unsigned int)L"[Regex] \"%c\" --> ",
            (const wchar_t *)v10);
          v5 = CXlatChar::Translate((CDFA *)((char *)this + 24), v10);
          v23 = v5;
          SearchIndexerDebug::Verbose(
            (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\xpr\\fa.cxx",
            (const wchar_t *)0x4BE,
            (unsigned int)L"%u\n",
            (const wchar_t *)v5);
        }
        else
        {
          v5 = 3;
          v23 = 3;
        }
      }
      LODWORD(v3) = v7;
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
      if ( *(_DWORD *)v6 == 1 )
        *((_DWORD *)this + 35) = 0;
      _InterlockedDecrement((volatile signed __int32 *)v6);
      CSyncReadWrite::LokInitReadEvent((CDFA *)((char *)this + 136));
      CEventSem::Set((CDFA *)((char *)this + 248));
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 5);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
      v5 = v23;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180067e40  mov     [rsp-8+arg_10], rbx
0x180067e45  push    rbp
0x180067e46  push    rsi
0x180067e47  push    rdi
0x180067e48  push    r12
0x180067e4a  push    r13
0x180067e4c  push    r14
0x180067e4e  push    r15
0x180067e50  lea     rbp, [rsp-20h]
0x180067e55  sub     rsp, 120h
0x180067e5c  mov     rax, cs:__security_cookie
0x180067e63  xor     rax, rsp
0x180067e66  mov     [rbp+50h+var_40], rax
0x180067e6a  mov     [rsp+150h+var_118], rdx
0x180067e6f  mov     r15, rcx
0x180067e72  mov     r12d, [rcx+60h]
0x180067e76  mov     rax, [rcx+78h]
0x180067e7a  mov     r13b, [r12+rax]
0x180067e7e  mov     edi, 2
0x180067e83  mov     [rsp+150h+var_11C], edi
0x180067e87  test    r13b, r13b
0x180067e8a  jnz     loc_180068003
0x180067e90  lea     rbx, [r15+88h]
0x180067e97  mov     rcx, rbx; this
0x180067e9a  call    ?GetReadAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetReadAccess(void)
0x180067e9f  movzx   ecx, di
0x180067ea2  mov     [rsp+150h+var_120], ecx
0x180067ea6  mov     eax, [r15+20h]
0x180067eaa  add     eax, 7
0x180067ead  imul    eax, r12d
0x180067eb1  add     ecx, eax
0x180067eb3  mov     rax, [r15+68h]
0x180067eb7  mov     r14d, [rax+rcx*4]
0x180067ebb  lea     rsi, [rbx+8]
0x180067ebf  lea     rdi, [rbx+40h]
0x180067ec3  cmp     dword ptr [rbx], 0
0x180067ec6  jnz     loc_180067F9D
0x180067ecc  lock dec dword ptr [rsi]
0x180067ecf  cmp     dword ptr [rbx], 0
0x180067ed2  jnz     loc_180068114
0x180067ed8  mov     dword ptr [rsp+150h+var_128], r14d
0x180067edd  mov     eax, [rsp+150h+var_120]
0x180067ee1  mov     dword ptr [rsp+150h+var_130], eax
0x180067ee5  mov     r9d, r12d; wchar_t *
0x180067ee8  lea     r8, aRegexDfaMoveUU; "[Regex] DFA move[ %u, %u ] = %u\n"
0x180067eef  mov     edx, 435h; wchar_t *
0x180067ef4  lea     rcx, aOnecoreuapBase_155; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180067efb  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180067f00  cmp     r14d, 0FFFFFFFFh
0x180067f04  jz      loc_180068008
0x180067f0a  cmp     r14d, 0FFFFFFFEh
0x180067f0e  jz      loc_180067FD5
0x180067f14  mov     ecx, r14d
0x180067f17  mov     rax, [r15+78h]
0x180067f1b  mov     r13b, [rcx+rax]
0x180067f1f  mov     edi, [rsp+150h+var_11C]
0x180067f23  mov     ecx, 3
0x180067f28  cmp     di, cx
0x180067f2b  jz      loc_180067FFE
0x180067f31  mov     rdx, [rsp+150h+var_118]
0x180067f36  movzx   ebx, word ptr [rdx]
0x180067f39  add     rdx, 2
0x180067f3d  mov     [rsp+150h+var_118], rdx
0x180067f42  test    bx, bx
0x180067f45  jz      loc_180067FCD
0x180067f4b  mov     r9d, ebx; wchar_t *
0x180067f4e  lea     r8, aRegexC; "[Regex] \"%c\" --> "
0x180067f55  mov     edx, 4B2h; wchar_t *
0x180067f5a  lea     rcx, aOnecoreuapBase_155; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180067f61  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180067f66  lea     rcx, [r15+18h]; this
0x180067f6a  movzx   edx, bx; wchar_t
0x180067f6d  call    ?Translate@CXlatChar@@QEBAI_W@Z; CXlatChar::Translate(wchar_t)
0x180067f72  movzx   edi, ax
0x180067f75  mov     [rsp+150h+var_11C], edi
0x180067f79  movzx   r9d, ax; wchar_t *
0x180067f7d  lea     r8, aU_1; "%u\n"
0x180067f84  mov     edx, 4BEh; wchar_t *
0x180067f89  lea     rcx, aOnecoreuapBase_155; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180067f90  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180067f95  mov     r12d, r14d
0x180067f98  jmp     loc_180067E87
0x180067f9d  mov     rcx, rdi; lpCriticalSection
0x180067fa0  call    cs:__imp_EnterCriticalSection
0x180067fa6  lock dec dword ptr [rsi]
0x180067fa9  cmp     dword ptr [rsi], 0
0x180067fac  jnz     short loc_180067FBF
0x180067fae  mov     rcx, rbx; this
0x180067fb1  call    ?LokInitWriteEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitWriteEvent(void)
0x180067fb6  lea     rcx, [rbx+78h]; this
0x180067fba  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x180067fbf  mov     rcx, rdi; lpCriticalSection
0x180067fc2  call    cs:__imp_LeaveCriticalSection
0x180067fc8  jmp     loc_180067ED8
0x180067fcd  mov     edi, ecx
0x180067fcf  mov     [rsp+150h+var_11C], ecx
0x180067fd3  jmp     short loc_180067F95
0x180067fd5  xor     al, al
0x180067fd7  mov     rcx, [rbp+50h+var_40]
0x180067fdb  xor     rcx, rsp; StackCookie
0x180067fde  call    __security_check_cookie
0x180067fe3  mov     rbx, [rsp+150h+arg_10]
0x180067feb  add     rsp, 120h
0x180067ff2  pop     r15
0x180067ff4  pop     r14
0x180067ff6  pop     r13
0x180067ff8  pop     r12
0x180067ffa  pop     rdi
0x180067ffb  pop     rsi
0x180067ffc  pop     rbp
0x180067ffd  retn
0x180067ffe  cmp     r12d, r14d
0x180068001  jnz     short loc_180067F95
0x180068003  mov     al, r13b
0x180068006  jmp     short loc_180067FD7
0x180068008  mov     [rsp+150h+var_110], rbx
0x18006800d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180068011  call    cs:__imp_EnterCriticalSection
0x180068017  lock inc dword ptr [rbx]
0x18006801a  call    cs:__imp_GetCurrentThreadId
0x180068020  mov     [rbx+4], eax
0x180068023  mov     rcx, rdi; lpCriticalSection
0x180068026  call    cs:__imp_EnterCriticalSection
0x18006802c  cmp     dword ptr [rsi], 0
0x18006802f  jnz     loc_180068122
0x180068035  xor     r14d, r14d
0x180068038  lea     rsi, [rbx+78h]
0x18006803c  mov     rcx, rdi; lpCriticalSection
0x18006803f  call    cs:__imp_LeaveCriticalSection
0x180068045  test    r14d, r14d
0x180068048  jnz     loc_180068141
0x18006804e  mov     ecx, [r15+20h]
0x180068052  add     ecx, 7
0x180068055  imul    ecx, r12d
0x180068059  add     ecx, [rsp+150h+var_120]
0x18006805d  mov     rax, [r15+68h]
0x180068061  cmp     dword ptr [rax+rcx*4], 0FFFFFFFFh
0x180068065  jz      loc_180068160
0x18006806b  mov     rcx, rdi; lpCriticalSection
0x18006806e  call    cs:__imp_EnterCriticalSection
0x180068074  cmp     dword ptr [rbx], 1
0x180068077  jz      loc_180068154
0x18006807d  lock dec dword ptr [rbx]
0x180068080  mov     rcx, rbx; this
0x180068083  call    ?LokInitReadEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitReadEvent(void)
0x180068088  lea     rcx, [rbx+70h]; this
0x18006808c  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x180068091  mov     rcx, rdi; lpCriticalSection
0x180068094  call    cs:__imp_LeaveCriticalSection
0x18006809a  lea     rcx, [rbx+10h]; lpCriticalSection
0x18006809e  call    cs:__imp_LeaveCriticalSection
0x1800680a4  mov     edi, [rsp+150h+var_11C]
0x1800680a8  jmp     loc_180067E87
0x1800680ad  mov     esi, 4
0x1800680b2  mov     edx, esi
0x1800680b4  mov     rcx, [rbp+50h+Block]; Block
0x1800680b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800680bd  nop
0x1800680be  mov     edx, esi
0x1800680c0  mov     rcx, [rbp+50h+var_90]; Block
0x1800680c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800680c9  nop
0x1800680ca  mov     edx, esi
0x1800680cc  mov     rcx, [rbp+50h+var_50]; Block
0x1800680d0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800680d5  nop
0x1800680d6  mov     rcx, rdi; lpCriticalSection
0x1800680d9  call    cs:__imp_EnterCriticalSection
0x1800680df  cmp     dword ptr [rbx], 1
0x1800680e2  jz      loc_1800681A4
0x1800680e8  lock dec dword ptr [rbx]
0x1800680eb  mov     rcx, rbx; this
0x1800680ee  call    ?LokInitReadEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitReadEvent(void)
0x1800680f3  lea     rcx, [rbx+70h]; this
0x1800680f7  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x1800680fc  mov     rcx, rdi; lpCriticalSection
0x1800680ff  call    cs:__imp_LeaveCriticalSection
0x180068105  lea     rcx, [rbx+10h]; lpCriticalSection
0x180068109  call    cs:__imp_LeaveCriticalSection
0x18006810f  jmp     loc_180067F0A
0x180068114  mov     rcx, rdi; lpCriticalSection
0x180068117  call    cs:__imp_EnterCriticalSection
0x18006811d  jmp     loc_180067FA9
0x180068122  mov     rcx, rbx; this
0x180068125  call    ?LokInitWriteEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitWriteEvent(void)
0x18006812a  lea     rsi, [rbx+78h]
0x18006812e  mov     rcx, rsi; this
0x180068131  call    ?Reset@CEventSem@@QEAAXXZ; CEventSem::Reset(void)
0x180068136  mov     r14d, 1
0x18006813c  jmp     loc_18006803C
0x180068141  xor     r8d, r8d; int
0x180068144  or      edx, 0FFFFFFFFh; unsigned int
0x180068147  mov     rcx, rsi; this
0x18006814a  call    ?Wait@CEventSem@@QEAAKKH@Z; CEventSem::Wait(ulong,int)
0x18006814f  jmp     loc_18006804E
0x180068154  mov     dword ptr [rbx+4], 0
0x18006815b  jmp     loc_18006807D
0x180068160  lea     rcx, [rbp+50h+var_80]; this
0x180068164  call    ??0CStateSet@@QEAA@XZ; CStateSet::CStateSet(void)
0x180068169  nop
0x18006816a  lea     rcx, [rbp+50h+var_C0]; this
0x18006816e  call    ??0CStateSet@@QEAA@XZ; CStateSet::CStateSet(void)
0x180068173  nop
0x180068174  lea     rcx, [rsp+150h+var_100]; this
0x180068179  call    ??0CStateSet@@QEAA@XZ; CStateSet::CStateSet(void)
0x18006817e  nop
0x18006817f  lea     r8, [rbp+50h+var_80]; struct CStateSet *
0x180068183  mov     edx, r12d; unsigned int
0x180068186  lea     rcx, [r15+48h]; this
0x18006818a  call    ?XlatToMany@CXlatState@@QEAAXIAEAVCStateSet@@@Z; CXlatState::XlatToMany(uint,CStateSet &)
0x18006818f  mov     esi, [rbp+50h+var_80]
0x180068192  mov     r13d, [rsp+150h+var_120]
0x180068197  test    esi, esi
0x180068199  jnz     loc_1802B8BDA
0x18006819f  jmp     loc_1802B8C0B
0x1800681a4  mov     dword ptr [rbx+4], 0
0x1800681ab  jmp     loc_1800680E8
0x1802b8bda  mov     edx, esi; unsigned int
0x1802b8bdc  lea     rcx, [rbp+50h+var_80]; this
0x1802b8be0  call    ?State@CStateSet@@QEBAII@Z; CStateSet::State(uint)
0x1802b8be5  mov     edx, eax; unsigned int
0x1802b8be7  lea     rcx, [r15+10h]; this
0x1802b8beb  call    ?Get@CNFA@@AEAAPEAVCNFAState@@I@Z; CNFA::Get(uint)
0x1802b8bf0  mov     r8d, r13d; unsigned int
0x1802b8bf3  lea     rdx, [rbp+50h+var_C0]; struct CStateSet *
0x1802b8bf7  mov     rcx, rax; this
0x1802b8bfa  call    ?Move@CNFAState@@QEAAXAEAVCStateSet@@I@Z; CNFAState::Move(CStateSet &,uint)
0x1802b8bff  add     esi, 0FFFFFFFFh
0x1802b8c02  jnz     short loc_1802B8BDA
0x1802b8c04  lea     rbx, [r15+88h]
0x1802b8c0b  mov     esi, [rbp+50h+var_C0]
0x1802b8c0e  test    esi, esi
0x1802b8c10  jnz     short loc_1802B8C55
0x1802b8c12  mov     edx, 0FFFFFFFEh
0x1802b8c17  mov     r14d, edx
0x1802b8c1a  mov     ecx, [r15+20h]
0x1802b8c1e  add     ecx, 7
0x1802b8c21  imul    ecx, r12d
0x1802b8c25  add     ecx, r13d
0x1802b8c28  mov     rax, [r15+68h]
0x1802b8c2c  mov     [rax+rcx*4], edx
0x1802b8c2f  mov     dword ptr [rsp+150h+var_130], r13d
0x1802b8c34  mov     r9d, r12d; wchar_t *
0x1802b8c37  lea     r8, aRegexUndefined; "[Regex] Undefined transition from %u on"...
0x1802b8c3e  mov     edx, 45Eh; wchar_t *
0x1802b8c43  lea     rcx, aOnecoreuapBase_155; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802b8c4a  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1802b8c4f  nop
0x1802b8c50  jmp     loc_1800680AD
0x1802b8c55  mov     edx, esi; unsigned int
0x1802b8c57  lea     rcx, [rbp+50h+var_C0]; this
0x1802b8c5b  call    ?State@CStateSet@@QEBAII@Z; CStateSet::State(uint)
0x1802b8c60  mov     edx, eax; unsigned int
0x1802b8c62  lea     r8, [rsp+150h+var_100]; struct CStateSet *
0x1802b8c67  lea     rcx, [r15+10h]; this
0x1802b8c6b  call    ?EpsClosure@CNFA@@QEAAXIAEAVCStateSet@@@Z; CNFA::EpsClosure(uint,CStateSet &)
0x1802b8c70  add     esi, 0FFFFFFFFh
0x1802b8c73  jnz     short loc_1802B8C55
0x1802b8c75  lea     rbx, [r15+88h]
0x1802b8c7c  lea     rdx, [rsp+150h+var_100]; struct CStateSet *
0x1802b8c81  lea     rcx, [r15+48h]; this
0x1802b8c85  call    ?XlatToOne@CXlatState@@QEAAIAEBVCStateSet@@@Z; CXlatState::XlatToOne(CStateSet const &)
0x1802b8c8a  mov     r14d, eax
0x1802b8c8d  cmp     eax, [r15+64h]
0x1802b8c91  ja      short loc_1802B8CA8
0x1802b8c93  mov     edx, [r15+20h]
0x1802b8c97  add     edx, 7
0x1802b8c9a  imul    edx, r14d
0x1802b8c9e  mov     rax, [r15+68h]
0x1802b8ca2  cmp     dword ptr [rax+rdx*4], 0FFFFFFFEh
0x1802b8ca6  jnz     short loc_1802B8CC4
0x1802b8ca8  lea     rdx, [rsp+150h+var_100]; struct CStateSet *
0x1802b8cad  lea     rcx, [r15+10h]; this
0x1802b8cb1  call    ?IsFinal@CNFA@@QEAAEAEAVCStateSet@@@Z; CNFA::IsFinal(CStateSet &)
0x1802b8cb6  mov     r8b, al; unsigned __int8
0x1802b8cb9  mov     edx, r14d; unsigned int
0x1802b8cbc  mov     rcx, r15; this
0x1802b8cbf  call    ?Add@CDFA@@AEAAXIE@Z; CDFA::Add(uint,uchar)
0x1802b8cc4  mov     ecx, [r15+20h]
0x1802b8cc8  add     ecx, 7
0x1802b8ccb  imul    ecx, r12d
0x1802b8ccf  add     ecx, r13d
0x1802b8cd2  mov     rax, [r15+68h]
0x1802b8cd6  mov     [rax+rcx*4], r14d
0x1802b8cda  mov     dword ptr [rsp+150h+var_128], r14d
0x1802b8cdf  mov     dword ptr [rsp+150h+var_130], r13d
0x1802b8ce4  mov     r9d, r12d; wchar_t *
0x1802b8ce7  lea     r8, aRegexAddingTra; "[Regex] Adding transition from %u on %u"...
0x1802b8cee  mov     edx, 47Bh; wchar_t *
0x1802b8cf3  lea     rcx, aOnecoreuapBase_155; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802b8cfa  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1802b8cff  nop
0x1802b8d00  jmp     loc_1800680AD
```
