# WerLiveKernelInitSystemExt

- ea: `0x140012080`
- end: `0x1400122ba`
- name: `WerLiveKernelInitSystemExt`
- size: `570`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140001748`
- `0x140002750`
- `0x14000d174`
- `0x14000f1d4`
- `0x140012080`
- `0x1400122c0`
- `0x140012588`
- `0x140012a94`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400121ff`
- `ntoskrnl!DbgPrintEx` at `0x1400121ff`
- `ntoskrnl!ZwClose` at `0x140012148`
- `ntoskrnl!ZwClose` at `0x1400121cd`
- `ntoskrnl!ZwClose` at `0x140012148`
- `ntoskrnl!ZwClose` at `0x1400121cd`
- `ntoskrnl!EtwSetInformation` at `0x14001229f`
- `ntoskrnl!EtwSetInformation` at `0x14001229f`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400121b0`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400121b0`
- `ntoskrnl!EtwRegister` at `0x14001227b`
- `ntoskrnl!EtwRegister` at `0x14001227b`
- `ntoskrnl!ZwOpenFile` at `0x14001211e`
- `ntoskrnl!ZwOpenFile` at `0x14001211e`

## string_xrefs

- `0x1400121ed`: `WERKERNELHOST: WerpInitRootPath failed with status 0x%X\n`
- `0x1400120c2`: `\SystemRoot\System32`
- `0x1400120d9`: `wersvc.dll`

## pseudocode

```c
__int64 WerLiveKernelInitSystemExt()
{
  __int64 v0; // rdx
  ULONG Length; // ebx
  void *Mem; // rax
  void *v3; // rdi
  unsigned int v5; // ebx
  int inited; // ebx
  void *FileHandle; // [rsp+60h] [rbp-19h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+68h] [rbp-11h] BYREF
  _QWORD v9[2]; // [rsp+78h] [rbp-1h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp+Fh] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp+3Fh] BYREF

  FileHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v9[1] = L"\\SystemRoot\\System32";
  v9[0] = 2752552;
  FileName.Buffer = L"wersvc.dll";
  *(_QWORD *)&FileName.Length = 1441812;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v9;
  IoStatusBlock = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 3u, 0x11u) < 0 )
    return 3221225474LL;
  Length = FileName.Length + 12;
  Mem = (void *)WerpAllocateMem(Length, v0);
  v3 = Mem;
  if ( !Mem )
  {
    ZwClose(FileHandle);
    return 3221225474LL;
  }
  v5 = (unsigned int)ZwQueryDirectoryFile(
                       FileHandle,
                       0,
                       0,
                       0,
                       &IoStatusBlock,
                       Mem,
                       Length,
                       FileNamesInformation,
                       1u,
                       &FileName,
                       1u) >> 31;
  WerpFreeMem(v3);
  ZwClose(FileHandle);
  if ( (unsigned __int8)v5 == 1 )
    return 3221225474LL;
  inited = WerpInitRootPath();
  if ( inited >= 0 )
  {
    inited = WerpInitThrottlePolicy();
    if ( inited >= 0 )
    {
      WerHighestAllowedPolicy = 2;
      WerKernelLiveReportInitialized = 1;
      IoStatusBlock = (struct _IO_STATUS_BLOCK)*((_OWORD *)EventInformation - 1);
      if ( RegHandle )
        __fastfail(5u);
      xmmword_140009070 = 0;
      if ( !EtwRegister((LPCGUID)&IoStatusBlock, tlgEnableCallback, &dword_140009048, &RegHandle) )
        EtwSetInformation(RegHandle, EventProviderSetTraits, EventInformation, *(unsigned __int16 *)EventInformation);
      McGenEventRegister_EtwRegister();
      wil_InitializeFeatureStaging();
    }
    else
    {
      DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpInitThrottlePolicy failed with status 0x%X\n", (unsigned int)inited);
    }
  }
  else
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpInitRootPath failed with status 0x%X\n", (unsigned int)inited);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140012080  mov     [rsp-8+arg_0], rbx
0x140012085  mov     [rsp-8+arg_8], rdi
0x14001208a  push    rbp
0x14001208b  lea     rbp, [rsp-57h]
0x140012090  sub     rsp, 0D0h
0x140012097  mov     rax, cs:__security_cookie
0x14001209e  xor     rax, rsp
0x1400120a1  mov     [rbp+57h+var_8], rax
0x1400120a5  xor     eax, eax
0x1400120a7  mov     [rsp+0D0h+OpenOptions], 11h; OpenOptions
0x1400120af  mov     [rbp+57h+FileHandle], rax
0x1400120b3  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400120b7  xorps   xmm0, xmm0
0x1400120ba  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400120c2  lea     rax, aSystemrootSyst; "\\SystemRoot\\System32"
0x1400120c9  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400120d1  mov     [rbp+57h+var_50], rax
0x1400120d5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400120d9  lea     rax, aWersvcDll; "wersvc.dll"
0x1400120e0  mov     [rbp+57h+var_58], 2A0028h
0x1400120e8  mov     [rbp+57h+var_68.Buffer], rax
0x1400120ec  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400120f0  lea     rax, [rbp+57h+var_58]
0x1400120f4  mov     qword ptr [rbp+57h+var_68.Length], 160014h
0x1400120fc  mov     edx, 100001h; DesiredAccess
0x140012101  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140012105  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140012109  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140012111  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140012116  mov     [rsp+0D0h+ShareAccess], 3; ShareAccess
0x14001211e  call    cs:__imp_ZwOpenFile
0x140012125  nop     dword ptr [rax+rax+00h]
0x14001212a  test    eax, eax
0x14001212c  js      short loc_140012154
0x14001212e  movzx   ebx, [rbp+57h+var_68.Length]
0x140012132  add     ebx, 0Ch
0x140012135  mov     ecx, ebx
0x140012137  call    WerpAllocateMem
0x14001213c  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140012140  mov     rdi, rax
0x140012143  test    rax, rax
0x140012146  jnz     short loc_14001217B
0x140012148  call    cs:__imp_ZwClose
0x14001214f  nop     dword ptr [rax+rax+00h]
0x140012154  mov     eax, 0C0000002h
0x140012159  mov     rcx, [rbp+57h+var_8]
0x14001215d  xor     rcx, rsp; StackCookie
0x140012160  call    __security_check_cookie
0x140012165  lea     r11, [rsp+0D0h+var_s0]
0x14001216d  mov     rbx, [r11+10h]
0x140012171  mov     rdi, [r11+18h]
0x140012175  mov     rsp, r11
0x140012178  pop     rbp
0x140012179  retn
0x14001217b  mov     [rsp+0D0h+RestartScan], 1; RestartScan
0x140012180  lea     rax, [rbp+57h+var_68]
0x140012184  mov     [rsp+0D0h+FileName], rax; FileName
0x140012189  xor     r9d, r9d; ApcContext
0x14001218c  mov     [rsp+0D0h+ReturnSingleEntry], 1; ReturnSingleEntry
0x140012191  lea     rax, [rbp+57h+IoStatusBlock]
0x140012195  mov     [rsp+0D0h+FileInformationClass], 0Ch; FileInformationClass
0x14001219d  xor     r8d, r8d; ApcRoutine
0x1400121a0  mov     [rsp+0D0h+Length], ebx; Length
0x1400121a4  xor     edx, edx; Event
0x1400121a6  mov     qword ptr [rsp+0D0h+OpenOptions], rdi; FileInformation
0x1400121ab  mov     qword ptr [rsp+0D0h+ShareAccess], rax; IoStatusBlock
0x1400121b0  call    cs:__imp_ZwQueryDirectoryFile
0x1400121b7  nop     dword ptr [rax+rax+00h]
0x1400121bc  mov     ebx, eax
0x1400121be  mov     rcx, rdi
0x1400121c1  shr     ebx, 1Fh
0x1400121c4  call    WerpFreeMem
0x1400121c9  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400121cd  call    cs:__imp_ZwClose
0x1400121d4  nop     dword ptr [rax+rax+00h]
0x1400121d9  xor     bl, 1
0x1400121dc  jz      loc_140012154
0x1400121e2  call    WerpInitRootPath
0x1400121e7  mov     ebx, eax
0x1400121e9  test    eax, eax
0x1400121eb  jns     short loc_140012212
0x1400121ed  lea     r8, aWerkernelhostW_37; "WERKERNELHOST: WerpInitRootPath failed "...
0x1400121f4  mov     edx, 1; Level
0x1400121f9  mov     r9d, ebx
0x1400121fc  lea     ecx, [rdx+4]; ComponentId
0x1400121ff  call    cs:__imp_DbgPrintEx
0x140012206  nop     dword ptr [rax+rax+00h]
0x14001220b  mov     eax, ebx
0x14001220d  jmp     loc_140012159
0x140012212  call    WerpInitThrottlePolicy
0x140012217  mov     ebx, eax
0x140012219  test    eax, eax
0x14001221b  jns     short loc_140012226
0x14001221d  lea     r8, aWerkernelhostW_28; "WERKERNELHOST: WerpInitThrottlePolicy f"...
0x140012224  jmp     short loc_1400121F4
0x140012226  cmp     cs:RegHandle, 0
0x14001222e  mov     edi, 2
0x140012233  mov     rax, cs:EventInformation
0x14001223a  mov     cs:WerHighestAllowedPolicy, edi
0x140012240  mov     cs:WerKernelLiveReportInitialized, 1
0x140012247  movups  xmm0, xmmword ptr [rax-10h]
0x14001224b  movdqu  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140012250  jz      short loc_140012257
0x140012252  lea     ecx, [rdi+3]
0x140012255  int     29h; Win8: RtlFailFast(ecx)
0x140012257  xorps   xmm0, xmm0
0x14001225a  lea     r9, RegHandle; RegHandle
0x140012261  lea     r8, dword_140009048; CallbackContext
0x140012268  lea     rdx, _tlgEnableCallback; EnableCallback
0x14001226f  lea     rcx, [rbp+57h+IoStatusBlock]; ProviderId
0x140012273  movdqu  cs:xmmword_140009070, xmm0
0x14001227b  call    cs:__imp_EtwRegister
0x140012282  nop     dword ptr [rax+rax+00h]
0x140012287  test    eax, eax
0x140012289  jnz     short loc_1400122AB
0x14001228b  mov     r8, cs:EventInformation; EventInformation
0x140012292  mov     edx, edi; InformationClass
0x140012294  mov     rcx, cs:RegHandle; RegHandle
0x14001229b  movzx   r9d, word ptr [r8]; InformationLength
0x14001229f  call    cs:__imp_EtwSetInformation
0x1400122a6  nop     dword ptr [rax+rax+00h]
0x1400122ab  call    McGenEventRegister_EtwRegister
0x1400122b0  call    wil_InitializeFeatureStaging
0x1400122b5  jmp     loc_14001220B
```
