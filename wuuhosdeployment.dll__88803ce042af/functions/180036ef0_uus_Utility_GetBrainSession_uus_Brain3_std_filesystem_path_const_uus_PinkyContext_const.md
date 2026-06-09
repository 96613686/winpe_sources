# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x180036ef0`
- end: `0x18003701d`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `301`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180034358`

## callees

- `0x180036ef0`
- `0x180037cf0`
- `0x180037fc0`
- `0x1800383d0`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180036fdc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180036fdc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180036f4c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180036f4c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036fa0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036fa0`

## string_xrefs

- `0x180036f96`: `DllGetSessionForPinky`
- `0x180036f84`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`
- `0x180037005`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x180036ef0  mov     [rsp+arg_10], rbx
0x180036ef5  mov     [rsp+arg_18], rsi
0x180036efa  push    rdi
0x180036efb  sub     rsp, 50h
0x180036eff  mov     rax, cs:__security_cookie
0x180036f06  xor     rax, rsp
0x180036f09  mov     [rsp+58h+var_10], rax
0x180036f0e  mov     rsi, rdx
0x180036f11  mov     rdi, rcx
0x180036f14  mov     [rsp+58h+var_28], 0
0x180036f1c  test    rdx, rdx
0x180036f1f  jz      short loc_180036F2C
0x180036f21  mov     eax, [rdx+0Ch]
0x180036f24  shr     eax, 2
0x180036f27  and     eax, 1
0x180036f2a  jmp     short loc_180036F2E
0x180036f2c  xor     eax, eax
0x180036f2e  xor     eax, 1
0x180036f31  shl     eax, 7
0x180036f34  lea     r8d, [rax+8]; dwFlags
0x180036f38  mov     [rsp+58h+var_28], 2
0x180036f40  cmp     qword ptr [rcx+18h], 7
0x180036f45  jbe     short loc_180036F4A
0x180036f47  mov     rcx, [rcx]; lpLibFileName
0x180036f4a  xor     edx, edx; hFile
0x180036f4c  call    cs:__imp_LoadLibraryExW
0x180036f52  mov     rbx, rax
0x180036f55  mov     [rsp+58h+var_20], rax
0x180036f5a  cmp     qword ptr [rdi+18h], 7
0x180036f5f  jbe     short loc_180036F64
0x180036f61  mov     rdi, [rdi]
0x180036f64  test    rbx, rbx
0x180036f67  setz    al
0x180036f6a  mov     rcx, [rsp+58h]; this
0x180036f6f  mov     [rsp+58h+var_30], rdi; char *
0x180036f74  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x180036f7b  mov     [rsp+58h+var_38], rdx; int
0x180036f80  movzx   r9d, al; char *
0x180036f84  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x180036f8b  mov     edx, 164h; void *
0x180036f90  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180036f95  nop
0x180036f96  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x180036f9d  mov     rcx, rbx; hModule
0x180036fa0  call    cs:__imp_GetProcAddress
0x180036fa6  mov     rcx, [rsp+58h]; this
0x180036fab  test    rax, rax
0x180036fae  jz      short loc_180037017
0x180036fb0  mov     [rsp+58h+var_18], 0
0x180036fb9  mov     rdx, rsi
0x180036fbc  lea     rcx, [rsp+58h+var_18]
0x180036fc1  call    _guard_dispatch_icall
0x180036fc6  mov     rcx, [rsp+58h]; this
0x180036fcb  test    eax, eax
0x180036fcd  js      short loc_180037002
0x180036fcf  mov     rdi, [rsp+58h+var_18]
0x180036fd4  test    rbx, rbx
0x180036fd7  jz      short loc_180036FE2
0x180036fd9  mov     rcx, rbx; hLibModule
0x180036fdc  call    cs:__imp_FreeLibrary
0x180036fe2  mov     rax, rdi
0x180036fe5  mov     rcx, [rsp+58h+var_10]
0x180036fea  xor     rcx, rsp; StackCookie
0x180036fed  call    __security_check_cookie
0x180036ff2  mov     rbx, [rsp+58h+arg_10]
0x180036ff7  mov     rsi, [rsp+58h+arg_18]
0x180036ffc  add     rsp, 50h
0x180037000  pop     rdi
0x180037001  retn
0x180037002  mov     r9d, eax; char *
0x180037005  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x18003700c  mov     edx, 177h; void *
0x180037011  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180037017  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
