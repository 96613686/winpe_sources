# VbsGetUILanguage(VAR *,int,VAR *)

- ea: `0x18006a5d0`
- end: `0x18006a66b`
- name: `?VbsGetUILanguage@@YAJPEAVVAR@@H0@Z`
- size: `155`
- prototype: `__int64 __fastcall(struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18006a5d0`
- `0x18007a010`

## import_xrefs

- `KERNEL32!GetUserDefaultLangID` at `0x18006a63e`
- `KERNEL32!GetUserDefaultLangID` at `0x18006a63e`
- `KERNEL32!LoadLibraryExW` at `0x18006a5fc`
- `KERNEL32!LoadLibraryExW` at `0x18006a5fc`
- `KERNEL32!FreeLibrary` at `0x18006a651`
- `KERNEL32!FreeLibrary` at `0x18006a651`
- `KERNEL32!GetProcAddress` at `0x18006a626`
- `KERNEL32!GetProcAddress` at `0x18006a626`

## string_xrefs

- `0x18006a5ef`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall VbsGetUILanguage(struct VAR *a1, int a2, struct VAR *a3)
{
  HMODULE Library; // rax
  HMODULE v6; // rbx
  __int64 (*ProcAddress)(void); // rax
  LANGID UserDefaultLangID; // ax

  *(_WORD *)a1 = 0;
  if ( a2 )
    return 2148139458LL;
  Library = LoadLibraryExW(L"kernel32.dll", 0, 0x800u);
  v6 = Library;
  if ( !Library )
    return 2148139015LL;
  *(_WORD *)a1 = 2;
  ProcAddress = GetProcAddress(Library, "GetUserDefaultUILanguage");
  if ( ProcAddress )
    UserDefaultLangID = ProcAddress();
  else
    UserDefaultLangID = GetUserDefaultLangID();
  *((_WORD *)a1 + 4) = UserDefaultLangID;
  FreeLibrary(v6);
  return 0;
}

```

## disassembly

```asm
0x18006a5d0  mov     [rsp+arg_0], rbx
0x18006a5d5  push    rdi
0x18006a5d6  sub     rsp, 20h
0x18006a5da  xor     eax, eax
0x18006a5dc  mov     rdi, rcx
0x18006a5df  mov     [rcx], ax
0x18006a5e2  test    edx, edx
0x18006a5e4  jz      short loc_18006A5ED
0x18006a5e6  mov     eax, 800A01C2h
0x18006a5eb  jmp     short loc_18006A65F
0x18006a5ed  xor     edx, edx; hFile
0x18006a5ef  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18006a5f6  mov     r8d, 800h; dwFlags
0x18006a5fc  call    cs:__imp_LoadLibraryExW
0x18006a603  nop     dword ptr [rax+rax+00h]
0x18006a608  mov     rbx, rax
0x18006a60b  test    rax, rax
0x18006a60e  jnz     short loc_18006A617
0x18006a610  mov     eax, 800A0007h
0x18006a615  jmp     short loc_18006A65F
0x18006a617  lea     rdx, aGetuserdefault; "GetUserDefaultUILanguage"
0x18006a61e  mov     word ptr [rdi], 2
0x18006a623  mov     rcx, rbx; hModule
0x18006a626  call    cs:__imp_GetProcAddress
0x18006a62d  nop     dword ptr [rax+rax+00h]
0x18006a632  test    rax, rax
0x18006a635  jz      short loc_18006A63E
0x18006a637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a63c  jmp     short loc_18006A64A
0x18006a63e  call    cs:__imp_GetUserDefaultLangID
0x18006a645  nop     dword ptr [rax+rax+00h]
0x18006a64a  mov     rcx, rbx; hLibModule
0x18006a64d  mov     [rdi+8], ax
0x18006a651  call    cs:__imp_FreeLibrary
0x18006a658  nop     dword ptr [rax+rax+00h]
0x18006a65d  xor     eax, eax
0x18006a65f  mov     rbx, [rsp+28h+arg_0]
0x18006a664  add     rsp, 20h
0x18006a668  pop     rdi
0x18006a669  retn
```
