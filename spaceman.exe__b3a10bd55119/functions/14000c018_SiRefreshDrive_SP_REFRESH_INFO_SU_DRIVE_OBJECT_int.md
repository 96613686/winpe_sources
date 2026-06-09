# SiRefreshDrive(_SP_REFRESH_INFO *,_SU_DRIVE_OBJECT *,int)

- ea: `0x14000c018`
- end: `0x14000c22a`
- name: `?SiRefreshDrive@@YAHPEAU_SP_REFRESH_INFO@@PEAU_SU_DRIVE_OBJECT@@H@Z`
- size: `530`
- prototype: `__int64 __fastcall(struct _SP_REFRESH_INFO *, struct _SU_DRIVE_OBJECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140005c20`

## callees

- `0x1400090b0`
- `0x14000aaa4`
- `0x14000c018`
- `0x14000d1be`
- `0x14000d1f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c1de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c1ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c1de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c1ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c18c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c19e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c18c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c19e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000c120`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000c168`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000c120`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000c168`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000c0cb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000c0cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c1f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c1f2`

## string_xrefs

- `0x14000c0dc`: `CreateFile`
- `0x14000c12c`: `SiUpdateProperties`

## pseudocode

```c
__int64 __fastcall SiRefreshDrive(struct _SP_REFRESH_INFO *a1, struct _SU_DRIVE_OBJECT *a2)
{
  __int64 FileW; // rsi
  __int128 v5; // xmm1
  unsigned int v6; // ebx
  const char *v7; // rdi
  DWORD v8; // r14d
  DWORD LastError; // eax
  int v10; // r8d
  int v11; // r9d
  DWORD BytesReturned; // [rsp+40h] [rbp-49h] BYREF
  DWORD v14; // [rsp+44h] [rbp-45h] BYREF
  _OWORD InBuffer[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v16; // [rsp+68h] [rbp-21h]
  WCHAR FileName[32]; // [rsp+70h] [rbp-19h] BYREF

  v14 = 0;
  FileW = -1;
  memset_0(FileName, 0, sizeof(FileName));
  v5 = *((_OWORD *)a1 + 1);
  InBuffer[0] = *(_OWORD *)a1;
  v16 = *((_QWORD *)a1 + 4);
  InBuffer[1] = v5;
  if ( BYTE4(v16) && *((_DWORD *)a2 + 28) != -1 )
  {
    StringCchPrintfW(FileName, 0x20u, L"\\\\.\\PhysicalDrive%d");
    FileW = (__int64)CreateFileW(FileName, 0xC0000000, 7u, 0, 3u, 0x80u, 0);
    if ( FileW == -1 )
    {
      v6 = 0;
      v7 = "CreateFile";
      goto LABEL_13;
    }
    BytesReturned = 0;
    v6 = DeviceIoControl((HANDLE)FileW, 0x70140u, 0, 0, 0, 0, &BytesReturned, 0);
    if ( !v6 )
    {
      v7 = "SiUpdateProperties";
      goto LABEL_13;
    }
    BYTE4(v16) = 0;
  }
  v8 = 0;
  v6 = DeviceIoControl(Spaceport, 0xE7041Cu, InBuffer, InBuffer[0], 0, 0, &v14, 0);
  if ( v6 )
    goto LABEL_16;
  if ( GetLastError() == 1167 || GetLastError() == 55 || GetLastError() == 2 )
  {
    SetLastError(0);
    v6 = 1;
    goto LABEL_16;
  }
  v7 = "DeviceIoControl - IOCTL_SPACEPORT_REFRESH_DRIVE";
LABEL_13:
  LastError = GetLastError();
  v8 = LastError;
  if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 2) != 0 )
    McTemplateK0zsjsq_EventWriteTransfer(
      (_DWORD)a2 + 56,
      (unsigned int)RefreshDriveFailed,
      v10,
      v11,
      (__int64)"SiRefreshDrive",
      (__int64)a2 + 56,
      (__int64)v7,
      LastError);
LABEL_16:
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( !v6 )
    SetLastError(v8);
  return v6;
}

```

## disassembly

```asm
0x14000c018  mov     [rsp-8+arg_10], rbx
0x14000c01d  push    rbp
0x14000c01e  push    rsi
0x14000c01f  push    rdi
0x14000c020  push    r14
0x14000c022  push    r15
0x14000c024  lea     rbp, [rsp-37h]
0x14000c029  sub     rsp, 0C0h
0x14000c030  mov     rax, cs:__security_cookie
0x14000c037  xor     rax, rsp
0x14000c03a  mov     [rbp+57h+var_30], rax
0x14000c03e  mov     r15, rdx
0x14000c041  mov     [rbp+57h+var_9C], 0
0x14000c048  mov     rbx, rcx
0x14000c04b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000c04f  xor     edx, edx; Val
0x14000c051  lea     rcx, [rbp+57h+FileName]; void *
0x14000c055  lea     r8d, [rsi+41h]; Size
0x14000c059  call    memset_0
0x14000c05e  movups  xmm0, xmmword ptr [rbx]
0x14000c061  movups  xmm1, xmmword ptr [rbx+10h]
0x14000c065  movups  [rbp+57h+InBuffer], xmm0
0x14000c069  movsd   xmm0, qword ptr [rbx+20h]
0x14000c06e  movsd   [rbp+57h+var_78], xmm0
0x14000c073  cmp     byte ptr [rbp+57h+var_78+4], 0
0x14000c077  movups  [rbp+57h+var_88], xmm1
0x14000c07b  jz      loc_14000C139
0x14000c081  mov     r9d, [r15+70h]
0x14000c085  cmp     r9d, 0FFFFFFFFh
0x14000c089  jz      loc_14000C139
0x14000c08f  lea     r8, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x14000c096  lea     edx, [rsi+21h]; unsigned __int64
0x14000c099  lea     rcx, [rbp+57h+FileName]; unsigned __int16 *
0x14000c09d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000c0a2  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x14000c0ab  lea     r8d, [rsi+8]; dwShareMode
0x14000c0af  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000c0b7  lea     rcx, [rbp+57h+FileName]; lpFileName
0x14000c0bb  xor     r9d, r9d; lpSecurityAttributes
0x14000c0be  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x14000c0c6  mov     edx, 0C0000000h; dwDesiredAccess
0x14000c0cb  call    cs:__imp_CreateFileW
0x14000c0d1  mov     rsi, rax
0x14000c0d4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000c0d8  jnz     short loc_14000C0E8
0x14000c0da  xor     ebx, ebx
0x14000c0dc  lea     rdi, aCreatefile; "CreateFile"
0x14000c0e3  jmp     loc_14000C19E
0x14000c0e8  mov     [rsp+0E0h+lpOverlapped], 0; lpOverlapped
0x14000c0f1  lea     rax, [rbp+57h+BytesReturned]
0x14000c0f5  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x14000c0fa  xor     r9d, r9d; nInBufferSize
0x14000c0fd  mov     [rsp+0E0h+dwFlagsAndAttributes], 0; nOutBufferSize
0x14000c105  xor     r8d, r8d; lpInBuffer
0x14000c108  mov     edx, 70140h; dwIoControlCode
0x14000c10d  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOutBuffer
0x14000c116  mov     rcx, rsi; hDevice
0x14000c119  mov     [rbp+57h+BytesReturned], 0
0x14000c120  call    cs:__imp_DeviceIoControl
0x14000c126  mov     ebx, eax
0x14000c128  test    eax, eax
0x14000c12a  jnz     short loc_14000C135
0x14000c12c  lea     rdi, aSiupdateproper; "SiUpdateProperties"
0x14000c133  jmp     short loc_14000C19E
0x14000c135  mov     byte ptr [rbp+57h+var_78+4], 0
0x14000c139  mov     r9d, dword ptr [rbp+57h+InBuffer]; nInBufferSize
0x14000c13d  lea     rax, [rbp+57h+var_9C]
0x14000c141  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x14000c148  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x14000c14c  xor     r14d, r14d
0x14000c14f  mov     edx, 0E7041Ch; dwIoControlCode
0x14000c154  mov     [rsp+0E0h+lpOverlapped], r14; lpOverlapped
0x14000c159  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x14000c15e  mov     [rsp+0E0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x14000c163  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r14; lpOutBuffer
0x14000c168  call    cs:__imp_DeviceIoControl
0x14000c16e  mov     ebx, eax
0x14000c170  test    eax, eax
0x14000c172  jnz     short loc_14000C1E9
0x14000c174  call    cs:__imp_GetLastError
0x14000c17a  cmp     eax, 48Fh
0x14000c17f  jz      short loc_14000C1DC
0x14000c181  call    cs:__imp_GetLastError
0x14000c187  cmp     eax, 37h ; '7'
0x14000c18a  jz      short loc_14000C1DC
0x14000c18c  call    cs:__imp_GetLastError
0x14000c192  cmp     eax, 2
0x14000c195  jz      short loc_14000C1DC
0x14000c197  lea     rdi, aDeviceiocontro; "DeviceIoControl - IOCTL_SPACEPORT_REFRE"...
0x14000c19e  call    cs:__imp_GetLastError
0x14000c1a4  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 2
0x14000c1ab  mov     r14d, eax
0x14000c1ae  jz      short loc_14000C1E9
0x14000c1b0  mov     dword ptr [rsp+0E0h+lpOverlapped], eax
0x14000c1b4  lea     rcx, [r15+38h]
0x14000c1b8  mov     [rsp+0E0h+hTemplateFile], rdi
0x14000c1bd  lea     rax, aSirefreshdrive; "SiRefreshDrive"
0x14000c1c4  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rcx
0x14000c1c9  lea     rdx, RefreshDriveFailed
0x14000c1d0  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax
0x14000c1d5  call    McTemplateK0zsjsq_EventWriteTransfer
0x14000c1da  jmp     short loc_14000C1E9
0x14000c1dc  xor     ecx, ecx; dwErrCode
0x14000c1de  call    cs:__imp_SetLastError
0x14000c1e4  mov     ebx, 1
0x14000c1e9  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000c1ed  jz      short loc_14000C1F8
0x14000c1ef  mov     rcx, rsi; hObject
0x14000c1f2  call    cs:__imp_CloseHandle
0x14000c1f8  test    ebx, ebx
0x14000c1fa  jnz     short loc_14000C205
0x14000c1fc  mov     ecx, r14d; dwErrCode
0x14000c1ff  call    cs:__imp_SetLastError
0x14000c205  mov     eax, ebx
0x14000c207  mov     rcx, [rbp+57h+var_30]
0x14000c20b  xor     rcx, rsp; StackCookie
0x14000c20e  call    __security_check_cookie
0x14000c213  mov     rbx, [rsp+0E0h+arg_10]
0x14000c21b  add     rsp, 0C0h
0x14000c222  pop     r15
0x14000c224  pop     r14
0x14000c226  pop     rdi
0x14000c227  pop     rsi
0x14000c228  pop     rbp
0x14000c229  retn
```
