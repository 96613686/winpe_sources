# WdsGetFileWriteTime

- ea: `0x18001bdc0`
- end: `0x18001beb7`
- name: `WdsGetFileWriteTime`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001a28c`
- `0x18001bdc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001be10`
- `KERNEL32!GetLastError` at `0x18001be51`
- `KERNEL32!GetLastError` at `0x18001be10`
- `KERNEL32!GetLastError` at `0x18001be51`
- `KERNEL32!CloseHandle` at `0x18001be93`
- `KERNEL32!CloseHandle` at `0x18001be93`
- `KERNEL32!CreateFileW` at `0x18001bdfb`
- `KERNEL32!CreateFileW` at `0x18001bdfb`
- `KERNEL32!GetFileTime` at `0x18001be41`
- `KERNEL32!GetFileTime` at `0x18001be41`

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
0x18001bdc0  mov     rax, rsp
0x18001bdc3  mov     [rax+8], rbx
0x18001bdc7  mov     [rax+10h], rbp
0x18001bdcb  mov     [rax+18h], rsi
0x18001bdcf  push    rdi
0x18001bdd0  sub     rsp, 40h
0x18001bdd4  xor     ebx, ebx
0x18001bdd6  mov     rdi, r8
0x18001bdd9  and     [rax-18h], rbx
0x18001bddd  mov     rsi, rdx
0x18001bde0  and     [rax+20h], rbx
0x18001bde4  xor     r9d, r9d; lpSecurityAttributes
0x18001bde7  mov     dword ptr [rax-20h], 80h
0x18001bdee  mov     edx, 80000000h; dwDesiredAccess
0x18001bdf3  lea     r8d, [rbx+3]; dwShareMode
0x18001bdf7  mov     [rax-28h], r8d
0x18001bdfb  call    cs:__imp_CreateFileW
0x18001be02  nop     dword ptr [rax+rax+00h]
0x18001be07  mov     rbp, rax
0x18001be0a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001be0e  jnz     short loc_18001BE34
0x18001be10  call    cs:__imp_GetLastError
0x18001be17  nop     dword ptr [rax+rax+00h]
0x18001be1c  mov     ecx, eax
0x18001be1e  mov     r9d, 1079h
0x18001be24  call    ElValidateWin32_8
0x18001be29  mov     ebx, eax
0x18001be2b  test    eax, eax
0x18001be2d  jnz     short loc_18001BE9F
0x18001be2f  lea     ebx, [rbp+20h]
0x18001be32  jmp     short loc_18001BE9F
0x18001be34  lea     r9, [rsp+48h+LastWriteTime]; lpLastWriteTime
0x18001be39  xor     r8d, r8d; lpLastAccessTime
0x18001be3c  xor     edx, edx; lpCreationTime
0x18001be3e  mov     rcx, rbp; hFile
0x18001be41  call    cs:__imp_GetFileTime
0x18001be48  nop     dword ptr [rax+rax+00h]
0x18001be4d  test    eax, eax
0x18001be4f  jnz     short loc_18001BE75
0x18001be51  call    cs:__imp_GetLastError
0x18001be58  nop     dword ptr [rax+rax+00h]
0x18001be5d  mov     ecx, eax
0x18001be5f  mov     r9d, 107Eh
0x18001be65  call    ElValidateWin32_8
0x18001be6a  mov     ebx, eax
0x18001be6c  test    eax, eax
0x18001be6e  jnz     short loc_18001BE90
0x18001be70  lea     ebx, [rax+1Fh]
0x18001be73  jmp     short loc_18001BE90
0x18001be75  mov     rax, qword ptr [rsp+48h+LastWriteTime.dwLowDateTime]
0x18001be7a  test    rdi, rdi
0x18001be7d  jz      short loc_18001BE88
0x18001be7f  mov     ecx, [rsp+48h+LastWriteTime.dwHighDateTime]
0x18001be83  mov     [rdi+4], ecx
0x18001be86  mov     [rdi], eax
0x18001be88  test    rsi, rsi
0x18001be8b  jz      short loc_18001BE90
0x18001be8d  mov     [rsi], rax
0x18001be90  mov     rcx, rbp; hObject
0x18001be93  call    cs:__imp_CloseHandle
0x18001be9a  nop     dword ptr [rax+rax+00h]
0x18001be9f  mov     rbp, [rsp+48h+arg_8]
0x18001bea4  mov     eax, ebx
0x18001bea6  mov     rbx, [rsp+48h+arg_0]
0x18001beab  mov     rsi, [rsp+48h+arg_10]
0x18001beb0  add     rsp, 40h
0x18001beb4  pop     rdi
0x18001beb5  retn
```
