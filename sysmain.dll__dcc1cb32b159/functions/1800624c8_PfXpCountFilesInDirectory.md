# PfXpCountFilesInDirectory

- ea: `0x1800624c8`
- end: `0x1800626c7`
- name: `PfXpCountFilesInDirectory`
- size: `511`
- prototype: `__int64 __fastcall(PCWSTR DosPathName)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003aa6c`
- `0x180062320`

## callees

- `0x1800624c8`

## import_xrefs

- `ntdll!NtQueryDirectoryFile` at `0x180062609`
- `ntdll!NtQueryDirectoryFile` at `0x180062609`
- `ntdll!RtlFreeHeap` at `0x180062685`
- `ntdll!RtlFreeHeap` at `0x180062685`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18006252e`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18006252e`
- `ntdll!NtOpenFile` at `0x180062583`
- `ntdll!NtOpenFile` at `0x180062583`
- `ntdll!RtlInitUnicodeString` at `0x18006251b`
- `ntdll!RtlInitUnicodeString` at `0x18006251b`
- `ntdll!RtlNtStatusToDosError` at `0x18006258f`
- `ntdll!RtlNtStatusToDosError` at `0x18006258f`
- `ntdll!NtClose` at `0x180062694`
- `ntdll!NtClose` at `0x180062694`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800626af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800626af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800625af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800625af`

## pseudocode

```c
__int64 __fastcall PfXpCountFilesInDirectory(PCWSTR DosPathName, __int64 a2, _DWORD *a3, _QWORD *a4)
{
  unsigned int *v7; // rdi
  ULONG v8; // ebx
  int v9; // eax
  int v10; // ebx
  BOOLEAN RestartScan; // r8
  __int64 v12; // rsi
  unsigned int *i; // rcx
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+108h] [rbp+6Fh] BYREF

  FileHandle = 0;
  v7 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  NtPathName = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"*.pf");
  if ( RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0) )
  {
    ObjectAttributes.ObjectName = &NtPathName;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 3u, 0x4021u);
    if ( v9 >= 0 )
    {
      v7 = (unsigned int *)HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0x2500u);
      if ( v7 )
      {
        v10 = 0;
        RestartScan = 1;
        v12 = 0;
        while ( 1 )
        {
          v9 = NtQueryDirectoryFile(
                 FileHandle,
                 0,
                 0,
                 0,
                 &IoStatusBlock,
                 v7,
                 0x2500u,
                 FileDirectoryInformation,
                 0,
                 &DestinationString,
                 RestartScan);
          if ( v9 == -1073741809 && !v10 )
            break;
          if ( v9 == -2147483642 )
            break;
          if ( (v9 & 0xC0000000) == 0xC0000000 )
            goto LABEL_4;
          RestartScan = 0;
          for ( i = v7; i < v7 + 2368; i = (unsigned int *)((char *)i + *i) )
          {
            v12 += *((_QWORD *)i + 5);
            ++v10;
            if ( !*i )
              break;
          }
        }
        *a3 = v10;
        if ( a4 )
          *a4 = v12;
        v8 = 0;
      }
      else
      {
        v8 = 8;
      }
    }
    else
    {
LABEL_4:
      v8 = RtlNtStatusToDosError(v9);
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  }
  else
  {
    v8 = 3;
  }
  if ( FileHandle )
    NtClose(FileHandle);
  if ( v7 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v7);
  return v8;
}

```

## disassembly

```asm
0x1800624c8  mov     [rsp-8+FileHandle], rdx
0x1800624cd  push    rbp
0x1800624ce  push    rbx
0x1800624cf  push    rsi
0x1800624d0  push    rdi
0x1800624d1  push    r14
0x1800624d3  push    r15
0x1800624d5  lea     rbp, [rsp-2Fh]
0x1800624da  sub     rsp, 0C8h
0x1800624e1  xorps   xmm0, xmm0
0x1800624e4  lea     rdx, aPf; "*.pf"
0x1800624eb  mov     rbx, rcx
0x1800624ee  xor     eax, eax
0x1800624f0  xorps   xmm1, xmm1
0x1800624f3  mov     [rbp+57h+FileHandle], rax
0x1800624f7  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800624fb  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800624ff  mov     r14, r9
0x180062502  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180062506  mov     r15, r8
0x180062509  xor     edi, edi
0x18006250b  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18006250f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180062513  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x180062517  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18006251b  call    cs:__imp_RtlInitUnicodeString
0x180062521  xor     r9d, r9d; DirectoryInfo
0x180062524  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x180062528  xor     r8d, r8d; NtFileNamePart
0x18006252b  mov     rcx, rbx; DosPathName
0x18006252e  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180062534  test    al, al
0x180062536  jnz     short loc_180062540
0x180062538  lea     ebx, [rdi+3]
0x18006253b  jmp     loc_18006268B
0x180062540  lea     rax, [rbp+57h+NtPathName]
0x180062544  mov     [rsp+0F0h+OpenOptions], 4021h; OpenOptions
0x18006254c  xorps   xmm0, xmm0
0x18006254f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180062553  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180062557  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006255e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180062562  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180062566  mov     edx, 100001h; DesiredAccess
0x18006256b  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180062572  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180062576  mov     [rsp+0F0h+ShareAccess], 3; ShareAccess
0x18006257e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180062583  call    cs:__imp_NtOpenFile
0x180062589  test    eax, eax
0x18006258b  jns     short loc_18006259C
0x18006258d  mov     ecx, eax; Status
0x18006258f  call    cs:__imp_RtlNtStatusToDosError
0x180062595  mov     ebx, eax
0x180062597  jmp     loc_180062672
0x18006259c  mov     rcx, cs:PfSvcGlobals
0x1800625a3  xor     edx, edx; dwFlags
0x1800625a5  mov     r8d, 2500h; dwBytes
0x1800625ab  mov     rcx, [rcx+58h]; hHeap
0x1800625af  call    cs:__imp_HeapAlloc
0x1800625b5  mov     rdi, rax
0x1800625b8  test    rax, rax
0x1800625bb  jnz     short loc_1800625C5
0x1800625bd  lea     ebx, [rax+8]
0x1800625c0  jmp     loc_180062672
0x1800625c5  xor     ebx, ebx
0x1800625c7  mov     r8b, 1
0x1800625ca  xor     esi, esi
0x1800625cc  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800625d0  lea     rax, [rbp+57h+DestinationString]
0x1800625d4  mov     [rsp+0F0h+RestartScan], r8b; RestartScan
0x1800625d9  xor     r9d, r9d; ApcContext
0x1800625dc  mov     [rsp+0F0h+FileName], rax; FileName
0x1800625e1  xor     r8d, r8d; ApcRoutine
0x1800625e4  mov     [rsp+0F0h+ReturnSingleEntry], 0; ReturnSingleEntry
0x1800625e9  lea     rax, [rbp+57h+IoStatusBlock]
0x1800625ed  mov     [rsp+0F0h+FileInformationClass], 1; FileInformationClass
0x1800625f5  xor     edx, edx; Event
0x1800625f7  mov     [rsp+0F0h+Length], 2500h; Length
0x1800625ff  mov     qword ptr [rsp+0F0h+OpenOptions], rdi; FileInformation
0x180062604  mov     qword ptr [rsp+0F0h+ShareAccess], rax; IoStatusBlock
0x180062609  call    cs:__imp_NtQueryDirectoryFile
0x18006260f  cmp     eax, 0C000000Fh
0x180062614  jnz     short loc_18006261A
0x180062616  test    ebx, ebx
0x180062618  jz      short loc_180062665
0x18006261a  cmp     eax, 80000006h
0x18006261f  jz      short loc_180062665
0x180062621  mov     ecx, eax
0x180062623  and     ecx, 0C0000000h
0x180062629  cmp     ecx, 0C0000000h
0x18006262f  jz      loc_18006258D
0x180062635  xor     r8b, r8b
0x180062638  lea     rdx, [rdi+2500h]
0x18006263f  mov     rcx, rdi
0x180062642  cmp     rdi, rdx
0x180062645  jnb     short loc_1800625CC
0x180062647  add     rsi, [rcx+28h]
0x18006264b  inc     ebx
0x18006264d  cmp     dword ptr [rcx], 0
0x180062650  jz      loc_1800625CC
0x180062656  mov     eax, [rcx]
0x180062658  add     rcx, rax
0x18006265b  cmp     rcx, rdx
0x18006265e  jb      short loc_180062647
0x180062660  jmp     loc_1800625CC
0x180062665  mov     [r15], ebx
0x180062668  test    r14, r14
0x18006266b  jz      short loc_180062670
0x18006266d  mov     [r14], rsi
0x180062670  xor     ebx, ebx
0x180062672  mov     rcx, gs:60h
0x18006267b  xor     edx, edx; Flags
0x18006267d  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x180062681  mov     rcx, [rcx+30h]; HeapHandle
0x180062685  call    cs:__imp_RtlFreeHeap
0x18006268b  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18006268f  test    rcx, rcx
0x180062692  jz      short loc_18006269A
0x180062694  call    cs:__imp_NtClose
0x18006269a  test    rdi, rdi
0x18006269d  jz      short loc_1800626B5
0x18006269f  mov     rcx, cs:PfSvcGlobals
0x1800626a6  mov     r8, rdi; lpMem
0x1800626a9  xor     edx, edx; dwFlags
0x1800626ab  mov     rcx, [rcx+58h]; hHeap
0x1800626af  call    cs:__imp_HeapFree
0x1800626b5  mov     eax, ebx
0x1800626b7  add     rsp, 0C8h
0x1800626be  pop     r15
0x1800626c0  pop     r14
0x1800626c2  pop     rdi
0x1800626c3  pop     rsi
0x1800626c4  pop     rbx
0x1800626c5  pop     rbp
0x1800626c6  retn
```
