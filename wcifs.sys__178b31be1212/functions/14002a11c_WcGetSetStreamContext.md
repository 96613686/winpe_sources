# WcGetSetStreamContext

- ea: `0x14002a11c`
- end: `0x14002a65e`
- name: `WcGetSetStreamContext`
- size: `1346`
- prototype: `NTSTATUS __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PFLT_CONTEXT Context, __int64, int, __int64, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400278a4`
- `0x140029658`

## callees

- `0x1400020c4`
- `0x1400024fc`
- `0x14000250c`
- `0x14000308c`
- `0x140004198`
- `0x140007c60`
- `0x1400080c0`
- `0x14002a11c`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x14002a248`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002a248`
- `ntoskrnl!FsRtlAcquireFileExclusive` at `0x14002a3f2`
- `ntoskrnl!FsRtlAcquireFileExclusive` at `0x14002a3f2`
- `ntoskrnl!KeInitializeEvent` at `0x14002a266`
- `ntoskrnl!KeInitializeEvent` at `0x14002a266`
- `ntoskrnl!FsRtlReleaseFile` at `0x14002a434`
- `ntoskrnl!FsRtlReleaseFile` at `0x14002a434`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002a5ba`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002a5ba`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002a3cd`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002a3cd`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14002a413`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14002a413`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14002a3e1`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14002a425`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14002a3e1`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14002a425`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002a5f2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002a5f2`
- `FLTMGR!FltAllocateContext` at `0x14002a1a3`
- `FLTMGR!FltAllocateContext` at `0x14002a1a3`
- `FLTMGR!FltSetStreamContext` at `0x14002a54c`
- `FLTMGR!FltSetStreamContext` at `0x14002a54c`
- `FLTMGR!FltQueryInformationFile` at `0x14002a330`
- `FLTMGR!FltQueryInformationFile` at `0x14002a330`
- `FLTMGR!FltReferenceContext` at `0x14002a1c8`
- `FLTMGR!FltReferenceContext` at `0x14002a1c8`
- `FLTMGR!FltReleaseContext` at `0x14002a569`
- `FLTMGR!FltReleaseContext` at `0x14002a61a`
- `FLTMGR!FltReleaseContext` at `0x14002a62f`
- `FLTMGR!FltReleaseContext` at `0x14002a569`
- `FLTMGR!FltReleaseContext` at `0x14002a61a`
- `FLTMGR!FltReleaseContext` at `0x14002a62f`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14002a378`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14002a378`
- `FLTMGR!FltGetInstanceContext` at `0x14002a2fa`
- `FLTMGR!FltGetInstanceContext` at `0x14002a2fa`

## pseudocode

```c
NTSTATUS __fastcall WcGetSetStreamContext(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        PFLT_CONTEXT Context,
        __int64 a4,
        int a5,
        __int64 a6,
        _QWORD *a7,
        _QWORD *a8)
{
  NTSTATUS result; // eax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  PFLT_CONTEXT v15; // rcx
  __int64 Source; // rax
  __int64 v17; // rdi
  NTSTATUS InstanceContext; // ebx
  char *v19; // rax
  char *v20; // rbx
  PFLT_GENERIC_WORKITEM GenericWorkItem; // rax
  char v22; // bl
  int v23; // edx
  int v24; // r9d
  int v25; // edx
  int v26; // eax
  NTSTATUS v27; // eax
  PFLT_CONTEXT v28; // rax
  _QWORD *v29; // rdx
  _QWORD *v30; // rax
  char v31; // [rsp+30h] [rbp-71h]
  char Status; // [rsp+38h] [rbp-69h]
  PFLT_CONTEXT NewContext; // [rsp+40h] [rbp-61h] BYREF
  ULONG LengthReturned; // [rsp+48h] [rbp-59h] BYREF
  PFLT_CONTEXT Contexta; // [rsp+50h] [rbp-51h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+58h] [rbp-49h] BYREF
  _QWORD *v37; // [rsp+60h] [rbp-41h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+68h] [rbp-39h] BYREF
  _BYTE FileInformation[24]; // [rsp+78h] [rbp-29h] BYREF

  v37 = a8;
  NewContext = 0;
  OldContext = 0;
  LengthReturned = 0;
  Contexta = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  IoStatus = 0;
  result = FltAllocateContext(Globals, 8u, 0x108u, (POOL_TYPE)512, &NewContext);
  if ( result < 0 )
    return result;
  memset(NewContext, 0, 0x108u);
  FltReferenceContext(Context);
  _InterlockedIncrement((volatile signed __int32 *)a4);
  v13 = NewContext;
  *((_QWORD *)NewContext + 1) = NewContext;
  *v13 = v13;
  *((_DWORD *)NewContext + 4) = 0;
  *((_DWORD *)NewContext + 5) = 0;
  *((_QWORD *)NewContext + 4) = Context;
  *((_DWORD *)NewContext + 6) = a5;
  *((_QWORD *)NewContext + 6) = FileObject->SectionObjectPointer;
  *((_QWORD *)NewContext + 32) = 0;
  *((_BYTE *)NewContext + 28) = 0;
  *((_BYTE *)NewContext + 29) = 0;
  *((_QWORD *)NewContext + 5) = a4;
  *((_QWORD *)NewContext + 28) = 0;
  ExInitializeResourceLite((PERESOURCE)((char *)NewContext + 120));
  KeInitializeEvent((PRKEVENT)((char *)NewContext + 232), SynchronizationEvent, 1u);
  v14 = (char *)NewContext + 56;
  *((_QWORD *)NewContext + 8) = (char *)NewContext + 56;
  *v14 = v14;
  if ( a7 )
  {
    if ( (_QWORD *)*a7 != a7 )
    {
      *((_QWORD *)NewContext + 9) = a6;
      *((_QWORD *)NewContext + 7) = *a7;
      *((_QWORD *)NewContext + 8) = a7[1];
      *(_QWORD *)(*a7 + 8LL) = (char *)NewContext + 56;
      *(_QWORD *)a7[1] = (char *)NewContext + 56;
      v15 = NewContext;
      a7[1] = a7;
      *a7 = a7;
      Source = WcGetSource(v15);
      v17 = Source;
      if ( (*(_DWORD *)(*(_QWORD *)(Source + 32) + 16LL) & 1) == 0 )
      {
        InstanceContext = FltGetInstanceContext(*(PFLT_INSTANCE *)Source, &Contexta);
        if ( InstanceContext < 0 )
          goto LABEL_41;
        InstanceContext = FltQueryInformationFile(
                            *(PFLT_INSTANCE *)v17,
                            *(PFILE_OBJECT *)(v17 + 16),
                            FileInformation,
                            0x18u,
                            FileMaximumInformation|FileBothDirectoryInformation,
                            &LengthReturned);
        if ( InstanceContext < 0 )
          goto LABEL_41;
        *(_OWORD *)((char *)NewContext + 100) = *(_OWORD *)((char *)Contexta + 40);
        *(_OWORD *)((char *)NewContext + 84) = *(_OWORD *)&FileInformation[8];
      }
    }
  }
  v19 = (char *)NewContext + 56;
  v20 = (char *)*((_QWORD *)NewContext + 7);
  while ( v20 != v19 )
  {
    if ( (*((_DWORD *)v20 + 8) & 1) != 0 )
    {
      GenericWorkItem = FltAllocateGenericWorkItem();
      *((_QWORD *)v20 + 2) = GenericWorkItem;
      if ( !GenericWorkItem )
      {
        InstanceContext = -1073741670;
        goto LABEL_41;
      }
    }
    v20 = *(char **)v20;
    v19 = (char *)NewContext + 56;
  }
  if ( (*((_DWORD *)Context + 22) & 1) == 0 && (a5 & 0x10) == 0 )
  {
    v22 = 0;
    if ( !IoGetTopLevelIrp() )
    {
      IoSetTopLevelIrp((PIRP)1);
      v22 = 1;
    }
    FsRtlAcquireFileExclusive(FileObject);
    CcCoherencyFlushAndPurgeCache(FileObject->SectionObjectPointer, 0, 0, &IoStatus, 0);
    if ( v22 )
      IoSetTopLevelIrp(0);
    FsRtlReleaseFile(FileObject);
    InstanceContext = IoStatus.Status;
    if ( IoStatus.Status < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_41;
      Status = IoStatus.Status;
      v24 = 10;
      v31 = 91;
      goto LABEL_22;
    }
    if ( (unsigned __int8)WcIsSourceAvailable(NewContext) )
    {
      v26 = WcSyncPlaceholderFileSize(Instance, FileObject);
      InstanceContext = v26;
      if ( v26 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          Status = v26;
          v24 = 11;
          v31 = 116;
LABEL_22:
          LOBYTE(v23) = 2;
          WPP_RECORDER_SF_sDd(
            wil_details_featureDescriptors_a->DeviceExtension,
            v23,
            5,
            v24,
            (__int64)WPP_950001495d7d34274b0ab8b7fcc7b560_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\context.c",
            v31,
            Status);
          goto LABEL_41;
        }
        goto LABEL_41;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v25) = 2;
      WPP_RECORDER_SF_sD(
        wil_details_featureDescriptors_a->DeviceExtension,
        v25,
        5,
        12,
        (__int64)WPP_950001495d7d34274b0ab8b7fcc7b560_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\context.c",
        132);
    }
  }
  v27 = FltSetStreamContext(Instance, FileObject, FLT_SET_CONTEXT_KEEP_IF_EXISTS, NewContext, &OldContext);
  InstanceContext = v27;
  if ( v27 >= 0 )
  {
    if ( (unsigned int)(*(_DWORD *)(a4 + 28) - 2) <= 1 )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(a4 + 200));
      v29 = *(_QWORD **)(a4 + 192);
      if ( *v29 != a4 + 184 )
        __fastfail(3u);
      v30 = NewContext;
      *(_QWORD *)NewContext = a4 + 184;
      v30[1] = v29;
      *v29 = v30;
      *(_QWORD *)(a4 + 192) = v30;
      ExReleaseFastMutex((PFAST_MUTEX)(a4 + 200));
    }
    v28 = NewContext;
  }
  else
  {
    if ( v27 != -1071906814 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        Status = v27;
        v24 = 13;
        v31 = -101;
        goto LABEL_22;
      }
      goto LABEL_41;
    }
    FltReleaseContext(NewContext);
    v28 = OldContext;
    InstanceContext = 0;
  }
  NewContext = 0;
  *v37 = v28;
LABEL_41:
  if ( Contexta )
    FltReleaseContext(Contexta);
  if ( NewContext )
    FltReleaseContext(NewContext);
  return InstanceContext;
}

```

## disassembly

```asm
0x14002a11c  push    rbp
0x14002a11e  push    rbx
0x14002a11f  push    rsi
0x14002a120  push    rdi
0x14002a121  push    r12
0x14002a123  push    r13
0x14002a125  push    r14
0x14002a127  push    r15
0x14002a129  lea     rbp, [rsp-7]
0x14002a12e  sub     rsp, 0A8h
0x14002a135  mov     rax, cs:__security_cookie
0x14002a13c  xor     rax, rsp
0x14002a13f  mov     [rbp+3Fh+var_50], rax
0x14002a143  mov     rax, [rbp+3Fh+arg_38]
0x14002a14a  xor     r14d, r14d
0x14002a14d  mov     rbx, [rbp+3Fh+arg_30]
0x14002a151  xorps   xmm0, xmm0
0x14002a154  mov     [rbp+3Fh+var_80], rax
0x14002a158  mov     r15, rdx
0x14002a15b  xor     eax, eax
0x14002a15d  mov     [rbp+3Fh+NewContext], r14
0x14002a161  mov     [rbp+3Fh+var_58], rax
0x14002a165  mov     r13, r9
0x14002a168  mov     rsi, r8
0x14002a16b  mov     [rbp+3Fh+OldContext], r14
0x14002a16f  mov     r12, rcx
0x14002a172  mov     [rbp+3Fh+var_98], r14d
0x14002a176  mov     rcx, cs:Globals; Filter
0x14002a17d  lea     edx, [rax+8]; ContextType
0x14002a180  lea     rax, [rbp+3Fh+NewContext]
0x14002a184  mov     [rbp+3Fh+Context], r14
0x14002a188  mov     edi, 108h
0x14002a18d  mov     [rsp+0E0h+ReturnedContext], rax; ReturnedContext
0x14002a192  mov     r9d, 200h; PoolType
0x14002a198  mov     r8d, edi; ContextSize
0x14002a19b  movups  [rbp+3Fh+FileInformation], xmm0
0x14002a19f  movups  xmmword ptr [rbp+3Fh+IoStatus], xmm0
0x14002a1a3  call    cs:__imp_FltAllocateContext
0x14002a1aa  nop     dword ptr [rax+rax+00h]
0x14002a1af  test    eax, eax
0x14002a1b1  js      loc_14002A63D
0x14002a1b7  mov     rcx, [rbp+3Fh+NewContext]; void *
0x14002a1bb  mov     r8d, edi; Size
0x14002a1be  xor     edx, edx; Val
0x14002a1c0  call    memset
0x14002a1c5  mov     rcx, rsi; Context
0x14002a1c8  call    cs:__imp_FltReferenceContext
0x14002a1cf  nop     dword ptr [rax+rax+00h]
0x14002a1d4  lock inc dword ptr [r13+0]
0x14002a1d9  mov     rax, [rbp+3Fh+NewContext]
0x14002a1dd  mov     ecx, [rbp+3Fh+arg_20]
0x14002a1e0  mov     [rax+8], rax
0x14002a1e4  mov     [rax], rax
0x14002a1e7  mov     rax, [rbp+3Fh+NewContext]
0x14002a1eb  mov     [rax+10h], r14d
0x14002a1ef  mov     rax, [rbp+3Fh+NewContext]
0x14002a1f3  mov     [rax+14h], r14d
0x14002a1f7  mov     rax, [rbp+3Fh+NewContext]
0x14002a1fb  mov     [rax+20h], rsi
0x14002a1ff  mov     rax, [rbp+3Fh+NewContext]
0x14002a203  mov     [rax+18h], ecx
0x14002a206  mov     rax, [rbp+3Fh+NewContext]
0x14002a20a  mov     rcx, [r15+28h]
0x14002a20e  mov     [rax+30h], rcx
0x14002a212  mov     rax, [rbp+3Fh+NewContext]
0x14002a216  mov     [rax+100h], r14
0x14002a21d  mov     rax, [rbp+3Fh+NewContext]
0x14002a221  mov     [rax+1Ch], r14b
0x14002a225  mov     rax, [rbp+3Fh+NewContext]
0x14002a229  mov     [rax+1Dh], r14b
0x14002a22d  mov     rax, [rbp+3Fh+NewContext]
0x14002a231  mov     [rax+28h], r13
0x14002a235  mov     rax, [rbp+3Fh+NewContext]
0x14002a239  mov     [rax+0E0h], r14
0x14002a240  mov     rcx, [rbp+3Fh+NewContext]
0x14002a244  add     rcx, 78h ; 'x'; Resource
0x14002a248  call    cs:__imp_ExInitializeResourceLite
0x14002a24f  nop     dword ptr [rax+rax+00h]
0x14002a254  mov     rcx, [rbp+3Fh+NewContext]
0x14002a258  lea     edx, [r14+1]; Type
0x14002a25c  add     rcx, 0E8h; Event
0x14002a263  mov     r8b, 1; State
0x14002a266  call    cs:__imp_KeInitializeEvent
0x14002a26d  nop     dword ptr [rax+rax+00h]
0x14002a272  mov     rax, [rbp+3Fh+NewContext]
0x14002a276  add     rax, 38h ; '8'
0x14002a27a  mov     [rax+8], rax
0x14002a27e  mov     [rax], rax
0x14002a281  test    rbx, rbx
0x14002a284  jz      loc_14002A364
0x14002a28a  cmp     [rbx], rbx
0x14002a28d  jz      loc_14002A364
0x14002a293  mov     rax, [rbp+3Fh+NewContext]
0x14002a297  mov     rcx, [rbp+3Fh+arg_28]
0x14002a29b  mov     [rax+48h], rcx
0x14002a29f  mov     rcx, [rbx]
0x14002a2a2  mov     rax, [rbp+3Fh+NewContext]
0x14002a2a6  mov     [rax+38h], rcx
0x14002a2aa  mov     rcx, [rbx+8]
0x14002a2ae  mov     rax, [rbp+3Fh+NewContext]
0x14002a2b2  mov     [rax+40h], rcx
0x14002a2b6  mov     rax, [rbx]
0x14002a2b9  mov     rcx, [rbp+3Fh+NewContext]
0x14002a2bd  add     rcx, 38h ; '8'
0x14002a2c1  mov     [rax+8], rcx
0x14002a2c5  mov     rax, [rbx+8]
0x14002a2c9  mov     rcx, [rbp+3Fh+NewContext]
0x14002a2cd  add     rcx, 38h ; '8'
0x14002a2d1  mov     [rax], rcx
0x14002a2d4  mov     rcx, [rbp+3Fh+NewContext]
0x14002a2d8  mov     [rbx+8], rbx
0x14002a2dc  mov     [rbx], rbx
0x14002a2df  call    WcGetSource
0x14002a2e4  mov     rdi, rax
0x14002a2e7  mov     rcx, [rax+20h]
0x14002a2eb  mov     edx, [rcx+10h]
0x14002a2ee  test    dl, 1
0x14002a2f1  jnz     short loc_14002A364
0x14002a2f3  mov     rcx, [rax]; Instance
0x14002a2f6  lea     rdx, [rbp+3Fh+Context]; Context
0x14002a2fa  call    cs:__imp_FltGetInstanceContext
0x14002a301  nop     dword ptr [rax+rax+00h]
0x14002a306  mov     ebx, eax
0x14002a308  test    eax, eax
0x14002a30a  js      loc_14002A611
0x14002a310  mov     rdx, [rdi+10h]; FileObject
0x14002a314  lea     rax, [rbp+3Fh+var_98]
0x14002a318  mov     rcx, [rdi]; Instance
0x14002a31b  lea     r9d, [r14+18h]; Length
0x14002a31f  mov     [rsp+0E0h+LengthReturned], rax; LengthReturned
0x14002a324  lea     r8, [rbp+3Fh+FileInformation]; FileInformation
0x14002a328  mov     dword ptr [rsp+0E0h+ReturnedContext], 3Bh ; ';'; FileInformationClass
0x14002a330  call    cs:__imp_FltQueryInformationFile
0x14002a337  nop     dword ptr [rax+rax+00h]
0x14002a33c  mov     ebx, eax
0x14002a33e  test    eax, eax
0x14002a340  js      loc_14002A611
0x14002a346  mov     rax, [rbp+3Fh+Context]
0x14002a34a  movups  xmm0, xmmword ptr [rax+28h]
0x14002a34e  mov     rax, [rbp+3Fh+NewContext]
0x14002a352  movdqu  xmmword ptr [rax+64h], xmm0
0x14002a357  mov     rax, [rbp+3Fh+NewContext]
0x14002a35b  movups  xmm1, [rbp+3Fh+FileInformation+8]
0x14002a35f  movdqu  xmmword ptr [rax+54h], xmm1
0x14002a364  mov     rax, [rbp+3Fh+NewContext]
0x14002a368  add     rax, 38h ; '8'
0x14002a36c  mov     rbx, [rax]
0x14002a36f  jmp     short loc_14002A39C
0x14002a371  mov     eax, [rbx+20h]
0x14002a374  test    al, 1
0x14002a376  jz      short loc_14002A391
0x14002a378  call    cs:__imp_FltAllocateGenericWorkItem
0x14002a37f  nop     dword ptr [rax+rax+00h]
0x14002a384  mov     [rbx+10h], rax
0x14002a388  test    rax, rax
0x14002a38b  jz      loc_14002A4A2
0x14002a391  mov     rax, [rbp+3Fh+NewContext]
0x14002a395  mov     rbx, [rbx]
0x14002a398  add     rax, 38h ; '8'
0x14002a39c  cmp     rbx, rax
0x14002a39f  jnz     short loc_14002A371
0x14002a3a1  mov     eax, [rsi+58h]
0x14002a3a4  lea     r14, WPP_950001495d7d34274b0ab8b7fcc7b560_Traceguids
0x14002a3ab  lea     rsi, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\wcifs\\context."...
0x14002a3b2  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002a3b9  test    al, 1
0x14002a3bb  jnz     loc_14002A533
0x14002a3c1  test    byte ptr [rbp+3Fh+arg_20], 10h
0x14002a3c5  jnz     loc_14002A533
0x14002a3cb  xor     bl, bl
0x14002a3cd  call    cs:__imp_IoGetTopLevelIrp
0x14002a3d4  nop     dword ptr [rax+rax+00h]
0x14002a3d9  test    rax, rax
0x14002a3dc  jnz     short loc_14002A3EF
0x14002a3de  lea     ecx, [rax+1]; Irp
0x14002a3e1  call    cs:__imp_IoSetTopLevelIrp
0x14002a3e8  nop     dword ptr [rax+rax+00h]
0x14002a3ed  mov     bl, 1
0x14002a3ef  mov     rcx, r15; FileObject
0x14002a3f2  call    cs:__imp_FsRtlAcquireFileExclusive
0x14002a3f9  nop     dword ptr [rax+rax+00h]
0x14002a3fe  mov     rcx, [r15+28h]; SectionObjectPointer
0x14002a402  lea     r9, [rbp+3Fh+IoStatus]; IoStatus
0x14002a406  xor     r8d, r8d; Length
0x14002a409  mov     dword ptr [rsp+0E0h+ReturnedContext], 0; Flags
0x14002a411  xor     edx, edx; FileOffset
0x14002a413  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x14002a41a  nop     dword ptr [rax+rax+00h]
0x14002a41f  test    bl, bl
0x14002a421  jz      short loc_14002A431
0x14002a423  xor     ecx, ecx; Irp
0x14002a425  call    cs:__imp_IoSetTopLevelIrp
0x14002a42c  nop     dword ptr [rax+rax+00h]
0x14002a431  mov     rcx, r15; FileObject
0x14002a434  call    cs:__imp_FsRtlReleaseFile
0x14002a43b  nop     dword ptr [rax+rax+00h]
0x14002a440  mov     ebx, dword ptr [rbp+3Fh+IoStatus]
0x14002a443  test    ebx, ebx
0x14002a445  jns     short loc_14002A4AC
0x14002a447  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002a44e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002a455  jz      loc_14002A611
0x14002a45b  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x14002a45f  mov     r9d, 0Ah
0x14002a465  mov     dword ptr [rsp+0E0h+var_B0], 25Bh
0x14002a46d  lea     rsi, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\wcifs\\context."...
0x14002a474  lea     r14, WPP_950001495d7d34274b0ab8b7fcc7b560_Traceguids
0x14002a47b  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002a482  mov     r8d, 5
0x14002a488  mov     [rsp+0E0h+LengthReturned], rsi
0x14002a48d  mov     dl, 2
0x14002a48f  mov     [rsp+0E0h+ReturnedContext], r14
0x14002a494  mov     rcx, [rcx+40h]
0x14002a498  call    WPP_RECORDER_SF_sDd
0x14002a49d  jmp     loc_14002A611
0x14002a4a2  mov     ebx, 0C000009Ah
0x14002a4a7  jmp     loc_14002A611
0x14002a4ac  mov     rcx, [rbp+3Fh+NewContext]
0x14002a4b0  call    WcIsSourceAvailable
0x14002a4b5  test    al, al
0x14002a4b7  jz      short loc_14002A4FC
0x14002a4b9  mov     r9, [rbp+3Fh+arg_28]
0x14002a4bd  mov     r8, rcx
0x14002a4c0  mov     rcx, r12; Instance
0x14002a4c3  mov     rdx, r15; FileObject
0x14002a4c6  call    WcSyncPlaceholderFileSize
0x14002a4cb  mov     ebx, eax
0x14002a4cd  test    eax, eax
0x14002a4cf  jns     short loc_14002A533
0x14002a4d1  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002a4d8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002a4df  jz      loc_14002A611
0x14002a4e5  mov     dword ptr [rsp+0E0h+var_A8], eax
0x14002a4e9  mov     r9d, 0Bh
0x14002a4ef  mov     dword ptr [rsp+0E0h+var_B0], 274h
0x14002a4f7  jmp     loc_14002A46D
0x14002a4fc  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002a503  jz      short loc_14002A533
0x14002a505  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002a50c  mov     r9d, 0Ch
0x14002a512  mov     dword ptr [rsp+0E0h+var_B0], 284h
0x14002a51a  mov     dl, 2
0x14002a51c  mov     [rsp+0E0h+LengthReturned], rsi
0x14002a521  mov     [rsp+0E0h+ReturnedContext], r14
0x14002a526  mov     rcx, [rcx+40h]
0x14002a52a  lea     r8d, [r9-7]
0x14002a52e  call    WPP_RECORDER_SF_sD
0x14002a533  mov     r9, [rbp+3Fh+NewContext]; NewContext
0x14002a537  lea     rax, [rbp+3Fh+OldContext]
0x14002a53b  mov     r8d, 1; Operation
0x14002a541  mov     [rsp+0E0h+ReturnedContext], rax; OldContext
0x14002a546  mov     rdx, r15; FileObject
0x14002a549  mov     rcx, r12; Instance
0x14002a54c  call    cs:__imp_FltSetStreamContext
0x14002a553  nop     dword ptr [rax+rax+00h]
0x14002a558  mov     ebx, eax
0x14002a55a  test    eax, eax
0x14002a55c  jns     short loc_14002A5A4
0x14002a55e  cmp     eax, 0C01C0002h
0x14002a563  jnz     short loc_14002A580
0x14002a565  mov     rcx, [rbp+3Fh+NewContext]; Context
0x14002a569  call    cs:__imp_FltReleaseContext
0x14002a570  nop     dword ptr [rax+rax+00h]
0x14002a575  mov     rax, [rbp+3Fh+OldContext]
0x14002a579  xor     ebx, ebx
0x14002a57b  jmp     loc_14002A602
0x14002a580  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002a587  jz      loc_14002A611
0x14002a58d  mov     dword ptr [rsp+0E0h+var_A8], eax
0x14002a591  mov     r9d, 0Dh
0x14002a597  mov     dword ptr [rsp+0E0h+var_B0], 29Bh
0x14002a59f  jmp     loc_14002A47B
0x14002a5a4  mov     eax, [r13+1Ch]
0x14002a5a8  sub     eax, 2
0x14002a5ab  cmp     eax, 1
0x14002a5ae  ja      short loc_14002A5FE
0x14002a5b0  lea     rdi, [r13+0C8h]
0x14002a5b7  mov     rcx, rdi; FastMutex
0x14002a5ba  call    cs:__imp_ExAcquireFastMutex
0x14002a5c1  nop     dword ptr [rax+rax+00h]
0x14002a5c6  lea     rcx, [r13+0B8h]
0x14002a5cd  mov     rdx, [rcx+8]
0x14002a5d1  cmp     [rdx], rcx
0x14002a5d4  jz      short loc_14002A5DD
0x14002a5d6  mov     ecx, 3
0x14002a5db  int     29h; Win8: RtlFailFast(ecx)
0x14002a5dd  mov     rax, [rbp+3Fh+NewContext]
0x14002a5e1  mov     [rax], rcx
0x14002a5e4  mov     [rax+8], rdx
0x14002a5e8  mov     [rdx], rax
0x14002a5eb  mov     [rcx+8], rax
0x14002a5ef  mov     rcx, rdi; FastMutex
0x14002a5f2  call    cs:__imp_ExReleaseFastMutex
0x14002a5f9  nop     dword ptr [rax+rax+00h]
0x14002a5fe  mov     rax, [rbp+3Fh+NewContext]
0x14002a602  mov     rcx, [rbp+3Fh+var_80]
0x14002a606  mov     [rbp+3Fh+NewContext], 0
0x14002a60e  mov     [rcx], rax
0x14002a611  mov     rcx, [rbp+3Fh+Context]; Context
0x14002a615  test    rcx, rcx
  ... truncated ...
```
