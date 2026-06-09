# GetAMFileID(ushort const *,_GUID *)

- ea: `0x1800052f0`
- end: `0x18000544d`
- name: `?GetAMFileID@@YAJPEBGPEAU_GUID@@@Z`
- size: `349`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800056fc`

## callees

- `0x1800034b0`
- `0x1800040b8`
- `0x1800052f0`
- `0x1800055cc`
- `0x1800ff514`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005359`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005359`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180005390`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800053da`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180005390`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800053da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053f4`

## pseudocode

```c
__int64 __fastcall GetAMFileID(LPCWSTR lpFileName, struct _GUID *a2)
{
  HANDLE FileW; // rax
  void *v5; // rdi
  unsigned int Win32Error; // ebx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-88h] BYREF
  _BYTE Buffer[16]; // [rsp+50h] [rbp-78h] BYREF
  struct _GUID v10; // [rsp+60h] [rbp-68h]
  _BYTE v11[16]; // [rsp+A0h] [rbp-28h] BYREF

  NumberOfBytesRead = 0;
  memset_0(Buffer, 0, 0x60u);
  FileW = CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v5 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( !ReadFile(FileW, Buffer, 0x50u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 80 )
      goto LABEL_8;
    if ( !memcmp_0(Buffer, &ACOUSTICMODELMAGIC_6, 0x10u) )
    {
      if ( !ReadFile(v5, v11, 0x10u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 16 )
      {
LABEL_8:
        Win32Error = HrFromLastWin32Error();
LABEL_9:
        CloseHandle(v5);
        return Win32Error;
      }
    }
    else if ( memcmp_0(Buffer, &ACOUSTICMODELMAGIC_5, 0x10u) )
    {
      Win32Error = 1;
      goto LABEL_9;
    }
    Win32Error = 0;
    *a2 = v10;
    goto LABEL_9;
  }
  return (unsigned int)HrFromLastWin32Error();
}

```

## disassembly

```asm
0x1800052f0  mov     [rsp+arg_10], rbx
0x1800052f5  mov     [rsp+arg_18], rsi
0x1800052fa  push    rdi
0x1800052fb  sub     rsp, 0C0h
0x180005302  mov     rax, cs:__security_cookie
0x180005309  xor     rax, rsp
0x18000530c  mov     [rsp+0C8h+var_18], rax
0x180005314  mov     rsi, rdx
0x180005317  mov     [rsp+0C8h+NumberOfBytesRead], 0
0x18000531f  xor     edx, edx; Val
0x180005321  mov     rbx, rcx
0x180005324  lea     rcx, [rsp+0C8h+Buffer]; void *
0x180005329  lea     r8d, [rdx+60h]; Size
0x18000532d  call    memset_0
0x180005332  mov     r8d, 3; dwShareMode
0x180005338  mov     [rsp+0C8h+hTemplateFile], 0; hTemplateFile
0x180005341  mov     [rsp+0C8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180005349  xor     r9d, r9d; lpSecurityAttributes
0x18000534c  mov     edx, 80000000h; dwDesiredAccess
0x180005351  mov     [rsp+0C8h+dwCreationDisposition], r8d; dwCreationDisposition
0x180005356  mov     rcx, rbx; lpFileName
0x180005359  call    cs:__imp_CreateFileW
0x18000535f  mov     rdi, rax
0x180005362  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005366  jnz     short loc_180005374
0x180005368  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000536d  mov     ebx, eax
0x18000536f  jmp     loc_1800053FA
0x180005374  lea     r9, [rsp+0C8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180005379  mov     qword ptr [rsp+0C8h+dwCreationDisposition], 0; lpOverlapped
0x180005382  mov     r8d, 50h ; 'P'; nNumberOfBytesToRead
0x180005388  lea     rdx, [rsp+0C8h+Buffer]; lpBuffer
0x18000538d  mov     rcx, rdi; hFile
0x180005390  call    cs:__imp_ReadFile
0x180005396  test    eax, eax
0x180005398  jz      short loc_1800053EA
0x18000539a  cmp     [rsp+0C8h+NumberOfBytesRead], 50h ; 'P'
0x18000539f  jnz     short loc_1800053EA
0x1800053a1  mov     ebx, 10h
0x1800053a6  lea     rdx, ACOUSTICMODELMAGIC_6; Buf2
0x1800053ad  mov     r8d, ebx; Size
0x1800053b0  lea     rcx, [rsp+0C8h+Buffer]; Buf1
0x1800053b5  call    memcmp_0
0x1800053ba  test    eax, eax
0x1800053bc  jnz     short loc_180005421
0x1800053be  lea     r9, [rsp+0C8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800053c3  mov     qword ptr [rsp+0C8h+dwCreationDisposition], 0; lpOverlapped
0x1800053cc  mov     r8d, ebx; nNumberOfBytesToRead
0x1800053cf  lea     rdx, [rsp+0C8h+var_28]; lpBuffer
0x1800053d7  mov     rcx, rdi; hFile
0x1800053da  call    cs:__imp_ReadFile
0x1800053e0  test    eax, eax
0x1800053e2  jz      short loc_1800053EA
0x1800053e4  cmp     [rsp+0C8h+NumberOfBytesRead], ebx
0x1800053e8  jz      short loc_180005440
0x1800053ea  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800053ef  mov     ebx, eax
0x1800053f1  mov     rcx, rdi; hObject
0x1800053f4  call    cs:__imp_CloseHandle
0x1800053fa  mov     eax, ebx
0x1800053fc  mov     rcx, [rsp+0C8h+var_18]
0x180005404  xor     rcx, rsp; StackCookie
0x180005407  call    __security_check_cookie
0x18000540c  lea     r11, [rsp+0C8h+var_8]
0x180005414  mov     rbx, [r11+20h]
0x180005418  mov     rsi, [r11+28h]
0x18000541c  mov     rsp, r11
0x18000541f  pop     rdi
0x180005420  retn
0x180005421  mov     r8, rbx; Size
0x180005424  lea     rdx, ACOUSTICMODELMAGIC_5; Buf2
0x18000542b  lea     rcx, [rsp+0C8h+Buffer]; Buf1
0x180005430  call    memcmp_0
0x180005435  test    eax, eax
0x180005437  jz      short loc_180005440
0x180005439  mov     ebx, 1
0x18000543e  jmp     short loc_1800053F1
0x180005440  movaps  xmm0, [rsp+0C8h+var_68]
0x180005445  xor     ebx, ebx
0x180005447  movdqu  xmmword ptr [rsi], xmm0
0x18000544b  jmp     short loc_1800053F1
```
