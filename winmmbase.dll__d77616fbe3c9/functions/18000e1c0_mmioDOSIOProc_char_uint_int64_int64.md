# mmioDOSIOProc(char *,uint,__int64,__int64)

- ea: `0x18000e1c0`
- end: `0x18000e4e2`
- name: `?mmioDOSIOProc@@YA_JPEADI_J1@Z`
- size: `802`
- prototype: `__int64(char *, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x180001eb0`
- `0x18000da80`
- `0x18000e1c0`
- `0x1800106c0`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18000e311`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18000e311`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000e40f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000e40f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e48f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e48f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000e3e9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000e3e9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e3c6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e3c6`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18000e3bb`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18000e3bb`
- `api-ms-win-core-kernel32-private-l1-1-0!_lwrite` at `0x18000e21d`
- `api-ms-win-core-kernel32-private-l1-1-0!_lwrite` at `0x18000e21d`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x18000e253`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x18000e4c0`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x18000e253`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x18000e4c0`
- `api-ms-win-core-kernel32-private-l1-1-0!_lclose` at `0x18000e357`
- `api-ms-win-core-kernel32-private-l1-1-0!_lclose` at `0x18000e357`
- `api-ms-win-core-kernel32-private-l1-1-0!_lread` at `0x18000e4d7`
- `api-ms-win-core-kernel32-private-l1-1-0!_lread` at `0x18000e4d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4ac`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18000e387`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18000e387`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18000e33d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18000e33d`

## pseudocode

```c
__int64 __fastcall mmioDOSIOProc(char *a1, int a2, void *a3, const WCHAR *a4)
{
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  __int64 result; // rax
  DWORD v12; // r14d
  DWORD v13; // esi
  int v14; // eax
  DWORD v15; // ebp
  bool v16; // zf
  UINT TempFileNameW; // eax
  signed int FileW; // eax
  LPWSTR FilePart[2]; // [rsp+40h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-248h] BYREF

  FilePart[0] = 0;
  if ( !a2 )
  {
    LODWORD(result) = _lread(*((_DWORD *)a1 + 18), a3, (UINT)a4);
LABEL_8:
    if ( (_DWORD)result != -1 )
      *((_DWORD *)a1 + 17) += result;
    return (int)result;
  }
  v6 = a2 - 1;
  if ( !v6 )
  {
LABEL_7:
    LODWORD(result) = _lwrite(*((_DWORD *)a1 + 18), (LPCCH)a3, (UINT)a4);
    goto LABEL_8;
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
  if ( !v8 )
  {
    if ( (*(_DWORD *)a1 & 0x20000) != 0 )
    {
      if ( !a3 )
        return 11;
      if ( !(unsigned int)GetTempPath2W(260, Buffer) )
        StringCbCopyW(Buffer, 0x208u, L".");
      TempFileNameW = GetTempFileNameW(Buffer, L"sje", *((unsigned __int16 *)a1 + 36), (LPWSTR)a3);
    }
    else
    {
      if ( !a3 )
        goto LABEL_53;
      if ( (*(_DWORD *)a1 & 0x200) == 0 )
      {
        if ( (*(_DWORD *)a1 & 0x4000) != 0 && (*(_DWORD *)a1 & 0x1000) == 0 )
        {
          v16 = GetFileAttributesW((LPCWSTR)a3) == -1;
          goto LABEL_42;
        }
        if ( (*(_DWORD *)a1 & 0x100) != 0 )
        {
          if ( GetFullPathNameW((LPCWSTR)a3, 0x104u, Buffer, FilePart) )
            return (unsigned int)StringCchCopyW((unsigned __int16 *)a3, 0x80u, Buffer) != 0 ? 0x102 : 0;
          return 257;
        }
        v12 = 2;
        if ( (*a1 & 2) != 0 )
          v13 = -1073741824;
        else
          v13 = (((*(_DWORD *)a1 & 1) == 0) + 1) << 30;
        v14 = *(_DWORD *)a1 & 0x70;
        if ( v14 == 16 )
        {
          v15 = 0;
        }
        else if ( v14 == 32 )
        {
          v15 = 1;
        }
        else
        {
          v15 = (v14 != 48) + 2;
        }
        if ( (*(_DWORD *)a1 & 0x1000) != 0 )
        {
          if ( (unsigned int)StringCbCopyW(Buffer, 0x208u, (const unsigned __int16 *)a3) )
            return 272;
        }
        else
        {
          v12 = 3;
          if ( !SearchPathW(0, (LPCWSTR)a3, 0, 0x103u, Buffer, FilePart) )
            return 257;
        }
        FileW = (unsigned int)CreateFileW(Buffer, v13, v15, 0, v12, 0x8000080u, 0);
        *((_DWORD *)a1 + 18) = FileW;
        if ( FileW == -1 )
          return 257;
        if ( (*(_DWORD *)a1 & 0x4000) != 0 )
        {
          CloseHandle((HANDLE)FileW);
          return 0;
        }
LABEL_53:
        *((_DWORD *)a1 + 17) = _llseek(*((_DWORD *)a1 + 18), 0, 1);
        return 0;
      }
      TempFileNameW = DeleteFileW((LPCWSTR)a3);
    }
    return TempFileNameW == 0 ? 0x101 : 0;
  }
  v9 = v8 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( !v10 )
      goto LABEL_7;
    if ( v10 != 1 )
      return 0;
    v16 = !MoveFileW((LPCWSTR)a3, a4);
LABEL_42:
    if ( !v16 )
      return 0;
    return 257;
  }
  if ( ((unsigned __int8)a3 & 0x10) != 0 || _lclose(*((_DWORD *)a1 + 18)) != -1 )
    return 0;
  return 260;
}

```

## disassembly

```asm
0x18000e1c0  push    rbx
0x18000e1c2  push    rbp
0x18000e1c3  push    rsi
0x18000e1c4  push    rdi
0x18000e1c5  push    r14
0x18000e1c7  sub     rsp, 270h
0x18000e1ce  mov     rax, cs:__security_cookie
0x18000e1d5  xor     rax, rsp
0x18000e1d8  mov     [rsp+298h+var_38], rax
0x18000e1e0  mov     [rsp+298h+FilePart], 0
0x18000e1e9  mov     rdi, r8
0x18000e1ec  mov     rbx, rcx
0x18000e1ef  test    edx, edx
0x18000e1f1  jz      loc_18000E4CE
0x18000e1f7  sub     edx, 1
0x18000e1fa  jz      short loc_18000E214
0x18000e1fc  sub     edx, 1
0x18000e1ff  jz      short loc_18000E24B
0x18000e201  sub     edx, 1
0x18000e204  jz      short loc_18000E270
0x18000e206  sub     edx, 1
0x18000e209  jz      loc_18000E34A
0x18000e20f  sub     edx, 1
0x18000e212  jnz     short loc_18000E263
0x18000e214  mov     ecx, [rcx+48h]; hFile
0x18000e217  mov     r8d, r9d; uBytes
0x18000e21a  mov     rdx, rdi; lpBuffer
0x18000e21d  call    cs:__imp__lwrite
0x18000e223  cmp     eax, 0FFFFFFFFh
0x18000e226  jz      short loc_18000E22B
0x18000e228  add     [rbx+44h], eax
0x18000e22b  cdqe
0x18000e22d  mov     rcx, [rsp+298h+var_38]
0x18000e235  xor     rcx, rsp; StackCookie
0x18000e238  call    __security_check_cookie
0x18000e23d  add     rsp, 270h
0x18000e244  pop     r14
0x18000e246  pop     rdi
0x18000e247  pop     rsi
0x18000e248  pop     rbp
0x18000e249  pop     rbx
0x18000e24a  retn
0x18000e24b  mov     ecx, [rcx+48h]; hFile
0x18000e24e  mov     r8d, r9d; iOrigin
0x18000e251  mov     edx, edi; lOffset
0x18000e253  call    cs:__imp__llseek
0x18000e259  cmp     eax, 0FFFFFFFFh
0x18000e25c  jz      short loc_18000E22B
0x18000e25e  mov     [rbx+44h], eax
0x18000e261  jmp     short loc_18000E22B
0x18000e263  cmp     edx, 1
0x18000e266  jz      loc_18000E337
0x18000e26c  xor     eax, eax
0x18000e26e  jmp     short loc_18000E22D
0x18000e270  test    dword ptr [rcx], 20000h
0x18000e276  jnz     loc_18000E370
0x18000e27c  test    rdi, rdi
0x18000e27f  jz      loc_18000E4B7
0x18000e285  test    dword ptr [rcx], 200h
0x18000e28b  jnz     loc_18000E3C3
0x18000e291  test    dword ptr [rbx], 4000h
0x18000e297  mov     ecx, 1000h
0x18000e29c  jnz     loc_18000E3DE
0x18000e2a2  test    dword ptr [rbx], 100h
0x18000e2a8  jnz     loc_18000E3FD
0x18000e2ae  mov     r14d, 2
0x18000e2b4  test    [rbx], r14b
0x18000e2b7  jz      short loc_18000E329
0x18000e2b9  mov     esi, 0C0000000h
0x18000e2be  mov     eax, [rbx]
0x18000e2c0  and     eax, 70h
0x18000e2c3  cmp     eax, 10h
0x18000e2c6  jz      loc_18000E448
0x18000e2cc  cmp     eax, 20h ; ' '
0x18000e2cf  jz      loc_18000E43E
0x18000e2d5  xor     ebp, ebp
0x18000e2d7  cmp     eax, 30h ; '0'
0x18000e2da  setnz   bpl
0x18000e2de  add     ebp, r14d
0x18000e2e1  test    [rbx], ecx
0x18000e2e3  jnz     loc_18000E44F
0x18000e2e9  lea     rax, [rsp+298h+FilePart]
0x18000e2ee  mov     r9d, 103h; nBufferLength
0x18000e2f4  mov     [rsp+298h+lpFilePart], rax; lpFilePart
0x18000e2f9  xor     r8d, r8d; lpExtension
0x18000e2fc  lea     rax, [rsp+298h+Buffer]
0x18000e301  mov     rdx, rdi; lpFileName
0x18000e304  xor     ecx, ecx; lpPath
0x18000e306  mov     [rsp+298h+lpBuffer], rax; lpBuffer
0x18000e30b  mov     r14d, 3
0x18000e311  call    cs:__imp_SearchPathW
0x18000e317  test    eax, eax
0x18000e319  jnz     loc_18000E46C
0x18000e31f  mov     eax, 101h
0x18000e324  jmp     loc_18000E22D
0x18000e329  mov     esi, [rbx]
0x18000e32b  not     esi
0x18000e32d  and     esi, 1
0x18000e330  inc     esi
0x18000e332  shl     esi, 1Eh
0x18000e335  jmp     short loc_18000E2BE
0x18000e337  mov     rdx, r9; lpNewFileName
0x18000e33a  mov     rcx, rdi; lpExistingFileName
0x18000e33d  call    cs:__imp_MoveFileW
0x18000e343  test    eax, eax
0x18000e345  jmp     loc_18000E3F2
0x18000e34a  test    dil, 10h
0x18000e34e  jnz     loc_18000E26C
0x18000e354  mov     ecx, [rcx+48h]; hFile
0x18000e357  call    cs:__imp__lclose
0x18000e35d  cmp     eax, 0FFFFFFFFh
0x18000e360  jnz     loc_18000E26C
0x18000e366  mov     eax, 104h
0x18000e36b  jmp     loc_18000E22D
0x18000e370  test    rdi, rdi
0x18000e373  jnz     short loc_18000E37D
0x18000e375  lea     eax, [rdi+0Bh]
0x18000e378  jmp     loc_18000E22D
0x18000e37d  lea     rdx, [rsp+298h+Buffer]
0x18000e382  mov     ecx, 104h
0x18000e387  call    cs:__imp_GetTempPath2W
0x18000e38d  test    eax, eax
0x18000e38f  jnz     short loc_18000E3A7
0x18000e391  lea     r8, asc_180025850; "."
0x18000e398  mov     edx, 208h; unsigned __int64
0x18000e39d  lea     rcx, [rsp+298h+Buffer]; unsigned __int16 *
0x18000e3a2  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e3a7  movzx   r8d, word ptr [rbx+48h]; uUnique
0x18000e3ac  lea     rdx, PrefixString; "sje"
0x18000e3b3  mov     r9, rdi; lpTempFileName
0x18000e3b6  lea     rcx, [rsp+298h+Buffer]; lpPathName
0x18000e3bb  call    cs:__imp_GetTempFileNameW
0x18000e3c1  jmp     short loc_18000E3CC
0x18000e3c3  mov     rcx, rdi; lpFileName
0x18000e3c6  call    cs:__imp_DeleteFileW
0x18000e3cc  neg     eax
0x18000e3ce  sbb     rax, rax
0x18000e3d1  not     rax
0x18000e3d4  and     eax, 101h
0x18000e3d9  jmp     loc_18000E22D
0x18000e3de  test    [rbx], ecx
0x18000e3e0  jnz     loc_18000E2A2
0x18000e3e6  mov     rcx, rdi; lpFileName
0x18000e3e9  call    cs:__imp_GetFileAttributesW
0x18000e3ef  cmp     eax, 0FFFFFFFFh
0x18000e3f2  jz      loc_18000E31F
0x18000e3f8  jmp     loc_18000E26C
0x18000e3fd  lea     r9, [rsp+298h+FilePart]; lpFilePart
0x18000e402  mov     edx, 104h; nBufferLength
0x18000e407  lea     r8, [rsp+298h+Buffer]; lpBuffer
0x18000e40c  mov     rcx, rdi; lpFileName
0x18000e40f  call    cs:__imp_GetFullPathNameW
0x18000e415  test    eax, eax
0x18000e417  jz      loc_18000E31F
0x18000e41d  lea     r8, [rsp+298h+Buffer]; unsigned __int16 *
0x18000e422  mov     edx, 80h; unsigned __int64
0x18000e427  mov     rcx, rdi; unsigned __int16 *
0x18000e42a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e42f  neg     eax
0x18000e431  sbb     rax, rax
0x18000e434  and     eax, 102h
0x18000e439  jmp     loc_18000E22D
0x18000e43e  mov     ebp, 1
0x18000e443  jmp     loc_18000E2E1
0x18000e448  xor     ebp, ebp
0x18000e44a  jmp     loc_18000E2E1
0x18000e44f  mov     edx, 208h; unsigned __int64
0x18000e454  lea     rcx, [rsp+298h+Buffer]; unsigned __int16 *
0x18000e459  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e45e  test    eax, eax
0x18000e460  jz      short loc_18000E46C
0x18000e462  mov     eax, 110h
0x18000e467  jmp     loc_18000E22D
0x18000e46c  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x18000e475  lea     rcx, [rsp+298h+Buffer]; lpFileName
0x18000e47a  mov     dword ptr [rsp+298h+lpFilePart], 8000080h; dwFlagsAndAttributes
0x18000e482  xor     r9d, r9d; lpSecurityAttributes
0x18000e485  mov     r8d, ebp; dwShareMode
0x18000e488  mov     dword ptr [rsp+298h+lpBuffer], r14d; dwCreationDisposition
0x18000e48d  mov     edx, esi; dwDesiredAccess
0x18000e48f  call    cs:__imp_CreateFileW
0x18000e495  mov     [rbx+48h], eax
0x18000e498  cmp     eax, 0FFFFFFFFh
0x18000e49b  jz      loc_18000E31F
0x18000e4a1  test    dword ptr [rbx], 4000h
0x18000e4a7  jz      short loc_18000E4B7
0x18000e4a9  movsxd  rcx, eax; hObject
0x18000e4ac  call    cs:__imp_CloseHandle
0x18000e4b2  jmp     loc_18000E26C
0x18000e4b7  mov     ecx, [rbx+48h]; hFile
0x18000e4ba  xor     edx, edx; lOffset
0x18000e4bc  lea     r8d, [rdx+1]; iOrigin
0x18000e4c0  call    cs:__imp__llseek
0x18000e4c6  mov     [rbx+44h], eax
0x18000e4c9  jmp     loc_18000E26C
0x18000e4ce  mov     ecx, [rcx+48h]; hFile
0x18000e4d1  mov     r8d, r9d; uBytes
0x18000e4d4  mov     rdx, rdi; lpBuffer
0x18000e4d7  call    cs:__imp__lread
0x18000e4dd  jmp     loc_18000E223
```
