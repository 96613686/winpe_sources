# pRemoveReparsePointData(ushort const *)

- ea: `0x180031e40`
- end: `0x180031fa7`
- name: `?pRemoveReparsePointData@@YAHPEBG@Z`
- size: `359`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x180029b30`
- `0x18002a870`

## callees

- `0x1800015ac`
- `0x180031e40`
- `0x180069020`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180031f88`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180031f88`
- `KERNEL32!CloseHandle` at `0x180031eea`
- `KERNEL32!CloseHandle` at `0x180031f7f`
- `KERNEL32!CloseHandle` at `0x180031eea`
- `KERNEL32!CloseHandle` at `0x180031f7f`
- `KERNEL32!DeviceIoControl` at `0x180031f1b`
- `KERNEL32!DeviceIoControl` at `0x180031f70`
- `KERNEL32!DeviceIoControl` at `0x180031f1b`
- `KERNEL32!DeviceIoControl` at `0x180031f70`
- `KERNEL32!CreateFileW` at `0x180031e85`
- `KERNEL32!CreateFileW` at `0x180031eb7`
- `KERNEL32!CreateFileW` at `0x180031e85`
- `KERNEL32!CreateFileW` at `0x180031eb7`

## pseudocode

```c
__int64 __fastcall pRemoveReparsePointData(LPCWSTR lpFileName)
{
  HANDLE FileW; // rbx
  char *v4; // rdi
  unsigned int v5; // esi
  int v6; // eax
  __int128 v7; // xmm0
  DWORD BytesReturned; // [rsp+40h] [rbp-58h] BYREF
  DWORD v9; // [rsp+44h] [rbp-54h] BYREF
  int InBuffer; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v11[20]; // [rsp+4Ch] [rbp-4Ch]
  int v12; // [rsp+60h] [rbp-38h]

  FileW = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 3u, 0x200000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    FileW = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 3u, 0x2200000u, 0);
    if ( FileW == (HANDLE)-1LL )
      return 0;
  }
  BytesReturned = 0;
  v4 = (char *)operator new[](0x4000u);
  if ( !v4 )
  {
    CloseHandle(FileW);
    return 0;
  }
  v5 = 0;
  if ( DeviceIoControl(FileW, 0x900A8u, 0, 0, v4, 0x4000u, &BytesReturned, 0) )
  {
    v6 = *(_DWORD *)v4;
    *(_OWORD *)v11 = 0;
    InBuffer = v6;
    v7 = *(_OWORD *)(v4 + 8);
    v12 = 0;
    *(_OWORD *)&v11[4] = v7;
    v9 = 0;
    v5 = DeviceIoControl(FileW, 0x900ACu, &InBuffer, 0x18u, 0, 0, &v9, 0);
  }
  CloseHandle(FileW);
  operator delete[](v4);
  return v5;
}

```

## disassembly

```asm
0x180031e40  push    rbx
0x180031e42  push    rsi
0x180031e43  push    rdi
0x180031e44  push    r15
0x180031e46  sub     rsp, 78h
0x180031e4a  mov     rax, cs:__security_cookie
0x180031e51  xor     rax, rsp
0x180031e54  mov     [rsp+98h+var_30], rax
0x180031e59  mov     esi, 3
0x180031e5e  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x180031e67  mov     [rsp+98h+dwFlagsAndAttributes], 200000h; dwFlagsAndAttributes
0x180031e6f  xor     r9d, r9d; lpSecurityAttributes
0x180031e72  mov     edx, 40000000h; dwDesiredAccess
0x180031e77  mov     [rsp+98h+dwCreationDisposition], esi; dwCreationDisposition
0x180031e7b  mov     rdi, rcx
0x180031e7e  lea     r15d, [rsi-2]
0x180031e82  mov     r8d, r15d; dwShareMode
0x180031e85  call    cs:__imp_CreateFileW
0x180031e8b  mov     rbx, rax
0x180031e8e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031e92  jnz     short loc_180031ECD
0x180031e94  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x180031e9d  xor     r9d, r9d; lpSecurityAttributes
0x180031ea0  mov     [rsp+98h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180031ea8  mov     r8d, r15d; dwShareMode
0x180031eab  mov     edx, 40000000h; dwDesiredAccess
0x180031eb0  mov     [rsp+98h+dwCreationDisposition], esi; dwCreationDisposition
0x180031eb4  mov     rcx, rdi; lpFileName
0x180031eb7  call    cs:__imp_CreateFileW
0x180031ebd  mov     rbx, rax
0x180031ec0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031ec4  jnz     short loc_180031ECD
0x180031ec6  xor     eax, eax
0x180031ec8  jmp     loc_180031F90
0x180031ecd  mov     ecx, 4000h; unsigned __int64
0x180031ed2  mov     [rsp+98h+BytesReturned], 0
0x180031eda  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180031edf  mov     rdi, rax
0x180031ee2  mov     rcx, rbx; hDevice
0x180031ee5  test    rax, rax
0x180031ee8  jnz     short loc_180031EF2
0x180031eea  call    cs:__imp_CloseHandle
0x180031ef0  jmp     short loc_180031EC6
0x180031ef2  lea     rax, [rsp+98h+BytesReturned]
0x180031ef7  xor     esi, esi
0x180031ef9  mov     [rsp+98h+lpOverlapped], rsi; lpOverlapped
0x180031efe  xor     r9d, r9d; nInBufferSize
0x180031f01  mov     [rsp+98h+hTemplateFile], rax; lpBytesReturned
0x180031f06  xor     r8d, r8d; lpInBuffer
0x180031f09  mov     [rsp+98h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x180031f11  mov     edx, 900A8h; dwIoControlCode
0x180031f16  mov     qword ptr [rsp+98h+dwCreationDisposition], rdi; lpOutBuffer
0x180031f1b  call    cs:__imp_DeviceIoControl
0x180031f21  test    eax, eax
0x180031f23  jz      short loc_180031F7C
0x180031f25  mov     eax, [rdi]
0x180031f27  lea     r9d, [rsi+18h]; nInBufferSize
0x180031f2b  xorps   xmm0, xmm0
0x180031f2e  mov     [rsp+98h+lpOverlapped], rsi; lpOverlapped
0x180031f33  movdqu  [rsp+98h+var_4C], xmm0
0x180031f39  mov     [rsp+98h+InBuffer], eax
0x180031f3d  lea     rax, [rsp+98h+var_54]
0x180031f42  movups  xmm0, xmmword ptr [rdi+8]
0x180031f46  mov     [rsp+98h+hTemplateFile], rax; lpBytesReturned
0x180031f4b  lea     r8, [rsp+98h+InBuffer]; lpInBuffer
0x180031f50  mov     qword ptr [rsp+98h+var_3C], rsi
0x180031f55  mov     edx, 900ACh; dwIoControlCode
0x180031f5a  mov     [rsp+98h+dwFlagsAndAttributes], esi; nOutBufferSize
0x180031f5e  mov     rcx, rbx; hDevice
0x180031f61  movdqu  [rsp+98h+var_4C+4], xmm0
0x180031f67  mov     [rsp+98h+var_54], esi
0x180031f6b  mov     qword ptr [rsp+98h+dwCreationDisposition], rsi; lpOutBuffer
0x180031f70  call    cs:__imp_DeviceIoControl
0x180031f76  test    eax, eax
0x180031f78  cmovnz  esi, r15d
0x180031f7c  mov     rcx, rbx; hObject
0x180031f7f  call    cs:__imp_CloseHandle
0x180031f85  mov     rcx, rdi
0x180031f88  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180031f8e  mov     eax, esi
0x180031f90  mov     rcx, [rsp+98h+var_30]
0x180031f95  xor     rcx, rsp; StackCookie
0x180031f98  call    __security_check_cookie
0x180031f9d  add     rsp, 78h
0x180031fa1  pop     r15
0x180031fa3  pop     rdi
0x180031fa4  pop     rsi
0x180031fa5  pop     rbx
0x180031fa6  retn
```
