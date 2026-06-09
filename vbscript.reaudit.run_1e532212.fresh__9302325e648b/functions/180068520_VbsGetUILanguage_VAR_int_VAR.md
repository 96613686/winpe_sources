# VbsGetUILanguage(VAR *,int,VAR *)

- ea: `0x180068520`
- end: `0x1800685a2`
- name: `?VbsGetUILanguage@@YAJPEAVVAR@@H0@Z`
- size: `130`
- prototype: `__int64 __fastcall(struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180068520`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetUserDefaultLangID` at `0x180068582`
- `KERNEL32!GetUserDefaultLangID` at `0x180068582`
- `KERNEL32!LoadLibraryExW` at `0x18006854c`
- `KERNEL32!LoadLibraryExW` at `0x18006854c`
- `KERNEL32!FreeLibrary` at `0x18006858f`
- `KERNEL32!FreeLibrary` at `0x18006858f`
- `KERNEL32!GetProcAddress` at `0x180068570`
- `KERNEL32!GetProcAddress` at `0x180068570`

## string_xrefs

- `0x18006853f`: `kernel32.dll`

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
0x180068520  mov     [rsp+arg_0], rbx
0x180068525  push    rdi
0x180068526  sub     rsp, 20h
0x18006852a  xor     eax, eax
0x18006852c  mov     rdi, rcx
0x18006852f  mov     [rcx], ax
0x180068532  test    edx, edx
0x180068534  jz      short loc_18006853D
0x180068536  mov     eax, 800A01C2h
0x18006853b  jmp     short loc_180068597
0x18006853d  xor     edx, edx; hFile
0x18006853f  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180068546  mov     r8d, 800h; dwFlags
0x18006854c  call    cs:__imp_LoadLibraryExW
0x180068552  mov     rbx, rax
0x180068555  test    rax, rax
0x180068558  jnz     short loc_180068561
0x18006855a  mov     eax, 800A0007h
0x18006855f  jmp     short loc_180068597
0x180068561  lea     rdx, aGetuserdefault; "GetUserDefaultUILanguage"
0x180068568  mov     word ptr [rdi], 2
0x18006856d  mov     rcx, rbx; hModule
0x180068570  call    cs:__imp_GetProcAddress
0x180068576  test    rax, rax
0x180068579  jz      short loc_180068582
0x18006857b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068580  jmp     short loc_180068588
0x180068582  call    cs:__imp_GetUserDefaultLangID
0x180068588  mov     rcx, rbx; hLibModule
0x18006858b  mov     [rdi+8], ax
0x18006858f  call    cs:__imp_FreeLibrary
0x180068595  xor     eax, eax
0x180068597  mov     rbx, [rsp+28h+arg_0]
0x18006859c  add     rsp, 20h
0x1800685a0  pop     rdi
0x1800685a1  retn
```
