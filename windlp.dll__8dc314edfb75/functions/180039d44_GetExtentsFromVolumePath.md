# GetExtentsFromVolumePath

- ea: `0x180039d44`
- end: `0x180039f47`
- name: `GetExtentsFromVolumePath`
- size: `515`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180019b00`
- `0x180039b70`

## callees

- `0x180039c40`
- `0x180039d44`
- `0x180039f50`
- `0x18003a2d4`
- `0x18007ed40`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x180039d98`
- `ntdll!RtlSetThreadErrorMode` at `0x180039e28`
- `ntdll!RtlSetThreadErrorMode` at `0x180039d98`
- `ntdll!RtlSetThreadErrorMode` at `0x180039e28`
- `ntdll!RtlGetThreadErrorMode` at `0x180039d89`
- `ntdll!RtlGetThreadErrorMode` at `0x180039d89`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039dc5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039dc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039e0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039e57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039f2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039e0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039e57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039f2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039e69`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039e69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039e1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039f3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039e1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039f3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039d77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039d77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039dfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039dfe`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180039eba`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180039eba`

## pseudocode

```c
_DWORD *__fastcall GetExtentsFromVolumePath(LPCWSTR lpFileName, int a2)
{
  ULONG v5; // r12d
  _DWORD *v6; // rdi
  ULONG ThreadErrorMode; // ebx
  HANDLE FileW; // rax
  void *v9; // r14
  int v10; // ebp
  _DWORD *VolumeDiskExtentsByHandle; // rax
  HANDLE v12; // rax
  HANDLE ProcessHeap; // rax
  _DWORD *v14; // rax
  __int64 v15; // rcx
  __int64 DriveLayout; // rax
  void *v17; // rsi
  __int64 v18; // rdx
  int v19; // r8d
  HANDLE v20; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-48h] BYREF
  __int64 OutBuffer; // [rsp+48h] [rbp-40h] BYREF
  int v23; // [rsp+50h] [rbp-38h]

  if ( !lpFileName )
  {
    SetLastError(0x57u);
    return 0;
  }
  v5 = 0;
  v6 = 0;
  ThreadErrorMode = RtlGetThreadErrorMode();
  if ( RtlSetThreadErrorMode(ThreadErrorMode | 0x10, 0) >= 0 )
    v5 = ThreadErrorMode;
  FileW = CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v9 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v10 = 0;
    VolumeDiskExtentsByHandle = (_DWORD *)GetVolumeDiskExtentsByHandle(FileW);
    v6 = VolumeDiskExtentsByHandle;
    if ( VolumeDiskExtentsByHandle )
    {
      if ( *VolumeDiskExtentsByHandle == 1 || (unsigned int)IsVolumeRetainedByHandle(v9) )
LABEL_9:
        v10 = 1;
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v14 = HeapAlloc(ProcessHeap, 8u, 0x38u);
      v6 = v14;
      if ( v14 )
      {
        OutBuffer = 0;
        v23 = 0;
        BytesReturned = 0;
        *v14 = 1;
        if ( DeviceIoControl(v9, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &BytesReturned, 0) )
        {
          v15 = HIDWORD(OutBuffer);
          v6[2] = HIDWORD(OutBuffer);
          if ( a2 )
          {
            if ( v23 )
            {
              DriveLayout = GetDriveLayout(v15, 0);
              v17 = (void *)DriveLayout;
              if ( DriveLayout )
              {
                v18 = 0;
                if ( *(_DWORD *)(DriveLayout + 4) )
                {
                  v19 = v23;
                  do
                  {
                    if ( v10 )
                      break;
                    if ( v19 == *(_DWORD *)(DriveLayout + 144 * v18 + 72) )
                    {
                      v10 = 1;
                      *((_QWORD *)v6 + 2) = *(_QWORD *)(DriveLayout + 144 * v18 + 56);
                      *((_QWORD *)v6 + 3) = *(_QWORD *)(DriveLayout + 144 * v18 + 64);
                    }
                    v18 = (unsigned int)(v18 + 1);
                  }
                  while ( (unsigned int)v18 < *(_DWORD *)(DriveLayout + 4) );
                }
                v20 = GetProcessHeap();
                HeapFree(v20, 0, v17);
              }
            }
            goto LABEL_10;
          }
          goto LABEL_9;
        }
      }
    }
LABEL_10:
    CloseHandle(v9);
    if ( !v10 )
    {
      if ( v6 )
      {
        v12 = GetProcessHeap();
        HeapFree(v12, 0, v6);
        v6 = 0;
      }
    }
  }
  RtlSetThreadErrorMode(v5, 0);
  return v6;
}

```

## disassembly

```asm
0x180039d44  mov     [rsp+arg_8], rbx
0x180039d49  mov     [rsp+arg_10], rbp
0x180039d4e  push    rsi
0x180039d4f  push    rdi
0x180039d50  push    r12
0x180039d52  push    r14
0x180039d54  push    r15
0x180039d56  sub     rsp, 60h
0x180039d5a  mov     rax, cs:__security_cookie
0x180039d61  xor     rax, rsp
0x180039d64  mov     [rsp+88h+var_30], rax
0x180039d69  mov     r15d, edx
0x180039d6c  mov     rsi, rcx
0x180039d6f  test    rcx, rcx
0x180039d72  jnz     short loc_180039D84
0x180039d74  lea     ecx, [rsi+57h]; dwErrCode
0x180039d77  call    cs:__imp_SetLastError
0x180039d7d  xor     eax, eax
0x180039d7f  jmp     loc_180039E31
0x180039d84  xor     r12d, r12d
0x180039d87  xor     edi, edi
0x180039d89  call    cs:__imp_RtlGetThreadErrorMode
0x180039d8f  mov     ecx, eax
0x180039d91  xor     edx, edx; OldMode
0x180039d93  or      ecx, 10h; NewMode
0x180039d96  mov     ebx, eax
0x180039d98  call    cs:__imp_RtlSetThreadErrorMode
0x180039d9e  mov     [rsp+88h+hTemplateFile], rdi; hTemplateFile
0x180039da3  lea     r8d, [rdi+3]; dwShareMode
0x180039da7  test    eax, eax
0x180039da9  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180039db1  mov     edx, 80000000h; dwDesiredAccess
0x180039db6  mov     [rsp+88h+dwCreationDisposition], r8d; dwCreationDisposition
0x180039dbb  cmovns  r12d, ebx
0x180039dbf  mov     rcx, rsi; lpFileName
0x180039dc2  xor     r9d, r9d; lpSecurityAttributes
0x180039dc5  call    cs:__imp_CreateFileW
0x180039dcb  mov     r14, rax
0x180039dce  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039dd2  jz      short loc_180039E23
0x180039dd4  mov     rcx, rax; hDevice
0x180039dd7  xor     ebp, ebp
0x180039dd9  call    GetVolumeDiskExtentsByHandle
0x180039dde  mov     rdi, rax
0x180039de1  test    rax, rax
0x180039de4  jz      short loc_180039E57
0x180039de6  lea     ebx, [rbp+1]
0x180039de9  cmp     [rax], ebx
0x180039deb  jz      short loc_180039DF9
0x180039ded  mov     rcx, r14
0x180039df0  call    IsVolumeRetainedByHandle
0x180039df5  test    eax, eax
0x180039df7  jz      short loc_180039DFB
0x180039df9  mov     ebp, ebx
0x180039dfb  mov     rcx, r14; hObject
0x180039dfe  call    cs:__imp_CloseHandle
0x180039e04  test    ebp, ebp
0x180039e06  jnz     short loc_180039E23
0x180039e08  test    rdi, rdi
0x180039e0b  jz      short loc_180039E23
0x180039e0d  call    cs:__imp_GetProcessHeap
0x180039e13  mov     r8, rdi; lpMem
0x180039e16  xor     edx, edx; dwFlags
0x180039e18  mov     rcx, rax; hHeap
0x180039e1b  call    cs:__imp_HeapFree
0x180039e21  xor     edi, edi
0x180039e23  xor     edx, edx; OldMode
0x180039e25  mov     ecx, r12d; NewMode
0x180039e28  call    cs:__imp_RtlSetThreadErrorMode
0x180039e2e  mov     rax, rdi
0x180039e31  mov     rcx, [rsp+88h+var_30]
0x180039e36  xor     rcx, rsp; StackCookie
0x180039e39  call    __security_check_cookie
0x180039e3e  lea     r11, [rsp+88h+var_28]
0x180039e43  mov     rbx, [r11+38h]
0x180039e47  mov     rbp, [r11+40h]
0x180039e4b  mov     rsp, r11
0x180039e4e  pop     r15
0x180039e50  pop     r14
0x180039e52  pop     r12
0x180039e54  pop     rdi
0x180039e55  pop     rsi
0x180039e56  retn
0x180039e57  call    cs:__imp_GetProcessHeap
0x180039e5d  mov     edx, 8; dwFlags
0x180039e62  mov     rcx, rax; hHeap
0x180039e65  lea     r8d, [rdx+30h]; dwBytes
0x180039e69  call    cs:__imp_HeapAlloc
0x180039e6f  mov     rdi, rax
0x180039e72  test    rax, rax
0x180039e75  jz      short loc_180039DFB
0x180039e77  xor     eax, eax
0x180039e79  xor     r9d, r9d; nInBufferSize
0x180039e7c  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x180039e81  xor     r8d, r8d; lpInBuffer
0x180039e84  mov     [rsp+88h+OutBuffer], rax
0x180039e89  mov     edx, 2D1080h; dwIoControlCode
0x180039e8e  mov     [rsp+88h+var_38], eax
0x180039e92  mov     rcx, r14; hDevice
0x180039e95  lea     ebx, [rax+1]
0x180039e98  mov     [rsp+88h+BytesReturned], eax
0x180039e9c  lea     rax, [rsp+88h+BytesReturned]
0x180039ea1  mov     [rdi], ebx
0x180039ea3  mov     [rsp+88h+hTemplateFile], rax; lpBytesReturned
0x180039ea8  lea     rax, [rsp+88h+OutBuffer]
0x180039ead  mov     [rsp+88h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x180039eb5  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; lpOutBuffer
0x180039eba  call    cs:__imp_DeviceIoControl
0x180039ec0  test    eax, eax
0x180039ec2  jz      loc_180039DFB
0x180039ec8  mov     ecx, dword ptr [rsp+88h+OutBuffer+4]
0x180039ecc  mov     [rdi+8], ecx
0x180039ecf  test    r15d, r15d
0x180039ed2  jz      loc_180039DF9
0x180039ed8  cmp     [rsp+88h+var_38], ebp
0x180039edc  jbe     loc_180039DFB
0x180039ee2  xor     edx, edx
0x180039ee4  call    GetDriveLayout
0x180039ee9  mov     rsi, rax
0x180039eec  test    rax, rax
0x180039eef  jz      loc_180039DFB
0x180039ef5  xor     edx, edx
0x180039ef7  cmp     [rax+4], edx
0x180039efa  jbe     short loc_180039F2E
0x180039efc  mov     r8d, [rsp+88h+var_38]
0x180039f01  test    ebp, ebp
0x180039f03  jnz     short loc_180039F2E
0x180039f05  lea     rcx, [rdx+rdx*8]
0x180039f09  add     rcx, rcx
0x180039f0c  cmp     r8d, [rsi+rcx*8+48h]
0x180039f11  jnz     short loc_180039F27
0x180039f13  mov     rax, [rsi+rcx*8+38h]
0x180039f18  mov     ebp, ebx
0x180039f1a  mov     [rdi+10h], rax
0x180039f1e  mov     rax, [rsi+rcx*8+40h]
0x180039f23  mov     [rdi+18h], rax
0x180039f27  add     edx, ebx
0x180039f29  cmp     edx, [rsi+4]
0x180039f2c  jb      short loc_180039F01
0x180039f2e  call    cs:__imp_GetProcessHeap
0x180039f34  mov     r8, rsi; lpMem
0x180039f37  xor     edx, edx; dwFlags
0x180039f39  mov     rcx, rax; hHeap
0x180039f3c  call    cs:__imp_HeapFree
0x180039f42  jmp     loc_180039DFB
```
