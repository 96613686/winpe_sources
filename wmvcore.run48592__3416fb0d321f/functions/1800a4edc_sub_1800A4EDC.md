# sub_1800A4EDC

- ea: `0x1800a4edc`
- end: `0x1800a5040`
- name: `sub_1800A4EDC`
- size: `356`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, DWORD FileSizeHigh)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800a3d90`

## callees

- `0x180011590`
- `0x18003f3a8`
- `0x18003f3b4`
- `0x1800a4edc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800a4ffa`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800a4ffa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a4f90`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a4f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4fa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4fa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5012`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a4fca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a4fca`

## pseudocode

```c
signed int __fastcall sub_1800A4EDC(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        int a7,
        __int64 FileSizeHigh)
{
  signed int result; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rbp
  unsigned __int128 v15; // rax
  unsigned __int64 v16; // kr00_8
  __int64 v17; // rax
  HANDLE FileW; // rdi
  void *v19; // rcx
  bool v20; // zf
  __int64 v21; // rax

  if ( !a3 )
    return -2147024809;
  v12 = *(_QWORD *)(a4 + 560);
  if ( v12 )
  {
    j_j__o_free(a3, a5, a3, v12, a5, a6);
    *(_QWORD *)(a4 + 560) = 0;
  }
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(a3 + 2 * v13) );
  v14 = v13 + 1;
  v16 = v13 + 1;
  v15 = (unsigned __int64)(v13 + 1) * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v16, 2u) )
    LODWORD(v15) = -1;
  v17 = sub_18003F3A8(a3, (int)a5, SDWORD2(v15), v15, (int)a5, a6);
  *(_QWORD *)(a4 + 560) = v17;
  if ( !v17 )
    return -2147024882;
  sub_180011590(a3, a5, v14, v17, a3);
  FileW = CreateFileW(*(LPCWSTR *)(a4 + 560), 0x80000000, 3u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v19 = *(void **)(a4 + 568);
    if ( v19 != (void *)-1LL )
      CloseHandle(v19);
    *(_QWORD *)(a4 + 568) = FileW;
    *(_DWORD *)(a4 + 552) = 1;
    HIDWORD(FileSizeHigh) = 0;
    LODWORD(FileSizeHigh) = GetFileSize(FileW, (LPDWORD)&FileSizeHigh + 1);
    if ( (_DWORD)FileSizeHigh != -1 || (v20 = GetLastError() == 0, v21 = 0, v20) )
      v21 = FileSizeHigh;
    *a5 = v21;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800a4edc  push    rbx
0x1800a4ede  push    rbp
0x1800a4edf  push    rsi
0x1800a4ee0  push    rdi
0x1800a4ee1  push    r14
0x1800a4ee3  push    r15
0x1800a4ee5  sub     rsp, 48h
0x1800a4ee9  xor     r14d, r14d
0x1800a4eec  mov     rsi, r8
0x1800a4eef  mov     rdi, rdx
0x1800a4ef2  mov     rbx, rcx
0x1800a4ef5  test    rdx, rdx
0x1800a4ef8  jnz     short loc_1800A4F04
0x1800a4efa  mov     eax, 80070057h
0x1800a4eff  jmp     loc_1800A5032
0x1800a4f04  mov     rcx, [rcx+230h]
0x1800a4f0b  test    rcx, rcx
0x1800a4f0e  jz      short loc_1800A4F1C
0x1800a4f10  call    j_j__o_free
0x1800a4f15  mov     [rbx+230h], r14
0x1800a4f1c  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800a4f20  mov     rax, r15
0x1800a4f23  inc     rax
0x1800a4f26  cmp     [rdi+rax*2], r14w
0x1800a4f2b  jnz     short loc_1800A4F23
0x1800a4f2d  lea     rbp, [rax+1]
0x1800a4f31  mov     eax, 2
0x1800a4f36  mul     rbp
0x1800a4f39  cmovb   rax, r15
0x1800a4f3d  mov     rcx, rax
0x1800a4f40  call    sub_18003F3A8
0x1800a4f45  mov     [rbx+230h], rax
0x1800a4f4c  test    rax, rax
0x1800a4f4f  jnz     short loc_1800A4F5B
0x1800a4f51  mov     eax, 8007000Eh
0x1800a4f56  jmp     loc_1800A5032
0x1800a4f5b  mov     r8, rdi
0x1800a4f5e  mov     rdx, rbp
0x1800a4f61  mov     rcx, rax
0x1800a4f64  call    sub_180011590
0x1800a4f69  mov     rcx, [rbx+230h]; lpFileName
0x1800a4f70  mov     r8d, 3; dwShareMode
0x1800a4f76  mov     [rsp+78h+hTemplateFile], r14; hTemplateFile
0x1800a4f7b  xor     r9d, r9d; lpSecurityAttributes
0x1800a4f7e  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a4f86  mov     edx, 80000000h; dwDesiredAccess
0x1800a4f8b  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800a4f90  call    cs:CreateFileW
0x1800a4f97  nop     dword ptr [rax+rax+00h]
0x1800a4f9c  mov     rdi, rax
0x1800a4f9f  cmp     rax, r15
0x1800a4fa2  jnz     short loc_1800A4FBE
0x1800a4fa4  call    cs:GetLastError
0x1800a4fab  nop     dword ptr [rax+rax+00h]
0x1800a4fb0  test    eax, eax
0x1800a4fb2  jle     short loc_1800A5032
0x1800a4fb4  movzx   eax, ax
0x1800a4fb7  or      eax, 80070000h
0x1800a4fbc  jmp     short loc_1800A5032
0x1800a4fbe  mov     rcx, [rbx+238h]; hObject
0x1800a4fc5  cmp     rcx, r15
0x1800a4fc8  jz      short loc_1800A4FD6
0x1800a4fca  call    cs:CloseHandle
0x1800a4fd1  nop     dword ptr [rax+rax+00h]
0x1800a4fd6  lea     rdx, [rsp+78h+FileSizeHigh+4]; lpFileSizeHigh
0x1800a4fde  mov     [rbx+238h], rdi
0x1800a4fe5  mov     rcx, rdi; hFile
0x1800a4fe8  mov     dword ptr [rbx+228h], 1
0x1800a4ff2  mov     [rsp+88h], r14
0x1800a4ffa  call    cs:GetFileSize
0x1800a5001  nop     dword ptr [rax+rax+00h]
0x1800a5006  mov     dword ptr [rsp+78h+FileSizeHigh], eax
0x1800a500d  cmp     eax, 0FFFFFFFFh
0x1800a5010  jnz     short loc_1800A5025
0x1800a5012  call    cs:GetLastError
0x1800a5019  nop     dword ptr [rax+rax+00h]
0x1800a501e  test    eax, eax
0x1800a5020  mov     rax, r14
0x1800a5023  jnz     short loc_1800A502D
0x1800a5025  mov     rax, [rsp+78h+FileSizeHigh]
0x1800a502d  mov     [rsi], rax
0x1800a5030  xor     eax, eax
0x1800a5032  add     rsp, 48h
0x1800a5036  pop     r15
0x1800a5038  pop     r14
0x1800a503a  pop     rdi
0x1800a503b  pop     rsi
0x1800a503c  pop     rbp
0x1800a503d  pop     rbx
0x1800a503e  retn
```
