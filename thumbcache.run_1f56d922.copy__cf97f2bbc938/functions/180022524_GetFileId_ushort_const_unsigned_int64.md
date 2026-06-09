# GetFileId(ushort const *,unsigned __int64 *)

- ea: `0x180022524`
- end: `0x1800225e8`
- name: `?GetFileId@@YAJPEBGPEA_K@Z`
- size: `196`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180022040`

## callees

- `0x18000b3c0`
- `0x180022524`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800225b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800225b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022568`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022568`
- `ntdll!NtQueryInformationFile` at `0x18002259d`
- `ntdll!NtQueryInformationFile` at `0x18002259d`

## pseudocode

```c
__int64 __fastcall GetFileId(const unsigned __int16 *a1, unsigned __int64 *a2)
{
  HANDLE FileW; // rax
  void *v4; // rdi
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  unsigned __int64 FileInformation; // [rsp+40h] [rbp-28h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-20h] BYREF

  *a2 = 0;
  FileW = CreateFileW(a1, 0, 7u, 0, 3u, 0x2000000u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return (unsigned int)ResultFromKnownLastError();
  }
  else
  {
    FileInformation = 0;
    IoStatusBlock = 0;
    v5 = NtQueryInformationFile(FileW, &IoStatusBlock, &FileInformation, 8u, FileInternalInformation);
    v6 = v5 | 0x10000000;
    if ( v5 >= 0 )
      *a2 = FileInformation;
    CloseHandle(v4);
  }
  return v6;
}

```

## disassembly

```asm
0x180022524  mov     [rsp+arg_10], rbx
0x180022529  mov     [rsp+arg_18], rsi
0x18002252e  push    rdi
0x18002252f  sub     rsp, 60h
0x180022533  mov     rax, cs:__security_cookie
0x18002253a  xor     rax, rsp
0x18002253d  mov     [rsp+68h+var_10], rax
0x180022542  xor     ebx, ebx
0x180022544  mov     rsi, rdx
0x180022547  mov     [rdx], rbx
0x18002254a  xor     r9d, r9d; lpSecurityAttributes
0x18002254d  mov     [rsp+68h+hTemplateFile], rbx; hTemplateFile
0x180022552  xor     edx, edx; dwDesiredAccess
0x180022554  mov     [rsp+68h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002255c  lea     r8d, [rbx+7]; dwShareMode
0x180022560  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180022568  call    cs:__imp_CreateFileW
0x18002256e  mov     rdi, rax
0x180022571  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022575  jz      short loc_1800225DF
0x180022577  xorps   xmm0, xmm0
0x18002257a  mov     [rsp+68h+FileInformation], rbx
0x18002257f  lea     r9d, [rbx+8]; Length
0x180022583  mov     [rsp+68h+dwCreationDisposition], 6; FileInformationClass
0x18002258b  lea     r8, [rsp+68h+FileInformation]; FileInformation
0x180022590  mov     rcx, rax; FileHandle
0x180022593  lea     rdx, [rsp+68h+IoStatusBlock]; IoStatusBlock
0x180022598  movups  xmmword ptr [rsp+68h+IoStatusBlock], xmm0
0x18002259d  call    cs:__imp_NtQueryInformationFile
0x1800225a3  mov     ebx, eax
0x1800225a5  or      ebx, 10000000h
0x1800225ab  jl      short loc_1800225B5
0x1800225ad  mov     rax, [rsp+68h+FileInformation]
0x1800225b2  mov     [rsi], rax
0x1800225b5  mov     rcx, rdi; hObject
0x1800225b8  call    cs:__imp_CloseHandle
0x1800225be  mov     eax, ebx
0x1800225c0  mov     rcx, [rsp+68h+var_10]
0x1800225c5  xor     rcx, rsp; StackCookie
0x1800225c8  call    __security_check_cookie
0x1800225cd  lea     r11, [rsp+68h+var_8]
0x1800225d2  mov     rbx, [r11+20h]
0x1800225d6  mov     rsi, [r11+28h]
0x1800225da  mov     rsp, r11
0x1800225dd  pop     rdi
0x1800225de  retn
0x1800225df  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800225e4  mov     ebx, eax
0x1800225e6  jmp     short loc_1800225BE
```
