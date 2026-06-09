# mmioDOSIOProc(char *,uint,__int64,__int64)

- ea: `0x1801e09f0`
- end: `0x1801e0ce5`
- name: `?mmioDOSIOProc@@YA_JPEADI_J1@Z`
- size: `757`
- prototype: `__int64(char *, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x1800156f0`
- `0x18003945c`
- `0x180079e30`
- `0x1801e09f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801e0c5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801e0c5c`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1801e0c16`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1801e0c16`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801e0b0d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801e0b0d`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1801e0ae1`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1801e0ae1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801e0b26`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801e0b26`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801e0b56`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801e0b56`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801e0c43`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801e0c43`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1801e0a5b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1801e0a5b`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1801e0aad`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1801e0aad`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x1801e0c77`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x1801e0c8d`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x1801e0c77`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x1801e0c8d`
- `api-ms-win-core-kernel32-private-l1-1-0!_lclose` at `0x1801e0a75`
- `api-ms-win-core-kernel32-private-l1-1-0!_lclose` at `0x1801e0a75`
- `api-ms-win-core-kernel32-private-l1-1-0!_lread` at `0x1801e0cb7`
- `api-ms-win-core-kernel32-private-l1-1-0!_lread` at `0x1801e0cb7`
- `api-ms-win-core-kernel32-private-l1-1-0!_lwrite` at `0x1801e0ca6`
- `api-ms-win-core-kernel32-private-l1-1-0!_lwrite` at `0x1801e0ca6`

## pseudocode

```c
__int64 __fastcall mmioDOSIOProc(char *a1, int a2, CHAR *a3, const WCHAR *a4)
{
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  bool v11; // zf
  __int64 result; // rax
  UINT TempFileNameW; // eax
  DWORD v14; // r14d
  DWORD v15; // esi
  int v16; // eax
  DWORD v17; // ebp
  signed int FileW; // eax
  LPWSTR FilePart[2]; // [rsp+40h] [rbp-258h] BYREF
  WCHAR PathName[264]; // [rsp+50h] [rbp-248h] BYREF

  FilePart[0] = 0;
  if ( a2 )
  {
    v6 = a2 - 1;
    if ( !v6 )
    {
LABEL_48:
      LODWORD(result) = _lwrite(*((_DWORD *)a1 + 18), a3, (UINT)a4);
      goto LABEL_50;
    }
    v7 = v6 - 1;
    if ( !v7 )
    {
      LODWORD(result) = _llseek(*((_DWORD *)a1 + 18), (LONG)a3, (int)a4);
      if ( (_DWORD)result != -1 )
        *((_DWORD *)a1 + 17) = result;
      return (int)result;
    }
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( !v9 )
      {
        if ( ((unsigned __int8)a3 & 0x10) == 0 && _lclose(*((_DWORD *)a1 + 18)) == -1 )
          return 260;
        return 0;
      }
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 != 1 )
          return 0;
        v11 = !MoveFileW((LPCWSTR)a3, a4);
        goto LABEL_24;
      }
      goto LABEL_48;
    }
    if ( (*(_DWORD *)a1 & 0x20000) != 0 )
    {
      if ( !a3 )
        return 11;
      if ( !(unsigned int)GetTempPath2W(260, PathName) )
        StringCbCopyW(PathName, 0x208u, L".");
      TempFileNameW = GetTempFileNameW(PathName, L"sje", *((unsigned __int16 *)a1 + 36), (LPWSTR)a3);
      return TempFileNameW == 0 ? 0x101 : 0;
    }
    if ( !a3 )
    {
LABEL_45:
      *((_DWORD *)a1 + 17) = _llseek(*((_DWORD *)a1 + 18), 0, 1);
      return 0;
    }
    if ( (*(_DWORD *)a1 & 0x200) != 0 )
    {
      TempFileNameW = DeleteFileW((LPCWSTR)a3);
      return TempFileNameW == 0 ? 0x101 : 0;
    }
    if ( (*(_DWORD *)a1 & 0x5000) == 0x4000 )
    {
      v11 = GetFileAttributesW((LPCWSTR)a3) == -1;
LABEL_24:
      if ( !v11 )
        return 0;
      return 257;
    }
    if ( (*(_DWORD *)a1 & 0x100) != 0 )
    {
      if ( GetFullPathNameW((LPCWSTR)a3, 0x104u, PathName, FilePart) )
        return (unsigned int)StringCchCopyW((unsigned __int16 *)a3, 0x80u, PathName) != 0 ? 0x102 : 0;
      return 257;
    }
    v14 = 2;
    if ( (*a1 & 2) != 0 )
      v15 = -1073741824;
    else
      v15 = (((*(_DWORD *)a1 & 1) == 0) + 1) << 30;
    v16 = *(_DWORD *)a1 & 0x70;
    if ( v16 == 16 )
    {
      v17 = 0;
    }
    else if ( v16 == 32 )
    {
      v17 = 1;
    }
    else
    {
      v17 = (v16 != 48) + 2;
    }
    if ( (*(_DWORD *)a1 & 0x1000) != 0 )
    {
      if ( (unsigned int)StringCbCopyW(PathName, 0x208u, (const unsigned __int16 *)a3) )
        return 272;
    }
    else
    {
      v14 = 3;
      if ( !SearchPathW(0, (LPCWSTR)a3, 0, 0x103u, PathName, FilePart) )
        return 257;
    }
    FileW = (unsigned int)CreateFileW(PathName, v15, v17, 0, v14, 0x8000080u, 0);
    *((_DWORD *)a1 + 18) = FileW;
    if ( FileW != -1 )
    {
      if ( (*(_DWORD *)a1 & 0x4000) != 0 )
      {
        CloseHandle((HANDLE)FileW);
        return 0;
      }
      goto LABEL_45;
    }
    return 257;
  }
  LODWORD(result) = _lread(*((_DWORD *)a1 + 18), a3, (UINT)a4);
LABEL_50:
  if ( (_DWORD)result != -1 )
    *((_DWORD *)a1 + 17) += result;
  return (int)result;
}

```

## disassembly

```asm
0x1801e09f0  push    rbx
0x1801e09f2  push    rbp
0x1801e09f3  push    rsi
0x1801e09f4  push    rdi
0x1801e09f5  push    r14
0x1801e09f7  sub     rsp, 270h
0x1801e09fe  mov     rax, cs:__security_cookie
0x1801e0a05  xor     rax, rsp
0x1801e0a08  mov     [rsp+298h+var_38], rax
0x1801e0a10  mov     [rsp+298h+FilePart], 0
0x1801e0a19  mov     rdi, r8
0x1801e0a1c  mov     rbx, rcx
0x1801e0a1f  test    edx, edx
0x1801e0a21  jz      loc_1801E0CAE
0x1801e0a27  sub     edx, 1
0x1801e0a2a  jz      loc_1801E0C9D
0x1801e0a30  sub     edx, 1
0x1801e0a33  jz      loc_1801E0C85
0x1801e0a39  sub     edx, 1
0x1801e0a3c  jz      short loc_1801E0A8E
0x1801e0a3e  sub     edx, 1
0x1801e0a41  jz      short loc_1801E0A68
0x1801e0a43  sub     edx, 1
0x1801e0a46  jz      loc_1801E0C9D
0x1801e0a4c  cmp     edx, 1
0x1801e0a4f  jnz     loc_1801E0B35
0x1801e0a55  mov     rdx, r9; lpNewFileName
0x1801e0a58  mov     rcx, r8; lpExistingFileName
0x1801e0a5b  call    cs:__imp_MoveFileW
0x1801e0a61  test    eax, eax
0x1801e0a63  jmp     loc_1801E0B2F
0x1801e0a68  test    dil, 10h
0x1801e0a6c  jnz     loc_1801E0B35
0x1801e0a72  mov     ecx, [rcx+48h]; hFile
0x1801e0a75  call    cs:__imp__lclose
0x1801e0a7b  cmp     eax, 0FFFFFFFFh
0x1801e0a7e  jnz     loc_1801E0B35
0x1801e0a84  mov     eax, 104h
0x1801e0a89  jmp     loc_1801E0CC7
0x1801e0a8e  test    dword ptr [rcx], 20000h
0x1801e0a94  jz      short loc_1801E0AF9
0x1801e0a96  test    rdi, rdi
0x1801e0a99  jnz     short loc_1801E0AA3
0x1801e0a9b  lea     eax, [rdi+0Bh]
0x1801e0a9e  jmp     loc_1801E0CC7
0x1801e0aa3  lea     rdx, [rsp+298h+PathName]
0x1801e0aa8  mov     ecx, 104h
0x1801e0aad  call    cs:__imp_GetTempPath2W
0x1801e0ab3  test    eax, eax
0x1801e0ab5  jnz     short loc_1801E0ACD
0x1801e0ab7  lea     r8, asc_1802C8F70; "."
0x1801e0abe  mov     edx, 208h; unsigned __int64
0x1801e0ac3  lea     rcx, [rsp+298h+PathName]; unsigned __int16 *
0x1801e0ac8  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1801e0acd  movzx   r8d, word ptr [rbx+48h]; uUnique
0x1801e0ad2  lea     rdx, aSje; "sje"
0x1801e0ad9  mov     r9, rdi; lpTempFileName
0x1801e0adc  lea     rcx, [rsp+298h+PathName]; lpPathName
0x1801e0ae1  call    cs:__imp_GetTempFileNameW
0x1801e0ae7  neg     eax
0x1801e0ae9  sbb     rax, rax
0x1801e0aec  not     rax
0x1801e0aef  and     eax, 101h
0x1801e0af4  jmp     loc_1801E0CC7
0x1801e0af9  test    rdi, rdi
0x1801e0afc  jz      loc_1801E0C6E
0x1801e0b02  test    dword ptr [rcx], 200h
0x1801e0b08  jz      short loc_1801E0B15
0x1801e0b0a  mov     rcx, rdi; lpFileName
0x1801e0b0d  call    cs:__imp_DeleteFileW
0x1801e0b13  jmp     short loc_1801E0AE7
0x1801e0b15  mov     eax, [rcx]
0x1801e0b17  and     eax, 5000h
0x1801e0b1c  cmp     eax, 4000h
0x1801e0b21  jnz     short loc_1801E0B3C
0x1801e0b23  mov     rcx, rdi; lpFileName
0x1801e0b26  call    cs:__imp_GetFileAttributesW
0x1801e0b2c  cmp     eax, 0FFFFFFFFh
0x1801e0b2f  jz      loc_1801E0C67
0x1801e0b35  xor     eax, eax
0x1801e0b37  jmp     loc_1801E0CC7
0x1801e0b3c  test    dword ptr [rcx], 100h
0x1801e0b42  jz      short loc_1801E0B85
0x1801e0b44  lea     r9, [rsp+298h+FilePart]; lpFilePart
0x1801e0b49  mov     edx, 104h; nBufferLength
0x1801e0b4e  lea     r8, [rsp+298h+PathName]; lpBuffer
0x1801e0b53  mov     rcx, rdi; lpFileName
0x1801e0b56  call    cs:__imp_GetFullPathNameW
0x1801e0b5c  test    eax, eax
0x1801e0b5e  jz      loc_1801E0C67
0x1801e0b64  lea     r8, [rsp+298h+PathName]; unsigned __int16 *
0x1801e0b69  mov     edx, 80h; unsigned __int64
0x1801e0b6e  mov     rcx, rdi; unsigned __int16 *
0x1801e0b71  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801e0b76  neg     eax
0x1801e0b78  sbb     rax, rax
0x1801e0b7b  and     eax, 102h
0x1801e0b80  jmp     loc_1801E0CC7
0x1801e0b85  mov     r14d, 2
0x1801e0b8b  test    [rcx], r14b
0x1801e0b8e  jz      short loc_1801E0B97
0x1801e0b90  mov     esi, 0C0000000h
0x1801e0b95  jmp     short loc_1801E0BA3
0x1801e0b97  mov     esi, [rcx]
0x1801e0b99  not     esi
0x1801e0b9b  and     esi, 1
0x1801e0b9e  inc     esi
0x1801e0ba0  shl     esi, 1Eh
0x1801e0ba3  mov     eax, [rcx]
0x1801e0ba5  and     eax, 70h
0x1801e0ba8  cmp     eax, 10h
0x1801e0bab  jz      short loc_1801E0BC7
0x1801e0bad  cmp     eax, 20h ; ' '
0x1801e0bb0  jz      short loc_1801E0BC0
0x1801e0bb2  xor     ebp, ebp
0x1801e0bb4  cmp     eax, 30h ; '0'
0x1801e0bb7  setnz   bpl
0x1801e0bbb  add     ebp, r14d
0x1801e0bbe  jmp     short loc_1801E0BC9
0x1801e0bc0  mov     ebp, 1
0x1801e0bc5  jmp     short loc_1801E0BC9
0x1801e0bc7  xor     ebp, ebp
0x1801e0bc9  test    dword ptr [rcx], 1000h
0x1801e0bcf  jz      short loc_1801E0BEE
0x1801e0bd1  mov     edx, 208h; unsigned __int64
0x1801e0bd6  lea     rcx, [rsp+298h+PathName]; unsigned __int16 *
0x1801e0bdb  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1801e0be0  test    eax, eax
0x1801e0be2  jz      short loc_1801E0C20
0x1801e0be4  mov     eax, 110h
0x1801e0be9  jmp     loc_1801E0CC7
0x1801e0bee  lea     rax, [rsp+298h+FilePart]
0x1801e0bf3  mov     r9d, 103h; nBufferLength
0x1801e0bf9  mov     [rsp+298h+lpFilePart], rax; lpFilePart
0x1801e0bfe  xor     r8d, r8d; lpExtension
0x1801e0c01  lea     rax, [rsp+298h+PathName]
0x1801e0c06  mov     rdx, rdi; lpFileName
0x1801e0c09  xor     ecx, ecx; lpPath
0x1801e0c0b  mov     [rsp+298h+lpBuffer], rax; lpBuffer
0x1801e0c10  mov     r14d, 3
0x1801e0c16  call    cs:__imp_SearchPathW
0x1801e0c1c  test    eax, eax
0x1801e0c1e  jz      short loc_1801E0C67
0x1801e0c20  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x1801e0c29  lea     rcx, [rsp+298h+PathName]; lpFileName
0x1801e0c2e  mov     dword ptr [rsp+298h+lpFilePart], 8000080h; dwFlagsAndAttributes
0x1801e0c36  xor     r9d, r9d; lpSecurityAttributes
0x1801e0c39  mov     r8d, ebp; dwShareMode
0x1801e0c3c  mov     dword ptr [rsp+298h+lpBuffer], r14d; dwCreationDisposition
0x1801e0c41  mov     edx, esi; dwDesiredAccess
0x1801e0c43  call    cs:__imp_CreateFileW
0x1801e0c49  mov     [rbx+48h], eax
0x1801e0c4c  cmp     eax, 0FFFFFFFFh
0x1801e0c4f  jz      short loc_1801E0C67
0x1801e0c51  test    dword ptr [rbx], 4000h
0x1801e0c57  jz      short loc_1801E0C6E
0x1801e0c59  movsxd  rcx, eax; hObject
0x1801e0c5c  call    cs:__imp_CloseHandle
0x1801e0c62  jmp     loc_1801E0B35
0x1801e0c67  mov     eax, 101h
0x1801e0c6c  jmp     short loc_1801E0CC7
0x1801e0c6e  mov     ecx, [rbx+48h]; hFile
0x1801e0c71  xor     edx, edx; lOffset
0x1801e0c73  lea     r8d, [rdx+1]; iOrigin
0x1801e0c77  call    cs:__imp__llseek
0x1801e0c7d  mov     [rbx+44h], eax
0x1801e0c80  jmp     loc_1801E0B35
0x1801e0c85  mov     ecx, [rcx+48h]; hFile
0x1801e0c88  mov     r8d, r9d; iOrigin
0x1801e0c8b  mov     edx, edi; lOffset
0x1801e0c8d  call    cs:__imp__llseek
0x1801e0c93  cmp     eax, 0FFFFFFFFh
0x1801e0c96  jz      short loc_1801E0CC5
0x1801e0c98  mov     [rbx+44h], eax
0x1801e0c9b  jmp     short loc_1801E0CC5
0x1801e0c9d  mov     ecx, [rcx+48h]; hFile
0x1801e0ca0  mov     r8d, r9d; uBytes
0x1801e0ca3  mov     rdx, rdi; lpBuffer
0x1801e0ca6  call    cs:__imp__lwrite
0x1801e0cac  jmp     short loc_1801E0CBD
0x1801e0cae  mov     ecx, [rcx+48h]; hFile
0x1801e0cb1  mov     r8d, r9d; uBytes
0x1801e0cb4  mov     rdx, rdi; lpBuffer
0x1801e0cb7  call    cs:__imp__lread
0x1801e0cbd  cmp     eax, 0FFFFFFFFh
0x1801e0cc0  jz      short loc_1801E0CC5
0x1801e0cc2  add     [rbx+44h], eax
0x1801e0cc5  cdqe
0x1801e0cc7  mov     rcx, [rsp+298h+var_38]
0x1801e0ccf  xor     rcx, rsp; StackCookie
0x1801e0cd2  call    __security_check_cookie
0x1801e0cd7  add     rsp, 270h
0x1801e0cde  pop     r14
0x1801e0ce0  pop     rdi
0x1801e0ce1  pop     rsi
0x1801e0ce2  pop     rbp
0x1801e0ce3  pop     rbx
0x1801e0ce4  retn
```
