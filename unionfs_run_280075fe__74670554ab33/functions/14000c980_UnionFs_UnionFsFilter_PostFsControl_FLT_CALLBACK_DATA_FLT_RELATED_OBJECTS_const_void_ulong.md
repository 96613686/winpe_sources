# UnionFs::UnionFsFilter::PostFsControl(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)

- ea: `0x14000c980`
- end: `0x14000cb6c`
- name: `?PostFsControl@UnionFsFilter@UnionFs@@SA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z`
- size: `492`
- prototype: `enum _FLT_POSTOP_CALLBACK_STATUS __fastcall(struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, FsFltWil::Details *this, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400056b4`
- `0x1400060b4`
- `0x140006168`
- `0x14000c980`
- `0x14000f680`
- `0x140056afc`
- `0x140079df4`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cabd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cb01`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cb2b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cabd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cb01`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cb2b`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PostFsControl(
        struct _FLT_CALLBACK_DATA *a1,
        const struct _FLT_RELATED_OBJECTS *a2,
        const struct UnionFs::UfsStreamHandleCtx **this,
        char a4)
{
  const struct UnionFs::UfsStreamHandleCtx **v8; // rbx
  NTSTATUS Status; // ecx
  __int64 v10; // rdx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  NTSTATUS v12; // ebp
  struct FsFltWil::Details::RundownRefCacheAware *v13; // rdx
  const struct UnionFs::UfsStreamHandleCtx *v14; // rcx
  const struct UnionFs::UfsStreamHandleCtx *v15; // rcx
  struct UnionFs::StackEventTracer *v17; // [rsp+28h] [rbp-320h]
  char v18[4]; // [rsp+30h] [rbp-318h] BYREF

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v18, 0x76200010BD0uLL, a1);
  if ( a1->Iopb->Parameters.Read.ByteOffset.LowPart == 590059 )
  {
    v8 = this;
    this = 0;
  }
  else
  {
    v8 = 0;
    if ( !this )
      MicrosoftTelemetryAssertTriggeredMsgKM("No COW-I/O sync rundown");
  }
  Status = a1->IoStatus.Status;
  v10 = 0x80000000LL;
  if ( ((int)(Status + 0x80000000) < 0 || Status == -2147483643) && (a4 & 1) == 0 )
  {
    Iopb = a1->Iopb;
    if ( Iopb->Parameters.Read.ByteOffset.LowPart == 590059 )
    {
      v12 = UnionFs::UnionFsFilter::VirtualizeUSNInfo(
              (UnionFs::UnionFsFilter *)v18,
              a2,
              v8[1],
              *v8,
              (struct USN_RECORD_V2 *)Iopb->Parameters.Create.EaBuffer,
              (struct UnionFs::StackEventTracer *)v18);
      if ( v12 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v12,
          (int)v18,
          (struct UnionFs::StackEventTracer *)0x76100010C00LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PostFsControl",
          "PUSH: Post USN info virtualization",
          (const char *)v17);
        a1->IoStatus.Status = v12;
        a1->IoStatus.Information = 0;
        if ( this )
        {
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)this, v13);
          v14 = this[16];
          if ( v14 )
            (*(void (__fastcall **)(const struct UnionFs::UfsStreamHandleCtx *))(*(_QWORD *)v14 + 24LL))(v14);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), this);
        }
LABEL_19:
        UnionFs::QueryUsnContext::~QueryUsnContext((UnionFs::QueryUsnContext *)v8);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 704), v8);
        goto LABEL_20;
      }
    }
  }
  if ( this )
  {
    FsFltWil::Details::ReleaseRundownProtectionCacheAware(
      (FsFltWil::Details *)this,
      (struct FsFltWil::Details::RundownRefCacheAware *)v10);
    v15 = this[16];
    if ( v15 )
      (*(void (__fastcall **)(const struct UnionFs::UfsStreamHandleCtx *))(*(_QWORD *)v15 + 24LL))(v15);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), this);
  }
  if ( v8 )
    goto LABEL_19;
LABEL_20:
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v18);
  return 0;
}

```

## disassembly

```asm
0x14000c980  mov     [rsp+arg_10], rbx
0x14000c985  mov     [rsp+arg_18], rbp
0x14000c98a  push    rsi
0x14000c98b  push    rdi
0x14000c98c  push    r14
0x14000c98e  sub     rsp, 330h
0x14000c995  mov     rax, cs:__security_cookie
0x14000c99c  xor     rax, rsp
0x14000c99f  mov     [rsp+348h+var_28], rax
0x14000c9a7  mov     rdi, r8
0x14000c9aa  mov     r14, rdx
0x14000c9ad  mov     r8, rcx; struct _FLT_CALLBACK_DATA *
0x14000c9b0  mov     rsi, rcx
0x14000c9b3  lea     rcx, [rsp+348h+var_318]; this
0x14000c9b8  mov     rdx, 76200010BD0h; unsigned __int64
0x14000c9c2  mov     ebp, r9d
0x14000c9c5  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x14000c9ca  mov     rax, [rsi+10h]
0x14000c9ce  cmp     dword ptr [rax+28h], 900EBh
0x14000c9d5  jz      short loc_14000C9EC
0x14000c9d7  xor     ebx, ebx
0x14000c9d9  test    rdi, rdi
0x14000c9dc  jnz     short loc_14000C9F1
0x14000c9de  lea     rcx, aNoCowIOSyncRun; "No COW-I/O sync rundown"
0x14000c9e5  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14000c9ea  jmp     short loc_14000C9F1
0x14000c9ec  mov     rbx, rdi
0x14000c9ef  xor     edi, edi
0x14000c9f1  mov     ecx, [rsi+18h]
0x14000c9f4  mov     edx, 80000000h; struct FsFltWil::Details::RundownRefCacheAware *
0x14000c9f9  lea     eax, [rcx+rdx]
0x14000c9fc  test    edx, eax
0x14000c9fe  jnz     short loc_14000CA0C
0x14000ca00  cmp     ecx, 80000005h
0x14000ca06  jnz     loc_14000CACB
0x14000ca0c  test    bpl, 1
0x14000ca10  jnz     loc_14000CACB
0x14000ca16  mov     rax, [rsi+10h]
0x14000ca1a  cmp     dword ptr [rax+28h], 900EBh
0x14000ca21  jnz     loc_14000CACB
0x14000ca27  mov     rax, [rax+38h]
0x14000ca2b  lea     rcx, [rsp+348h+var_318]; this
0x14000ca30  mov     r9, [rbx]; struct UnionFs::UfsStreamHandleCtx *
0x14000ca33  mov     rdx, r14; struct _FLT_RELATED_OBJECTS *
0x14000ca36  mov     r8, [rbx+8]; struct UnionFs::UfsUnionCtx *
0x14000ca3a  mov     [rsp+348h+var_320], rcx; char *
0x14000ca3f  mov     [rsp+348h+var_328], rax; struct USN_RECORD_V2 *
0x14000ca44  call    ?VirtualizeUSNInfo@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_RELATED_OBJECTS@@AEAVUfsUnionCtx@2@AEBVUfsStreamHandleCtx@2@AEAUUSN_RECORD_V2@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::VirtualizeUSNInfo(_FLT_RELATED_OBJECTS const &,UnionFs::UfsUnionCtx &,UnionFs::UfsStreamHandleCtx const &,USN_RECORD_V2 &,UnionFs::StackEventTracer &)
0x14000ca49  mov     ebp, eax
0x14000ca4b  test    eax, eax
0x14000ca4d  jns     short loc_14000CACB
0x14000ca4f  lea     rax, aPushPostUsnInf; "PUSH: Post USN info virtualization"
0x14000ca56  mov     r8, 76100010C00h; struct UnionFs::StackEventTracer *
0x14000ca60  lea     r9, aUnionfsUnionfs_38; "UnionFs::UnionFsFilter::PostFsControl"
0x14000ca67  mov     [rsp+348h+var_328], rax; char *
0x14000ca6c  lea     rdx, [rsp+348h+var_318]; int
0x14000ca71  mov     ecx, ebp; this
0x14000ca73  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000ca78  mov     [rsi+18h], ebp
0x14000ca7b  mov     qword ptr [rsi+20h], 0
0x14000ca83  test    rdi, rdi
0x14000ca86  jz      loc_14000CB12
0x14000ca8c  mov     rcx, rdi; this
0x14000ca8f  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14000ca94  mov     rcx, [rdi+80h]
0x14000ca9b  test    rcx, rcx
0x14000ca9e  jz      short loc_14000CAAC
0x14000caa0  mov     rax, [rcx]
0x14000caa3  mov     rax, [rax+18h]
0x14000caa7  call    _guard_dispatch_icall
0x14000caac  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000cab3  mov     rdx, rdi; Entry
0x14000cab6  add     rcx, 380h; Lookaside
0x14000cabd  call    cs:__imp_ExFreeToLookasideListEx
0x14000cac4  nop     dword ptr [rax+rax+00h]
0x14000cac9  jmp     short loc_14000CB12
0x14000cacb  test    rdi, rdi
0x14000cace  jz      short loc_14000CB0D
0x14000cad0  mov     rcx, rdi; this
0x14000cad3  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14000cad8  mov     rcx, [rdi+80h]
0x14000cadf  test    rcx, rcx
0x14000cae2  jz      short loc_14000CAF0
0x14000cae4  mov     rax, [rcx]
0x14000cae7  mov     rax, [rax+18h]
0x14000caeb  call    _guard_dispatch_icall
0x14000caf0  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000caf7  mov     rdx, rdi; Entry
0x14000cafa  add     rcx, 380h; Lookaside
0x14000cb01  call    cs:__imp_ExFreeToLookasideListEx
0x14000cb08  nop     dword ptr [rax+rax+00h]
0x14000cb0d  test    rbx, rbx
0x14000cb10  jz      short loc_14000CB37
0x14000cb12  mov     rcx, rbx; this
0x14000cb15  call    ??1QueryUsnContext@UnionFs@@QEAA@XZ; UnionFs::QueryUsnContext::~QueryUsnContext(void)
0x14000cb1a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000cb21  mov     rdx, rbx; Entry
0x14000cb24  add     rcx, 2C0h; Lookaside
0x14000cb2b  call    cs:__imp_ExFreeToLookasideListEx
0x14000cb32  nop     dword ptr [rax+rax+00h]
0x14000cb37  lea     rcx, [rsp+348h+var_318]; this
0x14000cb3c  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x14000cb41  xor     eax, eax
0x14000cb43  mov     rcx, [rsp+348h+var_28]
0x14000cb4b  xor     rcx, rsp; StackCookie
0x14000cb4e  call    __security_check_cookie
0x14000cb53  lea     r11, [rsp+348h+var_18]
0x14000cb5b  mov     rbx, [r11+30h]
0x14000cb5f  mov     rbp, [r11+38h]
0x14000cb63  mov     rsp, r11
0x14000cb66  pop     r14
0x14000cb68  pop     rdi
0x14000cb69  pop     rsi
0x14000cb6a  retn
```
