# CVdsVolume::SetClearFsFlags(ulong,int)

- ea: `0x140015944`
- end: `0x140015b90`
- name: `?SetClearFsFlags@CVdsVolume@@AEAAJKH@Z`
- size: `588`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this, unsigned int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140040c60`
- `0x1400432f0`

## callees

- `0x140004460`
- `0x14000d0f0`
- `0x140015944`
- `0x140015dd0`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015aed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015aed`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140015a76`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140015a76`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140015ad0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140015ad0`
- `vdsutil!RemoveTempVolumeName` at `0x140015b2e`
- `vdsutil!RemoveTempVolumeName` at `0x140015b2e`
- `vdsutil!VdsTraceEx` at `0x140015a07`
- `vdsutil!VdsTraceEx` at `0x140015a46`
- `vdsutil!VdsTraceEx` at `0x140015b0a`
- `vdsutil!VdsTraceEx` at `0x140015b4a`
- `vdsutil!VdsTraceEx` at `0x140015a07`
- `vdsutil!VdsTraceEx` at `0x140015a46`
- `vdsutil!VdsTraceEx` at `0x140015b0a`
- `vdsutil!VdsTraceEx` at `0x140015b4a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001598f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001598f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140015a1e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140015b61`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140015a1e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140015b61`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsVolume::SetClearFsFlags(CVdsVolume *this, int a2, int a3)
{
  int VolumeName; // eax
  unsigned int v7; // edi
  signed int v9; // ebx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  const char *v12; // r8
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  __int16 InBuffer; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE hDevice; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v17[16]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v19[280]; // [rsp+270h] [rbp+170h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v17, 0x5Eu, "CVdsVolume::SetClearFsFlags()");
  BytesReturned = 0;
  hDevice = (HANDLE)-1LL;
  if ( a2 && (a2 & 0xFFFFFFFE) == 0 )
  {
    InBuffer = a3 == 1;
    VolumeName = CVdsVolume::GetVolumeName(this, FileName, (int *)&BytesReturned, 1, 0x112u, v19);
    v7 = VolumeName;
    if ( VolumeName < 0 )
    {
      VdsTraceEx(94, 0, "CVdsVolume::SetClearFsFlags, 2, hr=%lX", VolumeName);
      CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&hDevice);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
      return v7;
    }
    if ( BytesReturned == 1 )
    {
      v9 = -2147211914;
      VdsTraceEx(94, 0, "CVdsVolume::SetClearFsFlags, 3, hr=%lX", -2147211914);
      goto LABEL_14;
    }
    FileW = CreateFileW(FileName, 3u, 3u, 0, 3u, 0x2000000u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    CVdsHandleImpl<-1>::operator=(&hDevice, FileW);
    if ( hDevice == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v12 = "CVdsVolume::SetClearFsFlags, 5, name=%s, %ld";
    }
    else
    {
      BytesReturned = 0;
      if ( DeviceIoControl(hDevice, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
      {
        v9 = 0;
LABEL_14:
        if ( v7 == 1 )
          RemoveTempVolumeName(FileName);
        goto LABEL_17;
      }
      LastError = GetLastError();
      v12 = "CVdsVolume::SetClearFsFlags, 4, name=%s, %ld";
    }
    v9 = LastError;
    dwCreationDisposition[0] = LastError;
    VdsTraceEx(94, 0, v12, FileName, *(_QWORD *)dwCreationDisposition);
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_14;
  }
  v9 = -2147211936;
  VdsTraceEx(94, 0, "CVdsVolume::SetClearFsFlags, 1, hr=%lX", -2147211936);
LABEL_17:
  CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&hDevice);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140015944  mov     [rsp-8+arg_8], rbx
0x140015949  mov     [rsp-8+arg_10], rsi
0x14001594e  push    rbp
0x14001594f  push    rdi
0x140015950  push    r15
0x140015952  lea     rbp, [rsp-3B0h]
0x14001595a  sub     rsp, 4B0h
0x140015961  mov     rax, cs:__security_cookie
0x140015968  xor     rax, rsp
0x14001596b  mov     [rbp+3C0h+var_20], rax
0x140015972  mov     edi, r8d
0x140015975  mov     ebx, edx
0x140015977  mov     rsi, rcx
0x14001597a  lea     r8, aCvdsvolumeSetc_0; "CVdsVolume::SetClearFsFlags()"
0x140015981  mov     r15d, 5Eh ; '^'
0x140015987  mov     edx, r15d
0x14001598a  lea     rcx, [rsp+4C0h+var_470]
0x14001598f  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140015995  nop
0x140015996  mov     [rsp+4C0h+BytesReturned], 0
0x14001599e  mov     [rsp+4C0h+hDevice], 0FFFFFFFFFFFFFFFFh
0x1400159a7  test    ebx, ebx
0x1400159a9  jz      loc_140015B36
0x1400159af  test    ebx, 0FFFFFFFEh
0x1400159b5  jnz     loc_140015B36
0x1400159bb  xor     eax, eax
0x1400159bd  cmp     edi, 1
0x1400159c0  setz    al
0x1400159c3  mov     [rsp+4C0h+InBuffer], ax
0x1400159c8  lea     rax, [rbp+3C0h+var_250]
0x1400159cf  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1400159d4  mov     [rsp+4C0h+dwCreationDisposition], 112h; unsigned int
0x1400159dc  lea     r9d, [r15-5Dh]; int
0x1400159e0  lea     r8, [rsp+4C0h+BytesReturned]; int *
0x1400159e5  lea     rdx, [rsp+4C0h+FileName]; unsigned __int16 *
0x1400159ea  mov     rcx, rsi; this
0x1400159ed  call    ?GetVolumeName@CVdsVolume@@AEAAJQEAGPEAHHKPEAG@Z; CVdsVolume::GetVolumeName(ushort * const,int *,int,ulong,ushort *)
0x1400159f2  mov     edi, eax
0x1400159f4  test    eax, eax
0x1400159f6  jns     short loc_140015A2B
0x1400159f8  mov     r9d, eax
0x1400159fb  lea     r8, aCvdsvolumeSetc_2; "CVdsVolume::SetClearFsFlags, 2, hr=%lX"
0x140015a02  xor     edx, edx
0x140015a04  mov     ecx, r15d
0x140015a07  call    cs:__imp_VdsTraceEx
0x140015a0d  nop
0x140015a0e  lea     rcx, [rsp+4C0h+hDevice]
0x140015a13  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x140015a18  nop
0x140015a19  lea     rcx, [rsp+4C0h+var_470]
0x140015a1e  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140015a24  mov     eax, edi
0x140015a26  jmp     loc_140015B69
0x140015a2b  cmp     [rsp+4C0h+BytesReturned], 1
0x140015a30  jnz     short loc_140015A51
0x140015a32  mov     ebx, 80042576h
0x140015a37  mov     r9d, ebx
0x140015a3a  lea     r8, aCvdsvolumeSetc; "CVdsVolume::SetClearFsFlags, 3, hr=%lX"
0x140015a41  xor     edx, edx
0x140015a43  mov     ecx, r15d
0x140015a46  call    cs:__imp_VdsTraceEx
0x140015a4c  jmp     loc_140015B1D
0x140015a51  mov     [rsp+4C0h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x140015a5a  mov     [rsp+4C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x140015a62  mov     edx, 3; dwDesiredAccess
0x140015a67  mov     [rsp+4C0h+dwCreationDisposition], edx; dwCreationDisposition
0x140015a6b  xor     r9d, r9d; lpSecurityAttributes
0x140015a6e  mov     r8d, edx; dwShareMode
0x140015a71  lea     rcx, [rsp+4C0h+FileName]; lpFileName
0x140015a76  call    cs:__imp_CreateFileW
0x140015a7c  mov     rdx, rax
0x140015a7f  lea     rcx, [rsp+4C0h+hDevice]
0x140015a84  call    ??4?$CVdsHandleImpl@$0?0@@QEAAPEAXPEAX@Z; CVdsHandleImpl<-1>::operator=(void *)
0x140015a89  mov     rcx, [rsp+4C0h+hDevice]; hDevice
0x140015a8e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140015a92  jz      short loc_140015AED
0x140015a94  mov     [rsp+4C0h+BytesReturned], 0
0x140015a9c  mov     [rsp+4C0h+lpOverlapped], 0; lpOverlapped
0x140015aa5  lea     rax, [rsp+4C0h+BytesReturned]
0x140015aaa  mov     [rsp+4C0h+hTemplateFile], rax; lpBytesReturned
0x140015aaf  mov     [rsp+4C0h+dwFlagsAndAttributes], 0; nOutBufferSize
0x140015ab7  mov     qword ptr [rsp+4C0h+dwCreationDisposition], 0; lpOutBuffer
0x140015ac0  mov     r9d, 2; nInBufferSize
0x140015ac6  lea     r8, [rsp+4C0h+InBuffer]; lpInBuffer
0x140015acb  mov     edx, 9C040h; dwIoControlCode
0x140015ad0  call    cs:__imp_DeviceIoControl
0x140015ad6  test    eax, eax
0x140015ad8  jz      short loc_140015ADE
0x140015ada  xor     ebx, ebx
0x140015adc  jmp     short loc_140015B1D
0x140015ade  call    cs:__imp_GetLastError
0x140015ae4  lea     r8, aCvdsvolumeSetc_5; "CVdsVolume::SetClearFsFlags, 4, name=%s"...
0x140015aeb  jmp     short loc_140015AFA
0x140015aed  call    cs:__imp_GetLastError
0x140015af3  lea     r8, aCvdsvolumeSetc_4; "CVdsVolume::SetClearFsFlags, 5, name=%s"...
0x140015afa  mov     ebx, eax
0x140015afc  mov     [rsp+4C0h+dwCreationDisposition], eax
0x140015b00  lea     r9, [rsp+4C0h+FileName]
0x140015b05  xor     edx, edx
0x140015b07  mov     ecx, r15d
0x140015b0a  call    cs:__imp_VdsTraceEx
0x140015b10  test    ebx, ebx
0x140015b12  jle     short loc_140015B1D
0x140015b14  movzx   ebx, bx
0x140015b17  or      ebx, 80070000h
0x140015b1d  cmp     edi, 1
0x140015b20  jnz     short loc_140015B51
0x140015b22  lea     rdx, [rbp+3C0h+var_250]
0x140015b29  lea     rcx, [rsp+4C0h+FileName]
0x140015b2e  call    cs:__imp_RemoveTempVolumeName
0x140015b34  jmp     short loc_140015B51
0x140015b36  mov     ebx, 80042560h
0x140015b3b  mov     r9d, ebx
0x140015b3e  lea     r8, aCvdsvolumeSetc_1; "CVdsVolume::SetClearFsFlags, 1, hr=%lX"
0x140015b45  xor     edx, edx
0x140015b47  mov     ecx, r15d
0x140015b4a  call    cs:__imp_VdsTraceEx
0x140015b50  nop
0x140015b51  lea     rcx, [rsp+4C0h+hDevice]
0x140015b56  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x140015b5b  nop
0x140015b5c  lea     rcx, [rsp+4C0h+var_470]
0x140015b61  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140015b67  mov     eax, ebx
0x140015b69  mov     rcx, [rbp+3C0h+var_20]
0x140015b70  xor     rcx, rsp; StackCookie
0x140015b73  call    __security_check_cookie
0x140015b78  lea     r11, [rsp+4C0h+var_10]
0x140015b80  mov     rbx, [r11+28h]
0x140015b84  mov     rsi, [r11+30h]
0x140015b88  mov     rsp, r11
0x140015b8b  pop     r15
0x140015b8d  pop     rdi
0x140015b8e  pop     rbp
0x140015b8f  retn
```
