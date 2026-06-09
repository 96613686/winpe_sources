# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x180008714`
- end: `0x180008841`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `301`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180008848`

## callees

- `0x180008614`
- `0x1800086f8`
- `0x180008714`
- `0x180009e68`
- `0x18000fc90`
- `0x1800159b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008770`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008770`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800087c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800087c4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008800`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008800`

## string_xrefs

- `0x1800087ba`: `DllGetSessionForPinky`
- `0x1800087a8`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`
- `0x180008829`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
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
0x180008714  mov     [rsp+arg_10], rbx
0x180008719  mov     [rsp+arg_18], rsi
0x18000871e  push    rdi
0x18000871f  sub     rsp, 50h
0x180008723  mov     rax, cs:__security_cookie
0x18000872a  xor     rax, rsp
0x18000872d  mov     [rsp+58h+var_10], rax
0x180008732  mov     rsi, rdx
0x180008735  mov     rdi, rcx
0x180008738  mov     [rsp+58h+var_28], 0
0x180008740  test    rdx, rdx
0x180008743  jz      short loc_180008750
0x180008745  mov     eax, [rdx+0Ch]
0x180008748  shr     eax, 2
0x18000874b  and     eax, 1
0x18000874e  jmp     short loc_180008752
0x180008750  xor     eax, eax
0x180008752  xor     eax, 1
0x180008755  shl     eax, 7
0x180008758  lea     r8d, [rax+8]; dwFlags
0x18000875c  mov     [rsp+58h+var_28], 2
0x180008764  cmp     qword ptr [rcx+18h], 7
0x180008769  jbe     short loc_18000876E
0x18000876b  mov     rcx, [rcx]; lpLibFileName
0x18000876e  xor     edx, edx; hFile
0x180008770  call    cs:__imp_LoadLibraryExW
0x180008776  mov     rbx, rax
0x180008779  mov     [rsp+58h+var_20], rax
0x18000877e  cmp     qword ptr [rdi+18h], 7
0x180008783  jbe     short loc_180008788
0x180008785  mov     rdi, [rdi]
0x180008788  test    rbx, rbx
0x18000878b  setz    al
0x18000878e  mov     rcx, [rsp+58h]; this
0x180008793  mov     [rsp+58h+var_30], rdi; char *
0x180008798  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x18000879f  mov     [rsp+58h+var_38], rdx; int
0x1800087a4  movzx   r9d, al; char *
0x1800087a8  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x1800087af  mov     edx, 164h; void *
0x1800087b4  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800087b9  nop
0x1800087ba  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x1800087c1  mov     rcx, rbx; hModule
0x1800087c4  call    cs:__imp_GetProcAddress
0x1800087ca  mov     rcx, [rsp+58h]; this
0x1800087cf  test    rax, rax
0x1800087d2  jz      short loc_18000883B
0x1800087d4  mov     [rsp+58h+var_18], 0
0x1800087dd  mov     rdx, rsi
0x1800087e0  lea     rcx, [rsp+58h+var_18]
0x1800087e5  call    _guard_dispatch_icall
0x1800087ea  mov     rcx, [rsp+58h]; this
0x1800087ef  test    eax, eax
0x1800087f1  js      short loc_180008826
0x1800087f3  mov     rdi, [rsp+58h+var_18]
0x1800087f8  test    rbx, rbx
0x1800087fb  jz      short loc_180008806
0x1800087fd  mov     rcx, rbx; hLibModule
0x180008800  call    cs:__imp_FreeLibrary
0x180008806  mov     rax, rdi
0x180008809  mov     rcx, [rsp+58h+var_10]
0x18000880e  xor     rcx, rsp; StackCookie
0x180008811  call    __security_check_cookie
0x180008816  mov     rbx, [rsp+58h+arg_10]
0x18000881b  mov     rsi, [rsp+58h+arg_18]
0x180008820  add     rsp, 50h
0x180008824  pop     rdi
0x180008825  retn
0x180008826  mov     r9d, eax; char *
0x180008829  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x180008830  mov     edx, 177h; void *
0x180008835  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000883b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
