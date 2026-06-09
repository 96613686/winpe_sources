# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x1400067c8`
- end: `0x1400068d3`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `267`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x140007ea8`

## callees

- `0x1400067c8`
- `0x140009c74`
- `0x14000a170`
- `0x14000a1b8`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400068a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400068a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006867`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006867`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140006810`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140006810`

## string_xrefs

- `0x14000685d`: `DllGetSessionForPinky`
- `0x140006848`: `OneCore\Internal\Enduser\inc\UndockedUpdateStack.hpp`

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
    (unsigned int)"OneCore\\Internal\\Enduser\\inc\\UndockedUpdateStack.hpp",
    (const char *)(Library == 0),
    (bool)"Error loading library %s",
    v3);
  ProcAddress = GetProcAddress(Library, "DllGetSessionForPinky");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x173,
      (unsigned int)"OneCore\\Internal\\Enduser\\inc\\UndockedUpdateStack.hpp",
      v7);
  v13 = 0;
  v8 = ((__int64 (__fastcall *)(__int64 *, __int64))ProcAddress)(&v13, a2);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"OneCore\\Internal\\Enduser\\inc\\UndockedUpdateStack.hpp",
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
0x1400067c8  push    rbx
0x1400067ca  push    rsi
0x1400067cb  push    rdi
0x1400067cc  sub     rsp, 30h
0x1400067d0  mov     rsi, rdx
0x1400067d3  mov     rbx, rcx
0x1400067d6  mov     [rsp+48h+arg_0], 0
0x1400067de  test    rdx, rdx
0x1400067e1  jz      short loc_1400067F0
0x1400067e3  mov     eax, [rdx+0Ch]
0x1400067e6  shr     eax, 2
0x1400067e9  not     eax
0x1400067eb  and     eax, 1
0x1400067ee  jmp     short loc_1400067F5
0x1400067f0  mov     eax, 1
0x1400067f5  shl     eax, 7
0x1400067f8  lea     r8d, [rax+8]; dwFlags
0x1400067fc  mov     [rsp+48h+arg_0], 2
0x140006804  cmp     qword ptr [rcx+18h], 7
0x140006809  jbe     short loc_14000680E
0x14000680b  mov     rcx, [rcx]; lpLibFileName
0x14000680e  xor     edx, edx; hFile
0x140006810  call    cs:__imp_LoadLibraryExW
0x140006816  mov     rdi, rax
0x140006819  mov     [rsp+48h+arg_10], rax
0x14000681e  cmp     qword ptr [rbx+18h], 7
0x140006823  jbe     short loc_140006828
0x140006825  mov     rbx, [rbx]
0x140006828  test    rdi, rdi
0x14000682b  setz    al
0x14000682e  mov     rcx, [rsp+48h]; this
0x140006833  mov     [rsp+48h+var_20], rbx; char *
0x140006838  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x14000683f  mov     qword ptr [rsp+48h+var_28], rdx; int
0x140006844  movzx   r9d, al; char *
0x140006848  lea     rbx, aOnecoreInterna_1; "OneCore\\Internal\\Enduser\\inc\\Undock"...
0x14000684f  mov     r8, rbx; unsigned int
0x140006852  mov     edx, 164h; void *
0x140006857  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x14000685c  nop
0x14000685d  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x140006864  mov     rcx, rdi; hModule
0x140006867  call    cs:__imp_GetProcAddress
0x14000686d  mov     rcx, [rsp+48h]; this
0x140006872  test    rax, rax
0x140006875  jz      short loc_1400068C5
0x140006877  mov     [rsp+48h+arg_8], 0
0x140006880  mov     rdx, rsi
0x140006883  lea     rcx, [rsp+48h+arg_8]
0x140006888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000688d  mov     rcx, [rsp+48h]; this
0x140006892  test    eax, eax
0x140006894  js      short loc_1400068B4
0x140006896  mov     rbx, [rsp+48h+arg_8]
0x14000689b  test    rdi, rdi
0x14000689e  jz      short loc_1400068A9
0x1400068a0  mov     rcx, rdi; hLibModule
0x1400068a3  call    cs:__imp_FreeLibrary
0x1400068a9  mov     rax, rbx
0x1400068ac  add     rsp, 30h
0x1400068b0  pop     rdi
0x1400068b1  pop     rsi
0x1400068b2  pop     rbx
0x1400068b3  retn
0x1400068b4  mov     r9d, eax; char *
0x1400068b7  mov     r8, rbx; unsigned int
0x1400068ba  mov     edx, 177h; void *
0x1400068bf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400068c5  mov     r8, rbx; unsigned int
0x1400068c8  mov     edx, 173h; void *
0x1400068cd  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
