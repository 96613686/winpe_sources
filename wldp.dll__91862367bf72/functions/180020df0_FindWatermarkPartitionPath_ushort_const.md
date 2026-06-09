# FindWatermarkPartitionPath(ushort const * *)

- ea: `0x180020df0`
- end: `0x18002103b`
- name: `?FindWatermarkPartitionPath@@YAJPEAPEBG@Z`
- size: `587`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18002a940`

## callees

- `0x1800049d0`
- `0x180020df0`
- `0x180021044`
- `0x180021ec0`
- `0x18002a530`
- `0x18002a5f8`
- `0x18002a70c`
- `0x18003ddd4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020e2e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020f8f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020e2e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020f8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f5f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180020ea1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180020ea1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180020fd6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180020fd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall FindWatermarkPartitionPath(unsigned __int16 **a1)
{
  __int64 v2; // rsi
  _DWORD *v3; // rdi
  unsigned __int16 *v4; // r14
  unsigned __int16 *v5; // rax
  unsigned int v6; // ecx
  WCHAR *v7; // r15
  __int64 FirstDisk; // r12
  signed int LastError; // ebx
  unsigned int v10; // edx
  HANDLE FileW; // rax
  int DiskPartitions; // eax
  unsigned int i; // ebp
  const wchar_t *v14; // rdx
  __int64 v16; // r9
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-88h]
  HLOCAL hMem; // [rsp+40h] [rbp-68h] BYREF
  int v19; // [rsp+48h] [rbp-60h]

  hMem = 0;
  v2 = -1;
  v3 = 0;
  v4 = 0;
  v5 = (unsigned __int16 *)LocalAlloc(0x40u, 0x208u);
  v7 = v5;
  if ( v5 )
  {
    FirstDisk = (__int64)FindFirstDisk(v6, v5);
    if ( FirstDisk == -1 )
    {
LABEL_5:
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_19;
    }
    while ( 1 )
    {
      if ( *v7 )
      {
        FileW = CreateFileW(v7, 0xC0000000, 3u, 0, 3u, 0, 0);
        v2 = (__int64)FileW;
        if ( FileW == (HANDLE)-1LL )
          goto LABEL_5;
        DiskPartitions = GetDiskPartitions(FileW, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&hMem);
        v3 = hMem;
        LastError = DiskPartitions;
        if ( DiskPartitions < 0 )
          goto LABEL_19;
        if ( *(_DWORD *)hMem == 1 )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= v3[1] )
              goto LABEL_16;
            v14 = (const wchar_t *)&v3[36 * i + 30];
            if ( v14 )
            {
              if ( !wcscmp_0(L"OPP", v14) )
                break;
            }
          }
          v4 = (unsigned __int16 *)LocalAlloc(0x40u, 0x208u);
          if ( !v4 )
            goto LABEL_3;
          hMem = 0;
          v19 = 0;
          if ( DeviceIoControl((HANDLE)v2, 0x2D1080u, 0, 0, &hMem, 0xCu, 0, 0) )
          {
            v16 = HIDWORD(hMem);
          }
          else
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v16 = 0;
            if ( LastError < 0 )
              goto LABEL_19;
          }
          dwCreationDisposition[0] = i + 1;
          LastError = StringCchPrintfW(
                        v4,
                        0x104u,
                        L"\\\\.\\harddisk%upartition%u\\\\",
                        v16,
                        *(_QWORD *)dwCreationDisposition);
          if ( LastError >= 0 )
          {
            *a1 = v4;
            v4 = 0;
          }
          goto LABEL_19;
        }
LABEL_16:
        LocalFree(v3);
        hMem = 0;
        v3 = 0;
        CloseHandle((HANDLE)v2);
      }
      if ( !FindNextDisk((void *)FirstDisk, v10, v7) )
      {
        LastError = -2147023728;
        v2 = -1;
        goto LABEL_19;
      }
    }
  }
  FirstDisk = -1;
LABEL_3:
  LastError = -2147024882;
LABEL_19:
  LocalFree(v7);
  LocalFree(v4);
  LocalFree(v3);
  FindDiskClose((void *)FirstDisk);
  CloseHandle((HANDLE)v2);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180020df0  push    rbx
0x180020df2  push    rbp
0x180020df3  push    rsi
0x180020df4  push    rdi
0x180020df5  push    r12
0x180020df7  push    r13
0x180020df9  push    r14
0x180020dfb  push    r15
0x180020dfd  sub     rsp, 68h
0x180020e01  mov     rax, cs:__security_cookie
0x180020e08  xor     rax, rsp
0x180020e0b  mov     [rsp+0A8h+var_58], rax
0x180020e10  xor     ebx, ebx
0x180020e12  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180020e16  mov     r13, rcx
0x180020e19  mov     [rsp+0A8h+hMem], rbx
0x180020e1e  mov     edx, 208h; uBytes
0x180020e23  mov     rsi, rbp
0x180020e26  mov     edi, ebx
0x180020e28  mov     r14d, ebx
0x180020e2b  lea     ecx, [rbp+41h]; uFlags
0x180020e2e  call    cs:__imp_LocalAlloc
0x180020e34  mov     r15, rax
0x180020e37  test    rax, rax
0x180020e3a  jnz     short loc_180020E49
0x180020e3c  mov     r12, rbp
0x180020e3f  mov     ebx, 8007000Eh
0x180020e44  jmp     loc_180020F39
0x180020e49  mov     rdx, r15; unsigned __int16 *
0x180020e4c  call    ?FindFirstDisk@@YAPEAXKPEAG@Z; FindFirstDisk(ulong,ushort *)
0x180020e51  mov     r12, rax
0x180020e54  cmp     rax, rbp
0x180020e57  jnz     short loc_180020E77
0x180020e59  call    cs:__imp_GetLastError
0x180020e5f  mov     ebx, eax
0x180020e61  test    eax, eax
0x180020e63  jle     loc_180020F39
0x180020e69  movzx   ebx, bx
0x180020e6c  or      ebx, 80070000h
0x180020e72  jmp     loc_180020F39
0x180020e77  cmp     [r15], bx
0x180020e7b  jz      loc_180020F1E
0x180020e81  xor     r9d, r9d; lpSecurityAttributes
0x180020e84  mov     [rsp+0A8h+hTemplateFile], rbx; hTemplateFile
0x180020e89  mov     [rsp+0A8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180020e8d  mov     edx, 0C0000000h; dwDesiredAccess
0x180020e92  mov     rcx, r15; lpFileName
0x180020e95  mov     [rsp+0A8h+dwCreationDisposition], 3; dwCreationDisposition
0x180020e9d  lea     r8d, [r9+3]; dwShareMode
0x180020ea1  call    cs:__imp_CreateFileW
0x180020ea7  mov     rsi, rax
0x180020eaa  cmp     rax, rbp
0x180020ead  jz      short loc_180020E59
0x180020eaf  lea     rdx, [rsp+0A8h+hMem]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x180020eb4  mov     rcx, rax; hDevice
0x180020eb7  call    ?GetDiskPartitions@@YAJPEAXPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; GetDiskPartitions(void *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x180020ebc  mov     rdi, [rsp+0A8h+hMem]
0x180020ec1  mov     ebx, eax
0x180020ec3  test    eax, eax
0x180020ec5  js      short loc_180020F39
0x180020ec7  xor     ebx, ebx
0x180020ec9  cmp     dword ptr [rdi], 1
0x180020ecc  jnz     short loc_180020F04
0x180020ece  mov     ebp, ebx
0x180020ed0  cmp     ebp, [rdi+4]
0x180020ed3  jnb     short loc_180020F00
0x180020ed5  mov     eax, ebp
0x180020ed7  lea     rdx, [rax+rax*8]
0x180020edb  shl     rdx, 4
0x180020edf  add     rdx, 78h ; 'x'
0x180020ee3  add     rdx, rdi; String2
0x180020ee6  jz      short loc_180020EFC
0x180020ee8  lea     rcx, aOpp; "OPP"
0x180020eef  call    wcscmp_0
0x180020ef4  test    eax, eax
0x180020ef6  jz      loc_180020F85
0x180020efc  inc     ebp
0x180020efe  jmp     short loc_180020ED0
0x180020f00  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180020f04  mov     rcx, rdi; hMem
0x180020f07  call    cs:__imp_LocalFree
0x180020f0d  mov     rcx, rsi; hObject
0x180020f10  mov     [rsp+0A8h+hMem], rbx
0x180020f15  mov     rdi, rbx
0x180020f18  call    cs:__imp_CloseHandle
0x180020f1e  mov     r8, r15; unsigned __int16 *
0x180020f21  mov     rcx, r12; void *
0x180020f24  call    ?FindNextDisk@@YAHPEAXKPEAG@Z; FindNextDisk(void *,ulong,ushort *)
0x180020f29  test    eax, eax
0x180020f2b  jnz     loc_180020E77
0x180020f31  mov     ebx, 80070490h
0x180020f36  mov     rsi, rbp
0x180020f39  mov     rcx, r15; hMem
0x180020f3c  call    cs:__imp_LocalFree
0x180020f42  mov     rcx, r14; hMem
0x180020f45  call    cs:__imp_LocalFree
0x180020f4b  mov     rcx, rdi; hMem
0x180020f4e  call    cs:__imp_LocalFree
0x180020f54  mov     rcx, r12; void *
0x180020f57  call    ?FindDiskClose@@YAXPEAX@Z; FindDiskClose(void *)
0x180020f5c  mov     rcx, rsi; hObject
0x180020f5f  call    cs:__imp_CloseHandle
0x180020f65  mov     eax, ebx
0x180020f67  mov     rcx, [rsp+0A8h+var_58]
0x180020f6c  xor     rcx, rsp; StackCookie
0x180020f6f  call    __security_check_cookie
0x180020f74  add     rsp, 68h
0x180020f78  pop     r15
0x180020f7a  pop     r14
0x180020f7c  pop     r13
0x180020f7e  pop     r12
0x180020f80  pop     rdi
0x180020f81  pop     rsi
0x180020f82  pop     rbp
0x180020f83  pop     rbx
0x180020f84  retn
0x180020f85  mov     edx, 208h; uBytes
0x180020f8a  mov     ecx, 40h ; '@'; uFlags
0x180020f8f  call    cs:__imp_LocalAlloc
0x180020f95  mov     r14, rax
0x180020f98  test    rax, rax
0x180020f9b  jz      loc_180020E3F
0x180020fa1  xor     eax, eax
0x180020fa3  mov     [rsp+0A8h+lpOverlapped], rbx; lpOverlapped
0x180020fa8  mov     [rsp+0A8h+hMem], rax
0x180020fad  xor     r9d, r9d; nInBufferSize
0x180020fb0  mov     [rsp+0A8h+var_60], eax
0x180020fb4  xor     r8d, r8d; lpInBuffer
0x180020fb7  lea     rax, [rsp+0A8h+hMem]
0x180020fbc  mov     [rsp+0A8h+hTemplateFile], rbx; lpBytesReturned
0x180020fc1  mov     [rsp+0A8h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x180020fc9  mov     edx, 2D1080h; dwIoControlCode
0x180020fce  mov     rcx, rsi; hDevice
0x180020fd1  mov     qword ptr [rsp+0A8h+dwCreationDisposition], rax; lpOutBuffer
0x180020fd6  call    cs:__imp_DeviceIoControl
0x180020fdc  test    eax, eax
0x180020fde  jnz     short loc_180021003
0x180020fe0  call    cs:__imp_GetLastError
0x180020fe6  mov     ebx, eax
0x180020fe8  xor     eax, eax
0x180020fea  test    ebx, ebx
0x180020fec  jle     short loc_180020FF7
0x180020fee  movzx   ebx, bx
0x180020ff1  or      ebx, 80070000h
0x180020ff7  mov     r9d, eax
0x180020ffa  test    ebx, ebx
0x180020ffc  jns     short loc_180021008
0x180020ffe  jmp     loc_180020F39
0x180021003  mov     r9d, dword ptr [rsp+0A8h+hMem+4]
0x180021008  lea     eax, [rbp+1]
0x18002100b  mov     edx, 104h; unsigned __int64
0x180021010  lea     r8, aHarddiskUparti; "\\\\.\\harddisk%upartition%u\\\\"
0x180021017  mov     [rsp+0A8h+dwCreationDisposition], eax
0x18002101b  mov     rcx, r14; unsigned __int16 *
0x18002101e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021023  mov     ebx, eax
0x180021025  xor     eax, eax
0x180021027  test    ebx, ebx
0x180021029  js      loc_180020F39
0x18002102f  mov     [r13+0], r14
0x180021033  mov     r14d, eax
0x180021036  jmp     loc_180020F39
```
