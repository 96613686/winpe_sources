# WcPreCleanup

- ea: `0x140034410`
- end: `0x140034bec`
- name: `WcPreCleanup`
- size: `2012`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140001500`
- `0x1400016f0`
- `0x1400020c4`
- `0x140007c60`
- `0x14001bcec`
- `0x1400278a4`
- `0x140029658`
- `0x14002d648`
- `0x140034410`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400345cb`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400345cb`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400345b3`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400345dd`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400345b3`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400345dd`
- `ntoskrnl!EtwWriteTransfer` at `0x140034b97`
- `ntoskrnl!EtwWriteTransfer` at `0x140034b97`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140034585`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140034585`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400344e9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400348e4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400344e9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400348e4`
- `ntoskrnl!ObfDereferenceObject` at `0x140034694`
- `ntoskrnl!ObfDereferenceObject` at `0x1400346be`
- `ntoskrnl!ObfDereferenceObject` at `0x140034694`
- `ntoskrnl!ObfDereferenceObject` at `0x1400346be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003462d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003462d`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400345fc`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400345fc`
- `ntoskrnl!ExReleaseFastMutex` at `0x140034619`
- `ntoskrnl!ExReleaseFastMutex` at `0x140034619`
- `FLTMGR!FltCreateFileEx2` at `0x14003482c`
- `FLTMGR!FltCreateFileEx2` at `0x14003482c`
- `FLTMGR!FltClose` at `0x140034680`
- `FLTMGR!FltClose` at `0x1400346a9`
- `FLTMGR!FltClose` at `0x140034680`
- `FLTMGR!FltClose` at `0x1400346a9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003456a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003456a`
- `FLTMGR!FltGetFileNameInformation` at `0x140034788`
- `FLTMGR!FltGetFileNameInformation` at `0x140034933`
- `FLTMGR!FltGetFileNameInformation` at `0x140034788`
- `FLTMGR!FltGetFileNameInformation` at `0x140034933`
- `FLTMGR!FltParseFileNameInformation` at `0x14003494b`
- `FLTMGR!FltParseFileNameInformation` at `0x14003494b`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400344a8`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400344a8`
- `FLTMGR!FltReleaseContext` at `0x140034642`
- `FLTMGR!FltReleaseContext` at `0x140034656`
- `FLTMGR!FltReleaseContext` at `0x14003466b`
- `FLTMGR!FltReleaseContext` at `0x1400346d3`
- `FLTMGR!FltReleaseContext` at `0x1400346e8`
- `FLTMGR!FltReleaseContext` at `0x140034642`
- `FLTMGR!FltReleaseContext` at `0x140034656`
- `FLTMGR!FltReleaseContext` at `0x14003466b`
- `FLTMGR!FltReleaseContext` at `0x1400346d3`
- `FLTMGR!FltReleaseContext` at `0x1400346e8`

## pseudocode

```c
__int64 __fastcall WcPreCleanup(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rbx
  struct _FILE_OBJECT *v5; // rdx
  struct _FLT_INSTANCE *v8; // rcx
  struct _FILE_OBJECT *v9; // r12
  __int64 UnionContext; // rdi
  _QWORD *v11; // rax
  int v12; // edx
  int v13; // r9d
  unsigned int v14; // r13d
  _BYTE *v15; // rsi
  PVOID i; // rax
  struct _FLT_INSTANCE *v18; // rdx
  NTSTATUS v19; // eax
  __int16 v20; // cx
  __int16 v21; // ax
  struct _FLT_INSTANCE *v22; // rcx
  int SetContextFileObject; // eax
  char v24; // r9
  int v25; // eax
  int v26; // edx
  int DesiredAccess; // [rsp+20h] [rbp-E0h]
  char IoStatusBlock; // [rsp+30h] [rbp-D0h]
  PLARGE_INTEGER AllocationSize; // [rsp+38h] [rbp-C8h]
  char v30; // [rsp+80h] [rbp-80h] BYREF
  char v31; // [rsp+81h] [rbp-7Fh] BYREF
  PFLT_CONTEXT v32; // [rsp+88h] [rbp-78h] BYREF
  int v33; // [rsp+90h] [rbp-70h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+98h] [rbp-68h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE v36; // [rsp+A8h] [rbp-58h] BYREF
  PFLT_CONTEXT Context; // [rsp+B0h] [rbp-50h] BYREF
  PFLT_CONTEXT v38; // [rsp+B8h] [rbp-48h] BYREF
  HANDLE FileHandle; // [rsp+C0h] [rbp-40h] BYREF
  PVOID Object; // [rsp+C8h] [rbp-38h] BYREF
  PFLT_CONTEXT v41; // [rsp+D0h] [rbp-30h] BYREF
  PFLT_CONTEXT v42; // [rsp+D8h] [rbp-28h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+E0h] [rbp-20h] BYREF
  __m128i Name; // [rsp+F0h] [rbp-10h] BYREF
  PFLT_CALLBACK_DATA CallbackDataa; // [rsp+100h] [rbp+0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+108h] [rbp+8h] BYREF
  struct _IO_STATUS_BLOCK v47; // [rsp+138h] [rbp+38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+150h] [rbp+50h] BYREF
  char *v49; // [rsp+160h] [rbp+60h]
  int v50; // [rsp+168h] [rbp+68h]
  int v51; // [rsp+16Ch] [rbp+6Ch]
  char *v52; // [rsp+170h] [rbp+70h]
  __int64 v53; // [rsp+178h] [rbp+78h]
  char *v54; // [rsp+180h] [rbp+80h]
  __int64 v55; // [rsp+188h] [rbp+88h]
  int *v56; // [rsp+190h] [rbp+90h]
  __int64 v57; // [rsp+198h] [rbp+98h]

  v3 = 0;
  *(_QWORD *)&EventDescriptor.Id = a3;
  CallbackDataa = CallbackData;
  v32 = 0;
  v5 = *(struct _FILE_OBJECT **)(a2 + 32);
  v38 = 0;
  v8 = *(struct _FLT_INSTANCE **)(a2 + 24);
  Context = 0;
  FileNameInformation = 0;
  v9 = 0;
  Name = 0;
  FileHandle = 0;
  UnionContext = 0;
  FileObject = 0;
  v30 = 0;
  v36 = 0;
  memset(&ObjectAttributes, 0, 44);
  Object = 0;
  v42 = 0;
  v47 = 0;
  v41 = 0;
  if ( FltGetStreamHandleContext(v8, v5, &Context) >= 0 && (*((_DWORD *)Context + 10) & 1) != 0 )
  {
    v33 = WcPrepareForDelete(CallbackData, a2);
    if ( v33 < 0 )
    {
      v11 = ExAllocateFromPagedLookasideList(&stru_14000E500);
      v3 = v11;
      if ( v11 )
      {
        *((_BYTE *)v11 + 17) = 1;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 2;
          WPP_RECORDER_SF_sDd(
            wil_details_featureDescriptors_a->DeviceExtension,
            v12,
            5,
            55,
            (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
            131,
            v33);
        }
        if ( FltGetFileNameInformation(CallbackDataa, 0x101u, &FileNameInformation) >= 0 )
        {
          v18 = *(struct _FLT_INSTANCE **)(a2 + 24);
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &FileNameInformation->Name;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v19 = FltCreateFileEx2(
                  Globals,
                  v18,
                  &v36,
                  (PFILE_OBJECT *)&Object,
                  0x10000u,
                  &ObjectAttributes,
                  &v47,
                  0,
                  0x80u,
                  3u,
                  1u,
                  0x200000u,
                  0,
                  0,
                  0x800u,
                  0);
          if ( v19 >= 0 )
          {
            v14 = 5;
            *v3 = 0;
            v3[1] = 0;
            v3[3] = v36;
            v36 = 0;
            **(_QWORD **)&EventDescriptor.Id = v3;
            v3 = 0;
            goto LABEL_9;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(AllocationSize) = v19;
            v13 = 56;
            IoStatusBlock = -89;
            goto LABEL_7;
          }
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(AllocationSize) = -1073741670;
        v13 = 54;
        IoStatusBlock = 125;
LABEL_7:
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v12,
          5,
          v13,
          (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
          IoStatusBlock,
          AllocationSize);
      }
LABEL_8:
      v14 = 1;
LABEL_9:
      v15 = v32;
      goto LABEL_10;
    }
  }
  if ( !WcGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &v38, &v32) )
    goto LABEL_8;
  v15 = v32;
  if ( !v32 )
    goto LABEL_73;
  UnionContext = WcGetUnionContext(
                   CallbackData,
                   *(struct _FLT_INSTANCE **)(a2 + 24),
                   *(struct _FILE_OBJECT **)(a2 + 32));
  if ( !UnionContext || !v15[28] )
  {
    v14 = 0;
    v3 = 0;
    goto LABEL_10;
  }
  v3 = ExAllocateFromPagedLookasideList(&stru_14000E500);
  if ( !v3 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_8;
    LODWORD(AllocationSize) = -1073741670;
    v13 = 57;
    IoStatusBlock = -53;
    goto LABEL_7;
  }
  if ( FltGetFileNameInformation(CallbackData, 0x301u, &FileNameInformation) < 0
    || FltParseFileNameInformation(FileNameInformation) < 0 )
  {
LABEL_73:
    v14 = 1;
    goto LABEL_10;
  }
  Name = (__m128i)FileNameInformation->Name;
  v20 = _mm_cvtsi128_si32(Name) - FileNameInformation->FinalComponent.Length;
  v21 = v20 - 2;
  Name.m128i_i16[0] = v20 - 2;
  if ( v20 - 2 == FileNameInformation->Volume.Length )
    v21 = v20;
  v22 = *(struct _FLT_INSTANCE **)(a2 + 24);
  Name.m128i_i16[0] = v21;
  if ( (int)WcOpenPlaceHolder(
              v22,
              (__int64)&Name,
              0x29u,
              *(_DWORD *)(UnionContext + 36),
              &FileHandle,
              (PVOID *)&FileObject,
              &v30) < 0
    || !v30 )
  {
    v9 = FileObject;
    goto LABEL_73;
  }
  v9 = FileObject;
  SetContextFileObject = WcGetSetContextFileObject(
                           *(PFLT_INSTANCE *)(a2 + 24),
                           FileObject,
                           UnionContext,
                           1,
                           DesiredAccess,
                           &v41,
                           &v42);
  if ( SetContextFileObject < 0 || SetContextFileObject == 260 )
    goto LABEL_73;
  *((_BYTE *)v3 + 16) = 0;
  v24 = 0;
  if ( (*((_DWORD *)v15 + 6) & 0x10) != 0 )
  {
    *((_BYTE *)v3 + 16) = 1;
    v24 = 1;
  }
  v25 = WcAddInMemoryTombstone(
          (__int64)CallbackData,
          *(struct _FLT_INSTANCE **)(a2 + 24),
          &FileNameInformation->FinalComponent,
          v24,
          v9);
  v33 = v25;
  v26 = v25;
  if ( v25 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v26) = 2;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v26,
        5,
        58,
        (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
        25,
        v25);
      v26 = v33;
    }
    if ( (unsigned int)dword_14000E060 > 5
      && (qword_14000E070 & 0x400000000000LL) != 0
      && (qword_14000E078 & 0x400000000000LL) == qword_14000E078 )
    {
      v33 = v26;
      v52 = &v30;
      EventDescriptor.Keyword = 0x400000000000LL;
      v54 = &v31;
      v30 = 3;
      v56 = &v33;
      v14 = 1;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_14000E068;
      v53 = 1;
      v31 = 4;
      v55 = 1;
      v57 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      UserData.Size = *(unsigned __int16 *)off_14000E068;
      v49 = byte_14000BE61;
      UserData.Reserved = 2;
      v50 = 82;
      v51 = 1;
      LODWORD(FileObject) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
      goto LABEL_9;
    }
    goto LABEL_8;
  }
  *((_BYTE *)v3 + 17) = 0;
  v3[3] = 0;
  v14 = 0;
  *v3 = FileNameInformation;
  FileNameInformation = 0;
  v3[1] = v9;
  v9 = 0;
  *a3 = v3;
  v3 = 0;
LABEL_10:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v3 )
    ExFreeToPagedLookasideList(&stru_14000E500, v3);
  if ( UnionContext && _InterlockedExchangeAdd((volatile signed __int32 *)UnionContext, 0xFFFFFFFF) == 1 )
  {
    for ( i = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(UnionContext + 64), 1u);
          i;
          i = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(UnionContext + 64), 0) )
    {
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(UnionContext + 64), i);
    }
    if ( (*(_DWORD *)(UnionContext + 32) & 1) != 0 )
    {
      ExAcquireFastMutex(&FastMutex);
      --dword_14000E244;
      *(_DWORD *)(UnionContext + 32) &= ~1u;
      ExReleaseFastMutex(&FastMutex);
    }
    ExFreePoolWithTag((PVOID)UnionContext, 0x63754357u);
  }
  if ( v38 )
    FltReleaseContext(v38);
  if ( v15 )
    FltReleaseContext(v15);
  if ( Context )
    FltReleaseContext(Context);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v9 )
    ObfDereferenceObject(v9);
  if ( v36 )
    FltClose(v36);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( v41 )
    FltReleaseContext(v41);
  if ( v42 )
    FltReleaseContext(v42);
  return v14;
}

```

## disassembly

```asm
0x140034410  mov     [rsp-8+arg_18], rbx
0x140034415  push    rbp
0x140034416  push    rsi
0x140034417  push    rdi
0x140034418  push    r12
0x14003441a  push    r13
0x14003441c  push    r14
0x14003441e  push    r15
0x140034420  lea     rbp, [rsp-0B0h]
0x140034428  sub     rsp, 1B0h
0x14003442f  mov     rax, cs:__security_cookie
0x140034436  xor     rax, rsp
0x140034439  mov     [rbp+0E0h+var_40], rax
0x140034440  xor     ebx, ebx
0x140034442  mov     qword ptr [rbp+0E0h+EventDescriptor.Id], r8
0x140034446  xorps   xmm0, xmm0
0x140034449  mov     [rbp+0E0h+CallbackData], rcx
0x14003444d  mov     r13, rdx
0x140034450  mov     [rbp+0E0h+var_158], rbx
0x140034454  mov     rdx, [rdx+20h]; FileObject
0x140034458  mov     r15, r8
0x14003445b  mov     r14, rcx
0x14003445e  mov     [rbp+0E0h+var_128], rbx
0x140034462  movups  xmmword ptr [rbp+0E0h+var_D8.ObjectName], xmm0
0x140034466  mov     rcx, [r13+18h]; Instance
0x14003446a  lea     r8, [rbp+0E0h+Context]; Context
0x14003446e  xor     eax, eax
0x140034470  mov     [rbp+0E0h+Context], rbx
0x140034474  mov     [rbp+0E0h+FileNameInformation], rbx
0x140034478  mov     r12d, ebx
0x14003447b  movups  [rbp+0E0h+var_F0], xmm0
0x14003447f  mov     [rbp+0E0h+FileHandle], rbx
0x140034483  mov     edi, ebx
0x140034485  mov     [rbp+0E0h+FileObject], rbx
0x140034489  mov     [rbp+0E0h+var_160], bl
0x14003448c  mov     [rbp+0E0h+var_138], rbx
0x140034490  movups  xmmword ptr [rbp+0E0h+var_D8.Length], xmm0
0x140034494  mov     [rbp+0E0h+Object], rbx
0x140034498  movups  xmmword ptr [rbp+0E0h+var_D8+1Ch], xmm0
0x14003449c  mov     [rbp+0E0h+var_108], rbx
0x1400344a0  movups  xmmword ptr [rbp+0E0h+var_A8], xmm0
0x1400344a4  mov     [rbp+0E0h+var_110], rbx
0x1400344a8  call    cs:__imp_FltGetStreamHandleContext
0x1400344af  nop     dword ptr [rax+rax+00h]
0x1400344b4  test    eax, eax
0x1400344b6  js      loc_14003488E
0x1400344bc  mov     rax, [rbp+0E0h+Context]
0x1400344c0  mov     ecx, [rax+28h]
0x1400344c3  test    cl, 1
0x1400344c6  jz      loc_14003488E
0x1400344cc  mov     rdx, r13
0x1400344cf  mov     rcx, r14; CallbackData
0x1400344d2  call    WcPrepareForDelete
0x1400344d7  mov     [rbp+0E0h+var_150], eax
0x1400344da  test    eax, eax
0x1400344dc  jns     loc_14003488E
0x1400344e2  lea     rcx, stru_14000E500; Lookaside
0x1400344e9  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400344f0  nop     dword ptr [rax+rax+00h]
0x1400344f5  mov     rbx, rax
0x1400344f8  test    rax, rax
0x1400344fb  jnz     loc_140034722
0x140034501  lea     rsi, WPP_RECORDER_INITIALIZED
0x140034508  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14003450f  jz      short loc_140034557
0x140034511  mov     dword ptr [rsp+1E0h+AllocationSize], 0C000009Ah
0x140034519  mov     r9d, 36h ; '6'
0x14003451f  mov     dword ptr [rsp+1E0h+IoStatusBlock], 87Dh
0x140034527  lea     r14, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x14003452e  mov     [rsp+1E0h+ObjectAttributes], r14
0x140034533  lea     r15, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x14003453a  mov     rcx, cs:wil_details_featureDescriptors_a
0x140034541  mov     r8d, 5
0x140034547  mov     dl, 2
0x140034549  mov     qword ptr [rsp+1E0h+DesiredAccess], r15
0x14003454e  mov     rcx, [rcx+40h]
0x140034552  call    WPP_RECORDER_SF_sDd
0x140034557  mov     r13d, 1
0x14003455d  mov     rsi, [rbp+0E0h+var_158]
0x140034561  mov     rcx, [rbp+0E0h+FileNameInformation]; FileNameInformation
0x140034565  test    rcx, rcx
0x140034568  jz      short loc_140034576
0x14003456a  call    cs:__imp_FltReleaseFileNameInformation
0x140034571  nop     dword ptr [rax+rax+00h]
0x140034576  test    rbx, rbx
0x140034579  jz      short loc_140034591
0x14003457b  mov     rdx, rbx; Entry
0x14003457e  lea     rcx, stru_14000E500; Lookaside
0x140034585  call    cs:__imp_ExFreeToPagedLookasideList
0x14003458c  nop     dword ptr [rax+rax+00h]
0x140034591  test    rdi, rdi
0x140034594  jz      loc_140034639
0x14003459a  mov     eax, 0FFFFFFFFh
0x14003459f  lock xadd [rdi], eax
0x1400345a3  cmp     eax, 1
0x1400345a6  jnz     loc_140034639
0x1400345ac  movzx   edx, al; Restart
0x1400345af  lea     rcx, [rdi+40h]; Table
0x1400345b3  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400345ba  nop     dword ptr [rax+rax+00h]
0x1400345bf  test    rax, rax
0x1400345c2  jz      short loc_1400345EE
0x1400345c4  mov     rdx, rax; Buffer
0x1400345c7  lea     rcx, [rdi+40h]; Table
0x1400345cb  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400345d2  nop     dword ptr [rax+rax+00h]
0x1400345d7  xor     edx, edx; Restart
0x1400345d9  lea     rcx, [rdi+40h]; Table
0x1400345dd  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400345e4  nop     dword ptr [rax+rax+00h]
0x1400345e9  test    rax, rax
0x1400345ec  jnz     short loc_1400345C4
0x1400345ee  mov     eax, [rdi+20h]
0x1400345f1  test    al, 1
0x1400345f3  jz      short loc_140034625
0x1400345f5  lea     rcx, FastMutex; FastMutex
0x1400345fc  call    cs:__imp_ExAcquireFastMutex
0x140034603  nop     dword ptr [rax+rax+00h]
0x140034608  dec     cs:dword_14000E244
0x14003460e  lea     rcx, FastMutex; FastMutex
0x140034615  and     dword ptr [rdi+20h], 0FFFFFFFEh
0x140034619  call    cs:__imp_ExReleaseFastMutex
0x140034620  nop     dword ptr [rax+rax+00h]
0x140034625  mov     edx, 63754357h; Tag
0x14003462a  mov     rcx, rdi; P
0x14003462d  call    cs:__imp_ExFreePoolWithTag
0x140034634  nop     dword ptr [rax+rax+00h]
0x140034639  mov     rcx, [rbp+0E0h+var_128]; Context
0x14003463d  test    rcx, rcx
0x140034640  jz      short loc_14003464E
0x140034642  call    cs:__imp_FltReleaseContext
0x140034649  nop     dword ptr [rax+rax+00h]
0x14003464e  test    rsi, rsi
0x140034651  jz      short loc_140034662
0x140034653  mov     rcx, rsi; Context
0x140034656  call    cs:__imp_FltReleaseContext
0x14003465d  nop     dword ptr [rax+rax+00h]
0x140034662  mov     rcx, [rbp+0E0h+Context]; Context
0x140034666  test    rcx, rcx
0x140034669  jz      short loc_140034677
0x14003466b  call    cs:__imp_FltReleaseContext
0x140034672  nop     dword ptr [rax+rax+00h]
0x140034677  mov     rcx, [rbp+0E0h+FileHandle]; FileHandle
0x14003467b  test    rcx, rcx
0x14003467e  jz      short loc_14003468C
0x140034680  call    cs:__imp_FltClose
0x140034687  nop     dword ptr [rax+rax+00h]
0x14003468c  test    r12, r12
0x14003468f  jz      short loc_1400346A0
0x140034691  mov     rcx, r12; Object
0x140034694  call    cs:__imp_ObfDereferenceObject
0x14003469b  nop     dword ptr [rax+rax+00h]
0x1400346a0  mov     rcx, [rbp+0E0h+var_138]; FileHandle
0x1400346a4  test    rcx, rcx
0x1400346a7  jz      short loc_1400346B5
0x1400346a9  call    cs:__imp_FltClose
0x1400346b0  nop     dword ptr [rax+rax+00h]
0x1400346b5  mov     rcx, [rbp+0E0h+Object]; Object
0x1400346b9  test    rcx, rcx
0x1400346bc  jz      short loc_1400346CA
0x1400346be  call    cs:__imp_ObfDereferenceObject
0x1400346c5  nop     dword ptr [rax+rax+00h]
0x1400346ca  mov     rcx, [rbp+0E0h+var_110]; Context
0x1400346ce  test    rcx, rcx
0x1400346d1  jz      short loc_1400346DF
0x1400346d3  call    cs:__imp_FltReleaseContext
0x1400346da  nop     dword ptr [rax+rax+00h]
0x1400346df  mov     rcx, [rbp+0E0h+var_108]; Context
0x1400346e3  test    rcx, rcx
0x1400346e6  jz      short loc_1400346F4
0x1400346e8  call    cs:__imp_FltReleaseContext
0x1400346ef  nop     dword ptr [rax+rax+00h]
0x1400346f4  mov     eax, r13d
0x1400346f7  mov     rcx, [rbp+0E0h+var_40]
0x1400346fe  xor     rcx, rsp; StackCookie
0x140034701  call    __security_check_cookie
0x140034706  mov     rbx, [rsp+1E0h+arg_18]
0x14003470e  add     rsp, 1B0h
0x140034715  pop     r15
0x140034717  pop     r14
0x140034719  pop     r13
0x14003471b  pop     r12
0x14003471d  pop     rdi
0x14003471e  pop     rsi
0x14003471f  pop     rbp
0x140034720  retn
0x140034722  mov     byte ptr [rax+11h], 1
0x140034726  lea     rsi, WPP_RECORDER_INITIALIZED
0x14003472d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140034734  lea     r14, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x14003473b  lea     r15, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140034742  jz      short loc_14003477B
0x140034744  mov     rcx, cs:wil_details_featureDescriptors_a
0x14003474b  mov     r9d, 37h ; '7'
0x140034751  mov     eax, [rbp+0E0h+var_150]
0x140034754  mov     r8d, 5
0x14003475a  mov     dword ptr [rsp+1E0h+AllocationSize], eax
0x14003475e  mov     dl, 2
0x140034760  mov     dword ptr [rsp+1E0h+IoStatusBlock], 883h
0x140034768  mov     rcx, [rcx+40h]
0x14003476c  mov     [rsp+1E0h+ObjectAttributes], r14
0x140034771  mov     qword ptr [rsp+1E0h+DesiredAccess], r15
0x140034776  call    WPP_RECORDER_SF_sDd
0x14003477b  mov     rcx, [rbp+0E0h+CallbackData]; CallbackData
0x14003477f  lea     r8, [rbp+0E0h+FileNameInformation]; FileNameInformation
0x140034783  mov     edx, 101h; NameOptions
0x140034788  call    cs:__imp_FltGetFileNameInformation
0x14003478f  nop     dword ptr [rax+rax+00h]
0x140034794  test    eax, eax
0x140034796  js      loc_140034557
0x14003479c  mov     rax, [rbp+0E0h+FileNameInformation]
0x1400347a0  lea     r9, [rbp+0E0h+Object]; FileObject
0x1400347a4  mov     rdx, [r13+18h]; Instance
0x1400347a8  lea     r8, [rbp+0E0h+var_138]; FileHandle
0x1400347ac  xor     ecx, ecx
0x1400347ae  mov     [rbp+0E0h+var_D8.Length], 30h ; '0'
0x1400347b5  mov     [rsp+1E0h+DriverContext], rcx; DriverContext
0x1400347ba  add     rax, 8
0x1400347be  mov     [rsp+1E0h+Flags], 800h; Flags
0x1400347c6  xorps   xmm0, xmm0
0x1400347c9  mov     [rsp+1E0h+EaLength], ecx; EaLength
0x1400347cd  mov     [rsp+1E0h+EaBuffer], rcx; EaBuffer
0x1400347d2  mov     [rsp+1E0h+CreateOptions], 200000h; CreateOptions
0x1400347da  mov     [rsp+1E0h+CreateDisposition], 1; CreateDisposition
0x1400347e2  mov     [rsp+1E0h+ShareAccess], 3; ShareAccess
0x1400347ea  mov     [rsp+1E0h+FileAttributes], 80h; FileAttributes
0x1400347f2  mov     [rsp+1E0h+AllocationSize], rcx; AllocationSize
0x1400347f7  mov     [rbp+0E0h+var_D8.ObjectName], rax
0x1400347fb  lea     rax, [rbp+0E0h+var_A8]
0x1400347ff  mov     [rsp+1E0h+IoStatusBlock], rax; IoStatusBlock
0x140034804  lea     rax, [rbp+0E0h+var_D8]
0x140034808  mov     [rbp+0E0h+var_D8.RootDirectory], rcx
0x14003480c  mov     rcx, cs:Globals; Filter
0x140034813  mov     [rsp+1E0h+ObjectAttributes], rax; ObjectAttributes
0x140034818  mov     [rsp+1E0h+DesiredAccess], 10000h; DesiredAccess
0x140034820  mov     [rbp+0E0h+var_D8.Attributes], 240h
0x140034827  movdqu  xmmword ptr [rbp+0E0h+var_D8.SecurityDescriptor], xmm0
0x14003482c  call    cs:__imp_FltCreateFileEx2
0x140034833  nop     dword ptr [rax+rax+00h]
0x140034838  test    eax, eax
0x14003483a  jns     short loc_140034865
0x14003483c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140034843  jz      loc_140034557
0x140034849  mov     dword ptr [rsp+1E0h+AllocationSize], eax
0x14003484d  mov     r9d, 38h ; '8'
0x140034853  mov     dword ptr [rsp+1E0h+IoStatusBlock], 8A7h
0x14003485b  mov     [rsp+1E0h+ObjectAttributes], r14
0x140034860  jmp     loc_14003453A
0x140034865  xor     ecx, ecx
0x140034867  mov     r13d, 5
0x14003486d  mov     [rbx], rcx
0x140034870  mov     [rbx+8], rcx
0x140034874  mov     rax, [rbp+0E0h+var_138]
0x140034878  mov     [rbx+18h], rax
0x14003487c  mov     rax, qword ptr [rbp+0E0h+EventDescriptor.Id]
0x140034880  mov     [rbp+0E0h+var_138], rcx
0x140034884  mov     [rax], rbx
0x140034887  mov     ebx, ecx
0x140034889  jmp     loc_14003455D
0x14003488e  mov     rdx, [r13+20h]; FileObject
0x140034892  lea     r9, [rbp+0E0h+var_158]
0x140034896  mov     rcx, [r13+18h]; Instance
0x14003489a  lea     r8, [rbp+0E0h+var_128]
0x14003489e  call    WcGetContextFileObject
0x1400348a3  test    al, al
0x1400348a5  jz      loc_140034557
0x1400348ab  mov     rsi, [rbp+0E0h+var_158]
0x1400348af  test    rsi, rsi
0x1400348b2  jz      loc_140034BD5
0x1400348b8  mov     r8, [r13+20h]
0x1400348bc  mov     rcx, r14
0x1400348bf  mov     rdx, [r13+18h]
0x1400348c3  call    WcGetUnionContext
0x1400348c8  mov     rdi, rax
0x1400348cb  test    rax, rax
0x1400348ce  jz      loc_140034BE0
0x1400348d4  cmp     [rsi+1Ch], bl
0x1400348d7  jz      loc_140034BE0
0x1400348dd  lea     rcx, stru_14000E500; Lookaside
0x1400348e4  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400348eb  nop     dword ptr [rax+rax+00h]
0x1400348f0  mov     rbx, rax
0x1400348f3  test    rax, rax
0x1400348f6  jnz     short loc_140034927
0x1400348f8  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400348ff  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140034906  jz      loc_140034557
0x14003490c  mov     dword ptr [rsp+1E0h+AllocationSize], 0C000009Ah
0x140034914  mov     r9d, 39h ; '9'
0x14003491a  mov     dword ptr [rsp+1E0h+IoStatusBlock], 8CBh
0x140034922  jmp     loc_140034527
0x140034927  lea     r8, [rbp+0E0h+FileNameInformation]; FileNameInformation
0x14003492b  mov     edx, 301h; NameOptions
0x140034930  mov     rcx, r14; CallbackData
0x140034933  call    cs:__imp_FltGetFileNameInformation
0x14003493a  nop     dword ptr [rax+rax+00h]
0x14003493f  test    eax, eax
0x140034941  js      loc_140034BD5
0x140034947  mov     rcx, [rbp+0E0h+FileNameInformation]; FileNameInformation
0x14003494b  call    cs:__imp_FltParseFileNameInformation
  ... truncated ...
```
