# FloppyDiskCreationOperation::RunTaskInternal(void)

- ea: `0x1403c7ec0`
- end: `0x1403c8132`
- name: `?RunTaskInternal@FloppyDiskCreationOperation@@UEAAJXZ`
- size: `626`
- prototype: `__int64 __fastcall(FloppyDiskCreationOperation *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task`

## callees

- `0x1401be65c`
- `0x1403c7ec0`
- `0x1403c8138`
- `0x1404828e0`
- `0x1404835a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1403c806a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1403c806a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1403c7fee`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1403c7fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403c7f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403c7f77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403c7f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403c7fd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403c804c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403c7f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403c7f77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403c7f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403c7fd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403c804c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1403c8079`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1403c8079`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1403c7f24`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1403c7f24`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1403c8037`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1403c8037`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1403c7f6b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1403c7fc9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1403c7f6b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1403c7fc9`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1403c7fae`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1403c7fae`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1403c80a4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1403c80a4`

## pseudocode

```c
__int64 __fastcall FloppyDiskCreationOperation::RunTaskInternal(FloppyDiskCreationOperation *this)
{
  const WCHAR **v1; // rsi
  const WCHAR *v2; // rcx
  HANDLE FileW; // rax
  void *v4; // rbx
  signed int LastError; // eax
  signed int v6; // edi
  signed int v7; // eax
  void *v8; // rax
  void *v9; // rbp
  unsigned int i; // r14d
  signed int v11; // eax
  const WCHAR *v12; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-88h] BYREF
  __int64 v15[4]; // [rsp+48h] [rbp-80h] BYREF
  __int64 v16[4]; // [rsp+68h] [rbp-60h] BYREF

  v1 = (const WCHAR **)((char *)this + 168);
  NumberOfBytesWritten = 0;
  if ( *((_QWORD *)this + 24) <= 7u )
    v2 = (const WCHAR *)((char *)this + 168);
  else
    v2 = *v1;
  FileW = CreateFileW(v2, 0xC0000000, 0, 0, 1u, 0x100080u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    SetFilePointer(FileW, 1474560, 0, 0);
    if ( GetLastError() || !SetEndOfFile(v4) || (SetFilePointer(v4, 0, 0, 0), GetLastError()) )
    {
      v7 = GetLastError();
      v6 = v7;
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      v8 = malloc(0x4000u);
      v9 = v8;
      if ( v8 )
      {
        v6 = 0;
        memset_0(v8, 0, 0x4000u);
        for ( i = 0; i < 0x168000; i += 0x4000 )
        {
          if ( !WriteFile(v4, v9, 0x4000u, &NumberOfBytesWritten, 0) )
          {
            v11 = GetLastError();
            v6 = v11;
            if ( v11 > 0 )
              v6 = (unsigned __int16)v11 | 0x80070000;
            break;
          }
        }
        free(v9);
      }
      else
      {
        v6 = -2147024882;
      }
    }
    CloseHandle(v4);
  }
  if ( v6 < 0 )
  {
    if ( v6 != -2147024816 )
    {
      if ( (unsigned __int64)v1[3] <= 7 )
        v12 = (const WCHAR *)v1;
      else
        v12 = *v1;
      DeleteFileW(v12);
    }
    _snwprintf_s<16>(v16, 16, L"%%%%%u", v6 & 0xEFFFFFFF);
    _snwprintf_s<16>(v15, 16, L"0x%08X", v6 & 0xEFFFFFFF);
    VmEventWriteAndReport<unsigned short (&)[16],unsigned short (&)[16],std::wstring &>(
      (struct _EVENT_DESCRIPTOR *)&MSVHDSVC_VFD_CREATION_FAILED,
      5u,
      (__int64)v16,
      (__int64)v15,
      (__int64)v1);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1403c7ec0  push    rbx
0x1403c7ec2  push    rbp
0x1403c7ec3  push    rsi
0x1403c7ec4  push    rdi
0x1403c7ec5  push    r12
0x1403c7ec7  push    r14
0x1403c7ec9  sub     rsp, 98h
0x1403c7ed0  mov     rax, cs:__security_cookie
0x1403c7ed7  xor     rax, rsp
0x1403c7eda  mov     [rsp+0C8h+var_40], rax
0x1403c7ee2  lea     rsi, [rcx+0A8h]
0x1403c7ee9  mov     [rsp+0C8h+NumberOfBytesWritten], 0
0x1403c7ef1  cmp     qword ptr [rsi+18h], 7
0x1403c7ef6  jbe     short loc_1403C7EFD
0x1403c7ef8  mov     rcx, [rsi]
0x1403c7efb  jmp     short loc_1403C7F00
0x1403c7efd  mov     rcx, rsi; lpFileName
0x1403c7f00  mov     [rsp+0C8h+hTemplateFile], 0; hTemplateFile
0x1403c7f09  xor     r9d, r9d; lpSecurityAttributes
0x1403c7f0c  mov     [rsp+0C8h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1403c7f14  xor     r8d, r8d; dwShareMode
0x1403c7f17  mov     edx, 0C0000000h; dwDesiredAccess
0x1403c7f1c  mov     [rsp+0C8h+dwCreationDisposition], 1; dwCreationDisposition
0x1403c7f24  call    cs:__imp_CreateFileW
0x1403c7f2b  nop     dword ptr [rax+rax+00h]
0x1403c7f30  mov     rbx, rax
0x1403c7f33  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1403c7f37  jnz     short loc_1403C7F5D
0x1403c7f39  call    cs:__imp_GetLastError
0x1403c7f40  nop     dword ptr [rax+rax+00h]
0x1403c7f45  mov     edi, eax
0x1403c7f47  test    eax, eax
0x1403c7f49  jle     loc_1403C8085
0x1403c7f4f  movzx   edi, ax
0x1403c7f52  or      edi, 80070000h
0x1403c7f58  jmp     loc_1403C8085
0x1403c7f5d  xor     r9d, r9d; dwMoveMethod
0x1403c7f60  xor     r8d, r8d; lpDistanceToMoveHigh
0x1403c7f63  mov     edx, 168000h; lDistanceToMove
0x1403c7f68  mov     rcx, rbx; hFile
0x1403c7f6b  call    cs:__imp_SetFilePointer
0x1403c7f72  nop     dword ptr [rax+rax+00h]
0x1403c7f77  call    cs:__imp_GetLastError
0x1403c7f7e  nop     dword ptr [rax+rax+00h]
0x1403c7f83  test    eax, eax
0x1403c7f85  jz      short loc_1403C7FAB
0x1403c7f87  call    cs:__imp_GetLastError
0x1403c7f8e  nop     dword ptr [rax+rax+00h]
0x1403c7f93  mov     edi, eax
0x1403c7f95  test    eax, eax
0x1403c7f97  jle     loc_1403C8076
0x1403c7f9d  movzx   edi, ax
0x1403c7fa0  or      edi, 80070000h
0x1403c7fa6  jmp     loc_1403C8076
0x1403c7fab  mov     rcx, rbx; hFile
0x1403c7fae  call    cs:__imp_SetEndOfFile
0x1403c7fb5  nop     dword ptr [rax+rax+00h]
0x1403c7fba  test    eax, eax
0x1403c7fbc  jz      short loc_1403C7F87
0x1403c7fbe  xor     r9d, r9d; dwMoveMethod
0x1403c7fc1  xor     r8d, r8d; lpDistanceToMoveHigh
0x1403c7fc4  xor     edx, edx; lDistanceToMove
0x1403c7fc6  mov     rcx, rbx; hFile
0x1403c7fc9  call    cs:__imp_SetFilePointer
0x1403c7fd0  nop     dword ptr [rax+rax+00h]
0x1403c7fd5  call    cs:__imp_GetLastError
0x1403c7fdc  nop     dword ptr [rax+rax+00h]
0x1403c7fe1  test    eax, eax
0x1403c7fe3  jnz     short loc_1403C7F87
0x1403c7fe5  mov     r12d, 4000h
0x1403c7feb  mov     ecx, r12d; Size
0x1403c7fee  call    cs:__imp_malloc
0x1403c7ff5  nop     dword ptr [rax+rax+00h]
0x1403c7ffa  mov     rbp, rax
0x1403c7ffd  test    rax, rax
0x1403c8000  jnz     short loc_1403C8009
0x1403c8002  mov     edi, 8007000Eh
0x1403c8007  jmp     short loc_1403C8076
0x1403c8009  mov     r8, r12; Size
0x1403c800c  xor     edx, edx; Val
0x1403c800e  mov     rcx, rbp; void *
0x1403c8011  xor     edi, edi
0x1403c8013  call    memset_0
0x1403c8018  xor     r14d, r14d
0x1403c801b  cmp     r14d, 168000h
0x1403c8022  jnb     short loc_1403C8067
0x1403c8024  lea     r9, [rsp+0C8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1403c8029  mov     qword ptr [rsp+0C8h+dwCreationDisposition], rdi; lpOverlapped
0x1403c802e  mov     r8d, r12d; nNumberOfBytesToWrite
0x1403c8031  mov     rdx, rbp; lpBuffer
0x1403c8034  mov     rcx, rbx; hFile
0x1403c8037  call    cs:__imp_WriteFile
0x1403c803e  nop     dword ptr [rax+rax+00h]
0x1403c8043  test    eax, eax
0x1403c8045  jz      short loc_1403C804C
0x1403c8047  add     r14d, r12d
0x1403c804a  jmp     short loc_1403C801B
0x1403c804c  call    cs:__imp_GetLastError
0x1403c8053  nop     dword ptr [rax+rax+00h]
0x1403c8058  mov     edi, eax
0x1403c805a  test    eax, eax
0x1403c805c  jle     short loc_1403C8067
0x1403c805e  movzx   edi, ax
0x1403c8061  or      edi, 80070000h
0x1403c8067  mov     rcx, rbp; Block
0x1403c806a  call    cs:__imp_free
0x1403c8071  nop     dword ptr [rax+rax+00h]
0x1403c8076  mov     rcx, rbx; hObject
0x1403c8079  call    cs:__imp_CloseHandle
0x1403c8080  nop     dword ptr [rax+rax+00h]
0x1403c8085  test    edi, edi
0x1403c8087  jns     loc_1403C810F
0x1403c808d  cmp     edi, 80070050h
0x1403c8093  jz      short loc_1403C80B0
0x1403c8095  cmp     qword ptr [rsi+18h], 7
0x1403c809a  jbe     short loc_1403C80A1
0x1403c809c  mov     rcx, [rsi]
0x1403c809f  jmp     short loc_1403C80A4
0x1403c80a1  mov     rcx, rsi; lpFileName
0x1403c80a4  call    cs:__imp_DeleteFileW
0x1403c80ab  nop     dword ptr [rax+rax+00h]
0x1403c80b0  mov     ebx, edi
0x1403c80b2  lea     r8, aU_1; "%%%%%u"
0x1403c80b9  btr     ebx, 1Ch
0x1403c80bd  lea     rcx, [rsp+0C8h+var_60]
0x1403c80c2  mov     ebp, 10h
0x1403c80c7  mov     r9d, ebx
0x1403c80ca  mov     edx, ebp
0x1403c80cc  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1403c80d1  mov     r9d, ebx
0x1403c80d4  lea     r8, a0x08x; "0x%08X"
0x1403c80db  mov     edx, ebp
0x1403c80dd  lea     rcx, [rsp+0C8h+var_80]
0x1403c80e2  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1403c80e7  lea     rax, [rsp+0C8h+var_80]
0x1403c80ec  mov     [rsp+0C8h+hTemplateFile], rsi; __int64
0x1403c80f1  mov     qword ptr [rsp+0C8h+dwFlagsAndAttributes], rax; __int64
0x1403c80f6  lea     edx, [rbp-0Bh]; unsigned int
0x1403c80f9  lea     rax, [rsp+0C8h+var_60]
0x1403c80fe  lea     rcx, MSVHDSVC_VFD_CREATION_FAILED; struct _EVENT_DESCRIPTOR *
0x1403c8105  mov     qword ptr [rsp+0C8h+dwCreationDisposition], rax; __int64
0x1403c810a  call    ??$VmEventWriteAndReport@AEAY0BA@GAEAY0BA@GAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBGAEAY0BA@G3AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; VmEventWriteAndReport<ushort (&)[16],ushort (&)[16],std::wstring &>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort (&)[16],ushort (&)[16],std::wstring &)
0x1403c810f  mov     eax, edi
0x1403c8111  mov     rcx, [rsp+0C8h+var_40]
0x1403c8119  xor     rcx, rsp; StackCookie
0x1403c811c  call    __security_check_cookie
0x1403c8121  add     rsp, 98h
0x1403c8128  pop     r14
0x1403c812a  pop     r12
0x1403c812c  pop     rdi
0x1403c812d  pop     rsi
0x1403c812e  pop     rbp
0x1403c812f  pop     rbx
0x1403c8130  retn
```
