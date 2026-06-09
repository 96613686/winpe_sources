# VhdmpiVhd1ActuallyExpandOnMount(_VHD_VIRTUAL_DISK *)

- ea: `0x1400be500`
- end: `0x1400be898`
- name: `?VhdmpiVhd1ActuallyExpandOnMount@@YAJPEAU_VHD_VIRTUAL_DISK@@@Z`
- size: `920`
- prototype: `__int64 __fastcall(struct _VHD_VIRTUAL_DISK *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x14003c3bc`

## callees

- `0x14001bc1c`
- `0x14001c088`
- `0x140022654`
- `0x140023980`
- `0x140026930`
- `0x140033124`
- `0x140033d2c`
- `0x140036284`
- `0x14003eb98`
- `0x1400bd52c`
- `0x1400be500`
- `0x1400e25fc`
- `0x1400e7b74`
- `0x1400ea500`

## import_xrefs

- `ntoskrnl!ZwSetInformationFile` at `0x1400be692`
- `ntoskrnl!ZwSetInformationFile` at `0x1400be6cd`
- `ntoskrnl!ZwSetInformationFile` at `0x1400be692`
- `ntoskrnl!ZwSetInformationFile` at `0x1400be6cd`

## string_xrefs

- `0x1400be56d`: `VhdmpiVhd1ActuallyExpandOnMount`
- `0x1400be63c`: `VhdmpiVhd1ActuallyExpandOnMount`
- `0x1400be771`: `VhdmpiVhd1ActuallyExpandOnMount`
- `0x1400be7d2`: `VhdmpiVhd1ActuallyExpandOnMount`
- `0x1400be874`: `VhdmpiVhd1ActuallyExpandOnMount`
- `0x1400be561`: `VhdmpiVhd1ActuallyExpandOnMount: enter... VirtualDisk 0x%p`
- `0x1400be765`: `VhdmpiVhd1ActuallyExpandOnMount: expand on mount failed (0x%08x)`
- `0x1400be626`: `VhdmpiVhd1ActuallyExpandOnMount: TargetFileSize: 0x%016I64x Existing file size: 0x%016I64x`
- `0x1400be85e`: `VhdmpiVhd1ActuallyExpandOnMount: leaving... VirtualDisk 0x%p (0x%08x)`
- `0x1400be7b8`: `VhdmpiVhd1ActuallyExpandOnMount: attempting to truncate BackingStore 0x%p due to failure`

## pseudocode

```c
__int64 __fastcall VhdmpiVhd1ActuallyExpandOnMount(struct _VHD_VIRTUAL_DISK *a1)
{
  __int64 v2; // rbx
  HANDLE v3; // rsi
  NTSTATUS v4; // edi
  unsigned __int8 v5; // r12
  __int64 v6; // rdx
  unsigned __int64 v7; // r14
  int v8; // eax
  int v9; // r8d
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int64 FileInformation; // [rsp+A0h] [rbp+48h] BYREF
  HANDLE FileHandle; // [rsp+A8h] [rbp+50h] BYREF
  __int64 v14; // [rsp+B0h] [rbp+58h] BYREF
  unsigned __int64 v15; // [rsp+B8h] [rbp+60h] BYREF

  FileInformation = 0;
  v14 = 0;
  v15 = 0;
  IoStatusBlock = 0;
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
    TraceEvents(
      "VhdmpiVhd1ActuallyExpandOnMount",
      0x1131u,
      4u,
      8u,
      "VhdmpiVhd1ActuallyExpandOnMount: enter... VirtualDisk 0x%p",
      a1);
  v2 = *((_QWORD *)a1 + 18);
  v3 = 0;
  v4 = 0;
  FileHandle = 0;
  if ( *(_DWORD *)(v2 + 1988) == 2 )
  {
    v5 = 0;
  }
  else
  {
    VhdmpiLockUnlockVhdFile(
      v2,
      (unsigned int)&v14,
      1,
      2,
      (char)"onecore\\vm\\dv\\storage\\vhd\\vhdmp\\vhd1parser.c",
      4437);
    VhdmpiAcquirePassiveLock(v2 + 3608);
    VhdmpiAcquirePassiveLock(v2 + 3592);
    v5 = 1;
    v7 = VhdmpiCalculateMaxPotentialFooterLocation((struct _VHD1_BACKING_STORE *)v2) + *(unsigned int *)(v2 + 1924);
    if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
      TraceEvents(
        "VhdmpiVhd1ActuallyExpandOnMount",
        0x1171u,
        4u,
        8u,
        "VhdmpiVhd1ActuallyExpandOnMount: TargetFileSize: 0x%016I64x Existing file size: 0x%016I64x",
        v7,
        *(_QWORD *)(v2 + 1168));
    if ( *(_QWORD *)(v2 + 1168) >= v7 )
      goto LABEL_18;
    LOBYTE(v6) = 1;
    v8 = VhdmpiPinFile(v2, v6, &FileHandle);
    v3 = FileHandle;
    v4 = v8;
    if ( v8 >= 0 )
    {
      FileInformation = v7;
      v4 = ZwSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 8u, FileEndOfFileInformation);
      if ( v4 >= 0 )
      {
        RmwVhdFileSizeChangeNotification(
          (struct _VHD_BACKING_STORE_HEADER *)v2,
          (struct _FILE_END_OF_FILE_INFORMATION *)&FileInformation);
        v15 = v7;
        v4 = ZwSetInformationFile(v3, &IoStatusBlock, &v15, 8u, FileValidDataLengthInformation);
        if ( v4 >= 0 )
        {
          *(_QWORD *)(v2 + 1168) = v7;
          VhdmpiReleasePassiveLock(v2 + 3592);
          VhdmpiReleasePassiveLock(v2 + 3608);
          v5 = 0;
          v4 = VhdmpiFlushFooters((struct _VHD1_BACKING_STORE *)v2, 0);
        }
      }
    }
  }
  if ( v3 && (__int64 *)v2 != &VhdmpiEmptyISOBackingStore )
    VhdmpiFileWrapperUnpinFile(v2 + 72, 1);
  if ( v4 >= 0 )
  {
LABEL_18:
    *((_BYTE *)a1 + 89) = 1;
    goto LABEL_27;
  }
  if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
    TraceEvents(
      "VhdmpiVhd1ActuallyExpandOnMount",
      0x11EAu,
      2u,
      8u,
      "VhdmpiVhd1ActuallyExpandOnMount: expand on mount failed (0x%08x)",
      v4);
  if ( (unsigned __int8)VhdmpiIsFileLockFullyAcquired(&v14) )
  {
    if ( (unsigned int)dword_1400876D0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
      TraceEvents(
        "VhdmpiVhd1ActuallyExpandOnMount",
        0x11FBu,
        v9,
        v9 + 1,
        "VhdmpiVhd1ActuallyExpandOnMount: attempting to truncate BackingStore 0x%p due to failure",
        (const void *)v2);
    VhdmpiVhd1TryTruncateBackingStoreFileInternal((struct _VHD_BACKING_STORE_HEADER *)v2, v5);
  }
LABEL_27:
  if ( v5 )
  {
    VhdmpiReleasePassiveLock(v2 + 3592);
    VhdmpiReleasePassiveLock(v2 + 3608);
  }
  VhdmpiLockUnlockVhdFile(
    v2,
    (unsigned int)&v14,
    0,
    2,
    (char)"onecore\\vm\\dv\\storage\\vhd\\vhdmp\\vhd1parser.c",
    4630);
  VhdmpiFlushBuffersFile(v2);
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
    TraceEvents(
      "VhdmpiVhd1ActuallyExpandOnMount",
      0x1228u,
      4u,
      8u,
      "VhdmpiVhd1ActuallyExpandOnMount: leaving... VirtualDisk 0x%p (0x%08x)",
      a1,
      v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400be500  push    rbp
0x1400be502  push    rbx
0x1400be503  push    rsi
0x1400be504  push    rdi
0x1400be505  push    r12
0x1400be507  push    r13
0x1400be509  push    r14
0x1400be50b  push    r15
0x1400be50d  mov     rbp, rsp
0x1400be510  sub     rsp, 58h
0x1400be514  mov     eax, cs:dword_1400876D0
0x1400be51a  xorps   xmm0, xmm0
0x1400be51d  mov     [rbp+FileInformation], 0
0x1400be525  mov     r15, rcx
0x1400be528  mov     [rbp+arg_10], 0
0x1400be530  mov     [rbp+arg_18], 0
0x1400be538  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1400be53c  cmp     eax, 4
0x1400be53f  jbe     short loc_1400BE582
0x1400be541  mov     edx, 8
0x1400be546  lea     rcx, dword_1400876D0
0x1400be54d  call    _tlgKeywordOn
0x1400be552  test    al, al
0x1400be554  jz      short loc_1400BE582
0x1400be556  mov     r9d, 8; int
0x1400be55c  mov     qword ptr [rsp+58h+var_30], r15; char
0x1400be561  lea     rax, aVhdmpivhd1actu_4; "VhdmpiVhd1ActuallyExpandOnMount: enter."...
0x1400be568  mov     edx, 1131h; int
0x1400be56d  lea     rcx, aVhdmpivhd1actu_2; "VhdmpiVhd1ActuallyExpandOnMount"
0x1400be574  mov     qword ptr [rsp+58h+FileInformationClass], rax; char *
0x1400be579  lea     r8d, [r9-4]; int
0x1400be57d  call    TraceEvents
0x1400be582  mov     rbx, [r15+90h]
0x1400be589  lea     rax, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\vhd\\vhdmp\\v"...
0x1400be590  xor     esi, esi
0x1400be592  xor     edi, edi
0x1400be594  mov     [rbp+FileHandle], rsi
0x1400be598  cmp     dword ptr [rbx+7C4h], 2
0x1400be59f  jz      loc_1400BE70B
0x1400be5a5  mov     dword ptr [rsp+58h+var_30], 1155h
0x1400be5ad  lea     rdx, [rbp+arg_10]
0x1400be5b1  mov     r9b, 2
0x1400be5b4  mov     qword ptr [rsp+58h+FileInformationClass], rax
0x1400be5b9  mov     r8b, 1
0x1400be5bc  mov     rcx, rbx
0x1400be5bf  call    VhdmpiLockUnlockVhdFile
0x1400be5c4  lea     r13, [rbx+0E18h]
0x1400be5cb  mov     rcx, r13
0x1400be5ce  call    VhdmpiAcquirePassiveLock
0x1400be5d3  lea     rcx, [rbx+0E08h]
0x1400be5da  call    VhdmpiAcquirePassiveLock
0x1400be5df  mov     rcx, rbx; struct _VHD1_BACKING_STORE *
0x1400be5e2  mov     r12b, 1
0x1400be5e5  call    ?VhdmpiCalculateMaxPotentialFooterLocation@@YA_KPEAU_VHD1_BACKING_STORE@@@Z; VhdmpiCalculateMaxPotentialFooterLocation(_VHD1_BACKING_STORE *)
0x1400be5ea  mov     r14d, [rbx+784h]
0x1400be5f1  add     r14, rax
0x1400be5f4  mov     eax, cs:dword_1400876D0
0x1400be5fa  cmp     eax, 4
0x1400be5fd  jbe     short loc_1400BE648
0x1400be5ff  lea     edx, [rsi+8]
0x1400be602  lea     rcx, dword_1400876D0
0x1400be609  call    _tlgKeywordOn
0x1400be60e  test    al, al
0x1400be610  jz      short loc_1400BE648
0x1400be612  mov     rax, [rbx+490h]
0x1400be619  lea     r9d, [rsi+8]; int
0x1400be61d  mov     [rsp+58h+var_28], rax
0x1400be622  lea     r8d, [rsi+4]; int
0x1400be626  lea     rax, aVhdmpivhd1actu_3; "VhdmpiVhd1ActuallyExpandOnMount: Target"...
0x1400be62d  mov     qword ptr [rsp+58h+var_30], r14; char
0x1400be632  mov     edx, 1171h; int
0x1400be637  mov     qword ptr [rsp+58h+FileInformationClass], rax; char *
0x1400be63c  lea     rcx, aVhdmpivhd1actu_2; "VhdmpiVhd1ActuallyExpandOnMount"
0x1400be643  call    TraceEvents
0x1400be648  cmp     [rbx+490h], r14
0x1400be64f  jnb     loc_1400BE731
0x1400be655  xor     r9d, r9d
0x1400be658  lea     r8, [rbp+FileHandle]
0x1400be65c  mov     dl, r12b
0x1400be65f  mov     rcx, rbx
0x1400be662  call    VhdmpiPinFile
0x1400be667  mov     rsi, [rbp+FileHandle]
0x1400be66b  mov     edi, eax
0x1400be66d  test    eax, eax
0x1400be66f  js      loc_1400BE70E
0x1400be675  mov     r9d, 8; Length
0x1400be67b  mov     [rbp+FileInformation], r14
0x1400be67f  lea     r8, [rbp+FileInformation]; FileInformation
0x1400be683  mov     [rsp+58h+FileInformationClass], 14h; FileInformationClass
0x1400be68b  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x1400be68f  mov     rcx, rsi; FileHandle
0x1400be692  call    cs:__imp_ZwSetInformationFile
0x1400be699  nop     dword ptr [rax+rax+00h]
0x1400be69e  mov     edi, eax
0x1400be6a0  test    eax, eax
0x1400be6a2  js      short loc_1400BE70E
0x1400be6a4  lea     rdx, [rbp+FileInformation]; struct _FILE_END_OF_FILE_INFORMATION *
0x1400be6a8  mov     rcx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x1400be6ab  call    ?RmwVhdFileSizeChangeNotification@@YAXPEAU_VHD_BACKING_STORE_HEADER@@PEAU_FILE_END_OF_FILE_INFORMATION@@@Z; RmwVhdFileSizeChangeNotification(_VHD_BACKING_STORE_HEADER *,_FILE_END_OF_FILE_INFORMATION *)
0x1400be6b0  mov     r9d, 8; Length
0x1400be6b6  mov     [rbp+arg_18], r14
0x1400be6ba  lea     r8, [rbp+arg_18]; FileInformation
0x1400be6be  mov     [rsp+58h+FileInformationClass], 27h ; '''; FileInformationClass
0x1400be6c6  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x1400be6ca  mov     rcx, rsi; FileHandle
0x1400be6cd  call    cs:__imp_ZwSetInformationFile
0x1400be6d4  nop     dword ptr [rax+rax+00h]
0x1400be6d9  mov     edi, eax
0x1400be6db  test    eax, eax
0x1400be6dd  js      short loc_1400BE70E
0x1400be6df  lea     rcx, [rbx+0E08h]
0x1400be6e6  mov     [rbx+490h], r14
0x1400be6ed  call    VhdmpiReleasePassiveLock
0x1400be6f2  mov     rcx, r13
0x1400be6f5  call    VhdmpiReleasePassiveLock
0x1400be6fa  xor     edx, edx; unsigned __int8
0x1400be6fc  mov     rcx, rbx; struct _VHD1_BACKING_STORE *
0x1400be6ff  xor     r12b, r12b
0x1400be702  call    ?VhdmpiFlushFooters@@YAJPEAU_VHD1_BACKING_STORE@@E@Z; VhdmpiFlushFooters(_VHD1_BACKING_STORE *,uchar)
0x1400be707  mov     edi, eax
0x1400be709  jmp     short loc_1400BE70E
0x1400be70b  xor     r12b, r12b
0x1400be70e  test    rsi, rsi
0x1400be711  jz      short loc_1400BE72D
0x1400be713  lea     rax, VhdmpiEmptyISOBackingStore
0x1400be71a  cmp     rbx, rax
0x1400be71d  jz      short loc_1400BE72D
0x1400be71f  lea     rcx, [rbx+48h]
0x1400be723  mov     edx, 1
0x1400be728  call    VhdmpiFileWrapperUnpinFile
0x1400be72d  test    edi, edi
0x1400be72f  js      short loc_1400BE73B
0x1400be731  mov     byte ptr [r15+59h], 1
0x1400be736  jmp     loc_1400BE7E9
0x1400be73b  mov     eax, cs:dword_1400876D0
0x1400be741  cmp     eax, 2
0x1400be744  jbe     short loc_1400BE786
0x1400be746  mov     edx, 8
0x1400be74b  lea     rcx, dword_1400876D0
0x1400be752  call    _tlgKeywordOn
0x1400be757  test    al, al
0x1400be759  jz      short loc_1400BE786
0x1400be75b  mov     r9d, 8; int
0x1400be761  mov     dword ptr [rsp+58h+var_30], edi; char
0x1400be765  lea     rax, aVhdmpivhd1actu; "VhdmpiVhd1ActuallyExpandOnMount: expand"...
0x1400be76c  mov     edx, 11EAh; int
0x1400be771  lea     rcx, aVhdmpivhd1actu_2; "VhdmpiVhd1ActuallyExpandOnMount"
0x1400be778  mov     qword ptr [rsp+58h+FileInformationClass], rax; char *
0x1400be77d  lea     r8d, [r9-6]; int
0x1400be781  call    TraceEvents
0x1400be786  lea     rcx, [rbp+arg_10]
0x1400be78a  call    VhdmpiIsFileLockFullyAcquired
0x1400be78f  test    al, al
0x1400be791  jz      short loc_1400BE7E9
0x1400be793  mov     eax, cs:dword_1400876D0
0x1400be799  mov     r8d, 3
0x1400be79f  cmp     eax, r8d
0x1400be7a2  jbe     short loc_1400BE7DE
0x1400be7a4  lea     edx, [r8+1]
0x1400be7a8  lea     rcx, dword_1400876D0
0x1400be7af  call    _tlgKeywordOn
0x1400be7b4  test    al, al
0x1400be7b6  jz      short loc_1400BE7DE
0x1400be7b8  lea     rax, aVhdmpivhd1actu_0; "VhdmpiVhd1ActuallyExpandOnMount: attemp"...
0x1400be7bf  mov     qword ptr [rsp+58h+var_30], rbx; char
0x1400be7c4  mov     edx, 11FBh; int
0x1400be7c9  mov     qword ptr [rsp+58h+FileInformationClass], rax; char *
0x1400be7ce  lea     r9d, [r8+1]; int
0x1400be7d2  lea     rcx, aVhdmpivhd1actu_2; "VhdmpiVhd1ActuallyExpandOnMount"
0x1400be7d9  call    TraceEvents
0x1400be7de  mov     dl, r12b; unsigned __int8
0x1400be7e1  mov     rcx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x1400be7e4  call    ?VhdmpiVhd1TryTruncateBackingStoreFileInternal@@YAJPEAU_VHD_BACKING_STORE_HEADER@@E@Z; VhdmpiVhd1TryTruncateBackingStoreFileInternal(_VHD_BACKING_STORE_HEADER *,uchar)
0x1400be7e9  test    r12b, r12b
0x1400be7ec  jz      short loc_1400BE806
0x1400be7ee  lea     rcx, [rbx+0E08h]
0x1400be7f5  call    VhdmpiReleasePassiveLock
0x1400be7fa  lea     rcx, [rbx+0E18h]
0x1400be801  call    VhdmpiReleasePassiveLock
0x1400be806  lea     rax, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\vhd\\vhdmp\\v"...
0x1400be80d  mov     dword ptr [rsp+58h+var_30], 1216h
0x1400be815  mov     r9b, 2
0x1400be818  mov     qword ptr [rsp+58h+FileInformationClass], rax
0x1400be81d  xor     r8d, r8d
0x1400be820  lea     rdx, [rbp+arg_10]
0x1400be824  mov     rcx, rbx
0x1400be827  call    VhdmpiLockUnlockVhdFile
0x1400be82c  mov     rcx, rbx
0x1400be82f  call    VhdmpiFlushBuffersFile
0x1400be834  mov     eax, cs:dword_1400876D0
0x1400be83a  cmp     eax, 4
0x1400be83d  jbe     short loc_1400BE884
0x1400be83f  mov     edx, 8
0x1400be844  lea     rcx, dword_1400876D0
0x1400be84b  call    _tlgKeywordOn
0x1400be850  test    al, al
0x1400be852  jz      short loc_1400BE884
0x1400be854  mov     r9d, 8; int
0x1400be85a  mov     dword ptr [rsp+58h+var_28], edi
0x1400be85e  lea     rax, aVhdmpivhd1actu_1; "VhdmpiVhd1ActuallyExpandOnMount: leavin"...
0x1400be865  mov     qword ptr [rsp+58h+var_30], r15; char
0x1400be86a  mov     edx, 1228h; int
0x1400be86f  mov     qword ptr [rsp+58h+FileInformationClass], rax; char *
0x1400be874  lea     rcx, aVhdmpivhd1actu_2; "VhdmpiVhd1ActuallyExpandOnMount"
0x1400be87b  lea     r8d, [r9-4]; int
0x1400be87f  call    TraceEvents
0x1400be884  mov     eax, edi
0x1400be886  add     rsp, 58h
0x1400be88a  pop     r15
0x1400be88c  pop     r14
0x1400be88e  pop     r13
0x1400be890  pop     r12
0x1400be892  pop     rdi
0x1400be893  pop     rsi
0x1400be894  pop     rbx
0x1400be895  pop     rbp
0x1400be896  retn
```
