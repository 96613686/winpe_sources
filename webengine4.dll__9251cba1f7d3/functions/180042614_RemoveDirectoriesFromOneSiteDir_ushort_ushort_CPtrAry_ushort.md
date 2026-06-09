# RemoveDirectoriesFromOneSiteDir(ushort *,ushort *,CPtrAry<ushort *> *)

- ea: `0x180042614`
- end: `0x180042953`
- name: `?RemoveDirectoriesFromOneSiteDir@@YAJPEAG0PEAV?$CPtrAry@PEAG@@@Z`
- size: `831`
- prototype: `__int64 __fastcall(unsigned __int16 *Src, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x180042a58`

## callees

- `0x180002584`
- `0x180007824`
- `0x180012b30`
- `0x18003aba8`
- `0x180042614`
- `0x18004d350`
- `0x18004d690`
- `0x18004d754`
- `0x18004e168`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18004267a`
- `KERNEL32!lstrlenW` at `0x180042720`
- `KERNEL32!lstrlenW` at `0x18004272b`
- `KERNEL32!lstrlenW` at `0x1800428f6`
- `KERNEL32!lstrlenW` at `0x18004267a`
- `KERNEL32!lstrlenW` at `0x180042720`
- `KERNEL32!lstrlenW` at `0x18004272b`
- `KERNEL32!lstrlenW` at `0x1800428f6`
- `KERNEL32!RemoveDirectoryW` at `0x180042818`
- `KERNEL32!RemoveDirectoryW` at `0x1800428c4`
- `KERNEL32!RemoveDirectoryW` at `0x180042818`
- `KERNEL32!RemoveDirectoryW` at `0x1800428c4`
- `ucrtbase_clr0400!_wcsicmp` at `0x180042919`
- `ucrtbase_clr0400!_wcsicmp` at `0x180042919`
- `SHLWAPI!PathIsDirectoryEmptyW` at `0x1800427f2`
- `SHLWAPI!PathIsDirectoryEmptyW` at `0x180042899`
- `SHLWAPI!PathIsDirectoryEmptyW` at `0x1800427f2`
- `SHLWAPI!PathIsDirectoryEmptyW` at `0x180042899`
- `SHLWAPI!PathRemoveBackslashW` at `0x180042671`
- `SHLWAPI!PathRemoveBackslashW` at `0x180042671`
- `SHLWAPI!PathIsDirectoryW` at `0x1800427e5`
- `SHLWAPI!PathIsDirectoryW` at `0x180042888`
- `SHLWAPI!PathIsDirectoryW` at `0x1800427e5`
- `SHLWAPI!PathIsDirectoryW` at `0x180042888`

## string_xrefs

- `0x18004263c`: `RemoveDirectoriesFromOneSiteDir`
- `0x1800426b0`: `RemoveDirectoriesFromOneSiteDir`
- `0x1800427fc`: `Removing directory`
- `0x18004282b`: `Removing directory`
- `0x1800428aa`: `Removing directory`
- `0x1800428d7`: `Removing directory`
- `0x180042806`: `RemoveDirectory`
- `0x180042835`: `RemoveDirectory`
- `0x1800428b1`: `RemoveDirectory`
- `0x1800428e1`: `RemoveDirectory`

## pseudocode

```c
__int64 __fastcall RemoveDirectoriesFromOneSiteDir(unsigned __int16 *Src, unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int LastWin32Error; // edi
  WCHAR *v7; // rsi
  unsigned __int16 *v8; // rbp
  WCHAR *v9; // rax
  wchar_t *v10; // r14
  signed __int64 v12; // r14
  int v13; // ebx
  int v14; // ecx
  unsigned __int64 v15; // rbx
  unsigned __int16 *v16; // rax
  BOOL v17; // ebx
  BOOL v18; // ebx
  WCHAR *i; // rax
  wchar_t *String2; // [rsp+78h] [rbp+20h]

  LastWin32Error = 0;
  v7 = 0;
  v8 = 0;
  CSetupLogging::Log(1, "RemoveDirectoriesFromOneSiteDir", 0, "Removing site scripts dirs");
  v9 = DupStr(Src);
  String2 = v9;
  if ( !v9 )
  {
    LastWin32Error = -2147024882;
    v10 = 0;
    goto LABEL_6;
  }
  PathRemoveBackslashW(v9);
  if ( lstrlenW(a2) >= 260 )
  {
    XspLogEvent(0x8000042E);
LABEL_5:
    v10 = String2;
    goto LABEL_6;
  }
  v7 = DupStr(a2);
  if ( !v7 )
  {
LABEL_8:
    LastWin32Error = -2147024882;
    goto LABEL_5;
  }
  v12 = ((unsigned __int64)*a3 >> 2) - 1;
  if ( v12 >= 0 )
  {
    while ( 1 )
    {
      v13 = lstrlenW(*(LPCWSTR *)(*((_QWORD *)a3 + 1) + 8 * v12));
      v14 = v13 + lstrlenW(v7) + 2;
      if ( v14 < 260 )
      {
        v15 = v14;
        v16 = (unsigned __int16 *)MemAlloc(saturated_mul(v14, 2u));
        v8 = v16;
        if ( !v16 )
          goto LABEL_8;
        LastWin32Error = StringCchCopyW(v16, v15, v7);
        if ( LastWin32Error )
          goto LABEL_5;
        LastWin32Error = StringCchCatW(v8, v15, L"\\");
        if ( LastWin32Error )
          goto LABEL_5;
        LastWin32Error = StringCchCatW(v8, v15, *(const unsigned __int16 **)(*((_QWORD *)a3 + 1) + 8 * v12));
        if ( LastWin32Error )
          goto LABEL_5;
        if ( PathIsDirectoryW(v8) && PathIsDirectoryEmptyW(v8) )
        {
          CSetupLogging::Log(1, "RemoveDirectory", 0, "Removing directory");
          v17 = RemoveDirectoryW(v8);
          if ( !v17 )
            LastWin32Error = GetLastWin32Error();
          CSetupLogging::Log(LastWin32Error, "RemoveDirectory", 0, "Removing directory");
          if ( !v17 )
          {
            XspLogEvent(0x8000042E);
            break;
          }
        }
        MemFree(v8);
      }
      else
      {
        XspLogEvent(0x8000042E);
      }
      if ( --v12 < 0 )
      {
        v8 = 0;
        break;
      }
    }
  }
  v10 = String2;
  while ( _wcsicmp(v7, String2) && PathIsDirectoryW(v7) && PathIsDirectoryEmptyW(v7) )
  {
    CSetupLogging::Log(1, "RemoveDirectory", 0, "Removing directory");
    v18 = RemoveDirectoryW(v7);
    if ( !v18 )
      LastWin32Error = GetLastWin32Error();
    CSetupLogging::Log(LastWin32Error, "RemoveDirectory", 0, "Removing directory");
    if ( !v18 )
    {
      XspLogEvent(0x8000042E);
      break;
    }
    for ( i = &v7[lstrlenW(v7)]; *i != 92; --i )
      ;
    *i = 0;
  }
  MemFree(v7);
  v7 = 0;
  LastWin32Error = 0;
LABEL_6:
  CSetupLogging::Log(LastWin32Error, "RemoveDirectoriesFromOneSiteDir", 0, "Removing site scripts dirs");
  MemFree(v7);
  MemFree(v10);
  MemFree(v8);
  return LastWin32Error;
}

```

## disassembly

```asm
0x180042614  mov     [rsp+arg_0], rbx
0x180042619  mov     [rsp+arg_8], rbp
0x18004261e  push    rsi
0x18004261f  push    rdi
0x180042620  push    r13
0x180042622  push    r14
0x180042624  push    r15
0x180042626  sub     rsp, 30h
0x18004262a  mov     r13, r8
0x18004262d  lea     r9, aRemovingSiteSc; "Removing site scripts dirs"
0x180042634  mov     r15, rdx
0x180042637  mov     rbx, rcx
0x18004263a  xor     edi, edi
0x18004263c  lea     rdx, aRemovedirector_0; "RemoveDirectoriesFromOneSiteDir"
0x180042643  xor     r8d, r8d; unsigned int
0x180042646  xor     esi, esi
0x180042648  xor     ebp, ebp
0x18004264a  lea     ecx, [rdi+1]; int
0x18004264d  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x180042652  mov     rcx, rbx; Src
0x180042655  call    ?DupStr@@YAPEAGPEBG@Z; DupStr(ushort const *)
0x18004265a  mov     [rsp+58h+String2], rax
0x18004265f  test    rax, rax
0x180042662  jnz     short loc_18004266E
0x180042664  mov     edi, 8007000Eh
0x180042669  mov     r14, rax
0x18004266c  jmp     short loc_1800426A6
0x18004266e  mov     rcx, rax; pszPath
0x180042671  call    cs:__imp_PathRemoveBackslashW
0x180042677  mov     rcx, r15; lpString
0x18004267a  call    cs:__imp_lstrlenW
0x180042680  cmp     eax, 104h
0x180042685  jl      short loc_1800426EF
0x180042687  mov     r9d, 800700CEh
0x18004268d  lea     rdx, aS08x; "%s^%08x"
0x180042694  mov     r8, r15
0x180042697  mov     ecx, 8000042Eh; dwEventID
0x18004269c  call    XspLogEvent
0x1800426a1  mov     r14, [rsp+58h+String2]
0x1800426a6  lea     r9, aRemovingSiteSc; "Removing site scripts dirs"
0x1800426ad  xor     r8d, r8d; unsigned int
0x1800426b0  lea     rdx, aRemovedirector_0; "RemoveDirectoriesFromOneSiteDir"
0x1800426b7  mov     ecx, edi; int
0x1800426b9  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x1800426be  mov     rcx, rsi; lpMem
0x1800426c1  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800426c6  mov     rcx, r14; lpMem
0x1800426c9  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800426ce  mov     rcx, rbp; lpMem
0x1800426d1  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800426d6  mov     rbx, [rsp+58h+arg_0]
0x1800426db  mov     eax, edi
0x1800426dd  mov     rbp, [rsp+58h+arg_8]
0x1800426e2  add     rsp, 30h
0x1800426e6  pop     r15
0x1800426e8  pop     r14
0x1800426ea  pop     r13
0x1800426ec  pop     rdi
0x1800426ed  pop     rsi
0x1800426ee  retn
0x1800426ef  mov     rcx, r15; Src
0x1800426f2  call    ?DupStr@@YAPEAGPEBG@Z; DupStr(ushort const *)
0x1800426f7  mov     rsi, rax
0x1800426fa  test    rax, rax
0x1800426fd  jnz     short loc_180042706
0x1800426ff  mov     edi, 8007000Eh
0x180042704  jmp     short loc_1800426A1
0x180042706  mov     r14d, [r13+0]
0x18004270a  shr     r14, 2
0x18004270e  sub     r14, 1
0x180042712  js      loc_180042878
0x180042718  mov     rcx, [r13+8]
0x18004271c  mov     rcx, [rcx+r14*8]; lpString
0x180042720  call    cs:__imp_lstrlenW
0x180042726  mov     rcx, rsi; lpString
0x180042729  mov     ebx, eax
0x18004272b  call    cs:__imp_lstrlenW
0x180042731  lea     ecx, [rax+2]
0x180042734  add     ecx, ebx
0x180042736  cmp     ecx, 104h
0x18004273c  jl      short loc_180042767
0x18004273e  mov     r9, [r13+8]
0x180042742  lea     rdx, aSS08x_0; "%s\\%s^%08x"
0x180042749  mov     r8, r15
0x18004274c  mov     [rsp+58h+var_38], 800700CEh
0x180042754  mov     ecx, 8000042Eh; dwEventID
0x180042759  mov     r9, [r9+r14*8]
0x18004275d  call    XspLogEvent
0x180042762  jmp     loc_18004284F
0x180042767  movsxd  rbx, ecx
0x18004276a  mov     eax, 2
0x18004276f  mul     rbx
0x180042772  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180042779  cmovo   rax, rcx
0x18004277d  mov     rcx, rax; unsigned __int64
0x180042780  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180042785  mov     rbp, rax
0x180042788  test    rax, rax
0x18004278b  jz      loc_1800426FF
0x180042791  mov     r8, rsi; unsigned __int16 *
0x180042794  mov     rdx, rbx; unsigned __int64
0x180042797  mov     rcx, rax; unsigned __int16 *
0x18004279a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004279f  mov     edi, eax
0x1800427a1  test    eax, eax
0x1800427a3  jnz     loc_1800426A1
0x1800427a9  lea     r8, SubBlock; "\\"
0x1800427b0  mov     rdx, rbx; unsigned __int64
0x1800427b3  mov     rcx, rbp; unsigned __int16 *
0x1800427b6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800427bb  mov     edi, eax
0x1800427bd  test    eax, eax
0x1800427bf  jnz     loc_1800426A1
0x1800427c5  mov     r8, [r13+8]
0x1800427c9  mov     rdx, rbx; unsigned __int64
0x1800427cc  mov     rcx, rbp; unsigned __int16 *
0x1800427cf  mov     r8, [r8+r14*8]; unsigned __int16 *
0x1800427d3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800427d8  mov     edi, eax
0x1800427da  test    eax, eax
0x1800427dc  jnz     loc_1800426A1
0x1800427e2  mov     rcx, rbp; pszPath
0x1800427e5  call    cs:__imp_PathIsDirectoryW
0x1800427eb  test    eax, eax
0x1800427ed  jz      short loc_180042847
0x1800427ef  mov     rcx, rbp; pszPath
0x1800427f2  call    cs:__imp_PathIsDirectoryEmptyW
0x1800427f8  test    eax, eax
0x1800427fa  jz      short loc_180042847
0x1800427fc  lea     r9, aRemovingDirect; "Removing directory"
0x180042803  xor     r8d, r8d; unsigned int
0x180042806  lea     rdx, aRemovedirector; "RemoveDirectory"
0x18004280d  lea     ecx, [rdi+1]; int
0x180042810  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x180042815  mov     rcx, rbp; lpPathName
0x180042818  call    cs:__imp_RemoveDirectoryW
0x18004281e  mov     ebx, eax
0x180042820  test    eax, eax
0x180042822  jnz     short loc_18004282B
0x180042824  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180042829  mov     edi, eax
0x18004282b  lea     r9, aRemovingDirect; "Removing directory"
0x180042832  xor     r8d, r8d; unsigned int
0x180042835  lea     rdx, aRemovedirector; "RemoveDirectory"
0x18004283c  mov     ecx, edi; int
0x18004283e  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x180042843  test    ebx, ebx
0x180042845  jz      short loc_180042861
0x180042847  mov     rcx, rbp; lpMem
0x18004284a  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18004284f  sub     r14, 1
0x180042853  jns     loc_180042718
0x180042859  xor     r15d, r15d
0x18004285c  mov     ebp, r15d
0x18004285f  jmp     short loc_18004287B
0x180042861  mov     r9d, edi
0x180042864  lea     rdx, aS08x; "%s^%08x"
0x18004286b  mov     r8, rbp
0x18004286e  mov     ecx, 8000042Eh; dwEventID
0x180042873  call    XspLogEvent
0x180042878  xor     r15d, r15d
0x18004287b  mov     r14, [rsp+58h+String2]
0x180042880  jmp     loc_180042913
0x180042885  mov     rcx, rsi; pszPath
0x180042888  call    cs:__imp_PathIsDirectoryW
0x18004288e  test    eax, eax
0x180042890  jz      loc_180042940
0x180042896  mov     rcx, rsi; pszPath
0x180042899  call    cs:__imp_PathIsDirectoryEmptyW
0x18004289f  test    eax, eax
0x1800428a1  jz      loc_180042940
0x1800428a7  xor     r8d, r8d; unsigned int
0x1800428aa  lea     r9, aRemovingDirect; "Removing directory"
0x1800428b1  lea     rdx, aRemovedirector; "RemoveDirectory"
0x1800428b8  lea     ecx, [r8+1]; int
0x1800428bc  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x1800428c1  mov     rcx, rsi; lpPathName
0x1800428c4  call    cs:__imp_RemoveDirectoryW
0x1800428ca  mov     ebx, eax
0x1800428cc  test    eax, eax
0x1800428ce  jnz     short loc_1800428D7
0x1800428d0  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800428d5  mov     edi, eax
0x1800428d7  lea     r9, aRemovingDirect; "Removing directory"
0x1800428de  xor     r8d, r8d; unsigned int
0x1800428e1  lea     rdx, aRemovedirector; "RemoveDirectory"
0x1800428e8  mov     ecx, edi; int
0x1800428ea  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x1800428ef  test    ebx, ebx
0x1800428f1  jz      short loc_180042929
0x1800428f3  mov     rcx, rsi; lpString
0x1800428f6  call    cs:__imp_lstrlenW
0x1800428fc  movsxd  rcx, eax
0x1800428ff  lea     rax, [rsi+rcx*2]
0x180042903  jmp     short loc_180042909
0x180042905  sub     rax, 2
0x180042909  cmp     word ptr [rax], 5Ch ; '\'
0x18004290d  jnz     short loc_180042905
0x18004290f  mov     [rax], r15w
0x180042913  mov     rdx, r14; String2
0x180042916  mov     rcx, rsi; String1
0x180042919  call    cs:__imp__wcsicmp
0x18004291f  test    eax, eax
0x180042921  jnz     loc_180042885
0x180042927  jmp     short loc_180042940
0x180042929  mov     r9d, edi
0x18004292c  lea     rdx, aS08; "%s^%08"
0x180042933  mov     r8, rsi
0x180042936  mov     ecx, 8000042Eh; dwEventID
0x18004293b  call    XspLogEvent
0x180042940  mov     rcx, rsi; lpMem
0x180042943  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180042948  mov     rsi, r15
0x18004294b  mov     edi, r15d
0x18004294e  jmp     loc_1800426A6
```
