# UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone(utl::shared_ptr<UnionFs::UfsUnionCtx> &&,UnionFs::UfsPathName const &,UnionFs::TombstoneState,utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &,UnionFs::UfsPathName const *,bool)

- ea: `0x140041040`
- end: `0x140041300`
- name: `?AllocAndInitSharedForTombstone@UfsPathCachePayload@UnionFs@@SAJ$$QEAV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEBVUfsPathName@2@W4TombstoneState@2@AEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@4@AEAVStackEventTracer@2@PEBV52@_N@Z`
- size: `704`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14005b4d0`
- `0x140061880`

## callees

- `0x14000f7fc`
- `0x140040e6c`
- `0x140041040`
- `0x140044748`
- `0x140056ac4`
- `0x140056afc`
- `0x140079c48`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400411bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004124e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400411bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004124e`

## string_xrefs

- `0x1400410b5`: `UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone`
- `0x14004111c`: `UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone`
- `0x14004117d`: `UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone`
- `0x1400412ad`: `UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone`
- `0x1400410dd`: `Renamed tombstone without OriginalPath`
- `0x140041176`: `PUSH: Getting copy of Path`
- `0x1400412a6`: `PUSH: Making copy of original path`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone(
        __int64 *a1,
        const UNICODE_STRING *a2,
        __int16 a3,
        utl::_RefCountBase **a4,
        __int64 a5,
        PCUNICODE_STRING SourceString)
{
  utl::_RefCountBase *v7; // rcx
  unsigned int inited; // ebx
  int v13; // esi
  struct _UNICODE_STRING *v14; // rdx
  struct _UNICODE_STRING *v15; // rbx
  utl::_RefCountBase *v16; // rbx
  __int64 v17; // rax
  struct _UNICODE_STRING *v18; // rdx
  utl::_RefCountBase *v19; // rcx
  __int64 v20; // rsi
  utl::_RefCountBase *v21; // rcx
  utl::_RefCountBase *v22; // rax
  const char *v23; // [rsp+28h] [rbp-30h]
  utl::_RefCountBase *v24[2]; // [rsp+30h] [rbp-28h] BYREF
  PVOID P; // [rsp+78h] [rbp+20h] BYREF

  *a4 = 0;
  v7 = a4[1];
  a4[1] = 0;
  if ( v7 )
    utl::_RefCountBase::_DecStrong(v7);
  if ( (unsigned __int16)(a3 - 2) > 1u )
  {
    if ( a3 != 4 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Unexpected tombstone type");
      inited = -1058209788;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0ED0004LL,
        a5,
        (struct UnionFs::StackEventTracer *)0x6F0012011ELL,
        (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone",
        "ORIGIN: Unexpected tombstone type",
        v23);
      return inited;
    }
    if ( !SourceString )
      MicrosoftTelemetryAssertTriggeredMsgKM("Renamed tombstone without OriginalPath");
  }
  *(_OWORD *)v24 = 0;
  inited = UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty(v24, a5, 0);
  if ( (inited & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)inited,
      a5,
      (struct UnionFs::StackEventTracer *)0x2C10012012ALL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone",
      "PUSH: Allocating tombstone payload",
      v23);
    if ( v24[1] )
      utl::_RefCountBase::_DecStrong(v24[1]);
    return inited;
  }
  P = 0;
  v13 = UnionFs::UfsPathName::Copy(a2, (__int64 *)&P, a5);
  if ( v13 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v13,
      a5,
      (struct UnionFs::StackEventTracer *)0x2E30012012FLL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone",
      "PUSH: Getting copy of Path",
      v23);
    v15 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v15, v14);
      ExFreePoolWithTag(v15, 0);
    }
    goto LABEL_17;
  }
  v16 = v24[0];
  v17 = *a1;
  v18 = (struct _UNICODE_STRING *)a1[1];
  *a1 = 0;
  a1[1] = 0;
  v19 = (utl::_RefCountBase *)*((_QWORD *)v16 + 24);
  *((_QWORD *)v16 + 23) = v17;
  *((_QWORD *)v16 + 24) = v18;
  if ( v19 )
    utl::_RefCountBase::_DecStrong(v19);
  v20 = *((_QWORD *)v16 + 25);
  *((_QWORD *)v16 + 25) = P;
  if ( v20 )
  {
    if ( !*(_BYTE *)(v20 + 16) )
      *(_OWORD *)v20 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v20, v18);
    ExFreePoolWithTag((PVOID)v20, 0);
  }
  *((_WORD *)v16 + 80) = a3;
  _mm_mfence();
  *((_BYTE *)v16 + 164) = 0;
  _mm_mfence();
  if ( SourceString )
  {
    v13 = UnionFs::UfsPathName::Copy(SourceString, (__int64 *)v16 + 26, a5);
    if ( v13 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v13,
        a5,
        (struct UnionFs::StackEventTracer *)0x35D0012013BLL,
        (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone",
        "PUSH: Making copy of original path",
        v23);
LABEL_17:
      if ( v24[1] )
        utl::_RefCountBase::_DecStrong(v24[1]);
      return (unsigned int)v13;
    }
  }
  v21 = a4[1];
  v22 = v24[1];
  *a4 = v16;
  a4[1] = v22;
  if ( v21 )
    utl::_RefCountBase::_DecStrong(v21);
  return 0;
}

```

## disassembly

```asm
0x140041040  mov     [rsp+arg_0], rbx
0x140041045  mov     [rsp+arg_8], rsi
0x14004104a  push    rdi
0x14004104b  push    r12
0x14004104d  push    r14
0x14004104f  sub     rsp, 40h
0x140041053  mov     r12, rcx
0x140041056  mov     qword ptr [r9], 0
0x14004105d  mov     rcx, [r9+8]; this
0x140041061  mov     rdi, r9
0x140041064  mov     qword ptr [r9+8], 0
0x14004106c  movzx   r14d, r8w
0x140041070  mov     rsi, rdx
0x140041073  test    rcx, rcx
0x140041076  jz      short loc_14004107D
0x140041078  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004107d  lea     eax, [r14-2]
0x140041081  cmp     ax, 1
0x140041085  jbe     short loc_1400410E9
0x140041087  cmp     r14w, 4
0x14004108c  jz      short loc_1400410D2
0x14004108e  lea     rcx, aUnexpectedTomb; "Unexpected tombstone type"
0x140041095  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14004109a  mov     rdx, [rsp+58h+arg_20]; int
0x1400410a2  lea     rax, aOriginUnexpect_3; "ORIGIN: Unexpected tombstone type"
0x1400410a9  mov     ebx, 0C0ED0004h
0x1400410ae  mov     [rsp+58h+var_38], rax; char *
0x1400410b3  mov     ecx, ebx; this
0x1400410b5  lea     r9, aUnionfsUfspath_6; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x1400410bc  mov     r8, 6F0012011Eh; struct UnionFs::StackEventTracer *
0x1400410c6  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400410cb  mov     eax, ebx
0x1400410cd  jmp     loc_1400412EB
0x1400410d2  cmp     [rsp+58h+SourceString], 0
0x1400410db  jnz     short loc_1400410E9
0x1400410dd  lea     rcx, aRenamedTombsto; "Renamed tombstone without OriginalPath"
0x1400410e4  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400410e9  mov     rdx, [rsp+58h+arg_20]
0x1400410f1  lea     rcx, [rsp+58h+var_28]
0x1400410f6  xorps   xmm0, xmm0
0x1400410f9  xor     r8d, r8d
0x1400410fc  movdqu  xmmword ptr [rsp+58h+var_28], xmm0
0x140041102  call    ?AllocAndInitSharedEmpty@UfsPathCachePayload@UnionFs@@SAJAEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty(utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &,bool)
0x140041107  mov     ebx, eax
0x140041109  test    eax, eax
0x14004110b  jns     short loc_14004114A
0x14004110d  mov     rdx, [rsp+58h+arg_20]; int
0x140041115  lea     rax, aPushAllocating_33; "PUSH: Allocating tombstone payload"
0x14004111c  lea     r9, aUnionfsUfspath_6; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x140041123  mov     [rsp+58h+var_38], rax; char *
0x140041128  mov     r8, 2C10012012Ah; struct UnionFs::StackEventTracer *
0x140041132  mov     ecx, ebx; this
0x140041134  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140041139  mov     rcx, [rsp+58h+var_28+8]; this
0x14004113e  test    rcx, rcx
0x140041141  jz      short loc_1400410CB
0x140041143  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140041148  jmp     short loc_1400410CB
0x14004114a  mov     r8, [rsp+58h+arg_20]
0x140041152  lea     rdx, [rsp+58h+P]
0x140041157  mov     rcx, rsi; SourceString
0x14004115a  mov     [rsp+58h+P], 0
0x140041163  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140041168  mov     esi, eax
0x14004116a  test    eax, eax
0x14004116c  jns     short loc_1400411DF
0x14004116e  mov     rdx, [rsp+58h+arg_20]; int
0x140041176  lea     rax, aPushGettingCop_0; "PUSH: Getting copy of Path"
0x14004117d  lea     r9, aUnionfsUfspath_6; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x140041184  mov     [rsp+58h+var_38], rax; char *
0x140041189  mov     r8, 2E30012012Fh; struct UnionFs::StackEventTracer *
0x140041193  mov     ecx, esi; this
0x140041195  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004119a  mov     rbx, [rsp+58h+P]
0x14004119f  test    rbx, rbx
0x1400411a2  jz      short loc_1400411C9
0x1400411a4  cmp     byte ptr [rbx+10h], 0
0x1400411a8  jnz     short loc_1400411B0
0x1400411aa  xorps   xmm0, xmm0
0x1400411ad  movups  xmmword ptr [rbx], xmm0
0x1400411b0  mov     rcx, rbx; UnicodeString
0x1400411b3  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400411b8  xor     edx, edx; Tag
0x1400411ba  mov     rcx, rbx; P
0x1400411bd  call    cs:__imp_ExFreePoolWithTag
0x1400411c4  nop     dword ptr [rax+rax+00h]
0x1400411c9  mov     rcx, [rsp+58h+var_28+8]; this
0x1400411ce  test    rcx, rcx
0x1400411d1  jz      short loc_1400411D8
0x1400411d3  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400411d8  mov     eax, esi
0x1400411da  jmp     loc_1400412EB
0x1400411df  mov     rbx, [rsp+58h+var_28]
0x1400411e4  mov     rax, [r12]
0x1400411e8  mov     rdx, [r12+8]
0x1400411ed  mov     qword ptr [r12], 0
0x1400411f5  mov     qword ptr [r12+8], 0
0x1400411fe  mov     rcx, [rbx+0C0h]; this
0x140041205  mov     [rbx+0B8h], rax
0x14004120c  mov     [rbx+0C0h], rdx
0x140041213  test    rcx, rcx
0x140041216  jz      short loc_14004121D
0x140041218  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004121d  mov     rsi, [rbx+0C8h]
0x140041224  mov     rax, [rsp+58h+P]
0x140041229  mov     [rbx+0C8h], rax
0x140041230  test    rsi, rsi
0x140041233  jz      short loc_14004125A
0x140041235  cmp     byte ptr [rsi+10h], 0
0x140041239  jnz     short loc_140041241
0x14004123b  xorps   xmm0, xmm0
0x14004123e  movups  xmmword ptr [rsi], xmm0
0x140041241  mov     rcx, rsi; UnicodeString
0x140041244  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140041249  xor     edx, edx; Tag
0x14004124b  mov     rcx, rsi; P
0x14004124e  call    cs:__imp_ExFreePoolWithTag
0x140041255  nop     dword ptr [rax+rax+00h]
0x14004125a  nop
0x14004125b  mov     [rbx+0A0h], r14w
0x140041263  mfence
0x140041266  nop
0x140041267  mov     byte ptr [rbx+0A4h], 0
0x14004126e  mfence
0x140041271  cmp     [rsp+58h+SourceString], 0
0x14004127a  jz      short loc_1400412CF
0x14004127c  mov     r8, [rsp+58h+arg_20]
0x140041284  lea     rdx, [rbx+0D0h]
0x14004128b  mov     rcx, [rsp+58h+SourceString]; SourceString
0x140041293  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140041298  mov     esi, eax
0x14004129a  test    eax, eax
0x14004129c  jns     short loc_1400412CF
0x14004129e  mov     rdx, [rsp+58h+arg_20]; int
0x1400412a6  lea     rax, aPushMakingCopy; "PUSH: Making copy of original path"
0x1400412ad  lea     r9, aUnionfsUfspath_6; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x1400412b4  mov     [rsp+58h+var_38], rax; char *
0x1400412b9  mov     r8, 35D0012013Bh; struct UnionFs::StackEventTracer *
0x1400412c3  mov     ecx, esi; this
0x1400412c5  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400412ca  jmp     loc_1400411C9
0x1400412cf  mov     rcx, [rdi+8]; this
0x1400412d3  mov     rax, [rsp+58h+var_28+8]
0x1400412d8  mov     [rdi], rbx
0x1400412db  mov     [rdi+8], rax
0x1400412df  test    rcx, rcx
0x1400412e2  jz      short loc_1400412E9
0x1400412e4  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400412e9  xor     eax, eax
0x1400412eb  mov     rbx, [rsp+58h+arg_0]
0x1400412f0  mov     rsi, [rsp+58h+arg_8]
0x1400412f5  add     rsp, 40h
0x1400412f9  pop     r14
0x1400412fb  pop     r12
0x1400412fd  pop     rdi
0x1400412fe  retn
```
