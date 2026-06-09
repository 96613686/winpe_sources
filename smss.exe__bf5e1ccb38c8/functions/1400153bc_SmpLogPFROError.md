# SmpLogPFROError

- ea: `0x1400153bc`
- end: `0x140015657`
- name: `SmpLogPFROError`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140015ae8`

## callees

- `0x14000ad0c`
- `0x14000d4c0`
- `0x14000eaec`
- `0x1400153bc`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x1400154de`
- `ntdll!NtClose` at `0x14001551f`
- `ntdll!NtClose` at `0x1400154de`
- `ntdll!NtClose` at `0x14001551f`
- `ntdll!NtSetInformationFile` at `0x14001550c`
- `ntdll!NtSetInformationFile` at `0x14001550c`
- `ntdll!NtQueryInformationFile` at `0x1400154cb`
- `ntdll!NtQueryInformationFile` at `0x1400154cb`
- `ntdll!NtCreateFile` at `0x140015482`
- `ntdll!NtCreateFile` at `0x140015482`
- `ntdll!NtWriteFile` at `0x14001560e`
- `ntdll!NtWriteFile` at `0x14001560e`

## pseudocode

```c
bool __fastcall SmpLogPFROError(__int64 a1, const wchar_t *a2, int a3)
{
  ULONG v6; // ebx
  NTSTATUS v7; // eax
  __int64 v8; // r8
  __int64 v9; // rdx
  NTSTATUS v11; // edi
  NTSTATUS v12; // edi
  const wchar_t *v13; // r11
  NTSTATUS v14; // eax
  wchar_t *v15; // rax
  NTSTATUS v16; // eax
  NTSTATUS v17; // ebx
  __int64 ShareAccess; // [rsp+30h] [rbp-D0h]
  ULONG CreateDisposition[2]; // [rsp+38h] [rbp-C8h]
  ULONG CreateOptions[2]; // [rsp+40h] [rbp-C0h]
  PVOID EaBuffer; // [rsp+48h] [rbp-B8h]
  __int64 EaLength; // [rsp+50h] [rbp-B0h]
  __int64 v23; // [rsp+80h] [rbp-80h] BYREF
  size_t pcbRemaining; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  struct _TIME_FIELDS TimeFields; // [rsp+D0h] [rbp-30h] BYREF
  __int128 FileInformation; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v29; // [rsp+F0h] [rbp-10h]
  wchar_t pszDest[256]; // [rsp+100h] [rbp+0h] BYREF

  pcbRemaining = 0;
  v6 = 48;
  IoStatusBlock = 0;
  TimeFields = 0;
  if ( !SmpLogFileHandle )
  {
    v29 = 0;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    v23 = 0;
    FileInformation = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)L"(*";
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = NtCreateFile(&SmpLogFileHandle, 0x120002u, &ObjectAttributes, &IoStatusBlock, 0, 0, 0, 3u, 0x64u, 0, 0);
    if ( v7 < 0 )
    {
      v8 = (unsigned int)v7;
      v9 = 12126;
LABEL_4:
      SmpLogFileHandle = 0;
      SmpLogFailure("SmpLogPFROError", v9, v8);
      return 0;
    }
    v11 = NtQueryInformationFile(SmpLogFileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    if ( v11 < 0 )
    {
      NtClose(SmpLogFileHandle);
      v8 = (unsigned int)v11;
      v9 = 12143;
      goto LABEL_4;
    }
    v23 = *((_QWORD *)&FileInformation + 1);
    v12 = NtSetInformationFile(SmpLogFileHandle, &IoStatusBlock, &v23, 8u, FilePositionInformation);
    if ( v12 < 0 )
    {
      NtClose(SmpLogFileHandle);
      v8 = (unsigned int)v12;
      v9 = 12161;
      goto LABEL_4;
    }
  }
  SmpGetTime(&TimeFields);
  v13 = L"$&";
  if ( *a2 )
    v13 = a2;
  LODWORD(EaLength) = TimeFields.Minute;
  LODWORD(EaBuffer) = TimeFields.Hour;
  CreateOptions[0] = TimeFields.Year;
  CreateDisposition[0] = TimeFields.Day;
  LODWORD(ShareAccess) = TimeFields.Month;
  v14 = RtlStringCbPrintfExW(
          pszDest,
          0x200u,
          0,
          &pcbRemaining,
          0,
          L"%d/%d/%d %d:%d:%d - PFRO Error: %wZ, %wZ, 0x%x\r\n",
          ShareAccess,
          *(_QWORD *)CreateDisposition,
          *(_QWORD *)CreateOptions,
          EaBuffer,
          EaLength,
          TimeFields.Second,
          a1,
          v13,
          a3);
  if ( v14 >= 0 )
  {
    v15 = pszDest;
    v6 = 512 - pcbRemaining;
  }
  else
  {
    SmpLogFailure("SmpLogPFROError", 12193, (unsigned int)v14);
    v15 = L"Error logging PFRO error";
  }
  v16 = NtWriteFile(SmpLogFileHandle, 0, 0, 0, &IoStatusBlock, v15, v6, 0, 0);
  v17 = v16;
  if ( v16 < 0 )
    SmpLogFailure("SmpLogPFROError", 12216, (unsigned int)v16);
  return v17 >= 0;
}

```

## disassembly

```asm
0x1400153bc  push    rbp
0x1400153be  push    rbx
0x1400153bf  push    rsi
0x1400153c0  push    rdi
0x1400153c1  push    r12
0x1400153c3  push    r14
0x1400153c5  push    r15
0x1400153c7  lea     rbp, [rsp-210h]
0x1400153cf  sub     rsp, 310h
0x1400153d6  mov     rax, cs:__security_cookie
0x1400153dd  xor     rax, rsp
0x1400153e0  mov     [rbp+240h+var_40], rax
0x1400153e7  xor     r12d, r12d
0x1400153ea  xorps   xmm0, xmm0
0x1400153ed  cmp     cs:SmpLogFileHandle, r12
0x1400153f4  xorps   xmm1, xmm1
0x1400153f7  mov     r15d, r8d
0x1400153fa  mov     [rbp+240h+pcbRemaining], r12
0x1400153fe  mov     rsi, rdx
0x140015401  mov     r14, rcx
0x140015404  lea     ebx, [r12+30h]
0x140015409  movups  xmmword ptr [rbp+240h+IoStatusBlock], xmm0
0x14001540d  movups  xmmword ptr [rbp+240h+TimeFields.Year], xmm1
0x140015411  jnz     loc_140015532
0x140015417  mov     dword ptr [rsp+340h+EaLength], r12d; EaLength
0x14001541c  lea     r9, [rbp+240h+IoStatusBlock]; IoStatusBlock
0x140015420  mov     [rsp+340h+EaBuffer], r12; EaBuffer
0x140015425  lea     r8, [rbp+240h+ObjectAttributes]; ObjectAttributes
0x140015429  mov     [rsp+340h+CreateOptions], 64h ; 'd'; CreateOptions
0x140015431  lea     rcx, SmpLogFileHandle; FileHandle
0x140015438  xor     eax, eax
0x14001543a  mov     [rsp+340h+CreateDisposition], 3; CreateDisposition
0x140015442  mov     [rbp+240h+var_250], rax
0x140015446  mov     edx, 120002h; DesiredAccess
0x14001544b  mov     dword ptr [rsp+340h+ShareAccess], r12d; ShareAccess
0x140015450  lea     rax, SmpLogfileName; "(*"
0x140015457  mov     [rsp+340h+FileAttributes], r12d; FileAttributes
0x14001545c  mov     [rsp+340h+AllocationSize], r12; AllocationSize
0x140015461  mov     qword ptr [rbp+240h+ObjectAttributes.Length], rbx
0x140015465  mov     qword ptr [rbp+240h+ObjectAttributes.Attributes], 40h ; '@'
0x14001546d  mov     [rbp+240h+var_2C0], r12
0x140015471  movups  [rbp+240h+FileInformation], xmm0
0x140015475  mov     [rbp+240h+ObjectAttributes.RootDirectory], r12
0x140015479  mov     [rbp+240h+ObjectAttributes.ObjectName], rax
0x14001547d  movdqu  xmmword ptr [rbp+240h+ObjectAttributes.SecurityDescriptor], xmm0
0x140015482  call    cs:__imp_NtCreateFile
0x140015488  test    eax, eax
0x14001548a  jns     short loc_1400154AE
0x14001548c  mov     r8d, eax
0x14001548f  mov     edx, 2F5Eh
0x140015494  lea     rcx, aSmplogpfroerro; "SmpLogPFROError"
0x14001549b  mov     cs:SmpLogFileHandle, r12
0x1400154a2  call    SmpLogFailure
0x1400154a7  xor     al, al
0x1400154a9  jmp     loc_140015636
0x1400154ae  mov     rcx, cs:SmpLogFileHandle; FileHandle
0x1400154b5  lea     r8, [rbp+240h+FileInformation]; FileInformation
0x1400154b9  mov     r9d, 18h; Length
0x1400154bf  mov     dword ptr [rsp+340h+AllocationSize], 5; FileInformationClass
0x1400154c7  lea     rdx, [rbp+240h+IoStatusBlock]; IoStatusBlock
0x1400154cb  call    cs:__imp_NtQueryInformationFile
0x1400154d1  mov     rcx, cs:SmpLogFileHandle; FileHandle
0x1400154d8  mov     edi, eax
0x1400154da  test    eax, eax
0x1400154dc  jns     short loc_1400154EE
0x1400154de  call    cs:__imp_NtClose
0x1400154e4  mov     r8d, edi
0x1400154e7  mov     edx, 2F6Fh
0x1400154ec  jmp     short loc_140015494
0x1400154ee  mov     rax, qword ptr [rbp+240h+FileInformation+8]
0x1400154f2  lea     r8, [rbp+240h+var_2C0]; FileInformation
0x1400154f6  mov     r9d, 8; Length
0x1400154fc  mov     [rbp+240h+var_2C0], rax
0x140015500  lea     rdx, [rbp+240h+IoStatusBlock]; IoStatusBlock
0x140015504  mov     dword ptr [rsp+340h+AllocationSize], 0Eh; FileInformationClass
0x14001550c  call    cs:__imp_NtSetInformationFile
0x140015512  mov     edi, eax
0x140015514  test    eax, eax
0x140015516  jns     short loc_140015532
0x140015518  mov     rcx, cs:SmpLogFileHandle; Handle
0x14001551f  call    cs:__imp_NtClose
0x140015525  mov     r8d, edi
0x140015528  mov     edx, 2F81h
0x14001552d  jmp     loc_140015494
0x140015532  lea     rcx, [rbp+240h+TimeFields]; TimeFields
0x140015536  call    SmpGetTime
0x14001553b  movsx   eax, [rbp+240h+TimeFields.Second]
0x14001553f  lea     r11, SmpDeletedFile; "$&"
0x140015546  movsx   ecx, [rbp+240h+TimeFields.Minute]
0x14001554a  mov     edi, 200h
0x14001554f  movsx   edx, [rbp+240h+TimeFields.Hour]
0x140015553  movsx   r8d, [rbp+240h+TimeFields.Year]
0x140015558  movsx   r9d, [rbp+240h+TimeFields.Day]
0x14001555d  cmp     [rsi], r12w
0x140015561  movsx   r10d, [rbp+240h+TimeFields.Month]
0x140015566  mov     [rsp+340h+var_2D0], r15d
0x14001556b  cmovnz  r11, rsi
0x14001556f  mov     [rsp+340h+var_2D8], r11
0x140015574  mov     [rsp+340h+var_2E0], r14
0x140015579  mov     [rsp+340h+var_2E8], eax
0x14001557d  lea     rax, aDDDDDDPfroErro; "%d/%d/%d %d:%d:%d - PFRO Error: %wZ, %w"...
0x140015584  mov     dword ptr [rsp+340h+EaLength], ecx
0x140015588  lea     rcx, [rbp+240h+pszDest]; pszDest
0x14001558c  mov     dword ptr [rsp+340h+EaBuffer], edx
0x140015590  mov     edx, edi; cbDest
0x140015592  mov     [rsp+340h+CreateOptions], r8d
0x140015597  xor     r8d, r8d; ppszDestEnd
0x14001559a  mov     [rsp+340h+CreateDisposition], r9d
0x14001559f  lea     r9, [rbp+240h+pcbRemaining]; pcbRemaining
0x1400155a3  mov     dword ptr [rsp+340h+ShareAccess], r10d
0x1400155a8  mov     qword ptr [rsp+340h+FileAttributes], rax; pszFormat
0x1400155ad  mov     [rsp+340h+AllocationSize], r12; dwFlags
0x1400155b2  call    RtlStringCbPrintfExW
0x1400155b7  test    eax, eax
0x1400155b9  jns     short loc_1400155D8
0x1400155bb  mov     r8d, eax
0x1400155be  lea     rcx, aSmplogpfroerro; "SmpLogPFROError"
0x1400155c5  mov     edx, 2FA1h
0x1400155ca  call    SmpLogFailure
0x1400155cf  lea     rax, aErrorLoggingPf; "Error logging PFRO error"
0x1400155d6  jmp     short loc_1400155E3
0x1400155d8  mov     rbx, rdi
0x1400155db  lea     rax, [rbp+240h+pszDest]
0x1400155df  sub     rbx, [rbp+240h+pcbRemaining]
0x1400155e3  mov     rcx, cs:SmpLogFileHandle; FileHandle
0x1400155ea  xor     r9d, r9d; ApcContext
0x1400155ed  mov     qword ptr [rsp+340h+CreateOptions], r12; Key
0x1400155f2  xor     r8d, r8d; ApcRoutine
0x1400155f5  mov     qword ptr [rsp+340h+CreateDisposition], r12; ByteOffset
0x1400155fa  xor     edx, edx; Event
0x1400155fc  mov     dword ptr [rsp+340h+ShareAccess], ebx; Length
0x140015600  mov     qword ptr [rsp+340h+FileAttributes], rax; Buffer
0x140015605  lea     rax, [rbp+240h+IoStatusBlock]
0x140015609  mov     [rsp+340h+AllocationSize], rax; IoStatusBlock
0x14001560e  call    cs:__imp_NtWriteFile
0x140015614  mov     ebx, eax
0x140015616  test    eax, eax
0x140015618  jns     short loc_14001562E
0x14001561a  mov     r8d, eax
0x14001561d  lea     rcx, aSmplogpfroerro; "SmpLogPFROError"
0x140015624  mov     edx, 2FB8h
0x140015629  call    SmpLogFailure
0x14001562e  shr     ebx, 1Fh
0x140015631  xor     bl, 1
0x140015634  mov     al, bl
0x140015636  mov     rcx, [rbp+240h+var_40]
0x14001563d  xor     rcx, rsp; StackCookie
0x140015640  call    __security_check_cookie
0x140015645  add     rsp, 310h
0x14001564c  pop     r15
0x14001564e  pop     r14
0x140015650  pop     r12
0x140015652  pop     rdi
0x140015653  pop     rsi
0x140015654  pop     rbx
0x140015655  pop     rbp
0x140015656  retn
```
