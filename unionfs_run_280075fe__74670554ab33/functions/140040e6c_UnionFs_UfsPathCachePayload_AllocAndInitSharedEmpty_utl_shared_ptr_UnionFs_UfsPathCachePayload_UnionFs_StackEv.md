# UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty(utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &,bool)

- ea: `0x140040e6c`
- end: `0x140041039`
- name: `?AllocAndInitSharedEmpty@UfsPathCachePayload@UnionFs@@SAJAEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAVStackEventTracer@2@_N@Z`
- size: `461`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14002e3c8`
- `0x140041040`
- `0x14005e200`
- `0x14007090c`

## callees

- `0x14000f7fc`
- `0x14003f4f8`
- `0x14003f7b0`
- `0x14003fd70`
- `0x14003fe98`
- `0x140040e6c`
- `0x140056ac4`
- `0x140056afc`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040f0a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040fd0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140041017`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040f0a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040fd0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140041017`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140040f33`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140040f33`

## string_xrefs

- `0x140040ed2`: `UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty`
- `0x140040f8b`: `UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty(_QWORD *a1, __int64 a2, char a3)
{
  utl::_RefCountBase *v4; // rcx
  int v7; // ebx
  PVOID v8; // rdi
  PVOID v10; // rax
  __int64 v11; // r8
  UnionFs::UfsPathCachePayloadNP *v12; // rbx
  utl::_RefCountBase *v13; // rcx
  const char *v14; // [rsp+28h] [rbp-18h]
  utl::_RefCountBase *v15[2]; // [rsp+30h] [rbp-10h] BYREF
  PVOID Entry; // [rsp+60h] [rbp+20h] BYREF

  *a1 = 0;
  v4 = (utl::_RefCountBase *)a1[1];
  a1[1] = 0;
  if ( v4 )
    utl::_RefCountBase::_DecStrong(v4);
  Entry = 0;
  v7 = UnionFs::UfsPathCachePayloadNP::AllocAndInit(&Entry, a2);
  if ( v7 >= 0 )
  {
    *(_OWORD *)v15 = 0;
    v10 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1664));
    if ( v10 )
    {
      v12 = 0;
      LOBYTE(v11) = a3;
      v10 = (PVOID)UnionFs::UfsPathCachePayload::UfsPathCachePayload(v10, &Entry, v11);
    }
    else
    {
      v12 = (UnionFs::UfsPathCachePayloadNP *)Entry;
    }
    utl::shared_ptr<UnionFs::UfsPathCachePayload>::reset<UnionFs::UfsPathCachePayload,0>(v15, v10);
    if ( v15[0] )
    {
      v13 = (utl::_RefCountBase *)a1[1];
      *a1 = v15[0];
      a1[1] = v15[1];
      if ( v13 )
        utl::_RefCountBase::_DecStrong(v13);
      if ( v12 )
      {
        UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v12);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v12);
      }
      return 0;
    }
    else
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        a2,
        (struct UnionFs::StackEventTracer *)0x1FC0012015BLL,
        (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty",
        "ORIGIN: Allocating tombstone payload",
        v14);
      if ( v15[1] )
        utl::_RefCountBase::_DecStrong(v15[1]);
      if ( v12 )
      {
        UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v12);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v12);
      }
      return 3221225626LL;
    }
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v7,
      a2,
      (struct UnionFs::StackEventTracer *)0x11B00120151LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty",
      "PUSH: Creating NP ctx",
      v14);
    v8 = Entry;
    if ( Entry )
    {
      UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP((UnionFs::UfsPathCachePayloadNP *)Entry);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v8);
    }
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x140040e6c  mov     [rsp-18h+arg_8], rbx
0x140040e71  mov     [rsp-18h+arg_10], rsi
0x140040e76  push    rbp
0x140040e77  push    rdi
0x140040e78  push    r14
0x140040e7a  mov     rbp, rsp
0x140040e7d  sub     rsp, 40h
0x140040e81  mov     rdi, rcx
0x140040e84  mov     qword ptr [rcx], 0
0x140040e8b  mov     rcx, [rcx+8]; this
0x140040e8f  mov     r14b, r8b
0x140040e92  mov     rsi, rdx
0x140040e95  mov     qword ptr [rdi+8], 0
0x140040e9d  test    rcx, rcx
0x140040ea0  jz      short loc_140040EA7
0x140040ea2  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140040ea7  mov     rdx, rsi
0x140040eaa  mov     [rbp+Entry], 0
0x140040eb2  lea     rcx, [rbp+Entry]
0x140040eb6  call    ?AllocAndInit@UfsPathCachePayloadNP@UnionFs@@SAJAEAV?$unique_ptr@VUfsPathCachePayloadNP@UnionFs@@U?$default_delete@VUfsPathCachePayloadNP@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayloadNP::AllocAndInit(utl::unique_ptr<UnionFs::UfsPathCachePayloadNP,utl::default_delete<UnionFs::UfsPathCachePayloadNP>> &,UnionFs::StackEventTracer &)
0x140040ebb  mov     ebx, eax
0x140040ebd  test    eax, eax
0x140040ebf  jns     short loc_140040F1D
0x140040ec1  lea     rax, aPushCreatingNp; "PUSH: Creating NP ctx"
0x140040ec8  mov     r8, 11B00120151h; struct UnionFs::StackEventTracer *
0x140040ed2  lea     r9, aUnionfsUfspath_54; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x140040ed9  mov     [rsp+40h+var_20], rax; char *
0x140040ede  mov     rdx, rsi; int
0x140040ee1  mov     ecx, ebx; this
0x140040ee3  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140040ee8  mov     rdi, [rbp+Entry]
0x140040eec  test    rdi, rdi
0x140040eef  jz      short loc_140040F16
0x140040ef1  mov     rcx, rdi; this
0x140040ef4  call    ??1UfsPathCachePayloadNP@UnionFs@@QEAA@XZ; UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(void)
0x140040ef9  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140040f00  mov     rdx, rdi; Entry
0x140040f03  add     rcx, 620h; Lookaside
0x140040f0a  call    cs:__imp_ExFreeToLookasideListEx
0x140040f11  nop     dword ptr [rax+rax+00h]
0x140040f16  mov     eax, ebx
0x140040f18  jmp     loc_140041025
0x140040f1d  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140040f24  xorps   xmm0, xmm0
0x140040f27  add     rcx, 680h; Lookaside
0x140040f2e  movdqu  xmmword ptr [rbp+var_10], xmm0
0x140040f33  call    cs:__imp_ExAllocateFromLookasideListEx
0x140040f3a  nop     dword ptr [rax+rax+00h]
0x140040f3f  test    rax, rax
0x140040f42  jz      short loc_140040F5F
0x140040f44  mov     rcx, [rbp+Entry]
0x140040f48  lea     rdx, [rbp+Entry]
0x140040f4c  mov     [rbp+Entry], rcx
0x140040f50  xor     ebx, ebx
0x140040f52  mov     rcx, rax
0x140040f55  mov     r8b, r14b
0x140040f58  call    ??0UfsPathCachePayload@UnionFs@@AEAA@V?$unique_ptr@$$CBVUfsPathCachePayloadNP@UnionFs@@U?$default_delete@$$CBVUfsPathCachePayloadNP@UnionFs@@@utl@@@utl@@_N@Z; UnionFs::UfsPathCachePayload::UfsPathCachePayload(utl::unique_ptr<UnionFs::UfsPathCachePayloadNP const,utl::default_delete<UnionFs::UfsPathCachePayloadNP const>>,bool)
0x140040f5d  jmp     short loc_140040F63
0x140040f5f  mov     rbx, [rbp+Entry]
0x140040f63  mov     rdx, rax
0x140040f66  lea     rcx, [rbp+var_10]
0x140040f6a  call    ??$reset@VUfsPathCachePayload@UnionFs@@$0A@@?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@QEAA_NPEAVUfsPathCachePayload@UnionFs@@@Z; utl::shared_ptr<UnionFs::UfsPathCachePayload>::reset<UnionFs::UfsPathCachePayload,0>(UnionFs::UfsPathCachePayload *)
0x140040f6f  mov     rax, [rbp+var_10]
0x140040f73  test    rax, rax
0x140040f76  jnz     short loc_140040FE0
0x140040f78  lea     rax, aOriginAllocati_11; "ORIGIN: Allocating tombstone payload"
0x140040f7f  mov     edi, 0C000009Ah
0x140040f84  mov     ecx, edi; this
0x140040f86  mov     [rsp+40h+var_20], rax; char *
0x140040f8b  lea     r9, aUnionfsUfspath_54; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x140040f92  mov     r8, 1FC0012015Bh; struct UnionFs::StackEventTracer *
0x140040f9c  mov     rdx, rsi; int
0x140040f9f  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140040fa4  mov     rcx, [rbp+var_10+8]; this
0x140040fa8  test    rcx, rcx
0x140040fab  jz      short loc_140040FB2
0x140040fad  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140040fb2  test    rbx, rbx
0x140040fb5  jz      short loc_140040FDC
0x140040fb7  mov     rcx, rbx; this
0x140040fba  call    ??1UfsPathCachePayloadNP@UnionFs@@QEAA@XZ; UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(void)
0x140040fbf  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140040fc6  mov     rdx, rbx; Entry
0x140040fc9  add     rcx, 620h; Lookaside
0x140040fd0  call    cs:__imp_ExFreeToLookasideListEx
0x140040fd7  nop     dword ptr [rax+rax+00h]
0x140040fdc  mov     eax, edi
0x140040fde  jmp     short loc_140041025
0x140040fe0  mov     rcx, [rdi+8]; this
0x140040fe4  mov     [rdi], rax
0x140040fe7  mov     rax, [rbp+var_10+8]
0x140040feb  mov     [rdi+8], rax
0x140040fef  test    rcx, rcx
0x140040ff2  jz      short loc_140040FF9
0x140040ff4  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140040ff9  test    rbx, rbx
0x140040ffc  jz      short loc_140041023
0x140040ffe  mov     rcx, rbx; this
0x140041001  call    ??1UfsPathCachePayloadNP@UnionFs@@QEAA@XZ; UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(void)
0x140041006  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14004100d  mov     rdx, rbx; Entry
0x140041010  add     rcx, 620h; Lookaside
0x140041017  call    cs:__imp_ExFreeToLookasideListEx
0x14004101e  nop     dword ptr [rax+rax+00h]
0x140041023  xor     eax, eax
0x140041025  mov     rbx, [rsp+40h+arg_8]
0x14004102a  mov     rsi, [rsp+40h+arg_10]
0x14004102f  add     rsp, 40h
0x140041033  pop     r14
0x140041035  pop     rdi
0x140041036  pop     rbp
0x140041037  retn
```
