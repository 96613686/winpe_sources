# FvepIsVolumeEncryptedNoDriverTest

- ea: `0x1400525bc`
- end: `0x1400527c0`
- name: `FvepIsVolumeEncryptedNoDriverTest`
- size: `516`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140051500`

## callees

- `0x140051ba4`
- `0x1400521d0`
- `0x1400524c8`
- `0x1400525bc`
- `0x1400527c8`
- `0x140052b28`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400526b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005271c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400526b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005271c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052797`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052797`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140052712`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140052712`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140052639`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140052639`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400526a9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400526a9`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x14005278e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x14005278e`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1400526ee`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1400526ee`

## pseudocode

```c
__int64 __fastcall FvepIsVolumeEncryptedNoDriverTest(STRSAFE_PCNZWCH pszSrc)
{
  unsigned int IsBandBitLockerManaged; // ebx
  HANDLE FileW; // rax
  void *v4; // rdi
  signed int v5; // eax
  signed int LastError; // eax
  DWORD v7; // ebx
  void *v8; // rax
  void *v9; // r14
  signed int v10; // eax
  BOOL v11; // edx
  int v12; // eax
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-2Ch] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-28h] BYREF
  __int128 OutBuffer; // [rsp+50h] [rbp-20h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h]

  v17 = 0;
  OutBuffer = 0;
  BytesReturned = 0;
  NumberOfBytesRead = 0;
  if ( (unsigned int)FvepIsVolumeEncryptedCached(pszSrc) )
    return 1;
  FileW = CreateFileW(pszSrc, 0x80000000, 3u, 0, 3u, 0x20000000u, 0);
  v4 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    IsBandBitLockerManaged = FvepIsBandBitLockerManaged(FileW);
    if ( !IsBandBitLockerManaged )
    {
LABEL_25:
      CloseHandle(v4);
      return IsBandBitLockerManaged;
    }
    if ( !DeviceIoControl(v4, 0x70000u, 0, 0, &OutBuffer, 0x18u, &BytesReturned, 0)
      || (v7 = (HIDWORD(v17) + 511) & 0xFFFFFE00, v8 = VirtualAlloc(0, v7, 0x3000u, 4u), (v9 = v8) == 0) )
    {
      LastError = GetLastError();
      IsBandBitLockerManaged = LastError;
      if ( LastError > 0 )
        IsBandBitLockerManaged = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_25;
    }
    if ( ReadFile(v4, v8, v7, &NumberOfBytesRead, 0) )
    {
      v12 = FveCheckVolumeTypeEx(v9, NumberOfBytesRead, 0);
      if ( (unsigned int)(v12 - 2) <= 1 )
      {
        IsBandBitLockerManaged = 0;
      }
      else if ( v12 == 1 )
      {
        IsBandBitLockerManaged = FvepCheckForVolumeControlFiles(v4);
        if ( (IsBandBitLockerManaged & 0x80000000) != 0 )
        {
LABEL_24:
          VirtualFree(v9, 0, 0x8000u);
          goto LABEL_25;
        }
      }
      else
      {
        IsBandBitLockerManaged = 1;
      }
      v11 = IsBandBitLockerManaged == 0;
    }
    else
    {
      v10 = GetLastError();
      IsBandBitLockerManaged = v10;
      if ( v10 > 0 )
        IsBandBitLockerManaged = (unsigned __int16)v10 | 0x80070000;
      if ( IsBandBitLockerManaged != -2144272384 )
        goto LABEL_24;
      IsBandBitLockerManaged = 0;
      v11 = 1;
    }
    FvepSetVolumeEncryptedCached(pszSrc, v11);
    goto LABEL_24;
  }
  v5 = GetLastError();
  IsBandBitLockerManaged = v5;
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return IsBandBitLockerManaged;
}

```

## disassembly

```asm
0x1400525bc  mov     [rsp-18h+arg_8], rbx
0x1400525c1  mov     [rsp-18h+arg_10], rsi
0x1400525c6  push    rbp
0x1400525c7  push    rdi
0x1400525c8  push    r14
0x1400525ca  mov     rbp, rsp
0x1400525cd  sub     rsp, 70h
0x1400525d1  mov     rax, cs:__security_cookie
0x1400525d8  xor     rax, rsp
0x1400525db  mov     [rbp+var_8], rax
0x1400525df  xor     eax, eax
0x1400525e1  lea     rdx, [rbp+var_30]
0x1400525e5  xorps   xmm0, xmm0
0x1400525e8  mov     [rbp+var_10], rax
0x1400525ec  movups  [rbp+OutBuffer], xmm0
0x1400525f0  mov     [rbp+BytesReturned], eax
0x1400525f3  mov     rsi, rcx
0x1400525f6  mov     [rbp+NumberOfBytesRead], eax
0x1400525f9  mov     [rbp+var_30], eax
0x1400525fc  call    FvepIsVolumeEncryptedCached
0x140052601  test    eax, eax
0x140052603  jz      short loc_140052612
0x140052605  xor     ebx, ebx
0x140052607  cmp     [rbp+var_30], ebx
0x14005260a  setz    bl
0x14005260d  jmp     loc_14005279D
0x140052612  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x14005261b  mov     r8d, 3; dwShareMode
0x140052621  mov     [rsp+70h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x140052629  xor     r9d, r9d; lpSecurityAttributes
0x14005262c  mov     edx, 80000000h; dwDesiredAccess
0x140052631  mov     [rsp+70h+dwCreationDisposition], r8d; dwCreationDisposition
0x140052636  mov     rcx, rsi; lpFileName
0x140052639  call    cs:__imp_CreateFileW
0x14005263f  mov     rdi, rax
0x140052642  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140052646  jnz     short loc_140052666
0x140052648  call    cs:__imp_GetLastError
0x14005264e  mov     ebx, eax
0x140052650  test    eax, eax
0x140052652  jle     loc_14005279D
0x140052658  movzx   ebx, ax
0x14005265b  or      ebx, 80070000h
0x140052661  jmp     loc_14005279D
0x140052666  mov     rcx, rdi; hDevice
0x140052669  call    FvepIsBandBitLockerManaged
0x14005266e  mov     ebx, eax
0x140052670  test    eax, eax
0x140052672  jz      loc_140052794
0x140052678  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x140052681  lea     rax, [rbp+BytesReturned]
0x140052685  mov     [rsp+70h+hTemplateFile], rax; lpBytesReturned
0x14005268a  xor     r9d, r9d; nInBufferSize
0x14005268d  lea     rax, [rbp+OutBuffer]
0x140052691  mov     [rsp+70h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x140052699  xor     r8d, r8d; lpInBuffer
0x14005269c  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpOutBuffer
0x1400526a1  mov     edx, 70000h; dwIoControlCode
0x1400526a6  mov     rcx, rdi; hDevice
0x1400526a9  call    cs:__imp_DeviceIoControl
0x1400526af  test    eax, eax
0x1400526b1  jnz     short loc_1400526D1
0x1400526b3  call    cs:__imp_GetLastError
0x1400526b9  mov     ebx, eax
0x1400526bb  test    eax, eax
0x1400526bd  jle     loc_140052794
0x1400526c3  movzx   ebx, ax
0x1400526c6  or      ebx, 80070000h
0x1400526cc  jmp     loc_140052794
0x1400526d1  mov     eax, dword ptr [rbp+var_10+4]
0x1400526d4  xor     ecx, ecx; lpAddress
0x1400526d6  add     eax, 1FFh
0x1400526db  mov     r8d, 3000h; flAllocationType
0x1400526e1  and     eax, 0FFFFFE00h
0x1400526e6  mov     edx, eax; dwSize
0x1400526e8  lea     r9d, [rcx+4]; flProtect
0x1400526ec  mov     ebx, eax
0x1400526ee  call    cs:__imp_VirtualAlloc
0x1400526f4  mov     r14, rax
0x1400526f7  test    rax, rax
0x1400526fa  jz      short loc_1400526B3
0x1400526fc  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x140052700  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x140052709  mov     r8d, ebx; nNumberOfBytesToRead
0x14005270c  mov     rdx, rax; lpBuffer
0x14005270f  mov     rcx, rdi; hFile
0x140052712  call    cs:__imp_ReadFile
0x140052718  test    eax, eax
0x14005271a  jnz     short loc_140052740
0x14005271c  call    cs:__imp_GetLastError
0x140052722  mov     ebx, eax
0x140052724  test    eax, eax
0x140052726  jle     short loc_140052731
0x140052728  movzx   ebx, ax
0x14005272b  or      ebx, 80070000h
0x140052731  cmp     ebx, 80310000h
0x140052737  jnz     short loc_140052783
0x140052739  xor     ebx, ebx
0x14005273b  lea     edx, [rbx+1]
0x14005273e  jmp     short loc_14005277B
0x140052740  mov     edx, [rbp+NumberOfBytesRead]
0x140052743  xor     r8d, r8d
0x140052746  mov     rcx, r14
0x140052749  call    FveCheckVolumeTypeEx
0x14005274e  lea     ecx, [rax-2]
0x140052751  cmp     ecx, 1
0x140052754  jbe     short loc_140052772
0x140052756  cmp     eax, 1
0x140052759  jnz     short loc_14005276B
0x14005275b  mov     rcx, rdi; hDevice
0x14005275e  call    FvepCheckForVolumeControlFiles
0x140052763  mov     ebx, eax
0x140052765  test    eax, eax
0x140052767  js      short loc_140052783
0x140052769  jmp     short loc_140052774
0x14005276b  mov     ebx, 1
0x140052770  jmp     short loc_140052774
0x140052772  xor     ebx, ebx
0x140052774  xor     edx, edx
0x140052776  test    ebx, ebx
0x140052778  setz    dl
0x14005277b  mov     rcx, rsi; pszSrc
0x14005277e  call    FvepSetVolumeEncryptedCached
0x140052783  xor     edx, edx; dwSize
0x140052785  mov     r8d, 8000h; dwFreeType
0x14005278b  mov     rcx, r14; lpAddress
0x14005278e  call    cs:__imp_VirtualFree
0x140052794  mov     rcx, rdi; hObject
0x140052797  call    cs:__imp_CloseHandle
0x14005279d  mov     eax, ebx
0x14005279f  mov     rcx, [rbp+var_8]
0x1400527a3  xor     rcx, rsp; StackCookie
0x1400527a6  call    __security_check_cookie
0x1400527ab  lea     r11, [rsp+70h+var_s0]
0x1400527b0  mov     rbx, [r11+28h]
0x1400527b4  mov     rsi, [r11+30h]
0x1400527b8  mov     rsp, r11
0x1400527bb  pop     r14
0x1400527bd  pop     rdi
0x1400527be  pop     rbp
0x1400527bf  retn
```
