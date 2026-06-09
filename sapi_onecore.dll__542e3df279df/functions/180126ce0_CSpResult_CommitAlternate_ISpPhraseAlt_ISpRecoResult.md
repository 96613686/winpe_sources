# CSpResult::CommitAlternate(ISpPhraseAlt *,ISpRecoResult * *)

- ea: `0x180126ce0`
- end: `0x180126f77`
- name: `?CommitAlternate@CSpResult@@UEAAJPEAUISpPhraseAlt@@PEAPEAUISpRecoResult@@@Z`
- size: `663`
- prototype: `int(CSpResult *__hidden this, struct ISpPhraseAlt *, struct ISpRecoResult **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000bec4`
- `0x18006ae10`
- `0x180111f50`
- `0x180126ce0`
- `0x180127260`
- `0x180128f84`
- `0x18017dadc`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180126d1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180126d1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126f3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126f47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126f54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126f3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126f47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126f54`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180126dd2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180126dd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180126f26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180126f26`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSpResult::CommitAlternate(CSpResult *this, struct ISpPhraseAlt *a2, struct ISpRecoResult **a3)
{
  struct ISpPhraseAltVtbl *v6; // r14
  struct _RTL_CRITICAL_SECTION *v7; // r12
  struct ISpPhrase **lpVtbl; // rdi
  ULONG (__stdcall *AddRef)(ISpPhraseAlt *); // rcx
  __int64 v10; // rax
  int inited; // ebx
  __int64 v12; // rcx
  int v13; // eax
  struct CSpResult *v14; // rdi
  struct CSpResult *v16; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int64 v17; // [rsp+38h] [rbp-38h]
  __int128 v18; // [rsp+40h] [rbp-30h] BYREF
  __int128 v19; // [rsp+50h] [rbp-20h]
  __int128 v20; // [rsp+60h] [rbp-10h]
  unsigned int v21; // [rsp+B0h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+48h] BYREF
  LPVOID ppv; // [rsp+C8h] [rbp+58h] BYREF

  v6 = (struct ISpPhraseAltVtbl *)((char *)this - 8);
  v17 = ((unsigned __int64)this + 16) & -(__int64)(this != (CSpResult *)8);
  v7 = (struct _RTL_CRITICAL_SECTION *)(v17 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
  if ( !a2 || (lpVtbl = (struct ISpPhrase **)a2[9].lpVtbl) == 0 || !*lpVtbl || a2[11].lpVtbl != v6 )
  {
    LeaveCriticalSection(v7);
    return 2147942487LL;
  }
  AddRef = v6[1].AddRef;
  if ( *((_DWORD *)AddRef + 20) )
    goto LABEL_33;
  v10 = *((_QWORD *)AddRef + 3) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v10 )
    v10 = *((_QWORD *)AddRef + 4) - *(_QWORD *)GUID_NULL.Data4;
  if ( !v10 )
  {
LABEL_33:
    LeaveCriticalSection(v7);
    return 0;
  }
  inited = 0;
  if ( a2[14].lpVtbl )
    inited = ((__int64 (__fastcall *)(struct ISpPhrase *))(*lpVtbl)->lpVtbl[1].AddRef)(*lpVtbl);
  pv = 0;
  v21 = 0;
  ppv = 0;
  if ( CoCreateInstance(
         (const IID *const)(*((_QWORD *)this + 9) + 24LL),
         0,
         0x17u,
         &GUID_fece8294_2be1_408f_8e68_2de377092f0e,
         &ppv) < 0 )
  {
    if ( inited < 0 )
      goto LABEL_24;
    goto LABEL_23;
  }
  inited = CSpResult::InitAltRequestInfo((CSpResult *)v6);
  if ( inited < 0 )
    goto LABEL_24;
  v18 = *(_OWORD *)((char *)this + 216);
  v19 = *(_OWORD *)((char *)this + 232);
  v20 = *(_OWORD *)((char *)this + 248);
  *(_QWORD *)&v18 = lpVtbl[1];
  DWORD2(v18) = a2[10].lpVtbl;
  v12 = *((_QWORD *)this + 9);
  *(_QWORD *)&v19 = *(_DWORD *)(v12 + 96) ? v12 + *(unsigned int *)(v12 + 96) : 0LL;
  DWORD2(v19) = *(_DWORD *)(v12 + 92);
  inited = (*(__int64 (__fastcall **)(LPVOID, __int128 *, struct ISpPhrase **, LPVOID *, unsigned int *))(*(_QWORD *)ppv + 32LL))(
             ppv,
             &v18,
             lpVtbl,
             &pv,
             &v21);
  if ( inited < 0 )
    goto LABEL_24;
  if ( v21 )
  {
    if ( pv )
      goto LABEL_23;
LABEL_21:
    inited = -2147200949;
    goto LABEL_24;
  }
  if ( pv )
    goto LABEL_21;
LABEL_23:
  inited = CSpPhraseAlt::CacheOriginalPhrase((CSpPhraseAlt *)a2, *lpVtbl);
LABEL_24:
  v13 = CSpResult::ConvertEnginePhrase((CSpResult *)v6, (struct ISpPhraseBuilder *)*lpVtbl);
  if ( inited >= 0 )
  {
    inited = v13;
    if ( v13 >= 0 )
    {
      if ( a3 )
      {
        v16 = 0;
        inited = ATL::CComObject<CSpResult>::CreateInstance(&v16);
        v14 = v16;
        if ( inited < 0
          || ((*(void (__fastcall **)(struct CSpResult *))(*(_QWORD *)v16 + 8LL))(v16),
              inited = CSpResult::InitResultFromPhraseAlt((CSpResult *)v6, v14, (struct CSpPhraseAlt *)a2, pv, v21),
              inited < 0) )
        {
          if ( v14 )
            (*(void (__fastcall **)(struct CSpResult *))(*(_QWORD *)v14 + 16LL))(v14);
        }
        else
        {
          *a3 = (struct ISpRecoResult *)((char *)v14 + 8);
        }
      }
    }
  }
  CoTaskMemFree(pv);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppv);
  LeaveCriticalSection(v7);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180126ce0  mov     [rsp-38h+arg_10], rbx
0x180126ce5  push    rbp
0x180126ce6  push    rsi
0x180126ce7  push    rdi
0x180126ce8  push    r12
0x180126cea  push    r13
0x180126cec  push    r14
0x180126cee  push    r15
0x180126cf0  mov     rbp, rsp
0x180126cf3  sub     rsp, 70h
0x180126cf7  mov     r13, r8
0x180126cfa  mov     rsi, rdx
0x180126cfd  mov     r15, rcx
0x180126d00  lea     r14, [rcx-8]
0x180126d04  mov     rax, r14
0x180126d07  lea     r9, [rcx+10h]
0x180126d0b  neg     rax
0x180126d0e  sbb     r10, r10
0x180126d11  and     r10, r9
0x180126d14  mov     [rbp+var_38], r10
0x180126d18  lea     r12, [r10+8]
0x180126d1c  mov     rcx, r12; lpCriticalSection
0x180126d1f  call    cs:__imp_EnterCriticalSection
0x180126d25  nop
0x180126d26  test    rsi, rsi
0x180126d29  jz      loc_180126F51
0x180126d2f  mov     rdi, [rsi+48h]
0x180126d33  test    rdi, rdi
0x180126d36  jz      loc_180126F51
0x180126d3c  mov     r8, [rdi]
0x180126d3f  test    r8, r8
0x180126d42  jz      loc_180126F51
0x180126d48  cmp     [rsi+58h], r14
0x180126d4c  jnz     loc_180126F51
0x180126d52  mov     rcx, [r14+50h]
0x180126d56  cmp     dword ptr [rcx+50h], 0
0x180126d5a  jnz     loc_180126F44
0x180126d60  mov     rax, [rcx+18h]
0x180126d64  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180126d6b  jnz     short loc_180126D78
0x180126d6d  mov     rax, [rcx+20h]
0x180126d71  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180126d78  test    rax, rax
0x180126d7b  jz      loc_180126F44
0x180126d81  mov     rdx, [rsi+70h]
0x180126d85  xor     ebx, ebx
0x180126d87  test    rdx, rdx
0x180126d8a  jz      short loc_180126D9D
0x180126d8c  mov     rax, [r8]
0x180126d8f  mov     rcx, r8
0x180126d92  mov     rax, [rax+40h]
0x180126d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180126d9b  mov     ebx, eax
0x180126d9d  mov     [rbp+pv], 0
0x180126da5  mov     [rbp+arg_0], 0
0x180126dac  mov     [rbp+arg_18], 0
0x180126db4  mov     rcx, [r15+48h]
0x180126db8  add     rcx, 18h; rclsid
0x180126dbc  lea     rax, [rbp+arg_18]
0x180126dc0  mov     [rsp+70h+ppv], rax; ppv
0x180126dc5  lea     r9, _GUID_fece8294_2be1_408f_8e68_2de377092f0e; riid
0x180126dcc  xor     edx, edx; pUnkOuter
0x180126dce  lea     r8d, [rdx+17h]; dwClsContext
0x180126dd2  call    cs:__imp_CoCreateInstance
0x180126dd8  test    eax, eax
0x180126dda  js      loc_180126E90
0x180126de0  mov     rcx, r14; this
0x180126de3  call    ?InitAltRequestInfo@CSpResult@@AEAAJXZ; CSpResult::InitAltRequestInfo(void)
0x180126de8  mov     ebx, eax
0x180126dea  test    eax, eax
0x180126dec  js      loc_180126EA1
0x180126df2  movups  xmm0, xmmword ptr [r15+0D8h]
0x180126dfa  movups  [rbp+var_30], xmm0
0x180126dfe  movups  xmm1, xmmword ptr [r15+0E8h]
0x180126e06  movups  [rbp+var_20], xmm1
0x180126e0a  movups  xmm0, xmmword ptr [r15+0F8h]
0x180126e12  movups  [rbp+var_10], xmm0
0x180126e16  mov     eax, [rdi+8]
0x180126e19  mov     dword ptr [rbp+var_30], eax
0x180126e1c  mov     eax, [rdi+0Ch]
0x180126e1f  mov     dword ptr [rbp+var_30+4], eax
0x180126e22  mov     eax, [rsi+50h]
0x180126e25  mov     dword ptr [rbp+var_30+8], eax
0x180126e28  mov     rcx, [r15+48h]
0x180126e2c  xor     r15d, r15d
0x180126e2f  cmp     [rcx+60h], r15d
0x180126e33  jz      short loc_180126E41
0x180126e35  mov     eax, [rcx+60h]
0x180126e38  add     rax, rcx
0x180126e3b  mov     qword ptr [rbp+var_20], rax
0x180126e3f  jmp     short loc_180126E45
0x180126e41  mov     qword ptr [rbp+var_20], r15
0x180126e45  mov     eax, [rcx+5Ch]
0x180126e48  mov     dword ptr [rbp+var_20+8], eax
0x180126e4b  mov     rcx, [rbp+arg_18]
0x180126e4f  mov     rax, [rcx]
0x180126e52  lea     rdx, [rbp+arg_0]
0x180126e56  mov     [rsp+70h+ppv], rdx
0x180126e5b  lea     r9, [rbp+pv]
0x180126e5f  mov     r8, rdi
0x180126e62  lea     rdx, [rbp+var_30]
0x180126e66  mov     rax, [rax+20h]
0x180126e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180126e6f  mov     ebx, eax
0x180126e71  test    eax, eax
0x180126e73  js      short loc_180126EA1
0x180126e75  cmp     [rbp+arg_0], r15d
0x180126e79  jz      short loc_180126E83
0x180126e7b  cmp     [rbp+pv], r15
0x180126e7f  jz      short loc_180126E89
0x180126e81  jmp     short loc_180126E94
0x180126e83  cmp     [rbp+pv], r15
0x180126e87  jz      short loc_180126E94
0x180126e89  mov     ebx, 8004504Bh
0x180126e8e  jmp     short loc_180126EA1
0x180126e90  test    ebx, ebx
0x180126e92  js      short loc_180126EA1
0x180126e94  mov     rdx, [rdi]; struct ISpPhrase *
0x180126e97  mov     rcx, rsi; this
0x180126e9a  call    ?CacheOriginalPhrase@CSpPhraseAlt@@QEAAJPEAUISpPhrase@@@Z; CSpPhraseAlt::CacheOriginalPhrase(ISpPhrase *)
0x180126e9f  mov     ebx, eax
0x180126ea1  mov     rdx, [rdi]; struct ISpPhraseBuilder *
0x180126ea4  mov     rcx, r14; this
0x180126ea7  call    ?ConvertEnginePhrase@CSpResult@@AEAAJPEAUISpPhraseBuilder@@@Z; CSpResult::ConvertEnginePhrase(ISpPhraseBuilder *)
0x180126eac  test    ebx, ebx
0x180126eae  js      short loc_180126F22
0x180126eb0  mov     ebx, eax
0x180126eb2  test    eax, eax
0x180126eb4  js      short loc_180126F22
0x180126eb6  test    r13, r13
0x180126eb9  jz      short loc_180126F22
0x180126ebb  mov     [rbp+var_40], 0
0x180126ec3  lea     rcx, [rbp+var_40]
0x180126ec7  call    ?CreateInstance@?$CComObject@VCSpResult@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSpResult>::CreateInstance(ATL::CComObject<CSpResult> * *)
0x180126ecc  mov     ebx, eax
0x180126ece  mov     rdi, [rbp+var_40]
0x180126ed2  test    eax, eax
0x180126ed4  js      short loc_180126F0E
0x180126ed6  mov     rax, [rdi]
0x180126ed9  mov     rcx, rdi
0x180126edc  mov     rax, [rax+8]
0x180126ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180126ee5  mov     eax, [rbp+arg_0]
0x180126ee8  mov     dword ptr [rsp+70h+ppv], eax; unsigned int
0x180126eec  mov     r9, [rbp+pv]; void *
0x180126ef0  mov     r8, rsi; struct CSpPhraseAlt *
0x180126ef3  mov     rdx, rdi; struct CSpResult *
0x180126ef6  mov     rcx, r14; this
0x180126ef9  call    ?InitResultFromPhraseAlt@CSpResult@@AEAAJPEAV1@PEAVCSpPhraseAlt@@PEAXK@Z; CSpResult::InitResultFromPhraseAlt(CSpResult *,CSpPhraseAlt *,void *,ulong)
0x180126efe  mov     ebx, eax
0x180126f00  test    eax, eax
0x180126f02  js      short loc_180126F0E
0x180126f04  lea     rax, [rdi+8]
0x180126f08  mov     [r13+0], rax
0x180126f0c  jmp     short loc_180126F22
0x180126f0e  test    rdi, rdi
0x180126f11  jz      short loc_180126F22
0x180126f13  mov     rax, [rdi]
0x180126f16  mov     rcx, rdi
0x180126f19  mov     rax, [rax+10h]
0x180126f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180126f22  mov     rcx, [rbp+pv]; pv
0x180126f26  call    cs:__imp_CoTaskMemFree
0x180126f2c  nop
0x180126f2d  lea     rcx, [rbp+arg_18]
0x180126f31  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x180126f36  nop
0x180126f37  mov     rcx, r12; lpCriticalSection
0x180126f3a  call    cs:__imp_LeaveCriticalSection
0x180126f40  mov     eax, ebx
0x180126f42  jmp     short loc_180126F5F
0x180126f44  mov     rcx, r12; lpCriticalSection
0x180126f47  call    cs:__imp_LeaveCriticalSection
0x180126f4d  xor     eax, eax
0x180126f4f  jmp     short loc_180126F5F
0x180126f51  mov     rcx, r12; lpCriticalSection
0x180126f54  call    cs:__imp_LeaveCriticalSection
0x180126f5a  mov     eax, 80070057h
0x180126f5f  mov     rbx, [rsp+70h+arg_10]
0x180126f67  add     rsp, 70h
0x180126f6b  pop     r15
0x180126f6d  pop     r14
0x180126f6f  pop     r13
0x180126f71  pop     r12
0x180126f73  pop     rdi
0x180126f74  pop     rsi
0x180126f75  pop     rbp
0x180126f76  retn
```
