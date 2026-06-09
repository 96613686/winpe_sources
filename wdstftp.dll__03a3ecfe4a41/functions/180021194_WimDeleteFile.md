# WimDeleteFile

- ea: `0x180021194`
- end: `0x180021259`
- name: `WimDeleteFile`
- size: `197`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000f7c4`
- `0x180014454`

## callees

- `0x180021194`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x1800211bd`
- `KERNEL32!SetFileAttributesW` at `0x1800211bd`
- `KERNEL32!GetLastError` at `0x180021214`
- `KERNEL32!GetLastError` at `0x180021214`
- `KERNEL32!CloseHandle` at `0x180021202`
- `KERNEL32!CloseHandle` at `0x180021202`
- `KERNEL32!CreateFileW` at `0x1800211ed`
- `KERNEL32!CreateFileW` at `0x1800211ed`
- `KERNEL32!SetLastError` at `0x180021226`
- `KERNEL32!SetLastError` at `0x18002123b`
- `KERNEL32!SetLastError` at `0x180021226`
- `KERNEL32!SetLastError` at `0x18002123b`

## pseudocode

```c
__int64 __fastcall WimDeleteFile(LPCWSTR lpFileName)
{
  unsigned int v2; // ebx
  HANDLE FileW; // rax
  DWORD LastError; // eax

  v2 = 0;
  if ( lpFileName && *lpFileName )
  {
    SetFileAttributesW(lpFileName, 0x80u);
    FileW = CreateFileW(lpFileName, 0x10000u, 7u, 0, 3u, 0x6200000u, 0);
    if ( FileW == (HANDLE)-1LL || (v2 = CloseHandle(FileW)) == 0 )
    {
      LastError = GetLastError();
      if ( LastError )
        SetLastError(LastError);
    }
    return v2;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x180021194  mov     [rsp+arg_0], rbx
0x180021199  mov     [rsp+arg_8], rsi
0x18002119e  push    rdi
0x18002119f  sub     rsp, 40h
0x1800211a3  xor     esi, esi
0x1800211a5  mov     rdi, rcx
0x1800211a8  mov     ebx, esi
0x1800211aa  test    rcx, rcx
0x1800211ad  jz      loc_180021236
0x1800211b3  cmp     [rcx], si
0x1800211b6  jz      short loc_180021236
0x1800211b8  mov     edx, 80h; dwFileAttributes
0x1800211bd  call    cs:__imp_SetFileAttributesW
0x1800211c4  nop     dword ptr [rax+rax+00h]
0x1800211c9  mov     [rsp+48h+hTemplateFile], rsi; hTemplateFile
0x1800211ce  lea     r8d, [rsi+7]; dwShareMode
0x1800211d2  mov     [rsp+48h+dwFlagsAndAttributes], 6200000h; dwFlagsAndAttributes
0x1800211da  xor     r9d, r9d; lpSecurityAttributes
0x1800211dd  mov     edx, 10000h; dwDesiredAccess
0x1800211e2  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800211ea  mov     rcx, rdi; lpFileName
0x1800211ed  call    cs:__imp_CreateFileW
0x1800211f4  nop     dword ptr [rax+rax+00h]
0x1800211f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800211fd  jz      short loc_180021214
0x1800211ff  mov     rcx, rax; hObject
0x180021202  call    cs:__imp_CloseHandle
0x180021209  nop     dword ptr [rax+rax+00h]
0x18002120e  mov     ebx, eax
0x180021210  test    eax, eax
0x180021212  jnz     short loc_180021232
0x180021214  call    cs:__imp_GetLastError
0x18002121b  nop     dword ptr [rax+rax+00h]
0x180021220  test    eax, eax
0x180021222  jz      short loc_180021232
0x180021224  mov     ecx, eax; dwErrCode
0x180021226  call    cs:__imp_SetLastError
0x18002122d  nop     dword ptr [rax+rax+00h]
0x180021232  mov     eax, ebx
0x180021234  jmp     short loc_180021249
0x180021236  mov     ecx, 57h ; 'W'; dwErrCode
0x18002123b  call    cs:__imp_SetLastError
0x180021242  nop     dword ptr [rax+rax+00h]
0x180021247  xor     eax, eax
0x180021249  mov     rbx, [rsp+48h+arg_0]
0x18002124e  mov     rsi, [rsp+48h+arg_8]
0x180021253  add     rsp, 40h
0x180021257  pop     rdi
0x180021258  retn
```
