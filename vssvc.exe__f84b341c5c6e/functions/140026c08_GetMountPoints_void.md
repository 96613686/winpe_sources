# GetMountPoints(void)

- ea: `0x140026c08`
- end: `0x140026f4c`
- name: `?GetMountPoints@@YAPEAU_MOUNTMGR_MOUNT_POINTS@@XZ`
- size: `836`
- prototype: `struct _MOUNTMGR_MOUNT_POINTS *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x1400235e0`
- `0x140025e3c`

## callees

- `0x140026c08`
- `0x140091560`
- `0x1400d2b80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140026ca4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140026eef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140026ca4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140026eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026e8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026ebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026e8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026ebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140026f29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140026f29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140026c37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140026c37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140026c4e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140026dbd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140026c4e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140026dbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140026efd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140026f14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140026efd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140026f14`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140026ce2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140026ce2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140026d89`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140026e4f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140026d89`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140026e4f`

## string_xrefs

- `0x140026cb6`: `\\.\MountPointManager`
- `0x140026c82`: `!pMountPointIn`
- `0x140026e98`: `(!cbMountPoints || !bResult)`
- `0x140026d22`: `(!hMountMgr || INVALID_HANDLE_VALUE == hMountMgr)`
- `0x140026dea`: `!pMountPointsOut`

## pseudocode

```c
struct _MOUNTMGR_MOUNT_POINTS *GetMountPoints(void)
{
  void *v0; // rdi
  HANDLE ProcessHeap; // r14
  unsigned __int16 *v2; // rax
  unsigned __int16 *v3; // rsi
  char LastError; // al
  char *FileW; // rbp
  char v6; // bl
  DWORD v7; // eax
  int v8; // r8d
  int v9; // edx
  const char *v10; // rcx
  DWORD v11; // ebx
  DWORD v12; // ecx
  DWORD v13; // eax
  char v14; // al
  int v15; // r8d
  BOOL v16; // eax
  char v17; // al
  int v18; // r8d
  DWORD BytesReturned; // [rsp+40h] [rbp-68h] BYREF
  _OWORD OutBuffer[2]; // [rsp+48h] [rbp-60h] BYREF

  v0 = 0;
  memset(OutBuffer, 0, sizeof(OutBuffer));
  BytesReturned = 0;
  ProcessHeap = GetProcessHeap();
  v2 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x1Au);
  v3 = v2;
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_DDs(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        53,
        (unsigned int)"!pMountPointIn",
        8,
        LastError,
        (__int64)"!pMountPointIn");
    }
    SetLastError(8u);
    return (struct _MOUNTMGR_MOUNT_POINTS *)v0;
  }
  *((_DWORD *)v2 + 4) = 24;
  v2[10] = 0;
  FileW = (char *)CreateFileW(L"\\\\.\\MountPointManager", 0, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_11;
    }
    v6 = GetLastError();
    v7 = GetLastError();
    v9 = 54;
    v10 = "(!hMountMgr || INVALID_HANDLE_VALUE == hMountMgr)";
    goto LABEL_10;
  }
  if ( DeviceIoControl(FileW, 0x6D0008u, v3, v3[10] + 24, OutBuffer, 0x20u, &BytesReturned, 0) )
  {
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v17 = GetLastError();
      WPP_SF_DDs(*(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4, 57, v18, 0, v17, (__int64)"bResult");
    }
    v11 = 0;
    v12 = 0;
    goto LABEL_30;
  }
  v13 = GetLastError();
  v11 = v13;
  if ( v13 == 234 || v13 == 122 || v13 == 24 )
  {
    v11 = 0;
    v0 = HeapAlloc(ProcessHeap, 8u, LODWORD(OutBuffer[0]));
    if ( !v0 )
    {
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v14 = GetLastError();
        WPP_SF_DDs(*(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4, 55, v15, 8, v14, (__int64)"!pMountPointsOut");
      }
      v11 = 8;
      v12 = 8;
      goto LABEL_30;
    }
  }
  v16 = DeviceIoControl(FileW, 0x6D0008u, v3, v3[10] + 24, v0, OutBuffer[0], &BytesReturned, 0);
  if ( BytesReturned && v16 )
    goto LABEL_31;
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
  {
    v6 = GetLastError();
    v7 = GetLastError();
    v9 = 58;
    v10 = "(!cbMountPoints || !bResult)";
LABEL_10:
    WPP_SF_DDs(*(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4, v9, v8, v7, v6, (__int64)v10);
  }
LABEL_11:
  v11 = GetLastError();
  v12 = v11;
LABEL_30:
  SetLastError(v12);
LABEL_31:
  HeapFree(ProcessHeap, 0, v3);
  if ( v11 && v0 )
  {
    HeapFree(ProcessHeap, 0, v0);
    v0 = 0;
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return (struct _MOUNTMGR_MOUNT_POINTS *)v0;
}

```

## disassembly

```asm
0x140026c08  push    rbx
0x140026c0a  push    rbp
0x140026c0b  push    rsi
0x140026c0c  push    rdi
0x140026c0d  push    r14
0x140026c0f  push    r15
0x140026c11  sub     rsp, 78h
0x140026c15  mov     rax, cs:__security_cookie
0x140026c1c  xor     rax, rsp
0x140026c1f  mov     [rsp+0A8h+var_40], rax
0x140026c24  xorps   xmm0, xmm0
0x140026c27  xor     edi, edi
0x140026c29  movups  [rsp+0A8h+OutBuffer], xmm0
0x140026c2e  mov     [rsp+0A8h+BytesReturned], edi
0x140026c32  movups  [rsp+0A8h+var_50], xmm0
0x140026c37  call    cs:__imp_GetProcessHeap
0x140026c3d  lea     r15d, [rdi+8]
0x140026c41  mov     rcx, rax; hHeap
0x140026c44  mov     edx, r15d; dwFlags
0x140026c47  lea     r8d, [rdi+1Ah]; dwBytes
0x140026c4b  mov     r14, rax
0x140026c4e  call    cs:__imp_HeapAlloc
0x140026c54  mov     rsi, rax
0x140026c57  test    rax, rax
0x140026c5a  jnz     short loc_140026CAF
0x140026c5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140026c63  lea     rax, WPP_GLOBAL_Control
0x140026c6a  cmp     rcx, rax
0x140026c6d  jz      short loc_140026CA1
0x140026c6f  test    [rcx+1Ch], r15b
0x140026c73  jz      short loc_140026CA1
0x140026c75  call    cs:__imp_GetLastError
0x140026c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140026c82  lea     r8, aPmountpointin; "!pMountPointIn"
0x140026c89  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], r8
0x140026c8e  lea     edx, [rdi+35h]
0x140026c91  mov     r9d, r15d
0x140026c94  mov     [rsp+0A8h+dwCreationDisposition], eax
0x140026c98  mov     rcx, [rcx+10h]
0x140026c9c  call    WPP_SF_DDs
0x140026ca1  mov     ecx, r15d; dwErrCode
0x140026ca4  call    cs:__imp_SetLastError
0x140026caa  jmp     loc_140026F2F
0x140026caf  mov     dword ptr [rax+10h], 18h
0x140026cb6  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x140026cbd  xor     eax, eax
0x140026cbf  mov     [rsp+0A8h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x140026cc8  mov     [rsp+0A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140026cd0  xor     r9d, r9d; lpSecurityAttributes
0x140026cd3  xor     edx, edx; dwDesiredAccess
0x140026cd5  mov     [rsi+14h], ax
0x140026cd9  lea     r8d, [rax+3]; dwShareMode
0x140026cdd  mov     [rsp+0A8h+dwCreationDisposition], r8d; dwCreationDisposition
0x140026ce2  call    cs:__imp_CreateFileW
0x140026ce8  mov     rbp, rax
0x140026ceb  inc     rax
0x140026cee  test    rax, 0FFFFFFFFFFFFFFFEh
0x140026cf4  jnz     short loc_140026D54
0x140026cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x140026cfd  lea     rax, WPP_GLOBAL_Control
0x140026d04  cmp     rcx, rax
0x140026d07  jz      short loc_140026D45
0x140026d09  test    [rcx+1Ch], r15b
0x140026d0d  jz      short loc_140026D45
0x140026d0f  call    cs:__imp_GetLastError
0x140026d15  mov     ebx, eax
0x140026d17  call    cs:__imp_GetLastError
0x140026d1d  mov     edx, 36h ; '6'
0x140026d22  lea     rcx, aHmountmgrInval; "(!hMountMgr || INVALID_HANDLE_VALUE == "...
0x140026d29  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rcx
0x140026d2e  mov     r9d, eax
0x140026d31  mov     rcx, cs:WPP_GLOBAL_Control
0x140026d38  mov     [rsp+0A8h+dwCreationDisposition], ebx
0x140026d3c  mov     rcx, [rcx+10h]
0x140026d40  call    WPP_SF_DDs
0x140026d45  call    cs:__imp_GetLastError
0x140026d4b  mov     ebx, eax
0x140026d4d  mov     ecx, eax
0x140026d4f  jmp     loc_140026EEF
0x140026d54  movzx   r9d, word ptr [rsi+14h]
0x140026d59  lea     rax, [rsp+0A8h+BytesReturned]
0x140026d5e  mov     [rsp+0A8h+lpOverlapped], rdi; lpOverlapped
0x140026d63  add     r9d, 18h; nInBufferSize
0x140026d67  mov     [rsp+0A8h+hTemplateFile], rax; lpBytesReturned
0x140026d6c  mov     r8, rsi; lpInBuffer
0x140026d6f  lea     rax, [rsp+0A8h+OutBuffer]
0x140026d74  mov     [rsp+0A8h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x140026d7c  mov     edx, 6D0008h; dwIoControlCode
0x140026d81  mov     qword ptr [rsp+0A8h+dwCreationDisposition], rax; lpOutBuffer
0x140026d86  mov     rcx, rbp; hDevice
0x140026d89  call    cs:__imp_DeviceIoControl
0x140026d8f  test    eax, eax
0x140026d91  jnz     loc_140026EA4
0x140026d97  call    cs:__imp_GetLastError
0x140026d9d  mov     ebx, eax
0x140026d9f  cmp     eax, 0EAh
0x140026da4  jz      short loc_140026DB0
0x140026da6  cmp     eax, 7Ah ; 'z'
0x140026da9  jz      short loc_140026DB0
0x140026dab  cmp     eax, 18h
0x140026dae  jnz     short loc_140026E1B
0x140026db0  mov     r8d, dword ptr [rsp+0A8h+OutBuffer]; dwBytes
0x140026db5  mov     edx, r15d; dwFlags
0x140026db8  mov     rcx, r14; hHeap
0x140026dbb  xor     ebx, ebx
0x140026dbd  call    cs:__imp_HeapAlloc
0x140026dc3  mov     rdi, rax
0x140026dc6  test    rax, rax
0x140026dc9  jnz     short loc_140026E1B
0x140026dcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140026dd2  lea     rax, WPP_GLOBAL_Control
0x140026dd9  cmp     rcx, rax
0x140026ddc  jz      short loc_140026E10
0x140026dde  test    [rcx+1Ch], r15b
0x140026de2  jz      short loc_140026E10
0x140026de4  call    cs:__imp_GetLastError
0x140026dea  lea     rcx, aPmountpointsou; "!pMountPointsOut"
0x140026df1  mov     r9d, r15d
0x140026df4  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rcx
0x140026df9  lea     edx, [rbx+37h]
0x140026dfc  mov     rcx, cs:WPP_GLOBAL_Control
0x140026e03  mov     [rsp+0A8h+dwCreationDisposition], eax
0x140026e07  mov     rcx, [rcx+10h]
0x140026e0b  call    WPP_SF_DDs
0x140026e10  mov     ebx, r15d
0x140026e13  mov     ecx, r15d
0x140026e16  jmp     loc_140026EEF
0x140026e1b  movzx   r9d, word ptr [rsi+14h]
0x140026e20  lea     rax, [rsp+0A8h+BytesReturned]
0x140026e25  mov     [rsp+0A8h+lpOverlapped], 0; lpOverlapped
0x140026e2e  add     r9d, 18h; nInBufferSize
0x140026e32  mov     [rsp+0A8h+hTemplateFile], rax; lpBytesReturned
0x140026e37  mov     r8, rsi; lpInBuffer
0x140026e3a  mov     eax, dword ptr [rsp+0A8h+OutBuffer]
0x140026e3e  mov     edx, 6D0008h; dwIoControlCode
0x140026e43  mov     [rsp+0A8h+dwFlagsAndAttributes], eax; nOutBufferSize
0x140026e47  mov     rcx, rbp; hDevice
0x140026e4a  mov     qword ptr [rsp+0A8h+dwCreationDisposition], rdi; lpOutBuffer
0x140026e4f  call    cs:__imp_DeviceIoControl
0x140026e55  cmp     [rsp+0A8h+BytesReturned], 0
0x140026e5a  jz      short loc_140026E64
0x140026e5c  test    eax, eax
0x140026e5e  jnz     loc_140026EF5
0x140026e64  mov     rcx, cs:WPP_GLOBAL_Control
0x140026e6b  lea     rax, WPP_GLOBAL_Control
0x140026e72  cmp     rcx, rax
0x140026e75  jz      loc_140026D45
0x140026e7b  test    [rcx+1Ch], r15b
0x140026e7f  jz      loc_140026D45
0x140026e85  call    cs:__imp_GetLastError
0x140026e8b  mov     ebx, eax
0x140026e8d  call    cs:__imp_GetLastError
0x140026e93  mov     edx, 3Ah ; ':'
0x140026e98  lea     rcx, aCbmountpointsB; "(!cbMountPoints || !bResult)"
0x140026e9f  jmp     loc_140026D29
0x140026ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x140026eab  lea     rax, WPP_GLOBAL_Control
0x140026eb2  cmp     rcx, rax
0x140026eb5  jz      short loc_140026EEB
0x140026eb7  test    [rcx+1Ch], r15b
0x140026ebb  jz      short loc_140026EEB
0x140026ebd  call    cs:__imp_GetLastError
0x140026ec3  lea     rcx, aBresult; "bResult"
0x140026eca  mov     edx, 39h ; '9'
0x140026ecf  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rcx
0x140026ed4  xor     r9d, r9d
0x140026ed7  mov     rcx, cs:WPP_GLOBAL_Control
0x140026ede  mov     [rsp+0A8h+dwCreationDisposition], eax
0x140026ee2  mov     rcx, [rcx+10h]
0x140026ee6  call    WPP_SF_DDs
0x140026eeb  xor     ebx, ebx
0x140026eed  xor     ecx, ecx; dwErrCode
0x140026eef  call    cs:__imp_SetLastError
0x140026ef5  mov     r8, rsi; lpMem
0x140026ef8  xor     edx, edx; dwFlags
0x140026efa  mov     rcx, r14; hHeap
0x140026efd  call    cs:__imp_HeapFree
0x140026f03  test    ebx, ebx
0x140026f05  jz      short loc_140026F1C
0x140026f07  test    rdi, rdi
0x140026f0a  jz      short loc_140026F1C
0x140026f0c  mov     r8, rdi; lpMem
0x140026f0f  xor     edx, edx; dwFlags
0x140026f11  mov     rcx, r14; hHeap
0x140026f14  call    cs:__imp_HeapFree
0x140026f1a  xor     edi, edi
0x140026f1c  lea     rax, [rbp-1]
0x140026f20  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140026f24  ja      short loc_140026F2F
0x140026f26  mov     rcx, rbp; hObject
0x140026f29  call    cs:__imp_CloseHandle
0x140026f2f  mov     rax, rdi
0x140026f32  mov     rcx, [rsp+0A8h+var_40]
0x140026f37  xor     rcx, rsp; StackCookie
0x140026f3a  call    __security_check_cookie
0x140026f3f  add     rsp, 78h
0x140026f43  pop     r15
0x140026f45  pop     r14
0x140026f47  pop     rdi
0x140026f48  pop     rsi
0x140026f49  pop     rbp
0x140026f4a  pop     rbx
0x140026f4b  retn
```
