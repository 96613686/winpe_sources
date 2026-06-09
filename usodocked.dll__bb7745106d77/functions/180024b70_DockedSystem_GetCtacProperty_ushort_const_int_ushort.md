# DockedSystem::GetCtacProperty(ushort const *,int *,ushort * *)

- ea: `0x180024b70`
- end: `0x180024d52`
- name: `?GetCtacProperty@DockedSystem@@UEAAJPEBGPEAHPEAPEAG@Z`
- size: `482`
- prototype: `__int64 __fastcall(DockedSystem *__hidden this, const unsigned __int16 *, int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x180007660`
- `0x1800183f4`
- `0x1800209fc`
- `0x180023a18`
- `0x180024b70`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024c0c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024c0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024c5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024c5d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024c32`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024c4d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024c32`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024c4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c3a`

## string_xrefs

- `0x180024baa`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180024bd4`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180024d16`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180024d2b`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180024d3f`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180024c05`: `appraiser.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DockedSystem::GetCtacProperty(
        DockedSystem *this,
        const unsigned __int16 *a2,
        int *a3,
        unsigned __int16 **a4)
{
  __int64 result; // rax
  int *v8; // rdi
  HMODULE Library; // rsi
  HMODULE v10; // r15
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax
  const char *v13; // r9
  int v14; // eax
  int v15; // eax
  const char *v16; // r9
  int v17; // [rsp+20h] [rbp-58h] BYREF
  __int64 v18; // [rsp+28h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a3 )
  {
    if ( a4 )
    {
      *a3 = 0;
      v8 = (int *)((char *)this + 16);
      if ( !*((_QWORD *)this + 2) )
      {
        Library = LoadLibraryExW(L"appraiser.dll", 0, 0x800u);
        if ( v8 == &v17 )
        {
          if ( Library )
            FreeLibrary(Library);
        }
        else
        {
          v10 = *(HMODULE *)v8;
          if ( *(_QWORD *)v8 )
          {
            LastError = GetLastError();
            FreeLibrary(v10);
            SetLastError(LastError);
          }
          *(_QWORD *)v8 = Library;
        }
      }
      ProcAddress = GetProcAddress(*(HMODULE *)v8, "GetCtacProvider");
      try
      {
        if ( !ProcAddress )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0xBA,
            (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
            v13);
        v18 = 0;
        v14 = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v18);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xBD,
            (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
            (const char *)(unsigned int)v14,
            v17);
        v15 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v18 + 24LL))(
                v18,
                a2,
                a4);
        if ( v15 == -2147217118 )
        {
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          result = 0;
        }
        else
        {
          if ( v15 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xC6,
              (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
              (const char *)(unsigned int)v15,
              v17);
          *a3 = 1;
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          result = 0;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0xCB,
                               (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docke"
                                             "d\\dll\\dockedsystem.cpp",
                               v16);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB0,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
        (const char *)0x80004003LL,
        v17);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
      (const char *)0x80004003LL,
      v17);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180024b70  push    rbx
0x180024b72  push    rsi
0x180024b73  push    rdi
0x180024b74  push    r12
0x180024b76  push    r13
0x180024b78  push    r14
0x180024b7a  push    r15
0x180024b7c  sub     rsp, 40h
0x180024b80  mov     rax, cs:__security_cookie
0x180024b87  xor     rax, rsp
0x180024b8a  mov     [rsp+78h+var_48], rax
0x180024b8f  mov     r12, r9
0x180024b92  mov     r14, r8
0x180024b95  mov     r13, rdx
0x180024b98  test    r8, r8
0x180024b9b  jnz     short loc_180024BC2
0x180024b9d  mov     rcx, [rsp+78h]; this
0x180024ba2  mov     ebx, 80004003h
0x180024ba7  mov     r9d, ebx; char *
0x180024baa  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024bb1  mov     edx, 0AFh; void *
0x180024bb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024bbb  mov     eax, ebx
0x180024bbd  jmp     loc_180024CF9
0x180024bc2  test    r12, r12
0x180024bc5  jnz     short loc_180024BEC
0x180024bc7  mov     rcx, [rsp+78h]; this
0x180024bcc  mov     ebx, 80004003h
0x180024bd1  mov     r9d, ebx; char *
0x180024bd4  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024bdb  mov     edx, 0B0h; void *
0x180024be0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024be5  mov     eax, ebx
0x180024be7  jmp     loc_180024CF9
0x180024bec  mov     dword ptr [r8], 0
0x180024bf3  lea     rdi, [rcx+10h]
0x180024bf7  cmp     qword ptr [rdi], 0
0x180024bfb  jnz     short loc_180024C53
0x180024bfd  xor     edx, edx; hFile
0x180024bff  mov     r8d, 800h; dwFlags
0x180024c05  lea     rcx, LibFileName; "appraiser.dll"
0x180024c0c  call    cs:__imp_LoadLibraryExW
0x180024c12  mov     rsi, rax
0x180024c15  lea     rax, [rsp+78h+var_58]
0x180024c1a  cmp     rdi, rax
0x180024c1d  jz      short loc_180024C45
0x180024c1f  mov     r15, [rdi]
0x180024c22  test    r15, r15
0x180024c25  jz      short loc_180024C40
0x180024c27  call    cs:__imp_GetLastError
0x180024c2d  mov     ebx, eax
0x180024c2f  mov     rcx, r15; hLibModule
0x180024c32  call    cs:__imp_FreeLibrary
0x180024c38  mov     ecx, ebx; dwErrCode
0x180024c3a  call    cs:__imp_SetLastError
0x180024c40  mov     [rdi], rsi
0x180024c43  jmp     short loc_180024C53
0x180024c45  test    rsi, rsi
0x180024c48  jz      short loc_180024C53
0x180024c4a  mov     rcx, rsi; hLibModule
0x180024c4d  call    cs:__imp_FreeLibrary
0x180024c53  lea     rdx, aGetctacprovide; "GetCtacProvider"
0x180024c5a  mov     rcx, [rdi]; hModule
0x180024c5d  call    cs:__imp_GetProcAddress
0x180024c63  mov     rcx, [rsp+78h]; this
0x180024c68  test    rax, rax
0x180024c6b  jz      loc_180024D16
0x180024c71  mov     [rsp+78h+var_50], 0
0x180024c7a  lea     rcx, [rsp+78h+var_50]
0x180024c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c84  mov     rcx, [rsp+78h]; this
0x180024c89  test    eax, eax
0x180024c8b  js      loc_180024D28
0x180024c91  mov     rcx, [rsp+78h+var_50]
0x180024c96  mov     rax, [rcx]
0x180024c99  mov     r8, r12
0x180024c9c  mov     rdx, r13
0x180024c9f  mov     rax, [rax+18h]
0x180024ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ca8  cmp     eax, 80041122h
0x180024cad  jnz     short loc_180024CCA
0x180024caf  mov     rcx, [rsp+78h+var_50]
0x180024cb4  test    rcx, rcx
0x180024cb7  jz      short loc_180024CC6
0x180024cb9  mov     rax, [rcx]
0x180024cbc  mov     rax, [rax+10h]
0x180024cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cc5  nop
0x180024cc6  xor     eax, eax
0x180024cc8  jmp     short loc_180024CF9
0x180024cca  mov     rcx, [rsp+78h]; this
0x180024ccf  test    eax, eax
0x180024cd1  js      short loc_180024D3C
0x180024cd3  mov     dword ptr [r14], 1
0x180024cda  mov     rcx, [rsp+78h+var_50]
0x180024cdf  test    rcx, rcx
0x180024ce2  jz      short loc_180024CF1
0x180024ce4  mov     rax, [rcx]
0x180024ce7  mov     rax, [rax+10h]
0x180024ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cf0  nop
0x180024cf1  xor     eax, eax
0x180024cf3  jmp     short loc_180024CF9
0x180024cf5  mov     eax, dword ptr [rsp+78h+var_50]
0x180024cf9  mov     rcx, [rsp+78h+var_48]
0x180024cfe  xor     rcx, rsp; StackCookie
0x180024d01  call    __security_check_cookie
0x180024d06  add     rsp, 40h
0x180024d0a  pop     r15
0x180024d0c  pop     r14
0x180024d0e  pop     r13
0x180024d10  pop     r12
0x180024d12  pop     rdi
0x180024d13  pop     rsi
0x180024d14  pop     rbx
0x180024d15  retn
0x180024d16  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024d1d  mov     edx, 0BAh; void *
0x180024d22  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180024d28  mov     r9d, eax; char *
0x180024d2b  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024d32  mov     edx, 0BDh; void *
0x180024d37  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024d3c  mov     r9d, eax; char *
0x180024d3f  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024d46  mov     edx, 0C6h; void *
0x180024d4b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
