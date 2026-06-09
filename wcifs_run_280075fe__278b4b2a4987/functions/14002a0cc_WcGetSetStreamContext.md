# WcGetSetStreamContext

- ea: `0x14002a0cc`
- end: `0x14002a60e`
- name: `WcGetSetStreamContext`
- size: `1346`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, PFLT_CONTEXT Context@<r8>, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140027854`
- `0x140029608`

## callees

- `0x1400020c4`
- `0x1400024fc`
- `0x14000250c`
- `0x14000308c`
- `0x140004198`
- `0x140007c60`
- `0x1400080c0`
- `0x14002a0cc`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x14002a1f8`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002a1f8`
- `ntoskrnl!FsRtlAcquireFileExclusive` at `0x14002a3a2`
- `ntoskrnl!FsRtlAcquireFileExclusive` at `0x14002a3a2`
- `ntoskrnl!KeInitializeEvent` at `0x14002a216`
- `ntoskrnl!KeInitializeEvent` at `0x14002a216`
- `ntoskrnl!FsRtlReleaseFile` at `0x14002a3e4`
- `ntoskrnl!FsRtlReleaseFile` at `0x14002a3e4`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002a56a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002a56a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002a37d`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002a37d`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14002a3c3`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14002a3c3`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14002a391`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14002a3d5`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14002a391`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14002a3d5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002a5a2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002a5a2`
- `FLTMGR!FltAllocateContext` at `0x14002a153`
- `FLTMGR!FltAllocateContext` at `0x14002a153`
- `FLTMGR!FltSetStreamContext` at `0x14002a4fc`
- `FLTMGR!FltSetStreamContext` at `0x14002a4fc`
- `FLTMGR!FltQueryInformationFile` at `0x14002a2e0`
- `FLTMGR!FltQueryInformationFile` at `0x14002a2e0`
- `FLTMGR!FltReferenceContext` at `0x14002a178`
- `FLTMGR!FltReferenceContext` at `0x14002a178`
- `FLTMGR!FltReleaseContext` at `0x14002a519`
- `FLTMGR!FltReleaseContext` at `0x14002a5ca`
- `FLTMGR!FltReleaseContext` at `0x14002a5df`
- `FLTMGR!FltReleaseContext` at `0x14002a519`
- `FLTMGR!FltReleaseContext` at `0x14002a5ca`
- `FLTMGR!FltReleaseContext` at `0x14002a5df`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14002a328`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14002a328`
- `FLTMGR!FltGetInstanceContext` at `0x14002a2aa`
- `FLTMGR!FltGetInstanceContext` at `0x14002a2aa`

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
            WPP_GLOBAL_Control->DeviceExtension,
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
        WPP_GLOBAL_Control->DeviceExtension,
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
0x14002a0cc  push    rbp
0x14002a0ce  push    rbx
0x14002a0cf  push    rsi
0x14002a0d0  push    rdi
0x14002a0d1  push    r12
0x14002a0d3  push    r13
0x14002a0d5  push    r14
0x14002a0d7  push    r15
0x14002a0d9  lea     rbp, [rsp-7]
0x14002a0de  sub     rsp, 0A8h
0x14002a0e5  mov     rax, cs:__security_cookie
0x14002a0ec  xor     rax, rsp
0x14002a0ef  mov     [rbp+3Fh+var_50], rax
0x14002a0f3  mov     rax, [rbp+3Fh+arg_38]
0x14002a0fa  xor     r14d, r14d
0x14002a0fd  mov     rbx, [rbp+3Fh+arg_30]
0x14002a101  xorps   xmm0, xmm0
0x14002a104  mov     [rbp+3Fh+var_80], rax
0x14002a108  mov     r15, rdx
0x14002a10b  xor     eax, eax
0x14002a10d  mov     [rbp+3Fh+NewContext], r14
0x14002a111  mov     [rbp+3Fh+var_58], rax
0x14002a115  mov     r13, r9
0x14002a118  mov     rsi, r8
0x14002a11b  mov     [rbp+3Fh+OldContext], r14
0x14002a11f  mov     r12, rcx
0x14002a122  mov     [rbp+3Fh+var_98], r14d
0x14002a126  mov     rcx, cs:Globals; Filter
0x14002a12d  lea     edx, [rax+8]; ContextType
0x14002a130  lea     rax, [rbp+3Fh+NewContext]
0x14002a134  mov     [rbp+3Fh+Context], r14
0x14002a138  mov     edi, 108h
0x14002a13d  mov     [rsp+0E0h+ReturnedContext], rax; ReturnedContext
0x14002a142  mov     r9d, 200h; PoolType
0x14002a148  mov     r8d, edi; ContextSize
0x14002a14b  movups  [rbp+3Fh+FileInformation], xmm0
0x14002a14f  movups  xmmword ptr [rbp+3Fh+IoStatus], xmm0
0x14002a153  call    cs:__imp_FltAllocateContext
0x14002a15a  nop     dword ptr [rax+rax+00h]
0x14002a15f  test    eax, eax
0x14002a161  js      loc_14002A5ED
0x14002a167  mov     rcx, [rbp+3Fh+NewContext]; void *
0x14002a16b  mov     r8d, edi; Size
0x14002a16e  xor     edx, edx; Val
0x14002a170  call    memset
0x14002a175  mov     rcx, rsi; Context
0x14002a178  call    cs:__imp_FltReferenceContext
0x14002a17f  nop     dword ptr [rax+rax+00h]
0x14002a184  lock inc dword ptr [r13+0]
0x14002a189  mov     rax, [rbp+3Fh+NewContext]
0x14002a18d  mov     ecx, [rbp+3Fh+arg_20]
0x14002a190  mov     [rax+8], rax
0x14002a194  mov     [rax], rax
0x14002a197  mov     rax, [rbp+3Fh+NewContext]
0x14002a19b  mov     [rax+10h], r14d
0x14002a19f  mov     rax, [rbp+3Fh+NewContext]
0x14002a1a3  mov     [rax+14h], r14d
0x14002a1a7  mov     rax, [rbp+3Fh+NewContext]
0x14002a1ab  mov     [rax+20h], rsi
0x14002a1af  mov     rax, [rbp+3Fh+NewContext]
0x14002a1b3  mov     [rax+18h], ecx
0x14002a1b6  mov     rax, [rbp+3Fh+NewContext]
0x14002a1ba  mov     rcx, [r15+28h]
0x14002a1be  mov     [rax+30h], rcx
0x14002a1c2  mov     rax, [rbp+3Fh+NewContext]
0x14002a1c6  mov     [rax+100h], r14
0x14002a1cd  mov     rax, [rbp+3Fh+NewContext]
0x14002a1d1  mov     [rax+1Ch], r14b
0x14002a1d5  mov     rax, [rbp+3Fh+NewContext]
0x14002a1d9  mov     [rax+1Dh], r14b
0x14002a1dd  mov     rax, [rbp+3Fh+NewContext]
0x14002a1e1  mov     [rax+28h], r13
0x14002a1e5  mov     rax, [rbp+3Fh+NewContext]
0x14002a1e9  mov     [rax+0E0h], r14
0x14002a1f0  mov     rcx, [rbp+3Fh+NewContext]
0x14002a1f4  add     rcx, 78h ; 'x'; Resource
0x14002a1f8  call    cs:__imp_ExInitializeResourceLite
0x14002a1ff  nop     dword ptr [rax+rax+00h]
0x14002a204  mov     rcx, [rbp+3Fh+NewContext]
0x14002a208  lea     edx, [r14+1]; Type
0x14002a20c  add     rcx, 0E8h; Event
0x14002a213  mov     r8b, 1; State
0x14002a216  call    cs:__imp_KeInitializeEvent
0x14002a21d  nop     dword ptr [rax+rax+00h]
0x14002a222  mov     rax, [rbp+3Fh+NewContext]
0x14002a226  add     rax, 38h ; '8'
0x14002a22a  mov     [rax+8], rax
0x14002a22e  mov     [rax], rax
0x14002a231  test    rbx, rbx
0x14002a234  jz      loc_14002A314
0x14002a23a  cmp     [rbx], rbx
0x14002a23d  jz      loc_14002A314
0x14002a243  mov     rax, [rbp+3Fh+NewContext]
0x14002a247  mov     rcx, [rbp+3Fh+arg_28]
0x14002a24b  mov     [rax+48h], rcx
0x14002a24f  mov     rcx, [rbx]
0x14002a252  mov     rax, [rbp+3Fh+NewContext]
0x14002a256  mov     [rax+38h], rcx
0x14002a25a  mov     rcx, [rbx+8]
0x14002a25e  mov     rax, [rbp+3Fh+NewContext]
0x14002a262  mov     [rax+40h], rcx
0x14002a266  mov     rax, [rbx]
0x14002a269  mov     rcx, [rbp+3Fh+NewContext]
0x14002a26d  add     rcx, 38h ; '8'
0x14002a271  mov     [rax+8], rcx
0x14002a275  mov     rax, [rbx+8]
0x14002a279  mov     rcx, [rbp+3Fh+NewContext]
0x14002a27d  add     rcx, 38h ; '8'
0x14002a281  mov     [rax], rcx
0x14002a284  mov     rcx, [rbp+3Fh+NewContext]
0x14002a288  mov     [rbx+8], rbx
0x14002a28c  mov     [rbx], rbx
0x14002a28f  call    WcGetSource
0x14002a294  mov     rdi, rax
0x14002a297  mov     rcx, [rax+20h]
0x14002a29b  mov     edx, [rcx+10h]
0x14002a29e  test    dl, 1
0x14002a2a1  jnz     short loc_14002A314
0x14002a2a3  mov     rcx, [rax]; Instance
0x14002a2a6  lea     rdx, [rbp+3Fh+Context]; Context
0x14002a2aa  call    cs:__imp_FltGetInstanceContext
0x14002a2b1  nop     dword ptr [rax+rax+00h]
0x14002a2b6  mov     ebx, eax
0x14002a2b8  test    eax, eax
0x14002a2ba  js      loc_14002A5C1
0x14002a2c0  mov     rdx, [rdi+10h]; FileObject
0x14002a2c4  lea     rax, [rbp+3Fh+var_98]
0x14002a2c8  mov     rcx, [rdi]; Instance
0x14002a2cb  lea     r9d, [r14+18h]; Length
0x14002a2cf  mov     [rsp+0E0h+LengthReturned], rax; LengthReturned
0x14002a2d4  lea     r8, [rbp+3Fh+FileInformation]; FileInformation
0x14002a2d8  mov     dword ptr [rsp+0E0h+ReturnedContext], 3Bh ; ';'; FileInformationClass
0x14002a2e0  call    cs:__imp_FltQueryInformationFile
0x14002a2e7  nop     dword ptr [rax+rax+00h]
0x14002a2ec  mov     ebx, eax
0x14002a2ee  test    eax, eax
0x14002a2f0  js      loc_14002A5C1
0x14002a2f6  mov     rax, [rbp+3Fh+Context]
0x14002a2fa  movups  xmm0, xmmword ptr [rax+28h]
0x14002a2fe  mov     rax, [rbp+3Fh+NewContext]
0x14002a302  movdqu  xmmword ptr [rax+64h], xmm0
0x14002a307  mov     rax, [rbp+3Fh+NewContext]
0x14002a30b  movups  xmm1, [rbp+3Fh+FileInformation+8]
0x14002a30f  movdqu  xmmword ptr [rax+54h], xmm1
0x14002a314  mov     rax, [rbp+3Fh+NewContext]
0x14002a318  add     rax, 38h ; '8'
0x14002a31c  mov     rbx, [rax]
0x14002a31f  jmp     short loc_14002A34C
0x14002a321  mov     eax, [rbx+20h]
0x14002a324  test    al, 1
0x14002a326  jz      short loc_14002A341
0x14002a328  call    cs:__imp_FltAllocateGenericWorkItem
0x14002a32f  nop     dword ptr [rax+rax+00h]
0x14002a334  mov     [rbx+10h], rax
0x14002a338  test    rax, rax
0x14002a33b  jz      loc_14002A452
0x14002a341  mov     rax, [rbp+3Fh+NewContext]
0x14002a345  mov     rbx, [rbx]
0x14002a348  add     rax, 38h ; '8'
0x14002a34c  cmp     rbx, rax
0x14002a34f  jnz     short loc_14002A321
0x14002a351  mov     eax, [rsi+58h]
0x14002a354  lea     r14, WPP_950001495d7d34274b0ab8b7fcc7b560_Traceguids
0x14002a35b  lea     rsi, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\wcifs\\context."...
0x14002a362  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002a369  test    al, 1
0x14002a36b  jnz     loc_14002A4E3
0x14002a371  test    byte ptr [rbp+3Fh+arg_20], 10h
0x14002a375  jnz     loc_14002A4E3
0x14002a37b  xor     bl, bl
0x14002a37d  call    cs:__imp_IoGetTopLevelIrp
0x14002a384  nop     dword ptr [rax+rax+00h]
0x14002a389  test    rax, rax
0x14002a38c  jnz     short loc_14002A39F
0x14002a38e  lea     ecx, [rax+1]; Irp
0x14002a391  call    cs:__imp_IoSetTopLevelIrp
0x14002a398  nop     dword ptr [rax+rax+00h]
0x14002a39d  mov     bl, 1
0x14002a39f  mov     rcx, r15; FileObject
0x14002a3a2  call    cs:__imp_FsRtlAcquireFileExclusive
0x14002a3a9  nop     dword ptr [rax+rax+00h]
0x14002a3ae  mov     rcx, [r15+28h]; SectionObjectPointer
0x14002a3b2  lea     r9, [rbp+3Fh+IoStatus]; IoStatus
0x14002a3b6  xor     r8d, r8d; Length
0x14002a3b9  mov     dword ptr [rsp+0E0h+ReturnedContext], 0; Flags
0x14002a3c1  xor     edx, edx; FileOffset
0x14002a3c3  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x14002a3ca  nop     dword ptr [rax+rax+00h]
0x14002a3cf  test    bl, bl
0x14002a3d1  jz      short loc_14002A3E1
0x14002a3d3  xor     ecx, ecx; Irp
0x14002a3d5  call    cs:__imp_IoSetTopLevelIrp
0x14002a3dc  nop     dword ptr [rax+rax+00h]
0x14002a3e1  mov     rcx, r15; FileObject
0x14002a3e4  call    cs:__imp_FsRtlReleaseFile
0x14002a3eb  nop     dword ptr [rax+rax+00h]
0x14002a3f0  mov     ebx, dword ptr [rbp+3Fh+IoStatus]
0x14002a3f3  test    ebx, ebx
0x14002a3f5  jns     short loc_14002A45C
0x14002a3f7  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002a3fe  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002a405  jz      loc_14002A5C1
0x14002a40b  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x14002a40f  mov     r9d, 0Ah
0x14002a415  mov     dword ptr [rsp+0E0h+var_B0], 25Bh
0x14002a41d  lea     rsi, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\wcifs\\context."...
0x14002a424  lea     r14, WPP_950001495d7d34274b0ab8b7fcc7b560_Traceguids
0x14002a42b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a432  mov     r8d, 5
0x14002a438  mov     [rsp+0E0h+LengthReturned], rsi
0x14002a43d  mov     dl, 2
0x14002a43f  mov     [rsp+0E0h+ReturnedContext], r14
0x14002a444  mov     rcx, [rcx+40h]
0x14002a448  call    WPP_RECORDER_SF_sDd
0x14002a44d  jmp     loc_14002A5C1
0x14002a452  mov     ebx, 0C000009Ah
0x14002a457  jmp     loc_14002A5C1
0x14002a45c  mov     rcx, [rbp+3Fh+NewContext]
0x14002a460  call    WcIsSourceAvailable
0x14002a465  test    al, al
0x14002a467  jz      short loc_14002A4AC
0x14002a469  mov     r9, [rbp+3Fh+arg_28]
0x14002a46d  mov     r8, rcx
0x14002a470  mov     rcx, r12; Instance
0x14002a473  mov     rdx, r15; FileObject
0x14002a476  call    WcSyncPlaceholderFileSize
0x14002a47b  mov     ebx, eax
0x14002a47d  test    eax, eax
0x14002a47f  jns     short loc_14002A4E3
0x14002a481  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002a488  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002a48f  jz      loc_14002A5C1
0x14002a495  mov     dword ptr [rsp+0E0h+var_A8], eax
0x14002a499  mov     r9d, 0Bh
0x14002a49f  mov     dword ptr [rsp+0E0h+var_B0], 274h
0x14002a4a7  jmp     loc_14002A41D
0x14002a4ac  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002a4b3  jz      short loc_14002A4E3
0x14002a4b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a4bc  mov     r9d, 0Ch
0x14002a4c2  mov     dword ptr [rsp+0E0h+var_B0], 284h
0x14002a4ca  mov     dl, 2
0x14002a4cc  mov     [rsp+0E0h+LengthReturned], rsi
0x14002a4d1  mov     [rsp+0E0h+ReturnedContext], r14
0x14002a4d6  mov     rcx, [rcx+40h]
0x14002a4da  lea     r8d, [r9-7]
0x14002a4de  call    WPP_RECORDER_SF_sD
0x14002a4e3  mov     r9, [rbp+3Fh+NewContext]; NewContext
0x14002a4e7  lea     rax, [rbp+3Fh+OldContext]
0x14002a4eb  mov     r8d, 1; Operation
0x14002a4f1  mov     [rsp+0E0h+ReturnedContext], rax; OldContext
0x14002a4f6  mov     rdx, r15; FileObject
0x14002a4f9  mov     rcx, r12; Instance
0x14002a4fc  call    cs:__imp_FltSetStreamContext
0x14002a503  nop     dword ptr [rax+rax+00h]
0x14002a508  mov     ebx, eax
0x14002a50a  test    eax, eax
0x14002a50c  jns     short loc_14002A554
0x14002a50e  cmp     eax, 0C01C0002h
0x14002a513  jnz     short loc_14002A530
0x14002a515  mov     rcx, [rbp+3Fh+NewContext]; Context
0x14002a519  call    cs:__imp_FltReleaseContext
0x14002a520  nop     dword ptr [rax+rax+00h]
0x14002a525  mov     rax, [rbp+3Fh+OldContext]
0x14002a529  xor     ebx, ebx
0x14002a52b  jmp     loc_14002A5B2
0x14002a530  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002a537  jz      loc_14002A5C1
0x14002a53d  mov     dword ptr [rsp+0E0h+var_A8], eax
0x14002a541  mov     r9d, 0Dh
0x14002a547  mov     dword ptr [rsp+0E0h+var_B0], 29Bh
0x14002a54f  jmp     loc_14002A42B
0x14002a554  mov     eax, [r13+1Ch]
0x14002a558  sub     eax, 2
0x14002a55b  cmp     eax, 1
0x14002a55e  ja      short loc_14002A5AE
0x14002a560  lea     rdi, [r13+0C8h]
0x14002a567  mov     rcx, rdi; FastMutex
0x14002a56a  call    cs:__imp_ExAcquireFastMutex
0x14002a571  nop     dword ptr [rax+rax+00h]
0x14002a576  lea     rcx, [r13+0B8h]
0x14002a57d  mov     rdx, [rcx+8]
0x14002a581  cmp     [rdx], rcx
0x14002a584  jz      short loc_14002A58D
0x14002a586  mov     ecx, 3
0x14002a58b  int     29h; Win8: RtlFailFast(ecx)
0x14002a58d  mov     rax, [rbp+3Fh+NewContext]
0x14002a591  mov     [rax], rcx
0x14002a594  mov     [rax+8], rdx
0x14002a598  mov     [rdx], rax
0x14002a59b  mov     [rcx+8], rax
0x14002a59f  mov     rcx, rdi; FastMutex
0x14002a5a2  call    cs:__imp_ExReleaseFastMutex
0x14002a5a9  nop     dword ptr [rax+rax+00h]
0x14002a5ae  mov     rax, [rbp+3Fh+NewContext]
0x14002a5b2  mov     rcx, [rbp+3Fh+var_80]
0x14002a5b6  mov     [rbp+3Fh+NewContext], 0
0x14002a5be  mov     [rcx], rax
0x14002a5c1  mov     rcx, [rbp+3Fh+Context]; Context
0x14002a5c5  test    rcx, rcx
  ... truncated ...
```
