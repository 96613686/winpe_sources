# AslFileMappingCreate

- ea: `0x14000f644`
- end: `0x14000f978`
- name: `AslFileMappingCreate`
- size: `820`
- prototype: `__int64 __fastcall(_QWORD *, const WCHAR *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140016198`
- `0x140018e34`

## callees

- `0x14000f644`
- `0x14000f980`
- `0x14001008c`
- `0x140010d44`
- `0x14002e420`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x14000f7b2`
- `msvcrt!_wcsnicmp` at `0x14000f7b2`
- `ntdll!RtlFreeUnicodeString` at `0x14000f941`
- `ntdll!RtlFreeUnicodeString` at `0x14000f941`
- `ntdll!RtlInitUnicodeString` at `0x14000f6b7`
- `ntdll!RtlInitUnicodeString` at `0x14000f6b7`
- `ntdll!RtlAllocateHeap` at `0x14000f6d4`
- `ntdll!RtlAllocateHeap` at `0x14000f6d4`
- `ntdll!ZwClose` at `0x14000f892`
- `ntdll!ZwClose` at `0x14000f892`
- `ntdll!ZwCreateFile` at `0x14000f865`
- `ntdll!ZwCreateFile` at `0x14000f865`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14000f7c9`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14000f7c9`
- `ntdll!ZwQueryInformationFile` at `0x14000f765`
- `ntdll!ZwQueryInformationFile` at `0x14000f765`

## string_xrefs

- `0x14000f7d9`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x14000f785`: `AslFileMappingCreate`
- `0x14000f7e9`: `AslFileMappingCreate`
- `0x14000f8eb`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x14000f901`: `RtlFileMapInitializeByFilePath failed %S [%x]`

## pseudocode

```c
__int64 __fastcall AslFileMappingCreate(_QWORD *a1, const WCHAR *a2, __int64 a3)
{
  char *Heap; // rax
  char *v7; // rdi
  NTSTATUS v8; // ebx
  NTSTATUS v9; // eax
  __int64 v10; // r8
  const char *v11; // r9
  __int64 v12; // rax
  int v13; // eax
  const char *v14; // r9
  __int64 v15; // r8
  void *v16; // rcx
  unsigned __int64 v17; // rax
  __int64 v18; // rcx
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+20h] [rbp-A1h]
  __int64 FileAttributes; // [rsp+28h] [rbp-99h]
  void *FileHandle; // [rsp+60h] [rbp-61h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK v26; // [rsp+B8h] [rbp-9h] BYREF
  __int128 FileInformation; // [rsp+C8h] [rbp+7h] BYREF
  __int64 v28; // [rsp+D8h] [rbp+17h]

  v28 = 0;
  FileInformation = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  if ( !a2 || !*a2 || !a1 )
    return 3221225485LL;
  *a1 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x50u);
  v7 = Heap;
  if ( Heap )
  {
    v9 = AslStringDuplicate(Heap, a2);
    v8 = v9;
    if ( v9 < 0 )
    {
      v10 = 123;
      v11 = "AslStringDuplicate failed [%x]";
LABEL_14:
      FileInformationClass[0] = v9;
      AslLogCallPrintf(1, "AslFileMappingCreate", v10, v11, *(_QWORD *)FileInformationClass);
LABEL_15:
      AslFileMappingDelete(v7);
      goto LABEL_36;
    }
    v12 = 0;
    if ( a3 != -1 )
      v12 = a3;
    if ( v12 )
    {
      *(_OWORD *)(v7 + 8) = 0;
      *(_OWORD *)(v7 + 24) = 0;
      *(_OWORD *)(v7 + 40) = 0;
      *((_QWORD *)v7 + 1) = v12;
LABEL_12:
      v28 = 0;
      IoStatusBlock = 0;
      FileInformation = 0;
      v9 = ZwQueryInformationFile(*((HANDLE *)v7 + 1), &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v8 = 0;
        *((_QWORD *)v7 + 3) = *((_QWORD *)&FileInformation + 1);
        *((_DWORD *)v7 + 14) = (*((_QWORD *)&FileInformation + 1) != 0) + 1;
        *a1 = v7;
        goto LABEL_36;
      }
      v11 = "NtQueryInformationFile failed [%x]";
      v10 = 183;
      goto LABEL_14;
    }
    if ( _wcsnicmp(a2, L"\\SystemRoot\\", 0xCu)
      && (v13 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &DestinationString, 0, 0), v8 = v13, v13 < 0) )
    {
      LODWORD(FileAttributes) = v13;
      v14 = "RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]";
      v15 = 148;
    }
    else
    {
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      v26 = 0;
      FileHandle = 0;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v8 = ZwCreateFile(&FileHandle, 0x80100080, &ObjectAttributes, &v26, 0, 0x80u, 5u, 1u, 0x60u, 0, 0);
      if ( v8 < 0 )
      {
        v16 = FileHandle;
      }
      else
      {
        v16 = 0;
        *((_QWORD *)v7 + 1) = FileHandle;
        v8 = 0;
        FileHandle = 0;
        v7[48] = 1;
      }
      if ( v16 )
        ZwClose(v16);
      if ( v8 >= 0 )
        goto LABEL_12;
      if ( v8 == -1073741766 || v8 == -1073741772 || v8 == -1073741620 )
        goto LABEL_15;
      v17 = (unsigned int)(v8 + 1073741805);
      if ( (unsigned int)v17 <= 0x30 && (v18 = 0x1000000008001LL, _bittest64(&v18, v17)) || v8 == -1073741638 )
      {
        LODWORD(FileAttributes) = v8;
        AslLogCallPrintf(
          3,
          "AslFileMappingCreate",
          163,
          "RtlFileMapInitializeByFilePath failed %S [%x]",
          a2,
          FileAttributes);
        goto LABEL_15;
      }
      LODWORD(FileAttributes) = v8;
      v14 = "RtlFileMapInitializeByFilePath failed %S [%x]";
      v15 = 161;
    }
    AslLogCallPrintf(1, "AslFileMappingCreate", v15, v14, a2, FileAttributes);
    goto LABEL_15;
  }
  v8 = -1073741801;
LABEL_36:
  if ( DestinationString.Buffer != a2 )
    RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000f644  mov     [rsp-8+arg_10], rbx
0x14000f649  mov     [rsp-8+arg_18], rsi
0x14000f64e  push    rbp
0x14000f64f  push    rdi
0x14000f650  push    r12
0x14000f652  push    r14
0x14000f654  push    r15
0x14000f656  lea     rbp, [rsp-2Fh]
0x14000f65b  sub     rsp, 0F0h
0x14000f662  mov     rax, cs:__security_cookie
0x14000f669  xor     rax, rsp
0x14000f66c  mov     [rbp+4Fh+var_30], rax
0x14000f670  xor     eax, eax
0x14000f672  xorps   xmm0, xmm0
0x14000f675  xor     r12d, r12d
0x14000f678  mov     [rbp+4Fh+var_38], rax
0x14000f67c  xorps   xmm1, xmm1
0x14000f67f  mov     r14, r8
0x14000f682  mov     rsi, rdx
0x14000f685  mov     r15, rcx
0x14000f688  movups  [rbp+4Fh+FileInformation], xmm0
0x14000f68c  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x14000f690  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm1
0x14000f694  test    rdx, rdx
0x14000f697  jz      loc_14000F94B
0x14000f69d  cmp     [rdx], r12w
0x14000f6a1  jz      loc_14000F94B
0x14000f6a7  test    rcx, rcx
0x14000f6aa  jz      loc_14000F94B
0x14000f6b0  mov     [rcx], r12
0x14000f6b3  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14000f6b7  call    cs:__imp_RtlInitUnicodeString
0x14000f6bd  mov     rcx, gs:60h
0x14000f6c6  lea     edx, [r12+8]; Flags
0x14000f6cb  lea     r8d, [r12+50h]; Size
0x14000f6d0  mov     rcx, [rcx+30h]; HeapHandle
0x14000f6d4  call    cs:__imp_RtlAllocateHeap
0x14000f6da  mov     rdi, rax
0x14000f6dd  test    rax, rax
0x14000f6e0  jnz     short loc_14000F6EC
0x14000f6e2  mov     ebx, 0C0000017h
0x14000f6e7  jmp     loc_14000F937
0x14000f6ec  mov     rdx, rsi
0x14000f6ef  mov     rcx, rdi
0x14000f6f2  call    AslStringDuplicate
0x14000f6f7  mov     ebx, eax
0x14000f6f9  test    eax, eax
0x14000f6fb  jns     short loc_14000F710
0x14000f6fd  mov     r8d, 7Bh ; '{'
0x14000f703  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x14000f70a  lea     ecx, [r8-7Ah]
0x14000f70e  jmp     short loc_14000F785
0x14000f710  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14000f714  mov     rax, r12
0x14000f717  cmovnz  rax, r14
0x14000f71b  mov     r14d, 1
0x14000f721  test    rax, rax
0x14000f724  jz      short loc_14000F7A2
0x14000f726  xorps   xmm0, xmm0
0x14000f729  movups  xmmword ptr [rdi+8], xmm0
0x14000f72d  movups  xmmword ptr [rdi+18h], xmm0
0x14000f731  movups  xmmword ptr [rdi+28h], xmm0
0x14000f735  mov     [rdi+8], rax
0x14000f739  xor     eax, eax
0x14000f73b  mov     [rsp+110h+FileInformationClass], 5; FileInformationClass
0x14000f743  xorps   xmm0, xmm0
0x14000f746  mov     [rbp+4Fh+var_38], rax
0x14000f74a  xorps   xmm1, xmm1
0x14000f74d  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x14000f751  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x14000f755  lea     r9d, [rax+18h]; Length
0x14000f759  movups  [rbp+4Fh+FileInformation], xmm1
0x14000f75d  mov     rcx, [rdi+8]; FileHandle
0x14000f761  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x14000f765  call    cs:__imp_ZwQueryInformationFile
0x14000f76b  mov     ebx, eax
0x14000f76d  test    eax, eax
0x14000f76f  jns     loc_14000F918
0x14000f775  lea     r9, aNtqueryinforma_0; "NtQueryInformationFile failed [%x]"
0x14000f77c  mov     r8d, 0B7h
0x14000f782  mov     ecx, r14d
0x14000f785  lea     rdx, aAslfilemapping_0; "AslFileMappingCreate"
0x14000f78c  mov     [rsp+110h+FileInformationClass], eax
0x14000f790  call    AslLogCallPrintf
0x14000f795  mov     rcx, rdi; P
0x14000f798  call    AslFileMappingDelete
0x14000f79d  jmp     loc_14000F937
0x14000f7a2  mov     r8d, 0Ch; MaxCount
0x14000f7a8  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x14000f7af  mov     rcx, rsi; String1
0x14000f7b2  call    cs:__imp__wcsnicmp
0x14000f7b8  test    eax, eax
0x14000f7ba  jz      short loc_14000F7FC
0x14000f7bc  xor     r9d, r9d
0x14000f7bf  lea     rdx, [rbp+4Fh+DestinationString]
0x14000f7c3  xor     r8d, r8d
0x14000f7c6  mov     rcx, rsi
0x14000f7c9  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x14000f7cf  mov     ebx, eax
0x14000f7d1  test    eax, eax
0x14000f7d3  jns     short loc_14000F7FC
0x14000f7d5  mov     dword ptr [rsp+110h+FileAttributes], eax
0x14000f7d9  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x14000f7e0  mov     r8d, 94h
0x14000f7e6  mov     ecx, r14d
0x14000f7e9  lea     rdx, aAslfilemapping_0; "AslFileMappingCreate"
0x14000f7f0  mov     qword ptr [rsp+110h+FileInformationClass], rsi
0x14000f7f5  call    AslLogCallPrintf
0x14000f7fa  jmp     short loc_14000F795
0x14000f7fc  mov     [rsp+110h+EaLength], r12d; EaLength
0x14000f801  lea     rax, [rbp+4Fh+DestinationString]
0x14000f805  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x14000f80a  lea     r9, [rbp+4Fh+var_58]; IoStatusBlock
0x14000f80e  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x14000f816  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14000f81a  mov     [rsp+110h+CreateDisposition], r14d; CreateDisposition
0x14000f81f  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x14000f823  xorps   xmm0, xmm0
0x14000f826  mov     [rsp+110h+ShareAccess], 5; ShareAccess
0x14000f82e  mov     dword ptr [rsp+110h+FileAttributes], 80h; FileAttributes
0x14000f836  mov     edx, 80100080h; DesiredAccess
0x14000f83b  mov     qword ptr [rsp+110h+FileInformationClass], r12; AllocationSize
0x14000f840  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14000f848  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x14000f850  movups  xmmword ptr [rbp+4Fh+var_58], xmm0
0x14000f854  mov     [rbp+4Fh+FileHandle], r12
0x14000f858  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x14000f85c  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x14000f860  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14000f865  call    cs:__imp_ZwCreateFile
0x14000f86b  mov     ebx, eax
0x14000f86d  test    eax, eax
0x14000f86f  js      short loc_14000F889
0x14000f871  mov     rax, [rbp+4Fh+FileHandle]
0x14000f875  mov     rcx, r12
0x14000f878  mov     [rdi+8], rax
0x14000f87c  mov     ebx, r12d
0x14000f87f  mov     [rbp+4Fh+FileHandle], rcx
0x14000f883  mov     [rdi+30h], r14b
0x14000f887  jmp     short loc_14000F88D
0x14000f889  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x14000f88d  test    rcx, rcx
0x14000f890  jz      short loc_14000F898
0x14000f892  call    cs:__imp_ZwClose
0x14000f898  test    ebx, ebx
0x14000f89a  jns     loc_14000F739
0x14000f8a0  cmp     ebx, 0C000003Ah
0x14000f8a6  jz      loc_14000F795
0x14000f8ac  cmp     ebx, 0C0000034h
0x14000f8b2  jz      loc_14000F795
0x14000f8b8  cmp     ebx, 0C00000CCh
0x14000f8be  jz      loc_14000F795
0x14000f8c4  lea     eax, [rbx+3FFFFFEDh]
0x14000f8ca  cmp     eax, 30h ; '0'
0x14000f8cd  ja      short loc_14000F8DF
0x14000f8cf  mov     rcx, 1000000008001h
0x14000f8d9  bt      rcx, rax
0x14000f8dd  jb      short loc_14000F8FD
0x14000f8df  cmp     ebx, 0C00000BAh
0x14000f8e5  jz      short loc_14000F8FD
0x14000f8e7  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x14000f8eb  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x14000f8f2  mov     r8d, 0A1h
0x14000f8f8  jmp     loc_14000F7E6
0x14000f8fd  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x14000f901  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x14000f908  mov     r8d, 0A3h
0x14000f90e  mov     ecx, 3
0x14000f913  jmp     loc_14000F7E9
0x14000f918  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x14000f91c  mov     ebx, r12d
0x14000f91f  mov     [rdi+18h], rax
0x14000f923  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x14000f927  neg     rax
0x14000f92a  sbb     ecx, ecx
0x14000f92c  neg     ecx
0x14000f92e  add     ecx, r14d
0x14000f931  mov     [rdi+38h], ecx
0x14000f934  mov     [r15], rdi
0x14000f937  cmp     [rbp+4Fh+DestinationString.Buffer], rsi
0x14000f93b  jz      short loc_14000F947
0x14000f93d  lea     rcx, [rbp+4Fh+DestinationString]; UnicodeString
0x14000f941  call    cs:__imp_RtlFreeUnicodeString
0x14000f947  mov     eax, ebx
0x14000f949  jmp     short loc_14000F950
0x14000f94b  mov     eax, 0C000000Dh
0x14000f950  mov     rcx, [rbp+4Fh+var_30]
0x14000f954  xor     rcx, rsp; StackCookie
0x14000f957  call    __security_check_cookie
0x14000f95c  lea     r11, [rsp+110h+var_20]
0x14000f964  mov     rbx, [r11+40h]
0x14000f968  mov     rsi, [r11+48h]
0x14000f96c  mov     rsp, r11
0x14000f96f  pop     r15
0x14000f971  pop     r14
0x14000f973  pop     r12
0x14000f975  pop     rdi
0x14000f976  pop     rbp
0x14000f977  retn
```
