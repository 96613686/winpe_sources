# CMemFileWriter::Seek(__int64,ulong)

- ea: `0x383a8a370`
- end: `0x383a8a526`
- name: `?Seek@CMemFileWriter@@UEAAJ_JK@Z`
- size: `438`
- prototype: `__int64 __fastcall(CMemFileWriter *__hidden this, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x383a896c0`
- `0x383a8a370`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383a8a477`
- `KERNEL32!GetLastError` at `0x383a8a477`
- `KERNEL32!CloseHandle` at `0x383a8a433`
- `KERNEL32!CloseHandle` at `0x383a8a433`
- `KERNEL32!MapViewOfFile` at `0x383a8a4c2`
- `KERNEL32!MapViewOfFile` at `0x383a8a4c2`
- `KERNEL32!UnmapViewOfFile` at `0x383a8a3f5`
- `KERNEL32!UnmapViewOfFile` at `0x383a8a3f5`
- `KERNEL32!CreateFileMappingW` at `0x383a8a45c`
- `KERNEL32!CreateFileMappingW` at `0x383a8a45c`

## pseudocode

```c
signed int __fastcall CMemFileWriter::Seek(CMemFileWriter *this, __int64 a2, DWORD a3)
{
  signed int result; // eax
  __int64 v5; // rcx
  signed __int64 v6; // rcx
  signed __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // eax
  void *v11; // rcx
  HANDLE FileMappingW; // rax
  LPVOID v13; // rax

  if ( !*((_DWORD *)this + 8) )
    return CFileWriter::Seek(this, a2, a3);
  if ( !a3 )
  {
    if ( a2 <= *((_QWORD *)this + 2) && a2 >= 0 )
    {
      *((_QWORD *)this + 7) = a2;
      goto LABEL_11;
    }
    return -2147221297;
  }
  if ( a3 != 1 )
    return -2147221297;
  v5 = a2 + *((_QWORD *)this + 7);
  if ( v5 > *((_QWORD *)this + 2) || v5 < 0 )
    return -2147221297;
  *((_QWORD *)this + 7) = v5;
LABEL_11:
  v6 = *((_QWORD *)this + 7);
  v7 = *((_QWORD *)this + 8);
  if ( v6 >= v7 && v6 < v7 + *((unsigned int *)this + 19) )
  {
LABEL_24:
    *((_DWORD *)this + 18) = *((_DWORD *)this + 14) - *((_DWORD *)this + 16);
    return 0;
  }
  if ( !UnmapViewOfFile(*((LPCVOID *)this + 6)) )
    goto LABEL_19;
  v8 = *((_QWORD *)this + 7) & 0xFFFFFFFFFFF00000uLL;
  v9 = *((_QWORD *)this + 2) - v8;
  *((_QWORD *)this + 8) = v8;
  if ( v9 <= 0x100000 )
    v10 = *((_DWORD *)this + 4) - v8;
  else
    v10 = 0x100000;
  *((_DWORD *)this + 19) = v10;
  if ( v10 >= 0x100000 )
  {
LABEL_22:
    v13 = MapViewOfFile(
            *((HANDLE *)this + 5),
            2u,
            *((_DWORD *)this + 17),
            *((_DWORD *)this + 16),
            *((unsigned int *)this + 19));
    *((_QWORD *)this + 6) = v13;
    if ( !v13 )
    {
      (*(void (__fastcall **)(CMemFileWriter *))(*(_QWORD *)this + 48LL))(this);
      *((_DWORD *)this + 6) = 0;
      return -2147221298;
    }
    goto LABEL_24;
  }
  CloseHandle(*((HANDLE *)this + 5));
  v11 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 2) += (unsigned int)(0x100000 - *((_DWORD *)this + 19));
  FileMappingW = CreateFileMappingW(v11, 0, 4u, *((_DWORD *)this + 5), *((_DWORD *)this + 4), 0);
  *((_QWORD *)this + 5) = FileMappingW;
  if ( FileMappingW )
  {
    *((_DWORD *)this + 19) = *((_DWORD *)this + 4) - *((_DWORD *)this + 16);
    goto LABEL_22;
  }
LABEL_19:
  (*(void (__fastcall **)(CMemFileWriter *))(*(_QWORD *)this + 48LL))(this);
  *((_DWORD *)this + 6) = 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x383a8a370  mov     [rsp+arg_0], rbx
0x383a8a375  mov     [rsp+arg_8], rsi
0x383a8a37a  push    rdi
0x383a8a37b  sub     rsp, 30h
0x383a8a37f  xor     edi, edi
0x383a8a381  mov     rbx, rcx
0x383a8a384  cmp     [rcx+20h], edi
0x383a8a387  jz      loc_383A8A50F
0x383a8a38d  test    r8d, r8d
0x383a8a390  jz      short loc_383A8A3C6
0x383a8a392  dec     r8d
0x383a8a395  jz      short loc_383A8A3AE
0x383a8a397  mov     edi, 800400CFh
0x383a8a39c  mov     eax, edi
0x383a8a39e  mov     rbx, [rsp+38h+arg_0]
0x383a8a3a3  mov     rsi, [rsp+38h+arg_8]
0x383a8a3a8  add     rsp, 30h
0x383a8a3ac  pop     rdi
0x383a8a3ad  retn
0x383a8a3ae  mov     rcx, [rcx+38h]
0x383a8a3b2  add     rcx, rdx
0x383a8a3b5  cmp     rcx, [rbx+10h]
0x383a8a3b9  jg      short loc_383A8A397
0x383a8a3bb  test    rcx, rcx
0x383a8a3be  js      short loc_383A8A397
0x383a8a3c0  mov     [rbx+38h], rcx
0x383a8a3c4  jmp     short loc_383A8A3D5
0x383a8a3c6  cmp     rdx, [rcx+10h]
0x383a8a3ca  jg      short loc_383A8A397
0x383a8a3cc  test    rdx, rdx
0x383a8a3cf  js      short loc_383A8A397
0x383a8a3d1  mov     [rcx+38h], rdx
0x383a8a3d5  mov     rcx, [rbx+38h]
0x383a8a3d9  mov     rdx, [rbx+40h]
0x383a8a3dd  cmp     rcx, rdx
0x383a8a3e0  jl      short loc_383A8A3F1
0x383a8a3e2  mov     eax, [rbx+4Ch]
0x383a8a3e5  add     rax, rdx
0x383a8a3e8  cmp     rcx, rax
0x383a8a3eb  jl      loc_383A8A4F4
0x383a8a3f1  mov     rcx, [rbx+30h]; lpBaseAddress
0x383a8a3f5  call    cs:__imp_UnmapViewOfFile
0x383a8a3fb  test    eax, eax
0x383a8a3fd  jz      short loc_383A8A46B
0x383a8a3ff  mov     rcx, [rbx+38h]
0x383a8a403  mov     rax, [rbx+10h]
0x383a8a407  mov     esi, 100000h
0x383a8a40c  and     rcx, 0FFFFFFFFFFF00000h
0x383a8a413  sub     rax, rcx
0x383a8a416  mov     [rbx+40h], rcx
0x383a8a41a  cmp     rax, rsi
0x383a8a41d  jle     short loc_383A8A423
0x383a8a41f  mov     eax, esi
0x383a8a421  jmp     short loc_383A8A428
0x383a8a423  mov     eax, [rbx+10h]
0x383a8a426  sub     eax, ecx
0x383a8a428  mov     [rbx+4Ch], eax
0x383a8a42b  cmp     eax, esi
0x383a8a42d  jnb     short loc_383A8A4A9
0x383a8a42f  mov     rcx, [rbx+28h]; hObject
0x383a8a433  call    cs:__imp_CloseHandle
0x383a8a439  sub     esi, [rbx+4Ch]
0x383a8a43c  mov     rcx, [rbx+8]; hFile
0x383a8a440  mov     eax, esi
0x383a8a442  xor     edx, edx; lpFileMappingAttributes
0x383a8a444  mov     [rsp+38h+lpName], rdi; lpName
0x383a8a449  add     [rbx+10h], rax
0x383a8a44d  mov     eax, [rbx+10h]
0x383a8a450  mov     r9d, [rbx+14h]; dwMaximumSizeHigh
0x383a8a454  lea     r8d, [rdx+4]; flProtect
0x383a8a458  mov     [rsp+38h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x383a8a45c  call    cs:__imp_CreateFileMappingW
0x383a8a462  mov     [rbx+28h], rax
0x383a8a466  test    rax, rax
0x383a8a469  jnz     short loc_383A8A4A0
0x383a8a46b  mov     rax, [rbx]
0x383a8a46e  mov     rcx, rbx
0x383a8a471  call    qword ptr [rax+30h]
0x383a8a474  mov     [rbx+18h], edi
0x383a8a477  call    cs:__imp_GetLastError
0x383a8a47d  test    eax, eax
0x383a8a47f  jle     loc_383A8A514
0x383a8a485  movzx   edi, ax
0x383a8a488  or      edi, 80070000h
0x383a8a48e  mov     eax, edi
0x383a8a490  mov     rbx, [rsp+38h+arg_0]
0x383a8a495  mov     rsi, [rsp+38h+arg_8]
0x383a8a49a  add     rsp, 30h
0x383a8a49e  pop     rdi
0x383a8a49f  retn
0x383a8a4a0  mov     eax, [rbx+10h]
0x383a8a4a3  sub     eax, [rbx+40h]
0x383a8a4a6  mov     [rbx+4Ch], eax
0x383a8a4a9  mov     eax, [rbx+4Ch]
0x383a8a4ac  mov     r9d, [rbx+40h]; dwFileOffsetLow
0x383a8a4b0  mov     r8d, [rbx+44h]; dwFileOffsetHigh
0x383a8a4b4  mov     rcx, [rbx+28h]; hFileMappingObject
0x383a8a4b8  mov     edx, 2; dwDesiredAccess
0x383a8a4bd  mov     qword ptr [rsp+38h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x383a8a4c2  call    cs:__imp_MapViewOfFile
0x383a8a4c8  mov     [rbx+30h], rax
0x383a8a4cc  test    rax, rax
0x383a8a4cf  jnz     short loc_383A8A4F4
0x383a8a4d1  mov     rax, [rbx]
0x383a8a4d4  mov     rcx, rbx
0x383a8a4d7  call    qword ptr [rax+30h]
0x383a8a4da  mov     [rbx+18h], edi
0x383a8a4dd  mov     edi, 800400CEh
0x383a8a4e2  mov     eax, edi
0x383a8a4e4  mov     rbx, [rsp+38h+arg_0]
0x383a8a4e9  mov     rsi, [rsp+38h+arg_8]
0x383a8a4ee  add     rsp, 30h
0x383a8a4f2  pop     rdi
0x383a8a4f3  retn
0x383a8a4f4  mov     eax, [rbx+38h]
0x383a8a4f7  sub     eax, [rbx+40h]
0x383a8a4fa  mov     [rbx+48h], eax
0x383a8a4fd  mov     eax, edi
0x383a8a4ff  mov     rbx, [rsp+38h+arg_0]
0x383a8a504  mov     rsi, [rsp+38h+arg_8]
0x383a8a509  add     rsp, 30h
0x383a8a50d  pop     rdi
0x383a8a50e  retn
0x383a8a50f  call    ?Seek@CFileWriter@@UEAAJ_JK@Z; CFileWriter::Seek(__int64,ulong)
0x383a8a514  mov     rbx, [rsp+38h+arg_0]
0x383a8a519  mov     rsi, [rsp+38h+arg_8]
0x383a8a51e  mov     edi, eax
0x383a8a520  add     rsp, 30h
0x383a8a524  pop     rdi
0x383a8a525  retn
```
