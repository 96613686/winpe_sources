# CreateInfFile(HINSTANCE__ *,ushort *,int *)

- ea: `0x1800365bc`
- end: `0x180036754`
- name: `?CreateInfFile@@YAJPEAUHINSTANCE__@@PEAGPEAH@Z`
- size: `408`
- prototype: `__int64 __fastcall(HINSTANCE hModule, LPCWSTR lpFileName, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180036aa0`

## callees

- `0x1800365bc`
- `0x18003680c`
- `0x180043118`
- `0x18004d030`
- `0x18004d350`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180036701`
- `KERNEL32!WriteFile` at `0x180036701`
- `KERNEL32!CloseHandle` at `0x180036725`
- `KERNEL32!CloseHandle` at `0x180036725`
- `KERNEL32!CreateFileW` at `0x1800366d4`
- `KERNEL32!CreateFileW` at `0x1800366d4`
- `KERNEL32!GetTempFileNameW` at `0x180036661`
- `KERNEL32!GetTempFileNameW` at `0x180036661`
- `KERNEL32!GetWindowsDirectoryW` at `0x180036635`
- `KERNEL32!GetWindowsDirectoryW` at `0x180036635`
- `KERNEL32!LoadResource` at `0x18003669a`
- `KERNEL32!LoadResource` at `0x18003669a`
- `KERNEL32!LockResource` at `0x1800366a3`
- `KERNEL32!LockResource` at `0x1800366a3`
- `KERNEL32!SizeofResource` at `0x18003668c`
- `KERNEL32!SizeofResource` at `0x18003668c`
- `KERNEL32!FindResourceW` at `0x180036678`
- `KERNEL32!FindResourceW` at `0x180036678`

## pseudocode

```c
__int64 __fastcall CreateInfFile(HINSTANCE hModule, WCHAR *lpFileName, int *a3)
{
  int v6; // edi
  unsigned int LastWin32Error; // ebx
  UINT WindowsDirectoryW; // eax
  HRSRC ResourceW; // rax
  HRSRC v10; // rbx
  DWORD v11; // ebp
  HGLOBAL Resource; // rax
  const void *v13; // rbx
  HANDLE FileW; // rax
  void *v15; // rsi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-248h] BYREF

  v6 = 0;
  memset_0(Buffer, 0, 0x208u);
  *a3 = 0;
  if ( SecureGetTempPath(0x104u, Buffer) > 0x104 )
    return (unsigned int)-2147418113;
  if ( !(unsigned int)IsGoodDir(Buffer) )
  {
    WindowsDirectoryW = GetWindowsDirectoryW(Buffer, 0x104u);
    if ( !WindowsDirectoryW )
      return (unsigned int)GetLastWin32Error();
    if ( WindowsDirectoryW > 0x104 )
      return (unsigned int)-2147418113;
  }
  if ( !GetTempFileNameW(Buffer, L"RGI", 0, lpFileName) )
    return (unsigned int)GetLastWin32Error();
  ResourceW = FindResourceW(hModule, L"REGINST", L"REGINST");
  v10 = ResourceW;
  if ( !ResourceW )
    return (unsigned int)GetLastWin32Error();
  v11 = SizeofResource(hModule, ResourceW);
  Resource = LoadResource(hModule, v10);
  v13 = LockResource(Resource);
  if ( !v13 )
    return (unsigned int)GetLastWin32Error();
  FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v15 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return (unsigned int)GetLastWin32Error();
  *a3 = 1;
  if ( WriteFile(FileW, v13, v11, &NumberOfBytesWritten, 0) )
  {
    if ( NumberOfBytesWritten != v11 )
      v6 = -2147418113;
    LastWin32Error = v6;
  }
  else
  {
    LastWin32Error = GetLastWin32Error();
  }
  CloseHandle(v15);
  return LastWin32Error;
}

```

## disassembly

```asm
0x1800365bc  mov     [rsp+arg_18], rbx
0x1800365c1  push    rbp
0x1800365c2  push    rsi
0x1800365c3  push    rdi
0x1800365c4  push    r14
0x1800365c6  push    r15
0x1800365c8  sub     rsp, 270h
0x1800365cf  mov     rax, cs:__security_cookie
0x1800365d6  xor     rax, rsp
0x1800365d9  mov     [rsp+298h+var_38], rax
0x1800365e1  mov     r15, r8
0x1800365e4  mov     r14, rdx
0x1800365e7  mov     rsi, rcx
0x1800365ea  xor     edx, edx; Val
0x1800365ec  mov     r8d, 208h; Size
0x1800365f2  lea     rcx, [rsp+298h+Buffer]; void *
0x1800365f7  xor     edi, edi
0x1800365f9  call    memset_0
0x1800365fe  mov     ebx, 104h
0x180036603  mov     [r15], edi
0x180036606  mov     ecx, ebx; nBufferLength
0x180036608  lea     rdx, [rsp+298h+Buffer]; lpBuffer
0x18003660d  call    ?SecureGetTempPath@@YAKKPEAG@Z; SecureGetTempPath(ulong,ushort *)
0x180036612  cmp     eax, ebx
0x180036614  jbe     short loc_180036620
0x180036616  mov     ebx, 8000FFFFh
0x18003661b  jmp     loc_18003672B
0x180036620  lea     rcx, [rsp+298h+Buffer]; lpFileName
0x180036625  call    ?IsGoodDir@@YAHPEAG@Z; IsGoodDir(ushort *)
0x18003662a  test    eax, eax
0x18003662c  jnz     short loc_18003664F
0x18003662e  mov     edx, ebx; uSize
0x180036630  lea     rcx, [rsp+298h+Buffer]; lpBuffer
0x180036635  call    cs:__imp_GetWindowsDirectoryW
0x18003663b  test    eax, eax
0x18003663d  jnz     short loc_18003664B
0x18003663f  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180036644  mov     ebx, eax
0x180036646  jmp     loc_18003672B
0x18003664b  cmp     eax, ebx
0x18003664d  ja      short loc_180036616
0x18003664f  mov     r9, r14; lpTempFileName
0x180036652  lea     rdx, PrefixString; "RGI"
0x180036659  xor     r8d, r8d; uUnique
0x18003665c  lea     rcx, [rsp+298h+Buffer]; lpPathName
0x180036661  call    cs:__imp_GetTempFileNameW
0x180036667  test    eax, eax
0x180036669  jz      short loc_18003663F
0x18003666b  lea     rdx, Type; "REGINST"
0x180036672  mov     rcx, rsi; hModule
0x180036675  mov     r8, rdx; lpType
0x180036678  call    cs:__imp_FindResourceW
0x18003667e  mov     rbx, rax
0x180036681  test    rax, rax
0x180036684  jz      short loc_18003663F
0x180036686  mov     rdx, rax; hResInfo
0x180036689  mov     rcx, rsi; hModule
0x18003668c  call    cs:__imp_SizeofResource
0x180036692  mov     rdx, rbx; hResInfo
0x180036695  mov     rcx, rsi; hModule
0x180036698  mov     ebp, eax
0x18003669a  call    cs:__imp_LoadResource
0x1800366a0  mov     rcx, rax; hResData
0x1800366a3  call    cs:__imp_LockResource
0x1800366a9  mov     rbx, rax
0x1800366ac  test    rax, rax
0x1800366af  jz      short loc_18003663F
0x1800366b1  mov     [rsp+298h+hTemplateFile], rdi; hTemplateFile
0x1800366b6  xor     r9d, r9d; lpSecurityAttributes
0x1800366b9  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800366c1  xor     r8d, r8d; dwShareMode
0x1800366c4  mov     edx, 40000000h; dwDesiredAccess
0x1800366c9  mov     [rsp+298h+dwCreationDisposition], 2; dwCreationDisposition
0x1800366d1  mov     rcx, r14; lpFileName
0x1800366d4  call    cs:__imp_CreateFileW
0x1800366da  mov     rsi, rax
0x1800366dd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800366e1  jz      loc_18003663F
0x1800366e7  lea     r9, [rsp+298h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800366ec  mov     dword ptr [r15], 1
0x1800366f3  mov     r8d, ebp; nNumberOfBytesToWrite
0x1800366f6  mov     qword ptr [rsp+298h+dwCreationDisposition], rdi; lpOverlapped
0x1800366fb  mov     rdx, rbx; lpBuffer
0x1800366fe  mov     rcx, rax; hFile
0x180036701  call    cs:__imp_WriteFile
0x180036707  test    eax, eax
0x180036709  jnz     short loc_180036714
0x18003670b  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180036710  mov     ebx, eax
0x180036712  jmp     short loc_180036722
0x180036714  cmp     [rsp+298h+NumberOfBytesWritten], ebp
0x180036718  mov     ebx, 8000FFFFh
0x18003671d  cmovnz  edi, ebx
0x180036720  mov     ebx, edi
0x180036722  mov     rcx, rsi; hObject
0x180036725  call    cs:__imp_CloseHandle
0x18003672b  mov     eax, ebx
0x18003672d  mov     rcx, [rsp+298h+var_38]
0x180036735  xor     rcx, rsp; StackCookie
0x180036738  call    __security_check_cookie
0x18003673d  mov     rbx, [rsp+298h+arg_18]
0x180036745  add     rsp, 270h
0x18003674c  pop     r15
0x18003674e  pop     r14
0x180036750  pop     rdi
0x180036751  pop     rsi
0x180036752  pop     rbp
0x180036753  retn
```
