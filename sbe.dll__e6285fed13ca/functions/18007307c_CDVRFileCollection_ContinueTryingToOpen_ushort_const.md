# CDVRFileCollection::ContinueTryingToOpen(ushort const *)

- ea: `0x18007307c`
- end: `0x1800731fc`
- name: `?ContinueTryingToOpen@CDVRFileCollection@@SAJPEBG@Z`
- size: `384`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180063528`

## callees

- `0x1800017e0`
- `0x1800017ec`
- `0x180001c00`
- `0x18007307c`
- `0x1800b33ed`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800731d7`
- `KERNEL32!CloseHandle` at `0x1800731d7`
- `KERNEL32!GetLastError` at `0x1800730d6`
- `KERNEL32!GetLastError` at `0x180073137`
- `KERNEL32!GetLastError` at `0x1800730d6`
- `KERNEL32!GetLastError` at `0x180073137`
- `KERNEL32!ReadFile` at `0x18007312d`
- `KERNEL32!ReadFile` at `0x18007312d`
- `KERNEL32!CreateFileW` at `0x1800730c7`
- `KERNEL32!CreateFileW` at `0x1800730c7`

## pseudocode

```c
__int64 __fastcall CDVRFileCollection::ContinueTryingToOpen(const unsigned __int16 *a1)
{
  HANDLE FileW; // rsi
  signed int LastError; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  unsigned __int64 v6; // rdx
  signed int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-18h] BYREF

  NumberOfBytesRead = 0;
  FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v3;
  }
  v4 = operator new[](0x778u);
  v5 = v4;
  if ( !v4 )
  {
    v3 = -2147024882;
    goto LABEL_21;
  }
  NumberOfBytesRead = 1912;
  if ( !ReadFile(FileW, v4, 0x778u, &NumberOfBytesRead, 0) )
  {
    v7 = GetLastError();
    v3 = v7;
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_20;
  }
  if ( NumberOfBytesRead >= 0x10 )
  {
    v8 = *v5 - 0x11CF668E75B22630LL;
    if ( *v5 == 0x11CF668E75B22630LL )
      v8 = v5[1] - 0x6CCE6200AA00D9A6LL;
    if ( !v8 )
      goto LABEL_13;
  }
  if ( NumberOfBytesRead != 1912 )
  {
    v3 = -2147024883;
    goto LABEL_20;
  }
  v9 = *v5 - *(_QWORD *)&CDVRFileCollection::m_guidV11.Data1;
  if ( *v5 == *(_QWORD *)&CDVRFileCollection::m_guidV11.Data1 )
    v9 = v5[1] - *(_QWORD *)CDVRFileCollection::m_guidV11.Data4;
  if ( v9 )
    v3 = memcmp_0(v5, &CDVRFileCollection::m_guidV1, 0x10u) != 0 ? -2147024883 : -2147220924;
  else
LABEL_13:
    v3 = 0;
LABEL_20:
  operator delete(v5, v6);
LABEL_21:
  if ( FileW )
    CloseHandle(FileW);
  return v3;
}

```

## disassembly

```asm
0x18007307c  mov     [rsp+arg_8], rbx
0x180073081  mov     [rsp+arg_10], rsi
0x180073086  push    rdi
0x180073087  sub     rsp, 50h
0x18007308b  mov     rax, cs:__security_cookie
0x180073092  xor     rax, rsp
0x180073095  mov     [rsp+58h+var_10], rax
0x18007309a  xor     r9d, r9d; lpSecurityAttributes
0x18007309d  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x1800730a6  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800730ae  mov     edx, 80000000h; dwDesiredAccess
0x1800730b3  mov     [rsp+58h+NumberOfBytesRead], 0
0x1800730bb  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1800730c3  lea     r8d, [r9+7]; dwShareMode
0x1800730c7  call    cs:__imp_CreateFileW
0x1800730cd  mov     rsi, rax
0x1800730d0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800730d4  jnz     short loc_1800730F4
0x1800730d6  call    cs:__imp_GetLastError
0x1800730dc  mov     ebx, eax
0x1800730de  test    eax, eax
0x1800730e0  jle     loc_1800731DD
0x1800730e6  movzx   ebx, ax
0x1800730e9  or      ebx, 80070000h
0x1800730ef  jmp     loc_1800731DD
0x1800730f4  mov     ebx, 778h
0x1800730f9  mov     ecx, ebx; unsigned __int64
0x1800730fb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180073100  mov     rdi, rax
0x180073103  test    rax, rax
0x180073106  jnz     short loc_180073112
0x180073108  mov     ebx, 8007000Eh
0x18007310d  jmp     loc_1800731CF
0x180073112  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180073117  mov     [rsp+58h+NumberOfBytesRead], ebx
0x18007311b  mov     r8d, ebx; nNumberOfBytesToRead
0x18007311e  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOverlapped
0x180073127  mov     rdx, rdi; lpBuffer
0x18007312a  mov     rcx, rsi; hFile
0x18007312d  call    cs:__imp_ReadFile
0x180073133  test    eax, eax
0x180073135  jnz     short loc_180073152
0x180073137  call    cs:__imp_GetLastError
0x18007313d  mov     ebx, eax
0x18007313f  test    eax, eax
0x180073141  jle     loc_1800731C7
0x180073147  movzx   ebx, ax
0x18007314a  or      ebx, 80070000h
0x180073150  jmp     short loc_1800731C7
0x180073152  mov     r8d, 10h; Size
0x180073158  cmp     [rsp+58h+NumberOfBytesRead], r8d
0x18007315d  jb      short loc_18007317F
0x18007315f  mov     rax, [rdi]
0x180073162  sub     rax, cs:qword_1800CAAC8
0x180073169  jnz     short loc_180073176
0x18007316b  mov     rax, [rdi+8]
0x18007316f  sub     rax, cs:qword_1800CAAD0
0x180073176  test    rax, rax
0x180073179  jnz     short loc_18007317F
0x18007317b  xor     ebx, ebx
0x18007317d  jmp     short loc_1800731C7
0x18007317f  cmp     [rsp+58h+NumberOfBytesRead], ebx
0x180073183  jnz     short loc_1800731C2
0x180073185  mov     rax, [rdi]
0x180073188  sub     rax, qword ptr cs:?m_guidV11@CDVRFileCollection@@2U_GUID@@B.Data1; _GUID const CDVRFileCollection::m_guidV11 ...
0x18007318f  jnz     short loc_18007319C
0x180073191  mov     rax, [rdi+8]
0x180073195  sub     rax, qword ptr cs:?m_guidV11@CDVRFileCollection@@2U_GUID@@B.Data4; _GUID const CDVRFileCollection::m_guidV11 ...
0x18007319c  test    rax, rax
0x18007319f  jz      short loc_18007317B
0x1800731a1  lea     rdx, ?m_guidV1@CDVRFileCollection@@2U_GUID@@B; Buf2
0x1800731a8  mov     rcx, rdi; Buf1
0x1800731ab  call    memcmp_0
0x1800731b0  neg     eax
0x1800731b2  sbb     ebx, ebx
0x1800731b4  and     ebx, 2FDC9h
0x1800731ba  add     ebx, 80040244h
0x1800731c0  jmp     short loc_1800731C7
0x1800731c2  mov     ebx, 8007000Dh
0x1800731c7  mov     rcx, rdi; void *
0x1800731ca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800731cf  test    rsi, rsi
0x1800731d2  jz      short loc_1800731DD
0x1800731d4  mov     rcx, rsi; hObject
0x1800731d7  call    cs:__imp_CloseHandle
0x1800731dd  mov     eax, ebx
0x1800731df  mov     rcx, [rsp+58h+var_10]
0x1800731e4  xor     rcx, rsp; StackCookie
0x1800731e7  call    __security_check_cookie
0x1800731ec  mov     rbx, [rsp+58h+arg_8]
0x1800731f1  mov     rsi, [rsp+58h+arg_10]
0x1800731f6  add     rsp, 50h
0x1800731fa  pop     rdi
0x1800731fb  retn
```
