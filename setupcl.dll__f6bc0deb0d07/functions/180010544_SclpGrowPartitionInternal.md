# SclpGrowPartitionInternal

- ea: `0x180010544`
- end: `0x1800108c8`
- name: `SclpGrowPartitionInternal`
- size: `900`
- prototype: `__int64 __fastcall(__int64, void *, void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180010170`

## callees

- `0x18000a524`
- `0x180010544`
- `0x1800179c5`
- `0x1800179e0`

## import_xrefs

- `ntdll!_wcsnicmp` at `0x180010624`
- `ntdll!_wcsnicmp` at `0x180010645`
- `ntdll!_wcsnicmp` at `0x180010669`
- `ntdll!_wcsnicmp` at `0x180010624`
- `ntdll!_wcsnicmp` at `0x180010645`
- `ntdll!_wcsnicmp` at `0x180010669`
- `ntdll!NtDeviceIoControlFile` at `0x1800107aa`
- `ntdll!NtDeviceIoControlFile` at `0x1800107aa`
- `ntdll!NtFsControlFile` at `0x18001081e`
- `ntdll!NtFsControlFile` at `0x18001081e`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800105d4`
- `ntdll!NtQueryVolumeInformationFile` at `0x180010691`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800105d4`
- `ntdll!NtQueryVolumeInformationFile` at `0x180010691`

## string_xrefs

- `0x180010872`: `Partition extension not needed.`

## pseudocode

```c
__int64 __fastcall SclpGrowPartitionInternal(__int64 a1, void *a2, void *a3, __int64 a4, __int64 a5)
{
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  char *v11; // rax
  int v12; // r9d
  int v13; // eax
  NTSTATUS v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r13
  __int64 v18; // r15
  __int64 v19; // r12
  __int64 v20; // rcx
  NTSTATUS v21; // eax
  NTSTATUS v22; // eax
  __int64 v23; // rcx
  PVOID InputBuffer; // [rsp+30h] [rbp-D0h]
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+70h] [rbp-90h]
  HANDLE FileHandle; // [rsp+78h] [rbp-88h]
  HANDLE v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h] BYREF
  __int64 v33; // [rsp+90h] [rbp-70h]
  __int128 v34; // [rsp+98h] [rbp-68h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-58h]
  _BYTE FsInformation[8]; // [rsp+B0h] [rbp-50h] BYREF
  int v37; // [rsp+B8h] [rbp-48h]
  wchar_t String1[42]; // [rsp+BCh] [rbp-44h] BYREF

  v31 = a3;
  FileHandle = a2;
  LODWORD(v33) = 0;
  v28 = a4;
  v29 = a5;
  v35 = 0;
  v32 = 0;
  v26 = 0;
  v34 = 0;
  IoStatusBlock = 0;
  memset_0(FsInformation, 0, 0x60u);
  v8 = NtQueryVolumeInformationFile(a3, &IoStatusBlock, FsInformation, 0x60u, FileFsAttributeInformation);
  v9 = v8;
  if ( v8 < 0 )
  {
    LODWORD(InputBuffer) = v8;
    v10 = a1 + 1152;
    v11 = "(%lx): Unable to get file system attributes.";
    v12 = 325;
    if ( !a1 )
      v10 = 0;
LABEL_29:
    SclLogGenericMessage(
      v10,
      3,
      (int)SclEvent_Generic_Error,
      v12,
      (__int64)"SclpGrowPartitionInternal",
      v11,
      InputBuffer);
    return v9;
  }
  v13 = v37;
  if ( v37 == 8 )
  {
    if ( !_wcsnicmp(String1, L"NTFS", 4u) )
      goto LABEL_13;
    v13 = v37;
  }
  if ( v13 == 6 )
  {
    if ( !_wcsnicmp(String1, L"FAT", 3u) )
      goto LABEL_13;
    v13 = v37;
  }
  if ( v13 != 10 || _wcsnicmp(String1, L"FAT32", 5u) )
    return 50;
LABEL_13:
  v14 = NtQueryVolumeInformationFile(a3, &IoStatusBlock, &v34, 0x18u, FileFsSizeInformation);
  v9 = v14;
  if ( v14 >= 0 )
  {
    v16 = *(_QWORD *)(a4 + 32) - *(_QWORD *)(a5 + 8);
    v17 = *(_QWORD *)(a5 + 16);
    v18 = (v16 / 0x100000) << 20;
    if ( v18 <= v17 )
    {
      if ( a1 )
        v23 = a1 + 1152;
      else
        v23 = 0;
      SclLogGenericMessage(
        v23,
        1,
        (int)SclEvent_Generic_Info,
        388,
        (__int64)"SclpGrowPartitionInternal",
        "Partition extension not needed.");
    }
    else
    {
      v19 = a1 + 1152;
      v20 = a1 + 1152;
      if ( !a1 )
        v20 = 0;
      SclLogGenericMessage(
        v20,
        1,
        (int)SclEvent_Generic_Info,
        384,
        (__int64)"SclpGrowPartitionInternal",
        "Grow partition [%ws] and its volume from from [%lld] to [%lld].",
        144LL * *(unsigned int *)(a5 + 24) + v28 + 120,
        v17,
        v18);
      LODWORD(v32) = *(_DWORD *)(v29 + 24);
      v33 = v18 - v17;
      v21 = NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x7C0D0u, &v32, 0x10u, 0, 0);
      v9 = v21;
      if ( v21 < 0 )
      {
        LODWORD(InputBuffer) = v21;
        v11 = "(%lx): Unable to grow partition.";
        v12 = 414;
        if ( !a1 )
          v19 = 0;
        v10 = v19;
        goto LABEL_29;
      }
      v26 = v18 / HIDWORD(v35);
      v22 = NtFsControlFile(v31, 0, 0, 0, &IoStatusBlock, 0x900F0u, &v26, 8u, 0, 0);
      v9 = v22;
      if ( v22 < 0 )
      {
        LODWORD(InputBuffer) = v22;
        v10 = 0;
        v11 = "(%lx): Unable to extend volume.";
        if ( a1 )
          v10 = a1 + 1152;
        v12 = 438;
        goto LABEL_29;
      }
    }
  }
  else
  {
    if ( a1 )
      v15 = a1 + 1152;
    else
      v15 = 0;
    SclLogGenericMessage(
      v15,
      3,
      (int)SclEvent_Generic_Error,
      364,
      (__int64)"SclpGrowPartitionInternal",
      "(%lx): Unable to get file system size information.",
      v14);
  }
  return v9;
}

```

## disassembly

```asm
0x180010544  push    rbp
0x180010546  push    rbx
0x180010547  push    rsi
0x180010548  push    rdi
0x180010549  push    r12
0x18001054b  push    r13
0x18001054d  push    r15
0x18001054f  lea     rbp, [rsp-20h]
0x180010554  sub     rsp, 120h
0x18001055b  mov     rax, cs:__security_cookie
0x180010562  xor     rax, rsp
0x180010565  mov     [rbp+50h+var_40], rax
0x180010569  mov     rsi, [rbp+50h+arg_20]
0x180010570  xor     eax, eax
0x180010572  xorps   xmm0, xmm0
0x180010575  mov     [rbp+50h+var_D0], r8
0x180010579  mov     r15, r8
0x18001057c  mov     [rsp+150h+FileHandle], rdx
0x180010581  mov     rdi, rcx
0x180010584  mov     qword ptr [rbp+50h+var_C4], rax
0x180010588  lea     ebx, [rax+60h]
0x18001058b  mov     [rsp+150h+var_E8], r9
0x180010590  mov     r8d, ebx; Size
0x180010593  mov     [rsp+150h+var_E0], rsi
0x180010598  xor     edx, edx; Val
0x18001059a  mov     [rbp+50h+var_A8], rax
0x18001059e  lea     rcx, [rbp+50h+FsInformation]; void *
0x1800105a2  mov     [rbp-78h], rax
0x1800105a6  mov     r13, r9
0x1800105a9  mov     [rsp+150h+var_100], rax
0x1800105ae  movups  [rbp+50h+var_B8], xmm0
0x1800105b2  movups  xmmword ptr [rsp+150h+IoStatusBlock], xmm0
0x1800105b7  call    memset_0
0x1800105bc  lea     r12d, [rbx-5Bh]
0x1800105c0  mov     r9d, ebx; Length
0x1800105c3  lea     r8, [rbp+50h+FsInformation]; FsInformation
0x1800105c7  mov     [rsp+150h+FsInformationClass], r12d; FsInformationClass
0x1800105cc  lea     rdx, [rsp+150h+IoStatusBlock]; IoStatusBlock
0x1800105d1  mov     rcx, r15; FileHandle
0x1800105d4  call    cs:__imp_NtQueryVolumeInformationFile
0x1800105da  mov     ebx, eax
0x1800105dc  test    eax, eax
0x1800105de  jns     short loc_18001060D
0x1800105e0  xor     edx, edx
0x1800105e2  mov     dword ptr [rsp+150h+InputBuffer], eax
0x1800105e6  test    rdi, rdi
0x1800105e9  lea     rcx, [rdi+480h]
0x1800105f0  lea     rax, aLxUnableToGetF_0; "(%lx): Unable to get file system attrib"...
0x1800105f7  mov     r9d, 145h
0x1800105fd  cmovz   rcx, rdx
0x180010601  lea     rsi, aSclpgrowpartit_0; "SclpGrowPartitionInternal"
0x180010608  jmp     loc_180010845
0x18001060d  mov     eax, [rbp+50h+var_98]
0x180010610  cmp     eax, 8
0x180010613  jnz     short loc_180010631
0x180010615  lea     r8d, [rax-4]; MaxCount
0x180010619  lea     rdx, aNtfs; "NTFS"
0x180010620  lea     rcx, [rbp+50h+String1]; String1
0x180010624  call    cs:__imp__wcsnicmp
0x18001062a  test    eax, eax
0x18001062c  jz      short loc_180010677
0x18001062e  mov     eax, [rbp+50h+var_98]
0x180010631  cmp     eax, 6
0x180010634  jnz     short loc_180010652
0x180010636  lea     r8d, [rax-3]; MaxCount
0x18001063a  lea     rdx, aFat; "FAT"
0x180010641  lea     rcx, [rbp+50h+String1]; String1
0x180010645  call    cs:__imp__wcsnicmp
0x18001064b  test    eax, eax
0x18001064d  jz      short loc_180010677
0x18001064f  mov     eax, [rbp+50h+var_98]
0x180010652  cmp     eax, 0Ah
0x180010655  jnz     loc_1800108A3
0x18001065b  mov     r8, r12; MaxCount
0x18001065e  lea     rdx, aFat32; "FAT32"
0x180010665  lea     rcx, [rbp+50h+String1]; String1
0x180010669  call    cs:__imp__wcsnicmp
0x18001066f  test    eax, eax
0x180010671  jnz     loc_1800108A3
0x180010677  mov     r9d, 18h; Length
0x18001067d  mov     [rsp+150h+FsInformationClass], 3; FsInformationClass
0x180010685  lea     r8, [rbp+50h+var_B8]; FsInformation
0x180010689  mov     rcx, r15; FileHandle
0x18001068c  lea     rdx, [rsp+150h+IoStatusBlock]; IoStatusBlock
0x180010691  call    cs:__imp_NtQueryVolumeInformationFile
0x180010697  mov     ebx, eax
0x180010699  test    eax, eax
0x18001069b  jns     short loc_1800106CA
0x18001069d  test    rdi, rdi
0x1800106a0  jz      short loc_1800106AB
0x1800106a2  lea     rcx, [rdi+480h]
0x1800106a9  jmp     short loc_1800106AD
0x1800106ab  xor     ecx, ecx
0x1800106ad  mov     dword ptr [rsp+150h+InputBuffer], eax
0x1800106b1  lea     rsi, aSclpgrowpartit_0; "SclpGrowPartitionInternal"
0x1800106b8  lea     rax, aLxUnableToGetF; "(%lx): Unable to get file system size i"...
0x1800106bf  mov     r9d, 16Ch
0x1800106c5  jmp     loc_180010845
0x1800106ca  mov     rax, [r13+20h]
0x1800106ce  mov     ecx, 100000h
0x1800106d3  sub     rax, [rsi+8]
0x1800106d7  mov     r13, [rsi+10h]
0x1800106db  cqo
0x1800106dd  idiv    rcx
0x1800106e0  mov     r15, rax
0x1800106e3  shl     r15, 14h
0x1800106e7  cmp     r15, r13
0x1800106ea  jle     loc_180010862
0x1800106f0  mov     eax, [rsi+18h]
0x1800106f3  lea     r12, [rdi+480h]
0x1800106fa  mov     rdx, [rsp+150h+var_E8]
0x1800106ff  lea     rsi, aSclpgrowpartit_0; "SclpGrowPartitionInternal"
0x180010706  add     rdx, 78h ; 'x'
0x18001070a  mov     [rsp+150h+OutputBuffer], r15
0x18001070f  mov     qword ptr [rsp+150h+InputBufferLength], r13
0x180010714  lea     r8, SclEvent_Generic_Info
0x18001071b  lea     rcx, [rax+rax*8]
0x18001071f  mov     r9d, 180h
0x180010725  shl     rcx, 4
0x180010729  xor     eax, eax
0x18001072b  add     rdx, rcx
0x18001072e  mov     rcx, r12
0x180010731  mov     [rsp+150h+InputBuffer], rdx
0x180010736  test    rdi, rdi
0x180010739  mov     edx, 1
0x18001073e  cmovz   rcx, rax
0x180010742  lea     rax, aGrowPartitionW; "Grow partition [%ws] and its volume fro"...
0x180010749  mov     qword ptr [rsp+150h+IoControlCode], rax
0x18001074e  mov     qword ptr [rsp+150h+FsInformationClass], rsi
0x180010753  call    SclLogGenericMessage
0x180010758  mov     rcx, [rsp+150h+var_E0]
0x18001075d  xor     r9d, r9d; ApcContext
0x180010760  xor     r8d, r8d; ApcRoutine
0x180010763  xor     edx, edx; Event
0x180010765  mov     eax, [rcx+18h]
0x180010768  mov     rcx, [rsp+150h+FileHandle]; FileHandle
0x18001076d  mov     [rbp+50h+var_C8], eax
0x180010770  mov     rax, r15
0x180010773  sub     rax, r13
0x180010776  xor     r13d, r13d
0x180010779  mov     [rsp+150h+OutputBufferLength], r13d; OutputBufferLength
0x18001077e  mov     [rsp+150h+OutputBuffer], r13; OutputBuffer
0x180010783  mov     qword ptr [rbp+50h+var_C4+4], rax
0x180010787  lea     rax, [rbp+50h+var_C8]
0x18001078b  mov     [rsp+150h+InputBufferLength], 10h; InputBufferLength
0x180010793  mov     [rsp+150h+InputBuffer], rax; InputBuffer
0x180010798  lea     rax, [rsp+150h+IoStatusBlock]
0x18001079d  mov     [rsp+150h+IoControlCode], 7C0D0h; IoControlCode
0x1800107a5  mov     qword ptr [rsp+150h+FsInformationClass], rax; IoStatusBlock
0x1800107aa  call    cs:__imp_NtDeviceIoControlFile
0x1800107b0  mov     ebx, eax
0x1800107b2  test    eax, eax
0x1800107b4  jns     short loc_1800107D3
0x1800107b6  test    rdi, rdi
0x1800107b9  mov     dword ptr [rsp+150h+InputBuffer], eax
0x1800107bd  lea     rax, aLxUnableToGrow; "(%lx): Unable to grow partition."
0x1800107c4  mov     r9d, 19Eh
0x1800107ca  cmovz   r12, r13
0x1800107ce  mov     rcx, r12
0x1800107d1  jmp     short loc_180010845
0x1800107d3  mov     r8d, dword ptr [rbp+50h+var_A8+4]
0x1800107d7  mov     rax, r15
0x1800107da  mov     rcx, [rbp+50h+var_D0]; FileHandle
0x1800107de  cqo
0x1800107e0  idiv    r8
0x1800107e3  mov     [rsp+150h+OutputBufferLength], r13d; OutputBufferLength
0x1800107e8  xor     r9d, r9d; ApcContext
0x1800107eb  mov     [rsp+150h+OutputBuffer], r13; OutputBuffer
0x1800107f0  xor     r8d, r8d; ApcRoutine
0x1800107f3  mov     [rsp+150h+var_100], rax
0x1800107f8  xor     edx, edx; Event
0x1800107fa  mov     [rsp+150h+InputBufferLength], 8; InputBufferLength
0x180010802  lea     rax, [rsp+150h+var_100]
0x180010807  mov     [rsp+150h+InputBuffer], rax; InputBuffer
0x18001080c  lea     rax, [rsp+150h+IoStatusBlock]
0x180010811  mov     [rsp+150h+IoControlCode], 900F0h; FsControlCode
0x180010819  mov     qword ptr [rsp+150h+FsInformationClass], rax; IoStatusBlock
0x18001081e  call    cs:__imp_NtFsControlFile
0x180010824  mov     ebx, eax
0x180010826  test    eax, eax
0x180010828  jns     short loc_1800108A8
0x18001082a  test    rdi, rdi
0x18001082d  mov     dword ptr [rsp+150h+InputBuffer], eax
0x180010831  mov     rcx, r13
0x180010834  lea     rax, aLxUnableToExte; "(%lx): Unable to extend volume."
0x18001083b  cmovnz  rcx, r12
0x18001083f  mov     r9d, 1B6h
0x180010845  mov     qword ptr [rsp+150h+IoControlCode], rax
0x18001084a  lea     r8, SclEvent_Generic_Error
0x180010851  mov     edx, 3
0x180010856  mov     qword ptr [rsp+150h+FsInformationClass], rsi
0x18001085b  call    SclLogGenericMessage
0x180010860  jmp     short loc_1800108A8
0x180010862  test    rdi, rdi
0x180010865  jz      short loc_180010870
0x180010867  lea     rcx, [rdi+480h]
0x18001086e  jmp     short loc_180010872
0x180010870  xor     ecx, ecx
0x180010872  lea     rax, aPartitionExten; "Partition extension not needed."
0x180010879  mov     r9d, 184h
0x18001087f  mov     qword ptr [rsp+150h+IoControlCode], rax
0x180010884  lea     rsi, aSclpgrowpartit_0; "SclpGrowPartitionInternal"
0x18001088b  lea     r8, SclEvent_Generic_Info
0x180010892  mov     qword ptr [rsp+150h+FsInformationClass], rsi
0x180010897  mov     edx, 1
0x18001089c  call    SclLogGenericMessage
0x1800108a1  jmp     short loc_1800108A8
0x1800108a3  mov     ebx, 32h ; '2'
0x1800108a8  mov     eax, ebx
0x1800108aa  mov     rcx, [rbp+50h+var_40]
0x1800108ae  xor     rcx, rsp; StackCookie
0x1800108b1  call    __security_check_cookie
0x1800108b6  add     rsp, 120h
0x1800108bd  pop     r15
0x1800108bf  pop     r13
0x1800108c1  pop     r12
0x1800108c3  pop     rdi
0x1800108c4  pop     rsi
0x1800108c5  pop     rbx
0x1800108c6  pop     rbp
0x1800108c7  retn
```
