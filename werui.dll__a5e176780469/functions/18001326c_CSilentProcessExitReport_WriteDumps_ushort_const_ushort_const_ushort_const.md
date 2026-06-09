# CSilentProcessExitReport::WriteDumps(ushort const *,ushort const *,ushort const *)

- ea: `0x18001326c`
- end: `0x18001357a`
- name: `?WriteDumps@CSilentProcessExitReport@@AEAAJPEBG00@Z`
- size: `782`
- prototype: `__int64 __fastcall(CSilentProcessExitReport *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18000f834`

## callees

- `0x180003604`
- `0x180003fe4`
- `0x180005c20`
- `0x180005c80`
- `0x180005ddc`
- `0x180009580`
- `0x18000983c`
- `0x180009b40`
- `0x18001326c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180013335`
- `KERNEL32!CreateFileW` at `0x180013490`
- `KERNEL32!CreateFileW` at `0x180013335`
- `KERNEL32!CreateFileW` at `0x180013490`
- `KERNEL32!GetLastError` at `0x180013355`
- `KERNEL32!GetLastError` at `0x1800133d7`
- `KERNEL32!GetLastError` at `0x1800134b0`
- `KERNEL32!GetLastError` at `0x180013514`
- `KERNEL32!GetLastError` at `0x180013355`
- `KERNEL32!GetLastError` at `0x1800133d7`
- `KERNEL32!GetLastError` at `0x1800134b0`
- `KERNEL32!GetLastError` at `0x180013514`
- `dbghelp!MiniDumpWriteDump` at `0x1800133c6`
- `dbghelp!MiniDumpWriteDump` at `0x18001350a`
- `dbghelp!MiniDumpWriteDump` at `0x1800133c6`
- `dbghelp!MiniDumpWriteDump` at `0x18001350a`

## pseudocode

```c
__int64 __fastcall CSilentProcessExitReport::WriteDumps(
        CSilentProcessExitReport *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  HANDLE FileW; // rax
  HANDLE v13; // rbx
  DWORD v14; // eax
  MINIDUMP_TYPE DwordData; // eax
  DWORD LastError; // eax
  unsigned int v17; // eax
  DWORD v18; // eax
  HANDLE v19; // rax
  HANDLE v20; // rbx
  DWORD v21; // eax
  MINIDUMP_TYPE v22; // eax
  DWORD v23; // eax
  int dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-60h]
  LPCWSTR v27[4]; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+60h] [rbp-20h] BYREF
  HANDLE hFile; // [rsp+B0h] [rbp+30h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpFileName);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v27);
  dwCreationDispositiona = *((_DWORD *)this + 1);
  hFile = 0;
  v8 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
         lpFileName,
         L"%ls\\%ls-(PID-%u).dmp",
         a2,
         a3,
         dwCreationDispositiona);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 27;
LABEL_5:
      WPP_SF_d(v10[2], v11, &WPP_0b9f8713f655331c3edd713292668335_Traceguids, (unsigned int)v8);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  FileW = CreateFileW(lpFileName[0], 2u, 0, 0, 2u, 0x80u, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, FileW);
  v13 = hFile;
  if ( (unsigned __int64)hFile + 1 > 1 )
  {
    DwordData = CRegSetting::GetDwordData((CSilentProcessExitReport *)((char *)this + 424));
    if ( MiniDumpWriteDump(*((HANDLE *)this + 3), *((_DWORD *)this + 1), v13, DwordData, 0, 0, 0) )
    {
      v18 = *(_DWORD *)this;
      if ( *((_DWORD *)this + 1) == *(_DWORD *)this )
        goto LABEL_29;
    }
    else
    {
      LastError = GetLastError();
      v17 = ERROR_HR_FROM_WIN32(LastError);
      v9 = v17;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_0b9f8713f655331c3edd713292668335_Traceguids, v17);
      v18 = *(_DWORD *)this;
      if ( *((_DWORD *)this + 1) == *(_DWORD *)this )
        goto LABEL_30;
    }
    dwCreationDisposition[0] = v18;
    v8 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
           v27,
           L"%ls\\%ls-(PID-%u).dmp",
           a2,
           a4,
           *(_QWORD *)dwCreationDisposition);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 30;
        goto LABEL_5;
      }
      goto LABEL_30;
    }
    v19 = CreateFileW(v27[0], 2u, 0, 0, 2u, 0x80u, 0);
    tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, v19);
    v20 = hFile;
    if ( (unsigned __int64)hFile + 1 <= 1 )
    {
      v21 = GetLastError();
      v8 = ERROR_HR_FROM_WIN32(v21);
      v9 = v8;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 31;
        goto LABEL_5;
      }
      goto LABEL_30;
    }
    v22 = CRegSetting::GetDwordData((CSilentProcessExitReport *)((char *)this + 424));
    if ( !MiniDumpWriteDump(*((HANDLE *)this + 2), *(_DWORD *)this, v20, v22, 0, 0, 0) )
    {
      v23 = GetLastError();
      v8 = ERROR_HR_FROM_WIN32(v23);
      v9 = v8;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 32;
        goto LABEL_5;
      }
      goto LABEL_30;
    }
LABEL_29:
    v9 = 0;
    goto LABEL_30;
  }
  v14 = GetLastError();
  v8 = ERROR_HR_FROM_WIN32(v14);
  v9 = v8;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 28;
    goto LABEL_5;
  }
LABEL_30:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v27);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpFileName);
  return v9;
}

```

## disassembly

```asm
0x18001326c  mov     [rsp-28h+arg_8], rbx
0x180013271  mov     [rsp-28h+arg_10], rsi
0x180013276  push    rbp
0x180013277  push    rdi
0x180013278  push    r12
0x18001327a  push    r14
0x18001327c  push    r15
0x18001327e  mov     rbp, rsp
0x180013281  sub     rsp, 80h
0x180013288  mov     rsi, rcx
0x18001328b  mov     r12, r9
0x18001328e  lea     rcx, [rbp+lpFileName]; void *
0x180013292  mov     rbx, r8
0x180013295  mov     r14, rdx
0x180013298  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18001329d  lea     rcx, [rbp+var_40]; void *
0x1800132a1  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x1800132a6  mov     eax, [rsi+4]
0x1800132a9  lea     rdx, aLsLsPidUDmp; "%ls\\%ls-(PID-%u).dmp"
0x1800132b0  mov     r9, rbx
0x1800132b3  mov     [rsp+80h+dwCreationDisposition], eax
0x1800132b7  mov     r8, r14
0x1800132ba  mov     [rbp+hFile], 0
0x1800132c2  lea     rcx, [rbp+lpFileName]
0x1800132c6  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x1800132cb  mov     ebx, eax
0x1800132cd  test    eax, eax
0x1800132cf  jns     short loc_18001330F
0x1800132d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132d8  lea     rdi, WPP_GLOBAL_Control
0x1800132df  cmp     rcx, rdi
0x1800132e2  jz      loc_180013541
0x1800132e8  test    byte ptr [rcx+1Ch], 1
0x1800132ec  jz      loc_180013541
0x1800132f2  mov     edx, 1Bh
0x1800132f7  mov     rcx, [rcx+10h]
0x1800132fb  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x180013302  mov     r9d, eax
0x180013305  call    WPP_SF_d
0x18001330a  jmp     loc_180013541
0x18001330f  mov     rcx, [rbp+lpFileName]; lpFileName
0x180013313  mov     eax, 2
0x180013318  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180013321  mov     edx, eax; dwDesiredAccess
0x180013323  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001332b  xor     r9d, r9d; lpSecurityAttributes
0x18001332e  xor     r8d, r8d; dwShareMode
0x180013331  mov     [rsp+80h+dwCreationDisposition], eax; dwCreationDisposition
0x180013335  call    cs:__imp_CreateFileW
0x18001333b  mov     rdx, rax
0x18001333e  lea     rcx, [rbp+hFile]
0x180013342  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180013347  mov     rbx, [rbp+hFile]
0x18001334b  lea     rax, [rbx+1]
0x18001334f  cmp     rax, 1
0x180013353  ja      short loc_18001338F
0x180013355  call    cs:__imp_GetLastError
0x18001335b  mov     ecx, eax; unsigned int
0x18001335d  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180013362  mov     ebx, eax
0x180013364  mov     rcx, cs:WPP_GLOBAL_Control
0x18001336b  lea     rdi, WPP_GLOBAL_Control
0x180013372  cmp     rcx, rdi
0x180013375  jz      loc_180013541
0x18001337b  test    byte ptr [rcx+1Ch], 1
0x18001337f  jz      loc_180013541
0x180013385  mov     edx, 1Ch
0x18001338a  jmp     loc_1800132F7
0x18001338f  lea     r15, [rsi+1A8h]
0x180013396  mov     rcx, r15; this
0x180013399  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18001339e  mov     edx, [rsi+4]; ProcessId
0x1800133a1  mov     r9d, eax; DumpType
0x1800133a4  mov     rcx, [rsi+18h]; hProcess
0x1800133a8  mov     r8, rbx; hFile
0x1800133ab  mov     [rsp+80h+hTemplateFile], 0; CallbackParam
0x1800133b4  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0; UserStreamParam
0x1800133bd  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; ExceptionParam
0x1800133c6  call    cs:__imp_MiniDumpWriteDump
0x1800133cc  lea     rdi, WPP_GLOBAL_Control
0x1800133d3  test    eax, eax
0x1800133d5  jnz     short loc_18001341D
0x1800133d7  call    cs:__imp_GetLastError
0x1800133dd  mov     ecx, eax; unsigned int
0x1800133df  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800133e4  mov     ebx, eax
0x1800133e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133ed  cmp     rcx, rdi
0x1800133f0  jz      short loc_180013410
0x1800133f2  test    byte ptr [rcx+1Ch], 1
0x1800133f6  jz      short loc_180013410
0x1800133f8  mov     rcx, [rcx+10h]
0x1800133fc  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x180013403  mov     edx, 1Dh
0x180013408  mov     r9d, eax
0x18001340b  call    WPP_SF_d
0x180013410  mov     eax, [rsi]
0x180013412  cmp     [rsi+4], eax
0x180013415  jz      loc_180013541
0x18001341b  jmp     short loc_180013428
0x18001341d  mov     eax, [rsi]
0x18001341f  cmp     [rsi+4], eax
0x180013422  jz      loc_18001353F
0x180013428  mov     r9, r12
0x18001342b  mov     [rsp+80h+dwCreationDisposition], eax
0x18001342f  mov     r8, r14
0x180013432  lea     rdx, aLsLsPidUDmp; "%ls\\%ls-(PID-%u).dmp"
0x180013439  lea     rcx, [rbp+var_40]
0x18001343d  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180013442  mov     ebx, eax
0x180013444  test    eax, eax
0x180013446  jns     short loc_18001346C
0x180013448  mov     rcx, cs:WPP_GLOBAL_Control
0x18001344f  cmp     rcx, rdi
0x180013452  jz      loc_180013541
0x180013458  test    byte ptr [rcx+1Ch], 1
0x18001345c  jz      loc_180013541
0x180013462  mov     edx, 1Eh
0x180013467  jmp     loc_1800132F7
0x18001346c  mov     rcx, [rbp+var_40]; lpFileName
0x180013470  mov     edx, 2; dwDesiredAccess
0x180013475  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18001347e  xor     r9d, r9d; lpSecurityAttributes
0x180013481  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180013489  xor     r8d, r8d; dwShareMode
0x18001348c  mov     [rsp+80h+dwCreationDisposition], edx; dwCreationDisposition
0x180013490  call    cs:__imp_CreateFileW
0x180013496  mov     rdx, rax
0x180013499  lea     rcx, [rbp+hFile]
0x18001349d  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800134a2  mov     rbx, [rbp+hFile]
0x1800134a6  lea     rax, [rbx+1]
0x1800134aa  cmp     rax, 1
0x1800134ae  ja      short loc_1800134DB
0x1800134b0  call    cs:__imp_GetLastError
0x1800134b6  mov     ecx, eax; unsigned int
0x1800134b8  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800134bd  mov     ebx, eax
0x1800134bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134c6  cmp     rcx, rdi
0x1800134c9  jz      short loc_180013541
0x1800134cb  test    byte ptr [rcx+1Ch], 1
0x1800134cf  jz      short loc_180013541
0x1800134d1  mov     edx, 1Fh
0x1800134d6  jmp     loc_1800132F7
0x1800134db  mov     rcx, r15; this
0x1800134de  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x1800134e3  mov     edx, [rsi]; ProcessId
0x1800134e5  mov     r9d, eax; DumpType
0x1800134e8  mov     rcx, [rsi+10h]; hProcess
0x1800134ec  mov     r8, rbx; hFile
0x1800134ef  mov     [rsp+80h+hTemplateFile], 0; CallbackParam
0x1800134f8  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0; UserStreamParam
0x180013501  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; ExceptionParam
0x18001350a  call    cs:__imp_MiniDumpWriteDump
0x180013510  test    eax, eax
0x180013512  jnz     short loc_18001353F
0x180013514  call    cs:__imp_GetLastError
0x18001351a  mov     ecx, eax; unsigned int
0x18001351c  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180013521  mov     ebx, eax
0x180013523  mov     rcx, cs:WPP_GLOBAL_Control
0x18001352a  cmp     rcx, rdi
0x18001352d  jz      short loc_180013541
0x18001352f  test    byte ptr [rcx+1Ch], 1
0x180013533  jz      short loc_180013541
0x180013535  mov     edx, 20h ; ' '
0x18001353a  jmp     loc_1800132F7
0x18001353f  xor     ebx, ebx
0x180013541  lea     rcx, [rbp+hFile]
0x180013545  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18001354a  lea     rcx, [rbp+var_40]
0x18001354e  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180013553  lea     rcx, [rbp+lpFileName]
0x180013557  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001355c  lea     r11, [rsp+80h+var_s0]
0x180013564  mov     eax, ebx
0x180013566  mov     rbx, [r11+38h]
0x18001356a  mov     rsi, [r11+40h]
0x18001356e  mov     rsp, r11
0x180013571  pop     r15
0x180013573  pop     r14
0x180013575  pop     r12
0x180013577  pop     rdi
0x180013578  pop     rbp
0x180013579  retn
```
