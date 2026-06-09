# CMemFileWriter::Write(ulong,void *)

- ea: `0x383a8a140`
- end: `0x383a8a361`
- name: `?Write@CMemFileWriter@@UEAAJKPEAX@Z`
- size: `545`
- prototype: `int(CMemFileWriter *__hidden this, unsigned int, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x3838427d0`
- `0x383a89650`
- `0x383a8a100`
- `0x383a8a140`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383a8a1ea`
- `KERNEL32!GetLastError` at `0x383a8a21f`
- `KERNEL32!GetLastError` at `0x383a8a2b9`
- `KERNEL32!GetLastError` at `0x383a8a1ea`
- `KERNEL32!GetLastError` at `0x383a8a21f`
- `KERNEL32!GetLastError` at `0x383a8a2b9`
- `KERNEL32!CloseHandle` at `0x383a8a273`
- `KERNEL32!CloseHandle` at `0x383a8a273`
- `KERNEL32!MapViewOfFile` at `0x383a8a2f5`
- `KERNEL32!MapViewOfFile` at `0x383a8a2f5`
- `KERNEL32!UnmapViewOfFile` at `0x383a8a20b`
- `KERNEL32!UnmapViewOfFile` at `0x383a8a20b`
- `KERNEL32!CreateFileMappingW` at `0x383a8a29f`
- `KERNEL32!CreateFileMappingW` at `0x383a8a29f`
- `KERNEL32!FlushViewOfFile` at `0x383a8a1d5`
- `KERNEL32!FlushViewOfFile` at `0x383a8a1d5`

## pseudocode

```c
__int64 __fastcall CMemFileWriter::Write(CMemFileWriter *this, unsigned int a2, char *a3)
{
  char *v3; // r12
  unsigned int v4; // r15d
  unsigned int v6; // esi
  unsigned int i; // r14d
  void *v8; // rcx
  signed int LastError; // eax
  signed int v10; // eax
  __int64 v11; // rcx
  unsigned int v12; // eax
  HANDLE FileMappingW; // rax
  signed int v14; // eax
  LPVOID v15; // rax

  v3 = a3;
  v4 = a2;
  v6 = 0;
  if ( !*((_DWORD *)this + 8) )
    return (unsigned int)CFileWriter::Write(this, a2, a3);
  if ( !a3 )
    return (unsigned int)-2147024809;
  for ( i = *((_DWORD *)this + 19) - *((_DWORD *)this + 18); ; i = *((_DWORD *)this + 19) )
  {
    v8 = (void *)(*((_QWORD *)this + 6) + *((unsigned int *)this + 18));
    if ( i >= v4 )
    {
      memcpy(v8, v3, v4);
      *((_QWORD *)this + 7) += v4;
      *((_DWORD *)this + 18) += v4;
      return v6;
    }
    memcpy(v8, v3, i);
    v4 -= i;
    *((_QWORD *)this + 7) += i;
    *((_DWORD *)this + 18) += i;
    v3 += i;
    if ( !FlushViewOfFile(*((LPCVOID *)this + 6), *((unsigned int *)this + 19)) )
    {
      CMemFileWriter::HandleMappingFailure(this, 3);
      LastError = GetLastError();
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return (unsigned int)LastError;
    }
    if ( !UnmapViewOfFile(*((LPCVOID *)this + 6)) )
    {
      CMemFileWriter::HandleMappingFailure(this, 0);
      v10 = GetLastError();
      if ( v10 > 0 )
        return (unsigned __int16)v10 | 0x80070000;
      return (unsigned int)v10;
    }
    *((_QWORD *)this + 8) += *((unsigned int *)this + 19);
    v11 = *((_QWORD *)this + 8);
    v12 = *((_QWORD *)this + 2) - v11 < 0x100000 ? *((_DWORD *)this + 4) - v11 : 0x100000;
    *((_DWORD *)this + 19) = v12;
    *((_DWORD *)this + 18) = 0;
    if ( v12 < 0x100000 )
      break;
LABEL_24:
    v15 = MapViewOfFile(
            *((HANDLE *)this + 5),
            2u,
            *((_DWORD *)this + 17),
            *((_DWORD *)this + 16),
            *((unsigned int *)this + 19));
    *((_QWORD *)this + 6) = v15;
    if ( !v15 )
    {
      CMemFileWriter::HandleMappingFailure(this, 2);
      return (unsigned int)-2147221298;
    }
  }
  CloseHandle(*((HANDLE *)this + 5));
  *((_QWORD *)this + 2) += (unsigned int)(0x100000 - *((_DWORD *)this + 19));
  FileMappingW = CreateFileMappingW(*((HANDLE *)this + 1), 0, 4u, *((_DWORD *)this + 5), *((_DWORD *)this + 4), 0);
  *((_QWORD *)this + 5) = FileMappingW;
  if ( FileMappingW )
  {
    *((_DWORD *)this + 19) = *((_DWORD *)this + 4) - *((_DWORD *)this + 16);
    goto LABEL_24;
  }
  CMemFileWriter::HandleMappingFailure(this, 1);
  v14 = GetLastError();
  if ( v14 > 0 )
    return (unsigned __int16)v14 | 0x80070000;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x383a8a140  mov     [rsp+arg_18], rbx
0x383a8a145  mov     [rsp+arg_0], rcx
0x383a8a14a  push    rsi
0x383a8a14b  push    rdi
0x383a8a14c  push    r12
0x383a8a14e  push    r14
0x383a8a150  push    r15
0x383a8a152  sub     rsp, 40h
0x383a8a156  mov     r12, r8
0x383a8a159  mov     r15d, edx
0x383a8a15c  mov     rbx, rcx
0x383a8a15f  xor     esi, esi
0x383a8a161  cmp     [rcx+20h], esi
0x383a8a164  jz      loc_383A8A343
0x383a8a16a  test    r8, r8
0x383a8a16d  jnz     short loc_383A8A179
0x383a8a16f  mov     esi, 80070057h
0x383a8a174  jmp     loc_383A8A34A
0x383a8a179  mov     r14d, [rcx+4Ch]
0x383a8a17d  sub     r14d, [rcx+48h]
0x383a8a181  mov     ecx, [rbx+48h]
0x383a8a184  mov     rdx, r12; Src
0x383a8a187  add     rcx, [rbx+30h]; void *
0x383a8a18b  cmp     r14d, r15d
0x383a8a18e  jb      short loc_383A8A1A8
0x383a8a190  mov     edi, r15d
0x383a8a193  mov     r8d, r15d; Size
0x383a8a196  call    memcpy
0x383a8a19b  add     [rbx+38h], rdi
0x383a8a19f  add     [rbx+48h], r15d
0x383a8a1a3  jmp     loc_383A8A34A
0x383a8a1a8  mov     edi, r14d
0x383a8a1ab  mov     r8d, r14d; Size
0x383a8a1ae  call    memcpy
0x383a8a1b3  sub     r15d, r14d
0x383a8a1b6  mov     [rsp+68h+arg_8], r15d
0x383a8a1bb  add     [rbx+38h], rdi
0x383a8a1bf  add     [rbx+48h], r14d
0x383a8a1c3  add     r12, rdi
0x383a8a1c6  mov     [rsp+68h+arg_10], r12
0x383a8a1ce  mov     edx, [rbx+4Ch]; dwNumberOfBytesToFlush
0x383a8a1d1  mov     rcx, [rbx+30h]; lpBaseAddress
0x383a8a1d5  call    cs:__imp_FlushViewOfFile
0x383a8a1db  test    eax, eax
0x383a8a1dd  jnz     short loc_383A8A207
0x383a8a1df  lea     edx, [rax+3]
0x383a8a1e2  mov     rcx, rbx
0x383a8a1e5  call    ?HandleMappingFailure@CMemFileWriter@@AEAAXW4EMappingFailureWrite@@@Z; CMemFileWriter::HandleMappingFailure(EMappingFailureWrite)
0x383a8a1ea  call    cs:__imp_GetLastError
0x383a8a1f0  test    eax, eax
0x383a8a1f2  jle     short loc_383A8A1FC
0x383a8a1f4  movzx   eax, ax
0x383a8a1f7  or      eax, 80070000h
0x383a8a1fc  mov     esi, eax
0x383a8a1fe  mov     [rsp+68h+var_38], eax
0x383a8a202  jmp     loc_383A8A34A
0x383a8a207  mov     rcx, [rbx+30h]; lpBaseAddress
0x383a8a20b  call    cs:__imp_UnmapViewOfFile
0x383a8a211  test    eax, eax
0x383a8a213  jnz     short loc_383A8A23C
0x383a8a215  xor     edx, edx
0x383a8a217  mov     rcx, rbx
0x383a8a21a  call    ?HandleMappingFailure@CMemFileWriter@@AEAAXW4EMappingFailureWrite@@@Z; CMemFileWriter::HandleMappingFailure(EMappingFailureWrite)
0x383a8a21f  call    cs:__imp_GetLastError
0x383a8a225  test    eax, eax
0x383a8a227  jle     short loc_383A8A231
0x383a8a229  movzx   eax, ax
0x383a8a22c  or      eax, 80070000h
0x383a8a231  mov     esi, eax
0x383a8a233  mov     [rsp+68h+var_38], eax
0x383a8a237  jmp     loc_383A8A34A
0x383a8a23c  mov     eax, [rbx+4Ch]
0x383a8a23f  add     [rbx+40h], rax
0x383a8a243  mov     rcx, [rbx+40h]
0x383a8a247  mov     rax, [rbx+10h]
0x383a8a24b  sub     rax, rcx
0x383a8a24e  cmp     rax, 100000h
0x383a8a254  jl      short loc_383A8A25D
0x383a8a256  mov     eax, 100000h
0x383a8a25b  jmp     short loc_383A8A262
0x383a8a25d  mov     eax, [rbx+10h]
0x383a8a260  sub     eax, ecx
0x383a8a262  mov     [rbx+4Ch], eax
0x383a8a265  mov     [rbx+48h], esi
0x383a8a268  cmp     eax, 100000h
0x383a8a26d  jnb     short loc_383A8A2DC
0x383a8a26f  mov     rcx, [rbx+28h]; hObject
0x383a8a273  call    cs:__imp_CloseHandle
0x383a8a279  mov     eax, 100000h
0x383a8a27e  sub     eax, [rbx+4Ch]
0x383a8a281  add     [rbx+10h], rax
0x383a8a285  mov     [rsp+68h+lpName], rsi; lpName
0x383a8a28a  mov     eax, [rbx+10h]
0x383a8a28d  mov     [rsp+68h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x383a8a291  mov     r9d, [rbx+14h]; dwMaximumSizeHigh
0x383a8a295  xor     edx, edx; lpFileMappingAttributes
0x383a8a297  lea     r8d, [rdx+4]; flProtect
0x383a8a29b  mov     rcx, [rbx+8]; hFile
0x383a8a29f  call    cs:__imp_CreateFileMappingW
0x383a8a2a5  mov     [rbx+28h], rax
0x383a8a2a9  test    rax, rax
0x383a8a2ac  jnz     short loc_383A8A2D3
0x383a8a2ae  lea     edx, [rax+1]
0x383a8a2b1  mov     rcx, rbx
0x383a8a2b4  call    ?HandleMappingFailure@CMemFileWriter@@AEAAXW4EMappingFailureWrite@@@Z; CMemFileWriter::HandleMappingFailure(EMappingFailureWrite)
0x383a8a2b9  call    cs:__imp_GetLastError
0x383a8a2bf  test    eax, eax
0x383a8a2c1  jle     short loc_383A8A2CB
0x383a8a2c3  movzx   eax, ax
0x383a8a2c6  or      eax, 80070000h
0x383a8a2cb  mov     esi, eax
0x383a8a2cd  mov     [rsp+68h+var_38], eax
0x383a8a2d1  jmp     short loc_383A8A34A
0x383a8a2d3  mov     eax, [rbx+10h]
0x383a8a2d6  sub     eax, [rbx+40h]
0x383a8a2d9  mov     [rbx+4Ch], eax
0x383a8a2dc  mov     eax, [rbx+4Ch]
0x383a8a2df  mov     qword ptr [rsp+68h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x383a8a2e4  mov     r9d, [rbx+40h]; dwFileOffsetLow
0x383a8a2e8  mov     r8d, [rbx+44h]; dwFileOffsetHigh
0x383a8a2ec  mov     edx, 2; dwDesiredAccess
0x383a8a2f1  mov     rcx, [rbx+28h]; hFileMappingObject
0x383a8a2f5  call    cs:__imp_MapViewOfFile
0x383a8a2fb  mov     [rbx+30h], rax
0x383a8a2ff  test    rax, rax
0x383a8a302  jnz     short loc_383A8A31A
0x383a8a304  lea     edx, [rax+2]
0x383a8a307  mov     rcx, rbx
0x383a8a30a  call    ?HandleMappingFailure@CMemFileWriter@@AEAAXW4EMappingFailureWrite@@@Z; CMemFileWriter::HandleMappingFailure(EMappingFailureWrite)
0x383a8a30f  mov     esi, 800400CEh
0x383a8a314  mov     [rsp+68h+var_38], esi
0x383a8a318  jmp     short loc_383A8A34A
0x383a8a31a  mov     r14d, [rbx+4Ch]
0x383a8a31e  jmp     loc_383A8A181
0x383a8a323  mov     rbx, [rsp+68h+arg_0]
0x383a8a328  mov     rax, [rbx]
0x383a8a32b  mov     rcx, rbx
0x383a8a32e  call    qword ptr [rax+30h]
0x383a8a331  mov     dword ptr [rbx+18h], 0
0x383a8a338  mov     esi, 800400CEh
0x383a8a33d  mov     [rsp+68h+var_38], esi
0x383a8a341  jmp     short loc_383A8A34A
0x383a8a343  call    ?Write@CFileWriter@@UEAAJKPEAX@Z; CFileWriter::Write(ulong,void *)
0x383a8a348  mov     esi, eax
0x383a8a34a  mov     eax, esi
0x383a8a34c  mov     rbx, [rsp+68h+arg_18]
0x383a8a354  add     rsp, 40h
0x383a8a358  pop     r15
0x383a8a35a  pop     r14
0x383a8a35c  pop     r12
0x383a8a35e  pop     rdi
0x383a8a35f  pop     rsi
0x383a8a360  retn
```
