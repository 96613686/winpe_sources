# DfsGetDCName

- ea: `0x18000ace0`
- end: `0x18000af2c`
- name: `DfsGetDCName`
- size: `588`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002f910`

## callees

- `0x18000ace0`
- `0x18000af40`
- `0x18000b190`
- `0x18000c1e8`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000ae05`
- `ntdll!NtOpenFile` at `0x18000ae05`
- `ntdll!RtlNtStatusToDosError` at `0x18000ae23`
- `ntdll!RtlNtStatusToDosError` at `0x18000ae23`
- `ntdll!NtClose` at `0x18000af1b`
- `ntdll!NtClose` at `0x18000af1b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ae99`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ae99`
- `logoncli!DsGetDcNameW` at `0x18000ad5e`
- `logoncli!DsGetDcNameW` at `0x18000ad5e`
- `netutils!NetApiBufferFree` at `0x18000af0a`
- `netutils!NetApiBufferFree` at `0x18000af0a`
- `DSROLE!DsRoleFreeMemory` at `0x18000ae73`
- `DSROLE!DsRoleFreeMemory` at `0x18000ae73`

## pseudocode

```c
__int64 __fastcall DfsGetDCName(int a1, _BYTE *a2)
{
  __int64 v2; // rbx
  DWORD DomainNameInfo; // esi
  LPWSTR i; // rdi
  int Status; // eax
  __int64 v9; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-58h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+A8h] [rbp+10h] BYREF
  void *FileHandle; // [rsp+B0h] [rbp+18h] BYREF
  PVOID Buffer; // [rsp+B8h] [rbp+20h] BYREF

  *a2 = 1;
  v2 = -1;
  DomainControllerInfo = 0;
  FileHandle = (void *)-1LL;
  Buffer = 0;
  if ( (unsigned int)WsInAWorkgroup() == 1 )
    return 1355;
  if ( !hMupEvent )
    hMupEvent = CreateEventW(0, 1, 0, L"wkssvc:  MUP finished initializing event");
  DomainNameInfo = DfsGetDomainNameInfo((PBYTE *)&Buffer);
  if ( !DomainNameInfo )
  {
    DomainNameInfo = DsGetDcNameW(0, 0, 0, 0, a1 | 0x10, &DomainControllerInfo);
    if ( !DomainNameInfo )
    {
      for ( i = DomainControllerInfo->DomainControllerName; *i == 92; ++i )
        ;
      do
        ++v2;
      while ( i[v2] );
      if ( (_DWORD)v2 )
      {
        v9 = (unsigned int)(v2 - 1);
        if ( i[v9] != 46 )
          goto LABEL_11;
        i[v9] = 0;
        LODWORD(v2) = v2 - 1;
      }
      if ( (_DWORD)v2 )
      {
LABEL_11:
        *a2 = 0;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)LocalDfsName;
        *(_QWORD *)&ObjectAttributes.Length = 48;
        *(_QWORD *)&ObjectAttributes.Attributes = 64;
        ObjectAttributes.RootDirectory = 0;
        IoStatusBlock = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        Status = NtOpenFile(&FileHandle, 0x100002u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
        if ( Status < 0
          || (Status = IoStatusBlock.Status, IoStatusBlock.Status < 0)
          || (Status = DfsFsctl(FileHandle, 426148, i, (unsigned int)(2 * v2 + 2), 0, 0), Status < 0) )
        {
          DomainNameInfo = RtlNtStatusToDosError(Status);
        }
        goto LABEL_14;
      }
      DomainNameInfo = 59;
    }
  }
LABEL_14:
  if ( DomainControllerInfo )
    NetApiBufferFree(DomainControllerInfo);
  if ( FileHandle != (void *)-1LL )
    NtClose(FileHandle);
  if ( Buffer )
    DsRoleFreeMemory(Buffer);
  return DomainNameInfo;
}

```

## disassembly

```asm
0x18000ace0  mov     rax, rsp
0x18000ace3  push    rbx
0x18000ace4  push    rbp
0x18000ace5  push    rdi
0x18000ace6  push    r14
0x18000ace8  sub     rsp, 78h
0x18000acec  xor     ebp, ebp
0x18000acee  mov     byte ptr [rdx], 1
0x18000acf1  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000acf8  mov     [rax+10h], rbp
0x18000acfc  mov     [rax+18h], rbx
0x18000ad00  mov     r14, rdx
0x18000ad03  mov     [rax+20h], rbp
0x18000ad07  mov     edi, ecx
0x18000ad09  call    WsInAWorkgroup
0x18000ad0e  cmp     eax, 1
0x18000ad11  jz      loc_18000AE81
0x18000ad17  cmp     cs:hMupEvent, rbp
0x18000ad1e  mov     [rsp+98h+var_28], rsi
0x18000ad23  jz      loc_18000AE88
0x18000ad29  lea     rcx, [rsp+98h+Buffer]; Buffer
0x18000ad31  call    DfsGetDomainNameInfo
0x18000ad36  mov     esi, eax
0x18000ad38  test    eax, eax
0x18000ad3a  jnz     loc_18000AE31
0x18000ad40  lea     rax, [rsp+98h+arg_8]
0x18000ad48  or      edi, 10h
0x18000ad4b  mov     [rsp+98h+DomainControllerInfo], rax; DomainControllerInfo
0x18000ad50  xor     r9d, r9d; SiteName
0x18000ad53  xor     r8d, r8d; DomainGuid
0x18000ad56  mov     [rsp+98h+Flags], edi; Flags
0x18000ad5a  xor     edx, edx; DomainName
0x18000ad5c  xor     ecx, ecx; ComputerName
0x18000ad5e  call    cs:__imp_DsGetDcNameW
0x18000ad65  nop     dword ptr [rax+rax+00h]
0x18000ad6a  mov     esi, eax
0x18000ad6c  test    eax, eax
0x18000ad6e  jnz     loc_18000AE31
0x18000ad74  mov     rax, [rsp+98h+arg_8]
0x18000ad7c  mov     rdi, [rax]
0x18000ad7f  cmp     word ptr [rdi], 5Ch ; '\'
0x18000ad83  jnz     short loc_18000AD90
0x18000ad85  add     rdi, 2
0x18000ad89  cmp     word ptr [rdi], 5Ch ; '\'
0x18000ad8d  jz      short loc_18000AD85
0x18000ad8f  nop
0x18000ad90  inc     rbx
0x18000ad93  cmp     [rdi+rbx*2], bp
0x18000ad97  jnz     short loc_18000AD90
0x18000ad99  cmp     ebx, 1
0x18000ad9c  jnb     loc_18000AEB1
0x18000ada2  test    ebx, ebx
0x18000ada4  jz      loc_18000AF00
0x18000adaa  xorps   xmm0, xmm0
0x18000adad  mov     dword ptr [rsp+98h+DomainControllerInfo], 20h ; ' '; OpenOptions
0x18000adb5  lea     rax, LocalDfsName; "\"\""
0x18000adbc  mov     [r14], bpl
0x18000adbf  lea     r9, [rsp+98h+IoStatusBlock]; IoStatusBlock
0x18000adc4  mov     [rsp+98h+ObjectAttributes.ObjectName], rax
0x18000adc9  lea     r8, [rsp+98h+ObjectAttributes]; ObjectAttributes
0x18000adce  mov     qword ptr [rsp+98h+ObjectAttributes.Length], 30h ; '0'
0x18000add7  mov     edx, 100002h; DesiredAccess
0x18000addc  mov     qword ptr [rsp+98h+ObjectAttributes.Attributes], 40h ; '@'
0x18000ade5  lea     rcx, [rsp+98h+FileHandle]; FileHandle
0x18000aded  mov     [rsp+98h+ObjectAttributes.RootDirectory], rbp
0x18000adf2  movups  xmmword ptr [rsp+98h+IoStatusBlock], xmm0
0x18000adf7  mov     [rsp+98h+Flags], 7; ShareAccess
0x18000adff  movdqu  xmmword ptr [rsp+98h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ae05  call    cs:__imp_NtOpenFile
0x18000ae0c  nop     dword ptr [rax+rax+00h]
0x18000ae11  test    eax, eax
0x18000ae13  js      short loc_18000AE21
0x18000ae15  mov     eax, dword ptr [rsp+98h+IoStatusBlock]
0x18000ae19  test    eax, eax
0x18000ae1b  jns     loc_18000AECD
0x18000ae21  mov     ecx, eax; Status
0x18000ae23  call    cs:__imp_RtlNtStatusToDosError
0x18000ae2a  nop     dword ptr [rax+rax+00h]
0x18000ae2f  mov     esi, eax
0x18000ae31  mov     rcx, [rsp+98h+arg_8]; Buffer
0x18000ae39  test    rcx, rcx
0x18000ae3c  jnz     loc_18000AF0A
0x18000ae42  mov     rcx, [rsp+98h+FileHandle]; Handle
0x18000ae4a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ae4e  jnz     loc_18000AF1B
0x18000ae54  mov     rcx, [rsp+98h+Buffer]; Buffer
0x18000ae5c  test    rcx, rcx
0x18000ae5f  jnz     short loc_18000AE73
0x18000ae61  mov     eax, esi
0x18000ae63  mov     rsi, [rsp+98h+var_28]
0x18000ae68  add     rsp, 78h
0x18000ae6c  pop     r14
0x18000ae6e  pop     rdi
0x18000ae6f  pop     rbp
0x18000ae70  pop     rbx
0x18000ae71  retn
0x18000ae73  call    cs:__imp_DsRoleFreeMemory
0x18000ae7a  nop     dword ptr [rax+rax+00h]
0x18000ae7f  jmp     short loc_18000AE61
0x18000ae81  mov     eax, 54Bh
0x18000ae86  jmp     short loc_18000AE68
0x18000ae88  lea     r9, Name; "wkssvc:  MUP finished initializing even"...
0x18000ae8f  xor     r8d, r8d; bInitialState
0x18000ae92  mov     edx, 1; bManualReset
0x18000ae97  xor     ecx, ecx; lpEventAttributes
0x18000ae99  call    cs:__imp_CreateEventW
0x18000aea0  nop     dword ptr [rax+rax+00h]
0x18000aea5  mov     cs:hMupEvent, rax
0x18000aeac  jmp     loc_18000AD29
0x18000aeb1  lea     ecx, [rbx-1]
0x18000aeb4  cmp     word ptr [rdi+rcx*2], 2Eh ; '.'
0x18000aeb9  lea     rdx, [rdi+rcx*2]
0x18000aebd  jnz     loc_18000ADAA
0x18000aec3  mov     [rdx], bp
0x18000aec6  mov     ebx, ecx
0x18000aec8  jmp     loc_18000ADA2
0x18000aecd  mov     rcx, [rsp+98h+FileHandle]
0x18000aed5  lea     r9d, ds:2[rbx*2]
0x18000aedd  mov     dword ptr [rsp+98h+DomainControllerInfo], ebp
0x18000aee1  mov     r8, rdi
0x18000aee4  mov     edx, 680A4h
0x18000aee9  mov     qword ptr [rsp+98h+Flags], rbp
0x18000aeee  call    DfsFsctl
0x18000aef3  test    eax, eax
0x18000aef5  jns     loc_18000AE31
0x18000aefb  jmp     loc_18000AE21
0x18000af00  mov     esi, 3Bh ; ';'
0x18000af05  jmp     loc_18000AE31
0x18000af0a  call    cs:__imp_NetApiBufferFree
0x18000af11  nop     dword ptr [rax+rax+00h]
0x18000af16  jmp     loc_18000AE42
0x18000af1b  call    cs:__imp_NtClose
0x18000af22  nop     dword ptr [rax+rax+00h]
0x18000af27  jmp     loc_18000AE54
```
