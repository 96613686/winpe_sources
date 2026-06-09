# WdsEnumVolumeReparsePointsByHandle

- ea: `0x180016340`
- end: `0x18001658d`
- name: `WdsEnumVolumeReparsePointsByHandle`
- size: `589`
- prototype: `__int64 __fastcall(char *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800108d0`

## callees

- `0x180010b08`
- `0x180016340`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800163fe`
- `ntdll!RtlInitUnicodeString` at `0x1800163fe`
- `ntdll!NtClose` at `0x18001654e`
- `ntdll!NtClose` at `0x18001654e`
- `ntdll!NtOpenFile` at `0x180016448`
- `ntdll!NtOpenFile` at `0x180016448`
- `ntdll!NtQueryDirectoryFile` at `0x1800164ed`
- `ntdll!NtQueryDirectoryFile` at `0x1800164ed`

## string_xrefs

- `0x1800163f3`: `$Extend\$Reparse:$R:$INDEX_ALLOCATION`

## pseudocode

```c
__int64 __fastcall WdsEnumVolumeReparsePointsByHandle(char *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v7; // rdx
  unsigned int v8; // ecx
  __int64 v9; // rdi
  int Status; // ebx
  int v11; // esi
  __int64 v12; // r12
  struct _UNICODE_STRING *FileName; // r14
  BOOLEAN RestartScan; // r15
  NTSTATUS v15; // eax
  void *FileHandle; // [rsp+60h] [rbp-81h] BYREF
  struct _UNICODE_STRING v18; // [rsp+68h] [rbp-79h] BYREF
  __int64 v19; // [rsp+78h] [rbp-69h]
  void *v20; // [rsp+80h] [rbp-61h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-19h] BYREF
  __int64 v24; // [rsp+D8h] [rbp-9h] BYREF
  int v25; // [rsp+E0h] [rbp-1h]
  __int128 FileInformation; // [rsp+E8h] [rbp+7h] BYREF

  v19 = a5;
  v20 = a1;
  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v7 = 0;
    while ( 1 )
    {
      v8 = *(_DWORD *)(a2 + 4 * v7);
      if ( (v8 & 0xFFF0000) != 0 || v8 <= 2 || (v8 & 0xC0000000) == 0x40000000 || (v8 & 0x30000000) == 0x30000000 )
        break;
      v7 = (unsigned int)(v7 + 1);
      if ( (unsigned int)v7 >= 2 )
      {
        RtlInitUnicodeString(&DestinationString, L"$Extend\\$Reparse:$R:$INDEX_ALLOCATION");
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = a1;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v9 = 0;
        Status = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 3u, 0x10u);
        if ( Status >= 0 )
        {
          while ( (unsigned int)v9 < 2 )
          {
            v11 = *(_DWORD *)(a2 + 4 * v9);
            v12 = 0;
            v24 = 0;
            v25 = 0;
            v18 = 0;
            if ( v11 )
            {
              LODWORD(v24) = v11;
              v18.Buffer = (PWSTR)&v24;
              FileName = &v18;
              *(_DWORD *)&v18.Length = 262148;
              RestartScan = 1;
            }
            else
            {
              FileName = 0;
              RestartScan = 0;
            }
            if ( Status < 0 )
              break;
            while ( 1 )
            {
              FileInformation = 0;
              v15 = NtQueryDirectoryFile(
                      FileHandle,
                      0,
                      0,
                      0,
                      &IoStatusBlock,
                      &FileInformation,
                      0x10u,
                      FileReparsePointInformation,
                      1u,
                      FileName,
                      RestartScan);
              Status = v15;
              if ( v15 == -2147483642 || v15 == -1073741809 )
                break;
              if ( v15 < 0 )
                goto LABEL_23;
              Status = IoStatusBlock.Status;
              if ( IoStatusBlock.Status < 0 )
                goto LABEL_23;
              if ( v11 )
              {
                if ( DWORD2(FileInformation) != v11 || (_QWORD)FileInformation == v12 )
                  goto LABEL_27;
                v12 = FileInformation;
              }
              RestartScan = 0;
              FileName = 0;
              Status = SclpLinkProcessReparsePoint(v20, FileInformation, SDWORD2(FileInformation), v19);
              if ( Status < 0 )
                goto LABEL_23;
            }
            Status = 0;
LABEL_27:
            v9 = (unsigned int)(v9 + 1);
          }
        }
LABEL_23:
        if ( FileHandle )
          NtClose(FileHandle);
        return (unsigned int)Status;
      }
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x180016340  mov     [rsp-8+arg_10], rbx
0x180016345  push    rbp
0x180016346  push    rsi
0x180016347  push    rdi
0x180016348  push    r12
0x18001634a  push    r13
0x18001634c  push    r14
0x18001634e  push    r15
0x180016350  lea     rbp, [rsp-1Fh]
0x180016355  sub     rsp, 100h
0x18001635c  mov     rax, cs:__security_cookie
0x180016363  xor     rax, rsp
0x180016366  mov     [rbp+4Fh+var_38], rax
0x18001636a  mov     rax, [rbp+4Fh+arg_20]
0x18001636e  xorps   xmm0, xmm0
0x180016371  mov     [rbp+4Fh+var_B8], rax
0x180016375  mov     r13, rdx
0x180016378  xor     eax, eax
0x18001637a  mov     [rbp+4Fh+var_B0], rcx
0x18001637e  lea     rax, [rcx-1]
0x180016382  mov     [rsp+130h+FileHandle], 0
0x18001638b  mov     rbx, rcx
0x18001638e  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x180016392  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x180016396  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18001639a  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x18001639e  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x1800163a2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800163a6  ja      loc_180016561
0x1800163ac  xor     edx, edx
0x1800163ae  mov     r8d, 30000000h
0x1800163b4  mov     ecx, [r13+rdx*4+0]
0x1800163b9  test    ecx, 0FFF0000h
0x1800163bf  jnz     loc_180016561
0x1800163c5  cmp     ecx, 2
0x1800163c8  jbe     loc_180016561
0x1800163ce  mov     eax, ecx
0x1800163d0  and     eax, 0C0000000h
0x1800163d5  cmp     eax, 40000000h
0x1800163da  jz      loc_180016561
0x1800163e0  and     ecx, r8d
0x1800163e3  cmp     ecx, r8d
0x1800163e6  jz      loc_180016561
0x1800163ec  inc     edx
0x1800163ee  cmp     edx, 2
0x1800163f1  jb      short loc_1800163B4
0x1800163f3  lea     rdx, aExtendReparseR; "$Extend\\$Reparse:$R:$INDEX_ALLOCATION"
0x1800163fa  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800163fe  call    cs:__imp_RtlInitUnicodeString
0x180016404  lea     rax, [rbp+4Fh+DestinationString]
0x180016408  mov     [rsp+130h+OpenOptions], 10h; OpenOptions
0x180016410  xorps   xmm0, xmm0
0x180016413  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x180016417  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x18001641b  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180016422  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180016426  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rbx
0x18001642a  mov     edx, 100001h; DesiredAccess
0x18001642f  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x180016436  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x18001643b  mov     [rsp+130h+ShareAccess], 3; ShareAccess
0x180016443  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180016448  call    cs:__imp_NtOpenFile
0x18001644e  xor     edi, edi
0x180016450  mov     ebx, eax
0x180016452  test    eax, eax
0x180016454  js      loc_180016544
0x18001645a  cmp     edi, 2
0x18001645d  jnb     loc_180016544
0x180016463  mov     esi, [r13+rdi*4+0]
0x180016468  xor     eax, eax
0x18001646a  xor     r12d, r12d
0x18001646d  mov     [rbp+4Fh+var_58], rax
0x180016471  mov     [rbp+4Fh+var_50], eax
0x180016474  xorps   xmm0, xmm0
0x180016477  movups  xmmword ptr [rbp+4Fh+var_C8.Length], xmm0
0x18001647b  test    esi, esi
0x18001647d  jz      short loc_18001649A
0x18001647f  lea     rax, [rbp+4Fh+var_58]
0x180016483  mov     dword ptr [rbp+4Fh+var_58], esi
0x180016486  mov     [rbp+4Fh+var_C8.Buffer], rax
0x18001648a  lea     r14, [rbp+4Fh+var_C8]
0x18001648e  mov     dword ptr [rbp+4Fh+var_C8.Length], 40004h
0x180016495  mov     r15b, 1
0x180016498  jmp     short loc_1800164A0
0x18001649a  xor     r14d, r14d
0x18001649d  xor     r15b, r15b
0x1800164a0  test    ebx, ebx
0x1800164a2  js      loc_180016544
0x1800164a8  mov     rcx, [rsp+130h+FileHandle]; FileHandle
0x1800164ad  lea     rax, [rbp+4Fh+FileInformation]
0x1800164b1  mov     [rsp+130h+RestartScan], r15b; RestartScan
0x1800164b6  xorps   xmm0, xmm0
0x1800164b9  mov     [rsp+130h+FileName], r14; FileName
0x1800164be  xor     r9d, r9d; ApcContext
0x1800164c1  mov     [rsp+130h+ReturnSingleEntry], 1; ReturnSingleEntry
0x1800164c6  xor     r8d, r8d; ApcRoutine
0x1800164c9  mov     [rsp+130h+FileInformationClass], 21h ; '!'; FileInformationClass
0x1800164d1  xor     edx, edx; Event
0x1800164d3  mov     [rsp+130h+Length], 10h; Length
0x1800164db  mov     qword ptr [rsp+130h+OpenOptions], rax; FileInformation
0x1800164e0  lea     rax, [rbp+4Fh+IoStatusBlock]
0x1800164e4  mov     qword ptr [rsp+130h+ShareAccess], rax; IoStatusBlock
0x1800164e9  movups  [rbp+4Fh+FileInformation], xmm0
0x1800164ed  call    cs:__imp_NtQueryDirectoryFile
0x1800164f3  mov     ebx, eax
0x1800164f5  cmp     eax, 80000006h
0x1800164fa  jz      short loc_180016558
0x1800164fc  cmp     eax, 0C000000Fh
0x180016501  jz      short loc_180016558
0x180016503  test    eax, eax
0x180016505  js      short loc_180016544
0x180016507  mov     ebx, dword ptr [rbp+4Fh+IoStatusBlock]
0x18001650a  test    ebx, ebx
0x18001650c  js      short loc_180016544
0x18001650e  mov     r8d, dword ptr [rbp+4Fh+FileInformation+8]
0x180016512  mov     rdx, qword ptr [rbp+4Fh+FileInformation]
0x180016516  test    esi, esi
0x180016518  jz      short loc_180016527
0x18001651a  cmp     r8d, esi
0x18001651d  jnz     short loc_18001655A
0x18001651f  cmp     rdx, r12
0x180016522  jz      short loc_18001655A
0x180016524  mov     r12, rdx
0x180016527  mov     r9, [rbp+4Fh+var_B8]
0x18001652b  xor     r15b, r15b
0x18001652e  mov     rcx, [rbp+4Fh+var_B0]
0x180016532  xor     r14d, r14d
0x180016535  call    SclpLinkProcessReparsePoint
0x18001653a  mov     ebx, eax
0x18001653c  test    eax, eax
0x18001653e  jns     loc_1800164A8
0x180016544  mov     rcx, [rsp+130h+FileHandle]; Handle
0x180016549  test    rcx, rcx
0x18001654c  jz      short loc_180016554
0x18001654e  call    cs:__imp_NtClose
0x180016554  mov     eax, ebx
0x180016556  jmp     short loc_180016566
0x180016558  xor     ebx, ebx
0x18001655a  inc     edi
0x18001655c  jmp     loc_18001645A
0x180016561  mov     eax, 0C000000Dh
0x180016566  mov     rcx, [rbp+4Fh+var_38]
0x18001656a  xor     rcx, rsp; StackCookie
0x18001656d  call    __security_check_cookie
0x180016572  mov     rbx, [rsp+130h+arg_10]
0x18001657a  add     rsp, 100h
0x180016581  pop     r15
0x180016583  pop     r14
0x180016585  pop     r13
0x180016587  pop     r12
0x180016589  pop     rdi
0x18001658a  pop     rsi
0x18001658b  pop     rbp
0x18001658c  retn
```
