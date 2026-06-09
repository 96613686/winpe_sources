# CVaultTransacted::FileOperationsCreateFile(ushort const *,ulong,eWriteMode,void * *)

- ea: `0x180040200`
- end: `0x1800402a0`
- name: `?FileOperationsCreateFile@CVaultTransacted@@UEAAKPEBGKW4eWriteMode@@PEAPEAX@Z`
- size: `160`
- prototype: `unsigned int __high(const unsigned __int16 *, unsigned int, enum eWriteMode, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180040200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004028b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004028b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileTransactedW` at `0x18004026d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileTransactedW` at `0x18004026d`

## pseudocode

```c
DWORD __fastcall CVaultTransacted::FileOperationsCreateFile(__int64 a1, const WCHAR *a2, DWORD a3, int a4, _QWORD *a5)
{
  DWORD dwCreationDisposition; // r10d
  HANDLE FileTransactedW; // rax

  dwCreationDisposition = 2;
  if ( a4 != 1 )
    dwCreationDisposition = 4;
  FileTransactedW = CreateFileTransactedW(
                      a2,
                      a3,
                      0,
                      0,
                      dwCreationDisposition,
                      ((unsigned __int8)(dword_18005F638 & 1) << 31) + 128,
                      0,
                      *(HANDLE *)(a1 + 8),
                      0,
                      0);
  *a5 = FileTransactedW;
  if ( FileTransactedW != (HANDLE)-1LL )
    return 0;
  *a5 = 0;
  return GetLastError();
}

```

## disassembly

```asm
0x180040200  mov     [rsp+arg_0], rbx
0x180040205  push    rdi
0x180040206  sub     rsp, 50h
0x18004020a  mov     r11d, cs:dword_18005F638
0x180040211  mov     eax, 4
0x180040216  mov     [rsp+58h+lpExtendedParameter], 0; lpExtendedParameter
0x18004021f  and     r11d, 1
0x180040223  mov     [rsp+58h+pusMiniVersion], 0; pusMiniVersion
0x18004022c  mov     ebx, r8d
0x18004022f  shl     r11d, 1Fh
0x180040233  mov     rdi, rdx
0x180040236  sub     r11d, 0FFFFFF80h
0x18004023a  lea     r10d, [rax-2]
0x18004023e  cmp     r9d, 1
0x180040242  mov     edx, ebx; dwDesiredAccess
0x180040244  cmovnz  r10d, eax
0x180040248  mov     rax, [rcx+8]
0x18004024c  mov     [rsp+58h+hTransaction], rax; hTransaction
0x180040251  xor     r9d, r9d; lpSecurityAttributes
0x180040254  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18004025d  xor     r8d, r8d; dwShareMode
0x180040260  mov     [rsp+58h+dwFlagsAndAttributes], r11d; dwFlagsAndAttributes
0x180040265  mov     rcx, rdi; lpFileName
0x180040268  mov     [rsp+58h+dwCreationDisposition], r10d; dwCreationDisposition
0x18004026d  call    cs:__imp_CreateFileTransactedW
0x180040273  mov     rcx, [rsp+58h+arg_20]
0x18004027b  mov     [rcx], rax
0x18004027e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180040282  jnz     short loc_180040293
0x180040284  mov     qword ptr [rcx], 0
0x18004028b  call    cs:__imp_GetLastError
0x180040291  jmp     short loc_180040295
0x180040293  xor     eax, eax
0x180040295  mov     rbx, [rsp+58h+arg_0]
0x18004029a  add     rsp, 50h
0x18004029e  pop     rdi
0x18004029f  retn
```
