# WerpCreateDumpFile

- ea: `0x14000dc94`
- end: `0x14000dfc8`
- name: `WerpCreateDumpFile`
- size: `820`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000cb50`

## callees

- `0x140001a24`
- `0x140002750`
- `0x14000dc94`
- `0x14000e260`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000dd44`
- `ntoskrnl!DbgPrintEx` at `0x14000dda9`
- `ntoskrnl!DbgPrintEx` at `0x14000ddc9`
- `ntoskrnl!DbgPrintEx` at `0x14000de33`
- `ntoskrnl!DbgPrintEx` at `0x14000df3a`
- `ntoskrnl!DbgPrintEx` at `0x14000df62`
- `ntoskrnl!DbgPrintEx` at `0x14000df85`
- `ntoskrnl!DbgPrintEx` at `0x14000dd44`
- `ntoskrnl!DbgPrintEx` at `0x14000dda9`
- `ntoskrnl!DbgPrintEx` at `0x14000ddc9`
- `ntoskrnl!DbgPrintEx` at `0x14000de33`
- `ntoskrnl!DbgPrintEx` at `0x14000df3a`
- `ntoskrnl!DbgPrintEx` at `0x14000df62`
- `ntoskrnl!DbgPrintEx` at `0x14000df85`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14000de73`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14000de73`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000de90`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000de90`
- `ntoskrnl!IoCreateFile` at `0x14000df14`
- `ntoskrnl!IoCreateFile` at `0x14000df14`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000de52`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000de52`

## string_xrefs

- `0x14000df78`: `WERKERNELHOST: WerpCreateDumpFile: Invalid parameter\n`
- `0x14000dd37`: `WERKERNELHOST: A dump file has already been opened. Filename %ws\n`
- `0x14000ddeb`: `WERKERNELHOST: Failed to create report directory, status 0x%X\n`
- `0x14000df30`: `WERKERNELHOST: Could not create file %ws, status 0x%X\n`
- `0x14000df51`: `WERKERNELHOST: WerpCreateDumpFile - created file handle %p, name %ws\n`

## pseudocode

```c
__int64 __fastcall WerpCreateDumpFile(__int64 a1, void **a2)
{
  const WCHAR *v4; // rdi
  NTSTATUS v5; // ebx
  int v6; // eax
  NTSTATUS v7; // eax
  const CHAR *v8; // r8
  int ReportDirectory; // eax
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-E0h]
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v18; // [rsp+D8h] [rbp-28h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD Owner[4]; // [rsp+F0h] [rbp-10h] BYREF

  Owner[0] = 257;
  Owner[1] = 83886080;
  FileHandle = 0;
  v18 = 0;
  Owner[2] = 18;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( a1 && a2 )
  {
    v4 = (const WCHAR *)(a1 + 136);
    *a2 = 0;
    if ( *(_WORD *)(a1 + 136) )
    {
      DbgPrintEx(5u, 1u, "WERKERNELHOST: A dump file has already been opened. Filename %ws\n", a1 + 136);
      return (unsigned int)-1073741561;
    }
    v6 = *(_DWORD *)(a1 + 4);
    if ( v6 == 1 )
    {
      v7 = RtlStringCchPrintfW(
             (NTSTRSAFE_PWSTR)(a1 + 136),
             0x104u,
             L"%wZ\\%ws\\%ws",
             &WerKernelLiveReportRootPath,
             a1 + 24,
             a1 + 56);
      v5 = v7;
      if ( v7 < 0 )
      {
        DbgPrintEx(5u, 1u, "WERKERNELHOST: RtlStringCbPrintfW failed for wszFileName, status 0x%X. \n", v7);
        v8 = "WERKERNELHOST: WerpSetDumpFileNameMini failed with status 0x%X.\n";
LABEL_8:
        *v4 = 0;
        DbgPrintEx(5u, 1u, v8, (unsigned int)v5);
        return (unsigned int)v5;
      }
      ReportDirectory = WerpCreateReportDirectory(a1);
      v5 = ReportDirectory;
      if ( ReportDirectory < 0 )
      {
        DbgPrintEx(
          5u,
          1u,
          "WERKERNELHOST: Failed to create report directory, status 0x%X\n",
          (unsigned int)ReportDirectory);
        return (unsigned int)v5;
      }
    }
    else if ( v6 == 2 )
    {
      v10 = RtlStringCchPrintfW((NTSTRSAFE_PWSTR)(a1 + 136), 0x104u, L"%wZ\\%ws", &WerKernelLiveReportRootPath, a1 + 56);
      v5 = v10;
      if ( v10 < 0 )
      {
        DbgPrintEx(5u, 1u, "WERKERNELHOST: RtlStringCbPrintfW failed for wszFileName, status 0x%X. \n", v10);
        v8 = "WERKERNELHOST: WerpSetDumpFileNameKernel failed with status 0x%X.\n";
        goto LABEL_8;
      }
    }
    v5 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
    if ( v5 >= 0 )
    {
      v5 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Owner, 0);
      if ( v5 >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, v4);
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
        ObjectAttributes.SecurityQualityOfService = 0;
        v11 = IoCreateFile(
                &FileHandle,
                0x120116u,
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                0x80u,
                0,
                2u,
                0x22u,
                0,
                0,
                CreateFileTypeNone,
                0,
                0x100u);
        v5 = v11;
        if ( v11 >= 0 )
        {
          DbgPrintEx(5u, 3u, "WERKERNELHOST: WerpCreateDumpFile - created file handle %p, name %ws\n", FileHandle, v4);
          *a2 = FileHandle;
        }
        else
        {
          LODWORD(AllocationSize) = v11;
          DbgPrintEx(5u, 1u, "WERKERNELHOST: Could not create file %ws, status 0x%X\n", v4, AllocationSize);
          *v4 = 0;
        }
      }
    }
  }
  else
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpCreateDumpFile: Invalid parameter\n");
    if ( a2 )
      *a2 = 0;
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000dc94  mov     [rsp-8+arg_10], rbx
0x14000dc99  push    rbp
0x14000dc9a  push    rsi
0x14000dc9b  push    rdi
0x14000dc9c  push    r12
0x14000dc9e  push    r13
0x14000dca0  push    r14
0x14000dca2  push    r15
0x14000dca4  lea     rbp, [rsp-10h]
0x14000dca9  sub     rsp, 110h
0x14000dcb0  mov     rax, cs:__security_cookie
0x14000dcb7  xor     rax, rsp
0x14000dcba  mov     [rbp+40h+var_40], rax
0x14000dcbe  xorps   xmm0, xmm0
0x14000dcc1  mov     [rbp+40h+Owner], 101h
0x14000dcc8  xor     r15d, r15d
0x14000dccb  mov     [rbp+40h+var_4C], 5000000h
0x14000dcd2  xor     eax, eax
0x14000dcd4  mov     [rsp+140h+FileHandle], r15
0x14000dcd9  mov     [rbp+40h+var_68], rax
0x14000dcdd  xorps   xmm1, xmm1
0x14000dce0  mov     [rbp+40h+var_48], 12h
0x14000dce7  mov     rsi, rdx
0x14000dcea  lea     r12d, [r15+1]
0x14000dcee  mov     r14, rcx
0x14000dcf1  lea     r13d, [r15+5]
0x14000dcf5  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x14000dcf9  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x14000dcfd  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm1
0x14000dd01  movups  xmmword ptr [rsp+140h+ObjectAttributes.Length], xmm0
0x14000dd06  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x14000dd0a  movups  [rbp+40h+SecurityDescriptor], xmm0
0x14000dd0e  movups  [rbp+40h+var_78], xmm0
0x14000dd12  test    rcx, rcx
0x14000dd15  jz      loc_14000DF78
0x14000dd1b  test    rdx, rdx
0x14000dd1e  jz      loc_14000DF78
0x14000dd24  lea     rdi, [rcx+88h]
0x14000dd2b  mov     [rdx], r15
0x14000dd2e  cmp     [rdi], r15w
0x14000dd32  jz      short loc_14000DD5A
0x14000dd34  mov     r9, rdi
0x14000dd37  lea     r8, aWerkernelhostA; "WERKERNELHOST: A dump file has already "...
0x14000dd3e  mov     edx, r12d; Level
0x14000dd41  mov     ecx, r13d; ComponentId
0x14000dd44  call    cs:__imp_DbgPrintEx
0x14000dd4b  nop     dword ptr [rax+rax+00h]
0x14000dd50  mov     ebx, 0C0000107h
0x14000dd55  jmp     loc_14000DF9E
0x14000dd5a  mov     eax, [rcx+4]
0x14000dd5d  cmp     eax, r12d
0x14000dd60  jnz     loc_14000DDF4
0x14000dd66  lea     rax, [rcx+38h]
0x14000dd6a  mov     edx, 104h; cchDest
0x14000dd6f  add     rcx, 18h
0x14000dd73  mov     qword ptr [rsp+140h+FileAttributes], rax
0x14000dd78  mov     [rsp+140h+AllocationSize], rcx
0x14000dd7d  lea     r9, WerKernelLiveReportRootPath
0x14000dd84  mov     rcx, rdi; pszDest
0x14000dd87  lea     r8, aWzWsWs; "%wZ\\%ws\\%ws"
0x14000dd8e  call    RtlStringCchPrintfW
0x14000dd93  mov     ebx, eax
0x14000dd95  test    eax, eax
0x14000dd97  jns     short loc_14000DDDA
0x14000dd99  mov     r9d, eax
0x14000dd9c  lea     r8, aWerkernelhostR_6; "WERKERNELHOST: RtlStringCbPrintfW faile"...
0x14000dda3  mov     edx, r12d; Level
0x14000dda6  mov     ecx, r13d; ComponentId
0x14000dda9  call    cs:__imp_DbgPrintEx
0x14000ddb0  nop     dword ptr [rax+rax+00h]
0x14000ddb5  lea     r8, aWerkernelhostW_54; "WERKERNELHOST: WerpSetDumpFileNameMini "...
0x14000ddbc  mov     r9d, ebx
0x14000ddbf  mov     [rdi], r15w
0x14000ddc3  mov     edx, r12d; Level
0x14000ddc6  mov     ecx, r13d; ComponentId
0x14000ddc9  call    cs:__imp_DbgPrintEx
0x14000ddd0  nop     dword ptr [rax+rax+00h]
0x14000ddd5  jmp     loc_14000DF9E
0x14000ddda  mov     rcx, r14
0x14000dddd  call    WerpCreateReportDirectory
0x14000dde2  mov     ebx, eax
0x14000dde4  test    eax, eax
0x14000dde6  jns     short loc_14000DE4B
0x14000dde8  mov     r9d, eax
0x14000ddeb  lea     r8, aWerkernelhostF_0; "WERKERNELHOST: Failed to create report "...
0x14000ddf2  jmp     short loc_14000DDC3
0x14000ddf4  cmp     eax, 2
0x14000ddf7  jnz     short loc_14000DE4B
0x14000ddf9  lea     rax, [rcx+38h]
0x14000ddfd  mov     edx, 104h; cchDest
0x14000de02  mov     rcx, rdi; pszDest
0x14000de05  mov     [rsp+140h+AllocationSize], rax
0x14000de0a  lea     r9, WerKernelLiveReportRootPath
0x14000de11  lea     r8, aWzWs; "%wZ\\%ws"
0x14000de18  call    RtlStringCchPrintfW
0x14000de1d  mov     ebx, eax
0x14000de1f  test    eax, eax
0x14000de21  jns     short loc_14000DE4B
0x14000de23  mov     r9d, eax
0x14000de26  lea     r8, aWerkernelhostR_6; "WERKERNELHOST: RtlStringCbPrintfW faile"...
0x14000de2d  mov     edx, r12d; Level
0x14000de30  mov     ecx, r13d; ComponentId
0x14000de33  call    cs:__imp_DbgPrintEx
0x14000de3a  nop     dword ptr [rax+rax+00h]
0x14000de3f  lea     r8, aWerkernelhostW_12; "WERKERNELHOST: WerpSetDumpFileNameKerne"...
0x14000de46  jmp     loc_14000DDBC
0x14000de4b  mov     edx, r12d; Revision
0x14000de4e  lea     rcx, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x14000de52  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000de59  nop     dword ptr [rax+rax+00h]
0x14000de5e  mov     ebx, eax
0x14000de60  test    eax, eax
0x14000de62  js      loc_14000DF9E
0x14000de68  xor     r8d, r8d; OwnerDefaulted
0x14000de6b  lea     rdx, [rbp+40h+Owner]; Owner
0x14000de6f  lea     rcx, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x14000de73  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14000de7a  nop     dword ptr [rax+rax+00h]
0x14000de7f  mov     ebx, eax
0x14000de81  test    eax, eax
0x14000de83  js      loc_14000DF9E
0x14000de89  mov     rdx, rdi; SourceString
0x14000de8c  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x14000de90  call    cs:__imp_RtlInitUnicodeString
0x14000de97  nop     dword ptr [rax+rax+00h]
0x14000de9c  mov     [rsp+140h+Options], 100h; Options
0x14000dea4  lea     rax, [rbp+40h+DestinationString]
0x14000dea8  mov     [rsp+140h+InternalParameters], r15; InternalParameters
0x14000dead  lea     r9, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x14000deb1  mov     [rsp+140h+CreateFileType], r15d; CreateFileType
0x14000deb6  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x14000debb  mov     [rsp+140h+EaLength], r15d; EaLength
0x14000dec0  lea     rcx, [rsp+140h+FileHandle]; FileHandle
0x14000dec5  mov     [rsp+140h+EaBuffer], r15; EaBuffer
0x14000deca  mov     edx, 120116h; DesiredAccess
0x14000decf  mov     [rsp+140h+CreateOptions], 22h ; '"'; CreateOptions
0x14000ded7  mov     [rsp+140h+Disposition], 2; Disposition
0x14000dedf  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x14000dee3  lea     rax, [rbp+40h+SecurityDescriptor]
0x14000dee7  mov     [rsp+140h+ShareAccess], r15d; ShareAccess
0x14000deec  mov     [rsp+140h+FileAttributes], 80h; FileAttributes
0x14000def4  mov     [rsp+140h+AllocationSize], r15; AllocationSize
0x14000def9  mov     [rsp+140h+ObjectAttributes.Length], 30h ; '0'
0x14000df01  mov     [rbp+40h+ObjectAttributes.RootDirectory], r15
0x14000df05  mov     [rbp+40h+ObjectAttributes.Attributes], 240h
0x14000df0c  mov     [rbp+40h+ObjectAttributes.SecurityDescriptor], rax
0x14000df10  mov     [rbp+40h+ObjectAttributes.SecurityQualityOfService], r15
0x14000df14  call    cs:__imp_IoCreateFile
0x14000df1b  nop     dword ptr [rax+rax+00h]
0x14000df20  mov     ebx, eax
0x14000df22  mov     ecx, r13d; ComponentId
0x14000df25  test    eax, eax
0x14000df27  jns     short loc_14000DF4C
0x14000df29  mov     r9, rdi
0x14000df2c  mov     dword ptr [rsp+140h+AllocationSize], eax
0x14000df30  lea     r8, aWerkernelhostC_3; "WERKERNELHOST: Could not create file %w"...
0x14000df37  mov     edx, r12d; Level
0x14000df3a  call    cs:__imp_DbgPrintEx
0x14000df41  nop     dword ptr [rax+rax+00h]
0x14000df46  mov     [rdi], r15w
0x14000df4a  jmp     short loc_14000DF9E
0x14000df4c  mov     r9, [rsp+140h+FileHandle]
0x14000df51  lea     r8, aWerkernelhostW; "WERKERNELHOST: WerpCreateDumpFile - cre"...
0x14000df58  mov     edx, 3; Level
0x14000df5d  mov     [rsp+140h+AllocationSize], rdi
0x14000df62  call    cs:__imp_DbgPrintEx
0x14000df69  nop     dword ptr [rax+rax+00h]
0x14000df6e  mov     rax, [rsp+140h+FileHandle]
0x14000df73  mov     [rsi], rax
0x14000df76  jmp     short loc_14000DF9E
0x14000df78  lea     r8, aWerkernelhostW_5; "WERKERNELHOST: WerpCreateDumpFile: Inva"...
0x14000df7f  mov     edx, r12d; Level
0x14000df82  mov     ecx, r13d; ComponentId
0x14000df85  call    cs:__imp_DbgPrintEx
0x14000df8c  nop     dword ptr [rax+rax+00h]
0x14000df91  test    rsi, rsi
0x14000df94  jz      short loc_14000DF99
0x14000df96  mov     [rsi], r15
0x14000df99  mov     ebx, 0C000000Dh
0x14000df9e  mov     eax, ebx
0x14000dfa0  mov     rcx, [rbp+40h+var_40]
0x14000dfa4  xor     rcx, rsp; StackCookie
0x14000dfa7  call    __security_check_cookie
0x14000dfac  mov     rbx, [rsp+140h+arg_10]
0x14000dfb4  add     rsp, 110h
0x14000dfbb  pop     r15
0x14000dfbd  pop     r14
0x14000dfbf  pop     r13
0x14000dfc1  pop     r12
0x14000dfc3  pop     rdi
0x14000dfc4  pop     rsi
0x14000dfc5  pop     rbp
0x14000dfc6  retn
```
