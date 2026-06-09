# SBE2PauseBuffer::CSBE2PauseBufferWriter::ConfigureTMPDirectory(void)

- ea: `0x1800a8ba4`
- end: `0x1800a8c6f`
- name: `?ConfigureTMPDirectory@CSBE2PauseBufferWriter@SBE2PauseBuffer@@AEAAJXZ`
- size: `203`
- prototype: `__int64 __fastcall(SBE2PauseBuffer::CSBE2PauseBufferWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1800a84a4`

## callees

- `0x1800567b0`
- `0x1800627f0`
- `0x1800a8ba4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800a8c18`
- `KERNEL32!GetLastError` at `0x1800a8c18`
- `KERNEL32!GetFileAttributesW` at `0x1800a8c0d`
- `KERNEL32!GetFileAttributesW` at `0x1800a8c0d`
- `KERNEL32!SetFileAttributesW` at `0x1800a8c57`
- `KERNEL32!SetFileAttributesW` at `0x1800a8c57`
- `KERNEL32!CreateDirectoryW` at `0x1800a8c00`
- `KERNEL32!CreateDirectoryW` at `0x1800a8c00`

## string_xrefs

- `0x1800a8bed`: `multimedia\dshow\filters\sbe\pausebuffer\pbwriter.cpp`

## pseudocode

```c
__int64 __fastcall SBE2PauseBuffer::CSBE2PauseBufferWriter::ConfigureTMPDirectory(
        SBE2PauseBuffer::CSBE2PauseBufferWriter *this,
        unsigned __int64 a2)
{
  const WCHAR *v3; // rax
  const WCHAR *v4; // rdi
  unsigned int v5; // ebx
  unsigned int v6; // r9d
  unsigned int v7; // r8d
  DWORD FileAttributesW; // eax
  signed int LastError; // eax

  v3 = CTSDVRSettings::SBE2TMPDirectory(
         (CTSDVRSettings *)(*((_QWORD *)this + 133) + 328LL),
         a2,
         (unsigned __int16 *)this + 164);
  v4 = v3;
  if ( v3 )
  {
    if ( CreateDirectoryW(v3, 0) )
      goto LABEL_11;
    FileAttributesW = GetFileAttributesW(v4);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v6 = v5;
      v7 = 508;
      goto LABEL_3;
    }
    if ( (FileAttributesW & 0x10) != 0 )
    {
LABEL_11:
      v5 = 0;
      SetFileAttributesW(v4, 6u);
      return v5;
    }
    v5 = -2147024629;
    v6 = -2147024629;
    v7 = 512;
  }
  else
  {
    v5 = -2147418113;
    v6 = -2147418113;
    v7 = 499;
  }
LABEL_3:
  SBEBasicTracers::EtwTraceError(
    (SBE2PauseBuffer::CSBE2PauseBufferWriter *)((char *)this + 88),
    "multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbwriter.cpp",
    v7,
    v6);
  return v5;
}

```

## disassembly

```asm
0x1800a8ba4  mov     [rsp+arg_0], rbx
0x1800a8ba9  mov     [rsp+arg_8], rsi
0x1800a8bae  push    rdi
0x1800a8baf  sub     rsp, 20h
0x1800a8bb3  mov     rsi, rcx
0x1800a8bb6  lea     r8, [rcx+148h]; unsigned __int16 *
0x1800a8bbd  mov     rcx, [rcx+428h]
0x1800a8bc4  add     rcx, 148h; this
0x1800a8bcb  call    ?SBE2TMPDirectory@CTSDVRSettings@@QEAAPEAG_KPEAG@Z; CTSDVRSettings::SBE2TMPDirectory(unsigned __int64,ushort *)
0x1800a8bd0  mov     rdi, rax
0x1800a8bd3  test    rax, rax
0x1800a8bd6  jnz     short loc_1800A8BFB
0x1800a8bd8  mov     ebx, 8000FFFFh
0x1800a8bdd  mov     r9d, 8000FFFFh; unsigned int
0x1800a8be3  mov     r8d, 1F3h; unsigned int
0x1800a8be9  lea     rcx, [rsi+58h]; struct CEhEventTracer *
0x1800a8bed  lea     rdx, aMultimediaDsho_27; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800a8bf4  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x1800a8bf9  jmp     short loc_1800A8C5D
0x1800a8bfb  xor     edx, edx; lpSecurityAttributes
0x1800a8bfd  mov     rcx, rdi; lpPathName
0x1800a8c00  call    cs:__imp_CreateDirectoryW
0x1800a8c06  test    eax, eax
0x1800a8c08  jnz     short loc_1800A8C4F
0x1800a8c0a  mov     rcx, rdi; lpFileName
0x1800a8c0d  call    cs:__imp_GetFileAttributesW
0x1800a8c13  cmp     eax, 0FFFFFFFFh
0x1800a8c16  jnz     short loc_1800A8C38
0x1800a8c18  call    cs:__imp_GetLastError
0x1800a8c1e  mov     ebx, eax
0x1800a8c20  test    eax, eax
0x1800a8c22  jle     short loc_1800A8C2D
0x1800a8c24  movzx   ebx, ax
0x1800a8c27  or      ebx, 80070000h
0x1800a8c2d  mov     r9d, ebx
0x1800a8c30  mov     r8d, 1FCh
0x1800a8c36  jmp     short loc_1800A8BE9
0x1800a8c38  test    al, 10h
0x1800a8c3a  jnz     short loc_1800A8C4F
0x1800a8c3c  mov     ebx, 8007010Bh
0x1800a8c41  mov     r9d, 8007010Bh
0x1800a8c47  mov     r8d, 200h
0x1800a8c4d  jmp     short loc_1800A8BE9
0x1800a8c4f  xor     ebx, ebx
0x1800a8c51  mov     rcx, rdi; lpFileName
0x1800a8c54  lea     edx, [rbx+6]; dwFileAttributes
0x1800a8c57  call    cs:__imp_SetFileAttributesW
0x1800a8c5d  mov     rsi, [rsp+28h+arg_8]
0x1800a8c62  mov     eax, ebx
0x1800a8c64  mov     rbx, [rsp+28h+arg_0]
0x1800a8c69  add     rsp, 20h
0x1800a8c6d  pop     rdi
0x1800a8c6e  retn
```
