# CTptReadFile::ModifiedSinceOpen(void)

- ea: `0x18000c49c`
- end: `0x18000c5f5`
- name: `?ModifiedSinceOpen@CTptReadFile@@QEAAHXZ`
- size: `345`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006c90`
- `0x18000710c`
- `0x1800098a0`
- `0x180009d20`
- `0x18000a014`

## callees

- `0x18000c49c`
- `0x18003ce78`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000c4b3`
- `KERNEL32!EnterCriticalSection` at `0x18000c4b3`
- `KERNEL32!LeaveCriticalSection` at `0x18000c5dc`
- `KERNEL32!LeaveCriticalSection` at `0x18000c5dc`
- `KERNEL32!GetLastError` at `0x18000c50b`
- `KERNEL32!GetLastError` at `0x18000c54d`
- `KERNEL32!GetLastError` at `0x18000c58d`
- `KERNEL32!GetLastError` at `0x18000c50b`
- `KERNEL32!GetLastError` at `0x18000c54d`
- `KERNEL32!GetLastError` at `0x18000c58d`
- `KERNEL32!CloseHandle` at `0x18000c5ca`
- `KERNEL32!CloseHandle` at `0x18000c5ca`
- `KERNEL32!CreateFileW` at `0x18000c4f6`
- `KERNEL32!CreateFileW` at `0x18000c4f6`
- `KERNEL32!GetFileTime` at `0x18000c53d`
- `KERNEL32!GetFileTime` at `0x18000c57d`
- `KERNEL32!GetFileTime` at `0x18000c53d`
- `KERNEL32!GetFileTime` at `0x18000c57d`
- `KERNEL32!CompareFileTime` at `0x18000c5ad`
- `KERNEL32!CompareFileTime` at `0x18000c5ad`

## string_xrefs

- `0x18000c51f`: `base\eco\wds\transport\lib\tptreadfile.cpp`
- `0x18000c55f`: `base\eco\wds\transport\lib\tptreadfile.cpp`

## pseudocode

```c
__int64 __fastcall CTptReadFile::ModifiedSinceOpen(LPCRITICAL_SECTION lpCriticalSection)
{
  __int64 v2; // rbx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  const char *v5; // rdx
  unsigned int v6; // r9d
  DWORD v7; // eax
  const char *v8; // rdx
  unsigned int DebugInfo; // ebx
  _FILETIME LastWriteTime; // [rsp+50h] [rbp+8h] BYREF

  LastWriteTime = 0;
  v2 = -1;
  EnterCriticalSection(lpCriticalSection);
  if ( LODWORD(lpCriticalSection[3].DebugInfo) )
    goto LABEL_14;
  if ( LODWORD(lpCriticalSection[1].DebugInfo) != 1 )
  {
    if ( !GetFileTime(lpCriticalSection[1].OwningThread, 0, 0, &LastWriteTime) )
    {
      LastError = GetLastError();
      v6 = 307;
      goto LABEL_5;
    }
    goto LABEL_10;
  }
  FileW = CreateFileW(*(LPCWSTR *)&lpCriticalSection[1].LockCount, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v2 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = 293;
LABEL_5:
    ElValidateWin32(LastError, v5, "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp", v6);
    goto LABEL_14;
  }
  if ( GetFileTime(FileW, 0, 0, &LastWriteTime) )
  {
LABEL_10:
    if ( CompareFileTime(&LastWriteTime, (const FILETIME *)&lpCriticalSection[2].SpinCount) == 1 )
      LODWORD(lpCriticalSection[3].DebugInfo) = 1;
    goto LABEL_12;
  }
  v7 = GetLastError();
  ElValidateWin32(v7, v8, "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp", 0x12Au);
LABEL_12:
  if ( v2 != -1 )
    CloseHandle((HANDLE)v2);
LABEL_14:
  DebugInfo = (unsigned int)lpCriticalSection[3].DebugInfo;
  LeaveCriticalSection(lpCriticalSection);
  return DebugInfo;
}

```

## disassembly

```asm
0x18000c49c  mov     [rsp+arg_8], rbx
0x18000c4a1  push    rdi
0x18000c4a2  sub     rsp, 40h
0x18000c4a6  and     qword ptr [rsp+48h+LastWriteTime.dwLowDateTime], 0
0x18000c4ac  mov     rdi, rcx
0x18000c4af  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c4b3  call    cs:__imp_EnterCriticalSection
0x18000c4ba  nop     dword ptr [rax+rax+00h]
0x18000c4bf  cmp     dword ptr [rdi+78h], 0
0x18000c4c3  jnz     loc_18000C5D6
0x18000c4c9  cmp     dword ptr [rdi+28h], 1
0x18000c4cd  jnz     loc_18000C56F
0x18000c4d3  and     [rsp+48h+var_18], 0
0x18000c4d9  lea     r8d, [rbx+4]; dwShareMode
0x18000c4dd  mov     rcx, [rdi+30h]; lpFileName
0x18000c4e1  xor     r9d, r9d; lpSecurityAttributes
0x18000c4e4  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000c4ec  mov     edx, 80000000h; dwDesiredAccess
0x18000c4f1  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000c4f6  call    cs:__imp_CreateFileW
0x18000c4fd  nop     dword ptr [rax+rax+00h]
0x18000c502  mov     rbx, rax
0x18000c505  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c509  jnz     short loc_18000C530
0x18000c50b  call    cs:__imp_GetLastError
0x18000c512  nop     dword ptr [rax+rax+00h]
0x18000c517  mov     r9d, 125h; unsigned int
0x18000c51d  mov     ecx, eax; unsigned int
0x18000c51f  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000c526  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c52b  jmp     loc_18000C5D6
0x18000c530  lea     r9, [rsp+48h+LastWriteTime]; lpLastWriteTime
0x18000c535  xor     r8d, r8d; lpLastAccessTime
0x18000c538  xor     edx, edx; lpCreationTime
0x18000c53a  mov     rcx, rax; hFile
0x18000c53d  call    cs:__imp_GetFileTime
0x18000c544  nop     dword ptr [rax+rax+00h]
0x18000c549  test    eax, eax
0x18000c54b  jnz     short loc_18000C5A4
0x18000c54d  call    cs:__imp_GetLastError
0x18000c554  nop     dword ptr [rax+rax+00h]
0x18000c559  mov     r9d, 12Ah; unsigned int
0x18000c55f  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000c566  mov     ecx, eax; unsigned int
0x18000c568  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c56d  jmp     short loc_18000C5C1
0x18000c56f  mov     rcx, [rdi+38h]; hFile
0x18000c573  lea     r9, [rsp+48h+LastWriteTime]; lpLastWriteTime
0x18000c578  xor     r8d, r8d; lpLastAccessTime
0x18000c57b  xor     edx, edx; lpCreationTime
0x18000c57d  call    cs:__imp_GetFileTime
0x18000c584  nop     dword ptr [rax+rax+00h]
0x18000c589  test    eax, eax
0x18000c58b  jnz     short loc_18000C5A4
0x18000c58d  call    cs:__imp_GetLastError
0x18000c594  nop     dword ptr [rax+rax+00h]
0x18000c599  mov     r9d, 133h
0x18000c59f  jmp     loc_18000C51D
0x18000c5a4  lea     rdx, [rdi+70h]; lpFileTime2
0x18000c5a8  lea     rcx, [rsp+48h+LastWriteTime]; lpFileTime1
0x18000c5ad  call    cs:__imp_CompareFileTime
0x18000c5b4  nop     dword ptr [rax+rax+00h]
0x18000c5b9  cmp     eax, 1
0x18000c5bc  jnz     short loc_18000C5C1
0x18000c5be  mov     [rdi+78h], eax
0x18000c5c1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000c5c5  jz      short loc_18000C5D6
0x18000c5c7  mov     rcx, rbx; hObject
0x18000c5ca  call    cs:__imp_CloseHandle
0x18000c5d1  nop     dword ptr [rax+rax+00h]
0x18000c5d6  mov     ebx, [rdi+78h]
0x18000c5d9  mov     rcx, rdi; lpCriticalSection
0x18000c5dc  call    cs:__imp_LeaveCriticalSection
0x18000c5e3  nop     dword ptr [rax+rax+00h]
0x18000c5e8  mov     eax, ebx
0x18000c5ea  mov     rbx, [rsp+48h+arg_8]
0x18000c5ef  add     rsp, 40h
0x18000c5f3  pop     rdi
0x18000c5f4  retn
```
