# PriExchangeDirs

- ea: `0x14000223c`
- end: `0x1400028ae`
- name: `PriExchangeDirs`
- size: `1650`
- prototype: `__int64 __fastcall(void *, void *, void *, void *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14000b110`

## callees

- `0x140002164`
- `0x14000223c`
- `0x140002950`
- `0x1400029e8`
- `0x140002bb0`
- `0x140002d00`
- `0x14000aa34`
- `0x14000aee0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000251b`
- `ntoskrnl!ZwClose` at `0x14000252c`
- `ntoskrnl!ZwClose` at `0x140002803`
- `ntoskrnl!ZwClose` at `0x14000251b`
- `ntoskrnl!ZwClose` at `0x14000252c`
- `ntoskrnl!ZwClose` at `0x140002803`
- `ntoskrnl!TmTransactionObjectType` at `0x14000227a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140002429`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140002448`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400024b4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400024d2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400025ef`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140002429`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140002448`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400024b4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400024d2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400025ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002853`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000287c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002853`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000287c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140002622`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140002622`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140002307`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140002307`
- `ntoskrnl!ObfDereferenceObject` at `0x1400024ed`
- `ntoskrnl!ObfDereferenceObject` at `0x1400024fe`
- `ntoskrnl!ObfDereferenceObject` at `0x1400027c1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400024ed`
- `ntoskrnl!ObfDereferenceObject` at `0x1400024fe`
- `ntoskrnl!ObfDereferenceObject` at `0x1400027c1`
- `FLTMGR!FltObjectDereference` at `0x1400027e2`
- `FLTMGR!FltObjectDereference` at `0x1400027e2`
- `FLTMGR!FltGetVolumeName` at `0x1400023ac`
- `FLTMGR!FltClose` at `0x140002824`
- `FLTMGR!FltClose` at `0x140002824`
- `FLTMGR!FltSetInformationFile` at `0x140002681`
- `FLTMGR!FltSetInformationFile` at `0x1400026c6`
- `FLTMGR!FltSetInformationFile` at `0x1400026ff`
- `FLTMGR!FltSetInformationFile` at `0x14000272a`
- `FLTMGR!FltSetInformationFile` at `0x140002681`
- `FLTMGR!FltSetInformationFile` at `0x1400026c6`
- `FLTMGR!FltSetInformationFile` at `0x1400026ff`
- `FLTMGR!FltSetInformationFile` at `0x14000272a`

## pseudocode

```c
__int64 __fastcall PriExchangeDirs(void *a1, void *a2, void *a3, void *a4, void *a5)
{
  PFLT_INSTANCE v7; // rdi
  void *v8; // r14
  PVOID v9; // r12
  _DWORD *v10; // rsi
  int ObjectsFromUserHandle; // ebx
  int v12; // eax
  int String; // eax
  int v14; // r15d
  int v15; // r9d
  int v16; // r9d
  int Length; // eax
  _DWORD *PoolWithTag; // rax
  void *v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // eax
  __int64 v22; // rdi
  void *v23; // rcx
  __int64 i; // rdi
  PVOID v25; // rcx
  __int64 j; // rdi
  HANDLE v27; // rcx
  __int64 k; // rdi
  HANDLE v29; // rcx
  __int64 m; // rdi
  __int64 v31; // r14
  void *v32; // rcx
  int HandleInformation; // [rsp+28h] [rbp-D8h]
  int HandleInformationa; // [rsp+28h] [rbp-D8h]
  char v36[8]; // [rsp+40h] [rbp-C0h] BYREF
  PVOID v37; // [rsp+48h] [rbp-B8h] BYREF
  PVOID FileObject; // [rsp+50h] [rbp-B0h] BYREF
  PFLT_INSTANCE Instance; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-98h] BYREF
  HANDLE v42; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING v44; // [rsp+88h] [rbp-78h] BYREF
  PVOID v45; // [rsp+98h] [rbp-68h] BYREF
  PVOID v46; // [rsp+A0h] [rbp-60h]
  PVOID v47; // [rsp+A8h] [rbp-58h]
  UNICODE_STRING v48; // [rsp+B0h] [rbp-50h] BYREF
  PVOID Object; // [rsp+C0h] [rbp-40h] BYREF
  PFLT_FILTER Filter; // [rsp+C8h] [rbp-38h] BYREF
  UNICODE_STRING Source; // [rsp+D0h] [rbp-30h] BYREF
  void *v52; // [rsp+E0h] [rbp-20h] BYREF
  void *v53; // [rsp+E8h] [rbp-18h] BYREF
  int v54[4]; // [rsp+F0h] [rbp-10h] BYREF
  HANDLE FileHandle[2]; // [rsp+100h] [rbp+0h]
  HANDLE v56[2]; // [rsp+110h] [rbp+10h]
  PVOID FltObject[4]; // [rsp+120h] [rbp+20h]
  _QWORD v58[4]; // [rsp+140h] [rbp+40h]
  _OWORD FileInformation[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v60; // [rsp+180h] [rbp+80h]

  v56[0] = a5;
  v60 = 0;
  FileHandle[0] = a4;
  v7 = 0;
  v8 = 0;
  Filter = 0;
  v9 = 0;
  Instance = 0;
  v10 = 0;
  v40 = 0;
  v45 = 0;
  FileObject = 0;
  v37 = 0;
  Handle = 0;
  v42 = 0;
  v52 = 0;
  v53 = 0;
  *(_OWORD *)v54 = 0;
  v36[0] = 0;
  Source = 0;
  Object = 0;
  v48 = 0;
  Destination = 0;
  v44 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  ObjectsFromUserHandle = ObReferenceObjectByHandle(a1, 0, (POBJECT_TYPE)TmTransactionObjectType, 1, &Object, 0);
  if ( ObjectsFromUserHandle < 0 )
    goto LABEL_29;
  ObjectsFromUserHandle = PriGetObjectsFromUserHandle(
                            a2,
                            0x10000u,
                            &Filter,
                            &Instance,
                            (PFLT_VOLUME *)&v40,
                            &Handle,
                            &FileObject);
  if ( ObjectsFromUserHandle < 0 )
  {
    v8 = (void *)v40;
    goto LABEL_28;
  }
  v12 = PriGetObjectsFromUserHandle(a3, 0x10000u, 0, 0, (PFLT_VOLUME *)&v45, &v42, &v37);
  v8 = (void *)v40;
  ObjectsFromUserHandle = v12;
  v9 = v45;
  if ( v12 < 0 )
  {
LABEL_28:
    v7 = Instance;
    goto LABEL_29;
  }
  if ( (PVOID)v40 != v45 )
  {
    ObjectsFromUserHandle = -1073741811;
    goto LABEL_28;
  }
  String = PriGetString(v40, FltGetVolumeName, &Source);
  v7 = Instance;
  ObjectsFromUserHandle = String;
  if ( String >= 0 )
  {
    v46 = FileObject;
    v45 = Instance;
    ObjectsFromUserHandle = PriGetString(&v45, &PriGetFileNameCallback, &v48);
    if ( ObjectsFromUserHandle >= 0 )
    {
      ObjectsFromUserHandle = PriStringEnsureCapacity(
                                &Destination,
                                Source.Length + v48.Length + (unsigned int)::Source.Length);
      if ( ObjectsFromUserHandle >= 0 )
      {
        ObjectsFromUserHandle = RtlAppendUnicodeStringToString(&Destination, &Source);
        if ( ObjectsFromUserHandle >= 0 )
        {
          ObjectsFromUserHandle = RtlAppendUnicodeStringToString(&Destination, &v48);
          if ( ObjectsFromUserHandle >= 0 )
          {
            v45 = v7;
            v48.Length = 0;
            v46 = v37;
            ObjectsFromUserHandle = PriGetString(&v45, &PriGetFileNameCallback, &v48);
            if ( ObjectsFromUserHandle >= 0 )
            {
              ObjectsFromUserHandle = PriStringEnsureCapacity(&v44, Source.Length + (unsigned int)v48.Length);
              if ( ObjectsFromUserHandle >= 0 )
              {
                ObjectsFromUserHandle = RtlAppendUnicodeStringToString(&v44, &Source);
                if ( ObjectsFromUserHandle >= 0 )
                {
                  ObjectsFromUserHandle = RtlAppendUnicodeStringToString(&v44, &v48);
                  if ( ObjectsFromUserHandle >= 0 )
                  {
                    ObfDereferenceObject(FileObject);
                    ObfDereferenceObject(v37);
                    v37 = 0;
                    FileObject = 0;
                    ZwClose(Handle);
                    ZwClose(v42);
                    v14 = (int)Filter;
                    v42 = 0;
                    Handle = 0;
                    ObjectsFromUserHandle = PFSendExchangeCloseHandlesMessage(Filter);
                    if ( ObjectsFromUserHandle >= 0 )
                    {
                      v54[0] = -131056;
                      *(_BYTE *)v56[0] = 1;
                      *(_QWORD *)&v54[2] = Object;
                      ObjectsFromUserHandle = PriCreateTransactional(
                                                v14,
                                                (int)v7,
                                                (int)v54,
                                                v15,
                                                (__int64)&Destination,
                                                HandleInformation,
                                                &v52,
                                                (PFILE_OBJECT *)&FileObject);
                      if ( ObjectsFromUserHandle >= 0 )
                      {
                        ObjectsFromUserHandle = PriCreateTransactional(
                                                  v14,
                                                  (int)v7,
                                                  (int)v54,
                                                  v16,
                                                  (__int64)&v44,
                                                  HandleInformationa,
                                                  &v53,
                                                  (PFILE_OBJECT *)&v37);
                        if ( ObjectsFromUserHandle >= 0 )
                        {
                          ObjectsFromUserHandle = RtlAppendUnicodeStringToString(&Destination, &::Source);
                          if ( ObjectsFromUserHandle >= 0 )
                          {
                            Length = Destination.Length;
                            if ( v44.Length > Destination.Length )
                              Length = v44.Length;
                            PoolWithTag = ExAllocatePoolWithTag(PagedPool, (unsigned int)(Length + 20), 0x574D6365u);
                            v10 = PoolWithTag;
                            if ( PoolWithTag )
                            {
                              *(_BYTE *)PoolWithTag = 0;
                              v19 = PoolWithTag + 5;
                              *((_QWORD *)PoolWithTag + 1) = 0;
                              v20 = Destination.Length;
                              v10[4] = Destination.Length;
                              memmove(v19, Destination.Buffer, v20);
                              ObjectsFromUserHandle = FltSetInformationFile(
                                                        v7,
                                                        (PFILE_OBJECT)v37,
                                                        v10,
                                                        v10[4] + 20,
                                                        FileRenameInformation);
                              if ( ObjectsFromUserHandle >= 0 )
                              {
                                v21 = v44.Length;
                                v10[4] = v44.Length;
                                memmove(v10 + 5, v44.Buffer, v21);
                                ObjectsFromUserHandle = FltSetInformationFile(
                                                          v7,
                                                          (PFILE_OBJECT)FileObject,
                                                          v10,
                                                          v10[4] + 20,
                                                          FileRenameInformation);
                                if ( ObjectsFromUserHandle >= 0 )
                                {
                                  LODWORD(v60) = 128;
                                  v36[0] = 1;
                                  ObjectsFromUserHandle = FltSetInformationFile(
                                                            v7,
                                                            (PFILE_OBJECT)v37,
                                                            FileInformation,
                                                            0x28u,
                                                            FileBasicInformation);
                                  if ( ObjectsFromUserHandle >= 0 )
                                    ObjectsFromUserHandle = FltSetInformationFile(
                                                              v7,
                                                              (PFILE_OBJECT)v37,
                                                              v36,
                                                              1u,
                                                              FileDispositionInformation);
                                }
                              }
                            }
                            else
                            {
                              ObjectsFromUserHandle = -1073741801;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_29:
  v45 = Object;
  v46 = FileObject;
  v47 = v37;
  FltObject[0] = Filter;
  v56[0] = Handle;
  v56[1] = v42;
  FileHandle[0] = v52;
  FileHandle[1] = v53;
  v58[0] = &Source;
  v58[1] = &v48;
  v58[2] = &Destination;
  FltObject[1] = v7;
  v22 = 0;
  v58[3] = &v44;
  FltObject[2] = v8;
  FltObject[3] = v9;
  do
  {
    v23 = *(&v45 + v22);
    if ( v23 )
      ObfDereferenceObject(v23);
    ++v22;
  }
  while ( v22 != 3 );
  for ( i = 0; i != 4; ++i )
  {
    v25 = FltObject[i];
    if ( v25 )
      FltObjectDereference(v25);
  }
  for ( j = 0; j != 2; ++j )
  {
    v27 = v56[j];
    if ( v27 )
      ZwClose(v27);
  }
  for ( k = 0; k != 2; ++k )
  {
    v29 = FileHandle[k];
    if ( v29 )
      FltClose(v29);
  }
  for ( m = 0; m != 4; ++m )
  {
    v31 = v58[m];
    if ( v31 )
    {
      v32 = *(void **)(v31 + 8);
      if ( v32 )
        ExFreePoolWithTag(v32, 0x574D6365u);
      *(_OWORD *)v31 = 0;
    }
  }
  if ( v10 )
    ExFreePoolWithTag(v10, 0x574D6365u);
  return (unsigned int)ObjectsFromUserHandle;
}

```

## disassembly

```asm
0x14000223c  push    rbp
0x14000223e  push    rbx
0x14000223f  push    rsi
0x140002240  push    rdi
0x140002241  push    r12
0x140002243  push    r13
0x140002245  push    r14
0x140002247  push    r15
0x140002249  lea     rbp, [rsp-98h]
0x140002251  sub     rsp, 198h
0x140002258  mov     rax, cs:__security_cookie
0x14000225f  xor     rax, rsp
0x140002262  mov     [rbp+0D0h+var_48], rax
0x140002269  mov     rax, [rbp+0D0h+arg_20]
0x140002270  xorps   xmm0, xmm0
0x140002273  mov     r15, r8
0x140002276  mov     [rbp+0D0h+var_C0], rax
0x14000227a  mov     r8, cs:__imp_TmTransactionObjectType
0x140002281  xor     eax, eax
0x140002283  xorps   xmm1, xmm1
0x140002286  mov     [rbp+0D0h+var_50], rax
0x14000228d  mov     r13, rdx
0x140002290  mov     [rbp+0D0h+FileHandle], r9
0x140002294  xor     edx, edx; DesiredAccess
0x140002296  lea     rax, [rbp+0D0h+var_110]
0x14000229a  mov     r8, [r8]; ObjectType
0x14000229d  mov     r9b, 1; AccessMode
0x1400022a0  mov     [rsp+1D0h+HandleInformation], rdx; HandleInformation
0x1400022a5  mov     edi, edx
0x1400022a7  mov     [rsp+1D0h+Object], rax; Object
0x1400022ac  mov     r14d, edx
0x1400022af  mov     [rbp+0D0h+Filter], rdx
0x1400022b3  mov     r12d, edx
0x1400022b6  mov     [rsp+1D0h+Instance], rdx
0x1400022bb  mov     esi, edx
0x1400022bd  mov     [rsp+1D0h+var_170], rdx
0x1400022c2  mov     [rbp+0D0h+var_138], rdx
0x1400022c6  mov     [rsp+1D0h+var_180], rdx
0x1400022cb  mov     [rsp+1D0h+var_188], rdx
0x1400022d0  mov     [rsp+1D0h+Handle], rdx
0x1400022d5  mov     [rsp+1D0h+var_160], rdx
0x1400022da  mov     [rbp+0D0h+var_F0], rdx
0x1400022de  mov     [rbp+0D0h+var_E8], rdx
0x1400022e2  movups  xmmword ptr [rbp+0D0h+var_E0], xmm0
0x1400022e6  mov     [rsp+1D0h+var_190], dl
0x1400022ea  movups  xmmword ptr [rbp+0D0h+Source.Length], xmm1
0x1400022ee  mov     [rbp+0D0h+var_110], rdx
0x1400022f2  movups  xmmword ptr [rbp+0D0h+var_120.Length], xmm0
0x1400022f6  movups  xmmword ptr [rsp+1D0h+Destination.Length], xmm1
0x1400022fb  movups  xmmword ptr [rbp+0D0h+var_148.Length], xmm0
0x1400022ff  movups  [rbp+0D0h+FileInformation], xmm0
0x140002303  movups  [rbp+0D0h+var_60], xmm0
0x140002307  call    cs:__imp_ObReferenceObjectByHandle
0x14000230e  nop     dword ptr [rax+rax+00h]
0x140002313  mov     ebx, eax
0x140002315  test    eax, eax
0x140002317  js      loc_140002744
0x14000231d  lea     rax, [rsp+1D0h+var_180]
0x140002322  mov     edi, 10000h
0x140002327  mov     [rsp+1D0h+var_1A0], rax; __int64
0x14000232c  lea     r9, [rsp+1D0h+Instance]
0x140002331  lea     rax, [rsp+1D0h+Handle]
0x140002336  mov     edx, edi; DesiredAccess
0x140002338  mov     [rsp+1D0h+HandleInformation], rax; __int64
0x14000233d  lea     r8, [rbp+0D0h+Filter]
0x140002341  lea     rax, [rsp+1D0h+var_170]
0x140002346  mov     rcx, r13; Handle
0x140002349  mov     [rsp+1D0h+Object], rax; __int64
0x14000234e  call    PriGetObjectsFromUserHandle
0x140002353  mov     ebx, eax
0x140002355  test    eax, eax
0x140002357  js      loc_14000273A
0x14000235d  lea     rax, [rsp+1D0h+var_188]
0x140002362  xor     r9d, r9d
0x140002365  mov     [rsp+1D0h+var_1A0], rax; __int64
0x14000236a  xor     r8d, r8d
0x14000236d  lea     rax, [rsp+1D0h+var_160]
0x140002372  mov     edx, edi; DesiredAccess
0x140002374  mov     [rsp+1D0h+HandleInformation], rax; int
0x140002379  mov     rcx, r15; Handle
0x14000237c  lea     rax, [rbp+0D0h+var_138]
0x140002380  mov     [rsp+1D0h+Object], rax; __int64
0x140002385  call    PriGetObjectsFromUserHandle
0x14000238a  mov     r14, [rsp+1D0h+var_170]
0x14000238f  mov     ebx, eax
0x140002391  mov     r12, [rbp+0D0h+var_138]
0x140002395  test    eax, eax
0x140002397  js      loc_14000273F
0x14000239d  cmp     r14, r12
0x1400023a0  jz      short loc_1400023AC
0x1400023a2  mov     ebx, 0C000000Dh
0x1400023a7  jmp     loc_14000273F
0x1400023ac  mov     rdx, cs:__imp_FltGetVolumeName
0x1400023b3  lea     r8, [rbp+0D0h+Source]
0x1400023b7  mov     rcx, r14
0x1400023ba  call    PriGetString
0x1400023bf  mov     rdi, [rsp+1D0h+Instance]
0x1400023c4  mov     ebx, eax
0x1400023c6  test    eax, eax
0x1400023c8  js      loc_140002744
0x1400023ce  mov     rax, [rsp+1D0h+var_180]
0x1400023d3  lea     r8, [rbp+0D0h+var_120]
0x1400023d7  lea     rdx, PriGetFileNameCallback
0x1400023de  mov     [rbp+0D0h+var_130], rax
0x1400023e2  lea     rcx, [rbp+0D0h+var_138]
0x1400023e6  mov     [rbp+0D0h+var_138], rdi
0x1400023ea  call    PriGetString
0x1400023ef  mov     ebx, eax
0x1400023f1  test    eax, eax
0x1400023f3  js      loc_140002744
0x1400023f9  movzx   eax, [rbp+0D0h+var_120.Length]
0x1400023fd  lea     rcx, [rsp+1D0h+Destination]
0x140002402  movzx   edx, cs:Source.Length
0x140002409  add     edx, eax
0x14000240b  movzx   eax, [rbp+0D0h+Source.Length]
0x14000240f  add     edx, eax
0x140002411  call    PriStringEnsureCapacity
0x140002416  mov     ebx, eax
0x140002418  test    eax, eax
0x14000241a  js      loc_140002744
0x140002420  lea     rdx, [rbp+0D0h+Source]; Source
0x140002424  lea     rcx, [rsp+1D0h+Destination]; Destination
0x140002429  call    cs:__imp_RtlAppendUnicodeStringToString
0x140002430  nop     dword ptr [rax+rax+00h]
0x140002435  mov     ebx, eax
0x140002437  test    eax, eax
0x140002439  js      loc_140002744
0x14000243f  lea     rdx, [rbp+0D0h+var_120]; Source
0x140002443  lea     rcx, [rsp+1D0h+Destination]; Destination
0x140002448  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000244f  nop     dword ptr [rax+rax+00h]
0x140002454  mov     ebx, eax
0x140002456  test    eax, eax
0x140002458  js      loc_140002744
0x14000245e  xor     eax, eax
0x140002460  mov     [rbp+0D0h+var_138], rdi
0x140002464  mov     [rbp+0D0h+var_120.Length], ax
0x140002468  lea     r8, [rbp+0D0h+var_120]
0x14000246c  mov     rax, [rsp+1D0h+var_188]
0x140002471  lea     rdx, PriGetFileNameCallback
0x140002478  lea     rcx, [rbp+0D0h+var_138]
0x14000247c  mov     [rbp+0D0h+var_130], rax
0x140002480  call    PriGetString
0x140002485  mov     ebx, eax
0x140002487  test    eax, eax
0x140002489  js      loc_140002744
0x14000248f  movzx   edx, [rbp+0D0h+var_120.Length]
0x140002493  lea     rcx, [rbp+0D0h+var_148]
0x140002497  movzx   eax, [rbp+0D0h+Source.Length]
0x14000249b  add     edx, eax
0x14000249d  call    PriStringEnsureCapacity
0x1400024a2  mov     ebx, eax
0x1400024a4  test    eax, eax
0x1400024a6  js      loc_140002744
0x1400024ac  lea     rdx, [rbp+0D0h+Source]; Source
0x1400024b0  lea     rcx, [rbp+0D0h+var_148]; Destination
0x1400024b4  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400024bb  nop     dword ptr [rax+rax+00h]
0x1400024c0  mov     ebx, eax
0x1400024c2  test    eax, eax
0x1400024c4  js      loc_140002744
0x1400024ca  lea     rdx, [rbp+0D0h+var_120]; Source
0x1400024ce  lea     rcx, [rbp+0D0h+var_148]; Destination
0x1400024d2  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400024d9  nop     dword ptr [rax+rax+00h]
0x1400024de  mov     ebx, eax
0x1400024e0  test    eax, eax
0x1400024e2  js      loc_140002744
0x1400024e8  mov     rcx, [rsp+1D0h+var_180]; Object
0x1400024ed  call    cs:__imp_ObfDereferenceObject
0x1400024f4  nop     dword ptr [rax+rax+00h]
0x1400024f9  mov     rcx, [rsp+1D0h+var_188]; Object
0x1400024fe  call    cs:__imp_ObfDereferenceObject
0x140002505  nop     dword ptr [rax+rax+00h]
0x14000250a  mov     rcx, [rsp+1D0h+Handle]; Handle
0x14000250f  xor     ebx, ebx
0x140002511  mov     [rsp+1D0h+var_188], rbx
0x140002516  mov     [rsp+1D0h+var_180], rbx
0x14000251b  call    cs:__imp_ZwClose
0x140002522  nop     dword ptr [rax+rax+00h]
0x140002527  mov     rcx, [rsp+1D0h+var_160]; Handle
0x14000252c  call    cs:__imp_ZwClose
0x140002533  nop     dword ptr [rax+rax+00h]
0x140002538  mov     rdx, [rbp+0D0h+FileHandle]
0x14000253c  mov     r9, r15
0x14000253f  mov     r15, [rbp+0D0h+Filter]
0x140002543  mov     r8, r13
0x140002546  mov     rcx, r15; Filter
0x140002549  mov     [rsp+1D0h+var_160], rbx
0x14000254e  mov     [rsp+1D0h+Handle], rbx
0x140002553  call    PFSendExchangeCloseHandlesMessage
0x140002558  mov     ebx, eax
0x14000255a  test    eax, eax
0x14000255c  js      loc_140002744
0x140002562  mov     rax, [rbp+0D0h+var_C0]
0x140002566  lea     r8, [rbp+0D0h+var_E0]; int
0x14000256a  mov     rdx, rdi; int
0x14000256d  mov     [rbp+0D0h+var_E0], 0FFFE0010h
0x140002574  mov     rcx, r15; int
0x140002577  mov     byte ptr [rax], 1
0x14000257a  mov     rax, [rbp+0D0h+var_110]
0x14000257e  mov     qword ptr [rbp+0D0h+var_E0+8], rax
0x140002582  lea     rax, [rsp+1D0h+var_180]
0x140002587  mov     [rsp+1D0h+FileObject], rax; FileObject
0x14000258c  lea     rax, [rbp+0D0h+var_F0]
0x140002590  mov     [rsp+1D0h+var_1A0], rax; FileHandle
0x140002595  lea     rax, [rsp+1D0h+Destination]
0x14000259a  mov     [rsp+1D0h+Object], rax; __int64
0x14000259f  call    PriCreateTransactional
0x1400025a4  mov     ebx, eax
0x1400025a6  test    eax, eax
0x1400025a8  js      loc_140002744
0x1400025ae  lea     rax, [rsp+1D0h+var_188]
0x1400025b3  mov     rdx, rdi; int
0x1400025b6  mov     [rsp+1D0h+FileObject], rax; FileObject
0x1400025bb  lea     r8, [rbp+0D0h+var_E0]; int
0x1400025bf  lea     rax, [rbp+0D0h+var_E8]
0x1400025c3  mov     rcx, r15; int
0x1400025c6  mov     [rsp+1D0h+var_1A0], rax; FileHandle
0x1400025cb  lea     rax, [rbp+0D0h+var_148]
0x1400025cf  mov     [rsp+1D0h+Object], rax; __int64
0x1400025d4  call    PriCreateTransactional
0x1400025d9  mov     ebx, eax
0x1400025db  test    eax, eax
0x1400025dd  js      loc_140002744
0x1400025e3  lea     rdx, Source; Source
0x1400025ea  lea     rcx, [rsp+1D0h+Destination]; Destination
0x1400025ef  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400025f6  nop     dword ptr [rax+rax+00h]
0x1400025fb  mov     ebx, eax
0x1400025fd  test    eax, eax
0x1400025ff  js      loc_140002744
0x140002605  movzx   eax, [rsp+1D0h+Destination.Length]
0x14000260a  cmp     [rbp+0D0h+var_148.Length], ax
0x14000260e  jbe     short loc_140002614
0x140002610  movzx   eax, [rbp+0D0h+var_148.Length]
0x140002614  lea     edx, [rax+14h]; NumberOfBytes
0x140002617  mov     ecx, 1; PoolType
0x14000261c  mov     r8d, 574D6365h; Tag
0x140002622  call    cs:__imp_ExAllocatePoolWithTag
0x140002629  nop     dword ptr [rax+rax+00h]
0x14000262e  mov     rsi, rax
0x140002631  test    rax, rax
0x140002634  jnz     short loc_140002640
0x140002636  mov     ebx, 0C0000017h
0x14000263b  jmp     loc_140002744
0x140002640  mov     byte ptr [rax], 0
0x140002643  lea     rcx, [rsi+14h]; void *
0x140002647  mov     qword ptr [rax+8], 0
0x14000264f  movzx   eax, [rsp+1D0h+Destination.Length]
0x140002654  mov     [rsi+10h], eax
0x140002657  mov     r8d, eax; Size
0x14000265a  mov     rdx, [rbp+0D0h+Destination.Buffer]; Src
0x14000265e  call    memmove
0x140002663  mov     r9d, [rsi+10h]
0x140002667  mov     r13d, 0Ah
0x14000266d  mov     rdx, [rsp+1D0h+var_188]; FileObject
0x140002672  add     r9d, 14h; Length
0x140002676  mov     r8, rsi; FileInformation
0x140002679  mov     dword ptr [rsp+1D0h+Object], r13d; FileInformationClass
0x14000267e  mov     rcx, rdi; Instance
0x140002681  call    cs:__imp_FltSetInformationFile
0x140002688  nop     dword ptr [rax+rax+00h]
0x14000268d  mov     ebx, eax
0x14000268f  test    eax, eax
0x140002691  js      loc_140002744
0x140002697  movzx   eax, [rbp+0D0h+var_148.Length]
0x14000269b  lea     rcx, [rsi+14h]; void *
0x14000269f  mov     [rsi+10h], eax
0x1400026a2  mov     r8d, eax; Size
0x1400026a5  mov     rdx, [rbp+0D0h+var_148.Buffer]; Src
0x1400026a9  call    memmove
0x1400026ae  mov     r9d, [rsi+10h]
0x1400026b2  mov     r8, rsi; FileInformation
0x1400026b5  mov     rdx, [rsp+1D0h+var_180]; FileObject
0x1400026ba  add     r9d, 14h; Length
0x1400026be  mov     rcx, rdi; Instance
0x1400026c1  mov     dword ptr [rsp+1D0h+Object], r13d; FileInformationClass
0x1400026c6  call    cs:__imp_FltSetInformationFile
0x1400026cd  nop     dword ptr [rax+rax+00h]
0x1400026d2  mov     ebx, eax
0x1400026d4  test    eax, eax
0x1400026d6  js      short loc_140002744
0x1400026d8  mov     rdx, [rsp+1D0h+var_188]; FileObject
0x1400026dd  lea     r9d, [r13+1Eh]; Length
0x1400026e1  lea     r8, [rbp+0D0h+FileInformation]; FileInformation
0x1400026e5  mov     dword ptr [rbp+0D0h+var_50], 80h
0x1400026ef  mov     rcx, rdi; Instance
0x1400026f2  mov     [rsp+1D0h+var_190], 1
0x1400026f7  mov     dword ptr [rsp+1D0h+Object], 4; FileInformationClass
0x1400026ff  call    cs:__imp_FltSetInformationFile
0x140002706  nop     dword ptr [rax+rax+00h]
0x14000270b  mov     ebx, eax
0x14000270d  test    eax, eax
0x14000270f  js      short loc_140002744
0x140002711  mov     rdx, [rsp+1D0h+var_188]; FileObject
0x140002716  lea     r9d, [r13-9]; Length
0x14000271a  lea     r8, [rsp+1D0h+var_190]; FileInformation
0x14000271f  mov     dword ptr [rsp+1D0h+Object], 0Dh; FileInformationClass
0x140002727  mov     rcx, rdi; Instance
  ... truncated ...
```
