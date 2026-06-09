# TpmEnsureDirExists

- ea: `0x14000bf68`
- end: `0x14000c224`
- name: `TpmEnsureDirExists`
- size: `700`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000a4f0`

## callees

- `0x14000a0a4`
- `0x14000a3d0`
- `0x14000bf68`
- `0x14001d63c`
- `0x140039740`
- `0x140039780`
- `0x140039b40`
- `0x140045430`
- `0x1400454a0`

## import_xrefs

- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14000c0b6`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14000c11d`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14000c0b6`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14000c11d`
- `ntoskrnl!ZwCreateFile` at `0x14000c1cb`
- `ntoskrnl!ZwCreateFile` at `0x14000c1cb`
- `ntoskrnl!ZwClose` at `0x14000c1e3`
- `ntoskrnl!ZwClose` at `0x14000c1e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c00a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c159`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c00a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c159`

## string_xrefs

- `0x14000c0a8`: `TpmDriverLogPath`
- `0x14000c10b`: `TpmDriverLogPath`
- `0x14000bfff`: `WBCLPath`

## pseudocode

```c
__int64 TpmEnsureDirExists()
{
  NTSTATUS PersistedStateLocation; // ebx
  unsigned __int8 *v1; // rdi
  WCHAR *v2; // rdx
  unsigned __int64 v4; // [rsp+60h] [rbp-A0h] BYREF
  struct WDFKEY__ *v5; // [rsp+68h] [rbp-98h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v7; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR SourceString[280]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t Src[264]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int64 retaddr; // [rsp+558h] [rbp+458h]

  FileHandle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v7 = 0;
  memset(Src, 0, 0x208u);
  memset(SourceString, 0, sizeof(SourceString));
  v4 = 0;
  v5 = 0;
  DestinationString = 0;
  PersistedStateLocation = TpmRegistry::OpenKey(0, 131097, &v5);
  if ( PersistedStateLocation >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"WBCLPath");
    PersistedStateLocation = (*((__int64 (__fastcall **)(PKDPC, struct WDFKEY__ *, struct _UNICODE_STRING *, __int64, wchar_t *, _QWORD, char *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                              + 235))(
                               WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                               v5,
                               &DestinationString,
                               520,
                               Src,
                               0,
                               (char *)&v4 + 4);
    if ( PersistedStateLocation >= 0 && HIDWORD(v4) != 1 )
      PersistedStateLocation = -1073741823;
  }
  TpmRegistry::CloseKey(v5);
  if ( PersistedStateLocation != -2147483643 )
  {
    if ( PersistedStateLocation != -1073741772 )
    {
      if ( PersistedStateLocation < 0 )
        goto LABEL_15;
      TpmConvertFilePathToObjectPath(SourceString, Src);
      v2 = SourceString;
      goto LABEL_14;
    }
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"TpmDriverLogPath",
                               0,
                               L"\\SystemRoot\\Logs\\MeasuredBoot",
                               1,
                               0,
                               0,
                               &v4);
    if ( PersistedStateLocation != -2147483643 )
      goto LABEL_15;
    v1 = TpmAlloc(1, (unsigned int)v4, retaddr);
    if ( !v1 )
    {
      PersistedStateLocation = -1073741670;
      goto LABEL_15;
    }
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"TpmDriverLogPath",
                               0,
                               L"\\SystemRoot\\Logs\\MeasuredBoot",
                               1,
                               v1,
                               v4,
                               &v4);
    if ( PersistedStateLocation >= 0 )
    {
      v2 = (WCHAR *)v1;
LABEL_14:
      RtlInitUnicodeString(&v7, v2);
      ObjectAttributes.ObjectName = &v7;
      ObjectAttributes.SecurityDescriptor = qword_14003D118;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 704;
      ObjectAttributes.SecurityQualityOfService = 0;
      PersistedStateLocation = ZwCreateFile(
                                 &FileHandle,
                                 0x100110u,
                                 &ObjectAttributes,
                                 &IoStatusBlock,
                                 0,
                                 4u,
                                 0,
                                 3u,
                                 0x21u,
                                 0,
                                 0);
    }
  }
LABEL_15:
  if ( FileHandle )
  {
    ZwClose(FileHandle);
    FileHandle = 0;
  }
  if ( v7.Buffer != SourceString )
    TpmFree(v7.Buffer);
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x14000bf68  push    rbp
0x14000bf6a  push    rbx
0x14000bf6b  push    rsi
0x14000bf6c  push    rdi
0x14000bf6d  lea     rbp, [rsp-438h]
0x14000bf75  sub     rsp, 538h
0x14000bf7c  mov     rax, cs:__security_cookie
0x14000bf83  xor     rax, rsp
0x14000bf86  mov     [rbp+450h+var_30], rax
0x14000bf8d  xorps   xmm1, xmm1
0x14000bf90  lea     rcx, [rbp+450h+Src]; void *
0x14000bf97  xorps   xmm0, xmm0
0x14000bf9a  mov     edi, 208h
0x14000bf9f  xor     esi, esi
0x14000bfa1  mov     r8d, edi; Size
0x14000bfa4  xor     edx, edx; Val
0x14000bfa6  mov     [rsp+550h+FileHandle], rsi
0x14000bfab  movups  xmmword ptr [rbp+450h+IoStatusBlock], xmm0
0x14000bfaf  movups  xmmword ptr [rbp+450h+ObjectAttributes.Length], xmm1
0x14000bfb3  movups  xmmword ptr [rbp+450h+ObjectAttributes.ObjectName], xmm1
0x14000bfb7  movups  xmmword ptr [rbp+450h+ObjectAttributes.SecurityDescriptor], xmm1
0x14000bfbb  movups  xmmword ptr [rsp+550h+var_4D8.Length], xmm0
0x14000bfc0  call    memset
0x14000bfc5  xor     edx, edx; Val
0x14000bfc7  lea     r8d, [rdi+28h]; Size
0x14000bfcb  lea     rcx, [rbp+450h+SourceString]; void *
0x14000bfcf  call    memset
0x14000bfd4  xorps   xmm0, xmm0
0x14000bfd7  mov     dword ptr [rsp+550h+var_4F0], esi
0x14000bfdb  lea     r8, [rsp+550h+var_4E8]
0x14000bfe0  mov     [rsp+550h+var_4E8], rsi
0x14000bfe5  mov     edx, 20019h
0x14000bfea  mov     dword ptr [rsp+550h+var_4F0+4], esi
0x14000bfee  xor     ecx, ecx
0x14000bff0  movups  xmmword ptr [rbp+450h+DestinationString.Length], xmm0
0x14000bff4  call    ?OpenKey@TpmRegistry@@CAJW4KEY_VALUES@1@KPEAPEAUWDFKEY__@@@Z; TpmRegistry::OpenKey(TpmRegistry::KEY_VALUES,ulong,WDFKEY__ * *)
0x14000bff9  mov     ebx, eax
0x14000bffb  test    eax, eax
0x14000bffd  js      short loc_14000C06A
0x14000bfff  lea     rdx, aWbclpath; "WBCLPath"
0x14000c006  lea     rcx, [rbp+450h+DestinationString]; DestinationString
0x14000c00a  call    cs:__imp_RtlInitUnicodeString
0x14000c011  nop     dword ptr [rax+rax+00h]
0x14000c016  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14000c01d  lea     rcx, [rsp+550h+var_4F0+4]
0x14000c022  mov     rdx, [rsp+550h+var_4E8]
0x14000c027  lea     r8, [rbp+450h+DestinationString]
0x14000c02b  mov     qword ptr [rsp+550h+ShareAccess], rcx
0x14000c030  mov     r9d, edi
0x14000c033  lea     rcx, [rbp+450h+Src]
0x14000c03a  mov     qword ptr [rsp+550h+FileAttributes], rsi
0x14000c03f  mov     rax, [rax+758h]
0x14000c046  mov     [rsp+550h+AllocationSize], rcx
0x14000c04b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14000c052  call    _guard_dispatch_icall
0x14000c057  mov     ebx, eax
0x14000c059  test    eax, eax
0x14000c05b  js      short loc_14000C06A
0x14000c05d  cmp     dword ptr [rsp+550h+var_4F0+4], 1
0x14000c062  mov     eax, 0C0000001h
0x14000c067  cmovnz  ebx, eax
0x14000c06a  mov     rcx, [rsp+550h+var_4E8]; struct WDFKEY__ *
0x14000c06f  call    ?CloseKey@TpmRegistry@@CAXPEAUWDFKEY__@@@Z; TpmRegistry::CloseKey(WDFKEY__ *)
0x14000c074  mov     edi, 80000005h
0x14000c079  cmp     ebx, edi
0x14000c07b  jz      loc_14000C1D9
0x14000c081  cmp     ebx, 0C0000034h
0x14000c087  jnz     loc_14000C138
0x14000c08d  lea     rax, [rsp+550h+var_4F0]
0x14000c092  mov     r9d, 1
0x14000c098  mov     qword ptr [rsp+550h+ShareAccess], rax
0x14000c09d  lea     r8, aSystemrootLogs; "\\SystemRoot\\Logs\\MeasuredBoot"
0x14000c0a4  mov     [rsp+550h+FileAttributes], esi
0x14000c0a8  lea     rcx, aTpmdriverlogpa; "TpmDriverLogPath"
0x14000c0af  xor     edx, edx
0x14000c0b1  mov     [rsp+550h+AllocationSize], rsi
0x14000c0b6  call    cs:__imp_RtlGetPersistedStateLocation
0x14000c0bd  nop     dword ptr [rax+rax+00h]
0x14000c0c2  mov     ebx, eax
0x14000c0c4  cmp     eax, edi
0x14000c0c6  jnz     loc_14000C1D9
0x14000c0cc  mov     r8, [rbp+458h]; unsigned __int64
0x14000c0d3  mov     cl, 1; bool
0x14000c0d5  mov     edx, dword ptr [rsp+550h+var_4F0]; unsigned __int64
0x14000c0d9  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14000c0de  mov     rdi, rax
0x14000c0e1  test    rax, rax
0x14000c0e4  jnz     short loc_14000C0F0
0x14000c0e6  mov     ebx, 0C000009Ah
0x14000c0eb  jmp     loc_14000C1D9
0x14000c0f0  lea     rax, [rsp+550h+var_4F0]
0x14000c0f5  mov     r9d, 1
0x14000c0fb  mov     qword ptr [rsp+550h+ShareAccess], rax
0x14000c100  lea     r8, aSystemrootLogs; "\\SystemRoot\\Logs\\MeasuredBoot"
0x14000c107  mov     eax, dword ptr [rsp+550h+var_4F0]
0x14000c10b  lea     rcx, aTpmdriverlogpa; "TpmDriverLogPath"
0x14000c112  mov     [rsp+550h+FileAttributes], eax
0x14000c116  xor     edx, edx
0x14000c118  mov     [rsp+550h+AllocationSize], rdi
0x14000c11d  call    cs:__imp_RtlGetPersistedStateLocation
0x14000c124  nop     dword ptr [rax+rax+00h]
0x14000c129  mov     ebx, eax
0x14000c12b  test    eax, eax
0x14000c12d  js      loc_14000C1D9
0x14000c133  mov     rdx, rdi
0x14000c136  jmp     short loc_14000C154
0x14000c138  test    ebx, ebx
0x14000c13a  js      loc_14000C1D9
0x14000c140  lea     rdx, [rbp+450h+Src]; Src
0x14000c147  lea     rcx, [rbp+450h+SourceString]; Dst
0x14000c14b  call    TpmConvertFilePathToObjectPath
0x14000c150  lea     rdx, [rbp+450h+SourceString]; SourceString
0x14000c154  lea     rcx, [rsp+550h+var_4D8]; DestinationString
0x14000c159  call    cs:__imp_RtlInitUnicodeString
0x14000c160  nop     dword ptr [rax+rax+00h]
0x14000c165  mov     [rsp+550h+EaLength], esi; EaLength
0x14000c169  lea     rax, [rsp+550h+var_4D8]
0x14000c16e  mov     [rsp+550h+EaBuffer], rsi; EaBuffer
0x14000c173  lea     r9, [rbp+450h+IoStatusBlock]; IoStatusBlock
0x14000c177  mov     [rsp+550h+CreateOptions], 21h ; '!'; CreateOptions
0x14000c17f  lea     r8, [rbp+450h+ObjectAttributes]; ObjectAttributes
0x14000c183  mov     [rsp+550h+CreateDisposition], 3; CreateDisposition
0x14000c18b  lea     rcx, [rsp+550h+FileHandle]; FileHandle
0x14000c190  mov     [rbp+450h+ObjectAttributes.ObjectName], rax
0x14000c194  mov     edx, 100110h; DesiredAccess
0x14000c199  lea     rax, qword_14003D118
0x14000c1a0  mov     [rsp+550h+ShareAccess], esi; ShareAccess
0x14000c1a4  mov     [rsp+550h+FileAttributes], 4; FileAttributes
0x14000c1ac  mov     [rbp+450h+ObjectAttributes.SecurityDescriptor], rax
0x14000c1b0  mov     [rsp+550h+AllocationSize], rsi; AllocationSize
0x14000c1b5  mov     [rbp+450h+ObjectAttributes.Length], 30h ; '0'
0x14000c1bc  mov     [rbp+450h+ObjectAttributes.RootDirectory], rsi
0x14000c1c0  mov     [rbp+450h+ObjectAttributes.Attributes], 2C0h
0x14000c1c7  mov     [rbp+450h+ObjectAttributes.SecurityQualityOfService], rsi
0x14000c1cb  call    cs:__imp_ZwCreateFile
0x14000c1d2  nop     dword ptr [rax+rax+00h]
0x14000c1d7  mov     ebx, eax
0x14000c1d9  mov     rcx, [rsp+550h+FileHandle]; Handle
0x14000c1de  test    rcx, rcx
0x14000c1e1  jz      short loc_14000C1F4
0x14000c1e3  call    cs:__imp_ZwClose
0x14000c1ea  nop     dword ptr [rax+rax+00h]
0x14000c1ef  mov     [rsp+550h+FileHandle], rsi
0x14000c1f4  mov     rcx, [rbp+450h+var_4D8.Buffer]; void *
0x14000c1f8  lea     rax, [rbp+450h+SourceString]
0x14000c1fc  cmp     rcx, rax
0x14000c1ff  jz      short loc_14000C206
0x14000c201  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14000c206  mov     eax, ebx
0x14000c208  mov     rcx, [rbp+450h+var_30]
0x14000c20f  xor     rcx, rsp; StackCookie
0x14000c212  call    __security_check_cookie
0x14000c217  add     rsp, 538h
0x14000c21e  pop     rdi
0x14000c21f  pop     rsi
0x14000c220  pop     rbx
0x14000c221  pop     rbp
0x14000c222  retn
```
