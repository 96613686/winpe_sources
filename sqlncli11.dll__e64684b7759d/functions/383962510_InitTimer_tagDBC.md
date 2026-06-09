# InitTimer(tagDBC *)

- ea: `0x383962510`
- end: `0x3839627a5`
- name: `?InitTimer@@YAFPEAUtagDBC@@@Z`
- size: `661`
- prototype: `__int16 __fastcall(struct tagDBC *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x383962810`
- `0x3839629f0`

## callees

- `0x38389a4e0`
- `0x38391aed0`
- `0x383962510`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x3839626f7`
- `KERNEL32!FreeLibrary` at `0x3839626f7`
- `KERNEL32!LoadLibraryW` at `0x383962539`
- `KERNEL32!LoadLibraryW` at `0x383962539`
- `KERNEL32!GetLastError` at `0x383962580`
- `KERNEL32!GetLastError` at `0x3839626cb`
- `KERNEL32!GetLastError` at `0x383962580`
- `KERNEL32!GetLastError` at `0x3839626cb`
- `KERNEL32!GetProcAddress` at `0x3839625e4`
- `KERNEL32!GetProcAddress` at `0x3839625ff`
- `KERNEL32!GetProcAddress` at `0x38396261a`
- `KERNEL32!GetProcAddress` at `0x383962635`
- `KERNEL32!GetProcAddress` at `0x3839625e4`
- `KERNEL32!GetProcAddress` at `0x3839625ff`
- `KERNEL32!GetProcAddress` at `0x38396261a`
- `KERNEL32!GetProcAddress` at `0x383962635`

## string_xrefs

- `0x38396252d`: `WINMM.DLL`

## pseudocode

```c
__int64 __fastcall InitTimer(struct tagDBC *a1)
{
  __int16 v1; // bx
  HMODULE LibraryW; // rax
  DWORD v4; // eax
  char *v5; // rcx
  __int64 v6; // r9
  __int64 v7; // rdx
  unsigned int (*ProcAddress)(unsigned int); // rax
  DWORD LastError; // eax
  __int64 v10; // rdx
  struct timecaps_tag v12; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  if ( !g_hTimeLib )
  {
    LibraryW = LoadLibraryW(L"WINMM.DLL");
    g_hTimeLib = LibraryW;
    if ( LibraryW )
    {
      fptimeGetDevCaps = (unsigned int (*)(struct timecaps_tag *, unsigned int))GetProcAddress(
                                                                                  LibraryW,
                                                                                  "timeGetDevCaps");
      fptimeGetTime = (unsigned int (*)(void))GetProcAddress(g_hTimeLib, "timeGetTime");
      fptimeBeginPeriod = (unsigned int (*)(unsigned int))GetProcAddress(g_hTimeLib, "timeBeginPeriod");
      ProcAddress = (unsigned int (*)(unsigned int))GetProcAddress(g_hTimeLib, "timeEndPeriod");
      fptimeEndPeriod = ProcAddress;
      if ( fptimeGetDevCaps && fptimeGetTime && fptimeBeginPeriod && ProcAddress )
      {
        fptimeGetDevCaps(&v12, 8u);
        if ( fptimeBeginPeriod(v12.wPeriodMin) )
          v12.wPeriodMin = 0;
        else
          g_SQLPerfData.TimerResolution = v12.wPeriodMin;
      }
      else
      {
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B43218[0], 88073, off_383B49120[0], 86);
        LastError = GetLastError();
        PostSQLErrorEx(a1, 0x9CD6u, LastError, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
        FreeLibrary(g_hTimeLib);
        g_hTimeLib = 0;
        fptimeGetDevCaps = 0;
        fptimeGetTime = 0;
        fptimeBeginPeriod = 0;
        fptimeEndPeriod = 0;
        v1 = -1;
        if ( (bidGblFlags & 2) != 0 )
        {
          v5 = off_383B43218[0];
          if ( off_383B49120[0] )
          {
            v6 = 97;
            v7 = 99337;
            goto LABEL_22;
          }
        }
      }
    }
    else
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43218[0], 75785, off_383B49120[0], 74);
      v4 = GetLastError();
      PostSQLErrorEx(a1, 0x9CD5u, v4, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      v1 = -1;
      if ( (bidGblFlags & 2) != 0 )
      {
        v5 = off_383B43218[0];
        if ( off_383B49120[0] )
        {
          v6 = 76;
          v7 = 77833;
LABEL_22:
          bidTraceW(v5, v7, off_383B49120[0], v6);
        }
      }
    }
  }
  if ( (bidGblFlags & 2) != 0 && (v1 || (bidGblFlags & 0x40) != 0) )
  {
    v10 = 111617;
    if ( v1 )
      v10 = 111649;
    bidTraceW(off_383B43218[0], v10, off_383B494E8[0], (unsigned int)v1);
  }
  return (unsigned __int16)v1;
}

```

## disassembly

```asm
0x383962510  push    rbx
0x383962512  sub     rsp, 30h
0x383962516  xor     ebx, ebx
0x383962518  mov     [rsp+38h+arg_0], rsi
0x38396251d  mov     rsi, rcx
0x383962520  cmp     cs:?g_hTimeLib@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hTimeLib
0x383962527  jnz     loc_383962759
0x38396252d  lea     rcx, aWinmmDll; "WINMM.DLL"
0x383962534  mov     [rsp+38h+arg_10], rdi
0x383962539  call    cs:__imp_LoadLibraryW
0x38396253f  mov     cs:?g_hTimeLib@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hTimeLib
0x383962546  test    rax, rax
0x383962549  jnz     loc_3839625DA
0x38396254f  test    byte ptr cs:_bidGblFlags, 2
0x383962556  jz      short loc_383962580
0x383962558  mov     rcx, cs:off_383B43218; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x38396255f  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383962566  test    rax, rax
0x383962569  jz      short loc_383962580
0x38396256b  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383962572  lea     r9d, [rbx+4Ah]
0x383962576  mov     edx, 12809h
0x38396257b  call    _bidTraceW
0x383962580  call    cs:__imp_GetLastError
0x383962586  or      rdi, 0FFFFFFFFFFFFFFFFh
0x38396258a  mov     edx, 9CD5h; unsigned __int16
0x38396258f  mov     rcx, rsi; struct tagOBJBASE *
0x383962592  mov     r8d, eax; int
0x383962595  mov     r9, rdi; unsigned __int64
0x383962598  mov     [rsp+38h+var_18], 0FFFFFFFFh; unsigned int
0x3839625a0  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x3839625a5  test    byte ptr cs:_bidGblFlags, 2
0x3839625ac  movzx   ebx, di
0x3839625af  jz      loc_383962754
0x3839625b5  mov     rcx, cs:off_383B43218; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839625bc  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3839625c3  test    rax, rax
0x3839625c6  jz      loc_383962754
0x3839625cc  lea     r9d, [rdi+4Dh]
0x3839625d0  mov     edx, 13009h
0x3839625d5  jmp     loc_383962748
0x3839625da  lea     rdx, aTimegetdevcaps; "timeGetDevCaps"
0x3839625e1  mov     rcx, rax; hModule
0x3839625e4  call    cs:__imp_GetProcAddress
0x3839625ea  mov     rcx, cs:?g_hTimeLib@@3PEAUHINSTANCE__@@EA; hModule
0x3839625f1  lea     rdx, aTimegettime; "timeGetTime"
0x3839625f8  mov     cs:?fptimeGetDevCaps@@3P6AIPEAUtimecaps_tag@@I@ZEA, rax; uint (*fptimeGetDevCaps)(timecaps_tag *,uint)
0x3839625ff  call    cs:__imp_GetProcAddress
0x383962605  mov     rcx, cs:?g_hTimeLib@@3PEAUHINSTANCE__@@EA; hModule
0x38396260c  lea     rdx, aTimebeginperio; "timeBeginPeriod"
0x383962613  mov     cs:?fptimeGetTime@@3P6AKXZEA, rax; ulong (*fptimeGetTime)(void)
0x38396261a  call    cs:__imp_GetProcAddress
0x383962620  mov     rcx, cs:?g_hTimeLib@@3PEAUHINSTANCE__@@EA; hModule
0x383962627  lea     rdx, aTimeendperiod; "timeEndPeriod"
0x38396262e  mov     cs:?fptimeBeginPeriod@@3P6AII@ZEA, rax; uint (*fptimeBeginPeriod)(uint)
0x383962635  call    cs:__imp_GetProcAddress
0x38396263b  mov     r8, cs:?fptimeGetDevCaps@@3P6AIPEAUtimecaps_tag@@I@ZEA; uint (*fptimeGetDevCaps)(timecaps_tag *,uint)
0x383962642  mov     cs:?fptimeEndPeriod@@3P6AII@ZEA, rax; uint (*fptimeEndPeriod)(uint)
0x383962649  test    r8, r8
0x38396264c  jz      short loc_383962698
0x38396264e  cmp     cs:?fptimeGetTime@@3P6AKXZEA, rbx; ulong (*fptimeGetTime)(void)
0x383962655  jz      short loc_383962698
0x383962657  cmp     cs:?fptimeBeginPeriod@@3P6AII@ZEA, rbx; uint (*fptimeBeginPeriod)(uint)
0x38396265e  jz      short loc_383962698
0x383962660  test    rax, rax
0x383962663  jz      short loc_383962698
0x383962665  lea     rcx, [rsp+38h+arg_8]
0x38396266a  mov     edx, 8
0x38396266f  call    r8 ; uint (*fptimeGetDevCaps)(timecaps_tag *,uint)
0x383962672  mov     ecx, dword ptr [rsp+38h+arg_8]
0x383962676  call    cs:?fptimeBeginPeriod@@3P6AII@ZEA; uint (*fptimeBeginPeriod)(uint)
0x38396267c  test    eax, eax
0x38396267e  jnz     short loc_38396268F
0x383962680  mov     eax, dword ptr [rsp+38h+arg_8]
0x383962684  mov     cs:?g_SQLPerfData@@3Usqlperf@@A, eax; sqlperf g_SQLPerfData
0x38396268a  jmp     loc_383962754
0x38396268f  mov     dword ptr [rsp+38h+arg_8], ebx
0x383962693  jmp     loc_383962754
0x383962698  test    byte ptr cs:_bidGblFlags, 2
0x38396269f  jz      short loc_3839626CB
0x3839626a1  mov     rcx, cs:off_383B43218; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839626a8  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3839626af  test    rax, rax
0x3839626b2  jz      short loc_3839626CB
0x3839626b4  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3839626bb  mov     r9d, 56h ; 'V'
0x3839626c1  mov     edx, 15809h
0x3839626c6  call    _bidTraceW
0x3839626cb  call    cs:__imp_GetLastError
0x3839626d1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x3839626d5  mov     edx, 9CD6h; unsigned __int16
0x3839626da  mov     rcx, rsi; struct tagOBJBASE *
0x3839626dd  mov     r8d, eax; int
0x3839626e0  mov     r9, rdi; unsigned __int64
0x3839626e3  mov     [rsp+38h+var_18], 0FFFFFFFFh; unsigned int
0x3839626eb  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x3839626f0  mov     rcx, cs:?g_hTimeLib@@3PEAUHINSTANCE__@@EA; hLibModule
0x3839626f7  call    cs:__imp_FreeLibrary
0x3839626fd  test    byte ptr cs:_bidGblFlags, 2
0x383962704  mov     cs:?g_hTimeLib@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hTimeLib
0x38396270b  mov     cs:?fptimeGetDevCaps@@3P6AIPEAUtimecaps_tag@@I@ZEA, rbx; uint (*fptimeGetDevCaps)(timecaps_tag *,uint)
0x383962712  mov     cs:?fptimeGetTime@@3P6AKXZEA, rbx; ulong (*fptimeGetTime)(void)
0x383962719  mov     cs:?fptimeBeginPeriod@@3P6AII@ZEA, rbx; uint (*fptimeBeginPeriod)(uint)
0x383962720  mov     cs:?fptimeEndPeriod@@3P6AII@ZEA, rbx; uint (*fptimeEndPeriod)(uint)
0x383962727  movzx   ebx, di
0x38396272a  jz      short loc_383962754
0x38396272c  mov     rcx, cs:off_383B43218; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383962733  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x38396273a  test    rax, rax
0x38396273d  jz      short loc_383962754
0x38396273f  lea     r9d, [rdi+62h]
0x383962743  mov     edx, 18409h
0x383962748  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x38396274f  call    _bidTraceW
0x383962754  mov     rdi, [rsp+38h+arg_10]
0x383962759  test    byte ptr cs:_bidGblFlags, 2
0x383962760  mov     rsi, [rsp+38h+arg_0]
0x383962765  jz      short loc_38396279C
0x383962767  mov     rcx, cs:off_383B43218; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x38396276e  mov     r8, cs:off_383B494E8; "<ODBC|DRIVER|RET> %d{SQLRETURN}\n"
0x383962775  test    bx, bx
0x383962778  jnz     short loc_383962783
0x38396277a  test    byte ptr cs:_bidGblFlags, 40h
0x383962781  jz      short loc_38396279C
0x383962783  mov     eax, 1B421h
0x383962788  test    bx, bx
0x38396278b  mov     edx, 1B401h
0x383962790  cmovnz  edx, eax
0x383962793  movsx   r9d, bx
0x383962797  call    _bidTraceW
0x38396279c  movzx   eax, bx
0x38396279f  add     rsp, 30h
0x3839627a3  pop     rbx
0x3839627a4  retn
```
