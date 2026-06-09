# _TreeResetCallback(ushort *,ulong,_PROGRESS_INVOKE_SETTING *,void *,int)

- ea: `0x180033680`
- end: `0x180033813`
- name: `?_TreeResetCallback@@YAXPEAGKPEAW4_PROGRESS_INVOKE_SETTING@@PEAXH@Z`
- size: `403`
- prototype: `void __stdcall(LPWSTR pObjectName, DWORD Status, PPROG_INVOKE_SETTING pInvokeSetting, PVOID Args, BOOL SecuritySet)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180033680`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18003374a`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18003374a`
- `ntdll!NtQueryInformationFile` at `0x1800337bb`
- `ntdll!NtQueryInformationFile` at `0x1800337bb`
- `ntdll!NtClose` at `0x180033760`
- `ntdll!NtClose` at `0x1800337d5`
- `ntdll!NtClose` at `0x180033760`
- `ntdll!NtClose` at `0x1800337d5`
- `ntdll!RtlGetLastNtStatus` at `0x180033754`
- `ntdll!RtlGetLastNtStatus` at `0x180033754`
- `ntdll!NtOpenFile` at `0x18003372c`
- `ntdll!NtOpenFile` at `0x18003378b`
- `ntdll!NtOpenFile` at `0x18003372c`
- `ntdll!NtOpenFile` at `0x18003378b`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800336c9`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800336c9`

## pseudocode

```c
void __fastcall _TreeResetCallback(
        const WCHAR *pObjectName,
        DWORD Status,
        PPROG_INVOKE_SETTING pInvokeSetting,
        PVOID Args,
        BOOL SecuritySet)
{
  int v8; // ebx
  NTSTATUS LastNtStatus; // edi
  void *FileHandle; // [rsp+30h] [rbp-61h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-59h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-49h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-39h] BYREF
  _OWORD FileInformation[2]; // [rsp+88h] [rbp-9h] BYREF
  __int64 v15; // [rsp+A8h] [rbp+17h]

  *pInvokeSetting = ProgressInvokeEveryObject;
  v8 = 1;
  DestinationString = 0;
  if ( RtlInitUnicodeStringEx(&DestinationString, pObjectName) >= 0 )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    ObjectAttributes.RootDirectory = 0;
    FileHandle = 0;
    IoStatusBlock = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    LastNtStatus = NtOpenFile(&FileHandle, 0x40000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x200000u);
    if ( LastNtStatus >= 0 )
    {
      if ( !SetKernelObjectSecurity(FileHandle, 4u, Args) )
        LastNtStatus = RtlGetLastNtStatus();
      NtClose(FileHandle);
      if ( LastNtStatus >= 0 && NtOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 7u, 0) >= 0 )
      {
        v15 = 0;
        memset(FileInformation, 0, sizeof(FileInformation));
        if ( NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation) >= 0
          && (v15 & 0x10) != 0 )
        {
          v8 = 0;
        }
        NtClose(FileHandle);
      }
    }
  }
  if ( SecuritySet && Status && !v8 )
    *pInvokeSetting = ProgressRetryOperation;
}

```

## disassembly

```asm
0x180033680  mov     [rsp-8+arg_8], rbx
0x180033685  push    rbp
0x180033686  push    rsi
0x180033687  push    rdi
0x180033688  push    r14
0x18003368a  push    r15
0x18003368c  lea     rbp, [rsp-2Fh]
0x180033691  sub     rsp, 0C0h
0x180033698  mov     rax, cs:__security_cookie
0x18003369f  xor     rax, rsp
0x1800336a2  mov     [rbp+4Fh+var_30], rax
0x1800336a6  mov     r14d, edx
0x1800336a9  mov     dword ptr [r8], 2
0x1800336b0  mov     rdx, rcx; SourceString
0x1800336b3  xorps   xmm0, xmm0
0x1800336b6  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800336ba  mov     r15, r9
0x1800336bd  mov     rsi, r8
0x1800336c0  mov     ebx, 1
0x1800336c5  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800336c9  call    cs:__imp_RtlInitUnicodeStringEx
0x1800336cf  test    eax, eax
0x1800336d1  js      loc_1800337DB
0x1800336d7  xorps   xmm0, xmm0
0x1800336da  mov     [rsp+0E0h+OpenOptions], 200000h; OpenOptions
0x1800336e2  lea     rax, [rbp+4Fh+DestinationString]
0x1800336e6  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800336ee  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800336f2  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1800336f6  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800336fa  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x180033702  mov     edx, 40000h; DesiredAccess
0x180033707  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x18003370f  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x180033713  mov     [rbp+4Fh+FileHandle], 0
0x18003371b  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x18003371f  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x180033727  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18003372c  call    cs:__imp_NtOpenFile
0x180033732  mov     edi, eax
0x180033734  test    eax, eax
0x180033736  js      loc_1800337DB
0x18003373c  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x180033740  mov     r8, r15; SecurityDescriptor
0x180033743  lea     r15d, [rbx+3]
0x180033747  mov     edx, r15d; SecurityInformation
0x18003374a  call    cs:__imp_SetKernelObjectSecurity
0x180033750  test    eax, eax
0x180033752  jnz     short loc_18003375C
0x180033754  call    cs:__imp_RtlGetLastNtStatus
0x18003375a  mov     edi, eax
0x18003375c  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x180033760  call    cs:__imp_NtClose
0x180033766  test    edi, edi
0x180033768  js      short loc_1800337DB
0x18003376a  mov     [rsp+0E0h+OpenOptions], 0; OpenOptions
0x180033772  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x180033776  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18003377a  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x180033782  mov     edx, 120089h; DesiredAccess
0x180033787  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x18003378b  call    cs:__imp_NtOpenFile
0x180033791  test    eax, eax
0x180033793  js      short loc_1800337DB
0x180033795  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x180033799  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x18003379d  xor     eax, eax
0x18003379f  mov     [rsp+0E0h+ShareAccess], r15d; FileInformationClass
0x1800337a4  xorps   xmm0, xmm0
0x1800337a7  mov     [rbp+4Fh+var_38], rax
0x1800337ab  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800337af  movups  [rbp+4Fh+FileInformation], xmm0
0x1800337b3  lea     r9d, [rax+28h]; Length
0x1800337b7  movups  [rbp+4Fh+var_48], xmm0
0x1800337bb  call    cs:__imp_NtQueryInformationFile
0x1800337c1  test    eax, eax
0x1800337c3  js      short loc_1800337D1
0x1800337c5  test    byte ptr [rbp+4Fh+var_38], 10h
0x1800337c9  mov     eax, 0
0x1800337ce  cmovnz  ebx, eax
0x1800337d1  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1800337d5  call    cs:__imp_NtClose
0x1800337db  cmp     [rbp+4Fh+SecuritySet], 0
0x1800337df  jz      short loc_1800337F0
0x1800337e1  test    r14d, r14d
0x1800337e4  jz      short loc_1800337F0
0x1800337e6  test    ebx, ebx
0x1800337e8  jnz     short loc_1800337F0
0x1800337ea  mov     dword ptr [rsi], 5
0x1800337f0  mov     rcx, [rbp+4Fh+var_30]
0x1800337f4  xor     rcx, rsp; StackCookie
0x1800337f7  call    __security_check_cookie
0x1800337fc  mov     rbx, [rsp+0E0h+arg_8]
0x180033804  add     rsp, 0C0h
0x18003380b  pop     r15
0x18003380d  pop     r14
0x18003380f  pop     rdi
0x180033810  pop     rsi
0x180033811  pop     rbp
0x180033812  retn
```
