# FvepIsVolumeEncryptedNoDriverTest

- ea: `0x1800320fc`
- end: `0x180032300`
- name: `FvepIsVolumeEncryptedNoDriverTest`
- size: `516`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180030fbc`

## callees

- `0x1800316e4`
- `0x180031d10`
- `0x180032008`
- `0x1800320fc`
- `0x180032308`
- `0x180032750`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032188`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003225c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032188`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003225c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800322d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800322d7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800321e9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800321e9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180032179`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180032179`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180032252`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180032252`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800322ce`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800322ce`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003222e`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003222e`

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
0x1800320fc  mov     [rsp-18h+arg_8], rbx
0x180032101  mov     [rsp-18h+arg_10], rsi
0x180032106  push    rbp
0x180032107  push    rdi
0x180032108  push    r14
0x18003210a  mov     rbp, rsp
0x18003210d  sub     rsp, 70h
0x180032111  mov     rax, cs:__security_cookie
0x180032118  xor     rax, rsp
0x18003211b  mov     [rbp+var_8], rax
0x18003211f  xor     eax, eax
0x180032121  lea     rdx, [rbp+var_30]
0x180032125  xorps   xmm0, xmm0
0x180032128  mov     [rbp+var_10], rax
0x18003212c  movups  [rbp+OutBuffer], xmm0
0x180032130  mov     [rbp+BytesReturned], eax
0x180032133  mov     rsi, rcx
0x180032136  mov     [rbp+NumberOfBytesRead], eax
0x180032139  mov     [rbp+var_30], eax
0x18003213c  call    FvepIsVolumeEncryptedCached
0x180032141  test    eax, eax
0x180032143  jz      short loc_180032152
0x180032145  xor     ebx, ebx
0x180032147  cmp     [rbp+var_30], ebx
0x18003214a  setz    bl
0x18003214d  jmp     loc_1800322DD
0x180032152  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x18003215b  mov     r8d, 3; dwShareMode
0x180032161  mov     [rsp+70h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x180032169  xor     r9d, r9d; lpSecurityAttributes
0x18003216c  mov     edx, 80000000h; dwDesiredAccess
0x180032171  mov     [rsp+70h+dwCreationDisposition], r8d; dwCreationDisposition
0x180032176  mov     rcx, rsi; lpFileName
0x180032179  call    cs:__imp_CreateFileW
0x18003217f  mov     rdi, rax
0x180032182  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032186  jnz     short loc_1800321A6
0x180032188  call    cs:__imp_GetLastError
0x18003218e  mov     ebx, eax
0x180032190  test    eax, eax
0x180032192  jle     loc_1800322DD
0x180032198  movzx   ebx, ax
0x18003219b  or      ebx, 80070000h
0x1800321a1  jmp     loc_1800322DD
0x1800321a6  mov     rcx, rdi; hDevice
0x1800321a9  call    FvepIsBandBitLockerManaged
0x1800321ae  mov     ebx, eax
0x1800321b0  test    eax, eax
0x1800321b2  jz      loc_1800322D4
0x1800321b8  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x1800321c1  lea     rax, [rbp+BytesReturned]
0x1800321c5  mov     [rsp+70h+hTemplateFile], rax; lpBytesReturned
0x1800321ca  xor     r9d, r9d; nInBufferSize
0x1800321cd  lea     rax, [rbp+OutBuffer]
0x1800321d1  mov     [rsp+70h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x1800321d9  xor     r8d, r8d; lpInBuffer
0x1800321dc  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpOutBuffer
0x1800321e1  mov     edx, 70000h; dwIoControlCode
0x1800321e6  mov     rcx, rdi; hDevice
0x1800321e9  call    cs:__imp_DeviceIoControl
0x1800321ef  test    eax, eax
0x1800321f1  jnz     short loc_180032211
0x1800321f3  call    cs:__imp_GetLastError
0x1800321f9  mov     ebx, eax
0x1800321fb  test    eax, eax
0x1800321fd  jle     loc_1800322D4
0x180032203  movzx   ebx, ax
0x180032206  or      ebx, 80070000h
0x18003220c  jmp     loc_1800322D4
0x180032211  mov     eax, dword ptr [rbp+var_10+4]
0x180032214  xor     ecx, ecx; lpAddress
0x180032216  add     eax, 1FFh
0x18003221b  mov     r8d, 3000h; flAllocationType
0x180032221  and     eax, 0FFFFFE00h
0x180032226  mov     edx, eax; dwSize
0x180032228  lea     r9d, [rcx+4]; flProtect
0x18003222c  mov     ebx, eax
0x18003222e  call    cs:__imp_VirtualAlloc
0x180032234  mov     r14, rax
0x180032237  test    rax, rax
0x18003223a  jz      short loc_1800321F3
0x18003223c  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180032240  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180032249  mov     r8d, ebx; nNumberOfBytesToRead
0x18003224c  mov     rdx, rax; lpBuffer
0x18003224f  mov     rcx, rdi; hFile
0x180032252  call    cs:__imp_ReadFile
0x180032258  test    eax, eax
0x18003225a  jnz     short loc_180032280
0x18003225c  call    cs:__imp_GetLastError
0x180032262  mov     ebx, eax
0x180032264  test    eax, eax
0x180032266  jle     short loc_180032271
0x180032268  movzx   ebx, ax
0x18003226b  or      ebx, 80070000h
0x180032271  cmp     ebx, 80310000h
0x180032277  jnz     short loc_1800322C3
0x180032279  xor     ebx, ebx
0x18003227b  lea     edx, [rbx+1]
0x18003227e  jmp     short loc_1800322BB
0x180032280  mov     edx, [rbp+NumberOfBytesRead]
0x180032283  xor     r8d, r8d
0x180032286  mov     rcx, r14
0x180032289  call    FveCheckVolumeTypeEx
0x18003228e  lea     ecx, [rax-2]
0x180032291  cmp     ecx, 1
0x180032294  jbe     short loc_1800322B2
0x180032296  cmp     eax, 1
0x180032299  jnz     short loc_1800322AB
0x18003229b  mov     rcx, rdi; hDevice
0x18003229e  call    FvepCheckForVolumeControlFiles
0x1800322a3  mov     ebx, eax
0x1800322a5  test    eax, eax
0x1800322a7  js      short loc_1800322C3
0x1800322a9  jmp     short loc_1800322B4
0x1800322ab  mov     ebx, 1
0x1800322b0  jmp     short loc_1800322B4
0x1800322b2  xor     ebx, ebx
0x1800322b4  xor     edx, edx
0x1800322b6  test    ebx, ebx
0x1800322b8  setz    dl
0x1800322bb  mov     rcx, rsi; pszSrc
0x1800322be  call    FvepSetVolumeEncryptedCached
0x1800322c3  xor     edx, edx; dwSize
0x1800322c5  mov     r8d, 8000h; dwFreeType
0x1800322cb  mov     rcx, r14; lpAddress
0x1800322ce  call    cs:__imp_VirtualFree
0x1800322d4  mov     rcx, rdi; hObject
0x1800322d7  call    cs:__imp_CloseHandle
0x1800322dd  mov     eax, ebx
0x1800322df  mov     rcx, [rbp+var_8]
0x1800322e3  xor     rcx, rsp; StackCookie
0x1800322e6  call    __security_check_cookie
0x1800322eb  lea     r11, [rsp+70h+var_s0]
0x1800322f0  mov     rbx, [r11+28h]
0x1800322f4  mov     rsi, [r11+30h]
0x1800322f8  mov     rsp, r11
0x1800322fb  pop     r14
0x1800322fd  pop     rdi
0x1800322fe  pop     rbp
0x1800322ff  retn
```
