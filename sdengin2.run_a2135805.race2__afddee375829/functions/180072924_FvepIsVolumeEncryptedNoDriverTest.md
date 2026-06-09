# FvepIsVolumeEncryptedNoDriverTest

- ea: `0x180072924`
- end: `0x180072b5f`
- name: `FvepIsVolumeEncryptedNoDriverTest`
- size: `571`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800715a8`

## callees

- `0x180071e20`
- `0x1800724ec`
- `0x18007281c`
- `0x180072924`
- `0x180072b68`
- `0x1800cde00`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!ReadFile` at `0x180072a98`
- `KERNEL32!ReadFile` at `0x180072a98`
- `KERNEL32!VirtualAlloc` at `0x180072a6e`
- `KERNEL32!VirtualAlloc` at `0x180072a6e`
- `KERNEL32!CreateFileW` at `0x1800729a1`
- `KERNEL32!CreateFileW` at `0x1800729a1`
- `KERNEL32!GetLastError` at `0x1800729b6`
- `KERNEL32!GetLastError` at `0x180072a2d`
- `KERNEL32!GetLastError` at `0x180072aa8`
- `KERNEL32!GetLastError` at `0x1800729b6`
- `KERNEL32!GetLastError` at `0x180072a2d`
- `KERNEL32!GetLastError` at `0x180072aa8`
- `KERNEL32!CloseHandle` at `0x180072b2f`
- `KERNEL32!CloseHandle` at `0x180072b2f`
- `KERNEL32!DeviceIoControl` at `0x180072a1d`
- `KERNEL32!DeviceIoControl` at `0x180072a1d`
- `KERNEL32!VirtualFree` at `0x180072b20`
- `KERNEL32!VirtualFree` at `0x180072b20`

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
0x180072924  mov     [rsp-18h+arg_8], rbx
0x180072929  mov     [rsp-18h+arg_10], rsi
0x18007292e  push    rbp
0x18007292f  push    rdi
0x180072930  push    r14
0x180072932  mov     rbp, rsp
0x180072935  sub     rsp, 70h
0x180072939  mov     rax, cs:__security_cookie
0x180072940  xor     rax, rsp
0x180072943  mov     [rbp+var_8], rax
0x180072947  xor     eax, eax
0x180072949  lea     rdx, [rbp+var_30]
0x18007294d  xorps   xmm0, xmm0
0x180072950  mov     [rbp+var_10], rax
0x180072954  movups  [rbp+OutBuffer], xmm0
0x180072958  mov     [rbp+BytesReturned], eax
0x18007295b  mov     rsi, rcx
0x18007295e  mov     [rbp+NumberOfBytesRead], eax
0x180072961  mov     [rbp+var_30], eax
0x180072964  call    FvepIsVolumeEncryptedCached
0x180072969  test    eax, eax
0x18007296b  jz      short loc_18007297A
0x18007296d  xor     ebx, ebx
0x18007296f  cmp     [rbp+var_30], ebx
0x180072972  setz    bl
0x180072975  jmp     loc_180072B3B
0x18007297a  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180072983  mov     r8d, 3; dwShareMode
0x180072989  mov     [rsp+70h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x180072991  xor     r9d, r9d; lpSecurityAttributes
0x180072994  mov     edx, 80000000h; dwDesiredAccess
0x180072999  mov     [rsp+70h+dwCreationDisposition], r8d; dwCreationDisposition
0x18007299e  mov     rcx, rsi; lpFileName
0x1800729a1  call    cs:__imp_CreateFileW
0x1800729a8  nop     dword ptr [rax+rax+00h]
0x1800729ad  mov     rdi, rax
0x1800729b0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800729b4  jnz     short loc_1800729DA
0x1800729b6  call    cs:__imp_GetLastError
0x1800729bd  nop     dword ptr [rax+rax+00h]
0x1800729c2  mov     ebx, eax
0x1800729c4  test    eax, eax
0x1800729c6  jle     loc_180072B3B
0x1800729cc  movzx   ebx, ax
0x1800729cf  or      ebx, 80070000h
0x1800729d5  jmp     loc_180072B3B
0x1800729da  mov     rcx, rdi; hDevice
0x1800729dd  call    FvepIsBandBitLockerManaged
0x1800729e2  mov     ebx, eax
0x1800729e4  test    eax, eax
0x1800729e6  jz      loc_180072B2C
0x1800729ec  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x1800729f5  lea     rax, [rbp+BytesReturned]
0x1800729f9  mov     [rsp+70h+hTemplateFile], rax; lpBytesReturned
0x1800729fe  xor     r9d, r9d; nInBufferSize
0x180072a01  lea     rax, [rbp+OutBuffer]
0x180072a05  mov     [rsp+70h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x180072a0d  xor     r8d, r8d; lpInBuffer
0x180072a10  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpOutBuffer
0x180072a15  mov     edx, 70000h; dwIoControlCode
0x180072a1a  mov     rcx, rdi; hDevice
0x180072a1d  call    cs:__imp_DeviceIoControl
0x180072a24  nop     dword ptr [rax+rax+00h]
0x180072a29  test    eax, eax
0x180072a2b  jnz     short loc_180072A51
0x180072a2d  call    cs:__imp_GetLastError
0x180072a34  nop     dword ptr [rax+rax+00h]
0x180072a39  mov     ebx, eax
0x180072a3b  test    eax, eax
0x180072a3d  jle     loc_180072B2C
0x180072a43  movzx   ebx, ax
0x180072a46  or      ebx, 80070000h
0x180072a4c  jmp     loc_180072B2C
0x180072a51  mov     eax, dword ptr [rbp+var_10+4]
0x180072a54  xor     ecx, ecx; lpAddress
0x180072a56  add     eax, 1FFh
0x180072a5b  mov     r8d, 3000h; flAllocationType
0x180072a61  and     eax, 0FFFFFE00h
0x180072a66  mov     edx, eax; dwSize
0x180072a68  lea     r9d, [rcx+4]; flProtect
0x180072a6c  mov     ebx, eax
0x180072a6e  call    cs:__imp_VirtualAlloc
0x180072a75  nop     dword ptr [rax+rax+00h]
0x180072a7a  mov     r14, rax
0x180072a7d  test    rax, rax
0x180072a80  jz      short loc_180072A2D
0x180072a82  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180072a86  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180072a8f  mov     r8d, ebx; nNumberOfBytesToRead
0x180072a92  mov     rdx, rax; lpBuffer
0x180072a95  mov     rcx, rdi; hFile
0x180072a98  call    cs:__imp_ReadFile
0x180072a9f  nop     dword ptr [rax+rax+00h]
0x180072aa4  test    eax, eax
0x180072aa6  jnz     short loc_180072AD2
0x180072aa8  call    cs:__imp_GetLastError
0x180072aaf  nop     dword ptr [rax+rax+00h]
0x180072ab4  mov     ebx, eax
0x180072ab6  test    eax, eax
0x180072ab8  jle     short loc_180072AC3
0x180072aba  movzx   ebx, ax
0x180072abd  or      ebx, 80070000h
0x180072ac3  cmp     ebx, 80310000h
0x180072ac9  jnz     short loc_180072B15
0x180072acb  xor     ebx, ebx
0x180072acd  lea     edx, [rbx+1]
0x180072ad0  jmp     short loc_180072B0D
0x180072ad2  mov     edx, [rbp+NumberOfBytesRead]
0x180072ad5  xor     r8d, r8d
0x180072ad8  mov     rcx, r14
0x180072adb  call    FveCheckVolumeTypeEx
0x180072ae0  lea     ecx, [rax-2]
0x180072ae3  cmp     ecx, 1
0x180072ae6  jbe     short loc_180072B04
0x180072ae8  cmp     eax, 1
0x180072aeb  jnz     short loc_180072AFD
0x180072aed  mov     rcx, rdi; hDevice
0x180072af0  call    FvepCheckForVolumeControlFiles
0x180072af5  mov     ebx, eax
0x180072af7  test    eax, eax
0x180072af9  js      short loc_180072B15
0x180072afb  jmp     short loc_180072B06
0x180072afd  mov     ebx, 1
0x180072b02  jmp     short loc_180072B06
0x180072b04  xor     ebx, ebx
0x180072b06  xor     edx, edx
0x180072b08  test    ebx, ebx
0x180072b0a  setz    dl
0x180072b0d  mov     rcx, rsi; pszSrc
0x180072b10  call    FvepSetVolumeEncryptedCached
0x180072b15  xor     edx, edx; dwSize
0x180072b17  mov     r8d, 8000h; dwFreeType
0x180072b1d  mov     rcx, r14; lpAddress
0x180072b20  call    cs:__imp_VirtualFree
0x180072b27  nop     dword ptr [rax+rax+00h]
0x180072b2c  mov     rcx, rdi; hObject
0x180072b2f  call    cs:__imp_CloseHandle
0x180072b36  nop     dword ptr [rax+rax+00h]
0x180072b3b  mov     eax, ebx
0x180072b3d  mov     rcx, [rbp+var_8]
0x180072b41  xor     rcx, rsp; StackCookie
0x180072b44  call    __security_check_cookie
0x180072b49  lea     r11, [rsp+70h+var_s0]
0x180072b4e  mov     rbx, [r11+28h]
0x180072b52  mov     rsi, [r11+30h]
0x180072b56  mov     rsp, r11
0x180072b59  pop     r14
0x180072b5b  pop     rdi
0x180072b5c  pop     rbp
0x180072b5d  retn
```
