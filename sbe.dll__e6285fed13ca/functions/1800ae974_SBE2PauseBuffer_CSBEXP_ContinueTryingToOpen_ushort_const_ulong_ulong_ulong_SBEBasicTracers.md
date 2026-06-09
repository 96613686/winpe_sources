# SBE2PauseBuffer::CSBEXP::ContinueTryingToOpen(ushort const *,ulong,ulong,ulong,SBEBasicTracers &)

- ea: `0x1800ae974`
- end: `0x1800aeb22`
- name: `?ContinueTryingToOpen@CSBEXP@SBE2PauseBuffer@@SAJPEBGKKKAEAVSBEBasicTracers@@@Z`
- size: `430`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, struct SBEBasicTracers *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800af928`

## callees

- `0x180001c00`
- `0x18000256c`
- `0x1800627f0`
- `0x1800ae974`
- `0x1800b33ed`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800aeafe`
- `KERNEL32!CloseHandle` at `0x1800aeafe`
- `KERNEL32!GetLastError` at `0x1800aea14`
- `KERNEL32!GetLastError` at `0x1800aea74`
- `KERNEL32!GetLastError` at `0x1800aea14`
- `KERNEL32!GetLastError` at `0x1800aea74`
- `KERNEL32!ReadFile` at `0x1800aea6a`
- `KERNEL32!ReadFile` at `0x1800aea6a`
- `KERNEL32!CreateFileW` at `0x1800aea05`
- `KERNEL32!CreateFileW` at `0x1800aea05`

## pseudocode

```c
__int64 __fastcall SBE2PauseBuffer::CSBEXP::ContinueTryingToOpen(
        LPCWSTR lpFileName,
        int a2,
        int a3,
        __int64 a4,
        struct SBEBasicTracers *a5)
{
  int v8; // ebp
  int v9; // ebx
  HANDLE FileW; // rax
  void *v11; // rdi
  signed int LastError; // eax
  signed int v13; // eax
  unsigned int v14; // r9d
  unsigned int v15; // r8d
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-88h] BYREF
  _BYTE Buffer[64]; // [rsp+50h] [rbp-78h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  NumberOfBytesRead = 64;
  v8 = a2 & 0x40000000;
  if ( v8 )
  {
    if ( a3 == 1 )
      return 0;
  }
  else if ( a3 != 3 )
  {
    return (unsigned int)-2147024809;
  }
  FileW = CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v11 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
      SBEBasicTracers::EtwTraceError(
        (struct SBEBasicTracers *)((char *)a5 + 88),
        "multimedia\\dshow\\filters\\sbe\\pausebuffer\\sbexp.cpp",
        0x4B4u,
        v9);
    return (unsigned int)v9;
  }
  if ( !ReadFile(FileW, Buffer, NumberOfBytesRead, &NumberOfBytesRead, 0) )
  {
    v13 = GetLastError();
    v9 = v13;
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
    if ( v9 >= 0 )
      goto LABEL_26;
    v14 = v9;
    v15 = 1216;
    goto LABEL_25;
  }
  if ( NumberOfBytesRead >= 0x40 )
  {
    if ( !memcmp_0(Buffer, &xmmword_1800CBE40, 0x10u) )
    {
LABEL_20:
      v9 = 0;
      goto LABEL_26;
    }
    v15 = 1249;
  }
  else
  {
    if ( !NumberOfBytesRead && v8 && a3 == 4 )
      goto LABEL_20;
    v15 = 1239;
  }
  v14 = -2147024883;
  v9 = -2147024883;
LABEL_25:
  SBEBasicTracers::EtwTraceError(
    (struct SBEBasicTracers *)((char *)a5 + 88),
    "multimedia\\dshow\\filters\\sbe\\pausebuffer\\sbexp.cpp",
    v15,
    v14);
LABEL_26:
  if ( v11 )
    CloseHandle(v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800ae974  push    rbx
0x1800ae976  push    rbp
0x1800ae977  push    rsi
0x1800ae978  push    rdi
0x1800ae979  sub     rsp, 0A8h
0x1800ae980  mov     rax, cs:__security_cookie
0x1800ae987  xor     rax, rsp
0x1800ae98a  mov     [rsp+0C8h+var_38], rax
0x1800ae992  mov     rsi, [rsp+0C8h+arg_20]
0x1800ae99a  mov     ebp, edx
0x1800ae99c  xor     edx, edx; Val
0x1800ae99e  mov     ebx, r8d
0x1800ae9a1  mov     rdi, rcx
0x1800ae9a4  lea     rcx, [rsp+0C8h+Buffer]; void *
0x1800ae9a9  lea     r8d, [rdx+40h]; Size
0x1800ae9ad  call    memset_0
0x1800ae9b2  mov     [rsp+0C8h+NumberOfBytesRead], 40h ; '@'
0x1800ae9ba  and     ebp, 40000000h
0x1800ae9c0  jz      short loc_1800AE9CE
0x1800ae9c2  cmp     ebx, 1
0x1800ae9c5  jnz     short loc_1800AE9DD
0x1800ae9c7  xor     ebx, ebx
0x1800ae9c9  jmp     loc_1800AEB04
0x1800ae9ce  cmp     ebx, 3
0x1800ae9d1  jz      short loc_1800AE9DD
0x1800ae9d3  mov     ebx, 80070057h
0x1800ae9d8  jmp     loc_1800AEB04
0x1800ae9dd  xor     r9d, r9d; lpSecurityAttributes
0x1800ae9e0  mov     [rsp+0C8h+hTemplateFile], 0; hTemplateFile
0x1800ae9e9  mov     [rsp+0C8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800ae9f1  mov     edx, 80000000h; dwDesiredAccess
0x1800ae9f6  mov     rcx, rdi; lpFileName
0x1800ae9f9  mov     [rsp+0C8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800aea01  lea     r8d, [r9+7]; dwShareMode
0x1800aea05  call    cs:__imp_CreateFileW
0x1800aea0b  mov     rdi, rax
0x1800aea0e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800aea12  jnz     short loc_1800AEA4F
0x1800aea14  call    cs:__imp_GetLastError
0x1800aea1a  mov     ebx, eax
0x1800aea1c  test    eax, eax
0x1800aea1e  jle     short loc_1800AEA29
0x1800aea20  movzx   ebx, ax
0x1800aea23  or      ebx, 80070000h
0x1800aea29  test    ebx, ebx
0x1800aea2b  jns     loc_1800AEB04
0x1800aea31  lea     rcx, [rsi+58h]; struct CEhEventTracer *
0x1800aea35  mov     r9d, ebx; unsigned int
0x1800aea38  mov     r8d, 4B4h; unsigned int
0x1800aea3e  lea     rdx, aMultimediaDsho_17; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800aea45  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x1800aea4a  jmp     loc_1800AEB04
0x1800aea4f  mov     r8d, [rsp+0C8h+NumberOfBytesRead]; nNumberOfBytesToRead
0x1800aea54  lea     r9, [rsp+0C8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800aea59  lea     rdx, [rsp+0C8h+Buffer]; lpBuffer
0x1800aea5e  mov     qword ptr [rsp+0C8h+dwCreationDisposition], 0; lpOverlapped
0x1800aea67  mov     rcx, rdi; hFile
0x1800aea6a  call    cs:__imp_ReadFile
0x1800aea70  test    eax, eax
0x1800aea72  jnz     short loc_1800AEA98
0x1800aea74  call    cs:__imp_GetLastError
0x1800aea7a  mov     ebx, eax
0x1800aea7c  test    eax, eax
0x1800aea7e  jle     short loc_1800AEA89
0x1800aea80  movzx   ebx, ax
0x1800aea83  or      ebx, 80070000h
0x1800aea89  test    ebx, ebx
0x1800aea8b  jns     short loc_1800AEAF6
0x1800aea8d  mov     r9d, ebx
0x1800aea90  mov     r8d, 4C0h
0x1800aea96  jmp     short loc_1800AEAE6
0x1800aea98  mov     eax, [rsp+0C8h+NumberOfBytesRead]
0x1800aea9c  cmp     eax, 40h ; '@'
0x1800aea9f  jnb     short loc_1800AEABA
0x1800aeaa1  test    eax, eax
0x1800aeaa3  jnz     short loc_1800AEAB2
0x1800aeaa5  test    ebp, ebp
0x1800aeaa7  jz      short loc_1800AEAB2
0x1800aeaa9  cmp     ebx, 4
0x1800aeaac  jnz     short loc_1800AEAB2
0x1800aeaae  xor     ebx, ebx
0x1800aeab0  jmp     short loc_1800AEAF6
0x1800aeab2  mov     r8d, 4D7h
0x1800aeab8  jmp     short loc_1800AEADB
0x1800aeaba  mov     r8d, 10h; Size
0x1800aeac0  lea     rdx, xmmword_1800CBE40; Buf2
0x1800aeac7  lea     rcx, [rsp+0C8h+Buffer]; Buf1
0x1800aeacc  call    memcmp_0
0x1800aead1  test    eax, eax
0x1800aead3  jz      short loc_1800AEAAE
0x1800aead5  mov     r8d, 4E1h; unsigned int
0x1800aeadb  mov     r9d, 8007000Dh; unsigned int
0x1800aeae1  mov     ebx, 8007000Dh
0x1800aeae6  lea     rdx, aMultimediaDsho_17; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800aeaed  lea     rcx, [rsi+58h]; struct CEhEventTracer *
0x1800aeaf1  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x1800aeaf6  test    rdi, rdi
0x1800aeaf9  jz      short loc_1800AEB04
0x1800aeafb  mov     rcx, rdi; hObject
0x1800aeafe  call    cs:__imp_CloseHandle
0x1800aeb04  mov     eax, ebx
0x1800aeb06  mov     rcx, [rsp+0C8h+var_38]
0x1800aeb0e  xor     rcx, rsp; StackCookie
0x1800aeb11  call    __security_check_cookie
0x1800aeb16  add     rsp, 0A8h
0x1800aeb1d  pop     rdi
0x1800aeb1e  pop     rsi
0x1800aeb1f  pop     rbp
0x1800aeb20  pop     rbx
0x1800aeb21  retn
```
