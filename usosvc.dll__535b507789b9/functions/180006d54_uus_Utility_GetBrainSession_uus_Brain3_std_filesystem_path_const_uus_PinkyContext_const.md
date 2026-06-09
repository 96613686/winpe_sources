# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x180006d54`
- end: `0x180006e5f`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `267`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800081ec`

## callees

- `0x180006d54`
- `0x180009ce4`
- `0x18000a1dc`
- `0x18000a224`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006df3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006df3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006e2f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006e2f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006d9c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006d9c`

## string_xrefs

- `0x180006de9`: `DllGetSessionForPinky`
- `0x180006dd4`: `onecore\internal\enduser\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
__int64 __fastcall uus::Utility::GetBrainSession<uus::Brain3>(char *a1, __int64 a2)
{
  char *v3; // rbx
  int v4; // eax
  HMODULE Library; // rdi
  FARPROC ProcAddress; // rax
  const char *v7; // r9
  int v8; // eax
  __int64 v9; // rbx
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v13; // [rsp+58h] [rbp+10h] BYREF
  HMODULE v14; // [rsp+60h] [rbp+18h]

  v3 = a1;
  if ( a2 )
    v4 = (*(_DWORD *)(a2 + 12) & 4) == 0;
  else
    v4 = 1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(char **)a1;
  Library = LoadLibraryExW((LPCWSTR)a1, 0, (v4 << 7) + 8);
  v14 = Library;
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(char **)v3;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x164,
    (unsigned int)"onecore\\internal\\enduser\\inc\\UndockedUpdateStack.hpp",
    (const char *)(Library == 0),
    (bool)"Error loading library %s",
    v3);
  ProcAddress = GetProcAddress(Library, "DllGetSessionForPinky");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x173,
      (unsigned int)"onecore\\internal\\enduser\\inc\\UndockedUpdateStack.hpp",
      v7);
  v13 = 0;
  v8 = ((__int64 (__fastcall *)(__int64 *, __int64))ProcAddress)(&v13, a2);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\internal\\enduser\\inc\\UndockedUpdateStack.hpp",
      (const char *)(unsigned int)v8,
      v11);
  v9 = v13;
  if ( Library )
    FreeLibrary(Library);
  return v9;
}

```

## disassembly

```asm
0x180006d54  push    rbx
0x180006d56  push    rsi
0x180006d57  push    rdi
0x180006d58  sub     rsp, 30h
0x180006d5c  mov     rsi, rdx
0x180006d5f  mov     rbx, rcx
0x180006d62  mov     [rsp+48h+arg_0], 0
0x180006d6a  test    rdx, rdx
0x180006d6d  jz      short loc_180006D7C
0x180006d6f  mov     eax, [rdx+0Ch]
0x180006d72  shr     eax, 2
0x180006d75  not     eax
0x180006d77  and     eax, 1
0x180006d7a  jmp     short loc_180006D81
0x180006d7c  mov     eax, 1
0x180006d81  shl     eax, 7
0x180006d84  lea     r8d, [rax+8]; dwFlags
0x180006d88  mov     [rsp+48h+arg_0], 2
0x180006d90  cmp     qword ptr [rcx+18h], 7
0x180006d95  jbe     short loc_180006D9A
0x180006d97  mov     rcx, [rcx]; lpLibFileName
0x180006d9a  xor     edx, edx; hFile
0x180006d9c  call    cs:__imp_LoadLibraryExW
0x180006da2  mov     rdi, rax
0x180006da5  mov     [rsp+48h+arg_10], rax
0x180006daa  cmp     qword ptr [rbx+18h], 7
0x180006daf  jbe     short loc_180006DB4
0x180006db1  mov     rbx, [rbx]
0x180006db4  test    rdi, rdi
0x180006db7  setz    al
0x180006dba  mov     rcx, [rsp+48h]; this
0x180006dbf  mov     [rsp+48h+var_20], rbx; char *
0x180006dc4  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x180006dcb  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180006dd0  movzx   r9d, al; char *
0x180006dd4  lea     rbx, aOnecoreInterna_2; "onecore\\internal\\enduser\\inc\\Undock"...
0x180006ddb  mov     r8, rbx; unsigned int
0x180006dde  mov     edx, 164h; void *
0x180006de3  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180006de8  nop
0x180006de9  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x180006df0  mov     rcx, rdi; hModule
0x180006df3  call    cs:__imp_GetProcAddress
0x180006df9  mov     rcx, [rsp+48h]; this
0x180006dfe  test    rax, rax
0x180006e01  jz      short loc_180006E51
0x180006e03  mov     [rsp+48h+arg_8], 0
0x180006e0c  mov     rdx, rsi
0x180006e0f  lea     rcx, [rsp+48h+arg_8]
0x180006e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e19  mov     rcx, [rsp+48h]; this
0x180006e1e  test    eax, eax
0x180006e20  js      short loc_180006E40
0x180006e22  mov     rbx, [rsp+48h+arg_8]
0x180006e27  test    rdi, rdi
0x180006e2a  jz      short loc_180006E35
0x180006e2c  mov     rcx, rdi; hLibModule
0x180006e2f  call    cs:__imp_FreeLibrary
0x180006e35  mov     rax, rbx
0x180006e38  add     rsp, 30h
0x180006e3c  pop     rdi
0x180006e3d  pop     rsi
0x180006e3e  pop     rbx
0x180006e3f  retn
0x180006e40  mov     r9d, eax; char *
0x180006e43  mov     r8, rbx; unsigned int
0x180006e46  mov     edx, 177h; void *
0x180006e4b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006e51  mov     r8, rbx; unsigned int
0x180006e54  mov     edx, 173h; void *
0x180006e59  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
