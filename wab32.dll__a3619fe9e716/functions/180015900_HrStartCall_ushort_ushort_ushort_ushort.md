# HrStartCall(ushort *,ushort *,ushort *,ushort *)

- ea: `0x180015900`
- end: `0x1800159b7`
- name: `?HrStartCall@@YAJPEAG000@Z`
- size: `183`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180014fbc`

## callees

- `0x180015900`
- `0x18001dcb8`
- `0x180033ae0`
- `0x180093010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18001592d`
- `KERNEL32!LoadLibraryW` at `0x18001592d`
- `KERNEL32!FreeLibrary` at `0x18001599c`
- `KERNEL32!FreeLibrary` at `0x18001599c`
- `KERNEL32!GetProcAddress` at `0x180015945`
- `KERNEL32!GetProcAddress` at `0x180015945`

## string_xrefs

- `0x180015921`: `tapi32.dll`

## pseudocode

```c
__int64 __fastcall HrStartCall(LPCWCH lpWideCharStr, unsigned __int16 *a2, unsigned __int16 *a3, unsigned __int16 *a4)
{
  unsigned int v6; // ebx
  HMODULE LibraryW; // rax
  HMODULE v8; // rdi
  FARPROC ProcAddress; // rsi
  void *v10; // rbx
  void *v12; // [rsp+58h] [rbp+10h] BYREF
  void *v13; // [rsp+68h] [rbp+20h] BYREF

  v13 = a4;
  v12 = a2;
  v6 = -2147467259;
  LibraryW = LoadLibraryW(L"tapi32.dll");
  v8 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "tapiRequestMakeCall");
    if ( ProcAddress )
    {
      v13 = ConvertWtoA(lpWideCharStr);
      v10 = v13;
      v12 = ConvertWtoA(a3);
      v6 = ((__int64 (__fastcall *)(void *, _QWORD, void *, _QWORD))ProcAddress)(v10, 0, v12, 0);
      LocalFreeAndNull(&v13);
      LocalFreeAndNull(&v12);
    }
    FreeLibrary(v8);
  }
  return v6;
}

```

## disassembly

```asm
0x180015900  mov     rax, rsp
0x180015903  mov     [rax+8], rbx
0x180015907  mov     [rax+18h], rbp
0x18001590b  mov     [rax+20h], r9
0x18001590f  mov     [rax+10h], rdx
0x180015913  push    rsi
0x180015914  push    rdi
0x180015915  push    r14
0x180015917  sub     rsp, 30h
0x18001591b  mov     r14, rcx
0x18001591e  mov     rbp, r8
0x180015921  lea     rcx, aTapi32Dll; "tapi32.dll"
0x180015928  mov     ebx, 80004005h
0x18001592d  call    cs:__imp_LoadLibraryW
0x180015933  mov     rdi, rax
0x180015936  test    rax, rax
0x180015939  jz      short loc_1800159A2
0x18001593b  lea     rdx, aTapirequestmak; "tapiRequestMakeCall"
0x180015942  mov     rcx, rax; hModule
0x180015945  call    cs:__imp_GetProcAddress
0x18001594b  mov     rsi, rax
0x18001594e  test    rax, rax
0x180015951  jz      short loc_180015999
0x180015953  mov     rcx, r14; lpWideCharStr
0x180015956  call    ?ConvertWtoA@@YAPEADPEBG@Z; ConvertWtoA(ushort const *)
0x18001595b  mov     rcx, rbp; lpWideCharStr
0x18001595e  mov     [rsp+48h+arg_18], rax
0x180015963  mov     rbx, rax
0x180015966  call    ?ConvertWtoA@@YAPEADPEBG@Z; ConvertWtoA(ushort const *)
0x18001596b  mov     [rsp+48h+arg_8], rax
0x180015970  mov     r8, rax
0x180015973  mov     rax, rsi
0x180015976  xor     r9d, r9d
0x180015979  xor     edx, edx
0x18001597b  mov     rcx, rbx
0x18001597e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015983  lea     rcx, [rsp+48h+arg_18]; void **
0x180015988  mov     ebx, eax
0x18001598a  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x18001598f  lea     rcx, [rsp+48h+arg_8]; void **
0x180015994  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x180015999  mov     rcx, rdi; hLibModule
0x18001599c  call    cs:__imp_FreeLibrary
0x1800159a2  mov     rbp, [rsp+48h+arg_10]
0x1800159a7  mov     eax, ebx
0x1800159a9  mov     rbx, [rsp+48h+arg_0]
0x1800159ae  add     rsp, 30h
0x1800159b2  pop     r14
0x1800159b4  pop     rdi
0x1800159b5  pop     rsi
0x1800159b6  retn
```
