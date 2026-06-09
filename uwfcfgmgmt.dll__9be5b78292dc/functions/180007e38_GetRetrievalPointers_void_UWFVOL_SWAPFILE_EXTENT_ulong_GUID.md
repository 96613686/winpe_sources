# GetRetrievalPointers(void *,_UWFVOL_SWAPFILE_EXTENT * *,ulong *,_GUID *)

- ea: `0x180007e38`
- end: `0x180008157`
- name: `?GetRetrievalPointers@@YAJPEAXPEAPEAU_UWFVOL_SWAPFILE_EXTENT@@PEAKPEAU_GUID@@@Z`
- size: `799`
- prototype: `signed int __fastcall(HANDLE hDevice, struct _UWFVOL_SWAPFILE_EXTENT **, unsigned int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path`

## callers

- `0x18000a3ac`

## callees

- `0x180002468`
- `0x1800075f4`
- `0x180007e38`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `msvcrt!malloc` at `0x180008077`
- `msvcrt!malloc` at `0x180008077`
- `msvcrt!free` at `0x180008088`
- `msvcrt!free` at `0x1800080fa`
- `msvcrt!free` at `0x180008088`
- `msvcrt!free` at `0x1800080fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007eaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000801f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007eaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000801f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000803b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008126`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000803b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008126`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007fa5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008015`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007fa5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008015`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x180007f1f`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x180007f1f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007f65`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007f65`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180007ea5`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180007ea5`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180007ee8`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180007ee8`

## pseudocode

```c
signed int __fastcall GetRetrievalPointers(
        HANDLE hDevice,
        struct _UWFVOL_SWAPFILE_EXTENT **a2,
        unsigned int *a3,
        struct _GUID *a4)
{
  unsigned int v8; // ebx
  signed int result; // eax
  WCHAR v10; // ax
  char *FileW; // rbx
  signed int v12; // eax
  unsigned int v13; // edi
  signed int v14; // eax
  unsigned int v15; // edx
  unsigned int v16; // r9d
  _QWORD *v17; // rbx
  int v18; // edi
  struct _UWFVOL_SWAPFILE_EXTENT *v19; // r8
  unsigned int v20; // r9d
  __int64 v21; // r10
  __int64 v22; // rcx
  __int64 v23; // rdx
  signed int LastError; // eax
  unsigned int *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  DWORD TotalNumberOfClusters; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesPerSector; // [rsp+44h] [rbp-BCh] BYREF
  DWORD SectorsPerCluster; // [rsp+48h] [rbp-B8h] BYREF
  void *Block; // [rsp+50h] [rbp-B0h] BYREF
  __int64 OutBuffer; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR szFilePath[264]; // [rsp+280h] [rbp+180h] BYREF

  OutBuffer = 0;
  memset_0(szFilePath, 0, 0x208u);
  v8 = 259;
  if ( !GetFinalPathNameByHandleW(hDevice, szFilePath, 0x103u, 0) )
    goto LABEL_2;
  memset_0(szVolumePathName, 0, 0x208u);
  if ( !GetVolumePathNameW(szFilePath, szVolumePathName, 0x103u) )
    goto LABEL_2;
  SectorsPerCluster = 0;
  BytesPerSector = 0;
  TotalNumberOfClusters = 0;
  if ( !GetDiskFreeSpaceW(
          szVolumePathName,
          &SectorsPerCluster,
          &BytesPerSector,
          &TotalNumberOfClusters,
          &TotalNumberOfClusters) )
    goto LABEL_2;
  while ( 1 )
  {
    v10 = szVolumePathName[v8];
    if ( v10 )
      break;
    if ( (--v8 & 0x80000000) != 0 )
      goto LABEL_8;
  }
  if ( v10 == 92 )
  {
    if ( 2 * (unsigned __int64)v8 >= 0x208 )
      _report_rangecheckfailure();
    szVolumePathName[v8] = 0;
  }
LABEL_8:
  FileW = (char *)CreateFileW(szVolumePathName, 0x80000000, 7u, 0, 3u, 0, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return v13;
    goto LABEL_29;
  }
  if ( !DeviceIoControl(FileW, 0x90234u, 0, 0, &OutBuffer, 8u, 0, 0) )
  {
    v12 = GetLastError();
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
LABEL_29:
    CloseHandle(FileW);
    return v13;
  }
  if ( a4 && !DeviceIoControl(FileW, 0x4D0018u, 0, 0, a4, 0x10u, 0, 0) )
  {
    v14 = GetLastError();
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    v13 = v14;
    goto LABEL_29;
  }
  CloseHandle(FileW);
  v31 = 0;
  Block = 0;
  if ( DeviceIoControlWithAlloc(hDevice, v15, &v31, v16, &Block, dwFlagsAndAttributes) )
  {
    v17 = Block;
    v18 = *(_DWORD *)Block;
    v19 = (struct _UWFVOL_SWAPFILE_EXTENT *)malloc(16LL * *(unsigned int *)Block);
    if ( v19 )
    {
      v20 = 0;
      v21 = SectorsPerCluster * BytesPerSector;
      v22 = v17[1];
      if ( v18 )
      {
        do
        {
          v23 = v20++;
          v23 *= 16;
          *(_QWORD *)((char *)v19 + v23) = v21 * (*(_QWORD *)((char *)v17 + v23 + 16) - v22);
          *(_QWORD *)((char *)v19 + v23 + 8) = OutBuffer + *(_QWORD *)((char *)Block + v23 + 24) * v21;
          v17 = Block;
          v22 = *(_QWORD *)((char *)Block + v23 + 16);
        }
        while ( v20 < *(_DWORD *)Block );
      }
      *a2 = v19;
      *a3 = *(_DWORD *)v17;
      free(v17);
      return 0;
    }
    else
    {
      free(v17);
      return -2147024882;
    }
  }
  else
  {
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180007e38  push    rbp
0x180007e3a  push    rbx
0x180007e3b  push    rsi
0x180007e3c  push    rdi
0x180007e3d  push    r12
0x180007e3f  push    r13
0x180007e41  push    r14
0x180007e43  push    r15
0x180007e45  lea     rbp, [rsp-3A8h]
0x180007e4d  sub     rsp, 4A8h
0x180007e54  mov     rax, cs:__security_cookie
0x180007e5b  xor     rax, rsp
0x180007e5e  mov     [rbp+3E0h+var_50], rax
0x180007e65  mov     r15, r8
0x180007e68  mov     r14, rdx
0x180007e6b  mov     rsi, rcx
0x180007e6e  mov     r13d, 208h
0x180007e74  xor     r12d, r12d
0x180007e77  lea     rcx, [rbp+3E0h+szFilePath]; void *
0x180007e7e  mov     r8d, r13d; Size
0x180007e81  mov     [rsp+4E0h+OutBuffer], r12
0x180007e86  xor     edx, edx; Val
0x180007e88  mov     rdi, r9
0x180007e8b  call    memset_0
0x180007e90  mov     ebx, 103h
0x180007e95  lea     rdx, [rbp+3E0h+szFilePath]; lpszFilePath
0x180007e9c  mov     r8d, ebx; cchFilePath
0x180007e9f  xor     r9d, r9d; dwFlags
0x180007ea2  mov     rcx, rsi; hFile
0x180007ea5  call    cs:__imp_GetFinalPathNameByHandleW
0x180007eab  test    eax, eax
0x180007ead  jnz     short loc_180007ECA
0x180007eaf  call    cs:__imp_GetLastError
0x180007eb5  test    eax, eax
0x180007eb7  jle     loc_18000812E
0x180007ebd  movzx   eax, ax
0x180007ec0  or      eax, 80070000h
0x180007ec5  jmp     loc_18000812E
0x180007eca  mov     r8, r13; Size
0x180007ecd  lea     rcx, [rsp+4E0h+szVolumePathName]; void *
0x180007ed2  xor     edx, edx; Val
0x180007ed4  call    memset_0
0x180007ed9  mov     r8d, ebx; cchBufferLength
0x180007edc  lea     rdx, [rsp+4E0h+szVolumePathName]; lpszVolumePathName
0x180007ee1  lea     rcx, [rbp+3E0h+szFilePath]; lpszFileName
0x180007ee8  call    cs:__imp_GetVolumePathNameW
0x180007eee  test    eax, eax
0x180007ef0  jz      short loc_180007EAF
0x180007ef2  lea     rax, [rsp+4E0h+TotalNumberOfClusters]
0x180007ef7  mov     [rsp+4E0h+SectorsPerCluster], r12d
0x180007efc  lea     r9, [rsp+4E0h+TotalNumberOfClusters]; lpNumberOfFreeClusters
0x180007f01  mov     [rsp+4E0h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x180007f06  lea     r8, [rsp+4E0h+BytesPerSector]; lpBytesPerSector
0x180007f0b  mov     [rsp+4E0h+BytesPerSector], r12d
0x180007f10  lea     rdx, [rsp+4E0h+SectorsPerCluster]; lpSectorsPerCluster
0x180007f15  mov     [rsp+4E0h+TotalNumberOfClusters], r12d
0x180007f1a  lea     rcx, [rsp+4E0h+szVolumePathName]; lpRootPathName
0x180007f1f  call    cs:__imp_GetDiskFreeSpaceW
0x180007f25  test    eax, eax
0x180007f27  jz      short loc_180007EAF
0x180007f29  mov     eax, ebx
0x180007f2b  lea     rcx, [rax+rax]
0x180007f2f  movzx   eax, [rsp+rcx+4E0h+szVolumePathName]
0x180007f34  test    ax, ax
0x180007f37  jnz     loc_180007FCD
0x180007f3d  sub     ebx, 1
0x180007f40  jns     short loc_180007F29
0x180007f42  xor     r9d, r9d; lpSecurityAttributes
0x180007f45  mov     [rsp+4E0h+hTemplateFile], r12; hTemplateFile
0x180007f4a  mov     dword ptr [rsp+4E0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180007f4f  lea     rcx, [rsp+4E0h+szVolumePathName]; lpFileName
0x180007f54  mov     edx, 80000000h; dwDesiredAccess
0x180007f59  mov     dword ptr [rsp+4E0h+lpTotalNumberOfClusters], 3; dwCreationDisposition
0x180007f61  lea     r8d, [r9+7]; dwShareMode
0x180007f65  call    cs:__imp_CreateFileW
0x180007f6b  mov     rbx, rax
0x180007f6e  dec     rax
0x180007f71  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007f75  ja      loc_180008104
0x180007f7b  mov     [rsp+4E0h+lpOverlapped], r12; lpOverlapped
0x180007f80  lea     rax, [rsp+4E0h+OutBuffer]
0x180007f85  mov     [rsp+4E0h+hTemplateFile], r12; lpBytesReturned
0x180007f8a  xor     r9d, r9d; nInBufferSize
0x180007f8d  mov     dword ptr [rsp+4E0h+dwFlagsAndAttributes], 8; unsigned int *
0x180007f95  xor     r8d, r8d; lpInBuffer
0x180007f98  mov     edx, 90234h; dwIoControlCode
0x180007f9d  mov     [rsp+4E0h+lpTotalNumberOfClusters], rax; lpOutBuffer
0x180007fa2  mov     rcx, rbx; hDevice
0x180007fa5  call    cs:__imp_DeviceIoControl
0x180007fab  test    eax, eax
0x180007fad  jnz     short loc_180007FEB
0x180007faf  call    cs:__imp_GetLastError
0x180007fb5  mov     edi, eax
0x180007fb7  test    eax, eax
0x180007fb9  jle     loc_180008123
0x180007fbf  movzx   edi, ax
0x180007fc2  or      edi, 80070000h
0x180007fc8  jmp     loc_180008123
0x180007fcd  cmp     ax, 5Ch ; '\'
0x180007fd1  jnz     loc_180007F42
0x180007fd7  cmp     rcx, r13
0x180007fda  jnb     loc_180008151
0x180007fe0  mov     [rsp+rcx+4E0h+szVolumePathName], r12w
0x180007fe6  jmp     loc_180007F42
0x180007feb  test    rdi, rdi
0x180007fee  jz      short loc_180008038
0x180007ff0  mov     [rsp+4E0h+lpOverlapped], r12; lpOverlapped
0x180007ff5  xor     r9d, r9d; nInBufferSize
0x180007ff8  mov     [rsp+4E0h+hTemplateFile], r12; lpBytesReturned
0x180007ffd  xor     r8d, r8d; lpInBuffer
0x180008000  mov     dword ptr [rsp+4E0h+dwFlagsAndAttributes], 10h; nOutBufferSize
0x180008008  mov     edx, 4D0018h; dwIoControlCode
0x18000800d  mov     rcx, rbx; hDevice
0x180008010  mov     [rsp+4E0h+lpTotalNumberOfClusters], rdi; lpOutBuffer
0x180008015  call    cs:__imp_DeviceIoControl
0x18000801b  test    eax, eax
0x18000801d  jnz     short loc_180008038
0x18000801f  call    cs:__imp_GetLastError
0x180008025  test    eax, eax
0x180008027  jle     short loc_180008031
0x180008029  movzx   eax, ax
0x18000802c  or      eax, 80070000h
0x180008031  mov     edi, eax
0x180008033  jmp     loc_180008123
0x180008038  mov     rcx, rbx; hObject
0x18000803b  call    cs:__imp_CloseHandle
0x180008041  lea     rax, [rsp+4E0h+Block]
0x180008046  mov     [rsp+4E0h+var_480], r12
0x18000804b  lea     r8, [rsp+4E0h+var_480]; void *
0x180008050  mov     [rsp+4E0h+lpTotalNumberOfClusters], rax; void **
0x180008055  mov     rcx, rsi; hDevice
0x180008058  mov     [rsp+4E0h+Block], r12
0x18000805d  call    ?DeviceIoControlWithAlloc@@YA_NPEAXK0KPEAPEAXPEAK@Z; DeviceIoControlWithAlloc(void *,ulong,void *,ulong,void * *,ulong *)
0x180008062  test    al, al
0x180008064  jz      loc_180007EAF
0x18000806a  mov     rbx, [rsp+4E0h+Block]
0x18000806f  mov     edi, [rbx]
0x180008071  mov     ecx, edi
0x180008073  shl     rcx, 4; Size
0x180008077  call    cs:__imp_malloc
0x18000807d  mov     r8, rax
0x180008080  test    rax, rax
0x180008083  jnz     short loc_180008098
0x180008085  mov     rcx, rbx; Block
0x180008088  call    cs:__imp_free
0x18000808e  mov     eax, 8007000Eh
0x180008093  jmp     loc_18000812E
0x180008098  mov     r10d, [rsp+4E0h+BytesPerSector]
0x18000809d  mov     r9d, r12d
0x1800080a0  imul    r10d, [rsp+4E0h+SectorsPerCluster]
0x1800080a6  mov     rcx, [rbx+8]
0x1800080aa  test    edi, edi
0x1800080ac  jz      short loc_1800080EF
0x1800080ae  mov     edx, r9d
0x1800080b1  inc     r9d
0x1800080b4  shl     rdx, 4
0x1800080b8  mov     rax, [rdx+rbx+10h]
0x1800080bd  sub     rax, rcx
0x1800080c0  mov     rcx, r10
0x1800080c3  imul    rax, r10
0x1800080c7  mov     [rdx+r8], rax
0x1800080cb  mov     rax, [rsp+4E0h+Block]
0x1800080d0  imul    rcx, [rdx+rax+18h]
0x1800080d6  add     rcx, [rsp+4E0h+OutBuffer]
0x1800080db  mov     [rdx+r8+8], rcx
0x1800080e0  mov     rbx, [rsp+4E0h+Block]
0x1800080e5  mov     rcx, [rdx+rbx+10h]
0x1800080ea  cmp     r9d, [rbx]
0x1800080ed  jb      short loc_1800080AE
0x1800080ef  mov     [r14], r8
0x1800080f2  mov     rcx, rbx; Block
0x1800080f5  mov     eax, [rbx]
0x1800080f7  mov     [r15], eax
0x1800080fa  call    cs:__imp_free
0x180008100  xor     eax, eax
0x180008102  jmp     short loc_18000812E
0x180008104  call    cs:__imp_GetLastError
0x18000810a  mov     edi, eax
0x18000810c  test    eax, eax
0x18000810e  jle     short loc_180008119
0x180008110  movzx   edi, ax
0x180008113  or      edi, 80070000h
0x180008119  lea     rcx, [rbx-1]
0x18000811d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180008121  ja      short loc_18000812C
0x180008123  mov     rcx, rbx; hObject
0x180008126  call    cs:__imp_CloseHandle
0x18000812c  mov     eax, edi
0x18000812e  mov     rcx, [rbp+3E0h+var_50]
0x180008135  xor     rcx, rsp; StackCookie
0x180008138  call    __security_check_cookie
0x18000813d  add     rsp, 4A8h
0x180008144  pop     r15
0x180008146  pop     r14
0x180008148  pop     r13
0x18000814a  pop     r12
0x18000814c  pop     rdi
0x18000814d  pop     rsi
0x18000814e  pop     rbx
0x18000814f  pop     rbp
0x180008150  retn
0x180008151  call    __report_rangecheckfailure
```
