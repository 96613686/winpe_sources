# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x14000951c`
- end: `0x140009649`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14000713c`

## callees

- `0x14000951c`
- `0x14000aca0`
- `0x14000b6f8`
- `0x14000bb30`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140009608`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140009608`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400095cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400095cc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140009578`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140009578`

## string_xrefs

- `0x1400095c2`: `DllGetSessionForPinky`
- `0x1400095b0`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`
- `0x140009631`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x14000951c  mov     [rsp+arg_10], rbx
0x140009521  mov     [rsp+arg_18], rsi
0x140009526  push    rdi
0x140009527  sub     rsp, 50h
0x14000952b  mov     rax, cs:__security_cookie
0x140009532  xor     rax, rsp
0x140009535  mov     [rsp+58h+var_10], rax
0x14000953a  mov     rsi, rdx
0x14000953d  mov     rdi, rcx
0x140009540  mov     [rsp+58h+var_28], 0
0x140009548  test    rdx, rdx
0x14000954b  jz      short loc_140009558
0x14000954d  mov     eax, [rdx+0Ch]
0x140009550  shr     eax, 2
0x140009553  and     eax, 1
0x140009556  jmp     short loc_14000955A
0x140009558  xor     eax, eax
0x14000955a  xor     eax, 1
0x14000955d  shl     eax, 7
0x140009560  lea     r8d, [rax+8]; dwFlags
0x140009564  mov     [rsp+58h+var_28], 2
0x14000956c  cmp     qword ptr [rcx+18h], 7
0x140009571  jbe     short loc_140009576
0x140009573  mov     rcx, [rcx]; lpLibFileName
0x140009576  xor     edx, edx; hFile
0x140009578  call    cs:__imp_LoadLibraryExW
0x14000957e  mov     rbx, rax
0x140009581  mov     [rsp+58h+var_20], rax
0x140009586  cmp     qword ptr [rdi+18h], 7
0x14000958b  jbe     short loc_140009590
0x14000958d  mov     rdi, [rdi]
0x140009590  test    rbx, rbx
0x140009593  setz    al
0x140009596  mov     rcx, [rsp+58h]; this
0x14000959b  mov     [rsp+58h+var_30], rdi; char *
0x1400095a0  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x1400095a7  mov     [rsp+58h+var_38], rdx; int
0x1400095ac  movzx   r9d, al; char *
0x1400095b0  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x1400095b7  mov     edx, 164h; void *
0x1400095bc  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1400095c1  nop
0x1400095c2  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x1400095c9  mov     rcx, rbx; hModule
0x1400095cc  call    cs:__imp_GetProcAddress
0x1400095d2  mov     rcx, [rsp+58h]; this
0x1400095d7  test    rax, rax
0x1400095da  jz      short loc_140009643
0x1400095dc  mov     [rsp+58h+var_18], 0
0x1400095e5  mov     rdx, rsi
0x1400095e8  lea     rcx, [rsp+58h+var_18]
0x1400095ed  call    _guard_dispatch_icall
0x1400095f2  mov     rcx, [rsp+58h]; this
0x1400095f7  test    eax, eax
0x1400095f9  js      short loc_14000962E
0x1400095fb  mov     rdi, [rsp+58h+var_18]
0x140009600  test    rbx, rbx
0x140009603  jz      short loc_14000960E
0x140009605  mov     rcx, rbx; hLibModule
0x140009608  call    cs:__imp_FreeLibrary
0x14000960e  mov     rax, rdi
0x140009611  mov     rcx, [rsp+58h+var_10]
0x140009616  xor     rcx, rsp; StackCookie
0x140009619  call    __security_check_cookie
0x14000961e  mov     rbx, [rsp+58h+arg_10]
0x140009623  mov     rsi, [rsp+58h+arg_18]
0x140009628  add     rsp, 50h
0x14000962c  pop     rdi
0x14000962d  retn
0x14000962e  mov     r9d, eax; char *
0x140009631  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x140009638  mov     edx, 177h; void *
0x14000963d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009643  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
