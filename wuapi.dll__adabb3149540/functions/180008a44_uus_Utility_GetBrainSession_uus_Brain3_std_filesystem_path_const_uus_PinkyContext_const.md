# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x180008a44`
- end: `0x180008b71`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `301`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180006f90`

## callees

- `0x180008a44`
- `0x180009b50`
- `0x18000a66c`
- `0x18000aa38`
- `0x18000fce0`
- `0x180015a00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008aa0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008aa0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008af4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008af4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008b30`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008b30`

## string_xrefs

- `0x180008aea`: `DllGetSessionForPinky`
- `0x180008ad8`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`
- `0x180008b59`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall uus::Utility::GetBrainSession<uus::Brain3>(char *a1, __int64 a2)
{
  char *v3; // rdi
  int v4; // eax
  HMODULE Library; // rbx
  FARPROC ProcAddress; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  int v10; // eax
  __int64 v11; // rdi
  int v13; // [rsp+20h] [rbp-38h]
  __int64 v14; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v3 = a1;
  if ( a2 )
    v4 = (*(_DWORD *)(a2 + 12) >> 2) & 1;
  else
    v4 = 0;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(char **)a1;
  Library = LoadLibraryExW((LPCWSTR)a1, 0, ((v4 ^ 1u) << 7) + 8);
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(char **)v3;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x164,
    (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UndockedUpdateStack.hpp",
    (const char *)(Library == 0),
    (void *)"Error loading library %s",
    v3,
    2,
    Library);
  ProcAddress = GetProcAddress(Library, "DllGetSessionForPinky");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, v7, v8, v9);
  v14 = 0;
  v10 = ((__int64 (__fastcall *)(__int64 *, __int64))ProcAddress)(&v14, a2);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UndockedUpdateStack.hpp",
      (const char *)(unsigned int)v10,
      v13);
  v11 = v14;
  if ( Library )
    FreeLibrary(Library);
  return v11;
}

```

## disassembly

```asm
0x180008a44  mov     [rsp+arg_10], rbx
0x180008a49  mov     [rsp+arg_18], rsi
0x180008a4e  push    rdi
0x180008a4f  sub     rsp, 50h
0x180008a53  mov     rax, cs:__security_cookie
0x180008a5a  xor     rax, rsp
0x180008a5d  mov     [rsp+58h+var_10], rax
0x180008a62  mov     rsi, rdx
0x180008a65  mov     rdi, rcx
0x180008a68  mov     [rsp+58h+var_28], 0
0x180008a70  test    rdx, rdx
0x180008a73  jz      short loc_180008A80
0x180008a75  mov     eax, [rdx+0Ch]
0x180008a78  shr     eax, 2
0x180008a7b  and     eax, 1
0x180008a7e  jmp     short loc_180008A82
0x180008a80  xor     eax, eax
0x180008a82  xor     eax, 1
0x180008a85  shl     eax, 7
0x180008a88  lea     r8d, [rax+8]; dwFlags
0x180008a8c  mov     [rsp+58h+var_28], 2
0x180008a94  cmp     qword ptr [rcx+18h], 7
0x180008a99  jbe     short loc_180008A9E
0x180008a9b  mov     rcx, [rcx]; lpLibFileName
0x180008a9e  xor     edx, edx; hFile
0x180008aa0  call    cs:__imp_LoadLibraryExW
0x180008aa6  mov     rbx, rax
0x180008aa9  mov     [rsp+58h+var_20], rax
0x180008aae  cmp     qword ptr [rdi+18h], 7
0x180008ab3  jbe     short loc_180008AB8
0x180008ab5  mov     rdi, [rdi]
0x180008ab8  test    rbx, rbx
0x180008abb  setz    al
0x180008abe  mov     rcx, [rsp+58h]; this
0x180008ac3  mov     [rsp+58h+var_30], rdi; char *
0x180008ac8  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x180008acf  mov     [rsp+58h+var_38], rdx; int
0x180008ad4  movzx   r9d, al; char *
0x180008ad8  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x180008adf  mov     edx, 164h; void *
0x180008ae4  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180008ae9  nop
0x180008aea  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x180008af1  mov     rcx, rbx; hModule
0x180008af4  call    cs:__imp_GetProcAddress
0x180008afa  mov     rcx, [rsp+58h]; this
0x180008aff  test    rax, rax
0x180008b02  jz      short loc_180008B6B
0x180008b04  mov     [rsp+58h+var_18], 0
0x180008b0d  mov     rdx, rsi
0x180008b10  lea     rcx, [rsp+58h+var_18]
0x180008b15  call    _guard_dispatch_icall
0x180008b1a  mov     rcx, [rsp+58h]; this
0x180008b1f  test    eax, eax
0x180008b21  js      short loc_180008B56
0x180008b23  mov     rdi, [rsp+58h+var_18]
0x180008b28  test    rbx, rbx
0x180008b2b  jz      short loc_180008B36
0x180008b2d  mov     rcx, rbx; hLibModule
0x180008b30  call    cs:__imp_FreeLibrary
0x180008b36  mov     rax, rdi
0x180008b39  mov     rcx, [rsp+58h+var_10]
0x180008b3e  xor     rcx, rsp; StackCookie
0x180008b41  call    __security_check_cookie
0x180008b46  mov     rbx, [rsp+58h+arg_10]
0x180008b4b  mov     rsi, [rsp+58h+arg_18]
0x180008b50  add     rsp, 50h
0x180008b54  pop     rdi
0x180008b55  retn
0x180008b56  mov     r9d, eax; char *
0x180008b59  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x180008b60  mov     edx, 177h; void *
0x180008b65  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180008b6b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
