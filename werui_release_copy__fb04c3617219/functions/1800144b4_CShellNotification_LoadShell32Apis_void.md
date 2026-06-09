# CShellNotification::LoadShell32Apis(void)

- ea: `0x1800144b4`
- end: `0x1800145b5`
- name: `?LoadShell32Apis@CShellNotification@@AEAAJXZ`
- size: `257`
- prototype: `__int64 __fastcall(CShellNotification *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001405c`

## callees

- `0x180003604`
- `0x180003fc4`
- `0x180003fe4`
- `0x18000bebc`
- `0x1800144b4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800144fc`
- `KERNEL32!GetLastError` at `0x180014556`
- `KERNEL32!GetLastError` at `0x1800144fc`
- `KERNEL32!GetLastError` at `0x180014556`
- `KERNEL32!GetProcAddress` at `0x180014548`
- `KERNEL32!GetProcAddress` at `0x180014548`
- `KERNEL32!LoadLibraryExW` at `0x1800144ec`
- `KERNEL32!LoadLibraryExW` at `0x1800144ec`

## string_xrefs

- `0x1800144e3`: `shell32.dll`

## pseudocode

```c
__int64 __fastcall CShellNotification::LoadShell32Apis(CShellNotification *this)
{
  char *v1; // rdi
  HMODULE Library; // rax
  DWORD LastError; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  FARPROC ProcAddress; // rsi
  DWORD v9; // eax
  HMODULE v11; // [rsp+30h] [rbp+8h] BYREF

  v1 = (char *)this + 1072;
  v11 = 0;
  if ( *((_QWORD *)this + 134) )
    goto LABEL_12;
  Library = LoadLibraryExW(L"shell32.dll", 0, 0);
  v11 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v5 = ERROR_HR_FROM_WIN32(LastError);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v7 = 13;
LABEL_6:
      WPP_SF_d(v6[2], v7, WPP_721966d903033a5712e56ad66803da37_Traceguids, v5);
      goto LABEL_13;
    }
    goto LABEL_13;
  }
  ProcAddress = GetProcAddress(Library, "Shell_NotifyIconW");
  if ( ProcAddress )
  {
    tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::operator=(
      v1,
      &v11);
    *((_QWORD *)this + 135) = ProcAddress;
LABEL_12:
    v5 = 0;
    goto LABEL_13;
  }
  v9 = GetLastError();
  v5 = ERROR_HR_FROM_WIN32(v9);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 14;
    goto LABEL_6;
  }
LABEL_13:
  tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v11);
  return v5;
}

```

## disassembly

```asm
0x1800144b4  mov     [rsp+arg_8], rbx
0x1800144b9  mov     [rsp+arg_10], rsi
0x1800144be  push    rdi
0x1800144bf  sub     rsp, 20h
0x1800144c3  lea     rdi, [rcx+430h]
0x1800144ca  mov     [rsp+28h+arg_0], 0
0x1800144d3  cmp     qword ptr [rdi], 0
0x1800144d7  mov     rbx, rcx
0x1800144da  jnz     loc_180014597
0x1800144e0  xor     r8d, r8d; dwFlags
0x1800144e3  lea     rcx, aShell32Dll_0; "shell32.dll"
0x1800144ea  xor     edx, edx; hFile
0x1800144ec  call    cs:__imp_LoadLibraryExW
0x1800144f2  mov     [rsp+28h+arg_0], rax
0x1800144f7  test    rax, rax
0x1800144fa  jnz     short loc_18001453E
0x1800144fc  call    cs:__imp_GetLastError
0x180014502  mov     ecx, eax; unsigned int
0x180014504  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180014509  mov     ebx, eax
0x18001450b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014512  lea     rax, WPP_GLOBAL_Control
0x180014519  cmp     rcx, rax
0x18001451c  jz      short loc_180014599
0x18001451e  test    byte ptr [rcx+1Ch], 4
0x180014522  jz      short loc_180014599
0x180014524  mov     edx, 0Dh
0x180014529  mov     rcx, [rcx+10h]
0x18001452d  lea     r8, WPP_721966d903033a5712e56ad66803da37_Traceguids
0x180014534  mov     r9d, ebx
0x180014537  call    WPP_SF_d
0x18001453c  jmp     short loc_180014599
0x18001453e  lea     rdx, aShellNotifyico; "Shell_NotifyIconW"
0x180014545  mov     rcx, rax; hModule
0x180014548  call    cs:__imp_GetProcAddress
0x18001454e  mov     rsi, rax
0x180014551  test    rax, rax
0x180014554  jnz     short loc_180014583
0x180014556  call    cs:__imp_GetLastError
0x18001455c  mov     ecx, eax; unsigned int
0x18001455e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180014563  mov     ebx, eax
0x180014565  mov     rcx, cs:WPP_GLOBAL_Control
0x18001456c  lea     rax, WPP_GLOBAL_Control
0x180014573  cmp     rcx, rax
0x180014576  jz      short loc_180014599
0x180014578  test    byte ptr [rcx+1Ch], 1
0x18001457c  jz      short loc_180014599
0x18001457e  lea     edx, [rsi+0Eh]
0x180014581  jmp     short loc_180014529
0x180014583  lea     rdx, [rsp+28h+arg_0]
0x180014588  mov     rcx, rdi
0x18001458b  call    ??4?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::operator=(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> &&)
0x180014590  mov     [rbx+438h], rsi
0x180014597  xor     ebx, ebx
0x180014599  lea     rcx, [rsp+28h+arg_0]
0x18001459e  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x1800145a3  mov     rsi, [rsp+28h+arg_10]
0x1800145a8  mov     eax, ebx
0x1800145aa  mov     rbx, [rsp+28h+arg_8]
0x1800145af  add     rsp, 20h
0x1800145b3  pop     rdi
0x1800145b4  retn
```
