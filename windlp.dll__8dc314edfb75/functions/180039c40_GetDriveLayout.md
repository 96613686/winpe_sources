# GetDriveLayout

- ea: `0x180039c40`
- end: `0x180039d3b`
- name: `GetDriveLayout`
- size: `251`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001ba90`
- `0x180039d44`
- `0x1800409cc`

## callees

- `0x180035c20`
- `0x180039c40`
- `0x18003a050`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039cd0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039cd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039c81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039d0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039c81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039cf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039cf8`

## pseudocode

```c
__int64 __fastcall GetDriveLayout(int a1)
{
  __int64 DriveLayout; // rsi
  int v4; // eax
  HANDLE FileW; // rax
  void *v6; // rdi
  DWORD LastError; // ebx
  WCHAR FileName[264]; // [rsp+40h] [rbp-238h] BYREF

  memset_0(FileName, 0, 0x208u);
  if ( a1 >= 0 )
  {
    DriveLayout = 0;
    v4 = StringCchPrintfW(FileName, 0x104u, L"\\\\.\\PHYSICALDRIVE%d", (unsigned int)a1);
    if ( v4 < 0 )
    {
      LastError = (unsigned __int16)v4;
    }
    else
    {
      FileW = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
      v6 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
      }
      else
      {
        DriveLayout = InternalGetDriveLayout(FileW);
        LastError = GetLastError();
        CloseHandle(v6);
      }
    }
    SetLastError(LastError);
    return DriveLayout;
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
0x180039c40  mov     [rsp+arg_10], rbx
0x180039c45  push    rbp
0x180039c46  push    rsi
0x180039c47  push    rdi
0x180039c48  sub     rsp, 260h
0x180039c4f  mov     rax, cs:__security_cookie
0x180039c56  xor     rax, rsp
0x180039c59  mov     [rsp+278h+var_28], rax
0x180039c61  mov     rbp, rdx
0x180039c64  mov     ebx, ecx
0x180039c66  xor     edx, edx; Val
0x180039c68  lea     rcx, [rsp+278h+FileName]; void *
0x180039c6d  mov     r8d, 208h; Size
0x180039c73  call    memset_0
0x180039c78  test    ebx, ebx
0x180039c7a  jns     short loc_180039C8E
0x180039c7c  mov     ecx, 57h ; 'W'; dwErrCode
0x180039c81  call    cs:__imp_SetLastError
0x180039c87  xor     eax, eax
0x180039c89  jmp     loc_180039D18
0x180039c8e  mov     r9d, ebx
0x180039c91  lea     r8, aPhysicaldriveD_0; "\\\\.\\PHYSICALDRIVE%d"
0x180039c98  mov     edx, 104h; unsigned __int64
0x180039c9d  lea     rcx, [rsp+278h+FileName]; unsigned __int16 *
0x180039ca2  xor     esi, esi
0x180039ca4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039ca9  test    eax, eax
0x180039cab  js      short loc_180039D0A
0x180039cad  mov     [rsp+278h+hTemplateFile], rsi; hTemplateFile
0x180039cb2  lea     r8d, [rsi+3]; dwShareMode
0x180039cb6  mov     [rsp+278h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180039cbe  lea     rcx, [rsp+278h+FileName]; lpFileName
0x180039cc3  xor     r9d, r9d; lpSecurityAttributes
0x180039cc6  mov     [rsp+278h+dwCreationDisposition], r8d; dwCreationDisposition
0x180039ccb  mov     edx, 80000000h; dwDesiredAccess
0x180039cd0  call    cs:__imp_CreateFileW
0x180039cd6  mov     rdi, rax
0x180039cd9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039cdd  jz      short loc_180039D00
0x180039cdf  mov     rdx, rbp
0x180039ce2  mov     rcx, rax; hDevice
0x180039ce5  call    InternalGetDriveLayout
0x180039cea  mov     rsi, rax
0x180039ced  call    cs:__imp_GetLastError
0x180039cf3  mov     rcx, rdi; hObject
0x180039cf6  mov     ebx, eax
0x180039cf8  call    cs:__imp_CloseHandle
0x180039cfe  jmp     short loc_180039D0D
0x180039d00  call    cs:__imp_GetLastError
0x180039d06  mov     ebx, eax
0x180039d08  jmp     short loc_180039D0D
0x180039d0a  movzx   ebx, ax
0x180039d0d  mov     ecx, ebx; dwErrCode
0x180039d0f  call    cs:__imp_SetLastError
0x180039d15  mov     rax, rsi
0x180039d18  mov     rcx, [rsp+278h+var_28]
0x180039d20  xor     rcx, rsp; StackCookie
0x180039d23  call    __security_check_cookie
0x180039d28  mov     rbx, [rsp+278h+arg_10]
0x180039d30  add     rsp, 260h
0x180039d37  pop     rdi
0x180039d38  pop     rsi
0x180039d39  pop     rbp
0x180039d3a  retn
```
