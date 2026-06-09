# MsiLoad(void)

- ea: `0x1400087e4`
- end: `0x140008a1c`
- name: `?MsiLoad@@YAJXZ`
- size: `568`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000b84c`

## callees

- `0x140001a63`
- `0x1400087e4`
- `0x140013490`
- `0x140014910`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000893a`
- `KERNEL32!GetProcAddress` at `0x140008979`
- `KERNEL32!GetProcAddress` at `0x14000893a`
- `KERNEL32!GetProcAddress` at `0x140008979`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x140008836`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x140008836`
- `KERNEL32!LoadLibraryW` at `0x1400088f2`
- `KERNEL32!LoadLibraryW` at `0x1400088f2`
- `KERNEL32!FreeLibrary` at `0x1400089e0`
- `KERNEL32!FreeLibrary` at `0x1400089e0`
- `KERNEL32!GetLastError` at `0x140008840`
- `KERNEL32!GetLastError` at `0x140008900`
- `KERNEL32!GetLastError` at `0x14000894c`
- `KERNEL32!GetLastError` at `0x14000898b`
- `KERNEL32!GetLastError` at `0x140008840`
- `KERNEL32!GetLastError` at `0x140008900`
- `KERNEL32!GetLastError` at `0x14000894c`
- `KERNEL32!GetLastError` at `0x14000898b`
- `ServicingCommon!SczEnsureBackslashTerminated` at `0x1400088a3`
- `ServicingCommon!SczEnsureBackslashTerminated` at `0x1400088a3`
- `ServicingCommon!SczAllocConcat2Sz` at `0x1400088d0`
- `ServicingCommon!SczAllocConcat2Sz` at `0x1400088d0`
- `ServicingCommon!SczFree` at `0x1400089f0`
- `ServicingCommon!SczFree` at `0x1400089f0`
- `ServicingCommon!SczAllocFromSz` at `0x140008870`
- `ServicingCommon!SczAllocFromSz` at `0x140008870`

## string_xrefs

- `0x1400088bd`: `msi.dll`
- `0x140008855`: `Failed to get windows directory.`
- `0x14000888d`: `MsiLoad`
- `0x1400089b6`: `MsiLoad`
- `0x14000887c`: `Failed to allocate msi path from windows directory: %S`
- `0x1400088af`: `Failed to ensure msi path ended with a backslash: %S`
- `0x1400088c4`: `system32\`
- `0x1400088dc`: `Failed to allocate full path to msi DLL.`
- `0x140008917`: `Failed to load msi DLL: %S`
- `0x140008930`: `MsiSetInternalUI`
- `0x140008961`: `Failed to get proc address for MsiSetInternalUI.`
- `0x14000896f`: `MsiConfigureProductW`
- `0x1400089a0`: `Failed to get proc address for MsiConfigureProductW.`

## pseudocode

```c
__int64 MsiLoad(void)
{
  HMODULE v0; // rdi
  signed int LastError; // eax
  signed int v2; // ebx
  const char *v3; // r8
  __int64 v4; // rdx
  const char *v5; // r8
  __int64 v6; // rdx
  HMODULE LibraryW; // rax
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  LPCWSTR lpLibFileName[2]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF

  lpLibFileName[0] = 0;
  v0 = 0;
  memset_0(Buffer, 0, 0x208u);
  if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    v3 = "Failed to get windows directory.";
    v4 = 1802;
LABEL_27:
    if ( v2 >= 0 )
      v2 = -2147467259;
    WusaLogDebugEventA(L"MsiLoad", v4, v3);
    goto LABEL_30;
  }
  v2 = SczAllocFromSz(lpLibFileName, Buffer);
  if ( v2 >= 0 )
  {
    v2 = SczEnsureBackslashTerminated(lpLibFileName);
    if ( v2 < 0 )
    {
      WusaLogDebugEventA(L"MsiLoad", 1809, "Failed to ensure msi path ended with a backslash: %S", lpLibFileName[0]);
      goto LABEL_30;
    }
    v2 = SczAllocConcat2Sz(lpLibFileName, L"system32\\", L"msi.dll");
    if ( v2 < 0 )
    {
      WusaLogDebugEventA(L"MsiLoad", 1812, "Failed to allocate full path to msi DLL.");
      goto LABEL_30;
    }
    LibraryW = LoadLibraryW(lpLibFileName[0]);
    v0 = LibraryW;
    if ( LibraryW )
    {
      qword_140020C30 = (__int64)GetProcAddress(LibraryW, "MsiSetInternalUI");
      if ( qword_140020C30 )
      {
        qword_140020C38 = (__int64)GetProcAddress(v0, "MsiConfigureProductW");
        if ( qword_140020C38 )
          goto LABEL_32;
        v10 = GetLastError();
        v2 = v10;
        if ( v10 > 0 )
          v2 = (unsigned __int16)v10 | 0x80070000;
        v3 = "Failed to get proc address for MsiConfigureProductW.";
        v4 = 1821;
      }
      else
      {
        v9 = GetLastError();
        v2 = v9;
        if ( v9 > 0 )
          v2 = (unsigned __int16)v9 | 0x80070000;
        v3 = "Failed to get proc address for MsiSetInternalUI.";
        v4 = 1818;
      }
      goto LABEL_27;
    }
    v8 = GetLastError();
    v2 = v8;
    if ( v8 > 0 )
      v2 = (unsigned __int16)v8 | 0x80070000;
    v5 = "Failed to load msi DLL: %S";
    v6 = 1815;
    if ( v2 >= 0 )
      v2 = -2147467259;
  }
  else
  {
    v5 = "Failed to allocate msi path from windows directory: %S";
    v6 = 1806;
  }
  WusaLogDebugEventA(L"MsiLoad", v6, v5, lpLibFileName[0], lpLibFileName[0]);
LABEL_30:
  qword_140020C30 = 0;
  qword_140020C38 = 0;
  if ( v0 )
    FreeLibrary(v0);
LABEL_32:
  if ( lpLibFileName[0] )
    SczFree();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400087e4  mov     [rsp-8+arg_0], rbx
0x1400087e9  mov     [rsp-8+arg_8], rdi
0x1400087ee  push    rbp
0x1400087ef  lea     rbp, [rsp-150h]
0x1400087f7  sub     rsp, 250h
0x1400087fe  mov     rax, cs:__security_cookie
0x140008805  xor     rax, rsp
0x140008808  mov     [rbp+150h+var_10], rax
0x14000880f  xor     edx, edx; Val
0x140008811  mov     [rsp+250h+lpLibFileName], 0
0x14000881a  mov     r8d, 208h; Size
0x140008820  lea     rcx, [rsp+250h+Buffer]; void *
0x140008825  xor     edi, edi
0x140008827  call    memset_0
0x14000882c  mov     edx, 104h; uSize
0x140008831  lea     rcx, [rsp+250h+Buffer]; lpBuffer
0x140008836  call    cs:__imp_GetSystemWindowsDirectoryW
0x14000883c  test    eax, eax
0x14000883e  jnz     short loc_140008866
0x140008840  call    cs:__imp_GetLastError
0x140008846  mov     ebx, eax
0x140008848  test    eax, eax
0x14000884a  jle     short loc_140008855
0x14000884c  movzx   ebx, ax
0x14000884f  or      ebx, 80070000h
0x140008855  lea     r8, aFailedToGetWin; "Failed to get windows directory."
0x14000885c  mov     edx, 70Ah
0x140008861  jmp     loc_1400089AC
0x140008866  lea     rdx, [rsp+250h+Buffer]
0x14000886b  lea     rcx, [rsp+250h+lpLibFileName]
0x140008870  call    cs:__imp_SczAllocFromSz
0x140008876  mov     ebx, eax
0x140008878  test    eax, eax
0x14000887a  jns     short loc_14000889E
0x14000887c  lea     r8, aFailedToAlloca_8; "Failed to allocate msi path from window"...
0x140008883  mov     edx, 70Eh
0x140008888  mov     r9, [rsp+250h+lpLibFileName]
0x14000888d  lea     rcx, aMsiload; "MsiLoad"
0x140008894  call    WusaLogDebugEventA
0x140008899  jmp     loc_1400089C2
0x14000889e  lea     rcx, [rsp+250h+lpLibFileName]
0x1400088a3  call    cs:__imp_SczEnsureBackslashTerminated
0x1400088a9  mov     ebx, eax
0x1400088ab  test    eax, eax
0x1400088ad  jns     short loc_1400088BD
0x1400088af  lea     r8, aFailedToEnsure; "Failed to ensure msi path ended with a "...
0x1400088b6  mov     edx, 711h
0x1400088bb  jmp     short loc_140008888
0x1400088bd  lea     r8, aMsiDll; "msi.dll"
0x1400088c4  lea     rdx, aSystem32; "system32\\"
0x1400088cb  lea     rcx, [rsp+250h+lpLibFileName]
0x1400088d0  call    cs:__imp_SczAllocConcat2Sz
0x1400088d6  mov     ebx, eax
0x1400088d8  test    eax, eax
0x1400088da  jns     short loc_1400088ED
0x1400088dc  lea     r8, aFailedToAlloca_19; "Failed to allocate full path to msi DLL"...
0x1400088e3  mov     edx, 714h
0x1400088e8  jmp     loc_1400089B6
0x1400088ed  mov     rcx, [rsp+250h+lpLibFileName]; lpLibFileName
0x1400088f2  call    cs:__imp_LoadLibraryW
0x1400088f8  mov     rdi, rax
0x1400088fb  test    rax, rax
0x1400088fe  jnz     short loc_140008930
0x140008900  call    cs:__imp_GetLastError
0x140008906  mov     ebx, eax
0x140008908  test    eax, eax
0x14000890a  jle     short loc_140008915
0x14000890c  movzx   ebx, ax
0x14000890f  or      ebx, 80070000h
0x140008915  test    ebx, ebx
0x140008917  lea     r8, aFailedToLoadMs; "Failed to load msi DLL: %S"
0x14000891e  mov     eax, 80004005h
0x140008923  mov     edx, 717h
0x140008928  cmovns  ebx, eax
0x14000892b  jmp     loc_140008888
0x140008930  lea     rdx, aMsisetinternal; "MsiSetInternalUI"
0x140008937  mov     rcx, rdi; hModule
0x14000893a  call    cs:__imp_GetProcAddress
0x140008940  mov     cs:qword_140020C30, rax
0x140008947  test    rax, rax
0x14000894a  jnz     short loc_14000896F
0x14000894c  call    cs:__imp_GetLastError
0x140008952  mov     ebx, eax
0x140008954  test    eax, eax
0x140008956  jle     short loc_140008961
0x140008958  movzx   ebx, ax
0x14000895b  or      ebx, 80070000h
0x140008961  lea     r8, aFailedToGetPro; "Failed to get proc address for MsiSetIn"...
0x140008968  mov     edx, 71Ah
0x14000896d  jmp     short loc_1400089AC
0x14000896f  lea     rdx, aMsiconfigurepr; "MsiConfigureProductW"
0x140008976  mov     rcx, rdi; hModule
0x140008979  call    cs:__imp_GetProcAddress
0x14000897f  mov     cs:qword_140020C38, rax
0x140008986  test    rax, rax
0x140008989  jnz     short loc_1400089E6
0x14000898b  call    cs:__imp_GetLastError
0x140008991  mov     ebx, eax
0x140008993  test    eax, eax
0x140008995  jle     short loc_1400089A0
0x140008997  movzx   ebx, ax
0x14000899a  or      ebx, 80070000h
0x1400089a0  lea     r8, aFailedToGetPro_0; "Failed to get proc address for MsiConfi"...
0x1400089a7  mov     edx, 71Dh
0x1400089ac  test    ebx, ebx
0x1400089ae  mov     eax, 80004005h
0x1400089b3  cmovns  ebx, eax
0x1400089b6  lea     rcx, aMsiload; "MsiLoad"
0x1400089bd  call    WusaLogDebugEventA
0x1400089c2  mov     cs:qword_140020C30, 0
0x1400089cd  mov     cs:qword_140020C38, 0
0x1400089d8  test    rdi, rdi
0x1400089db  jz      short loc_1400089E6
0x1400089dd  mov     rcx, rdi; hLibModule
0x1400089e0  call    cs:__imp_FreeLibrary
0x1400089e6  mov     rcx, [rsp+250h+lpLibFileName]
0x1400089eb  test    rcx, rcx
0x1400089ee  jz      short loc_1400089F6
0x1400089f0  call    cs:__imp_SczFree
0x1400089f6  mov     eax, ebx
0x1400089f8  mov     rcx, [rbp+150h+var_10]
0x1400089ff  xor     rcx, rsp; StackCookie
0x140008a02  call    __security_check_cookie
0x140008a07  lea     r11, [rsp+250h+var_s0]
0x140008a0f  mov     rbx, [r11+10h]
0x140008a13  mov     rdi, [r11+18h]
0x140008a17  mov     rsp, r11
0x140008a1a  pop     rbp
0x140008a1b  retn
```
