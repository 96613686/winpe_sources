# UnionFs::Utils::RequestOplockCompletionWorkItemRoutine(_FLT_GENERIC_WORKITEM *,void *,void *)

- ea: `0x1400769b0`
- end: `0x140076d9b`
- name: `?RequestOplockCompletionWorkItemRoutine@Utils@UnionFs@@YAXPEAU_FLT_GENERIC_WORKITEM@@PEAX1@Z`
- size: `1003`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400055d0`
- `0x140006168`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x1400579a4`
- `0x140076660`
- `0x1400769b0`
- `0x1400799a4`
- `0x140079ab4`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x140076c48`
- `ntoskrnl!KeClearEvent` at `0x140076c48`
- `ntoskrnl!KeInitializeEvent` at `0x140076bb6`
- `ntoskrnl!KeInitializeEvent` at `0x140076bb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076ae1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076d38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076ae1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076d38`
- `ntoskrnl!KeWaitForSingleObject` at `0x140076c37`
- `ntoskrnl!KeWaitForSingleObject` at `0x140076c37`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140076d67`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140076d67`
- `ntoskrnl!ExReleaseFastMutex` at `0x140076a9f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140076b91`
- `ntoskrnl!ExReleaseFastMutex` at `0x140076a9f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140076b91`
- `ntoskrnl!ExReleaseResourceLite` at `0x140076c09`
- `ntoskrnl!ExReleaseResourceLite` at `0x140076d1b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140076c09`
- `ntoskrnl!ExReleaseResourceLite` at `0x140076d1b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140076c15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140076d27`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140076c15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140076d27`

## string_xrefs

- `0x140076a27`: `UnionFs::Utils::RequestOplockCompletionWorkItemRoutine`
- `0x140076b28`: `UnionFs::Utils::RequestOplockCompletionWorkItemRoutine`
- `0x140076cd5`: `UnionFs::Utils::RequestOplockCompletionWorkItemRoutine`
- `0x140076d00`: `UnionFs::Utils::RequestOplockCompletionWorkItemRoutine`

## pseudocode

```c
void __fastcall UnionFs::Utils::RequestOplockCompletionWorkItemRoutine(
        PFLT_GENERIC_WORKITEM FltWorkItem,
        PVOID FltObject,
        PVOID Context)
{
  __int64 v4; // rcx
  int v5; // edx
  __int64 v6; // rsi
  __int64 v7; // rbx
  int v8; // eax
  struct _ERESOURCE *v9; // rdi
  unsigned int v10; // r14d
  struct _FAST_MUTEX *v11; // rcx
  PVOID v12; // rdx
  UnionFs *v13; // rcx
  unsigned int v14; // r14d
  struct _FAST_MUTEX *v15; // rcx
  int v16; // eax
  int v17; // eax
  PVOID v18; // rbx
  char *v19; // [rsp+28h] [rbp-D8h]
  char *v20; // [rsp+28h] [rbp-D8h]
  PFAST_MUTEX FastMutex; // [rsp+40h] [rbp-C0h] BYREF
  PVOID Entry; // [rsp+48h] [rbp-B8h] BYREF
  struct _KEVENT Event; // [rsp+50h] [rbp-B0h] BYREF
  char v24[4]; // [rsp+68h] [rbp-98h] BYREF

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v24, 0x6F700212695uLL);
  Entry = Context;
  v4 = *((_QWORD *)Context + 5);
  v5 = *((_DWORD *)Context + 6);
  v6 = *(_QWORD *)(*(_QWORD *)Context + 24LL);
  v7 = *(_QWORD *)(*(_QWORD *)(v4 + 16) + 48LL);
  if ( !v5 )
    goto LABEL_17;
  if ( v5 != 1 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000000DLL,
      (int)v24,
      (struct UnionFs::StackEventTracer *)0x6FD00212733LL,
      (unsigned __int64)"UnionFs::Utils::RequestOplockCompletionWorkItemRoutine",
      "ORIGIN: Invalid oplock operation in callback",
      v19);
    goto LABEL_19;
  }
  v8 = *(_DWORD *)(v4 + 24);
  if ( v8 == -2147483602 )
  {
    FsFltWil::AcquireResourceShared(&FastMutex, *(_QWORD *)(v6 + 120) + 56LL);
    v9 = (struct _ERESOURCE *)FastMutex;
    v10 = *(_DWORD *)(v7 + 8);
    FsFltWil::AcquireFastMutex(&FastMutex, *(_QWORD *)(v6 + 120) + 216LL);
    v11 = FastMutex;
    if ( v10 <= *(_DWORD *)(v6 + 216) )
      *(_DWORD *)(v6 + 216) = v10;
    if ( v11 )
      ExReleaseFastMutex(v11);
LABEL_32:
    v17 = UnionFs::Utils::RequestOplock(
            *((PFLT_INSTANCE *)Entry + 1),
            *((PFILE_OBJECT *)Entry + 2),
            (__int64)&Entry,
            (int)v24);
    if ( v17 < 0 )
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v17,
        (int)v24,
        (struct UnionFs::StackEventTracer *)0x6D100212744LL,
        (unsigned __int64)"UnionFs::Utils::RequestOplockCompletionWorkItemRoutine",
        "PUSH: Acknowledging oplock break",
        v20);
LABEL_35:
    if ( v9 )
    {
      ExReleaseResourceLite(v9);
      KeLeaveCriticalRegion();
    }
LABEL_37:
    ExFreePoolWithTag((PVOID)v7, 0);
LABEL_38:
    v18 = Entry;
    if ( Entry )
    {
      UnionFs::Utils::RequestOplockContext::~RequestOplockContext((UnionFs::Utils::RequestOplockContext *)Entry);
      v12 = v18;
      goto LABEL_40;
    }
    goto LABEL_41;
  }
  if ( v8 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v8,
      (int)v24,
      (struct UnionFs::StackEventTracer *)0x6F8002126D5LL,
      (unsigned __int64)"UnionFs::Utils::RequestOplockCompletionWorkItemRoutine",
      "API: Oplock break acknowledgment failed",
      v19);
    goto LABEL_19;
  }
  if ( v8 || *(_QWORD *)(v4 + 32) )
  {
LABEL_17:
    v13 = (UnionFs *)*(unsigned int *)(v4 + 24);
    if ( (int)v13 >= 0 )
    {
      FsFltWil::AcquireResourceShared(&FastMutex, *(_QWORD *)(v6 + 120) + 56LL);
      v9 = (struct _ERESOURCE *)FastMutex;
      v14 = *(_DWORD *)(v7 + 8);
      FsFltWil::AcquireFastMutex(&FastMutex, *(_QWORD *)(v6 + 120) + 216LL);
      v15 = FastMutex;
      if ( v14 <= *(_DWORD *)(v6 + 216) )
        *(_DWORD *)(v6 + 216) = v14;
      if ( v15 )
        ExReleaseFastMutex(v15);
      memset(&Event, 0, sizeof(Event));
      KeInitializeEvent(&Event, NotificationEvent, 0);
      while ( 1 )
      {
        LODWORD(v19) = 0;
        v16 = ((__int64 (__fastcall *)(__int64, _QWORD, struct _KEVENT *, void *, _QWORD))UnionFs::Flt_CheckUpperOplock)(
                v6 + 88,
                *(unsigned int *)(v7 + 8),
                &Event,
                &lambda_d3744a3ec78c830341c2c93f7007b5ba_::_lambda_invoker_cdecl_,
                0);
        if ( v16 < 0 )
        {
          UnionFs::ProcessTraceStatusFromApi(
            (UnionFs *)(unsigned int)v16,
            (int)v24,
            (struct UnionFs::StackEventTracer *)0x6FC00212717LL,
            (unsigned __int64)"UnionFs::Utils::RequestOplockCompletionWorkItemRoutine",
            "API: Unexpected FltCheckUpperOplock failure",
            v19);
          goto LABEL_35;
        }
        if ( v16 != 259 )
          break;
        if ( v9 )
        {
          ExReleaseResourceLite(v9);
          KeLeaveCriticalRegion();
        }
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        KeClearEvent(&Event);
        FsFltWil::AcquireResourceShared(&FastMutex, *(_QWORD *)(v6 + 120) + 56LL);
        v9 = (struct _ERESOURCE *)FastMutex;
        FastMutex = 0;
      }
      if ( (*(_BYTE *)(v7 + 12) & 1) == 0 )
        goto LABEL_35;
      goto LABEL_32;
    }
    UnionFs::ProcessTraceStatusFromApi(
      v13,
      (int)v24,
      (struct UnionFs::StackEventTracer *)0x6F9002126F5LL,
      (unsigned __int64)"UnionFs::Utils::RequestOplockCompletionWorkItemRoutine",
      "API: Oplock request failed",
      v19);
LABEL_19:
    if ( !v7 )
      goto LABEL_38;
    goto LABEL_37;
  }
  if ( v7 )
  {
    ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(v4 + 16) + 48LL), 0);
    Context = Entry;
  }
  if ( Context )
  {
    UnionFs::Utils::RequestOplockContext::~RequestOplockContext((UnionFs::Utils::RequestOplockContext *)Context);
    v12 = Context;
LABEL_40:
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 27, v12);
  }
LABEL_41:
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v24);
}

```

## disassembly

```asm
0x1400769b0  push    rbp
0x1400769b2  push    rbx
0x1400769b3  push    rsi
0x1400769b4  push    rdi
0x1400769b5  push    r14
0x1400769b7  lea     rbp, [rsp-260h]
0x1400769bf  sub     rsp, 360h
0x1400769c6  mov     rax, cs:__security_cookie
0x1400769cd  xor     rax, rsp
0x1400769d0  mov     [rbp+280h+var_28], rax
0x1400769d7  mov     rdx, 6F700212695h; unsigned __int64
0x1400769e1  lea     rcx, [rsp+380h+var_318]; this
0x1400769e6  mov     rdi, r8
0x1400769e9  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x1400769ee  mov     [rsp+380h+Entry], rdi
0x1400769f3  mov     rcx, [rdi+28h]
0x1400769f7  mov     rax, [rdi]
0x1400769fa  mov     edx, [rdi+18h]
0x1400769fd  mov     rbx, [rcx+10h]
0x140076a01  mov     rsi, [rax+18h]
0x140076a05  mov     rbx, [rbx+30h]
0x140076a09  test    edx, edx
0x140076a0b  jz      loc_140076B0B
0x140076a11  cmp     edx, 1
0x140076a14  jz      short loc_140076A47
0x140076a16  lea     rax, aOriginInvalidO; "ORIGIN: Invalid oplock operation in cal"...
0x140076a1d  mov     r8, 6FD00212733h; struct UnionFs::StackEventTracer *
0x140076a27  lea     r9, aUnionfsUtilsRe_0; "UnionFs::Utils::RequestOplockCompletion"...
0x140076a2e  mov     [rsp+380h+Timeout], rax; char *
0x140076a33  lea     rdx, [rsp+380h+var_318]; int
0x140076a38  mov     ecx, 0C000000Dh; this
0x140076a3d  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076a42  jmp     loc_140076B39
0x140076a47  mov     eax, [rcx+18h]
0x140076a4a  cmp     eax, 8000002Eh
0x140076a4f  jnz     short loc_140076AB0
0x140076a51  mov     rdx, [rsi+78h]
0x140076a55  lea     rcx, [rsp+380h+FastMutex]
0x140076a5a  add     rdx, 38h ; '8'
0x140076a5e  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x140076a63  mov     rdx, [rsi+78h]
0x140076a67  lea     rcx, [rsp+380h+FastMutex]
0x140076a6c  mov     rdi, [rsp+380h+FastMutex]
0x140076a71  add     rdx, 0D8h
0x140076a78  mov     r14d, [rbx+8]
0x140076a7c  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140076a81  mov     rcx, [rsp+380h+FastMutex]; FastMutex
0x140076a86  cmp     r14d, [rsi+0D8h]
0x140076a8d  ja      short loc_140076A96
0x140076a8f  mov     [rsi+0D8h], r14d
0x140076a96  test    rcx, rcx
0x140076a99  jz      loc_140076C83
0x140076a9f  call    cs:__imp_ExReleaseFastMutex
0x140076aa6  nop     dword ptr [rax+rax+00h]
0x140076aab  jmp     loc_140076C83
0x140076ab0  test    eax, eax
0x140076ab2  jns     short loc_140076ACE
0x140076ab4  lea     rcx, aApiOplockBreak_1; "API: Oplock break acknowledgment failed"
0x140076abb  mov     r8, 6F8002126D5h
0x140076ac5  mov     [rsp+380h+Timeout], rcx
0x140076aca  mov     ecx, eax
0x140076acc  jmp     short loc_140076B28
0x140076ace  jnz     short loc_140076B0B
0x140076ad0  cmp     qword ptr [rcx+20h], 0
0x140076ad5  jnz     short loc_140076B0B
0x140076ad7  test    rbx, rbx
0x140076ada  jz      short loc_140076AF2
0x140076adc  xor     edx, edx; Tag
0x140076ade  mov     rcx, rbx; P
0x140076ae1  call    cs:__imp_ExFreePoolWithTag
0x140076ae8  nop     dword ptr [rax+rax+00h]
0x140076aed  mov     rdi, [rsp+380h+Entry]
0x140076af2  test    rdi, rdi
0x140076af5  jz      loc_140076D73
0x140076afb  mov     rcx, rdi; this
0x140076afe  call    ??1RequestOplockContext@Utils@UnionFs@@QEAA@XZ; UnionFs::Utils::RequestOplockContext::~RequestOplockContext(void)
0x140076b03  mov     rdx, rdi
0x140076b06  jmp     loc_140076D59
0x140076b0b  mov     ecx, [rcx+18h]; this
0x140076b0e  test    ecx, ecx
0x140076b10  jns     short loc_140076B47
0x140076b12  lea     rax, aApiOplockReque; "API: Oplock request failed"
0x140076b19  mov     r8, 6F9002126F5h; struct UnionFs::StackEventTracer *
0x140076b23  mov     [rsp+380h+Timeout], rax; char *
0x140076b28  lea     r9, aUnionfsUtilsRe_0; "UnionFs::Utils::RequestOplockCompletion"...
0x140076b2f  lea     rdx, [rsp+380h+var_318]; int
0x140076b34  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076b39  test    rbx, rbx
0x140076b3c  jz      loc_140076D44
0x140076b42  jmp     loc_140076D33
0x140076b47  mov     rdx, [rsi+78h]
0x140076b4b  lea     rcx, [rsp+380h+FastMutex]
0x140076b50  add     rdx, 38h ; '8'
0x140076b54  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x140076b59  mov     rdx, [rsi+78h]
0x140076b5d  lea     rcx, [rsp+380h+FastMutex]
0x140076b62  mov     rdi, [rsp+380h+FastMutex]
0x140076b67  add     rdx, 0D8h
0x140076b6e  mov     r14d, [rbx+8]
0x140076b72  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140076b77  mov     rcx, [rsp+380h+FastMutex]; FastMutex
0x140076b7c  cmp     r14d, [rsi+0D8h]
0x140076b83  ja      short loc_140076B8C
0x140076b85  mov     [rsi+0D8h], r14d
0x140076b8c  test    rcx, rcx
0x140076b8f  jz      short loc_140076B9D
0x140076b91  call    cs:__imp_ExReleaseFastMutex
0x140076b98  nop     dword ptr [rax+rax+00h]
0x140076b9d  xorps   xmm0, xmm0
0x140076ba0  lea     rcx, [rsp+380h+Event]; Event
0x140076ba5  xor     eax, eax
0x140076ba7  xor     r8d, r8d; State
0x140076baa  xor     edx, edx; Type
0x140076bac  mov     [rsp+380h+Event.Header.WaitListHead.Blink], rax
0x140076bb1  movups  xmmword ptr [rsp+380h+Event.Header], xmm0
0x140076bb6  call    cs:__imp_KeInitializeEvent
0x140076bbd  nop     dword ptr [rax+rax+00h]
0x140076bc2  mov     rax, cs:?Flt_CheckUpperOplock@UnionFs@@3P6AJPEAPEAXKPEAXP6AXPEAU_FLT_CALLBACK_DATA@@1@Z3K@ZEA; long (*UnionFs::Flt_CheckUpperOplock)(void * *,ulong,void *,void (*)(_FLT_CALLBACK_DATA *,void *),void (*)(_FLT_CALLBACK_DATA *,void *),ulong)
0x140076bc9  lea     r9, _lambda_d3744a3ec78c830341c2c93f7007b5ba____lambda_invoker_cdecl_
0x140076bd0  mov     edx, [rbx+8]
0x140076bd3  lea     r8, [rsp+380h+Event]
0x140076bd8  mov     dword ptr [rsp+380h+var_358], 0; char *
0x140076be0  lea     rcx, [rsi+58h]
0x140076be4  mov     [rsp+380h+Timeout], 0
0x140076bed  call    _guard_dispatch_icall
0x140076bf2  test    eax, eax
0x140076bf4  js      loc_140076CEA
0x140076bfa  cmp     eax, 103h
0x140076bff  jnz     short loc_140076C79
0x140076c01  test    rdi, rdi
0x140076c04  jz      short loc_140076C21
0x140076c06  mov     rcx, rdi; Resource
0x140076c09  call    cs:__imp_ExReleaseResourceLite
0x140076c10  nop     dword ptr [rax+rax+00h]
0x140076c15  call    cs:__imp_KeLeaveCriticalRegion
0x140076c1c  nop     dword ptr [rax+rax+00h]
0x140076c21  xor     r9d, r9d; Alertable
0x140076c24  mov     [rsp+380h+Timeout], 0; Timeout
0x140076c2d  xor     r8d, r8d; WaitMode
0x140076c30  lea     rcx, [rsp+380h+Event]; Object
0x140076c35  xor     edx, edx; WaitReason
0x140076c37  call    cs:__imp_KeWaitForSingleObject
0x140076c3e  nop     dword ptr [rax+rax+00h]
0x140076c43  lea     rcx, [rsp+380h+Event]; Event
0x140076c48  call    cs:__imp_KeClearEvent
0x140076c4f  nop     dword ptr [rax+rax+00h]
0x140076c54  mov     rdx, [rsi+78h]
0x140076c58  lea     rcx, [rsp+380h+FastMutex]
0x140076c5d  add     rdx, 38h ; '8'
0x140076c61  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x140076c66  mov     rdi, [rsp+380h+FastMutex]
0x140076c6b  mov     [rsp+380h+FastMutex], 0
0x140076c74  jmp     loc_140076BC2
0x140076c79  test    byte ptr [rbx+0Ch], 1
0x140076c7d  jz      loc_140076D13
0x140076c83  mov     rcx, [rsp+380h+Entry]
0x140076c88  lea     rax, [rsp+380h+var_318]
0x140076c8d  mov     r9d, [rbx+8]
0x140076c91  mov     r8d, 1
0x140076c97  mov     [rsp+380h+var_350], 0
0x140076c9f  mov     [rsp+380h+var_358], rax; char *
0x140076ca4  lea     rax, [rsp+380h+Entry]
0x140076ca9  mov     rdx, [rcx+10h]; FileObject
0x140076cad  mov     rcx, [rcx+8]; Instance
0x140076cb1  mov     [rsp+380h+Timeout], rax; __int64
0x140076cb6  call    ?RequestOplock@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@W4RequestOplockOperation@12@K$$QEAV?$unique_ptr@VRequestOplockContext@Utils@UnionFs@@U?$default_delete@VRequestOplockContext@Utils@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@K@Z; UnionFs::Utils::RequestOplock(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::Utils::RequestOplockOperation,ulong,utl::unique_ptr<UnionFs::Utils::RequestOplockContext,utl::default_delete<UnionFs::Utils::RequestOplockContext>> &&,UnionFs::StackEventTracer &,ulong)
0x140076cbb  test    eax, eax
0x140076cbd  jns     short loc_140076D13
0x140076cbf  lea     rcx, aPushAcknowledg; "PUSH: Acknowledging oplock break"
0x140076cc6  mov     r8, 6D100212744h; struct UnionFs::StackEventTracer *
0x140076cd0  mov     [rsp+380h+Timeout], rcx; char *
0x140076cd5  lea     r9, aUnionfsUtilsRe_0; "UnionFs::Utils::RequestOplockCompletion"...
0x140076cdc  mov     ecx, eax; this
0x140076cde  lea     rdx, [rsp+380h+var_318]; int
0x140076ce3  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076ce8  jmp     short loc_140076D13
0x140076cea  lea     rcx, aApiUnexpectedF; "API: Unexpected FltCheckUpperOplock fai"...
0x140076cf1  mov     r8, 6FC00212717h; struct UnionFs::StackEventTracer *
0x140076cfb  mov     [rsp+380h+Timeout], rcx; char *
0x140076d00  lea     r9, aUnionfsUtilsRe_0; "UnionFs::Utils::RequestOplockCompletion"...
0x140076d07  mov     ecx, eax; this
0x140076d09  lea     rdx, [rsp+380h+var_318]; int
0x140076d0e  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076d13  test    rdi, rdi
0x140076d16  jz      short loc_140076D33
0x140076d18  mov     rcx, rdi; Resource
0x140076d1b  call    cs:__imp_ExReleaseResourceLite
0x140076d22  nop     dword ptr [rax+rax+00h]
0x140076d27  call    cs:__imp_KeLeaveCriticalRegion
0x140076d2e  nop     dword ptr [rax+rax+00h]
0x140076d33  xor     edx, edx; Tag
0x140076d35  mov     rcx, rbx; P
0x140076d38  call    cs:__imp_ExFreePoolWithTag
0x140076d3f  nop     dword ptr [rax+rax+00h]
0x140076d44  mov     rbx, [rsp+380h+Entry]
0x140076d49  test    rbx, rbx
0x140076d4c  jz      short loc_140076D73
0x140076d4e  mov     rcx, rbx; this
0x140076d51  call    ??1RequestOplockContext@Utils@UnionFs@@QEAA@XZ; UnionFs::Utils::RequestOplockContext::~RequestOplockContext(void)
0x140076d56  mov     rdx, rbx; Entry
0x140076d59  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140076d60  add     rcx, 0A20h; Lookaside
0x140076d67  call    cs:__imp_ExFreeToLookasideListEx
0x140076d6e  nop     dword ptr [rax+rax+00h]
0x140076d73  lea     rcx, [rsp+380h+var_318]; this
0x140076d78  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140076d7d  mov     rcx, [rbp+280h+var_28]
0x140076d84  xor     rcx, rsp; StackCookie
0x140076d87  call    __security_check_cookie
0x140076d8c  add     rsp, 360h
0x140076d93  pop     r14
0x140076d95  pop     rdi
0x140076d96  pop     rsi
0x140076d97  pop     rbx
0x140076d98  pop     rbp
0x140076d99  retn
```
