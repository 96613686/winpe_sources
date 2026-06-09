# CSpResult::CommitAlternate(CSpPhraseAlt *)

- ea: `0x180126a7c`
- end: `0x180126cd7`
- name: `?CommitAlternate@CSpResult@@QEAAJPEAVCSpPhraseAlt@@@Z`
- size: `603`
- prototype: `__int64 __fastcall(CSpResult *__hidden this, struct CSpPhraseAlt *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18017db30`

## callees

- `0x18000bec4`
- `0x18006ae10`
- `0x18009a9ac`
- `0x180126a7c`
- `0x180127260`
- `0x180127ac8`
- `0x180128f84`
- `0x18017dadc`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180126aaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180126aaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126af7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126cb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126cbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126af7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126cb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126cbd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180126b5f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180126b5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180126c7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180126c7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSpResult::CommitAlternate(CSpResult *this, struct CSpPhraseAlt *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  __int64 v5; // r15
  unsigned int v6; // r8d
  void *v7; // r9
  __int64 v8; // r10
  HRESULT inited; // ebx
  __int64 v11; // rcx
  HRESULT v12; // eax
  __int64 v13; // rcx
  __int128 v14; // [rsp+30h] [rbp-30h] BYREF
  __int128 v15; // [rsp+40h] [rbp-20h]
  __int128 v16; // [rsp+50h] [rbp-10h]
  unsigned int v17; // [rsp+A0h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+48h] BYREF
  LPVOID ppv; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int64 v20; // [rsp+B8h] [rbp+58h]

  v20 = ((unsigned __int64)this + 24) & -(__int64)(this != 0);
  v4 = (struct _RTL_CRITICAL_SECTION *)(v20 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v20 + 8));
  pv = 0;
  v17 = 0;
  v5 = *((_QWORD *)a2 + 9);
  if ( !v5 || !*(_QWORD *)v5 )
  {
    LeaveCriticalSection(v4);
    return 2147942487LL;
  }
  if ( !CSPList<CSpPhraseAlt *,CSpPhraseAlt *>::Find((char *)this + 168, a2) )
  {
    LeaveCriticalSection(v4);
    return 2147766321LL;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 10) + 80LL) != v6 )
    goto LABEL_25;
  inited = 0;
  if ( *((_QWORD *)a2 + 14) )
    inited = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 64LL))(v8);
  ppv = 0;
  if ( inited >= 0 )
  {
    inited = CoCreateInstance(
               (const IID *const)(*((_QWORD *)this + 10) + 24LL),
               0,
               0x17u,
               &GUID_fece8294_2be1_408f_8e68_2de377092f0e,
               &ppv);
    if ( inited >= 0 )
    {
      inited = CSpResult::InitAltRequestInfo(this);
      if ( inited >= 0 )
      {
        v14 = *((_OWORD *)this + 14);
        v15 = *((_OWORD *)this + 15);
        v16 = *((_OWORD *)this + 16);
        *(_QWORD *)&v14 = *(_QWORD *)(v5 + 8);
        DWORD2(v14) = *((_DWORD *)a2 + 20);
        v11 = *((_QWORD *)this + 10);
        if ( *(_DWORD *)(v11 + 96) )
          *(_QWORD *)&v15 = v11 + *(unsigned int *)(v11 + 96);
        else
          *(_QWORD *)&v15 = 0;
        DWORD2(v15) = *(_DWORD *)(v11 + 92);
        inited = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64, LPVOID *, unsigned int *))(*(_QWORD *)ppv + 32LL))(
                   ppv,
                   &v14,
                   v5,
                   &pv,
                   &v17);
        if ( inited >= 0 )
        {
          if ( v17 )
          {
            if ( pv )
            {
LABEL_17:
              inited = CSpPhraseAlt::CacheOriginalPhrase(a2, **((struct ISpPhrase ***)a2 + 9));
              goto LABEL_21;
            }
          }
          else if ( !pv )
          {
            goto LABEL_17;
          }
          inited = -2147200949;
        }
        pv = 0;
        v17 = 0;
      }
    }
  }
LABEL_21:
  v12 = CSpResult::ConvertEnginePhrase(this, *(struct ISpPhraseBuilder **)v5);
  if ( inited >= 0 )
    inited = v12;
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppv);
  if ( inited < 0 )
    goto LABEL_26;
  v7 = pv;
  v6 = v17;
LABEL_25:
  inited = CSpResult::InitResultFromPhraseAlt(this, 0, a2, v7, v6);
LABEL_26:
  CoTaskMemFree(pv);
  CSPList<LEXICONENTRY,LEXICONENTRY>::RemoveAll((char *)this + 168);
  v13 = *((_QWORD *)this + 32);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *((_QWORD *)this + 32) = 0;
  }
  LeaveCriticalSection(v4);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180126a7c  push    rbp
0x180126a7e  push    rbx
0x180126a7f  push    rsi
0x180126a80  push    rdi
0x180126a81  push    r12
0x180126a83  push    r14
0x180126a85  push    r15
0x180126a87  mov     rbp, rsp
0x180126a8a  sub     rsp, 60h
0x180126a8e  mov     rsi, rdx
0x180126a91  mov     rdi, rcx
0x180126a94  mov     rax, rcx
0x180126a97  lea     r8, [rcx+18h]
0x180126a9b  neg     rax
0x180126a9e  sbb     r9, r9
0x180126aa1  and     r9, r8
0x180126aa4  mov     [rbp+arg_18], r9
0x180126aa8  lea     r14, [r9+8]
0x180126aac  mov     rcx, r14; lpCriticalSection
0x180126aaf  call    cs:__imp_EnterCriticalSection
0x180126ab5  nop
0x180126ab6  xor     r9d, r9d
0x180126ab9  mov     [rbp+pv], r9
0x180126abd  xor     r8d, r8d
0x180126ac0  mov     [rbp+arg_0], r8d
0x180126ac4  mov     r15, [rsi+48h]
0x180126ac8  test    r15, r15
0x180126acb  jz      loc_180126CBA
0x180126ad1  mov     r10, [r15]
0x180126ad4  test    r10, r10
0x180126ad7  jz      loc_180126CBA
0x180126add  lea     r12, [rdi+0A8h]
0x180126ae4  mov     rdx, rsi
0x180126ae7  mov     rcx, r12
0x180126aea  call    ?Find@?$CSPList@PEAVCSpPhraseAlt@@PEAV1@@@QEBAPEAXPEAVCSpPhraseAlt@@PEAX@Z; CSPList<CSpPhraseAlt *,CSpPhraseAlt *>::Find(CSpPhraseAlt *,void *)
0x180126aef  test    rax, rax
0x180126af2  jnz     short loc_180126B07
0x180126af4  mov     rcx, r14; lpCriticalSection
0x180126af7  call    cs:__imp_LeaveCriticalSection
0x180126afd  mov     eax, 80045031h
0x180126b02  jmp     loc_180126CC8
0x180126b07  mov     rax, [rdi+50h]
0x180126b0b  cmp     [rax+50h], r8d
0x180126b0f  jnz     loc_180126C64
0x180126b15  mov     rdx, [rsi+70h]
0x180126b19  xor     ebx, ebx
0x180126b1b  test    rdx, rdx
0x180126b1e  jz      short loc_180126B31
0x180126b20  mov     rax, [r10]
0x180126b23  mov     rcx, r10
0x180126b26  mov     rax, [rax+40h]
0x180126b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180126b2f  mov     ebx, eax
0x180126b31  mov     [rbp+arg_10], 0
0x180126b39  test    ebx, ebx
0x180126b3b  js      loc_180126C3F
0x180126b41  mov     rcx, [rdi+50h]
0x180126b45  add     rcx, 18h; rclsid
0x180126b49  lea     rax, [rbp+arg_10]
0x180126b4d  mov     [rsp+60h+ppv], rax; ppv
0x180126b52  lea     r9, _GUID_fece8294_2be1_408f_8e68_2de377092f0e; riid
0x180126b59  xor     edx, edx; pUnkOuter
0x180126b5b  lea     r8d, [rdx+17h]; dwClsContext
0x180126b5f  call    cs:__imp_CoCreateInstance
0x180126b65  mov     ebx, eax
0x180126b67  test    eax, eax
0x180126b69  js      loc_180126C3F
0x180126b6f  mov     rcx, rdi; this
0x180126b72  call    ?InitAltRequestInfo@CSpResult@@AEAAJXZ; CSpResult::InitAltRequestInfo(void)
0x180126b77  mov     ebx, eax
0x180126b79  test    eax, eax
0x180126b7b  js      loc_180126C3F
0x180126b81  movups  xmm0, xmmword ptr [rdi+0E0h]
0x180126b88  movups  [rbp+var_30], xmm0
0x180126b8c  movups  xmm1, xmmword ptr [rdi+0F0h]
0x180126b93  movups  [rbp+var_20], xmm1
0x180126b97  movups  xmm0, xmmword ptr [rdi+100h]
0x180126b9e  movups  [rbp+var_10], xmm0
0x180126ba2  mov     eax, [r15+8]
0x180126ba6  mov     dword ptr [rbp+var_30], eax
0x180126ba9  mov     eax, [r15+0Ch]
0x180126bad  mov     dword ptr [rbp+var_30+4], eax
0x180126bb0  mov     eax, [rsi+50h]
0x180126bb3  mov     dword ptr [rbp+var_30+8], eax
0x180126bb6  mov     rcx, [rdi+50h]
0x180126bba  cmp     dword ptr [rcx+60h], 0
0x180126bbe  jz      short loc_180126BCC
0x180126bc0  mov     eax, [rcx+60h]
0x180126bc3  add     rax, rcx
0x180126bc6  mov     qword ptr [rbp+var_20], rax
0x180126bca  jmp     short loc_180126BD4
0x180126bcc  mov     qword ptr [rbp+var_20], 0
0x180126bd4  mov     eax, [rcx+5Ch]
0x180126bd7  mov     dword ptr [rbp+var_20+8], eax
0x180126bda  mov     rcx, [rbp+arg_10]
0x180126bde  mov     rax, [rcx]
0x180126be1  lea     rdx, [rbp+arg_0]
0x180126be5  mov     [rsp+60h+ppv], rdx
0x180126bea  lea     r9, [rbp+pv]
0x180126bee  mov     r8, r15
0x180126bf1  lea     rdx, [rbp+var_30]
0x180126bf5  mov     rax, [rax+20h]
0x180126bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180126bfe  mov     ebx, eax
0x180126c00  test    eax, eax
0x180126c02  js      short loc_180126C30
0x180126c04  cmp     [rbp+arg_0], 0
0x180126c08  jz      short loc_180126C24
0x180126c0a  cmp     [rbp+pv], 0
0x180126c0f  jz      short loc_180126C2B
0x180126c11  mov     rdx, [rsi+48h]
0x180126c15  mov     rdx, [rdx]; struct ISpPhrase *
0x180126c18  mov     rcx, rsi; this
0x180126c1b  call    ?CacheOriginalPhrase@CSpPhraseAlt@@QEAAJPEAUISpPhrase@@@Z; CSpPhraseAlt::CacheOriginalPhrase(ISpPhrase *)
0x180126c20  mov     ebx, eax
0x180126c22  jmp     short loc_180126C3F
0x180126c24  cmp     [rbp+pv], 0
0x180126c29  jz      short loc_180126C11
0x180126c2b  mov     ebx, 8004504Bh
0x180126c30  mov     [rbp+pv], 0
0x180126c38  mov     [rbp+arg_0], 0
0x180126c3f  mov     rdx, [r15]; struct ISpPhraseBuilder *
0x180126c42  mov     rcx, rdi; this
0x180126c45  call    ?ConvertEnginePhrase@CSpResult@@AEAAJPEAUISpPhraseBuilder@@@Z; CSpResult::ConvertEnginePhrase(ISpPhraseBuilder *)
0x180126c4a  test    ebx, ebx
0x180126c4c  cmovns  ebx, eax
0x180126c4f  lea     rcx, [rbp+arg_10]
0x180126c53  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x180126c58  test    ebx, ebx
0x180126c5a  js      short loc_180126C78
0x180126c5c  mov     r9, [rbp+pv]; void *
0x180126c60  mov     r8d, [rbp+arg_0]
0x180126c64  mov     dword ptr [rsp+60h+ppv], r8d; unsigned int
0x180126c69  mov     r8, rsi; struct CSpPhraseAlt *
0x180126c6c  xor     edx, edx; struct CSpResult *
0x180126c6e  mov     rcx, rdi; this
0x180126c71  call    ?InitResultFromPhraseAlt@CSpResult@@AEAAJPEAV1@PEAVCSpPhraseAlt@@PEAXK@Z; CSpResult::InitResultFromPhraseAlt(CSpResult *,CSpPhraseAlt *,void *,ulong)
0x180126c76  mov     ebx, eax
0x180126c78  mov     rcx, [rbp+pv]; pv
0x180126c7c  call    cs:__imp_CoTaskMemFree
0x180126c82  mov     rcx, r12
0x180126c85  call    ?RemoveAll@?$CSPList@ULEXICONENTRY@@U1@@@QEAAXXZ; CSPList<LEXICONENTRY,LEXICONENTRY>::RemoveAll(void)
0x180126c8a  mov     rcx, [rdi+100h]
0x180126c91  test    rcx, rcx
0x180126c94  jz      short loc_180126CAD
0x180126c96  mov     rdx, [rcx]
0x180126c99  mov     rax, [rdx+10h]
0x180126c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180126ca2  mov     qword ptr [rdi+100h], 0
0x180126cad  mov     rcx, r14; lpCriticalSection
0x180126cb0  call    cs:__imp_LeaveCriticalSection
0x180126cb6  mov     eax, ebx
0x180126cb8  jmp     short loc_180126CC8
0x180126cba  mov     rcx, r14; lpCriticalSection
0x180126cbd  call    cs:__imp_LeaveCriticalSection
0x180126cc3  mov     eax, 80070057h
0x180126cc8  add     rsp, 60h
0x180126ccc  pop     r15
0x180126cce  pop     r14
0x180126cd0  pop     r12
0x180126cd2  pop     rdi
0x180126cd3  pop     rsi
0x180126cd4  pop     rbx
0x180126cd5  pop     rbp
0x180126cd6  retn
```
