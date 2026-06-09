# CHost::InitWldp(void *)

- ea: `0x1400090c8`
- end: `0x140009196`
- name: `?InitWldp@CHost@@IEAAJPEAX@Z`
- size: `206`
- prototype: `__int64 __fastcall(CHost *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000757c`

## callees

- `0x1400090c8`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140009129`
- `KERNEL32!GetLastError` at `0x140009129`
- `KERNEL32!GetProcAddress` at `0x1400090fe`
- `KERNEL32!GetProcAddress` at `0x14000911e`
- `KERNEL32!GetProcAddress` at `0x1400090fe`
- `KERNEL32!GetProcAddress` at `0x14000911e`
- `KERNEL32!FreeLibrary` at `0x14000914a`
- `KERNEL32!FreeLibrary` at `0x14000914a`
- `KERNEL32!LoadLibraryExW` at `0x1400090e6`
- `KERNEL32!LoadLibraryExW` at `0x1400090e6`

## string_xrefs

- `0x1400090d9`: `WLDP.DLL`

## pseudocode

```c
__int64 __fastcall CHost::InitWldp(CHost *this, void *a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rdi
  FARPROC ProcAddress; // rbp
  FARPROC v7; // rax
  signed int LastError; // eax
  signed int v9; // ebx
  bool v11; // zf
  int v12; // [rsp+70h] [rbp+18h] BYREF

  Library = LoadLibraryExW(L"WLDP.DLL", 0, 0x800u);
  v5 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WldpIsClassInApprovedList");
    if ( ProcAddress )
    {
      v12 = 0;
      v7 = GetProcAddress(v5, "WldpCanExecuteFile");
      if ( v7 )
      {
        v9 = ((__int64 (__fastcall *)(__int64 *, _QWORD, void *, _QWORD, int *))v7)(
               WLDP_HOST_WINDOWS_SCRIPT_HOST,
               0,
               a2,
               0,
               &v12);
        if ( v9 >= 0 )
        {
          *((_QWORD *)this + 2) = v5;
          v11 = v12 == 1;
          *((_QWORD *)this + 3) = ProcAddress;
          *((_DWORD *)this + 2) = !v11;
          return (unsigned int)v9;
        }
        goto LABEL_8;
      }
    }
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( v9 < 0 && v5 )
LABEL_8:
    FreeLibrary(v5);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400090c8  push    rbx
0x1400090ca  push    rbp
0x1400090cb  push    rsi
0x1400090cc  push    rdi
0x1400090cd  sub     rsp, 38h
0x1400090d1  mov     rbx, rdx
0x1400090d4  mov     rsi, rcx
0x1400090d7  xor     edx, edx; hFile
0x1400090d9  lea     rcx, LibFileName; "WLDP.DLL"
0x1400090e0  mov     r8d, 800h; dwFlags
0x1400090e6  call    cs:__imp_LoadLibraryExW
0x1400090ec  mov     rdi, rax
0x1400090ef  test    rax, rax
0x1400090f2  jz      short loc_140009129
0x1400090f4  lea     rdx, aWldpisclassina; "WldpIsClassInApprovedList"
0x1400090fb  mov     rcx, rax; hModule
0x1400090fe  call    cs:__imp_GetProcAddress
0x140009104  mov     rbp, rax
0x140009107  test    rax, rax
0x14000910a  jz      short loc_140009129
0x14000910c  lea     rdx, aWldpcanexecute; "WldpCanExecuteFile"
0x140009113  mov     [rsp+58h+arg_10], 0
0x14000911b  mov     rcx, rdi; hModule
0x14000911e  call    cs:__imp_GetProcAddress
0x140009124  test    rax, rax
0x140009127  jnz     short loc_14000915B
0x140009129  call    cs:__imp_GetLastError
0x14000912f  mov     ebx, eax
0x140009131  test    eax, eax
0x140009133  jle     short loc_14000913E
0x140009135  movzx   ebx, ax
0x140009138  or      ebx, 80070000h
0x14000913e  test    ebx, ebx
0x140009140  jns     short loc_140009150
0x140009142  test    rdi, rdi
0x140009145  jz      short loc_140009150
0x140009147  mov     rcx, rdi; hLibModule
0x14000914a  call    cs:__imp_FreeLibrary
0x140009150  mov     eax, ebx
0x140009152  add     rsp, 38h
0x140009156  pop     rdi
0x140009157  pop     rsi
0x140009158  pop     rbp
0x140009159  pop     rbx
0x14000915a  retn
0x14000915b  lea     rcx, [rsp+58h+arg_10]
0x140009160  xor     r9d, r9d
0x140009163  mov     [rsp+58h+var_38], rcx
0x140009168  mov     r8, rbx
0x14000916b  lea     rcx, WLDP_HOST_WINDOWS_SCRIPT_HOST
0x140009172  xor     edx, edx
0x140009174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009179  mov     ebx, eax
0x14000917b  test    eax, eax
0x14000917d  js      short loc_140009147
0x14000917f  xor     ecx, ecx
0x140009181  mov     [rsi+10h], rdi
0x140009185  cmp     [rsp+58h+arg_10], 1
0x14000918a  mov     [rsi+18h], rbp
0x14000918e  setnz   cl
0x140009191  mov     [rsi+8], ecx
0x140009194  jmp     short loc_140009150
```
