# CMiscHelpersT<CEmptyType>::GetTempDir(ushort * *)

- ea: `0x18001c9d0`
- end: `0x18001cc3c`
- name: `?GetTempDir@?$CMiscHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z`
- size: `620`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18000af80`
- `0x18000b3cc`
- `0x180013444`
- `0x180018cc4`
- `0x18001b020`
- `0x1800244d4`
- `0x180028a30`
- `0x180029058`
- `0x18002cd9c`

## callees

- `0x180002898`
- `0x18000aba4`
- `0x18000d778`
- `0x18000ea20`
- `0x18001c9d0`
- `0x18001fd60`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cbf3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cbf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cc02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cc02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb8b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ca1e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001cb5b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ca1e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001cb5b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ca4b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001cb80`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ca4b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001cb80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cac2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cbaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cac2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cbaf`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001ca3a`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001cb6f`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001ca3a`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001cb6f`

## string_xrefs

- `0x18001ca17`: `kernelbase.dll`
- `0x18001cb54`: `kernelbase.dll`
- `0x18001cab8`: `GetTempPath2W`
- `0x18001cba5`: `GetTempPath2W`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMiscHelpersT<CEmptyType>::GetTempDir(WCHAR **a1)
{
  WCHAR *v2; // rsi
  HMODULE Library; // rax
  HMODULE v4; // rbx
  DWORD TempPathW; // r14d
  int StringCch; // eax
  unsigned int v7; // edi
  FARPROC ProcAddress; // rax
  __int64 v9; // rcx
  int v10; // eax
  HMODULE v11; // rax
  HMODULE v12; // rbx
  DWORD v13; // r15d
  signed int LastError; // eax
  FARPROC v15; // rax
  WCHAR *v16; // rax
  HANDLE ProcessHeap; // rax
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E0h] BYREF
  HMODULE v20; // [rsp+28h] [rbp-D8h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF

  v2 = 0;
  lpBuffer = 0;
  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v4 = Library;
  if ( Library && (v20 = Library, (ProcAddress = GetProcAddress(Library, "GetTempPath2W")) != 0) )
  {
    TempPathW = ((__int64 (__fastcall *)(__int64, WCHAR *))ProcAddress)(260, Buffer);
  }
  else
  {
    TempPathW = GetTempPathW(0x104u, Buffer);
    if ( !v4 )
      goto LABEL_4;
  }
  FreeLibrary(v4);
LABEL_4:
  if ( !TempPathW )
    goto LABEL_25;
  if ( TempPathW < 0x104 )
  {
    LODWORD(lpBuffer) = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Buffer, &lpBuffer);
    v7 = StringCch;
    if ( StringCch < 0
      || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                        Buffer,
                        (unsigned int)lpBuffer,
                        a1),
          v7 = StringCch,
          StringCch < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
    if ( (v7 & 0x80000000) != 0 )
      goto LABEL_16;
    goto LABEL_32;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v10 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateCchBufferN(v9, TempPathW, &lpBuffer);
  v7 = v10;
  if ( v10 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) != 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    v2 = lpBuffer;
    goto LABEL_32;
  }
  v2 = lpBuffer;
  v11 = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v12 = v11;
  if ( v11 && (v20 = v11, (v15 = GetProcAddress(v11, "GetTempPath2W")) != 0) )
  {
    v13 = ((__int64 (__fastcall *)(_QWORD, WCHAR *))v15)(TempPathW, v2);
  }
  else
  {
    v13 = GetTempPathW(TempPathW, v2);
    if ( !v12 )
      goto LABEL_24;
  }
  FreeLibrary(v12);
LABEL_24:
  if ( !v13 )
  {
LABEL_25:
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v7 = -2147467259;
    }
    goto LABEL_16;
  }
  if ( v13 != TempPathW - 1 )
  {
    v7 = -2147024774;
LABEL_16:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_32;
  }
  v16 = v2;
  v2 = 0;
  *a1 = v16;
LABEL_32:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v7;
}

```

## disassembly

```asm
0x18001c9d0  mov     [rsp-8+arg_8], rbx
0x18001c9d5  mov     [rsp-8+arg_10], rsi
0x18001c9da  push    rbp
0x18001c9db  push    rdi
0x18001c9dc  push    r12
0x18001c9de  push    r14
0x18001c9e0  push    r15
0x18001c9e2  lea     rbp, [rsp-150h]
0x18001c9ea  sub     rsp, 250h
0x18001c9f1  mov     rax, cs:__security_cookie
0x18001c9f8  xor     rax, rsp
0x18001c9fb  mov     [rbp+170h+var_30], rax
0x18001ca02  mov     r12, rcx
0x18001ca05  xor     esi, esi
0x18001ca07  mov     [rsp+270h+lpBuffer], rsi
0x18001ca0c  mov     r15d, 800h
0x18001ca12  mov     r8d, r15d; dwFlags
0x18001ca15  xor     edx, edx; hFile
0x18001ca17  lea     rcx, LibFileName; "kernelbase.dll"
0x18001ca1e  call    cs:__imp_LoadLibraryExW
0x18001ca24  mov     rbx, rax
0x18001ca27  test    rax, rax
0x18001ca2a  jnz     loc_18001CAB3
0x18001ca30  lea     rdx, [rsp+270h+Buffer]; lpBuffer
0x18001ca35  mov     ecx, 104h; nBufferLength
0x18001ca3a  call    cs:__imp_GetTempPathW
0x18001ca40  mov     r14d, eax
0x18001ca43  test    rbx, rbx
0x18001ca46  jz      short loc_18001CA51
0x18001ca48  mov     rcx, rbx; hLibModule
0x18001ca4b  call    cs:__imp_FreeLibrary
0x18001ca51  test    r14d, r14d
0x18001ca54  jz      loc_18001CB8B
0x18001ca5a  cmp     r14d, 104h
0x18001ca61  jnb     loc_18001CB06
0x18001ca67  mov     dword ptr [rsp+270h+lpBuffer], 0
0x18001ca6f  lea     rdx, [rsp+270h+lpBuffer]
0x18001ca74  lea     rcx, [rsp+270h+Buffer]
0x18001ca79  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18001ca7e  mov     edi, eax
0x18001ca80  test    eax, eax
0x18001ca82  js      short loc_18001CA9B
0x18001ca84  mov     r8, r12
0x18001ca87  mov     edx, dword ptr [rsp+270h+lpBuffer]
0x18001ca8b  lea     rcx, [rsp+270h+Buffer]; Src
0x18001ca90  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18001ca95  mov     edi, eax
0x18001ca97  test    eax, eax
0x18001ca99  jns     short loc_18001CAA2
0x18001ca9b  mov     ecx, eax
0x18001ca9d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001caa2  mov     ecx, edi
0x18001caa4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001caa9  test    edi, edi
0x18001caab  jns     loc_18001CBE6
0x18001cab1  jmp     short loc_18001CAFA
0x18001cab3  mov     [rsp+270h+var_248], rbx
0x18001cab8  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18001cabf  mov     rcx, rbx; hModule
0x18001cac2  call    cs:__imp_GetProcAddress
0x18001cac8  test    rax, rax
0x18001cacb  jz      loc_18001CA30
0x18001cad1  lea     rdx, [rsp+270h+Buffer]
0x18001cad6  mov     ecx, 104h
0x18001cadb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cae0  mov     r14d, eax
0x18001cae3  jmp     loc_18001CA48
0x18001cae8  mov     edi, 80004005h
0x18001caed  jmp     short loc_18001CAFA
0x18001caef  jle     short loc_18001CAFA
0x18001caf1  movzx   edi, ax
0x18001caf4  or      edi, 80070000h
0x18001cafa  mov     ecx, edi
0x18001cafc  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001cb01  jmp     loc_18001CBE6
0x18001cb06  xor     ecx, ecx
0x18001cb08  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001cb0d  xor     ecx, ecx
0x18001cb0f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001cb14  lea     r8, [rsp+270h+lpBuffer]
0x18001cb19  mov     edx, r14d
0x18001cb1c  call    ?CreateCchBufferN@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateCchBufferN(ushort,ulong,ushort * *)
0x18001cb21  mov     edi, eax
0x18001cb23  test    eax, eax
0x18001cb25  jns     short loc_18001CB2E
0x18001cb27  mov     ecx, eax
0x18001cb29  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001cb2e  mov     ecx, edi
0x18001cb30  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001cb35  test    edi, edi
0x18001cb37  jns     short loc_18001CB4A
0x18001cb39  mov     ecx, edi
0x18001cb3b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001cb40  mov     rsi, [rsp+270h+lpBuffer]
0x18001cb45  jmp     loc_18001CBE6
0x18001cb4a  mov     rsi, [rsp+270h+lpBuffer]
0x18001cb4f  mov     r8d, r15d; dwFlags
0x18001cb52  xor     edx, edx; hFile
0x18001cb54  lea     rcx, LibFileName; "kernelbase.dll"
0x18001cb5b  call    cs:__imp_LoadLibraryExW
0x18001cb61  mov     rbx, rax
0x18001cb64  test    rax, rax
0x18001cb67  jnz     short loc_18001CBA0
0x18001cb69  mov     rdx, rsi; lpBuffer
0x18001cb6c  mov     ecx, r14d; nBufferLength
0x18001cb6f  call    cs:__imp_GetTempPathW
0x18001cb75  mov     r15d, eax
0x18001cb78  test    rbx, rbx
0x18001cb7b  jz      short loc_18001CB86
0x18001cb7d  mov     rcx, rbx; hLibModule
0x18001cb80  call    cs:__imp_FreeLibrary
0x18001cb86  test    r15d, r15d
0x18001cb89  jnz     short loc_18001CBCA
0x18001cb8b  call    cs:__imp_GetLastError
0x18001cb91  test    eax, eax
0x18001cb93  mov     edi, eax
0x18001cb95  jz      loc_18001CAE8
0x18001cb9b  jmp     loc_18001CAEF
0x18001cba0  mov     [rsp+270h+var_248], rbx
0x18001cba5  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18001cbac  mov     rcx, rbx; hModule
0x18001cbaf  call    cs:__imp_GetProcAddress
0x18001cbb5  test    rax, rax
0x18001cbb8  jz      short loc_18001CB69
0x18001cbba  mov     rdx, rsi
0x18001cbbd  mov     ecx, r14d
0x18001cbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbc5  mov     r15d, eax
0x18001cbc8  jmp     short loc_18001CB7D
0x18001cbca  lea     eax, [r14-1]
0x18001cbce  cmp     r15d, eax
0x18001cbd1  jz      short loc_18001CBDD
0x18001cbd3  mov     edi, 8007007Ah
0x18001cbd8  jmp     loc_18001CAFA
0x18001cbdd  mov     rax, rsi
0x18001cbe0  xor     esi, esi
0x18001cbe2  mov     [r12], rax
0x18001cbe6  mov     ecx, edi
0x18001cbe8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001cbed  nop
0x18001cbee  test    rsi, rsi
0x18001cbf1  jz      short loc_18001CC0F
0x18001cbf3  call    cs:__imp_GetProcessHeap
0x18001cbf9  mov     rcx, rax; hHeap
0x18001cbfc  lea     r8, [rsi-4]; lpMem
0x18001cc00  xor     edx, edx; dwFlags
0x18001cc02  call    cs:__imp_HeapFree
0x18001cc08  xor     ecx, ecx
0x18001cc0a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001cc0f  mov     eax, edi
0x18001cc11  mov     rcx, [rbp+170h+var_30]
0x18001cc18  xor     rcx, rsp; StackCookie
0x18001cc1b  call    __security_check_cookie
0x18001cc20  lea     r11, [rsp+270h+var_20]
0x18001cc28  mov     rbx, [r11+38h]
0x18001cc2c  mov     rsi, [r11+40h]
0x18001cc30  mov     rsp, r11
0x18001cc33  pop     r15
0x18001cc35  pop     r14
0x18001cc37  pop     r12
0x18001cc39  pop     rdi
0x18001cc3a  pop     rbp
0x18001cc3b  retn
```
