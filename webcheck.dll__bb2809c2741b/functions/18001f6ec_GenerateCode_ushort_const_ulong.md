# GenerateCode(ushort const *,ulong *)

- ea: `0x18001f6ec`
- end: `0x18001f7d8`
- name: `?GenerateCode@@YAJPEBGPEAK@Z`
- size: `236`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180021940`
- `0x180021a5c`

## callees

- `0x18001f6ec`
- `0x180029280`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18001f733`
- `KERNEL32!CreateFileW` at `0x18001f733`
- `KERNEL32!CloseHandle` at `0x18001f7a2`
- `KERNEL32!CloseHandle` at `0x18001f7a2`
- `KERNEL32!ReadFile` at `0x18001f75e`
- `KERNEL32!ReadFile` at `0x18001f75e`

## pseudocode

```c
__int64 __fastcall GenerateCode(const unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int v2; // ebx
  unsigned int v4; // edi
  HANDLE FileW; // rsi
  __int64 i; // r9
  unsigned int v7; // eax
  int v8; // ebx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-438h] BYREF
  _DWORD Buffer[256]; // [rsp+50h] [rbp-428h] BYREF

  v2 = 0;
  NumberOfBytesRead = 0;
  v4 = 0;
  FileW = CreateFileW(a1, 0x80000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v4 = -2147467259;
  }
  else
  {
    do
    {
      NumberOfBytesRead = 0;
      if ( ReadFile(FileW, Buffer, 0x400u, &NumberOfBytesRead, 0) )
      {
        for ( i = 0; (unsigned int)i < NumberOfBytesRead >> 2; v2 = v7 | v8 )
        {
          v7 = v2 << 31;
          v8 = (v2 >> 1) + Buffer[i];
          i = (unsigned int)(i + 1);
        }
      }
    }
    while ( NumberOfBytesRead == 1024 );
    CloseHandle(FileW);
  }
  *a2 = v2;
  return v4;
}

```

## disassembly

```asm
0x18001f6ec  mov     [rsp+arg_10], rbx
0x18001f6f1  push    rsi
0x18001f6f2  push    rdi
0x18001f6f3  push    r14
0x18001f6f5  sub     rsp, 460h
0x18001f6fc  mov     rax, cs:__security_cookie
0x18001f703  xor     rax, rsp
0x18001f706  mov     [rsp+478h+var_28], rax
0x18001f70e  xor     ebx, ebx
0x18001f710  mov     r14, rdx
0x18001f713  mov     [rsp+478h+hTemplateFile], rbx; hTemplateFile
0x18001f718  xor     r9d, r9d; lpSecurityAttributes
0x18001f71b  mov     [rsp+478h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18001f71f  mov     edx, 80000000h; dwDesiredAccess
0x18001f724  mov     [rsp+478h+NumberOfBytesRead], ebx
0x18001f728  xor     edi, edi
0x18001f72a  lea     r8d, [rbx+3]; dwShareMode
0x18001f72e  mov     [rsp+478h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001f733  call    cs:__imp_CreateFileW
0x18001f739  mov     rsi, rax
0x18001f73c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f740  jz      short loc_18001F7AA
0x18001f742  lea     r9, [rsp+478h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001f747  mov     [rsp+478h+NumberOfBytesRead], edi
0x18001f74b  mov     r8d, 400h; nNumberOfBytesToRead
0x18001f751  mov     qword ptr [rsp+478h+dwCreationDisposition], rdi; lpOverlapped
0x18001f756  lea     rdx, [rsp+478h+Buffer]; lpBuffer
0x18001f75b  mov     rcx, rsi; hFile
0x18001f75e  call    cs:__imp_ReadFile
0x18001f764  test    eax, eax
0x18001f766  jz      short loc_18001F795
0x18001f768  mov     r8d, [rsp+478h+NumberOfBytesRead]
0x18001f76d  xor     r9d, r9d
0x18001f770  shr     r8d, 2
0x18001f774  test    r8d, r8d
0x18001f777  jz      short loc_18001F795
0x18001f779  mov     edx, [rsp+r9*4+478h+Buffer]
0x18001f77e  mov     ecx, ebx
0x18001f780  mov     eax, ebx
0x18001f782  shr     ecx, 1
0x18001f784  add     edx, ecx
0x18001f786  shl     eax, 1Fh
0x18001f789  mov     ebx, edx
0x18001f78b  inc     r9d
0x18001f78e  or      ebx, eax
0x18001f790  cmp     r9d, r8d
0x18001f793  jb      short loc_18001F779
0x18001f795  cmp     [rsp+478h+NumberOfBytesRead], 400h
0x18001f79d  jz      short loc_18001F742
0x18001f79f  mov     rcx, rsi; hObject
0x18001f7a2  call    cs:__imp_CloseHandle
0x18001f7a8  jmp     short loc_18001F7AF
0x18001f7aa  mov     edi, 80004005h
0x18001f7af  mov     [r14], ebx
0x18001f7b2  mov     eax, edi
0x18001f7b4  mov     rcx, [rsp+478h+var_28]
0x18001f7bc  xor     rcx, rsp; StackCookie
0x18001f7bf  call    __security_check_cookie
0x18001f7c4  mov     rbx, [rsp+478h+arg_10]
0x18001f7cc  add     rsp, 460h
0x18001f7d3  pop     r14
0x18001f7d5  pop     rdi
0x18001f7d6  pop     rsi
0x18001f7d7  retn
```
