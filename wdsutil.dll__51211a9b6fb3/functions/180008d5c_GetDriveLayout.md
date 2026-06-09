# GetDriveLayout

- ea: `0x180008d5c`
- end: `0x180008e7b`
- name: `GetDriveLayout`
- size: `287`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180006020`
- `0x180006570`
- `0x180008e84`

## callees

- `0x180008d5c`
- `0x180009214`
- `0x18000955c`
- `0x1800319ae`
- `0x1800319f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008e12`
- `KERNEL32!GetLastError` at `0x180008e31`
- `KERNEL32!GetLastError` at `0x180008e12`
- `KERNEL32!GetLastError` at `0x180008e31`
- `KERNEL32!CloseHandle` at `0x180008e23`
- `KERNEL32!CloseHandle` at `0x180008e23`
- `KERNEL32!SetLastError` at `0x180008d9d`
- `KERNEL32!SetLastError` at `0x180008e46`
- `KERNEL32!SetLastError` at `0x180008d9d`
- `KERNEL32!SetLastError` at `0x180008e46`
- `KERNEL32!CreateFileW` at `0x180008df2`
- `KERNEL32!CreateFileW` at `0x180008df2`

## pseudocode

```c
__int64 __fastcall GetDriveLayout(int a1)
{
  __int64 DriveLayout; // rsi
  int v4; // eax
  HANDLE FileW; // rax
  void *v6; // rdi
  DWORD LastError; // ebx
  WCHAR FileName[264]; // [rsp+40h] [rbp-228h] BYREF

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
0x180008d5c  mov     [rsp+arg_8], rbx
0x180008d61  mov     [rsp+arg_10], rsi
0x180008d66  push    rdi
0x180008d67  sub     rsp, 260h
0x180008d6e  mov     rax, cs:__security_cookie
0x180008d75  xor     rax, rsp
0x180008d78  mov     [rsp+268h+var_18], rax
0x180008d80  mov     ebx, ecx
0x180008d82  xor     edx, edx; Val
0x180008d84  lea     rcx, [rsp+268h+FileName]; void *
0x180008d89  mov     r8d, 208h; Size
0x180008d8f  call    memset_0
0x180008d94  test    ebx, ebx
0x180008d96  jns     short loc_180008DB0
0x180008d98  mov     ecx, 57h ; 'W'; dwErrCode
0x180008d9d  call    cs:__imp_SetLastError
0x180008da4  nop     dword ptr [rax+rax+00h]
0x180008da9  xor     eax, eax
0x180008dab  jmp     loc_180008E55
0x180008db0  mov     r9d, ebx
0x180008db3  lea     r8, aPhysicaldriveD; "\\\\.\\PHYSICALDRIVE%d"
0x180008dba  mov     edx, 104h; unsigned __int64
0x180008dbf  lea     rcx, [rsp+268h+FileName]; unsigned __int16 *
0x180008dc4  xor     esi, esi
0x180008dc6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008dcb  test    eax, eax
0x180008dcd  js      short loc_180008E41
0x180008dcf  mov     [rsp+268h+hTemplateFile], rsi; hTemplateFile
0x180008dd4  lea     r8d, [rsi+3]; dwShareMode
0x180008dd8  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180008de0  lea     rcx, [rsp+268h+FileName]; lpFileName
0x180008de5  xor     r9d, r9d; lpSecurityAttributes
0x180008de8  mov     [rsp+268h+dwCreationDisposition], r8d; dwCreationDisposition
0x180008ded  mov     edx, 80000000h; dwDesiredAccess
0x180008df2  call    cs:__imp_CreateFileW
0x180008df9  nop     dword ptr [rax+rax+00h]
0x180008dfe  mov     rdi, rax
0x180008e01  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008e05  jz      short loc_180008E31
0x180008e07  mov     rcx, rax; hDevice
0x180008e0a  call    InternalGetDriveLayout
0x180008e0f  mov     rsi, rax
0x180008e12  call    cs:__imp_GetLastError
0x180008e19  nop     dword ptr [rax+rax+00h]
0x180008e1e  mov     rcx, rdi; hObject
0x180008e21  mov     ebx, eax
0x180008e23  call    cs:__imp_CloseHandle
0x180008e2a  nop     dword ptr [rax+rax+00h]
0x180008e2f  jmp     short loc_180008E44
0x180008e31  call    cs:__imp_GetLastError
0x180008e38  nop     dword ptr [rax+rax+00h]
0x180008e3d  mov     ebx, eax
0x180008e3f  jmp     short loc_180008E44
0x180008e41  movzx   ebx, ax
0x180008e44  mov     ecx, ebx; dwErrCode
0x180008e46  call    cs:__imp_SetLastError
0x180008e4d  nop     dword ptr [rax+rax+00h]
0x180008e52  mov     rax, rsi
0x180008e55  mov     rcx, [rsp+268h+var_18]
0x180008e5d  xor     rcx, rsp; StackCookie
0x180008e60  call    __security_check_cookie
0x180008e65  lea     r11, [rsp+268h+var_8]
0x180008e6d  mov     rbx, [r11+18h]
0x180008e71  mov     rsi, [r11+20h]
0x180008e75  mov     rsp, r11
0x180008e78  pop     rdi
0x180008e79  retn
```
