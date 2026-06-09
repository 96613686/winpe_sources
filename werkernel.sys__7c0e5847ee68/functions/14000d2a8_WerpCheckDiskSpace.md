# WerpCheckDiskSpace

- ea: `0x14000d2a8`
- end: `0x14000d42f`
- name: `WerpCheckDiskSpace`
- size: `391`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000f1f8`

## callees

- `0x140002750`
- `0x14000d2a8`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000d34e`
- `ntoskrnl!DbgPrintEx` at `0x14000d3ea`
- `ntoskrnl!DbgPrintEx` at `0x14000d34e`
- `ntoskrnl!DbgPrintEx` at `0x14000d3ea`
- `ntoskrnl!ZwClose` at `0x14000d3ff`
- `ntoskrnl!ZwClose` at `0x14000d3ff`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x14000d379`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x14000d379`
- `ntoskrnl!ZwOpenFile` at `0x14000d32d`
- `ntoskrnl!ZwOpenFile` at `0x14000d32d`

## string_xrefs

- `0x14000d33d`: `WERKERNELHOST: Could not open root dump directory, status 0x%X\n`

## pseudocode

```c
char WerpCheckDiskSpace()
{
  char v0; // bl
  NTSTATUS v1; // eax
  NTSTATUS v2; // eax
  void *FileHandle; // [rsp+30h] [rbp-19h] BYREF
  __int64 v5; // [rsp+38h] [rbp-11h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  __int128 FsInformation; // [rsp+80h] [rbp+37h] BYREF
  __int64 v9; // [rsp+90h] [rbp+47h]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  v9 = 0;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = &WerKernelLiveReportRootPath;
  v0 = 0;
  IoStatusBlock = 0;
  FsInformation = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = ZwOpenFile(&FileHandle, 0x20000u, &ObjectAttributes, &IoStatusBlock, 3u, 1u);
  if ( v1 >= 0 )
  {
    v2 = ZwQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 0x18u, FileFsSizeInformation);
    if ( v2 >= 0 )
    {
      v5 = 0;
      if ( is_mul_ok((unsigned int)v9, HIDWORD(v9)) )
      {
        v5 = ((unsigned int)v9 * (unsigned __int128)HIDWORD(v9)) >> 64;
        if ( is_mul_ok(*((unsigned __int64 *)&FsInformation + 1), (unsigned int)v9 * (unsigned __int64)HIDWORD(v9)) )
        {
          if ( ((*((_QWORD *)&FsInformation + 1) * (unsigned int)v9 * (unsigned __int64)HIDWORD(v9))
              & 0xFFFFFFFFFFF00000uLL) < 0xAF000000 )
            DbgPrintEx(5u, 1u, "WERKERNELHOST: Free disk space is below minimum allowed by policy\n");
          else
            v0 = 1;
        }
        else
        {
          DbgPrintEx(5u, 1u, "WERKERNELHOST: Failed to calcalate DiskTotalFreeSpaceInBytes\n");
        }
      }
      else
      {
        DbgPrintEx(5u, 1u, "WERKERNELHOST: Failed to calcalate BytesPerAllocationUnit\n");
      }
    }
    else
    {
      DbgPrintEx(5u, 1u, "WERKERNELHOST: Failed to retrieve disk free space, status 0x%X\n", (unsigned int)v2);
    }
  }
  else
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: Could not open root dump directory, status 0x%X\n", (unsigned int)v1);
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return v0;
}

```

## disassembly

```asm
0x14000d2a8  mov     [rsp-8+arg_0], rbx
0x14000d2ad  mov     [rsp-8+arg_8], rsi
0x14000d2b2  push    rbp
0x14000d2b3  lea     rbp, [rsp-57h]
0x14000d2b8  sub     rsp, 0A0h
0x14000d2bf  mov     rax, cs:__security_cookie
0x14000d2c6  xor     rax, rsp
0x14000d2c9  mov     [rbp+57h+var_8], rax
0x14000d2cd  xor     eax, eax
0x14000d2cf  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000d2d7  xorps   xmm0, xmm0
0x14000d2da  mov     [rbp+57h+var_10], rax
0x14000d2de  mov     [rbp+57h+FileHandle], rax
0x14000d2e2  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000d2e6  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14000d2ea  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000d2ee  lea     rax, WerKernelLiveReportRootPath
0x14000d2f5  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x14000d2fd  xorps   xmm1, xmm1
0x14000d300  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000d304  mov     esi, 1
0x14000d309  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000d30d  mov     [rsp+0A0h+OpenOptions], esi; OpenOptions
0x14000d311  mov     edx, 20000h; DesiredAccess
0x14000d316  xor     bl, bl
0x14000d318  mov     [rsp+0A0h+ShareAccess], 3; ShareAccess
0x14000d320  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14000d324  movups  [rbp+57h+FsInformation], xmm1
0x14000d328  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000d32d  call    cs:__imp_ZwOpenFile
0x14000d334  nop     dword ptr [rax+rax+00h]
0x14000d339  test    eax, eax
0x14000d33b  jns     short loc_14000D35F
0x14000d33d  lea     r8, aWerkernelhostC_7; "WERKERNELHOST: Could not open root dump"...
0x14000d344  mov     r9d, eax
0x14000d347  mov     edx, esi; Level
0x14000d349  mov     ecx, 5; ComponentId
0x14000d34e  call    cs:__imp_DbgPrintEx
0x14000d355  nop     dword ptr [rax+rax+00h]
0x14000d35a  jmp     loc_14000D3F6
0x14000d35f  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000d363  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x14000d367  mov     r9d, 18h; Length
0x14000d36d  mov     [rsp+0A0h+ShareAccess], 3; FsInformationClass
0x14000d375  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000d379  call    cs:__imp_ZwQueryVolumeInformationFile
0x14000d380  nop     dword ptr [rax+rax+00h]
0x14000d385  test    eax, eax
0x14000d387  jns     short loc_14000D392
0x14000d389  lea     r8, aWerkernelhostF_6; "WERKERNELHOST: Failed to retrieve disk "...
0x14000d390  jmp     short loc_14000D344
0x14000d392  mov     eax, dword ptr [rbp+57h+var_10+4]
0x14000d395  mov     ecx, dword ptr [rbp+57h+var_10]
0x14000d398  mul     rcx
0x14000d39b  mov     [rbp+57h+var_68], 0
0x14000d3a3  test    rdx, rdx
0x14000d3a6  jnz     short loc_14000D3DC
0x14000d3a8  mov     [rbp+57h+var_68], rdx
0x14000d3ac  mul     qword ptr [rbp+57h+FsInformation+8]
0x14000d3b0  test    rdx, rdx
0x14000d3b3  jnz     short loc_14000D3D3
0x14000d3b5  and     rax, 0FFFFFFFFFFF00000h
0x14000d3bb  mov     ecx, 0AF000000h
0x14000d3c0  cmp     rax, rcx
0x14000d3c3  jb      short loc_14000D3CA
0x14000d3c5  mov     bl, sil
0x14000d3c8  jmp     short loc_14000D3F6
0x14000d3ca  lea     r8, aWerkernelhostF; "WERKERNELHOST: Free disk space is below"...
0x14000d3d1  jmp     short loc_14000D3E3
0x14000d3d3  lea     r8, aWerkernelhostF_3; "WERKERNELHOST: Failed to calcalate Disk"...
0x14000d3da  jmp     short loc_14000D3E3
0x14000d3dc  lea     r8, aWerkernelhostF_7; "WERKERNELHOST: Failed to calcalate Byte"...
0x14000d3e3  mov     edx, esi; Level
0x14000d3e5  mov     ecx, 5; ComponentId
0x14000d3ea  call    cs:__imp_DbgPrintEx
0x14000d3f1  nop     dword ptr [rax+rax+00h]
0x14000d3f6  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14000d3fa  test    rcx, rcx
0x14000d3fd  jz      short loc_14000D40B
0x14000d3ff  call    cs:__imp_ZwClose
0x14000d406  nop     dword ptr [rax+rax+00h]
0x14000d40b  mov     al, bl
0x14000d40d  mov     rcx, [rbp+57h+var_8]
0x14000d411  xor     rcx, rsp; StackCookie
0x14000d414  call    __security_check_cookie
0x14000d419  lea     r11, [rsp+0A0h+var_s0]
0x14000d421  mov     rbx, [r11+10h]
0x14000d425  mov     rsi, [r11+18h]
0x14000d429  mov     rsp, r11
0x14000d42c  pop     rbp
0x14000d42d  retn
```
