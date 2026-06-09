# WusaCreateLockFile(void * *)

- ea: `0x14000d44c`
- end: `0x14000d619`
- name: `?WusaCreateLockFile@@YAJPEAPEAX@Z`
- size: `461`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14000f8f0`

## callees

- `0x140001a63`
- `0x14000d44c`
- `0x14000e280`
- `0x140013490`
- `0x140014910`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000d5f6`
- `KERNEL32!LocalFree` at `0x14000d5f6`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x14000d497`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x14000d497`
- `KERNEL32!CreateFileW` at `0x14000d552`
- `KERNEL32!CreateFileW` at `0x14000d552`
- `KERNEL32!GetLastError` at `0x14000d4a1`
- `KERNEL32!GetLastError` at `0x14000d55e`
- `KERNEL32!GetLastError` at `0x14000d4a1`
- `KERNEL32!GetLastError` at `0x14000d55e`
- `msvcrt!wcsrchr` at `0x14000d4e7`
- `msvcrt!wcsrchr` at `0x14000d4e7`
- `ServicingCommon!SczFree` at `0x14000d5a9`
- `ServicingCommon!SczFree` at `0x14000d5a9`
- `ServicingCommon!SczAllocFormatted` at `0x14000d513`
- `ServicingCommon!SczAllocFormatted` at `0x14000d513`

## string_xrefs

- `0x14000d4b8`: `Failed to get windows directory.`
- `0x14000d4cc`: `WusaCreateLockFile`
- `0x14000d581`: `WusaCreateLockFile`
- `0x14000d5e2`: `WusaCreateLockFile`
- `0x14000d51f`: `Failed to allocate memory for lock file path.`
- `0x14000d578`: `Failed to create lock file %S`

## pseudocode

```c
__int64 __fastcall WusaCreateLockFile(void **a1)
{
  signed int v2; // eax
  signed int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // r8
  wchar_t *v6; // rax
  HANDLE FileW; // rax
  signed int LastError; // eax
  HLOCAL v9; // rdi
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(Buffer, 0, 0x208u);
  lpFileName = 0;
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) )
  {
    v6 = wcsrchr(Buffer, 0x5Cu);
    if ( v6 && !v6[1] )
      *v6 = 0;
    v3 = SczAllocFormatted(&lpFileName, L"%s\\%s", Buffer, L"wusa.lock");
    if ( v3 >= 0 )
    {
      FileW = CreateFileW(lpFileName, 0x10000000u, 0, 0, 2u, 0x4000102u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 >= 0 )
          v3 = -2147467259;
        WusaLogDebugEventA(L"WusaCreateLockFile", 398, "Failed to create lock file %S", lpFileName);
      }
      else
      {
        *a1 = FileW;
      }
    }
    else
    {
      WusaLogDebugEventA(L"WusaCreateLockFile", 383, "Failed to allocate memory for lock file path.");
    }
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
    WusaLogDebugEventA(L"WusaCreateLockFile", 377, "Failed to get windows directory.");
  }
  if ( lpFileName )
  {
    SczFree(lpFileName, v4, v5);
    lpFileName = 0;
  }
  if ( v3 < 0 )
  {
    hMem = 0;
    WusaGetErrorMessage(v3, (unsigned __int16 **)&hMem);
    v9 = hMem;
    WusaLogDebugEventA(L"WusaCreateLockFile", 409, "Exit with error code 0X%x (%ls)", v3, (const wchar_t *)hMem);
    if ( v9 )
      LocalFree(v9);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000d44c  push    rbp
0x14000d44e  push    rbx
0x14000d44f  push    rsi
0x14000d450  push    rdi
0x14000d451  lea     rbp, [rsp-178h]
0x14000d459  sub     rsp, 278h
0x14000d460  mov     rax, cs:__security_cookie
0x14000d467  xor     rax, rsp
0x14000d46a  mov     [rbp+190h+var_30], rax
0x14000d471  mov     rdi, rcx
0x14000d474  xor     edx, edx; Val
0x14000d476  lea     rcx, [rsp+290h+Buffer]; void *
0x14000d47b  mov     r8d, 208h; Size
0x14000d481  call    memset_0
0x14000d486  xor     esi, esi
0x14000d488  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x14000d48d  mov     edx, 104h; uSize
0x14000d492  mov     [rsp+290h+lpFileName], rsi
0x14000d497  call    cs:__imp_GetSystemWindowsDirectoryW
0x14000d49d  test    eax, eax
0x14000d49f  jnz     short loc_14000D4DD
0x14000d4a1  call    cs:__imp_GetLastError
0x14000d4a7  mov     ebx, eax
0x14000d4a9  test    eax, eax
0x14000d4ab  jle     short loc_14000D4B6
0x14000d4ad  movzx   ebx, ax
0x14000d4b0  or      ebx, 80070000h
0x14000d4b6  test    ebx, ebx
0x14000d4b8  lea     r8, aFailedToGetWin; "Failed to get windows directory."
0x14000d4bf  mov     eax, 80004005h
0x14000d4c4  mov     edx, 179h
0x14000d4c9  cmovns  ebx, eax
0x14000d4cc  lea     rcx, aWusacreatelock; "WusaCreateLockFile"
0x14000d4d3  call    WusaLogDebugEventA
0x14000d4d8  jmp     loc_14000D59F
0x14000d4dd  mov     edx, 5Ch ; '\'; Ch
0x14000d4e2  lea     rcx, [rsp+290h+Buffer]; Str
0x14000d4e7  call    cs:__imp_wcsrchr
0x14000d4ed  test    rax, rax
0x14000d4f0  jz      short loc_14000D4FB
0x14000d4f2  cmp     [rax+2], si
0x14000d4f6  jnz     short loc_14000D4FB
0x14000d4f8  mov     [rax], si
0x14000d4fb  lea     r9, aWusaLock; "wusa.lock"
0x14000d502  lea     r8, [rsp+290h+Buffer]
0x14000d507  lea     rdx, aSS; "%s\\%s"
0x14000d50e  lea     rcx, [rsp+290h+lpFileName]
0x14000d513  call    cs:__imp_SczAllocFormatted
0x14000d519  mov     ebx, eax
0x14000d51b  test    eax, eax
0x14000d51d  jns     short loc_14000D52D
0x14000d51f  lea     r8, aFailedToAlloca_24; "Failed to allocate memory for lock file"...
0x14000d526  mov     edx, 17Fh
0x14000d52b  jmp     short loc_14000D4CC
0x14000d52d  mov     rcx, [rsp+290h+lpFileName]; lpFileName
0x14000d532  xor     r9d, r9d; lpSecurityAttributes
0x14000d535  mov     [rsp+290h+hTemplateFile], rsi; hTemplateFile
0x14000d53a  xor     r8d, r8d; dwShareMode
0x14000d53d  mov     [rsp+290h+dwFlagsAndAttributes], 4000102h; dwFlagsAndAttributes
0x14000d545  mov     edx, 10000000h; dwDesiredAccess
0x14000d54a  mov     [rsp+290h+dwCreationDisposition], 2; dwCreationDisposition
0x14000d552  call    cs:__imp_CreateFileW
0x14000d558  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000d55c  jnz     short loc_14000D59C
0x14000d55e  call    cs:__imp_GetLastError
0x14000d564  mov     ebx, eax
0x14000d566  test    eax, eax
0x14000d568  jle     short loc_14000D573
0x14000d56a  movzx   ebx, ax
0x14000d56d  or      ebx, 80070000h
0x14000d573  mov     r9, [rsp+290h+lpFileName]
0x14000d578  lea     r8, aFailedToCreate_11; "Failed to create lock file %S"
0x14000d57f  test    ebx, ebx
0x14000d581  lea     rcx, aWusacreatelock; "WusaCreateLockFile"
0x14000d588  mov     eax, 80004005h
0x14000d58d  mov     edx, 18Eh
0x14000d592  cmovns  ebx, eax
0x14000d595  call    WusaLogDebugEventA
0x14000d59a  jmp     short loc_14000D59F
0x14000d59c  mov     [rdi], rax
0x14000d59f  mov     rcx, [rsp+290h+lpFileName]
0x14000d5a4  test    rcx, rcx
0x14000d5a7  jz      short loc_14000D5B4
0x14000d5a9  call    cs:__imp_SczFree
0x14000d5af  mov     [rsp+290h+lpFileName], rsi
0x14000d5b4  test    ebx, ebx
0x14000d5b6  jns     short loc_14000D5FC
0x14000d5b8  lea     rdx, [rsp+290h+hMem]; unsigned __int16 **
0x14000d5bd  mov     [rsp+290h+hMem], rsi
0x14000d5c2  mov     ecx, ebx; dwMessageId
0x14000d5c4  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14000d5c9  mov     rdi, [rsp+290h+hMem]
0x14000d5ce  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x14000d5d5  mov     r9d, ebx
0x14000d5d8  mov     qword ptr [rsp+290h+dwCreationDisposition], rdi
0x14000d5dd  mov     edx, 199h
0x14000d5e2  lea     rcx, aWusacreatelock; "WusaCreateLockFile"
0x14000d5e9  call    WusaLogDebugEventA
0x14000d5ee  test    rdi, rdi
0x14000d5f1  jz      short loc_14000D5FC
0x14000d5f3  mov     rcx, rdi; hMem
0x14000d5f6  call    cs:__imp_LocalFree
0x14000d5fc  mov     eax, ebx
0x14000d5fe  mov     rcx, [rbp+190h+var_30]
0x14000d605  xor     rcx, rsp; StackCookie
0x14000d608  call    __security_check_cookie
0x14000d60d  add     rsp, 278h
0x14000d614  pop     rdi
0x14000d615  pop     rsi
0x14000d616  pop     rbx
0x14000d617  pop     rbp
0x14000d618  retn
```
