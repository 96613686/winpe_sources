# VhdmpiVhd1ActuallyExpandOnMount(_VHD_VIRTUAL_DISK *)

- ea: `0x1400be510`
- end: `0x1400be8a8`
- name: `?VhdmpiVhd1ActuallyExpandOnMount@@YAJPEAU_VHD_VIRTUAL_DISK@@@Z`
- size: `920`
- prototype: `__int64 __fastcall(struct _VHD_VIRTUAL_DISK *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x14003bfcc`

## callees

- `0x14001b7fc`
- `0x14001bc68`
- `0x140022234`
- `0x140023560`
- `0x140026510`
- `0x140032c64`
- `0x14003386c`
- `0x140035e94`
- `0x14003e7a8`
- `0x1400bd53c`
- `0x1400be510`
- `0x1400e266c`
- `0x1400e7be4`
- `0x1400ea570`

## import_xrefs

- `ntoskrnl!ZwSetInformationFile` at `0x1400be6a2`
- `ntoskrnl!ZwSetInformationFile` at `0x1400be6dd`
- `ntoskrnl!ZwSetInformationFile` at `0x1400be6a2`
- `ntoskrnl!ZwSetInformationFile` at `0x1400be6dd`

## string_xrefs

- `0x1400be86e`: `VhdmpiVhd1ActuallyExpandOnMount: leaving... VirtualDisk 0x%p (0x%08x)`
- `0x1400be571`: `VhdmpiVhd1ActuallyExpandOnMount: enter... VirtualDisk 0x%p`
- `0x1400be636`: `VhdmpiVhd1ActuallyExpandOnMount: TargetFileSize: 0x%016I64x Existing file size: 0x%016I64x`
- `0x1400be57d`: `VhdmpiVhd1ActuallyExpandOnMount`
- `0x1400be64c`: `VhdmpiVhd1ActuallyExpandOnMount`
- `0x1400be781`: `VhdmpiVhd1ActuallyExpandOnMount`
- `0x1400be7e2`: `VhdmpiVhd1ActuallyExpandOnMount`
- `0x1400be884`: `VhdmpiVhd1ActuallyExpandOnMount`
- `0x1400be7c8`: `VhdmpiVhd1ActuallyExpandOnMount: attempting to truncate BackingStore 0x%p due to failure`
- `0x1400be775`: `VhdmpiVhd1ActuallyExpandOnMount: expand on mount failed (0x%08x)`

## pseudocode

```c
__int64 __fastcall VhdmpiVhd1ActuallyExpandOnMount(struct _VHD_VIRTUAL_DISK *a1)
{
  __int64 v2; // rbx
  HANDLE v3; // rsi
  NTSTATUS v4; // edi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned __int8 v9; // r12
  __int64 v10; // rdx
  unsigned __int64 v11; // r14
  int v12; // eax
  int v13; // r8d
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int64 FileInformation; // [rsp+A0h] [rbp+48h] BYREF
  HANDLE FileHandle; // [rsp+A8h] [rbp+50h] BYREF
  __int64 v18; // [rsp+B0h] [rbp+58h] BYREF
  unsigned __int64 v19; // [rsp+B8h] [rbp+60h] BYREF

  FileInformation = 0;
  v18 = 0;
  v19 = 0;
  IoStatusBlock = 0;
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
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
    v9 = 0;
  }
  else
  {
    VhdmpiLockUnlockVhdFile(
      v2,
      (unsigned int)&v18,
      1,
      2,
      (char)"onecore\\vm\\dv\\storage\\vhd\\vhdmp\\vhd1parser.c",
      4437);
    VhdmpiAcquirePassiveLock(v2 + 3608, v5, v6);
    VhdmpiAcquirePassiveLock(v2 + 3592, v7, v8);
    v9 = 1;
    v11 = VhdmpiCalculateMaxPotentialFooterLocation((struct _VHD1_BACKING_STORE *)v2) + *(unsigned int *)(v2 + 1924);
    if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
      TraceEvents(
        "VhdmpiVhd1ActuallyExpandOnMount",
        0x1171u,
        4u,
        8u,
        "VhdmpiVhd1ActuallyExpandOnMount: TargetFileSize: 0x%016I64x Existing file size: 0x%016I64x",
        v11,
        *(_QWORD *)(v2 + 1168));
    if ( *(_QWORD *)(v2 + 1168) >= v11 )
      goto LABEL_18;
    LOBYTE(v10) = 1;
    v12 = VhdmpiPinFile(v2, v10, &FileHandle, 0);
    v3 = FileHandle;
    v4 = v12;
    if ( v12 >= 0 )
    {
      FileInformation = v11;
      v4 = ZwSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 8u, FileEndOfFileInformation);
      if ( v4 >= 0 )
      {
        RmwVhdFileSizeChangeNotification(
          (struct _VHD_BACKING_STORE_HEADER *)v2,
          (struct _FILE_END_OF_FILE_INFORMATION *)&FileInformation);
        v19 = v11;
        v4 = ZwSetInformationFile(v3, &IoStatusBlock, &v19, 8u, FileValidDataLengthInformation);
        if ( v4 >= 0 )
        {
          *(_QWORD *)(v2 + 1168) = v11;
          VhdmpiReleasePassiveLock(v2 + 3592);
          VhdmpiReleasePassiveLock(v2 + 3608);
          v9 = 0;
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
  if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
    TraceEvents(
      "VhdmpiVhd1ActuallyExpandOnMount",
      0x11EAu,
      2u,
      8u,
      "VhdmpiVhd1ActuallyExpandOnMount: expand on mount failed (0x%08x)",
      v4);
  if ( (unsigned __int8)VhdmpiIsFileLockFullyAcquired(&v18) )
  {
    if ( (unsigned int)dword_140087708 > 3 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
      TraceEvents(
        "VhdmpiVhd1ActuallyExpandOnMount",
        0x11FBu,
        v13,
        v13 + 1,
        "VhdmpiVhd1ActuallyExpandOnMount: attempting to truncate BackingStore 0x%p due to failure",
        (const void *)v2);
    VhdmpiVhd1TryTruncateBackingStoreFileInternal((struct _VHD_BACKING_STORE_HEADER *)v2, v9);
  }
LABEL_27:
  if ( v9 )
  {
    VhdmpiReleasePassiveLock(v2 + 3592);
    VhdmpiReleasePassiveLock(v2 + 3608);
  }
  VhdmpiLockUnlockVhdFile(
    v2,
    (unsigned int)&v18,
    0,
    2,
    (char)"onecore\\vm\\dv\\storage\\vhd\\vhdmp\\vhd1parser.c",
    4630);
  VhdmpiFlushBuffersFile(v2);
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
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
0x1400be510  push    rbp
0x1400be512  push    rbx
0x1400be513  push    rsi
0x1400be514  push    rdi
0x1400be515  push    r12
0x1400be517  push    r13
0x1400be519  push    r14
0x1400be51b  push    r15
0x1400be51d  mov     rbp, rsp
0x1400be520  sub     rsp, 58h
0x1400be524  mov     eax, cs:dword_140087708
0x1400be52a  xorps   xmm0, xmm0
0x1400be52d  mov     [rbp+FileInformation], 0
0x1400be535  mov     r15, rcx
0x1400be538  mov     [rbp+arg_10], 0
0x1400be540  mov     [rbp+arg_18], 0
0x1400be548  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1400be54c  cmp     eax, 4
0x1400be54f  jbe     short loc_1400BE592
0x1400be551  mov     edx, 8
0x1400be556  lea     rcx, dword_140087708
0x1400be55d  call    _tlgKeywordOn
0x1400be562  test    al, al
0x1400be564  jz      short loc_1400BE592
0x1400be566  mov     r9d, 8; int
0x1400be56c  mov     qword ptr [rsp+58h+var_30], r15; char
0x1400be571  lea     rax, aVhdmpivhd1actu_4; "VhdmpiVhd1ActuallyExpandOnMount: enter."...
0x1400be578  mov     edx, 1131h; int
0x1400be57d  lea     rcx, aVhdmpivhd1actu_2; "VhdmpiVhd1ActuallyExpandOnMount"
0x1400be584  mov     qword ptr [rsp+58h+FileInformationClass], rax; char *
0x1400be589  lea     r8d, [r9-4]; int
0x1400be58d  call    TraceEvents
0x1400be592  mov     rbx, [r15+90h]
0x1400be599  lea     rax, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\vhd\\vhdmp\\v"...
0x1400be5a0  xor     esi, esi
0x1400be5a2  xor     edi, edi
0x1400be5a4  mov     [rbp+FileHandle], rsi
0x1400be5a8  cmp     dword ptr [rbx+7C4h], 2
0x1400be5af  jz      loc_1400BE71B
0x1400be5b5  mov     dword ptr [rsp+58h+var_30], 1155h
0x1400be5bd  lea     rdx, [rbp+arg_10]
0x1400be5c1  mov     r9b, 2
0x1400be5c4  mov     qword ptr [rsp+58h+FileInformationClass], rax
0x1400be5c9  mov     r8b, 1
0x1400be5cc  mov     rcx, rbx
0x1400be5cf  call    VhdmpiLockUnlockVhdFile
0x1400be5d4  lea     r13, [rbx+0E18h]
0x1400be5db  mov     rcx, r13
0x1400be5de  call    VhdmpiAcquirePassiveLock
0x1400be5e3  lea     rcx, [rbx+0E08h]
0x1400be5ea  call    VhdmpiAcquirePassiveLock
0x1400be5ef  mov     rcx, rbx; struct _VHD1_BACKING_STORE *
0x1400be5f2  mov     r12b, 1
0x1400be5f5  call    ?VhdmpiCalculateMaxPotentialFooterLocation@@YA_KPEAU_VHD1_BACKING_STORE@@@Z; VhdmpiCalculateMaxPotentialFooterLocation(_VHD1_BACKING_STORE *)
0x1400be5fa  mov     r14d, [rbx+784h]
0x1400be601  add     r14, rax
0x1400be604  mov     eax, cs:dword_140087708
0x1400be60a  cmp     eax, 4
0x1400be60d  jbe     short loc_1400BE658
0x1400be60f  lea     edx, [rsi+8]
0x1400be612  lea     rcx, dword_140087708
0x1400be619  call    _tlgKeywordOn
0x1400be61e  test    al, al
0x1400be620  jz      short loc_1400BE658
0x1400be622  mov     rax, [rbx+490h]
0x1400be629  lea     r9d, [rsi+8]; int
0x1400be62d  mov     [rsp+58h+var_28], rax
0x1400be632  lea     r8d, [rsi+4]; int
0x1400be636  lea     rax, aVhdmpivhd1actu_3; "VhdmpiVhd1ActuallyExpandOnMount: Target"...
0x1400be63d  mov     qword ptr [rsp+58h+var_30], r14; char
0x1400be642  mov     edx, 1171h; int
0x1400be647  mov     qword ptr [rsp+58h+FileInformationClass], rax; char *
0x1400be64c  lea     rcx, aVhdmpivhd1actu_2; "VhdmpiVhd1ActuallyExpandOnMount"
0x1400be653  call    TraceEvents
0x1400be658  cmp     [rbx+490h], r14
0x1400be65f  jnb     loc_1400BE741
0x1400be665  xor     r9d, r9d
0x1400be668  lea     r8, [rbp+FileHandle]
0x1400be66c  mov     dl, r12b
0x1400be66f  mov     rcx, rbx
0x1400be672  call    VhdmpiPinFile
0x1400be677  mov     rsi, [rbp+FileHandle]
0x1400be67b  mov     edi, eax
0x1400be67d  test    eax, eax
0x1400be67f  js      loc_1400BE71E
0x1400be685  mov     r9d, 8; Length
0x1400be68b  mov     [rbp+FileInformation], r14
0x1400be68f  lea     r8, [rbp+FileInformation]; FileInformation
0x1400be693  mov     [rsp+58h+FileInformationClass], 14h; FileInformationClass
0x1400be69b  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x1400be69f  mov     rcx, rsi; FileHandle
0x1400be6a2  call    cs:__imp_ZwSetInformationFile
0x1400be6a9  nop     dword ptr [rax+rax+00h]
0x1400be6ae  mov     edi, eax
0x1400be6b0  test    eax, eax
0x1400be6b2  js      short loc_1400BE71E
0x1400be6b4  lea     rdx, [rbp+FileInformation]; struct _FILE_END_OF_FILE_INFORMATION *
0x1400be6b8  mov     rcx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x1400be6bb  call    ?RmwVhdFileSizeChangeNotification@@YAXPEAU_VHD_BACKING_STORE_HEADER@@PEAU_FILE_END_OF_FILE_INFORMATION@@@Z; RmwVhdFileSizeChangeNotification(_VHD_BACKING_STORE_HEADER *,_FILE_END_OF_FILE_INFORMATION *)
0x1400be6c0  mov     r9d, 8; Length
0x1400be6c6  mov     [rbp+arg_18], r14
0x1400be6ca  lea     r8, [rbp+arg_18]; FileInformation
0x1400be6ce  mov     [rsp+58h+FileInformationClass], 27h ; '''; FileInformationClass
0x1400be6d6  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x1400be6da  mov     rcx, rsi; FileHandle
0x1400be6dd  call    cs:__imp_ZwSetInformationFile
0x1400be6e4  nop     dword ptr [rax+rax+00h]
0x1400be6e9  mov     edi, eax
0x1400be6eb  test    eax, eax
0x1400be6ed  js      short loc_1400BE71E
0x1400be6ef  lea     rcx, [rbx+0E08h]
0x1400be6f6  mov     [rbx+490h], r14
0x1400be6fd  call    VhdmpiReleasePassiveLock
0x1400be702  mov     rcx, r13
0x1400be705  call    VhdmpiReleasePassiveLock
0x1400be70a  xor     edx, edx; unsigned __int8
0x1400be70c  mov     rcx, rbx; struct _VHD1_BACKING_STORE *
0x1400be70f  xor     r12b, r12b
0x1400be712  call    ?VhdmpiFlushFooters@@YAJPEAU_VHD1_BACKING_STORE@@E@Z; VhdmpiFlushFooters(_VHD1_BACKING_STORE *,uchar)
0x1400be717  mov     edi, eax
0x1400be719  jmp     short loc_1400BE71E
0x1400be71b  xor     r12b, r12b
0x1400be71e  test    rsi, rsi
0x1400be721  jz      short loc_1400BE73D
0x1400be723  lea     rax, VhdmpiEmptyISOBackingStore
0x1400be72a  cmp     rbx, rax
0x1400be72d  jz      short loc_1400BE73D
0x1400be72f  lea     rcx, [rbx+48h]
0x1400be733  mov     edx, 1
0x1400be738  call    VhdmpiFileWrapperUnpinFile
0x1400be73d  test    edi, edi
0x1400be73f  js      short loc_1400BE74B
0x1400be741  mov     byte ptr [r15+59h], 1
0x1400be746  jmp     loc_1400BE7F9
0x1400be74b  mov     eax, cs:dword_140087708
0x1400be751  cmp     eax, 2
0x1400be754  jbe     short loc_1400BE796
0x1400be756  mov     edx, 8
0x1400be75b  lea     rcx, dword_140087708
0x1400be762  call    _tlgKeywordOn
0x1400be767  test    al, al
0x1400be769  jz      short loc_1400BE796
0x1400be76b  mov     r9d, 8; int
0x1400be771  mov     dword ptr [rsp+58h+var_30], edi; char
0x1400be775  lea     rax, aVhdmpivhd1actu; "VhdmpiVhd1ActuallyExpandOnMount: expand"...
0x1400be77c  mov     edx, 11EAh; int
0x1400be781  lea     rcx, aVhdmpivhd1actu_2; "VhdmpiVhd1ActuallyExpandOnMount"
0x1400be788  mov     qword ptr [rsp+58h+FileInformationClass], rax; char *
0x1400be78d  lea     r8d, [r9-6]; int
0x1400be791  call    TraceEvents
0x1400be796  lea     rcx, [rbp+arg_10]
0x1400be79a  call    VhdmpiIsFileLockFullyAcquired
0x1400be79f  test    al, al
0x1400be7a1  jz      short loc_1400BE7F9
0x1400be7a3  mov     eax, cs:dword_140087708
0x1400be7a9  mov     r8d, 3
0x1400be7af  cmp     eax, r8d
0x1400be7b2  jbe     short loc_1400BE7EE
0x1400be7b4  lea     edx, [r8+1]
0x1400be7b8  lea     rcx, dword_140087708
0x1400be7bf  call    _tlgKeywordOn
0x1400be7c4  test    al, al
0x1400be7c6  jz      short loc_1400BE7EE
0x1400be7c8  lea     rax, aVhdmpivhd1actu_0; "VhdmpiVhd1ActuallyExpandOnMount: attemp"...
0x1400be7cf  mov     qword ptr [rsp+58h+var_30], rbx; char
0x1400be7d4  mov     edx, 11FBh; int
0x1400be7d9  mov     qword ptr [rsp+58h+FileInformationClass], rax; char *
0x1400be7de  lea     r9d, [r8+1]; int
0x1400be7e2  lea     rcx, aVhdmpivhd1actu_2; "VhdmpiVhd1ActuallyExpandOnMount"
0x1400be7e9  call    TraceEvents
0x1400be7ee  mov     dl, r12b; unsigned __int8
0x1400be7f1  mov     rcx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x1400be7f4  call    ?VhdmpiVhd1TryTruncateBackingStoreFileInternal@@YAJPEAU_VHD_BACKING_STORE_HEADER@@E@Z; VhdmpiVhd1TryTruncateBackingStoreFileInternal(_VHD_BACKING_STORE_HEADER *,uchar)
0x1400be7f9  test    r12b, r12b
0x1400be7fc  jz      short loc_1400BE816
0x1400be7fe  lea     rcx, [rbx+0E08h]
0x1400be805  call    VhdmpiReleasePassiveLock
0x1400be80a  lea     rcx, [rbx+0E18h]
0x1400be811  call    VhdmpiReleasePassiveLock
0x1400be816  lea     rax, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\vhd\\vhdmp\\v"...
0x1400be81d  mov     dword ptr [rsp+58h+var_30], 1216h
0x1400be825  mov     r9b, 2
0x1400be828  mov     qword ptr [rsp+58h+FileInformationClass], rax
0x1400be82d  xor     r8d, r8d
0x1400be830  lea     rdx, [rbp+arg_10]
0x1400be834  mov     rcx, rbx
0x1400be837  call    VhdmpiLockUnlockVhdFile
0x1400be83c  mov     rcx, rbx
0x1400be83f  call    VhdmpiFlushBuffersFile
0x1400be844  mov     eax, cs:dword_140087708
0x1400be84a  cmp     eax, 4
0x1400be84d  jbe     short loc_1400BE894
0x1400be84f  mov     edx, 8
0x1400be854  lea     rcx, dword_140087708
0x1400be85b  call    _tlgKeywordOn
0x1400be860  test    al, al
0x1400be862  jz      short loc_1400BE894
0x1400be864  mov     r9d, 8; int
0x1400be86a  mov     dword ptr [rsp+58h+var_28], edi
0x1400be86e  lea     rax, aVhdmpivhd1actu_1; "VhdmpiVhd1ActuallyExpandOnMount: leavin"...
0x1400be875  mov     qword ptr [rsp+58h+var_30], r15; char
0x1400be87a  mov     edx, 1228h; int
0x1400be87f  mov     qword ptr [rsp+58h+FileInformationClass], rax; char *
0x1400be884  lea     rcx, aVhdmpivhd1actu_2; "VhdmpiVhd1ActuallyExpandOnMount"
0x1400be88b  lea     r8d, [r9-4]; int
0x1400be88f  call    TraceEvents
0x1400be894  mov     eax, edi
0x1400be896  add     rsp, 58h
0x1400be89a  pop     r15
0x1400be89c  pop     r14
0x1400be89e  pop     r13
0x1400be8a0  pop     r12
0x1400be8a2  pop     rdi
0x1400be8a3  pop     rsi
0x1400be8a4  pop     rbx
0x1400be8a5  pop     rbp
0x1400be8a6  retn
```
