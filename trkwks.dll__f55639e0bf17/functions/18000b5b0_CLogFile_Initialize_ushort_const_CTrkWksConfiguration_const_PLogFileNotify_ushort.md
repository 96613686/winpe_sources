# CLogFile::Initialize(ushort const *,CTrkWksConfiguration const *,PLogFileNotify *,ushort)

- ea: `0x18000b5b0`
- end: `0x18000b91b`
- name: `?Initialize@CLogFile@@QEAAXPEBGPEBVCTrkWksConfiguration@@PEAVPLogFileNotify@@G@Z`
- size: `875`
- prototype: `void __fastcall(CLogFile *this, const unsigned __int16 *, const struct CTrkWksConfiguration *, struct PLogFileNotify *, unsigned __int16)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000756c`

## callees

- `0x1800066c0`
- `0x18000b5b0`
- `0x18000b924`
- `0x18000b97c`
- `0x18000baac`
- `0x18000d038`
- `0x180010fca`
- `0x180011000`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18000b7b1`
- `ntdll!NtCreateFile` at `0x18000b7b1`
- `ntdll!RtlFreeHeap` at `0x18000b7d8`
- `ntdll!RtlFreeHeap` at `0x18000b7d8`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000b738`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000b738`
- `ntdll!NtQueryVolumeInformationFile` at `0x18000b801`
- `ntdll!NtQueryVolumeInformationFile` at `0x18000b801`
- `ntdll!NtClose` at `0x18000b80e`
- `ntdll!NtClose` at `0x18000b80e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b8f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b8f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b90d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b90d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b67d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b8c0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b8d1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b8e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b67d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b8c0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b8d1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b8e5`

## pseudocode

```c
void __fastcall CLogFile::Initialize(
        CLogFile *this,
        const unsigned __int16 *a2,
        const struct CTrkWksConfiguration *a3,
        struct PLogFileNotify *a4,
        unsigned __int16 a5)
{
  WCHAR *v7; // r8
  WCHAR *v8; // r10
  __int64 v9; // r11
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r9
  WCHAR *v13; // rax
  int v14; // r9d
  _WORD *v15; // rdx
  const unsigned __int16 *v16; // r8
  PWSTR Buffer; // rbx
  signed int v18; // edi
  signed int v19; // ebx
  unsigned int v20; // edx
  PLogFileNotify *v21; // rcx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK v28; // [rsp+B8h] [rbp-48h] BYREF
  __int128 FsInformation; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v30[2]; // [rsp+D8h] [rbp-28h]
  WCHAR DosPathName[261]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v32[6]; // [rsp+2EAh] [rbp+1EAh] BYREF

  FileHandle = 0;
  *(_QWORD *)v30 = 0;
  FsInformation = 0;
  v28 = 0;
  if ( a3 )
    *((_QWORD *)this + 6) = a3;
  if ( a2 )
    *((_QWORD *)this + 5) = a2;
  if ( a4 )
  {
    v21 = (PLogFileNotify *)*((_QWORD *)this + 7);
    if ( v21 )
      PLogFileNotify::Release(v21);
    *((_QWORD *)this + 7) = a4;
    _InterlockedIncrement((volatile signed __int32 *)a4 + 2);
  }
  *((_WORD *)this + 38) = a5;
  memset_0(DosPathName, 0, sizeof(DosPathName));
  v7 = (WCHAR *)*((_QWORD *)this + 5);
  v8 = DosPathName;
  v9 = 2147483646;
  v10 = 261;
  v11 = 2147483646;
  v12 = 261;
  while ( v11 && *v7 )
  {
    *v8++ = *v7++;
    --v11;
    if ( !--v12 )
    {
      *(v8 - 1) = 0;
      goto LABEL_11;
    }
  }
  *v8 = 0;
  v13 = DosPathName;
  while ( *v13 )
  {
    ++v13;
    if ( !--v10 )
      goto LABEL_11;
  }
  v14 = 0;
  v15 = &v32[-2 * v10];
  v16 = L"\\";
  while ( v9 && *v16 )
  {
    *v15++ = *v16++;
    --v9;
    if ( !--v10 )
    {
      --v15;
      v14 = -2147024774;
      break;
    }
  }
  *v15 = 0;
  if ( v14 < 0 )
  {
LABEL_11:
    RaiseException(0x80000005, 0, 0, 0);
    __debugbreak();
  }
  FileHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  NtPathName = 0;
  if ( !RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0) )
  {
    v18 = -1073741773;
    goto LABEL_36;
  }
  Buffer = NtPathName.Buffer;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v18 = NtCreateFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x800020u, 0, 0);
  if ( v18 < 0 )
    FileHandle = 0;
  if ( Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v18 < 0 )
  {
LABEL_36:
    RaiseException(v18, 0, 0, 0);
    __debugbreak();
  }
  v19 = NtQueryVolumeInformationFile(FileHandle, &v28, &FsInformation, 0x18u, FileFsSizeInformation);
  NtClose(FileHandle);
  if ( v19 < 0 )
  {
    RaiseException(v19, 0, 0, 0);
    __debugbreak();
  }
  v20 = v30[1];
  *((_DWORD *)this + 16) = v30[1];
  if ( v20 < 0x100 )
  {
    RaiseException(0xC0000206, 0, 0, 0);
    __debugbreak();
  }
  CLogFileHeader::Initialize((CLogFile *)((char *)this + 80), v20);
  CLogFileSector::Initialize((CLogFile *)((char *)this + 120), 1u, *((_DWORD *)this + 16));
  if ( *((_QWORD *)this + 21) == -1 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 21) = EventW;
    if ( EventW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      TrkRaiseWin32Error(LastError);
    }
  }
  CLogFile::ActivateLogFile(this);
}

```

## disassembly

```asm
0x18000b5b0  mov     [rsp-8+arg_10], rbx
0x18000b5b5  push    rbp
0x18000b5b6  push    rsi
0x18000b5b7  push    r14
0x18000b5b9  lea     rbp, [rsp-200h]
0x18000b5c1  sub     rsp, 300h
0x18000b5c8  mov     rax, cs:__security_cookie
0x18000b5cf  xor     rax, rsp
0x18000b5d2  mov     [rbp+210h+var_20], rax
0x18000b5d9  xor     r14d, r14d
0x18000b5dc  xor     eax, eax
0x18000b5de  mov     [rsp+310h+FileHandle], r14
0x18000b5e3  xorps   xmm0, xmm0
0x18000b5e6  mov     qword ptr [rbp+210h+var_238], rax
0x18000b5ea  mov     rbx, r9
0x18000b5ed  mov     rsi, rcx
0x18000b5f0  movups  [rbp+210h+FsInformation], xmm0
0x18000b5f4  movups  xmmword ptr [rbp+210h+var_258], xmm0
0x18000b5f8  test    r8, r8
0x18000b5fb  jz      short loc_18000B601
0x18000b5fd  mov     [rcx+30h], r8
0x18000b601  test    rdx, rdx
0x18000b604  jz      short loc_18000B60A
0x18000b606  mov     [rcx+28h], rdx
0x18000b60a  test    rbx, rbx
0x18000b60d  jnz     loc_18000B88A
0x18000b613  movzx   eax, [rbp+210h+arg_20]
0x18000b61a  lea     rcx, [rbp+210h+DosPathName]; void *
0x18000b61e  xor     edx, edx; Val
0x18000b620  mov     [rsi+4Ch], ax
0x18000b624  mov     r8d, 20Ah; Size
0x18000b62a  call    memset_0
0x18000b62f  mov     r8, [rsi+28h]
0x18000b633  lea     r10, [rbp+210h+DosPathName]
0x18000b637  mov     r11d, 7FFFFFFEh
0x18000b63d  mov     ecx, 105h
0x18000b642  mov     eax, r11d
0x18000b645  mov     r9d, ecx
0x18000b648  test    rax, rax
0x18000b64b  jz      short loc_18000B689
0x18000b64d  movzx   edx, word ptr [r8]
0x18000b651  test    dx, dx
0x18000b654  jz      short loc_18000B684
0x18000b656  mov     [r10], dx
0x18000b65a  add     r8, 2
0x18000b65e  add     r10, 2
0x18000b662  dec     rax
0x18000b665  sub     r9, 1
0x18000b669  jnz     short loc_18000B648
0x18000b66b  mov     [r10-2], r14w
0x18000b670  xor     r9d, r9d; lpArguments
0x18000b673  xor     r8d, r8d; nNumberOfArguments
0x18000b676  xor     edx, edx; dwExceptionFlags
0x18000b678  mov     ecx, 80000005h; dwExceptionCode
0x18000b67d  call    cs:__imp_RaiseException
0x18000b683  int     3; Trap to Debugger
0x18000b684  test    r9, r9
0x18000b687  jz      short loc_18000B66B
0x18000b689  mov     [r10], r14w
0x18000b68d  lea     rax, [rbp+210h+DosPathName]
0x18000b691  cmp     [rax], r14w
0x18000b695  jz      short loc_18000B6A3
0x18000b697  add     rax, 2
0x18000b69b  sub     rcx, 1
0x18000b69f  jnz     short loc_18000B691
0x18000b6a1  jmp     short loc_18000B670
0x18000b6a3  lea     rax, [rcx+rcx]
0x18000b6a7  mov     r9d, r14d
0x18000b6aa  lea     rdx, [rbp+210h+var_26]
0x18000b6b1  sub     rdx, rax
0x18000b6b4  lea     r8, asc_180015BC8; "\\"
0x18000b6bb  test    rcx, rcx
0x18000b6be  jz      short loc_18000B6E2
0x18000b6c0  test    r11, r11
0x18000b6c3  jz      short loc_18000B6F3
0x18000b6c5  movzx   eax, word ptr [r8]
0x18000b6c9  test    ax, ax
0x18000b6cc  jz      short loc_18000B6EE
0x18000b6ce  mov     [rdx], ax
0x18000b6d1  add     r8, 2
0x18000b6d5  add     rdx, 2
0x18000b6d9  dec     r11
0x18000b6dc  sub     rcx, 1
0x18000b6e0  jnz     short loc_18000B6C0
0x18000b6e2  sub     rdx, 2
0x18000b6e6  mov     r9d, 8007007Ah
0x18000b6ec  jmp     short loc_18000B6F3
0x18000b6ee  test    rcx, rcx
0x18000b6f1  jz      short loc_18000B6E2
0x18000b6f3  mov     [rdx], r14w
0x18000b6f7  test    r9d, r9d
0x18000b6fa  js      loc_18000B670
0x18000b700  xorps   xmm0, xmm0
0x18000b703  mov     [rsp+310h+arg_8], rdi
0x18000b70b  xorps   xmm1, xmm1
0x18000b70e  mov     [rsp+310h+FileHandle], r14
0x18000b713  xor     r9d, r9d; DirectoryInfo
0x18000b716  lea     rdx, [rsp+310h+NtPathName]; NtPathName
0x18000b71b  xor     r8d, r8d; NtFileNamePart
0x18000b71e  lea     rcx, [rbp+210h+DosPathName]; DosPathName
0x18000b722  movups  xmmword ptr [rsp+310h+ObjectAttributes.Length], xmm0
0x18000b727  movups  xmmword ptr [rbp+210h+ObjectAttributes.ObjectName], xmm0
0x18000b72b  movups  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b72f  movups  xmmword ptr [rbp+210h+IoStatusBlock], xmm0
0x18000b733  movups  xmmword ptr [rsp+310h+NtPathName.Length], xmm1
0x18000b738  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18000b73e  test    al, al
0x18000b740  jz      loc_18000B8B1
0x18000b746  mov     rbx, [rsp+310h+NtPathName.Buffer]
0x18000b74b  lea     rax, [rsp+310h+NtPathName]
0x18000b750  mov     [rsp+310h+EaLength], r14d; EaLength
0x18000b755  lea     r9, [rbp+210h+IoStatusBlock]; IoStatusBlock
0x18000b759  mov     [rsp+310h+EaBuffer], r14; EaBuffer
0x18000b75e  lea     r8, [rsp+310h+ObjectAttributes]; ObjectAttributes
0x18000b763  mov     [rsp+310h+CreateOptions], 800020h; CreateOptions
0x18000b76b  lea     rcx, [rsp+310h+FileHandle]; FileHandle
0x18000b770  mov     [rsp+310h+CreateDisposition], 1; CreateDisposition
0x18000b778  xorps   xmm0, xmm0
0x18000b77b  mov     [rsp+310h+ShareAccess], 7; ShareAccess
0x18000b783  mov     edx, 100080h; DesiredAccess
0x18000b788  mov     [rsp+310h+FileAttributes], 80h; FileAttributes
0x18000b790  mov     [rsp+310h+AllocationSize], r14; AllocationSize
0x18000b795  mov     [rsp+310h+ObjectAttributes.Length], 30h ; '0'
0x18000b79d  mov     [rbp+210h+ObjectAttributes.RootDirectory], r14
0x18000b7a1  mov     [rbp+210h+ObjectAttributes.Attributes], 40h ; '@'
0x18000b7a8  mov     [rbp+210h+ObjectAttributes.ObjectName], rax
0x18000b7ac  movdqu  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b7b1  call    cs:__imp_NtCreateFile
0x18000b7b7  mov     edi, eax
0x18000b7b9  test    eax, eax
0x18000b7bb  js      loc_18000B8A0
0x18000b7c1  test    rbx, rbx
0x18000b7c4  jz      short loc_18000B7DE
0x18000b7c6  mov     rcx, gs:60h
0x18000b7cf  mov     r8, rbx; P
0x18000b7d2  xor     edx, edx; Flags
0x18000b7d4  mov     rcx, [rcx+30h]; HeapHandle
0x18000b7d8  call    cs:__imp_RtlFreeHeap
0x18000b7de  test    edi, edi
0x18000b7e0  js      loc_18000B8B6
0x18000b7e6  mov     rcx, [rsp+310h+FileHandle]; FileHandle
0x18000b7eb  lea     r8, [rbp+210h+FsInformation]; FsInformation
0x18000b7ef  mov     r9d, 18h; Length
0x18000b7f5  mov     dword ptr [rsp+310h+AllocationSize], 3; FsInformationClass
0x18000b7fd  lea     rdx, [rbp+210h+var_258]; IoStatusBlock
0x18000b801  call    cs:__imp_NtQueryVolumeInformationFile
0x18000b807  mov     rcx, [rsp+310h+FileHandle]; Handle
0x18000b80c  mov     ebx, eax
0x18000b80e  call    cs:__imp_NtClose
0x18000b814  test    ebx, ebx
0x18000b816  js      loc_18000B8C7
0x18000b81c  mov     edx, [rbp+210h+var_238+4]; unsigned int
0x18000b81f  mov     [rsi+40h], edx
0x18000b822  cmp     edx, 100h
0x18000b828  jb      loc_18000B8D8
0x18000b82e  lea     rcx, [rsi+50h]; this
0x18000b832  call    ?Initialize@CLogFileHeader@@QEAAXK@Z; CLogFileHeader::Initialize(ulong)
0x18000b837  mov     r8d, [rsi+40h]; unsigned int
0x18000b83b  lea     rcx, [rsi+78h]; this
0x18000b83f  mov     edx, 1; unsigned int
0x18000b844  call    ?Initialize@CLogFileSector@@QEAAXKK@Z; CLogFileSector::Initialize(ulong,ulong)
0x18000b849  cmp     qword ptr [rsi+0A8h], 0FFFFFFFFFFFFFFFFh
0x18000b851  jz      loc_18000B8EC
0x18000b857  mov     rcx, rsi; this
0x18000b85a  call    ?ActivateLogFile@CLogFile@@QEAAXXZ; CLogFile::ActivateLogFile(void)
0x18000b85f  mov     rdi, [rsp+310h+arg_8]
0x18000b867  mov     rcx, [rbp+210h+var_20]
0x18000b86e  xor     rcx, rsp; StackCookie
0x18000b871  call    __security_check_cookie
0x18000b876  mov     rbx, [rsp+310h+arg_10]
0x18000b87e  add     rsp, 300h
0x18000b885  pop     r14
0x18000b887  pop     rsi
0x18000b888  pop     rbp
0x18000b889  retn
0x18000b88a  mov     rcx, [rcx+38h]; this
0x18000b88e  test    rcx, rcx
0x18000b891  jnz     short loc_18000B8AA
0x18000b893  mov     [rsi+38h], rbx
0x18000b897  lock inc dword ptr [rbx+8]
0x18000b89b  jmp     loc_18000B613
0x18000b8a0  mov     [rsp+310h+FileHandle], r14
0x18000b8a5  jmp     loc_18000B7C1
0x18000b8aa  call    ?Release@PLogFileNotify@@QEAAKXZ; PLogFileNotify::Release(void)
0x18000b8af  jmp     short loc_18000B893
0x18000b8b1  mov     edi, 0C0000033h
0x18000b8b6  xor     r9d, r9d; lpArguments
0x18000b8b9  xor     r8d, r8d; nNumberOfArguments
0x18000b8bc  xor     edx, edx; dwExceptionFlags
0x18000b8be  mov     ecx, edi; dwExceptionCode
0x18000b8c0  call    cs:__imp_RaiseException
0x18000b8c6  int     3; Trap to Debugger
0x18000b8c7  xor     r9d, r9d; lpArguments
0x18000b8ca  xor     r8d, r8d; nNumberOfArguments
0x18000b8cd  xor     edx, edx; dwExceptionFlags
0x18000b8cf  mov     ecx, ebx; dwExceptionCode
0x18000b8d1  call    cs:__imp_RaiseException
0x18000b8d7  int     3; Trap to Debugger
0x18000b8d8  xor     r9d, r9d; lpArguments
0x18000b8db  xor     r8d, r8d; nNumberOfArguments
0x18000b8de  xor     edx, edx; dwExceptionFlags
0x18000b8e0  mov     ecx, 0C0000206h; dwExceptionCode
0x18000b8e5  call    cs:__imp_RaiseException
0x18000b8eb  int     3; Trap to Debugger
0x18000b8ec  xor     r9d, r9d; lpName
0x18000b8ef  xor     r8d, r8d; bInitialState
0x18000b8f2  xor     edx, edx; bManualReset
0x18000b8f4  xor     ecx, ecx; lpEventAttributes
0x18000b8f6  call    cs:__imp_CreateEventW
0x18000b8fc  mov     [rsi+0A8h], rax
0x18000b903  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b907  jnz     loc_18000B857
0x18000b90d  call    cs:__imp_GetLastError
0x18000b913  mov     ecx, eax; int
0x18000b915  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
```
