# WerpCountFullDump

- ea: `0x14000da6c`
- end: `0x14000dc8b`
- name: `WerpCountFullDump`
- size: `543`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000d68c`

## callees

- `0x14000d174`
- `0x14000da6c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000dab9`
- `ntoskrnl!DbgPrintEx` at `0x14000db51`
- `ntoskrnl!DbgPrintEx` at `0x14000dc5c`
- `ntoskrnl!DbgPrintEx` at `0x14000dab9`
- `ntoskrnl!DbgPrintEx` at `0x14000db51`
- `ntoskrnl!DbgPrintEx` at `0x14000dc5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc3e`
- `ntoskrnl!ZwClose` at `0x14000dc20`
- `ntoskrnl!ZwClose` at `0x14000dc20`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000dc00`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000dc00`
- `ntoskrnl!ZwOpenFile` at `0x14000db2b`
- `ntoskrnl!ZwOpenFile` at `0x14000db2b`

## string_xrefs

- `0x14000db3f`: `WERKERNELHOST: Could not open root dump directory, status 0x%X\n`
- `0x14000dc7f`: `WERKERNELHOST: ZwQueryDirectoryFile failed with status 0x%X\n`

## pseudocode

```c
__int64 __fastcall WerpCountFullDump(_DWORD *a1)
{
  int v2; // edi
  NTSTATUS v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  unsigned int *Mem; // rdi
  ULONG Length; // r15d
  NTSTATUS i; // eax
  unsigned int *v10; // rcx
  unsigned int *v11; // rdx
  __int64 v12; // rax
  struct _UNICODE_STRING FileName; // [rsp+60h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+F0h] [rbp+67h] BYREF

  *(_QWORD *)&FileName.Length = 786442;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v2 = 10;
  FileName.Buffer = L"*.dmp";
  if ( a1 )
  {
    *a1 = 0;
    ObjectAttributes.ObjectName = &WerKernelLiveReportRootPath;
    FileHandle = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    IoStatusBlock = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = ZwOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 3u, 0x11u);
    v6 = v4;
    if ( v4 >= 0 )
    {
      if ( (unsigned int)dword_1400093C8 < 0xA )
        v2 = dword_1400093C8;
      Length = 532 * (v2 + 1);
      Mem = (unsigned int *)WerpAllocateMem(Length, v5);
      if ( Mem )
      {
        for ( i = ZwQueryDirectoryFile(
                    FileHandle,
                    0,
                    0,
                    0,
                    &IoStatusBlock,
                    Mem,
                    Length,
                    FileNamesInformation,
                    0,
                    &FileName,
                    1u);
              ;
              i = ZwQueryDirectoryFile(
                    FileHandle,
                    0,
                    0,
                    0,
                    &IoStatusBlock,
                    Mem,
                    Length,
                    FileNamesInformation,
                    0,
                    &FileName,
                    0) )
        {
          v6 = i;
          if ( i == -1073741809 || i == -2147483642 )
          {
            v6 = 0;
            goto LABEL_19;
          }
          if ( i < 0 )
            break;
          v10 = Mem;
          v11 = &Mem[Length / 4];
          if ( Mem < v11 )
          {
            do
            {
              ++*a1;
              v12 = *v10;
              if ( !(_DWORD)v12 )
                break;
              v10 = (unsigned int *)((char *)v10 + v12);
            }
            while ( v10 < v11 );
          }
        }
        DbgPrintEx(5u, 1u, "WERKERNELHOST: ZwQueryDirectoryFile failed with status 0x%X\n", (unsigned int)i);
      }
      else
      {
        v6 = -1073741801;
      }
    }
    else
    {
      Mem = 0;
      DbgPrintEx(5u, 1u, "WERKERNELHOST: Could not open root dump directory, status 0x%X\n", (unsigned int)v4);
    }
LABEL_19:
    if ( FileHandle )
    {
      ZwClose(FileHandle);
      FileHandle = 0;
    }
    if ( Mem )
      ExFreePoolWithTag(Mem, 0);
    DbgPrintEx(5u, 3u, "WERKERNELHOST: WerpCountFullDump returned FileCount 0x%X\n", *a1);
    return v6;
  }
  else
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpCountFullDump: Invalid params\n");
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14000da6c  push    rbp
0x14000da6e  push    rbx
0x14000da6f  push    rdi
0x14000da70  push    r13
0x14000da72  push    r14
0x14000da74  push    r15
0x14000da76  lea     rbp, [rsp-2Fh]
0x14000da7b  sub     rsp, 0B8h
0x14000da82  xor     eax, eax
0x14000da84  mov     qword ptr [rbp+57h+var_80.Length], 0C000Ah
0x14000da8c  mov     dword ptr [rbp+57h+ObjectAttributes+4], eax
0x14000da8f  mov     r14, rcx
0x14000da92  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], eax
0x14000da95  lea     edi, [rax+0Ah]
0x14000da98  lea     r13d, [rax+0Ch]
0x14000da9c  lea     rax, aDmp; "*.dmp"
0x14000daa3  mov     [rbp+57h+var_80.Buffer], rax
0x14000daa7  test    rcx, rcx
0x14000daaa  jnz     short loc_14000DACF
0x14000daac  lea     edx, [rcx+1]; Level
0x14000daaf  lea     ecx, [rdi-5]; ComponentId
0x14000dab2  lea     r8, aWerkernelhostW_34; "WERKERNELHOST: WerpCountFullDump: Inval"...
0x14000dab9  call    cs:__imp_DbgPrintEx
0x14000dac0  nop     dword ptr [rax+rax+00h]
0x14000dac5  mov     eax, 0C000000Dh
0x14000daca  jmp     loc_14000DC6A
0x14000dacf  xorps   xmm0, xmm0
0x14000dad2  mov     dword ptr [rcx], 0
0x14000dad8  lea     rax, WerKernelLiveReportRootPath
0x14000dadf  mov     [rsp+0E0h+OpenOptions], 11h; OpenOptions
0x14000dae7  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000daeb  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000daef  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000daf3  mov     [rbp+57h+FileHandle], 0
0x14000dafb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000daff  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000db06  mov     edx, 100001h; DesiredAccess
0x14000db0b  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14000db13  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14000db17  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000db1e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000db23  mov     [rsp+0E0h+ShareAccess], 3; ShareAccess
0x14000db2b  call    cs:__imp_ZwOpenFile
0x14000db32  nop     dword ptr [rax+rax+00h]
0x14000db37  mov     ebx, eax
0x14000db39  test    eax, eax
0x14000db3b  jns     short loc_14000DB62
0x14000db3d  xor     edi, edi
0x14000db3f  lea     r8, aWerkernelhostC_7; "WERKERNELHOST: Could not open root dump"...
0x14000db46  mov     r9d, eax
0x14000db49  mov     edx, 1; Level
0x14000db4e  lea     ecx, [rdx+4]; ComponentId
0x14000db51  call    cs:__imp_DbgPrintEx
0x14000db58  nop     dword ptr [rax+rax+00h]
0x14000db5d  jmp     loc_14000DC17
0x14000db62  cmp     cs:dword_1400093C8, edi
0x14000db68  cmovb   edi, cs:dword_1400093C8
0x14000db6f  lea     eax, [rdi+1]
0x14000db72  imul    r15d, eax, 214h
0x14000db79  mov     ecx, r15d
0x14000db7c  call    WerpAllocateMem
0x14000db81  mov     rdi, rax
0x14000db84  test    rax, rax
0x14000db87  jnz     short loc_14000DB93
0x14000db89  mov     ebx, 0C0000017h
0x14000db8e  jmp     loc_14000DC17
0x14000db93  mov     [rsp+0E0h+RestartScan], 1
0x14000db98  jmp     short loc_14000DBCE
0x14000db9a  cmp     ebx, 80000006h
0x14000dba0  jz      short loc_14000DC15
0x14000dba2  test    ebx, ebx
0x14000dba4  js      loc_14000DC7C
0x14000dbaa  mov     edx, r15d
0x14000dbad  mov     rcx, rdi
0x14000dbb0  add     rdx, rdi
0x14000dbb3  cmp     rdi, rdx
0x14000dbb6  jnb     short loc_14000DBC9
0x14000dbb8  inc     dword ptr [r14]
0x14000dbbb  mov     eax, [rcx]
0x14000dbbd  test    eax, eax
0x14000dbbf  jz      short loc_14000DBC9
0x14000dbc1  add     rcx, rax
0x14000dbc4  cmp     rcx, rdx
0x14000dbc7  jb      short loc_14000DBB8
0x14000dbc9  mov     [rsp+0E0h+RestartScan], 0; RestartScan
0x14000dbce  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000dbd2  lea     rax, [rbp+57h+var_80]
0x14000dbd6  mov     [rsp+0E0h+FileName], rax; FileName
0x14000dbdb  xor     r9d, r9d; ApcContext
0x14000dbde  mov     [rsp+0E0h+ReturnSingleEntry], 0; ReturnSingleEntry
0x14000dbe3  lea     rax, [rbp+57h+IoStatusBlock]
0x14000dbe7  mov     [rsp+0E0h+FileInformationClass], r13d; FileInformationClass
0x14000dbec  xor     r8d, r8d; ApcRoutine
0x14000dbef  mov     [rsp+0E0h+Length], r15d; Length
0x14000dbf4  xor     edx, edx; Event
0x14000dbf6  mov     qword ptr [rsp+0E0h+OpenOptions], rdi; FileInformation
0x14000dbfb  mov     qword ptr [rsp+0E0h+ShareAccess], rax; IoStatusBlock
0x14000dc00  call    cs:__imp_ZwQueryDirectoryFile
0x14000dc07  nop     dword ptr [rax+rax+00h]
0x14000dc0c  mov     ebx, eax
0x14000dc0e  cmp     eax, 0C000000Fh
0x14000dc13  jnz     short loc_14000DB9A
0x14000dc15  xor     ebx, ebx
0x14000dc17  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14000dc1b  test    rcx, rcx
0x14000dc1e  jz      short loc_14000DC34
0x14000dc20  call    cs:__imp_ZwClose
0x14000dc27  nop     dword ptr [rax+rax+00h]
0x14000dc2c  mov     [rbp+57h+FileHandle], 0
0x14000dc34  test    rdi, rdi
0x14000dc37  jz      short loc_14000DC4A
0x14000dc39  xor     edx, edx; Tag
0x14000dc3b  mov     rcx, rdi; P
0x14000dc3e  call    cs:__imp_ExFreePoolWithTag
0x14000dc45  nop     dword ptr [rax+rax+00h]
0x14000dc4a  mov     r9d, [r14]
0x14000dc4d  lea     r8, aWerkernelhostW_17; "WERKERNELHOST: WerpCountFullDump return"...
0x14000dc54  mov     edx, 3; Level
0x14000dc59  lea     ecx, [rdx+2]; ComponentId
0x14000dc5c  call    cs:__imp_DbgPrintEx
0x14000dc63  nop     dword ptr [rax+rax+00h]
0x14000dc68  mov     eax, ebx
0x14000dc6a  add     rsp, 0B8h
0x14000dc71  pop     r15
0x14000dc73  pop     r14
0x14000dc75  pop     r13
0x14000dc77  pop     rdi
0x14000dc78  pop     rbx
0x14000dc79  pop     rbp
0x14000dc7a  retn
0x14000dc7c  mov     r9d, ebx
0x14000dc7f  lea     r8, aWerkernelhostZ_12; "WERKERNELHOST: ZwQueryDirectoryFile fai"...
0x14000dc86  jmp     loc_14000DB49
```
