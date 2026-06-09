# UnionFs::UfsStreamHandleCtx::AddSubContext(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsUnionCtx &,UnionFs::UfsLayerCtx const &,ulong,_FILE_INFORMATION_CLASS,_UNICODE_STRING const &,uchar,UnionFs::StackEventTracer &,bool)

- ea: `0x140024c4c`
- end: `0x140024f87`
- name: `?AddSubContext@UfsStreamHandleCtx@UnionFs@@AEBAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAVUfsUnionCtx@2@AEBVUfsLayerCtx@2@KW4_FILE_INFORMATION_CLASS@@AEBU_UNICODE_STRING@@EAEAVStackEventTracer@2@_N@Z`
- size: `827`
- prototype: `__int64 __fastcall(UnionFs::UfsStreamHandleCtx *__hidden this, const struct _FLT_INSTANCE *, const struct _FILE_OBJECT *, struct UnionFs::UfsUnionCtx *, const struct UnionFs::UfsLayerCtx *, unsigned int, enum _FILE_INFORMATION_CLASS, const struct _UNICODE_STRING *, unsigned __int8, struct UnionFs::StackEventTracer *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140029e68`

## callees

- `0x14000f7fc`
- `0x14001ac2c`
- `0x14001bec0`
- `0x14001bf80`
- `0x140024c4c`
- `0x14002accc`
- `0x14002afb8`
- `0x140056ac4`
- `0x140056afc`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140024da8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140024e23`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140024eb6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140024da8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140024e23`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140024eb6`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140024cd4`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140024cd4`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsStreamHandleCtx::AddSubContext(
        UnionFs::UfsStreamHandleCtx *this,
        const struct _FLT_INSTANCE *a2,
        const struct _FILE_OBJECT *a3,
        struct UnionFs::UfsUnionCtx *a4,
        const struct UnionFs::UfsLayerCtx *a5,
        unsigned int a6,
        enum _FILE_INFORMATION_CLASS a7,
        const struct _UNICODE_STRING *a8,
        unsigned __int8 a9,
        struct UnionFs::StackEventTracer *a10,
        bool a11)
{
  unsigned int v16; // edi
  UnionFs::UfsEnumContext *v17; // rax
  UnionFs::UfsEnumContext *v18; // rbx
  int v19; // esi
  int v20; // edi
  int v21; // eax
  __int64 *v22; // rdi
  UnionFs::UfsEnumContext **v23; // rax
  UnionFs::UfsEnumContext *v24; // rsi
  __int64 v25; // r14
  UnionFs::UfsEnumContext **v26; // r8
  __int64 v27; // rdx
  char *v28; // rcx
  char *v29; // rax
  struct UnionFs::StackEventTracer *v30; // [rsp+28h] [rbp-38h]
  struct UnionFs::StackEventTracer *v31; // [rsp+28h] [rbp-38h]
  struct UnionFs::StackEventTracer *v32; // [rsp+28h] [rbp-38h]
  UnionFs::UfsEnumContext *v33; // [rsp+40h] [rbp-20h] BYREF
  __int64 v34; // [rsp+48h] [rbp-18h] BYREF
  utl::_RefCountBase *v35; // [rsp+50h] [rbp-10h]

  UnionFs::UfsStreamHandleCtx::TryGetScratchLayer(this, &v34);
  if ( !v34 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED0008LL,
      (int)a10,
      (struct UnionFs::StackEventTracer *)0x3D1000A0A86LL,
      (unsigned __int64)"UnionFs::UfsStreamHandleCtx::AddSubContext",
      "ORIGIN: Can't get scratch layer",
      (const char *)v30);
    if ( v35 )
      utl::_RefCountBase::_DecStrong(v35);
    return 3236757512LL;
  }
  v16 = *((_DWORD *)this + 43);
  v17 = (UnionFs::UfsEnumContext *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState
                                                                                    + 1184));
  v18 = v17;
  if ( !v17 )
  {
    v19 = (int)a10;
    v20 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a10,
      (struct UnionFs::StackEventTracer *)0x1D000040030LL,
      (unsigned __int64)"UnionFs::UfsEnumContext::AllocAndInit",
      "ORIGIN: Allocating UfsEnumContext",
      (const char *)v30);
    goto LABEL_29;
  }
  *((_QWORD *)v17 + 1) = a3;
  *(_QWORD *)v17 = a2;
  *((_QWORD *)v17 + 3) = a4;
  v19 = (int)a10;
  *((_QWORD *)v17 + 2) = a5;
  *((_QWORD *)v17 + 4) = 0;
  *((_DWORD *)v17 + 18) = a11;
  *((_QWORD *)v17 + 5) = 0;
  *((_QWORD *)v17 + 6) = 0;
  *((_QWORD *)v17 + 7) = 0;
  *((_DWORD *)v17 + 16) = 0;
  *((_BYTE *)v17 + 68) = 0;
  v20 = UnionFs::UfsEnumContext::ResetBuffer(v17, a6, a7, a9, v16, a10, 0);
  if ( v20 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v20,
      (int)a10,
      (struct UnionFs::StackEventTracer *)0x1D30004003ALL,
      (unsigned __int64)"UnionFs::UfsEnumContext::AllocAndInit",
      "PUSH: Resetting buffer",
      (const char *)v31);
    UnionFs::UfsEnumContext::~UfsEnumContext(v18);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1184), v18);
LABEL_29:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v20,
      v19,
      (struct UnionFs::StackEventTracer *)0x1CC000A0A98LL,
      (unsigned __int64)"UnionFs::UfsStreamHandleCtx::AddSubContext",
      "PUSH: UfsEnumContext::AllocAndInit",
      (const char *)v32);
    goto LABEL_30;
  }
  v21 = *((_DWORD *)this + 22);
  v33 = v18;
  if ( (v21 & 0x10) != 0 && (a9 & 1) == 0 )
  {
    v20 = UnionFs::UfsEnumContext::PrimeForEnumeration(v18, a9, a10, a8);
    if ( v20 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v20,
        (int)a10,
        (struct UnionFs::StackEventTracer *)0xC9000A0AA5LL,
        (unsigned __int64)"UnionFs::UfsStreamHandleCtx::AddSubContext",
        "PUSH: Error priming handle for resumed enumeration",
        (const char *)v31);
LABEL_12:
      UnionFs::UfsEnumContext::~UfsEnumContext(v18);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1184), v18);
LABEL_30:
      if ( v35 )
        utl::_RefCountBase::_DecStrong(v35);
      return (unsigned int)v20;
    }
    *((_DWORD *)v18 + 18) |= 2u;
  }
  v22 = (__int64 *)((char *)this + 144);
  v23 = (UnionFs::UfsEnumContext **)*((_QWORD *)this + 19);
  if ( v23 == *((UnionFs::UfsEnumContext ***)this + 20) )
  {
    v25 = *v22;
    if ( !(unsigned __int8)utl::vector<utl::unique_ptr<UnionFs::UfsEnumContext,utl::default_delete<UnionFs::UfsEnumContext>>,utl::allocator<utl::unique_ptr<UnionFs::UfsEnumContext,utl::default_delete<UnionFs::UfsEnumContext>>>>::_Grow(v22) )
    {
      v20 = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a10,
        (struct UnionFs::StackEventTracer *)0x1D1000A0AAFLL,
        (unsigned __int64)"UnionFs::UfsStreamHandleCtx::AddSubContext",
        "ORIGIN: Storing sub-context",
        (const char *)v31);
      if ( !v18 )
        goto LABEL_30;
      goto LABEL_12;
    }
    v26 = (UnionFs::UfsEnumContext **)v22[1];
    v27 = *v22;
    v28 = (char *)&v33 - v25;
    if ( (char *)&v33 - v25 >= (char *)v26 - *v22 )
    {
      v29 = (char *)&v33;
    }
    else
    {
      v29 = &v28[v27];
      v18 = *(UnionFs::UfsEnumContext **)&v28[v27];
    }
    *(_QWORD *)v29 = 0;
    v24 = v33;
    *v26 = v18;
  }
  else
  {
    v24 = 0;
    *v23 = v18;
  }
  v22[1] += 8;
  if ( v24 )
  {
    UnionFs::UfsEnumContext::~UfsEnumContext(v24);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1184), v24);
  }
  if ( v35 )
    utl::_RefCountBase::_DecStrong(v35);
  return 0;
}

```

## disassembly

```asm
0x140024c4c  push    rbp
0x140024c4e  push    rbx
0x140024c4f  push    rsi
0x140024c50  push    rdi
0x140024c51  push    r12
0x140024c53  push    r14
0x140024c55  push    r15
0x140024c57  mov     rbp, rsp
0x140024c5a  sub     rsp, 60h
0x140024c5e  mov     r12, rdx
0x140024c61  mov     rsi, r9
0x140024c64  lea     rdx, [rbp+var_18]
0x140024c68  mov     r15, r8
0x140024c6b  mov     r14, rcx
0x140024c6e  call    ?TryGetScratchLayer@UfsStreamHandleCtx@UnionFs@@QEBA?AV?$shared_ptr@$$CBVUfsLayerCtx@UnionFs@@@utl@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchLayer(void)
0x140024c73  cmp     [rbp+var_18], 0
0x140024c78  jnz     short loc_140024CBF
0x140024c7a  mov     rdx, [rbp+arg_48]; int
0x140024c81  lea     rax, aOriginCanTGetS_0; "ORIGIN: Can't get scratch layer"
0x140024c88  mov     ebx, 0C0ED0008h
0x140024c8d  mov     [rsp+60h+var_40], rax; char *
0x140024c92  mov     ecx, ebx; this
0x140024c94  lea     r9, aUnionfsUfsstre_24; "UnionFs::UfsStreamHandleCtx::AddSubCont"...
0x140024c9b  mov     r8, 3D1000A0A86h; struct UnionFs::StackEventTracer *
0x140024ca5  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140024caa  mov     rcx, [rbp+var_10]; this
0x140024cae  test    rcx, rcx
0x140024cb1  jz      short loc_140024CB8
0x140024cb3  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140024cb8  mov     eax, ebx
0x140024cba  jmp     loc_140024F77
0x140024cbf  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140024cc6  mov     edi, [r14+0ACh]
0x140024ccd  add     rcx, 4A0h; Lookaside
0x140024cd4  call    cs:__imp_ExAllocateFromLookasideListEx
0x140024cdb  nop     dword ptr [rax+rax+00h]
0x140024ce0  mov     rbx, rax
0x140024ce3  test    rax, rax
0x140024ce6  jz      loc_140024F0D
0x140024cec  mov     r8d, [rbp+arg_30]; enum _FILE_INFORMATION_CLASS
0x140024cf0  mov     rcx, rbx; this
0x140024cf3  mov     edx, [rbp+arg_28]; unsigned int
0x140024cf6  mov     [rax+8], r15
0x140024cfa  mov     r15b, [rbp+arg_40]
0x140024d01  mov     [rax], r12
0x140024d04  mov     r9b, r15b; unsigned __int8
0x140024d07  mov     rax, [rbp+arg_20]
0x140024d0b  mov     [rbx+18h], rsi
0x140024d0f  mov     rsi, [rbp+arg_48]
0x140024d16  mov     [rbx+10h], rax
0x140024d1a  movzx   eax, [rbp+arg_50]
0x140024d21  mov     [rsp+60h+var_30], 0; bool
0x140024d26  mov     qword ptr [rbx+20h], 0
0x140024d2e  mov     [rsp+60h+var_38], rsi; char *
0x140024d33  mov     [rbx+48h], eax
0x140024d36  mov     qword ptr [rbx+28h], 0
0x140024d3e  mov     qword ptr [rbx+30h], 0
0x140024d46  mov     qword ptr [rbx+38h], 0
0x140024d4e  mov     dword ptr [rbx+40h], 0
0x140024d55  mov     byte ptr [rbx+44h], 0
0x140024d59  mov     dword ptr [rsp+60h+var_40], edi; unsigned int
0x140024d5d  call    ?ResetBuffer@UfsEnumContext@UnionFs@@QEAAJKW4_FILE_INFORMATION_CLASS@@EKAEAVStackEventTracer@2@_N@Z; UnionFs::UfsEnumContext::ResetBuffer(ulong,_FILE_INFORMATION_CLASS,uchar,ulong,UnionFs::StackEventTracer &,bool)
0x140024d62  mov     edi, eax
0x140024d64  test    eax, eax
0x140024d66  jns     short loc_140024DB9
0x140024d68  lea     rax, aPushResettingB; "PUSH: Resetting buffer"
0x140024d6f  mov     r8, 1D30004003Ah; struct UnionFs::StackEventTracer *
0x140024d79  lea     r9, aUnionfsUfsenum; "UnionFs::UfsEnumContext::AllocAndInit"
0x140024d80  mov     [rsp+60h+var_40], rax; char *
0x140024d85  mov     rdx, rsi; int
0x140024d88  mov     ecx, edi; this
0x140024d8a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140024d8f  mov     rcx, rbx; this
0x140024d92  call    ??1UfsEnumContext@UnionFs@@QEAA@XZ; UnionFs::UfsEnumContext::~UfsEnumContext(void)
0x140024d97  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140024d9e  mov     rdx, rbx; Entry
0x140024da1  add     rcx, 4A0h; Lookaside
0x140024da8  call    cs:__imp_ExFreeToLookasideListEx
0x140024daf  nop     dword ptr [rax+rax+00h]
0x140024db4  jmp     loc_140024F40
0x140024db9  mov     eax, [r14+58h]
0x140024dbd  mov     [rbp+var_20], rbx
0x140024dc1  test    al, 10h
0x140024dc3  jz      short loc_140024E38
0x140024dc5  test    r15b, 1
0x140024dc9  jnz     short loc_140024E38
0x140024dcb  mov     r9, [rbp+arg_38]; struct _UNICODE_STRING *
0x140024dcf  mov     r8, rsi; struct UnionFs::StackEventTracer *
0x140024dd2  mov     dl, r15b; unsigned __int8
0x140024dd5  mov     rcx, rbx; this
0x140024dd8  call    ?PrimeForEnumeration@UfsEnumContext@UnionFs@@QEBAJEAEAVStackEventTracer@2@PEBU_UNICODE_STRING@@@Z; UnionFs::UfsEnumContext::PrimeForEnumeration(uchar,UnionFs::StackEventTracer &,_UNICODE_STRING const *)
0x140024ddd  mov     edi, eax
0x140024ddf  test    eax, eax
0x140024de1  jns     short loc_140024E34
0x140024de3  lea     rax, aPushErrorPrimi; "PUSH: Error priming handle for resumed "...
0x140024dea  mov     r8, 0C9000A0AA5h; struct UnionFs::StackEventTracer *
0x140024df4  lea     r9, aUnionfsUfsstre_24; "UnionFs::UfsStreamHandleCtx::AddSubCont"...
0x140024dfb  mov     [rsp+60h+var_40], rax; char *
0x140024e00  mov     rdx, rsi; int
0x140024e03  mov     ecx, edi; this
0x140024e05  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140024e0a  mov     rcx, rbx; this
0x140024e0d  call    ??1UfsEnumContext@UnionFs@@QEAA@XZ; UnionFs::UfsEnumContext::~UfsEnumContext(void)
0x140024e12  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140024e19  mov     rdx, rbx; Entry
0x140024e1c  add     rcx, 4A0h; Lookaside
0x140024e23  call    cs:__imp_ExFreeToLookasideListEx
0x140024e2a  nop     dword ptr [rax+rax+00h]
0x140024e2f  jmp     loc_140024F67
0x140024e34  or      dword ptr [rbx+48h], 2
0x140024e38  lea     rdi, [r14+90h]
0x140024e3f  mov     rax, [rdi+8]
0x140024e43  cmp     rax, [rdi+10h]
0x140024e47  jz      short loc_140024E50
0x140024e49  xor     esi, esi
0x140024e4b  mov     [rax], rbx
0x140024e4e  jmp     short loc_140024E93
0x140024e50  mov     r14, [rdi]
0x140024e53  mov     rcx, rdi
0x140024e56  call    ?_Grow@?$vector@V?$unique_ptr@VUfsEnumContext@UnionFs@@U?$default_delete@VUfsEnumContext@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsEnumContext@UnionFs@@U?$default_delete@VUfsEnumContext@UnionFs@@@utl@@@utl@@@2@@utl@@AEAA_NXZ; utl::vector<utl::unique_ptr<UnionFs::UfsEnumContext,utl::default_delete<UnionFs::UfsEnumContext>>,utl::allocator<utl::unique_ptr<UnionFs::UfsEnumContext,utl::default_delete<UnionFs::UfsEnumContext>>>>::_Grow(void)
0x140024e5b  test    al, al
0x140024e5d  jz      short loc_140024ED7
0x140024e5f  mov     r8, [rdi+8]
0x140024e63  lea     rcx, [rbp+var_20]
0x140024e67  mov     rdx, [rdi]
0x140024e6a  mov     rax, r8
0x140024e6d  sub     rax, rdx
0x140024e70  sub     rcx, r14
0x140024e73  cmp     rcx, rax
0x140024e76  jnb     short loc_140024E81
0x140024e78  lea     rax, [rcx+rdx]
0x140024e7c  mov     rbx, [rax]
0x140024e7f  jmp     short loc_140024E85
0x140024e81  lea     rax, [rbp+var_20]
0x140024e85  mov     qword ptr [rax], 0
0x140024e8c  mov     rsi, [rbp+var_20]
0x140024e90  mov     [r8], rbx
0x140024e93  add     qword ptr [rdi+8], 8
0x140024e98  test    rsi, rsi
0x140024e9b  jz      short loc_140024EC2
0x140024e9d  mov     rcx, rsi; this
0x140024ea0  call    ??1UfsEnumContext@UnionFs@@QEAA@XZ; UnionFs::UfsEnumContext::~UfsEnumContext(void)
0x140024ea5  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140024eac  mov     rdx, rsi; Entry
0x140024eaf  add     rcx, 4A0h; Lookaside
0x140024eb6  call    cs:__imp_ExFreeToLookasideListEx
0x140024ebd  nop     dword ptr [rax+rax+00h]
0x140024ec2  mov     rcx, [rbp+var_10]; this
0x140024ec6  test    rcx, rcx
0x140024ec9  jz      short loc_140024ED0
0x140024ecb  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140024ed0  xor     eax, eax
0x140024ed2  jmp     loc_140024F77
0x140024ed7  lea     rax, aOriginStoringS; "ORIGIN: Storing sub-context"
0x140024ede  mov     edi, 0C000009Ah
0x140024ee3  mov     ecx, edi; this
0x140024ee5  mov     [rsp+60h+var_40], rax; char *
0x140024eea  lea     r9, aUnionfsUfsstre_24; "UnionFs::UfsStreamHandleCtx::AddSubCont"...
0x140024ef1  mov     r8, 1D1000A0AAFh; struct UnionFs::StackEventTracer *
0x140024efb  mov     rdx, rsi; int
0x140024efe  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140024f03  test    rbx, rbx
0x140024f06  jz      short loc_140024F67
0x140024f08  jmp     loc_140024E0A
0x140024f0d  mov     rsi, [rbp+arg_48]
0x140024f14  lea     rax, aOriginAllocati_28; "ORIGIN: Allocating UfsEnumContext"
0x140024f1b  mov     edi, 0C000009Ah
0x140024f20  mov     [rsp+60h+var_40], rax; char *
0x140024f25  mov     rdx, rsi; int
0x140024f28  lea     r9, aUnionfsUfsenum; "UnionFs::UfsEnumContext::AllocAndInit"
0x140024f2f  mov     ecx, edi; this
0x140024f31  mov     r8, 1D000040030h; struct UnionFs::StackEventTracer *
0x140024f3b  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140024f40  lea     rax, aPushUfsenumcon; "PUSH: UfsEnumContext::AllocAndInit"
0x140024f47  mov     r8, 1CC000A0A98h; struct UnionFs::StackEventTracer *
0x140024f51  lea     r9, aUnionfsUfsstre_24; "UnionFs::UfsStreamHandleCtx::AddSubCont"...
0x140024f58  mov     [rsp+60h+var_40], rax; char *
0x140024f5d  mov     rdx, rsi; int
0x140024f60  mov     ecx, edi; this
0x140024f62  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140024f67  mov     rcx, [rbp+var_10]; this
0x140024f6b  test    rcx, rcx
0x140024f6e  jz      short loc_140024F75
0x140024f70  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140024f75  mov     eax, edi
0x140024f77  add     rsp, 60h
0x140024f7b  pop     r15
0x140024f7d  pop     r14
0x140024f7f  pop     r12
0x140024f81  pop     rdi
0x140024f82  pop     rsi
0x140024f83  pop     rbx
0x140024f84  pop     rbp
0x140024f85  retn
```
