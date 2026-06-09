# CopyScriptFilesToSites(ushort *,CPtrAry<ushort *> *,ushort const *)

- ea: `0x180041488`
- end: `0x180041723`
- name: `?CopyScriptFilesToSites@@YAJPEAGPEAV?$CPtrAry@PEAG@@PEBG@Z`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x1800418cc`

## callees

- `0x180002584`
- `0x180007824`
- `0x180012b30`
- `0x18003aba8`
- `0x18003abe4`
- `0x180041488`
- `0x18004d350`
- `0x18004d754`
- `0x18004d7d4`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x1800414ed`
- `KERNEL32!lstrlenW` at `0x1800414f8`
- `KERNEL32!lstrlenW` at `0x180041587`
- `KERNEL32!lstrlenW` at `0x180041594`
- `KERNEL32!lstrlenW` at `0x180041620`
- `KERNEL32!lstrlenW` at `0x180041632`
- `KERNEL32!lstrlenW` at `0x1800414ed`
- `KERNEL32!lstrlenW` at `0x1800414f8`
- `KERNEL32!lstrlenW` at `0x180041587`
- `KERNEL32!lstrlenW` at `0x180041594`
- `KERNEL32!lstrlenW` at `0x180041620`
- `KERNEL32!lstrlenW` at `0x180041632`
- `KERNEL32!CopyFileW` at `0x180041645`
- `KERNEL32!CopyFileW` at `0x180041645`

## string_xrefs

- `0x1800414ad`: `Copy the client side script or web admin files to a list of directories.`
- `0x1800416e1`: `Copy the client side script or web admin files to a list of directories.`
- `0x1800414bc`: `CopyScriptFilesToSites`
- `0x1800416eb`: `CopyScriptFilesToSites`
- `0x180041665`: `Copying file to :`
- `0x18004167c`: `Copying file to :`
- `0x18004166c`: `CopyFile`
- `0x18004168b`: `CopyFile`

## pseudocode

```c
__int64 __fastcall CopyScriptFilesToSites(const WCHAR *a1, _DWORD *a2, const unsigned __int16 *a3)
{
  const WCHAR *v3; // rbp
  _DWORD *v4; // rdi
  unsigned int LastWin32Error; // ebx
  unsigned __int16 *v6; // rsi
  unsigned __int16 *v7; // r13
  int v8; // r14d
  __int64 v9; // r12
  const WCHAR *v10; // r15
  int v11; // ebx
  unsigned __int64 v12; // rbp
  SIZE_T v13; // rax
  unsigned __int16 *v14; // rax
  int v15; // ebx
  unsigned __int64 v16; // rbp
  SIZE_T v17; // rax
  unsigned __int16 *v18; // rax
  const unsigned __int16 *v19; // rdi

  v3 = a3;
  v4 = a2;
  LastWin32Error = 0;
  v6 = 0;
  v7 = 0;
  CSetupLogging::Log(
    1,
    "CopyScriptFilesToSites",
    0,
    "Copy the client side script or web admin files to a list of directories.");
  v8 = 0;
  if ( (*v4 & 0xFFFFFFFC) != 0 )
  {
    v9 = 0;
    while ( 1 )
    {
      v10 = *(const WCHAR **)(v9 + *((_QWORD *)v4 + 1));
      v11 = lstrlenW(v10);
      v12 = v11 + lstrlenW(v3) + 2;
      v13 = 2 * v12;
      if ( !is_mul_ok(v12, 2u) )
        v13 = -1;
      v14 = (unsigned __int16 *)MemReAlloc(v6, v13);
      if ( !v14 )
        goto LABEL_23;
      v6 = v14;
      LastWin32Error = StringCchCopyW(v14, v12, a3);
      if ( LastWin32Error )
        goto LABEL_24;
      LastWin32Error = StringCchCatW(v6, v12, L"\\");
      if ( LastWin32Error )
        goto LABEL_24;
      LastWin32Error = StringCchCatW(v6, v12, v10);
      if ( LastWin32Error )
        goto LABEL_24;
      v15 = lstrlenW(v10);
      v16 = v15 + lstrlenW(a1) + 2;
      v17 = 2 * v16;
      if ( !is_mul_ok(v16, 2u) )
        v17 = -1;
      v18 = (unsigned __int16 *)MemReAlloc(v7, v17);
      v19 = v18;
      if ( !v18 )
      {
LABEL_23:
        LastWin32Error = -2147024882;
        goto LABEL_24;
      }
      v7 = v18;
      LastWin32Error = StringCchCopyW(v18, v16, a1);
      if ( LastWin32Error )
        goto LABEL_24;
      LastWin32Error = StringCchCatW(v7, v16, L"\\");
      if ( LastWin32Error )
        goto LABEL_24;
      LastWin32Error = StringCchCatW(v7, v16, v10);
      if ( LastWin32Error )
        goto LABEL_24;
      if ( lstrlenW(v6) >= 260 || lstrlenW(v7) >= 260 )
        break;
      if ( !CopyFileW(v6, v7, 0) )
      {
        LastWin32Error = GetLastWin32Error();
        goto LABEL_20;
      }
LABEL_21:
      v4 = a2;
      ++v8;
      v3 = a3;
      v9 += 8;
      if ( v8 >= *a2 >> 2 )
        goto LABEL_24;
    }
    LastWin32Error = -2147024690;
LABEL_20:
    CSetupLogging::Log(1, "CopyFile", 0, "Copying file to :", v19);
    CSetupLogging::Log(LastWin32Error, "CopyFile", 0, "Copying file to :", v19);
    XspLogEvent(0x8000042A);
    if ( LastWin32Error )
      goto LABEL_24;
    goto LABEL_21;
  }
LABEL_24:
  CSetupLogging::Log(
    LastWin32Error,
    "CopyScriptFilesToSites",
    0,
    "Copy the client side script or web admin files to a list of directories.");
  MemFree(v6);
  MemFree(v7);
  return LastWin32Error;
}

```

## disassembly

```asm
0x180041488  mov     rax, rsp
0x18004148b  mov     [rax+20h], rbx
0x18004148f  mov     [rax+18h], r8
0x180041493  mov     [rax+10h], rdx
0x180041497  mov     [rax+8], rcx
0x18004149b  push    rbp
0x18004149c  push    rsi
0x18004149d  push    rdi
0x18004149e  push    r12
0x1800414a0  push    r13
0x1800414a2  push    r14
0x1800414a4  push    r15
0x1800414a6  sub     rsp, 30h
0x1800414aa  mov     rbp, r8
0x1800414ad  lea     r9, aCopyTheClientS; "Copy the client side script or web admi"...
0x1800414b4  mov     rdi, rdx
0x1800414b7  xor     ebx, ebx
0x1800414b9  xor     r8d, r8d; unsigned int
0x1800414bc  lea     rdx, aCopyscriptfile; "CopyScriptFilesToSites"
0x1800414c3  xor     esi, esi
0x1800414c5  xor     r13d, r13d
0x1800414c8  lea     ecx, [rbx+1]; int
0x1800414cb  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x1800414d0  xor     r14d, r14d
0x1800414d3  test    dword ptr [rdi], 0FFFFFFFCh
0x1800414d9  jbe     loc_1800416E1
0x1800414df  xor     r12d, r12d
0x1800414e2  mov     rax, [rdi+8]
0x1800414e6  mov     r15, [r12+rax]
0x1800414ea  mov     rcx, r15; lpString
0x1800414ed  call    cs:__imp_lstrlenW
0x1800414f3  mov     rcx, rbp; lpString
0x1800414f6  mov     ebx, eax
0x1800414f8  call    cs:__imp_lstrlenW
0x1800414fe  lea     ecx, [rax+2]
0x180041501  mov     eax, 2
0x180041506  add     ecx, ebx
0x180041508  movsxd  rbp, ecx
0x18004150b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180041512  mul     rbp
0x180041515  cmovo   rax, rcx
0x180041519  mov     rcx, rsi; lpMem
0x18004151c  mov     rdx, rax; dwBytes
0x18004151f  call    ?MemReAlloc@@YAPEAXPEAX_K@Z; MemReAlloc(void *,unsigned __int64)
0x180041524  mov     rdi, rax
0x180041527  test    rax, rax
0x18004152a  jz      loc_1800416DC
0x180041530  mov     r8, [rsp+68h+arg_10]; unsigned __int16 *
0x180041538  mov     rdx, rbp; unsigned __int64
0x18004153b  mov     rcx, rax; unsigned __int16 *
0x18004153e  mov     rsi, rax
0x180041541  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041546  mov     ebx, eax
0x180041548  test    eax, eax
0x18004154a  jnz     loc_1800416E1
0x180041550  lea     r8, SubBlock; "\\"
0x180041557  mov     rdx, rbp; unsigned __int64
0x18004155a  mov     rcx, rsi; unsigned __int16 *
0x18004155d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180041562  mov     ebx, eax
0x180041564  test    eax, eax
0x180041566  jnz     loc_1800416E1
0x18004156c  mov     r8, r15; unsigned __int16 *
0x18004156f  mov     rdx, rbp; unsigned __int64
0x180041572  mov     rcx, rsi; unsigned __int16 *
0x180041575  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004157a  mov     ebx, eax
0x18004157c  test    eax, eax
0x18004157e  jnz     loc_1800416E1
0x180041584  mov     rcx, r15; lpString
0x180041587  call    cs:__imp_lstrlenW
0x18004158d  mov     rcx, [rsp+68h+lpString]; lpString
0x180041592  mov     ebx, eax
0x180041594  call    cs:__imp_lstrlenW
0x18004159a  lea     ecx, [rax+2]
0x18004159d  mov     eax, 2
0x1800415a2  add     ecx, ebx
0x1800415a4  movsxd  rbp, ecx
0x1800415a7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800415ae  mul     rbp
0x1800415b1  cmovo   rax, rcx
0x1800415b5  mov     rcx, r13; lpMem
0x1800415b8  mov     rdx, rax; dwBytes
0x1800415bb  call    ?MemReAlloc@@YAPEAXPEAX_K@Z; MemReAlloc(void *,unsigned __int64)
0x1800415c0  mov     rdi, rax
0x1800415c3  test    rax, rax
0x1800415c6  jz      loc_1800416DC
0x1800415cc  mov     r8, [rsp+68h+lpString]; unsigned __int16 *
0x1800415d1  mov     rdx, rbp; unsigned __int64
0x1800415d4  mov     rcx, rax; unsigned __int16 *
0x1800415d7  mov     r13, rax
0x1800415da  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800415df  mov     ebx, eax
0x1800415e1  test    eax, eax
0x1800415e3  jnz     loc_1800416E1
0x1800415e9  lea     r8, SubBlock; "\\"
0x1800415f0  mov     rdx, rbp; unsigned __int64
0x1800415f3  mov     rcx, r13; unsigned __int16 *
0x1800415f6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800415fb  mov     ebx, eax
0x1800415fd  test    eax, eax
0x1800415ff  jnz     loc_1800416E1
0x180041605  mov     r8, r15; unsigned __int16 *
0x180041608  mov     rdx, rbp; unsigned __int64
0x18004160b  mov     rcx, r13; unsigned __int16 *
0x18004160e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180041613  mov     ebx, eax
0x180041615  test    eax, eax
0x180041617  jnz     loc_1800416E1
0x18004161d  mov     rcx, rsi; lpString
0x180041620  call    cs:__imp_lstrlenW
0x180041626  mov     ebp, 104h
0x18004162b  cmp     eax, ebp
0x18004162d  jge     short loc_180041658
0x18004162f  mov     rcx, r13; lpString
0x180041632  call    cs:__imp_lstrlenW
0x180041638  cmp     eax, ebp
0x18004163a  jge     short loc_180041658
0x18004163c  xor     r8d, r8d; bFailIfExists
0x18004163f  mov     rdx, r13; lpNewFileName
0x180041642  mov     rcx, rsi; lpExistingFileName
0x180041645  call    cs:__imp_CopyFileW
0x18004164b  test    eax, eax
0x18004164d  jnz     short loc_1800416B8
0x18004164f  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180041654  mov     ebx, eax
0x180041656  jmp     short loc_18004165D
0x180041658  mov     ebx, 800700CEh
0x18004165d  xor     r8d, r8d; unsigned int
0x180041660  mov     [rsp+68h+var_48], rdi; unsigned __int16 *
0x180041665  lea     r9, aCopyingFileTo; "Copying file to :"
0x18004166c  lea     rdx, aCopyfile; "CopyFile"
0x180041673  lea     ecx, [r8+1]; int
0x180041677  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18004167c  lea     r9, aCopyingFileTo; "Copying file to :"
0x180041683  mov     [rsp+68h+var_48], rdi; unsigned __int16 *
0x180041688  xor     r8d, r8d; unsigned int
0x18004168b  lea     rdx, aCopyfile; "CopyFile"
0x180041692  mov     ecx, ebx; int
0x180041694  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180041699  mov     r9, rdi
0x18004169c  mov     dword ptr [rsp+68h+var_48], ebx
0x1800416a0  mov     r8, rsi
0x1800416a3  lea     rdx, aSS08x; "%s^%s^%08x"
0x1800416aa  mov     ecx, 8000042Ah; dwEventID
0x1800416af  call    XspLogEvent
0x1800416b4  test    ebx, ebx
0x1800416b6  jnz     short loc_1800416E1
0x1800416b8  mov     rdi, [rsp+68h+arg_8]
0x1800416bd  inc     r14d
0x1800416c0  mov     rbp, [rsp+68h+arg_10]
0x1800416c8  add     r12, 8
0x1800416cc  mov     eax, [rdi]
0x1800416ce  shr     eax, 2
0x1800416d1  cmp     r14d, eax
0x1800416d4  jl      loc_1800414E2
0x1800416da  jmp     short loc_1800416E1
0x1800416dc  mov     ebx, 8007000Eh
0x1800416e1  lea     r9, aCopyTheClientS; "Copy the client side script or web admi"...
0x1800416e8  xor     r8d, r8d; unsigned int
0x1800416eb  lea     rdx, aCopyscriptfile; "CopyScriptFilesToSites"
0x1800416f2  mov     ecx, ebx; int
0x1800416f4  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x1800416f9  mov     rcx, rsi; lpMem
0x1800416fc  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180041701  mov     rcx, r13; lpMem
0x180041704  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180041709  mov     eax, ebx
0x18004170b  mov     rbx, [rsp+68h+arg_18]
0x180041713  add     rsp, 30h
0x180041717  pop     r15
0x180041719  pop     r14
0x18004171b  pop     r13
0x18004171d  pop     r12
0x18004171f  pop     rdi
0x180041720  pop     rsi
0x180041721  pop     rbp
0x180041722  retn
```
