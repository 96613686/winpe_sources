# CVdsVolume::GetFsFlags(ulong *)

- ea: `0x140015b98`
- end: `0x140015dbb`
- name: `?GetFsFlags@CVdsVolume@@AEAAJPEAK@Z`
- size: `547`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140041b50`

## callees

- `0x140004460`
- `0x14000d0f0`
- `0x140015b98`
- `0x140015dd0`
- `0x14002e123`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015d4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015d4c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140015cc4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140015cc4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140015d12`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140015d12`
- `vdsutil!RemoveTempVolumeName` at `0x140015c94`
- `vdsutil!RemoveTempVolumeName` at `0x140015c94`
- `vdsutil!VdsTraceEx` at `0x140015c63`
- `vdsutil!VdsTraceEx` at `0x140015c82`
- `vdsutil!VdsTraceEx` at `0x140015d44`
- `vdsutil!VdsTraceEx` at `0x140015d69`
- `vdsutil!VdsTraceEx` at `0x140015c63`
- `vdsutil!VdsTraceEx` at `0x140015c82`
- `vdsutil!VdsTraceEx` at `0x140015d44`
- `vdsutil!VdsTraceEx` at `0x140015d69`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140015be1`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140015be1`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140015d8c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140015d8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsVolume::GetFsFlags(CVdsVolume *this, unsigned int *a2)
{
  int VolumeName; // eax
  signed int LastError; // ebx
  HANDLE FileW; // rax
  _WORD OutBuffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE hDevice; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v11[16]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v13[280]; // [rsp+270h] [rbp+170h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v11, 0x5Eu, "CVdsVolume::GetFsFlags()");
  BytesReturned = 0;
  OutBuffer[0] = 0;
  hDevice = (HANDLE)-1LL;
  *a2 = 0;
  memset_0(FileName, 0, 0x208u);
  memset_0(v13, 0, 0x224u);
  VolumeName = CVdsVolume::GetVolumeName(this, FileName, (int *)&BytesReturned, 1, 0x112u, v13);
  LastError = VolumeName;
  if ( VolumeName < 0 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::GetFsFlags, 1, hr=%lX", VolumeName);
    goto LABEL_14;
  }
  if ( VolumeName == 1 )
  {
    VdsTraceEx(94, 1, "CVdsVolume::GetFsFlags, 2, hr=%lX", 1);
    RemoveTempVolumeName(FileName);
    goto LABEL_14;
  }
  FileW = CreateFileW(FileName, 3u, 3u, 0, 3u, 0x2000000u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  CVdsHandleImpl<-1>::operator=(&hDevice, FileW);
  if ( hDevice == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    VdsTraceEx(94, 0, "CVdsVolume::SetClearFsFlags, 4, name=%s, error=%ld", (const char *)FileName, LastError);
  }
  else
  {
    BytesReturned = 0;
    if ( DeviceIoControl(hDevice, 0x9003Cu, 0, 0, OutBuffer, 2u, &BytesReturned, 0) )
    {
      if ( OutBuffer[0] )
        *a2 = 1;
      LastError = 0;
      goto LABEL_14;
    }
    LastError = GetLastError();
    VdsTraceEx(94, 0, "CVdsVolume::GetFsFlags, 3, error=%ld", LastError);
  }
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_14:
  CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&hDevice);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v11);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140015b98  mov     [rsp-8+arg_10], rbx
0x140015b9d  mov     [rsp-8+arg_18], rsi
0x140015ba2  push    rbp
0x140015ba3  push    rdi
0x140015ba4  push    r15
0x140015ba6  lea     rbp, [rsp-3B0h]
0x140015bae  sub     rsp, 4B0h
0x140015bb5  mov     rax, cs:__security_cookie
0x140015bbc  xor     rax, rsp
0x140015bbf  mov     [rbp+3C0h+var_20], rax
0x140015bc6  mov     rdi, rdx
0x140015bc9  mov     rbx, rcx
0x140015bcc  lea     r8, aCvdsvolumeGetf_9; "CVdsVolume::GetFsFlags()"
0x140015bd3  mov     r15d, 5Eh ; '^'
0x140015bd9  mov     edx, r15d
0x140015bdc  lea     rcx, [rsp+4C0h+var_470]
0x140015be1  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140015be7  nop
0x140015be8  xor     esi, esi
0x140015bea  mov     [rsp+4C0h+BytesReturned], esi
0x140015bee  mov     [rsp+4C0h+OutBuffer], si
0x140015bf3  mov     [rsp+4C0h+hDevice], 0FFFFFFFFFFFFFFFFh
0x140015bfc  mov     [rdi], esi
0x140015bfe  xor     edx, edx; Val
0x140015c00  mov     r8d, 208h; Size
0x140015c06  lea     rcx, [rsp+4C0h+FileName]; void *
0x140015c0b  call    memset_0
0x140015c10  xor     edx, edx; Val
0x140015c12  mov     r8d, 224h; Size
0x140015c18  lea     rcx, [rbp+3C0h+var_250]; void *
0x140015c1f  call    memset_0
0x140015c24  lea     rax, [rbp+3C0h+var_250]
0x140015c2b  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x140015c30  mov     [rsp+4C0h+dwCreationDisposition], 112h; unsigned int
0x140015c38  lea     r9d, [r15-5Dh]; int
0x140015c3c  lea     r8, [rsp+4C0h+BytesReturned]; int *
0x140015c41  lea     rdx, [rsp+4C0h+FileName]; unsigned __int16 *
0x140015c46  mov     rcx, rbx; this
0x140015c49  call    ?GetVolumeName@CVdsVolume@@AEAAJQEAGPEAHHKPEAG@Z; CVdsVolume::GetVolumeName(ushort * const,int *,int,ulong,ushort *)
0x140015c4e  mov     ebx, eax
0x140015c50  test    eax, eax
0x140015c52  jns     short loc_140015C6E
0x140015c54  mov     r9d, eax
0x140015c57  lea     r8, aCvdsvolumeGetf_12; "CVdsVolume::GetFsFlags, 1, hr=%lX"
0x140015c5e  xor     edx, edx
0x140015c60  mov     ecx, r15d
0x140015c63  call    cs:__imp_VdsTraceEx
0x140015c69  jmp     loc_140015D7C
0x140015c6e  cmp     ebx, 1
0x140015c71  jnz     short loc_140015C9F
0x140015c73  mov     r9d, ebx
0x140015c76  lea     r8, aCvdsvolumeGetf_14; "CVdsVolume::GetFsFlags, 2, hr=%lX"
0x140015c7d  mov     edx, ebx
0x140015c7f  mov     ecx, r15d
0x140015c82  call    cs:__imp_VdsTraceEx
0x140015c88  lea     rdx, [rbp+3C0h+var_250]
0x140015c8f  lea     rcx, [rsp+4C0h+FileName]
0x140015c94  call    cs:__imp_RemoveTempVolumeName
0x140015c9a  jmp     loc_140015D7C
0x140015c9f  mov     [rsp+4C0h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x140015ca8  mov     [rsp+4C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x140015cb0  mov     edx, 3; dwDesiredAccess
0x140015cb5  mov     [rsp+4C0h+dwCreationDisposition], edx; dwCreationDisposition
0x140015cb9  xor     r9d, r9d; lpSecurityAttributes
0x140015cbc  mov     r8d, edx; dwShareMode
0x140015cbf  lea     rcx, [rsp+4C0h+FileName]; lpFileName
0x140015cc4  call    cs:__imp_CreateFileW
0x140015cca  mov     rdx, rax
0x140015ccd  lea     rcx, [rsp+4C0h+hDevice]
0x140015cd2  call    ??4?$CVdsHandleImpl@$0?0@@QEAAPEAXPEAX@Z; CVdsHandleImpl<-1>::operator=(void *)
0x140015cd7  mov     rcx, [rsp+4C0h+hDevice]; hDevice
0x140015cdc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140015ce0  jz      short loc_140015D4C
0x140015ce2  mov     [rsp+4C0h+BytesReturned], esi
0x140015ce6  mov     [rsp+4C0h+lpOverlapped], rsi; lpOverlapped
0x140015ceb  lea     rax, [rsp+4C0h+BytesReturned]
0x140015cf0  mov     [rsp+4C0h+hTemplateFile], rax; lpBytesReturned
0x140015cf5  mov     [rsp+4C0h+dwFlagsAndAttributes], 2; nOutBufferSize
0x140015cfd  lea     rax, [rsp+4C0h+OutBuffer]
0x140015d02  mov     qword ptr [rsp+4C0h+dwCreationDisposition], rax; lpOutBuffer
0x140015d07  xor     r9d, r9d; nInBufferSize
0x140015d0a  xor     r8d, r8d; lpInBuffer
0x140015d0d  mov     edx, 9003Ch; dwIoControlCode
0x140015d12  call    cs:__imp_DeviceIoControl
0x140015d18  test    eax, eax
0x140015d1a  jz      short loc_140015D2D
0x140015d1c  cmp     [rsp+4C0h+OutBuffer], si
0x140015d21  jz      short loc_140015D29
0x140015d23  mov     dword ptr [rdi], 1
0x140015d29  mov     ebx, esi
0x140015d2b  jmp     short loc_140015D7C
0x140015d2d  call    cs:__imp_GetLastError
0x140015d33  mov     ebx, eax
0x140015d35  mov     r9d, eax
0x140015d38  lea     r8, aCvdsvolumeGetf_25; "CVdsVolume::GetFsFlags, 3, error=%ld"
0x140015d3f  xor     edx, edx
0x140015d41  mov     ecx, r15d
0x140015d44  call    cs:__imp_VdsTraceEx
0x140015d4a  jmp     short loc_140015D6F
0x140015d4c  call    cs:__imp_GetLastError
0x140015d52  mov     ebx, eax
0x140015d54  mov     [rsp+4C0h+dwCreationDisposition], eax
0x140015d58  lea     r9, [rsp+4C0h+FileName]
0x140015d5d  lea     r8, aCvdsvolumeSetc_3; "CVdsVolume::SetClearFsFlags, 4, name=%s"...
0x140015d64  xor     edx, edx
0x140015d66  mov     ecx, r15d
0x140015d69  call    cs:__imp_VdsTraceEx
0x140015d6f  test    ebx, ebx
0x140015d71  jle     short loc_140015D7C
0x140015d73  movzx   ebx, bx
0x140015d76  or      ebx, 80070000h
0x140015d7c  lea     rcx, [rsp+4C0h+hDevice]
0x140015d81  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x140015d86  nop
0x140015d87  lea     rcx, [rsp+4C0h+var_470]
0x140015d8c  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140015d92  mov     eax, ebx
0x140015d94  mov     rcx, [rbp+3C0h+var_20]
0x140015d9b  xor     rcx, rsp; StackCookie
0x140015d9e  call    __security_check_cookie
0x140015da3  lea     r11, [rsp+4C0h+var_10]
0x140015dab  mov     rbx, [r11+30h]
0x140015daf  mov     rsi, [r11+38h]
0x140015db3  mov     rsp, r11
0x140015db6  pop     r15
0x140015db8  pop     rdi
0x140015db9  pop     rbp
0x140015dba  retn
```
