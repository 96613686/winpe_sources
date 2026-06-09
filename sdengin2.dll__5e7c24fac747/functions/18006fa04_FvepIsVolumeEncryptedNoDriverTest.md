# FvepIsVolumeEncryptedNoDriverTest

- ea: `0x18006fa04`
- end: `0x18006fc08`
- name: `FvepIsVolumeEncryptedNoDriverTest`
- size: `516`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18006e84c`

## callees

- `0x18006efec`
- `0x18006f618`
- `0x18006f910`
- `0x18006fa04`
- `0x18006fc10`
- `0x1800c8178`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18006fb5a`
- `KERNEL32!ReadFile` at `0x18006fb5a`
- `KERNEL32!VirtualAlloc` at `0x18006fb36`
- `KERNEL32!VirtualAlloc` at `0x18006fb36`
- `KERNEL32!CreateFileW` at `0x18006fa81`
- `KERNEL32!CreateFileW` at `0x18006fa81`
- `KERNEL32!GetLastError` at `0x18006fa90`
- `KERNEL32!GetLastError` at `0x18006fafb`
- `KERNEL32!GetLastError` at `0x18006fb64`
- `KERNEL32!GetLastError` at `0x18006fa90`
- `KERNEL32!GetLastError` at `0x18006fafb`
- `KERNEL32!GetLastError` at `0x18006fb64`
- `KERNEL32!CloseHandle` at `0x18006fbdf`
- `KERNEL32!CloseHandle` at `0x18006fbdf`
- `KERNEL32!DeviceIoControl` at `0x18006faf1`
- `KERNEL32!DeviceIoControl` at `0x18006faf1`
- `KERNEL32!VirtualFree` at `0x18006fbd6`
- `KERNEL32!VirtualFree` at `0x18006fbd6`

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
0x18006fa04  mov     [rsp-18h+arg_8], rbx
0x18006fa09  mov     [rsp-18h+arg_10], rsi
0x18006fa0e  push    rbp
0x18006fa0f  push    rdi
0x18006fa10  push    r14
0x18006fa12  mov     rbp, rsp
0x18006fa15  sub     rsp, 70h
0x18006fa19  mov     rax, cs:__security_cookie
0x18006fa20  xor     rax, rsp
0x18006fa23  mov     [rbp+var_8], rax
0x18006fa27  xor     eax, eax
0x18006fa29  lea     rdx, [rbp+var_30]
0x18006fa2d  xorps   xmm0, xmm0
0x18006fa30  mov     [rbp+var_10], rax
0x18006fa34  movups  [rbp+OutBuffer], xmm0
0x18006fa38  mov     [rbp+BytesReturned], eax
0x18006fa3b  mov     rsi, rcx
0x18006fa3e  mov     [rbp+NumberOfBytesRead], eax
0x18006fa41  mov     [rbp+var_30], eax
0x18006fa44  call    FvepIsVolumeEncryptedCached
0x18006fa49  test    eax, eax
0x18006fa4b  jz      short loc_18006FA5A
0x18006fa4d  xor     ebx, ebx
0x18006fa4f  cmp     [rbp+var_30], ebx
0x18006fa52  setz    bl
0x18006fa55  jmp     loc_18006FBE5
0x18006fa5a  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x18006fa63  mov     r8d, 3; dwShareMode
0x18006fa69  mov     [rsp+70h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x18006fa71  xor     r9d, r9d; lpSecurityAttributes
0x18006fa74  mov     edx, 80000000h; dwDesiredAccess
0x18006fa79  mov     [rsp+70h+dwCreationDisposition], r8d; dwCreationDisposition
0x18006fa7e  mov     rcx, rsi; lpFileName
0x18006fa81  call    cs:__imp_CreateFileW
0x18006fa87  mov     rdi, rax
0x18006fa8a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006fa8e  jnz     short loc_18006FAAE
0x18006fa90  call    cs:__imp_GetLastError
0x18006fa96  mov     ebx, eax
0x18006fa98  test    eax, eax
0x18006fa9a  jle     loc_18006FBE5
0x18006faa0  movzx   ebx, ax
0x18006faa3  or      ebx, 80070000h
0x18006faa9  jmp     loc_18006FBE5
0x18006faae  mov     rcx, rdi; hDevice
0x18006fab1  call    FvepIsBandBitLockerManaged
0x18006fab6  mov     ebx, eax
0x18006fab8  test    eax, eax
0x18006faba  jz      loc_18006FBDC
0x18006fac0  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x18006fac9  lea     rax, [rbp+BytesReturned]
0x18006facd  mov     [rsp+70h+hTemplateFile], rax; lpBytesReturned
0x18006fad2  xor     r9d, r9d; nInBufferSize
0x18006fad5  lea     rax, [rbp+OutBuffer]
0x18006fad9  mov     [rsp+70h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x18006fae1  xor     r8d, r8d; lpInBuffer
0x18006fae4  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpOutBuffer
0x18006fae9  mov     edx, 70000h; dwIoControlCode
0x18006faee  mov     rcx, rdi; hDevice
0x18006faf1  call    cs:__imp_DeviceIoControl
0x18006faf7  test    eax, eax
0x18006faf9  jnz     short loc_18006FB19
0x18006fafb  call    cs:__imp_GetLastError
0x18006fb01  mov     ebx, eax
0x18006fb03  test    eax, eax
0x18006fb05  jle     loc_18006FBDC
0x18006fb0b  movzx   ebx, ax
0x18006fb0e  or      ebx, 80070000h
0x18006fb14  jmp     loc_18006FBDC
0x18006fb19  mov     eax, dword ptr [rbp+var_10+4]
0x18006fb1c  xor     ecx, ecx; lpAddress
0x18006fb1e  add     eax, 1FFh
0x18006fb23  mov     r8d, 3000h; flAllocationType
0x18006fb29  and     eax, 0FFFFFE00h
0x18006fb2e  mov     edx, eax; dwSize
0x18006fb30  lea     r9d, [rcx+4]; flProtect
0x18006fb34  mov     ebx, eax
0x18006fb36  call    cs:__imp_VirtualAlloc
0x18006fb3c  mov     r14, rax
0x18006fb3f  test    rax, rax
0x18006fb42  jz      short loc_18006FAFB
0x18006fb44  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18006fb48  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x18006fb51  mov     r8d, ebx; nNumberOfBytesToRead
0x18006fb54  mov     rdx, rax; lpBuffer
0x18006fb57  mov     rcx, rdi; hFile
0x18006fb5a  call    cs:__imp_ReadFile
0x18006fb60  test    eax, eax
0x18006fb62  jnz     short loc_18006FB88
0x18006fb64  call    cs:__imp_GetLastError
0x18006fb6a  mov     ebx, eax
0x18006fb6c  test    eax, eax
0x18006fb6e  jle     short loc_18006FB79
0x18006fb70  movzx   ebx, ax
0x18006fb73  or      ebx, 80070000h
0x18006fb79  cmp     ebx, 80310000h
0x18006fb7f  jnz     short loc_18006FBCB
0x18006fb81  xor     ebx, ebx
0x18006fb83  lea     edx, [rbx+1]
0x18006fb86  jmp     short loc_18006FBC3
0x18006fb88  mov     edx, [rbp+NumberOfBytesRead]
0x18006fb8b  xor     r8d, r8d
0x18006fb8e  mov     rcx, r14
0x18006fb91  call    FveCheckVolumeTypeEx
0x18006fb96  lea     ecx, [rax-2]
0x18006fb99  cmp     ecx, 1
0x18006fb9c  jbe     short loc_18006FBBA
0x18006fb9e  cmp     eax, 1
0x18006fba1  jnz     short loc_18006FBB3
0x18006fba3  mov     rcx, rdi; hDevice
0x18006fba6  call    FvepCheckForVolumeControlFiles
0x18006fbab  mov     ebx, eax
0x18006fbad  test    eax, eax
0x18006fbaf  js      short loc_18006FBCB
0x18006fbb1  jmp     short loc_18006FBBC
0x18006fbb3  mov     ebx, 1
0x18006fbb8  jmp     short loc_18006FBBC
0x18006fbba  xor     ebx, ebx
0x18006fbbc  xor     edx, edx
0x18006fbbe  test    ebx, ebx
0x18006fbc0  setz    dl
0x18006fbc3  mov     rcx, rsi; pszSrc
0x18006fbc6  call    FvepSetVolumeEncryptedCached
0x18006fbcb  xor     edx, edx; dwSize
0x18006fbcd  mov     r8d, 8000h; dwFreeType
0x18006fbd3  mov     rcx, r14; lpAddress
0x18006fbd6  call    cs:__imp_VirtualFree
0x18006fbdc  mov     rcx, rdi; hObject
0x18006fbdf  call    cs:__imp_CloseHandle
0x18006fbe5  mov     eax, ebx
0x18006fbe7  mov     rcx, [rbp+var_8]
0x18006fbeb  xor     rcx, rsp; StackCookie
0x18006fbee  call    __security_check_cookie
0x18006fbf3  lea     r11, [rsp+70h+var_s0]
0x18006fbf8  mov     rbx, [r11+28h]
0x18006fbfc  mov     rsi, [r11+30h]
0x18006fc00  mov     rsp, r11
0x18006fc03  pop     r14
0x18006fc05  pop     rdi
0x18006fc06  pop     rbp
0x18006fc07  retn
```
