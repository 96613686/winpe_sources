# WdsGetFileWriteTime

- ea: `0x18001cca0`
- end: `0x18001cd97`
- name: `WdsGetFileWriteTime`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001b0cc`
- `0x18001cca0`

## import_xrefs

- `KERNEL32!GetFileTime` at `0x18001cd21`
- `KERNEL32!GetFileTime` at `0x18001cd21`
- `KERNEL32!CreateFileW` at `0x18001ccdb`
- `KERNEL32!CreateFileW` at `0x18001ccdb`
- `KERNEL32!GetLastError` at `0x18001ccf0`
- `KERNEL32!GetLastError` at `0x18001cd31`
- `KERNEL32!GetLastError` at `0x18001ccf0`
- `KERNEL32!GetLastError` at `0x18001cd31`
- `KERNEL32!CloseHandle` at `0x18001cd73`
- `KERNEL32!CloseHandle` at `0x18001cd73`

## pseudocode

```c
__int64 __fastcall WdsGetFileWriteTime(const WCHAR *a1, struct _FILETIME *a2, DWORD *a3)
{
  unsigned int v3; // ebx
  HANDLE FileW; // rax
  void *v7; // rbp
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  DWORD v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  struct _FILETIME v14; // rax
  struct _FILETIME LastWriteTime; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  LastWriteTime = 0;
  FileW = CreateFileW(a1, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v7 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v3 = ElValidateWin32_8(LastError, v9, v10, 4217);
    if ( !v3 )
      return 31;
  }
  else
  {
    if ( GetFileTime(FileW, 0, 0, &LastWriteTime) )
    {
      v14 = LastWriteTime;
      if ( a3 )
      {
        a3[1] = LastWriteTime.dwHighDateTime;
        *a3 = v14.dwLowDateTime;
      }
      if ( a2 )
        *a2 = v14;
    }
    else
    {
      v11 = GetLastError();
      v3 = ElValidateWin32_8(v11, v12, v13, 4222);
      if ( !v3 )
        v3 = 31;
    }
    CloseHandle(v7);
  }
  return v3;
}

```

## disassembly

```asm
0x18001cca0  mov     rax, rsp
0x18001cca3  mov     [rax+8], rbx
0x18001cca7  mov     [rax+10h], rbp
0x18001ccab  mov     [rax+18h], rsi
0x18001ccaf  push    rdi
0x18001ccb0  sub     rsp, 40h
0x18001ccb4  xor     ebx, ebx
0x18001ccb6  mov     rdi, r8
0x18001ccb9  and     [rax-18h], rbx
0x18001ccbd  mov     rsi, rdx
0x18001ccc0  and     [rax+20h], rbx
0x18001ccc4  xor     r9d, r9d; lpSecurityAttributes
0x18001ccc7  mov     dword ptr [rax-20h], 80h
0x18001ccce  mov     edx, 80000000h; dwDesiredAccess
0x18001ccd3  lea     r8d, [rbx+3]; dwShareMode
0x18001ccd7  mov     [rax-28h], r8d
0x18001ccdb  call    cs:__imp_CreateFileW
0x18001cce2  nop     dword ptr [rax+rax+00h]
0x18001cce7  mov     rbp, rax
0x18001ccea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ccee  jnz     short loc_18001CD14
0x18001ccf0  call    cs:__imp_GetLastError
0x18001ccf7  nop     dword ptr [rax+rax+00h]
0x18001ccfc  mov     ecx, eax
0x18001ccfe  mov     r9d, 1079h
0x18001cd04  call    ElValidateWin32_8
0x18001cd09  mov     ebx, eax
0x18001cd0b  test    eax, eax
0x18001cd0d  jnz     short loc_18001CD7F
0x18001cd0f  lea     ebx, [rbp+20h]
0x18001cd12  jmp     short loc_18001CD7F
0x18001cd14  lea     r9, [rsp+48h+LastWriteTime]; lpLastWriteTime
0x18001cd19  xor     r8d, r8d; lpLastAccessTime
0x18001cd1c  xor     edx, edx; lpCreationTime
0x18001cd1e  mov     rcx, rbp; hFile
0x18001cd21  call    cs:__imp_GetFileTime
0x18001cd28  nop     dword ptr [rax+rax+00h]
0x18001cd2d  test    eax, eax
0x18001cd2f  jnz     short loc_18001CD55
0x18001cd31  call    cs:__imp_GetLastError
0x18001cd38  nop     dword ptr [rax+rax+00h]
0x18001cd3d  mov     ecx, eax
0x18001cd3f  mov     r9d, 107Eh
0x18001cd45  call    ElValidateWin32_8
0x18001cd4a  mov     ebx, eax
0x18001cd4c  test    eax, eax
0x18001cd4e  jnz     short loc_18001CD70
0x18001cd50  lea     ebx, [rax+1Fh]
0x18001cd53  jmp     short loc_18001CD70
0x18001cd55  mov     rax, qword ptr [rsp+48h+LastWriteTime.dwLowDateTime]
0x18001cd5a  test    rdi, rdi
0x18001cd5d  jz      short loc_18001CD68
0x18001cd5f  mov     ecx, [rsp+48h+LastWriteTime.dwHighDateTime]
0x18001cd63  mov     [rdi+4], ecx
0x18001cd66  mov     [rdi], eax
0x18001cd68  test    rsi, rsi
0x18001cd6b  jz      short loc_18001CD70
0x18001cd6d  mov     [rsi], rax
0x18001cd70  mov     rcx, rbp; hObject
0x18001cd73  call    cs:__imp_CloseHandle
0x18001cd7a  nop     dword ptr [rax+rax+00h]
0x18001cd7f  mov     rbp, [rsp+48h+arg_8]
0x18001cd84  mov     eax, ebx
0x18001cd86  mov     rbx, [rsp+48h+arg_0]
0x18001cd8b  mov     rsi, [rsp+48h+arg_10]
0x18001cd90  add     rsp, 40h
0x18001cd94  pop     rdi
0x18001cd95  retn
```
