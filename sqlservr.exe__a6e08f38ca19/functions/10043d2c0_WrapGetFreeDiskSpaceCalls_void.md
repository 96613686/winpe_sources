# WrapGetFreeDiskSpaceCalls(void)

- ea: `0x10043d2c0`
- end: `0x10043d5ea`
- name: `?WrapGetFreeDiskSpaceCalls@@YAJXZ`
- size: `810`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100425030`

## callees

- `0x100401580`
- `0x10043d2c0`
- `0x10043ddb0`
- `0x10043dfb0`
- `0x10043e2c0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x10043d493`
- `KERNEL32!GetProcAddress` at `0x10043d4b7`
- `KERNEL32!GetProcAddress` at `0x10043d4db`
- `KERNEL32!GetProcAddress` at `0x10043d4ff`
- `KERNEL32!GetProcAddress` at `0x10043d493`
- `KERNEL32!GetProcAddress` at `0x10043d4b7`
- `KERNEL32!GetProcAddress` at `0x10043d4db`
- `KERNEL32!GetProcAddress` at `0x10043d4ff`
- `KERNEL32!GetModuleFileNameW` at `0x10043d2f1`
- `KERNEL32!GetModuleFileNameW` at `0x10043d2f1`
- `KERNEL32!GetModuleHandleW` at `0x10043d483`
- `KERNEL32!GetModuleHandleW` at `0x10043d4a7`
- `KERNEL32!GetModuleHandleW` at `0x10043d4cb`
- `KERNEL32!GetModuleHandleW` at `0x10043d4ef`
- `KERNEL32!GetModuleHandleW` at `0x10043d483`
- `KERNEL32!GetModuleHandleW` at `0x10043d4a7`
- `KERNEL32!GetModuleHandleW` at `0x10043d4cb`
- `KERNEL32!GetModuleHandleW` at `0x10043d4ef`
- `KERNEL32!GetModuleFileNameA` at `0x10043d3c8`
- `KERNEL32!GetModuleFileNameA` at `0x10043d3c8`
- `KERNEL32!GetLastError` at `0x10043d2fd`
- `KERNEL32!GetLastError` at `0x10043d3d2`
- `KERNEL32!GetLastError` at `0x10043d2fd`
- `KERNEL32!GetLastError` at `0x10043d3d2`
- `VCRUNTIME140!strrchr` at `0x10043d3f7`
- `VCRUNTIME140!strrchr` at `0x10043d3f7`
- `VCRUNTIME140!wcsrchr` at `0x10043d325`
- `VCRUNTIME140!wcsrchr` at `0x10043d325`

## string_xrefs

- `0x10043d47c`: `kernel32.dll`
- `0x10043d499`: `kernel32.dll`
- `0x10043d4bd`: `kernel32.dll`
- `0x10043d4e1`: `kernel32.dll`

## pseudocode

```c
int WrapGetFreeDiskSpaceCalls(void)
{
  __int64 v0; // rbx
  int result; // eax
  bool v2; // zf
  wchar_t *v3; // rax
  unsigned __int64 v4; // rax
  wchar_t near **v5; // rcx
  __int64 v6; // rdx
  unsigned __int64 v7; // r9
  __int16 v8; // ax
  wchar_t near **v9; // rax
  bool v10; // zf
  char *v11; // rax
  unsigned __int64 v12; // rax
  char near **v13; // rcx
  unsigned __int64 v14; // r8
  char v15; // al
  char near **v16; // rax
  HMODULE ModuleHandleW; // rax
  HMODULE v18; // rax
  HMODULE v19; // rax
  HMODULE v20; // rax
  int (*ProcAddress)(const wchar_t *, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *); // rax
  CHAR Str[272]; // [rsp+30h] [rbp-338h] BYREF
  WCHAR Filename[264]; // [rsp+140h] [rbp-228h] BYREF

  v0 = 260;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v3 = wcsrchr(Filename, 0x5Cu);
    if ( v3 < Filename )
      return 1;
    v4 = v3 - Filename + 1;
    if ( v4 <= 0x7FFFFFFE )
    {
      v5 = &gProcessWorkingDirW;
      v6 = 260;
      v7 = v4 - 260;
      do
      {
        if ( !(v7 + v6) )
          break;
        v8 = *(_WORD *)((char *)v5 + (char *)Filename - (char *)&gProcessWorkingDirW);
        if ( !v8 )
          break;
        *(_WORD *)v5 = v8;
        v5 = (wchar_t near **)((char *)v5 + 2);
        --v6;
      }
      while ( v6 );
      v9 = (wchar_t near **)((char *)v5 - 2);
      if ( v6 )
        v9 = v5;
      *(_WORD *)v9 = 0;
      result = -2147024774;
      if ( v6 )
        result = 0;
    }
    else
    {
      result = -2147024809;
      LOWORD(gProcessWorkingDirW) = 0;
    }
  }
  else
  {
    result = GetLastError();
    v2 = result == 0;
    if ( result <= 0 )
      goto LABEL_16;
    result = (unsigned __int16)result | 0x80070000;
  }
  v2 = result == 0;
LABEL_16:
  if ( !v2 )
    return result;
  if ( GetModuleFileNameA(0, Str, 0x104u) )
  {
    v11 = strrchr(Str, 92);
    if ( v11 >= Str )
    {
      v12 = v11 - Str + 1;
      if ( v12 <= 0x7FFFFFFE )
      {
        v13 = &gProcessWorkingDirA;
        v14 = v12 - 260;
        do
        {
          if ( !(v14 + v0) )
            break;
          v15 = *((_BYTE *)v13 + Str - (CHAR *)&gProcessWorkingDirA);
          if ( !v15 )
            break;
          *(_BYTE *)v13 = v15;
          v13 = (char near **)((char *)v13 + 1);
          --v0;
        }
        while ( v0 );
        v16 = (char near **)((char *)v13 - 1);
        if ( v0 )
          v16 = v13;
        *(_BYTE *)v16 = 0;
        result = -2147024774;
        if ( v0 )
          result = 0;
      }
      else
      {
        result = -2147024809;
        LOBYTE(gProcessWorkingDirA) = 0;
      }
      goto LABEL_31;
    }
    return 1;
  }
  result = GetLastError();
  v10 = result == 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
LABEL_31:
    v10 = result == 0;
  }
  if ( v10 )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    gGetDiskFreeSpaceA = (int (*)(const char *, unsigned int *, unsigned int *, unsigned int *, unsigned int *))GetProcAddress(ModuleHandleW, "GetDiskFreeSpaceA");
    v18 = GetModuleHandleW(L"kernel32.dll");
    gGetDiskFreeSpaceExA = (int (*)(const char *, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *))GetProcAddress(v18, "GetDiskFreeSpaceExA");
    v19 = GetModuleHandleW(L"kernel32.dll");
    gGetDiskFreeSpaceW = (int (*)(const wchar_t *, unsigned int *, unsigned int *, unsigned int *, unsigned int *))GetProcAddress(v19, "GetDiskFreeSpaceW");
    v20 = GetModuleHandleW(L"kernel32.dll");
    ProcAddress = (int (*)(const wchar_t *, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *))GetProcAddress(v20, "GetDiskFreeSpaceExW");
    gGetDiskFreeSpaceExW = ProcAddress;
    if ( !gGetDiskFreeSpaceA )
      return 1;
    if ( !gGetDiskFreeSpaceExA )
      return 1;
    if ( !gGetDiskFreeSpaceW )
      return 1;
    if ( !ProcAddress )
      return 1;
    DetourTransactionBegin();
    DetourAttachEx((__int64 *)&gGetDiskFreeSpaceA, (__int64)WrapGetDiskFreeSpaceA, 0, 0, 0);
    DetourAttachEx((__int64 *)&gGetDiskFreeSpaceExA, (__int64)WrapGetDiskFreeSpaceExA, 0, 0, 0);
    DetourAttachEx((__int64 *)&gGetDiskFreeSpaceW, (__int64)WrapGetDiskFreeSpaceW, 0, 0, 0);
    DetourAttachEx((__int64 *)&gGetDiskFreeSpaceExW, (__int64)WrapGetDiskFreeSpaceExW, 0, 0, 0);
    result = DetourTransactionCommitEx(0);
    if ( result )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x10043d2c0  mov     [rsp+arg_0], rbx
0x10043d2c5  push    rdi
0x10043d2c6  sub     rsp, 360h
0x10043d2cd  mov     rax, cs:__security_cookie
0x10043d2d4  xor     rax, rsp
0x10043d2d7  mov     [rsp+368h+var_18], rax
0x10043d2df  mov     ebx, 104h
0x10043d2e4  lea     rdx, [rsp+368h+Filename]; lpFilename
0x10043d2ec  mov     r8d, ebx; nSize
0x10043d2ef  xor     ecx, ecx; hModule
0x10043d2f1  call    cs:__imp_GetModuleFileNameW
0x10043d2f7  xor     edi, edi
0x10043d2f9  test    eax, eax
0x10043d2fb  jnz     short loc_10043D318
0x10043d2fd  call    cs:__imp_GetLastError
0x10043d303  test    eax, eax
0x10043d305  jle     loc_10043D3B8
0x10043d30b  movzx   eax, ax
0x10043d30e  or      eax, 80070000h
0x10043d313  jmp     loc_10043D3B6
0x10043d318  mov     edx, 5Ch ; '\'; Ch
0x10043d31d  lea     rcx, [rsp+368h+Filename]; Str
0x10043d325  call    cs:__imp_wcsrchr
0x10043d32b  lea     rcx, [rsp+368h+Filename]
0x10043d333  cmp     rax, rcx
0x10043d336  jb      loc_10043D5C4
0x10043d33c  lea     rcx, [rsp+368h+Filename]
0x10043d344  sub     rax, rcx
0x10043d347  sar     rax, 1
0x10043d34a  inc     rax
0x10043d34d  cmp     rax, 7FFFFFFEh
0x10043d353  jbe     short loc_10043D363
0x10043d355  mov     eax, 80070057h
0x10043d35a  mov     cs:?gProcessWorkingDirW@@3PA_WA, di; wchar_t near * gProcessWorkingDirW
0x10043d361  jmp     short loc_10043D3B6
0x10043d363  lea     rcx, ?gProcessWorkingDirW@@3PA_WA; wchar_t near * gProcessWorkingDirW
0x10043d36a  mov     rdx, rbx
0x10043d36d  lea     r8, [rsp+368h+Filename]
0x10043d375  sub     r8, rcx
0x10043d378  lea     r9, [rax-104h]
0x10043d37f  nop
0x10043d380  lea     rax, [r9+rdx]
0x10043d384  test    rax, rax
0x10043d387  jz      short loc_10043D3A0
0x10043d389  movzx   eax, word ptr [r8+rcx]
0x10043d38e  test    ax, ax
0x10043d391  jz      short loc_10043D3A0
0x10043d393  mov     [rcx], ax
0x10043d396  add     rcx, 2
0x10043d39a  sub     rdx, 1
0x10043d39e  jnz     short loc_10043D380
0x10043d3a0  test    rdx, rdx
0x10043d3a3  lea     rax, [rcx-2]
0x10043d3a7  cmovnz  rax, rcx
0x10043d3ab  mov     [rax], di
0x10043d3ae  mov     eax, 8007007Ah
0x10043d3b3  cmovnz  eax, edi
0x10043d3b6  test    eax, eax
0x10043d3b8  jnz     loc_10043D5C9
0x10043d3be  mov     r8d, ebx; nSize
0x10043d3c1  lea     rdx, [rsp+368h+Str]; lpFilename
0x10043d3c6  xor     ecx, ecx; hModule
0x10043d3c8  call    cs:__imp_GetModuleFileNameA
0x10043d3ce  test    eax, eax
0x10043d3d0  jnz     short loc_10043D3ED
0x10043d3d2  call    cs:__imp_GetLastError
0x10043d3d8  test    eax, eax
0x10043d3da  jle     loc_10043D476
0x10043d3e0  movzx   eax, ax
0x10043d3e3  or      eax, 80070000h
0x10043d3e8  jmp     loc_10043D474
0x10043d3ed  mov     edx, 5Ch ; '\'; Ch
0x10043d3f2  lea     rcx, [rsp+368h+Str]; Str
0x10043d3f7  call    cs:__imp_strrchr
0x10043d3fd  lea     rcx, [rsp+368h+Str]
0x10043d402  cmp     rax, rcx
0x10043d405  jb      loc_10043D5C4
0x10043d40b  lea     rcx, [rsp+368h+Str]
0x10043d410  sub     rax, rcx
0x10043d413  inc     rax
0x10043d416  cmp     rax, 7FFFFFFEh
0x10043d41c  jbe     short loc_10043D42C
0x10043d41e  mov     eax, 80070057h
0x10043d423  mov     cs:?gProcessWorkingDirA@@3PADA, dil; char near * gProcessWorkingDirA
0x10043d42a  jmp     short loc_10043D474
0x10043d42c  lea     rcx, ?gProcessWorkingDirA@@3PADA; char near * gProcessWorkingDirA
0x10043d433  lea     rdx, [rsp+368h+Str]
0x10043d438  sub     rdx, rcx
0x10043d43b  lea     r8, [rax-104h]
0x10043d442  lea     rax, [r8+rbx]
0x10043d446  test    rax, rax
0x10043d449  jz      short loc_10043D45E
0x10043d44b  movzx   eax, byte ptr [rdx+rcx]
0x10043d44f  test    al, al
0x10043d451  jz      short loc_10043D45E
0x10043d453  mov     [rcx], al
0x10043d455  inc     rcx
0x10043d458  sub     rbx, 1
0x10043d45c  jnz     short loc_10043D442
0x10043d45e  test    rbx, rbx
0x10043d461  lea     rax, [rcx-1]
0x10043d465  cmovnz  rax, rcx
0x10043d469  mov     [rax], dil
0x10043d46c  mov     eax, 8007007Ah
0x10043d471  cmovnz  eax, edi
0x10043d474  test    eax, eax
0x10043d476  jnz     loc_10043D5C9
0x10043d47c  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x10043d483  call    cs:__imp_GetModuleHandleW
0x10043d489  mov     rcx, rax; hModule
0x10043d48c  lea     rdx, aGetdiskfreespa_1; "GetDiskFreeSpaceA"
0x10043d493  call    cs:__imp_GetProcAddress
0x10043d499  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x10043d4a0  mov     cs:?gGetDiskFreeSpaceA@@3P6AHPEBDPEAK111@ZEA, rax; int (*gGetDiskFreeSpaceA)(char const *,ulong *,ulong *,ulong *,ulong *)
0x10043d4a7  call    cs:__imp_GetModuleHandleW
0x10043d4ad  mov     rcx, rax; hModule
0x10043d4b0  lea     rdx, aGetdiskfreespa_2; "GetDiskFreeSpaceExA"
0x10043d4b7  call    cs:__imp_GetProcAddress
0x10043d4bd  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x10043d4c4  mov     cs:?gGetDiskFreeSpaceExA@@3P6AHPEBDPEAT_ULARGE_INTEGER@@11@ZEA, rax; int (*gGetDiskFreeSpaceExA)(char const *,_ULARGE_INTEGER *,_ULARGE_INTEGER *,_ULARGE_INTEGER *)
0x10043d4cb  call    cs:__imp_GetModuleHandleW
0x10043d4d1  mov     rcx, rax; hModule
0x10043d4d4  lea     rdx, aGetdiskfreespa; "GetDiskFreeSpaceW"
0x10043d4db  call    cs:__imp_GetProcAddress
0x10043d4e1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x10043d4e8  mov     cs:?gGetDiskFreeSpaceW@@3P6AHPEB_WPEAK111@ZEA, rax; int (*gGetDiskFreeSpaceW)(wchar_t const *,ulong *,ulong *,ulong *,ulong *)
0x10043d4ef  call    cs:__imp_GetModuleHandleW
0x10043d4f5  mov     rcx, rax; hModule
0x10043d4f8  lea     rdx, aGetdiskfreespa_0; "GetDiskFreeSpaceExW"
0x10043d4ff  call    cs:__imp_GetProcAddress
0x10043d505  cmp     cs:?gGetDiskFreeSpaceA@@3P6AHPEBDPEAK111@ZEA, rdi; int (*gGetDiskFreeSpaceA)(char const *,ulong *,ulong *,ulong *,ulong *)
0x10043d50c  mov     cs:?gGetDiskFreeSpaceExW@@3P6AHPEB_WPEAT_ULARGE_INTEGER@@11@ZEA, rax; int (*gGetDiskFreeSpaceExW)(wchar_t const *,_ULARGE_INTEGER *,_ULARGE_INTEGER *,_ULARGE_INTEGER *)
0x10043d513  jz      loc_10043D5C4
0x10043d519  cmp     cs:?gGetDiskFreeSpaceExA@@3P6AHPEBDPEAT_ULARGE_INTEGER@@11@ZEA, rdi; int (*gGetDiskFreeSpaceExA)(char const *,_ULARGE_INTEGER *,_ULARGE_INTEGER *,_ULARGE_INTEGER *)
0x10043d520  jz      loc_10043D5C4
0x10043d526  cmp     cs:?gGetDiskFreeSpaceW@@3P6AHPEB_WPEAK111@ZEA, rdi; int (*gGetDiskFreeSpaceW)(wchar_t const *,ulong *,ulong *,ulong *,ulong *)
0x10043d52d  jz      loc_10043D5C4
0x10043d533  test    rax, rax
0x10043d536  jz      loc_10043D5C4
0x10043d53c  call    DetourTransactionBegin
0x10043d541  xor     r9d, r9d
0x10043d544  mov     [rsp+368h+var_348], rdi
0x10043d549  xor     r8d, r8d
0x10043d54c  lea     rdx, ?WrapGetDiskFreeSpaceA@@YAHPEBDPEAK111@Z; WrapGetDiskFreeSpaceA(char const *,ulong *,ulong *,ulong *,ulong *)
0x10043d553  lea     rcx, ?gGetDiskFreeSpaceA@@3P6AHPEBDPEAK111@ZEA; int (*gGetDiskFreeSpaceA)(char const *,ulong *,ulong *,ulong *,ulong *)
0x10043d55a  call    DetourAttachEx
0x10043d55f  xor     r9d, r9d
0x10043d562  mov     [rsp+368h+var_348], rdi
0x10043d567  xor     r8d, r8d
0x10043d56a  lea     rdx, ?WrapGetDiskFreeSpaceExA@@YAHPEBDPEAT_ULARGE_INTEGER@@11@Z; WrapGetDiskFreeSpaceExA(char const *,_ULARGE_INTEGER *,_ULARGE_INTEGER *,_ULARGE_INTEGER *)
0x10043d571  lea     rcx, ?gGetDiskFreeSpaceExA@@3P6AHPEBDPEAT_ULARGE_INTEGER@@11@ZEA; int (*gGetDiskFreeSpaceExA)(char const *,_ULARGE_INTEGER *,_ULARGE_INTEGER *,_ULARGE_INTEGER *)
0x10043d578  call    DetourAttachEx
0x10043d57d  xor     r9d, r9d
0x10043d580  mov     [rsp+368h+var_348], rdi
0x10043d585  xor     r8d, r8d
0x10043d588  lea     rdx, ?WrapGetDiskFreeSpaceW@@YAHPEB_WPEAK111@Z; WrapGetDiskFreeSpaceW(wchar_t const *,ulong *,ulong *,ulong *,ulong *)
0x10043d58f  lea     rcx, ?gGetDiskFreeSpaceW@@3P6AHPEB_WPEAK111@ZEA; int (*gGetDiskFreeSpaceW)(wchar_t const *,ulong *,ulong *,ulong *,ulong *)
0x10043d596  call    DetourAttachEx
0x10043d59b  xor     r9d, r9d
0x10043d59e  mov     [rsp+368h+var_348], rdi
0x10043d5a3  xor     r8d, r8d
0x10043d5a6  lea     rdx, ?WrapGetDiskFreeSpaceExW@@YAHPEBDPEAT_ULARGE_INTEGER@@11@Z; WrapGetDiskFreeSpaceExW(char const *,_ULARGE_INTEGER *,_ULARGE_INTEGER *,_ULARGE_INTEGER *)
0x10043d5ad  lea     rcx, ?gGetDiskFreeSpaceExW@@3P6AHPEB_WPEAT_ULARGE_INTEGER@@11@ZEA; int (*gGetDiskFreeSpaceExW)(wchar_t const *,_ULARGE_INTEGER *,_ULARGE_INTEGER *,_ULARGE_INTEGER *)
0x10043d5b4  call    DetourAttachEx
0x10043d5b9  xor     ecx, ecx
0x10043d5bb  call    DetourTransactionCommitEx
0x10043d5c0  test    eax, eax
0x10043d5c2  jz      short loc_10043D5C9
0x10043d5c4  mov     eax, 1
0x10043d5c9  mov     rcx, [rsp+368h+var_18]
0x10043d5d1  xor     rcx, rsp; StackCookie
0x10043d5d4  call    __security_check_cookie
0x10043d5d9  mov     rbx, [rsp+368h+arg_0]
0x10043d5e1  add     rsp, 360h
0x10043d5e8  pop     rdi
0x10043d5e9  retn
```
