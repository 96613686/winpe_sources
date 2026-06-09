# SmpCreatePagingFiles

- ea: `0x14000fcf8`
- end: `0x14000fec8`
- name: `SmpCreatePagingFiles`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x14000f120`

## callees

- `0x140009100`
- `0x14000b464`
- `0x14000b4ac`
- `0x14000d494`
- `0x14000d4c0`
- `0x14000d53c`
- `0x14000efb8`
- `0x14000f3ec`
- `0x14000f4d8`
- `0x14000f5b0`
- `0x14000fa74`
- `0x14000fcf8`
- `0x1400101ec`
- `0x140010344`
- `0x140011158`
- `0x140011438`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14000feb4`
- `ntdll!RtlFreeHeap` at `0x14000feb4`
- `ntdll!NtSetSystemInformation` at `0x14000fd89`
- `ntdll!NtSetSystemInformation` at `0x14000fd89`

## string_xrefs

- `0x14000fd42`: `SmpCreatePagingFiles`
- `0x14000fd96`: `SmpCreatePagingFiles`

## pseudocode

```c
BOOLEAN SmpCreatePagingFiles()
{
  int VolumeDescriptors; // eax
  __int64 v1; // rdx
  BOOLEAN result; // al
  __int64 i; // rbx
  NTSTATUS v4; // eax
  __int64 v5; // rcx
  __int64 *v6; // rdi
  __int64 *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  PVOID *v10; // rdi
  char v11; // bl
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  _OWORD v16[2]; // [rsp+20h] [rbp-28h] BYREF
  int SystemInformation; // [rsp+50h] [rbp+8h] BYREF
  __int64 v18; // [rsp+58h] [rbp+10h] BYREF

  v18 = 0;
  v16[0] = 0;
  SystemInformation = 0;
  SmpCreateDedicatedMemoryPagefile();
  VolumeDescriptors = SmpBuildFilesStringFromList(&SmpExistingPageFilesList, v16);
  if ( VolumeDescriptors < 0 )
  {
    v1 = 2770;
LABEL_3:
    result = SmpLogFailure("SmpCreatePagingFiles", v1, (unsigned int)VolumeDescriptors);
    goto LABEL_31;
  }
  SmpSaveOldPageFiles();
  for ( i = SmpExistingPageFilesList; (__int64 *)i != &SmpExistingPageFilesList; i = *(_QWORD *)i )
    SmpCheckForCrashDump((struct _UNICODE_STRING *)(i + 16));
  SystemInformation = 2;
  v4 = NtSetSystemInformation(SystemCrashDumpStateInformation, &SystemInformation, 4u);
  if ( v4 < 0 )
    SmpLogFailure("SmpCreatePagingFiles", 2794, (unsigned int)v4);
  v6 = (__int64 *)SmpPagingFileList;
  while ( v6 != &SmpPagingFileList )
  {
    v7 = v6;
    SmpCreatePagingFileDescriptor((__int64)(v6 + 2));
    v6 = (__int64 *)*v6;
    SmpFreeSavedRegistryEntry(v7);
  }
  if ( !SmpNumberOfPagefileDescriptors && !SmpRegistrySpecifierPresent )
  {
    result = SmpCleanupStalePageFiles(v5);
    goto LABEL_31;
  }
  VolumeDescriptors = SmpCreateVolumeDescriptors(v5);
  if ( VolumeDescriptors < 0 )
  {
    v1 = 2843;
    goto LABEL_3;
  }
  SmpAdjustPagefileSizeforLowStorage(v8);
  v10 = (PVOID *)SmpPagingFileDescriptorList;
  v11 = 0;
  if ( SmpPagingFileDescriptorList != &SmpPagingFileDescriptorList )
  {
    do
    {
      v12 = SmpProcessPagefileDescriptor(v10);
      v10 = (PVOID *)*v10;
      if ( v12 >= 0 )
        v11 = 1;
    }
    while ( v10 != &SmpPagingFileDescriptorList );
    if ( v11 )
      goto LABEL_23;
  }
  if ( (int)SmpCreateEmergencyPagingFile(v9) >= 0 )
  {
LABEL_23:
    v14 = SmpCreateWorkingSetSwapPagingFile(&v18);
    if ( v14 < 0 )
    {
      if ( v14 != -1073741710 || SmpNumberOfPagefilesCreated != 1 )
        goto LABEL_30;
      v15 = 63;
      goto LABEL_29;
    }
    if ( (*(_BYTE *)(v18 + 16) & 0x10) != 0 )
    {
      v15 = *(unsigned __int16 *)(v18 + 28);
LABEL_29:
      SmpEnableSwapOnPagingFiles(&SmpPagingFileDescriptorList, v15);
    }
  }
LABEL_30:
  SmpCleanupStalePageFiles(v13);
  result = SmpRecordCreatedPageFiles(v11 == 0, (__int64)v16);
LABEL_31:
  if ( *((_QWORD *)&v16[0] + 1) )
    return RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, *((PVOID *)&v16[0] + 1));
  return result;
}

```

## disassembly

```asm
0x14000fcf8  mov     rax, rsp
0x14000fcfb  mov     [rax+18h], rbx
0x14000fcff  push    rbp
0x14000fd00  push    rdi
0x14000fd01  push    r14
0x14000fd03  sub     rsp, 30h
0x14000fd07  xorps   xmm0, xmm0
0x14000fd0a  mov     qword ptr [rax+10h], 0
0x14000fd12  movups  xmmword ptr [rax-28h], xmm0
0x14000fd16  mov     dword ptr [rax+8], 0
0x14000fd1d  call    SmpCreateDedicatedMemoryPagefile
0x14000fd22  lea     rdi, SmpExistingPageFilesList
0x14000fd29  mov     rcx, rdi
0x14000fd2c  lea     rdx, [rsp+48h+var_28]
0x14000fd31  call    SmpBuildFilesStringFromList
0x14000fd36  test    eax, eax
0x14000fd38  jns     short loc_14000FD53
0x14000fd3a  mov     edx, 0AD2h
0x14000fd3f  mov     r8d, eax
0x14000fd42  lea     rcx, aSmpcreatepagin_1; "SmpCreatePagingFiles"
0x14000fd49  call    SmpLogFailure
0x14000fd4e  jmp     loc_14000FE98
0x14000fd53  call    SmpSaveOldPageFiles
0x14000fd58  mov     rbx, cs:SmpExistingPageFilesList
0x14000fd5f  jmp     short loc_14000FD6D
0x14000fd61  lea     rcx, [rbx+10h]
0x14000fd65  call    SmpCheckForCrashDump
0x14000fd6a  mov     rbx, [rbx]
0x14000fd6d  cmp     rbx, rdi
0x14000fd70  jnz     short loc_14000FD61
0x14000fd72  mov     r8d, 4; SystemInformationLength
0x14000fd78  mov     [rsp+48h+SystemInformation], 2
0x14000fd80  lea     rdx, [rsp+48h+SystemInformation]; SystemInformation
0x14000fd85  lea     ecx, [r8+1Eh]; SystemInformationClass
0x14000fd89  call    cs:__imp_NtSetSystemInformation
0x14000fd8f  test    eax, eax
0x14000fd91  jns     short loc_14000FDA7
0x14000fd93  mov     r8d, eax
0x14000fd96  lea     rcx, aSmpcreatepagin_1; "SmpCreatePagingFiles"
0x14000fd9d  mov     edx, 0AEAh
0x14000fda2  call    SmpLogFailure
0x14000fda7  mov     rdi, cs:SmpPagingFileList
0x14000fdae  lea     rbp, SmpPagingFileList
0x14000fdb5  jmp     short loc_14000FDCE
0x14000fdb7  lea     rcx, [rdi+10h]
0x14000fdbb  mov     rbx, rdi
0x14000fdbe  call    SmpCreatePagingFileDescriptor
0x14000fdc3  mov     rdi, [rdi]
0x14000fdc6  mov     rcx, rbx
0x14000fdc9  call    SmpFreeSavedRegistryEntry
0x14000fdce  cmp     rdi, rbp
0x14000fdd1  jnz     short loc_14000FDB7
0x14000fdd3  cmp     cs:SmpNumberOfPagefileDescriptors, 0
0x14000fdda  jnz     short loc_14000FDEF
0x14000fddc  cmp     cs:SmpRegistrySpecifierPresent, 0
0x14000fde3  jnz     short loc_14000FDEF
0x14000fde5  call    SmpCleanupStalePageFiles
0x14000fdea  jmp     loc_14000FE98
0x14000fdef  call    SmpCreateVolumeDescriptors
0x14000fdf4  test    eax, eax
0x14000fdf6  jns     short loc_14000FE02
0x14000fdf8  mov     edx, 0B1Bh
0x14000fdfd  jmp     loc_14000FD3F
0x14000fe02  call    SmpAdjustPagefileSizeforLowStorage
0x14000fe07  mov     rdi, cs:SmpPagingFileDescriptorList
0x14000fe0e  lea     rbp, SmpPagingFileDescriptorList
0x14000fe15  xor     bl, bl
0x14000fe17  mov     r14d, 1
0x14000fe1d  cmp     rdi, rbp
0x14000fe20  jz      short loc_14000FE3F
0x14000fe22  mov     rcx, rdi
0x14000fe25  call    SmpProcessPagefileDescriptor
0x14000fe2a  mov     rdi, [rdi]
0x14000fe2d  test    eax, eax
0x14000fe2f  movzx   ebx, bl
0x14000fe32  cmovns  ebx, r14d
0x14000fe36  cmp     rdi, rbp
0x14000fe39  jnz     short loc_14000FE22
0x14000fe3b  test    bl, bl
0x14000fe3d  jnz     short loc_14000FE48
0x14000fe3f  call    SmpCreateEmergencyPagingFile
0x14000fe44  test    eax, eax
0x14000fe46  js      short loc_14000FE84
0x14000fe48  lea     rcx, [rsp+48h+arg_8]
0x14000fe4d  call    SmpCreateWorkingSetSwapPagingFile
0x14000fe52  test    eax, eax
0x14000fe54  js      short loc_14000FE67
0x14000fe56  mov     rdx, [rsp+48h+arg_8]
0x14000fe5b  test    byte ptr [rdx+10h], 10h
0x14000fe5f  jz      short loc_14000FE84
0x14000fe61  movzx   edx, word ptr [rdx+1Ch]
0x14000fe65  jmp     short loc_14000FE7C
0x14000fe67  cmp     eax, 0C0000072h
0x14000fe6c  jnz     short loc_14000FE84
0x14000fe6e  cmp     cs:SmpNumberOfPagefilesCreated, r14d
0x14000fe75  jnz     short loc_14000FE84
0x14000fe77  mov     edx, 3Fh ; '?'
0x14000fe7c  mov     rcx, rbp
0x14000fe7f  call    SmpEnableSwapOnPagingFiles
0x14000fe84  call    SmpCleanupStalePageFiles
0x14000fe89  test    bl, bl
0x14000fe8b  lea     rdx, [rsp+48h+var_28]
0x14000fe90  setz    cl
0x14000fe93  call    SmpRecordCreatedPageFiles
0x14000fe98  cmp     [rsp+48h+BaseAddress], 0
0x14000fe9e  jz      short loc_14000FEBA
0x14000fea0  mov     rcx, gs:60h
0x14000fea9  xor     edx, edx; Flags
0x14000feab  mov     r8, [rsp+48h+BaseAddress]; BaseAddress
0x14000feb0  mov     rcx, [rcx+30h]; HeapHandle
0x14000feb4  call    cs:__imp_RtlFreeHeap
0x14000feba  mov     rbx, [rsp+48h+arg_10]
0x14000febf  add     rsp, 30h
0x14000fec3  pop     r14
0x14000fec5  pop     rdi
0x14000fec6  pop     rbp
0x14000fec7  retn
```
