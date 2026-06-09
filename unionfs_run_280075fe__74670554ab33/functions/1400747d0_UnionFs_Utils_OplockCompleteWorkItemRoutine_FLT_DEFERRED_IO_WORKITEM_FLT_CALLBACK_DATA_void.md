# UnionFs::Utils::OplockCompleteWorkItemRoutine(_FLT_DEFERRED_IO_WORKITEM *,_FLT_CALLBACK_DATA *,void *)

- ea: `0x1400747d0`
- end: `0x140074964`
- name: `?OplockCompleteWorkItemRoutine@Utils@UnionFs@@YAXPEAU_FLT_DEFERRED_IO_WORKITEM@@PEAU_FLT_CALLBACK_DATA@@PEAX@Z`
- size: `404`
- prototype: `void __stdcall(PFLT_DEFERRED_IO_WORKITEM FltWorkItem, PFLT_CALLBACK_DATA CallbackData, PVOID Context)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400055d0`
- `0x140006168`
- `0x14000cce0`
- `0x140011e00`
- `0x140034890`
- `0x1400545c0`
- `0x140056ac4`
- `0x1400747d0`
- `0x14007b7d0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140074931`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140074931`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140074914`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140074914`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400748fa`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400748fa`

## string_xrefs

- `0x1400748d5`: `UnionFs::Utils::OplockCompleteWorkItemRoutine`
- `0x1400748cb`: `ORIGIN: Failure in oplock completion`

## pseudocode

```c
void __fastcall UnionFs::Utils::OplockCompleteWorkItemRoutine(
        PFLT_DEFERRED_IO_WORKITEM FltWorkItem,
        PFLT_CALLBACK_DATA CallbackData,
        const struct _FLT_RELATED_OBJECTS **Context)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  UCHAR MajorFunction; // cl
  __int64 v7; // rbp
  FLT_PREOP_CALLBACK_STATUS v8; // edi
  enum _FLT_PREOP_CALLBACK_STATUS v9; // eax
  UnionFs *Status; // rcx
  struct _FLT_DEFERRED_IO_WORKITEM *v11; // rcx
  const char *v12; // [rsp+28h] [rbp-330h]
  struct _FLT_RELATED_OBJECTS Contexta[15]; // [rsp+30h] [rbp-328h] BYREF

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)&Contexta[0].Filter, 0x6DA002127D0uLL);
  Iopb = CallbackData->Iopb;
  *(_QWORD *)&Contexta[0].Size = 0;
  MajorFunction = Iopb->MajorFunction;
  if ( MajorFunction )
  {
    switch ( MajorFunction )
    {
      case 3u:
        v7 = 0x6DC002127E7LL;
        v9 = UnionFs::UnionFsFilter::PreRead(CallbackData, *Context, (void **)Contexta);
        break;
      case 6u:
        v7 = 0x6DD002127EDLL;
        v9 = UnionFs::UnionFsFilter::PreSetInfo(CallbackData, *Context, Contexta);
        break;
      case 0xDu:
        v7 = 0x6DE002127F3LL;
        v9 = (unsigned int)UnionFs::UnionFsFilter::PreFsControl(CallbackData, *Context, (void **)Contexta);
        break;
      default:
        CallbackData->IoStatus.Status = -1073741808;
        v7 = 0x6DF002127FELL;
        CallbackData->IoStatus.Information = 0;
        v8 = FLT_PREOP_COMPLETE;
        goto LABEL_11;
    }
  }
  else
  {
    v7 = 0x6DB002127E1LL;
    v9 = (unsigned int)UnionFs::UnionFsFilter::PreCreate(CallbackData, *Context, (void **)Contexta);
  }
  v8 = v9;
  if ( v9 != FLT_PREOP_COMPLETE )
    goto LABEL_13;
LABEL_11:
  Status = (UnionFs *)(unsigned int)CallbackData->IoStatus.Status;
  if ( (int)Status < 0 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      Status,
      (int)&Contexta[0].Filter,
      (struct UnionFs::StackEventTracer *)v7,
      (unsigned __int64)"UnionFs::Utils::OplockCompleteWorkItemRoutine",
      "ORIGIN: Failure in oplock completion",
      v12);
LABEL_13:
    if ( v8 == FLT_PREOP_PENDING )
      goto LABEL_15;
  }
  FltCompletePendedPreOperation(CallbackData, v8, *(PVOID *)&Contexta[0].Size);
LABEL_15:
  if ( Context )
  {
    v11 = (struct _FLT_DEFERRED_IO_WORKITEM *)Context[1];
    if ( v11 )
      FltFreeDeferredIoWorkItem(v11);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 28, Context);
  }
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)&Contexta[0].Filter);
}

```

## disassembly

```asm
0x1400747d0  push    rbx
0x1400747d2  push    rbp
0x1400747d3  push    rsi
0x1400747d4  push    rdi
0x1400747d5  sub     rsp, 338h
0x1400747dc  mov     rax, cs:__security_cookie
0x1400747e3  xor     rax, rsp
0x1400747e6  mov     [rsp+358h+var_30], rax
0x1400747ee  mov     rbx, rdx
0x1400747f1  lea     rcx, [rsp+358h+var_320]; this
0x1400747f6  mov     rdx, 6DA002127D0h; unsigned __int64
0x140074800  mov     rsi, r8
0x140074803  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x140074808  mov     rax, [rbx+10h]
0x14007480c  mov     [rsp+358h+Context], 0
0x140074815  mov     cl, [rax+4]
0x140074818  test    cl, cl
0x14007481a  jz      loc_1400748A3
0x140074820  cmp     cl, 3
0x140074823  jz      short loc_140074887
0x140074825  cmp     cl, 6
0x140074828  jz      short loc_14007486B
0x14007482a  cmp     cl, 0Dh
0x14007482d  jz      short loc_14007484F
0x14007482f  mov     dword ptr [rbx+18h], 0C0000010h
0x140074836  mov     rbp, 6DF002127FEh
0x140074840  mov     qword ptr [rbx+20h], 0
0x140074848  mov     edi, 4
0x14007484d  jmp     short loc_1400748C4
0x14007484f  mov     rdx, [rsi]; struct _FLT_RELATED_OBJECTS *
0x140074852  lea     r8, [rsp+358h+Context]; void **
0x140074857  mov     rcx, rbx; struct _FLT_CALLBACK_DATA *
0x14007485a  mov     rbp, 6DE002127F3h
0x140074864  call    ?PreFsControl@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z; UnionFs::UnionFsFilter::PreFsControl(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)
0x140074869  jmp     short loc_1400748BD
0x14007486b  mov     rdx, [rsi]; struct _FLT_RELATED_OBJECTS *
0x14007486e  lea     r8, [rsp+358h+Context]; struct _FLT_RELATED_OBJECTS *
0x140074873  mov     rcx, rbx; this
0x140074876  mov     rbp, 6DD002127EDh
0x140074880  call    ?PreSetInfo@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z; UnionFs::UnionFsFilter::PreSetInfo(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)
0x140074885  jmp     short loc_1400748BD
0x140074887  mov     rdx, [rsi]; struct _FLT_RELATED_OBJECTS *
0x14007488a  lea     r8, [rsp+358h+Context]; void **
0x14007488f  mov     rcx, rbx; struct _FLT_CALLBACK_DATA *
0x140074892  mov     rbp, 6DC002127E7h
0x14007489c  call    ?PreRead@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z; UnionFs::UnionFsFilter::PreRead(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)
0x1400748a1  jmp     short loc_1400748BD
0x1400748a3  mov     rdx, [rsi]; struct _FLT_RELATED_OBJECTS *
0x1400748a6  lea     r8, [rsp+358h+Context]; void **
0x1400748ab  mov     rcx, rbx; struct _FLT_CALLBACK_DATA *
0x1400748ae  mov     rbp, 6DB002127E1h
0x1400748b8  call    ?PreCreate@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z; UnionFs::UnionFsFilter::PreCreate(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)
0x1400748bd  mov     edi, eax
0x1400748bf  cmp     eax, 4
0x1400748c2  jnz     short loc_1400748EB
0x1400748c4  mov     ecx, [rbx+18h]; this
0x1400748c7  test    ecx, ecx
0x1400748c9  jns     short loc_1400748F0
0x1400748cb  lea     rax, aOriginFailureI; "ORIGIN: Failure in oplock completion"
0x1400748d2  mov     r8, rbp; struct UnionFs::StackEventTracer *
0x1400748d5  lea     r9, aUnionfsUtilsOp_0; "UnionFs::Utils::OplockCompleteWorkItemR"...
0x1400748dc  mov     [rsp+358h+var_338], rax; char *
0x1400748e1  lea     rdx, [rsp+358h+var_320]; int
0x1400748e6  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400748eb  cmp     edi, 2
0x1400748ee  jz      short loc_140074906
0x1400748f0  mov     r8, [rsp+358h+Context]; Context
0x1400748f5  mov     edx, edi; CallbackStatus
0x1400748f7  mov     rcx, rbx; CallbackData
0x1400748fa  call    cs:__imp_FltCompletePendedPreOperation
0x140074901  nop     dword ptr [rax+rax+00h]
0x140074906  test    rsi, rsi
0x140074909  jz      short loc_14007493D
0x14007490b  mov     rcx, [rsi+8]; FltWorkItem
0x14007490f  test    rcx, rcx
0x140074912  jz      short loc_140074920
0x140074914  call    cs:__imp_FltFreeDeferredIoWorkItem
0x14007491b  nop     dword ptr [rax+rax+00h]
0x140074920  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140074927  mov     rdx, rsi; Entry
0x14007492a  add     rcx, 0A80h; Lookaside
0x140074931  call    cs:__imp_ExFreeToLookasideListEx
0x140074938  nop     dword ptr [rax+rax+00h]
0x14007493d  lea     rcx, [rsp+358h+var_320]; this
0x140074942  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140074947  mov     rcx, [rsp+358h+var_30]
0x14007494f  xor     rcx, rsp; StackCookie
0x140074952  call    __security_check_cookie
0x140074957  add     rsp, 338h
0x14007495e  pop     rdi
0x14007495f  pop     rsi
0x140074960  pop     rbp
0x140074961  pop     rbx
0x140074962  retn
```
