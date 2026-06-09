# PfDiVolumeGetInfoHelper

- ea: `0x180007840`
- end: `0x180007a5b`
- name: `PfDiVolumeGetInfoHelper`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007cbc`

## callees

- `0x180007568`
- `0x180007840`
- `0x180007a64`
- `0x180007c78`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800079a6`
- `ntdll!NtCreateFile` at `0x1800079a6`
- `ntdll!RtlInitUnicodeString` at `0x18000792a`
- `ntdll!RtlInitUnicodeString` at `0x18000792a`
- `ntdll!RtlNtStatusToDosError` at `0x1800079b2`
- `ntdll!RtlNtStatusToDosError` at `0x1800079b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007916`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a01`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007901`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007901`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a25`

## pseudocode

```c
__int64 __fastcall PfDiVolumeGetInfoHelper(__int64 a1, __int64 a2)
{
  bool v2; // zf
  __int64 v5; // rdx
  const WCHAR *v6; // rax
  WCHAR *v7; // rsi
  unsigned int DeviceInfo; // ebx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  int v11; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v17[528]; // [rsp+C0h] [rbp-40h] BYREF

  FileHandle = (void *)-1LL;
  v2 = (*(_BYTE *)(a1 + 26) & 1) == 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  if ( v2 )
    return 1173;
  v5 = *(_QWORD *)(a1 + 16);
  if ( !v5 )
    return 1173;
  v6 = (const WCHAR *)PfScStringGet(*(_QWORD *)&PfSvcGlobals + 96LL, v5, v17);
  v7 = (WCHAR *)v6;
  if ( v6 )
  {
    if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
    {
      FileW = CreateFileW(v6, 0, 7u, 0, 3u, 0, 0);
      FileHandle = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
LABEL_8:
        DeviceInfo = LastError;
        goto LABEL_17;
      }
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, v6);
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v11 = NtCreateFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x20u, 0, 0);
      if ( v11 < 0 )
      {
        LastError = RtlNtStatusToDosError(v11);
        goto LABEL_8;
      }
      FileW = FileHandle;
    }
    DeviceInfo = PfDiVolumeGetDeviceInfo(FileW, a2);
    if ( !DeviceInfo )
    {
      if ( (*(_BYTE *)(a2 + 4) & 0x20) != 0 )
      {
        DeviceInfo = PfDiGetVolumeInfo(FileHandle, a1);
        if ( !DeviceInfo )
          *(_DWORD *)(a1 + 40) &= ~2u;
      }
      else
      {
        DeviceInfo = 21;
      }
    }
    goto LABEL_17;
  }
  DeviceInfo = 8;
LABEL_17:
  if ( FileHandle != (void *)-1LL )
    CloseHandle(FileHandle);
  if ( v7 && v7 != (WCHAR *)v17 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v7);
  return DeviceInfo;
}

```

## disassembly

```asm
0x180007840  mov     [rsp-8+arg_10], rbx
0x180007845  mov     [rsp-8+arg_18], rsi
0x18000784a  push    rbp
0x18000784b  push    rdi
0x18000784c  push    r14
0x18000784e  lea     rbp, [rsp-1E0h]
0x180007856  sub     rsp, 2E0h
0x18000785d  mov     rax, cs:__security_cookie
0x180007864  xor     rax, rsp
0x180007867  mov     [rbp+1F0h+var_20], rax
0x18000786e  xorps   xmm0, xmm0
0x180007871  mov     [rsp+2F0h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18000787a  xor     eax, eax
0x18000787c  xorps   xmm1, xmm1
0x18000787f  test    byte ptr [rcx+1Ah], 1
0x180007883  mov     r14, rdx
0x180007886  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm0
0x18000788b  mov     rdi, rcx
0x18000788e  movups  xmmword ptr [rbp+1F0h+ObjectAttributes+1Ch], xmm0
0x180007892  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm0
0x180007897  movups  xmmword ptr [rbp+1F0h+IoStatusBlock], xmm0
0x18000789b  movups  xmmword ptr [rbp+1F0h+DestinationString.Length], xmm1
0x18000789f  jz      loc_180007A2D
0x1800078a5  mov     rdx, [rcx+10h]
0x1800078a9  test    rdx, rdx
0x1800078ac  jz      loc_180007A2D
0x1800078b2  mov     rcx, cs:PfSvcGlobals
0x1800078b9  lea     r8, [rbp+1F0h+var_230]
0x1800078bd  add     rcx, 60h ; '`'
0x1800078c1  call    PfScStringGet
0x1800078c6  mov     rsi, rax
0x1800078c9  test    rax, rax
0x1800078cc  jnz     short loc_1800078D6
0x1800078ce  lea     ebx, [rax+8]
0x1800078d1  jmp     loc_1800079F6
0x1800078d6  test    byte ptr [rdi+28h], 2
0x1800078da  jz      short loc_180007923
0x1800078dc  xor     r9d, r9d; lpSecurityAttributes
0x1800078df  mov     [rsp+2F0h+hTemplateFile], 0; hTemplateFile
0x1800078e8  mov     [rsp+2F0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800078f0  xor     edx, edx; dwDesiredAccess
0x1800078f2  mov     rcx, rsi; lpFileName
0x1800078f5  mov     [rsp+2F0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800078fd  lea     r8d, [r9+7]; dwShareMode
0x180007901  call    cs:__imp_CreateFileW
0x180007907  mov     [rsp+2F0h+FileHandle], rax
0x18000790c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007910  jnz     loc_1800079C2
0x180007916  call    cs:__imp_GetLastError
0x18000791c  mov     ebx, eax
0x18000791e  jmp     loc_1800079F6
0x180007923  mov     rdx, rsi; SourceString
0x180007926  lea     rcx, [rbp+1F0h+DestinationString]; DestinationString
0x18000792a  call    cs:__imp_RtlInitUnicodeString
0x180007930  mov     [rsp+2F0h+EaLength], 0; EaLength
0x180007938  lea     rax, [rbp+1F0h+DestinationString]
0x18000793c  mov     [rsp+2F0h+EaBuffer], 0; EaBuffer
0x180007945  lea     r9, [rbp+1F0h+IoStatusBlock]; IoStatusBlock
0x180007949  mov     [rsp+2F0h+CreateOptions], 20h ; ' '; CreateOptions
0x180007951  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x180007956  mov     [rsp+2F0h+CreateDisposition], 1; CreateDisposition
0x18000795e  lea     rcx, [rsp+2F0h+FileHandle]; FileHandle
0x180007963  mov     dword ptr [rsp+2F0h+hTemplateFile], 7; ShareAccess
0x18000796b  xorps   xmm0, xmm0
0x18000796e  mov     [rsp+2F0h+dwFlagsAndAttributes], 0; FileAttributes
0x180007976  mov     edx, 100080h; DesiredAccess
0x18000797b  mov     qword ptr [rsp+2F0h+dwCreationDisposition], 0; AllocationSize
0x180007984  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x18000798c  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], 0
0x180007995  mov     [rbp+1F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000799c  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x1800079a1  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800079a6  call    cs:__imp_NtCreateFile
0x1800079ac  test    eax, eax
0x1800079ae  jns     short loc_1800079BD
0x1800079b0  mov     ecx, eax; Status
0x1800079b2  call    cs:__imp_RtlNtStatusToDosError
0x1800079b8  jmp     loc_18000791C
0x1800079bd  mov     rax, [rsp+2F0h+FileHandle]
0x1800079c2  mov     rdx, r14
0x1800079c5  mov     rcx, rax
0x1800079c8  call    PfDiVolumeGetDeviceInfo
0x1800079cd  mov     ebx, eax
0x1800079cf  test    eax, eax
0x1800079d1  jnz     short loc_1800079F6
0x1800079d3  test    byte ptr [r14+4], 20h
0x1800079d8  jnz     short loc_1800079DF
0x1800079da  lea     ebx, [rax+15h]
0x1800079dd  jmp     short loc_1800079F6
0x1800079df  mov     rcx, [rsp+2F0h+FileHandle]
0x1800079e4  mov     rdx, rdi
0x1800079e7  call    PfDiGetVolumeInfo
0x1800079ec  mov     ebx, eax
0x1800079ee  test    eax, eax
0x1800079f0  jnz     short loc_1800079F6
0x1800079f2  and     dword ptr [rdi+28h], 0FFFFFFFDh
0x1800079f6  mov     rcx, [rsp+2F0h+FileHandle]; hObject
0x1800079fb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800079ff  jz      short loc_180007A07
0x180007a01  call    cs:__imp_CloseHandle
0x180007a07  test    rsi, rsi
0x180007a0a  jz      short loc_180007A32
0x180007a0c  lea     rax, [rbp+1F0h+var_230]
0x180007a10  cmp     rsi, rax
0x180007a13  jz      short loc_180007A32
0x180007a15  mov     rcx, cs:PfSvcGlobals
0x180007a1c  mov     r8, rsi; lpMem
0x180007a1f  xor     edx, edx; dwFlags
0x180007a21  mov     rcx, [rcx+58h]; hHeap
0x180007a25  call    cs:__imp_HeapFree
0x180007a2b  jmp     short loc_180007A32
0x180007a2d  mov     ebx, 495h
0x180007a32  mov     eax, ebx
0x180007a34  mov     rcx, [rbp+1F0h+var_20]
0x180007a3b  xor     rcx, rsp; StackCookie
0x180007a3e  call    __security_check_cookie
0x180007a43  lea     r11, [rsp+2F0h+var_10]
0x180007a4b  mov     rbx, [r11+30h]
0x180007a4f  mov     rsi, [r11+38h]
0x180007a53  mov     rsp, r11
0x180007a56  pop     r14
0x180007a58  pop     rdi
0x180007a59  pop     rbp
0x180007a5a  retn
```
