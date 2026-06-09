# WinSAT::StorageDevice::PreCopyOnWriteFile(ushort const *)

- ea: `0x140061f60`
- end: `0x140062204`
- name: `?PreCopyOnWriteFile@StorageDevice@WinSAT@@AEAAKPEBG@Z`
- size: `676`
- prototype: `__int64 __fastcall(WinSAT::StorageDevice *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x140061600`

## callees

- `0x1400033c8`
- `0x140061f60`
- `0x140113220`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x140062119`
- `KERNEL32!DeviceIoControl` at `0x1400621ac`
- `KERNEL32!DeviceIoControl` at `0x140062119`
- `KERNEL32!DeviceIoControl` at `0x1400621ac`
- `KERNEL32!CreateFileW` at `0x140062087`
- `KERNEL32!CreateFileW` at `0x1400620be`
- `KERNEL32!CreateFileW` at `0x140062087`
- `KERNEL32!CreateFileW` at `0x1400620be`
- `KERNEL32!CloseHandle` at `0x1400621c6`
- `KERNEL32!CloseHandle` at `0x1400621d5`
- `KERNEL32!CloseHandle` at `0x1400621c6`
- `KERNEL32!CloseHandle` at `0x1400621d5`
- `KERNEL32!GetLastError` at `0x140061fdf`
- `KERNEL32!GetLastError` at `0x1400620cd`
- `KERNEL32!GetLastError` at `0x140062123`
- `KERNEL32!GetLastError` at `0x140061fdf`
- `KERNEL32!GetLastError` at `0x1400620cd`
- `KERNEL32!GetLastError` at `0x140062123`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x140061ffa`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x140061ffa`
- `KERNEL32!GetVolumePathNameW` at `0x140061fd5`
- `KERNEL32!GetVolumePathNameW` at `0x140061fd5`
- `KERNEL32!GetDiskFreeSpaceW` at `0x14006204f`
- `KERNEL32!GetDiskFreeSpaceW` at `0x14006204f`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall WinSAT::StorageDevice::PreCopyOnWriteFile(WinSAT::StorageDevice *this, const unsigned __int16 *a2)
{
  DWORD LastError; // ebx
  __int64 v4; // rax
  unsigned __int64 v5; // rcx
  DWORD v6; // ebx
  HANDLE v7; // rsi
  HANDLE FileW; // rdi
  DWORD BytesPerSector; // [rsp+40h] [rbp-C0h] BYREF
  DWORD SectorsPerCluster; // [rsp+44h] [rbp-BCh] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-B8h] BYREF
  __int64 InBuffer; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v14; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h]
  __int128 OutBuffer; // [rsp+70h] [rbp-90h] BYREF
  __int128 v17; // [rsp+80h] [rbp-80h]
  WCHAR szVolumeName[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  SectorsPerCluster = 0;
  BytesPerSector = 0;
  InBuffer = 0;
  BytesReturned = 0;
  v15 = 0;
  OutBuffer = 0;
  v17 = 0;
  v14 = 0;
  if ( !GetVolumePathNameW(a2, szVolumePathName, 0x104u)
    || !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    return GetLastError();
  }
  v4 = -1;
  do
    ++v4;
  while ( szVolumeName[v4] );
  if ( v4 )
  {
    v5 = 2 * v4 - 2;
    if ( v5 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v5) = 0;
  }
  if ( GetDiskFreeSpaceW(szVolumePathName, &SectorsPerCluster, &BytesPerSector, 0, 0)
    && (v6 = SectorsPerCluster * BytesPerSector,
        v7 = CreateFileW(szVolumeName, 0xC0000000, 3u, 0, 3u, 0x80u, 0),
        v7 != (HANDLE)-1LL) )
  {
    FileW = CreateFileW(a2, 0xC0000000, 7u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      for ( InBuffer = 0;
            (DeviceIoControl(FileW, 0x90073u, &InBuffer, 8u, &OutBuffer, 0x20u, &BytesReturned, 0)
          || GetLastError() == 234)
         && (_DWORD)OutBuffer;
            InBuffer = v17 )
      {
        if ( *((_QWORD *)&v17 + 1) != -1 )
        {
          *((_QWORD *)&v14 + 1) = v6 * (InBuffer + *((_QWORD *)&v17 + 1) - *((_QWORD *)&OutBuffer + 1));
          *(_QWORD *)&v14 = 0x100000002LL;
          v15 = v6 * (v17 - InBuffer);
          DeviceIoControl(v7, 0x56C04Cu, &v14, 0x18u, 0, 0, &BytesReturned, 0);
        }
      }
      LastError = 0;
    }
    CloseHandle(v7);
    if ( FileW != (HANDLE)-1LL )
      CloseHandle(FileW);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x140061f60  mov     [rsp-8+arg_0], rbx
0x140061f65  mov     [rsp-8+arg_10], rsi
0x140061f6a  push    rbp
0x140061f6b  push    rdi
0x140061f6c  push    r14
0x140061f6e  lea     rbp, [rsp-3C0h]
0x140061f76  sub     rsp, 4C0h
0x140061f7d  mov     rax, cs:__security_cookie
0x140061f84  xor     rax, rsp
0x140061f87  mov     [rbp+3D0h+var_20], rax
0x140061f8e  xor     r14d, r14d
0x140061f91  mov     rdi, rdx
0x140061f94  xorps   xmm0, xmm0
0x140061f97  mov     [rsp+4D0h+SectorsPerCluster], r14d
0x140061f9c  xorps   xmm1, xmm1
0x140061f9f  mov     [rsp+4D0h+BytesPerSector], r14d
0x140061fa4  xor     eax, eax
0x140061fa6  mov     [rsp+4D0h+InBuffer], r14
0x140061fab  mov     ebx, 104h
0x140061fb0  mov     [rsp+4D0h+BytesReturned], r14d
0x140061fb5  mov     r8d, ebx; cchBufferLength
0x140061fb8  mov     [rsp+4D0h+var_468], rax
0x140061fbd  mov     rcx, rdi; lpszFileName
0x140061fc0  lea     rdx, [rbp+3D0h+szVolumePathName]; lpszVolumePathName
0x140061fc7  movups  [rsp+4D0h+OutBuffer], xmm0
0x140061fcc  movups  [rbp+3D0h+var_450], xmm0
0x140061fd0  movups  [rsp+4D0h+var_478], xmm1
0x140061fd5  call    cs:__imp_GetVolumePathNameW
0x140061fdb  test    eax, eax
0x140061fdd  jnz     short loc_140061FEC
0x140061fdf  call    cs:__imp_GetLastError
0x140061fe5  mov     ebx, eax
0x140061fe7  jmp     loc_1400621DB
0x140061fec  mov     r8d, ebx; cchBufferLength
0x140061fef  lea     rdx, [rbp+3D0h+szVolumeName]; lpszVolumeName
0x140061ff3  lea     rcx, [rbp+3D0h+szVolumePathName]; lpszVolumeMountPoint
0x140061ffa  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x140062000  test    eax, eax
0x140062002  jz      short loc_140061FDF
0x140062004  lea     rcx, [rbp+3D0h+szVolumeName]
0x140062008  or      rax, 0FFFFFFFFFFFFFFFFh
0x14006200c  inc     rax
0x14006200f  cmp     [rcx+rax*2], r14w
0x140062014  jnz     short loc_14006200C
0x140062016  test    rax, rax
0x140062019  jz      short loc_140062036
0x14006201b  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x140062023  cmp     rcx, 208h
0x14006202a  jnb     loc_1400620DA
0x140062030  mov     [rbp+rcx+3D0h+szVolumeName], r14w
0x140062036  xor     r9d, r9d; lpNumberOfFreeClusters
0x140062039  mov     [rsp+4D0h+lpTotalNumberOfClusters], r14; lpTotalNumberOfClusters
0x14006203e  lea     r8, [rsp+4D0h+BytesPerSector]; lpBytesPerSector
0x140062043  lea     rdx, [rsp+4D0h+SectorsPerCluster]; lpSectorsPerCluster
0x140062048  lea     rcx, [rbp+3D0h+szVolumePathName]; lpRootPathName
0x14006204f  call    cs:__imp_GetDiskFreeSpaceW
0x140062055  test    eax, eax
0x140062057  jz      short loc_140061FDF
0x140062059  mov     ebx, [rsp+4D0h+BytesPerSector]
0x14006205d  lea     rcx, [rbp+3D0h+szVolumeName]; lpFileName
0x140062061  imul    ebx, [rsp+4D0h+SectorsPerCluster]
0x140062066  xor     r9d, r9d; lpSecurityAttributes
0x140062069  mov     [rsp+4D0h+hTemplateFile], r14; hTemplateFile
0x14006206e  mov     edx, 0C0000000h; dwDesiredAccess
0x140062073  mov     [rsp+4D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14006207b  mov     dword ptr [rsp+4D0h+lpTotalNumberOfClusters], 3; dwCreationDisposition
0x140062083  lea     r8d, [r9+3]; dwShareMode
0x140062087  call    cs:__imp_CreateFileW
0x14006208d  mov     rsi, rax
0x140062090  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140062094  jz      loc_140061FDF
0x14006209a  xor     r9d, r9d; lpSecurityAttributes
0x14006209d  mov     [rsp+4D0h+hTemplateFile], r14; hTemplateFile
0x1400620a2  mov     [rsp+4D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400620aa  mov     edx, 0C0000000h; dwDesiredAccess
0x1400620af  mov     rcx, rdi; lpFileName
0x1400620b2  mov     dword ptr [rsp+4D0h+lpTotalNumberOfClusters], 3; dwCreationDisposition
0x1400620ba  lea     r8d, [r9+7]; dwShareMode
0x1400620be  call    cs:__imp_CreateFileW
0x1400620c4  mov     rdi, rax
0x1400620c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400620cb  jnz     short loc_1400620E0
0x1400620cd  call    cs:__imp_GetLastError
0x1400620d3  mov     ebx, eax
0x1400620d5  jmp     loc_1400621C3
0x1400620da  call    __report_rangecheckfailure
0x1400620e0  mov     [rsp+4D0h+InBuffer], r14
0x1400620e5  mov     [rsp+4D0h+lpOverlapped], r14; lpOverlapped
0x1400620ea  lea     rax, [rsp+4D0h+BytesReturned]
0x1400620ef  mov     [rsp+4D0h+hTemplateFile], rax; lpBytesReturned
0x1400620f4  lea     r8, [rsp+4D0h+InBuffer]; lpInBuffer
0x1400620f9  lea     rax, [rsp+4D0h+OutBuffer]
0x1400620fe  mov     [rsp+4D0h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x140062106  mov     r9d, 8; nInBufferSize
0x14006210c  mov     [rsp+4D0h+lpTotalNumberOfClusters], rax; lpOutBuffer
0x140062111  mov     edx, 90073h; dwIoControlCode
0x140062116  mov     rcx, rdi; hDevice
0x140062119  call    cs:__imp_DeviceIoControl
0x14006211f  test    eax, eax
0x140062121  jnz     short loc_140062134
0x140062123  call    cs:__imp_GetLastError
0x140062129  cmp     eax, 0EAh
0x14006212e  jnz     loc_1400621C0
0x140062134  cmp     dword ptr [rsp+4D0h+OutBuffer], r14d
0x140062139  jz      loc_1400621C0
0x14006213f  mov     rax, qword ptr [rbp+3D0h+var_450+8]
0x140062143  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140062147  jz      short loc_1400621B2
0x140062149  sub     rax, qword ptr [rsp+4D0h+OutBuffer+8]
0x14006214e  lea     r8, [rsp+4D0h+var_478]; lpInBuffer
0x140062153  add     rax, [rsp+4D0h+InBuffer]
0x140062158  mov     r9d, 18h; nInBufferSize
0x14006215e  mov     ecx, ebx
0x140062160  mov     edx, 56C04Ch; dwIoControlCode
0x140062165  imul    rax, rcx
0x140062169  mov     [rsp+4D0h+lpOverlapped], r14; lpOverlapped
0x14006216e  mov     qword ptr [rsp+4D0h+var_478+8], rax
0x140062173  mov     rax, qword ptr [rbp+3D0h+var_450]
0x140062177  sub     rax, [rsp+4D0h+InBuffer]
0x14006217c  imul    rax, rcx
0x140062180  mov     rcx, rsi; hDevice
0x140062183  mov     dword ptr [rsp+4D0h+var_478], 2
0x14006218b  mov     [rsp+4D0h+var_468], rax
0x140062190  lea     rax, [rsp+4D0h+BytesReturned]
0x140062195  mov     [rsp+4D0h+hTemplateFile], rax; lpBytesReturned
0x14006219a  mov     [rsp+4D0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x14006219f  mov     [rsp+4D0h+lpTotalNumberOfClusters], r14; lpOutBuffer
0x1400621a4  mov     dword ptr [rsp+4D0h+var_478+4], 1
0x1400621ac  call    cs:__imp_DeviceIoControl
0x1400621b2  mov     rax, qword ptr [rbp+3D0h+var_450]
0x1400621b6  mov     [rsp+4D0h+InBuffer], rax
0x1400621bb  jmp     loc_1400620E5
0x1400621c0  mov     ebx, r14d
0x1400621c3  mov     rcx, rsi; hObject
0x1400621c6  call    cs:__imp_CloseHandle
0x1400621cc  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400621d0  jz      short loc_1400621DB
0x1400621d2  mov     rcx, rdi; hObject
0x1400621d5  call    cs:__imp_CloseHandle
0x1400621db  mov     eax, ebx
0x1400621dd  mov     rcx, [rbp+3D0h+var_20]
0x1400621e4  xor     rcx, rsp; StackCookie
0x1400621e7  call    __security_check_cookie
0x1400621ec  lea     r11, [rsp+4D0h+var_10]
0x1400621f4  mov     rbx, [r11+20h]
0x1400621f8  mov     rsi, [r11+30h]
0x1400621fc  mov     rsp, r11
0x1400621ff  pop     r14
0x140062201  pop     rdi
0x140062202  pop     rbp
0x140062203  retn
```
