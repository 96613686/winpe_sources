# Windows::COM::GetCurrentDllWin32Path(void *,Windows::Auto<_LUNICODE_STRING> *)

- ea: `0x18001a260`
- end: `0x18001a5db`
- name: `?GetCurrentDllWin32Path@COM@Windows@@YAJPEAXPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z`
- size: `891`
- prototype: `__int64 __fastcall(LPCWSTR lpModuleName, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180002500`

## callees

- `0x1800054f0`
- `0x180007568`
- `0x1800077f4`
- `0x180007cc0`
- `0x180007d8c`
- `0x180009410`
- `0x18001a17c`
- `0x18001a260`
- `0x18001a5e4`
- `0x18001b7b0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001a460`
- `msvcrt!_wcsnicmp` at `0x18001a460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a58e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a58e`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18001a3fc`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18001a3fc`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18001a2e2`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18001a2e2`

## string_xrefs

- `0x18001a290`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x18001a315`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x18001a547`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x18001a2a9`: `Windows::COM::GetCurrentDllWin32Path`
- `0x18001a320`: `Windows::COM::GetCurrentDllWin32Path`
- `0x18001a552`: `Windows::COM::GetCurrentDllWin32Path`
- `0x18001a2b4`: `Not-null check failed: DirectoryOut`

## pseudocode

```c
__int64 __fastcall Windows::COM::GetCurrentDllWin32Path(LPCWSTR lpModuleName, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  int LastError; // ebx
  NTSTATUS i; // eax
  LPWSTR v8; // rcx
  unsigned __int64 v9; // rsi
  DWORD v10; // ebx
  unsigned __int64 v11; // rax
  const wchar_t *v12; // rdi
  DWORD ModuleFileNameW; // eax
  LPWSTR v14; // rcx
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rcx
  LPWSTR v18; // xmm1_8
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // [rsp+44h] [rbp-25h]
  int v22; // [rsp+4Ch] [rbp-1Dh]
  __int128 v23; // [rsp+50h] [rbp-19h] BYREF
  LPWSTR lpFilename; // [rsp+60h] [rbp-9h]
  __int128 v25; // [rsp+68h] [rbp-1h]
  __int64 v26; // [rsp+78h] [rbp+Fh]
  const char *v27; // [rsp+80h] [rbp+17h]
  __int128 v28; // [rsp+88h] [rbp+1Fh] BYREF
  WCHAR *v29; // [rsp+98h] [rbp+2Fh]
  HMODULE phModule; // [rsp+A0h] [rbp+37h] BYREF

  if ( !a2 )
  {
    v26 = 23;
    *(_QWORD *)&v25 = "onecore\\base\\wcp\\rtllib\\win32lib\\dllpath_library.cpp";
    *((_QWORD *)&v25 + 1) = "Windows::COM::GetCurrentDllWin32Path";
    v27 = "Not-null check failed: DirectoryOut";
    RtlReportErrorOrigination(lpModuleName, 0, 2147500035LL);
    return 2147500035LL;
  }
  phModule = 0;
  if ( !GetModuleHandleExW(6u, lpModuleName, &phModule) )
  {
    if ( !GetLastError() )
    {
      LastError = 14077;
LABEL_7:
      v26 = 29;
      *(_QWORD *)&v25 = "onecore\\base\\wcp\\rtllib\\win32lib\\dllpath_library.cpp";
      *((_QWORD *)&v25 + 1) = "Windows::COM::GetCurrentDllWin32Path";
      v27 = "GetLastError";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RtlReportErrorOrigination(v5, v4, (unsigned int)LastError);
      return (unsigned int)LastError;
    }
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_7;
LABEL_51:
    INTERNAL_ERROR_ACTION(-1073741595);
  }
  v23 = 0;
  lpFilename = 0;
  for ( i = RtlAllocateLUnicodeString(260, &v23); ; i = RtlReallocateLUnicodeString(v14, v9 + 260, &v23) )
  {
    if ( i < 0 )
      goto LABEL_13;
    v9 = *((_QWORD *)&v23 + 1);
    v10 = 0;
    v11 = (*((_QWORD *)&v23 + 1) >> 1) - 2LL;
    if ( v11 > 0xFFFFFFFF )
    {
      v21 = -2147024362;
      LOBYTE(v22) = 22;
    }
    else
    {
      v10 = (*((_QWORD *)&v23 + 1) >> 1) - 2;
      if ( v11 == (unsigned int)v11 )
      {
        v21 = 0;
        LOBYTE(v22) = 0;
      }
      else
      {
        v21 = -2147467259;
        LOBYTE(v22) = 5;
      }
    }
    *(_WORD *)((char *)&v22 + 1) = *(_WORD *)((char *)&v21 + 1);
    HIBYTE(v22) = HIBYTE(v21);
    if ( v22 < 0 )
    {
      if ( lpFilename )
        anonymous_namespace_::OurRtlFreeStringRoutine(lpFilename);
      return (unsigned int)v22;
    }
    v12 = lpFilename;
    ModuleFileNameW = GetModuleFileNameW(phModule, lpFilename, v10);
    if ( !ModuleFileNameW )
    {
      if ( GetLastError() )
      {
        LastError = GetLastError();
        if ( !LastError )
          goto LABEL_51;
      }
      else
      {
        LastError = 14077;
      }
      v26 = 44;
      *(_QWORD *)&v25 = "onecore\\base\\wcp\\rtllib\\win32lib\\dllpath_library.cpp";
      *((_QWORD *)&v25 + 1) = "Windows::COM::GetCurrentDllWin32Path";
      v27 = "GetLastError";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RtlReportErrorOrigination(v20, v19, (unsigned int)LastError);
      if ( v12 )
      {
        v8 = (LPWSTR)v12;
        goto LABEL_15;
      }
      return (unsigned int)LastError;
    }
    if ( ModuleFileNameW < v10 )
      break;
    if ( v9 + 260 < v9 )
    {
      if ( v12 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v12);
      return 2147942934LL;
    }
  }
  *(_QWORD *)&v23 = 2LL * ModuleFileNameW;
  if ( (unsigned __int64)v23 > 0x208 && _wcsnicmp(L"\\\\?\\", v12, 4u) )
  {
    v28 = 0;
    v29 = 0;
    LastError = Windows::COM::FilePathCombine((__int64)v14, &v23, (unsigned __int64 *)&v28);
    if ( LastError < 0 )
    {
      if ( v29 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v29);
LABEL_14:
      v8 = lpFilename;
      if ( lpFilename )
LABEL_15:
        anonymous_namespace_::OurRtlFreeStringRoutine(v8);
      return (unsigned int)LastError;
    }
    v14 = lpFilename;
    lpFilename = v29;
    v23 = v28;
    if ( v14 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v14);
  }
  v29 = 0;
  v26 = 0;
  v28 = 0;
  v25 = 0;
  i = RtlSplitLUnicodeString((_DWORD)v14, (unsigned int)&v23, v15, v16);
  if ( i < 0 )
  {
LABEL_13:
    LastError = ConvertNtStatusToHResult(i);
    goto LABEL_14;
  }
  v17 = *(_QWORD *)(a2 + 16);
  v18 = lpFilename;
  *(_QWORD *)&v23 = v28;
  *(_OWORD *)a2 = v23;
  *(_QWORD *)(a2 + 16) = v18;
  if ( v17 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v17);
  return 0;
}

```

## disassembly

```asm
0x18001a260  mov     [rsp-8+arg_10], rbx
0x18001a265  mov     [rsp-8+arg_18], rsi
0x18001a26a  push    rbp
0x18001a26b  push    rdi
0x18001a26c  push    r14
0x18001a26e  lea     rbp, [rsp-47h]
0x18001a273  sub     rsp, 0B0h
0x18001a27a  mov     rax, cs:__security_cookie
0x18001a281  xor     rax, rsp
0x18001a284  mov     [rbp+57h+var_18], rax
0x18001a288  mov     r14, rdx
0x18001a28b  test    rdx, rdx
0x18001a28e  jnz     short loc_18001A2CE
0x18001a290  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x18001a297  mov     [rbp+57h+var_48], 17h
0x18001a29f  mov     qword ptr [rbp+57h+var_58], rax
0x18001a2a3  mov     r8d, 80004003h
0x18001a2a9  lea     rax, aWindowsComGetc; "Windows::COM::GetCurrentDllWin32Path"
0x18001a2b0  mov     qword ptr [rbp+57h+var_58+8], rax
0x18001a2b4  lea     rax, aNotNullCheckFa_2; "Not-null check failed: DirectoryOut"
0x18001a2bb  mov     [rbp+57h+var_40], rax
0x18001a2bf  call    RtlReportErrorOrigination
0x18001a2c4  mov     eax, 80004003h
0x18001a2c9  jmp     loc_18001A5AC
0x18001a2ce  mov     rdx, rcx; lpModuleName
0x18001a2d1  mov     [rbp+57h+phModule], 0
0x18001a2d9  mov     ecx, 6; dwFlags
0x18001a2de  lea     r8, [rbp+57h+phModule]; phModule
0x18001a2e2  call    cs:__imp_GetModuleHandleExW
0x18001a2e8  test    eax, eax
0x18001a2ea  jnz     short loc_18001A352
0x18001a2ec  call    cs:__imp_GetLastError
0x18001a2f2  test    eax, eax
0x18001a2f4  jnz     short loc_18001A2FD
0x18001a2f6  mov     ebx, 36FDh
0x18001a2fb  jmp     short loc_18001A30D
0x18001a2fd  call    cs:__imp_GetLastError
0x18001a303  mov     ebx, eax
0x18001a305  test    eax, eax
0x18001a307  jz      loc_18001A5D0
0x18001a30d  mov     [rbp+57h+var_48], 1Dh
0x18001a315  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x18001a31c  mov     qword ptr [rbp+57h+var_58], rax
0x18001a320  lea     rax, aWindowsComGetc; "Windows::COM::GetCurrentDllWin32Path"
0x18001a327  mov     qword ptr [rbp+57h+var_58+8], rax
0x18001a32b  lea     rax, aGetlasterror; "GetLastError"
0x18001a332  mov     [rbp+57h+var_40], rax
0x18001a336  test    ebx, ebx
0x18001a338  jle     short loc_18001A343
0x18001a33a  movzx   ebx, bx
0x18001a33d  or      ebx, 80070000h
0x18001a343  mov     r8d, ebx
0x18001a346  call    RtlReportErrorOrigination
0x18001a34b  mov     eax, ebx
0x18001a34d  jmp     loc_18001A5AC
0x18001a352  xorps   xmm0, xmm0
0x18001a355  lea     rdx, [rbp+57h+var_70]
0x18001a359  xor     eax, eax
0x18001a35b  mov     ecx, 104h
0x18001a360  movups  [rbp+57h+var_70], xmm0
0x18001a364  mov     [rbp+57h+lpFilename], rax
0x18001a368  call    RtlAllocateLUnicodeString
0x18001a36d  test    eax, eax
0x18001a36f  jns     short loc_18001A38A
0x18001a371  mov     ecx, eax; Status
0x18001a373  call    ConvertNtStatusToHResult
0x18001a378  mov     ebx, eax
0x18001a37a  mov     rcx, [rbp+57h+lpFilename]
0x18001a37e  test    rcx, rcx
0x18001a381  jz      short loc_18001A34B
0x18001a383  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a388  jmp     short loc_18001A34B
0x18001a38a  mov     rsi, qword ptr [rbp+57h+var_70+8]
0x18001a38e  xor     ecx, ecx
0x18001a390  mov     rax, rsi
0x18001a393  mov     [rbp+57h+var_7C], ecx
0x18001a396  shr     rax, 1
0x18001a399  xor     ebx, ebx
0x18001a39b  add     rax, 0FFFFFFFFFFFFFFFEh
0x18001a39f  mov     ecx, 0FFFFFFFFh
0x18001a3a4  cmp     rax, rcx
0x18001a3a7  ja      short loc_18001A3CA
0x18001a3a9  mov     ebx, eax
0x18001a3ab  cmp     rax, rbx
0x18001a3ae  jz      short loc_18001A3BD
0x18001a3b0  mov     [rbp+57h+var_7C], 80004005h
0x18001a3b7  mov     byte ptr [rbp+57h+var_74], 5
0x18001a3bb  jmp     short loc_18001A3D5
0x18001a3bd  mov     [rbp+57h+var_7C], 0
0x18001a3c4  mov     byte ptr [rbp+57h+var_74], 0
0x18001a3c8  jmp     short loc_18001A3D5
0x18001a3ca  mov     [rbp+57h+var_7C], 80070216h
0x18001a3d1  mov     byte ptr [rbp+57h+var_74], 16h
0x18001a3d5  movzx   eax, word ptr [rbp+57h+var_7C+1]
0x18001a3d9  mov     word ptr [rbp+57h+var_74+1], ax
0x18001a3dd  mov     al, byte ptr [rbp+57h+var_7C+3]
0x18001a3e0  mov     byte ptr [rbp+57h+var_74+3], al
0x18001a3e3  mov     edi, [rbp+57h+var_74]
0x18001a3e6  test    edi, edi
0x18001a3e8  js      loc_18001A59C
0x18001a3ee  mov     rdi, [rbp+57h+lpFilename]
0x18001a3f2  mov     r8d, ebx; nSize
0x18001a3f5  mov     rcx, [rbp+57h+phModule]; hModule
0x18001a3f9  mov     rdx, rdi; lpFilename
0x18001a3fc  call    cs:__imp_GetModuleFileNameW
0x18001a402  test    eax, eax
0x18001a404  jz      loc_18001A530
0x18001a40a  cmp     eax, ebx
0x18001a40c  jb      short loc_18001A43F
0x18001a40e  lea     rdx, [rsi+104h]
0x18001a415  cmp     rdx, rsi
0x18001a418  jb      short loc_18001A428
0x18001a41a  lea     r8, [rbp+57h+var_70]
0x18001a41e  call    RtlReallocateLUnicodeString
0x18001a423  jmp     loc_18001A36D
0x18001a428  test    rdi, rdi
0x18001a42b  jz      short loc_18001A435
0x18001a42d  mov     rcx, rdi
0x18001a430  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a435  mov     eax, 80070216h
0x18001a43a  jmp     loc_18001A5AC
0x18001a43f  mov     eax, eax
0x18001a441  add     rax, rax
0x18001a444  mov     qword ptr [rbp+57h+var_70], rax
0x18001a448  cmp     rax, 208h
0x18001a44e  jbe     short loc_18001A4C1
0x18001a450  mov     r8d, 4; MaxCount
0x18001a456  lea     rcx, Buf2; "\\\\?\\"
0x18001a45d  mov     rdx, rdi; String2
0x18001a460  call    cs:__imp__wcsnicmp
0x18001a466  test    eax, eax
0x18001a468  jz      short loc_18001A4C1
0x18001a46a  xorps   xmm0, xmm0
0x18001a46d  lea     r8, [rbp+57h+var_38]
0x18001a471  xor     eax, eax
0x18001a473  lea     rdx, [rbp+57h+var_70]
0x18001a477  movups  [rbp+57h+var_38], xmm0
0x18001a47b  mov     [rbp+57h+var_28], rax
0x18001a47f  call    ?FilePathCombine@COM@Windows@@YAJPEB_WAEBU_LUNICODE_STRING@@PEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::FilePathCombine(wchar_t const *,_LUNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> *)
0x18001a484  mov     ebx, eax
0x18001a486  test    eax, eax
0x18001a488  jns     short loc_18001A4A1
0x18001a48a  mov     rcx, [rbp+57h+var_28]
0x18001a48e  test    rcx, rcx
0x18001a491  jz      loc_18001A37A
0x18001a497  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a49c  jmp     loc_18001A37A
0x18001a4a1  mov     rcx, [rbp+57h+lpFilename]
0x18001a4a5  movsd   xmm1, [rbp+57h+var_28]
0x18001a4aa  movsd   [rbp+57h+lpFilename], xmm1
0x18001a4af  movups  xmm0, [rbp+57h+var_38]
0x18001a4b3  movups  [rbp+57h+var_70], xmm0
0x18001a4b7  test    rcx, rcx
0x18001a4ba  jz      short loc_18001A4C1
0x18001a4bc  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a4c1  xor     eax, eax
0x18001a4c3  lea     rdx, [rbp+57h+var_70]
0x18001a4c7  mov     [rbp+57h+var_28], rax
0x18001a4cb  xorps   xmm0, xmm0
0x18001a4ce  mov     [rbp+57h+var_48], rax
0x18001a4d2  xorps   xmm1, xmm1
0x18001a4d5  lea     rax, [rbp+57h+var_58]
0x18001a4d9  mov     [rsp+0C0h+var_90], rax
0x18001a4de  lea     rax, [rbp+57h+var_38]
0x18001a4e2  mov     [rsp+0C0h+var_98], rax
0x18001a4e7  movups  [rbp+57h+var_38], xmm0
0x18001a4eb  movups  [rbp+57h+var_58], xmm1
0x18001a4ef  call    RtlSplitLUnicodeString
0x18001a4f4  test    eax, eax
0x18001a4f6  js      loc_18001A371
0x18001a4fc  movsd   xmm2, qword ptr [r14+10h]
0x18001a502  mov     rax, qword ptr [rbp+57h+var_38]
0x18001a506  movq    rcx, xmm2
0x18001a50b  movsd   xmm1, [rbp+57h+lpFilename]
0x18001a510  mov     qword ptr [rbp+57h+var_70], rax
0x18001a514  movups  xmm0, [rbp+57h+var_70]
0x18001a518  movups  xmmword ptr [r14], xmm0
0x18001a51c  movsd   qword ptr [r14+10h], xmm1
0x18001a522  test    rcx, rcx
0x18001a525  jz      short loc_18001A52C
0x18001a527  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a52c  xor     eax, eax
0x18001a52e  jmp     short loc_18001A5AC
0x18001a530  call    cs:__imp_GetLastError
0x18001a536  test    eax, eax
0x18001a538  jnz     short loc_18001A58E
0x18001a53a  mov     ebx, 36FDh
0x18001a53f  mov     [rbp+57h+var_48], 2Ch ; ','
0x18001a547  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x18001a54e  mov     qword ptr [rbp+57h+var_58], rax
0x18001a552  lea     rax, aWindowsComGetc; "Windows::COM::GetCurrentDllWin32Path"
0x18001a559  mov     qword ptr [rbp+57h+var_58+8], rax
0x18001a55d  lea     rax, aGetlasterror; "GetLastError"
0x18001a564  mov     [rbp+57h+var_40], rax
0x18001a568  test    ebx, ebx
0x18001a56a  jle     short loc_18001A575
0x18001a56c  movzx   ebx, bx
0x18001a56f  or      ebx, 80070000h
0x18001a575  mov     r8d, ebx
0x18001a578  call    RtlReportErrorOrigination
0x18001a57d  test    rdi, rdi
0x18001a580  jz      loc_18001A34B
0x18001a586  mov     rcx, rdi
0x18001a589  jmp     loc_18001A383
0x18001a58e  call    cs:__imp_GetLastError
0x18001a594  mov     ebx, eax
0x18001a596  test    eax, eax
0x18001a598  jz      short loc_18001A5D0
0x18001a59a  jmp     short loc_18001A53F
0x18001a59c  mov     rcx, [rbp+57h+lpFilename]
0x18001a5a0  test    rcx, rcx
0x18001a5a3  jz      short loc_18001A5AA
0x18001a5a5  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a5aa  mov     eax, edi
0x18001a5ac  mov     rcx, [rbp+57h+var_18]
0x18001a5b0  xor     rcx, rsp; StackCookie
0x18001a5b3  call    __security_check_cookie
0x18001a5b8  lea     r11, [rsp+0C0h+var_10]
0x18001a5c0  mov     rbx, [r11+30h]
0x18001a5c4  mov     rsi, [r11+38h]
0x18001a5c8  mov     rsp, r11
0x18001a5cb  pop     r14
0x18001a5cd  pop     rdi
0x18001a5ce  pop     rbp
0x18001a5cf  retn
0x18001a5d0  mov     ecx, 0C00000E5h; int
0x18001a5d5  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
