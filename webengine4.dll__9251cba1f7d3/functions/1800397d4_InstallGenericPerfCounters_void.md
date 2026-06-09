# InstallGenericPerfCounters(void)

- ea: `0x1800397d4`
- end: `0x180039aa3`
- name: `?InstallGenericPerfCounters@@YAJXZ`
- size: `719`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003c1e8`

## callees

- `0x180007824`
- `0x180037df0`
- `0x180038440`
- `0x1800397d4`
- `0x18003abe4`
- `0x180040248`
- `0x180040fa0`
- `0x18004d030`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180039a1c`
- `KERNEL32!lstrlenW` at `0x180039a1c`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x1800398d7`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x180039954`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x1800398d7`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x180039954`
- `loadperf!LoadPerfCounterTextStringsW` at `0x180039a3d`
- `loadperf!LoadPerfCounterTextStringsW` at `0x180039a3d`

## string_xrefs

- `0x180039807`: `OpenGenericCounters`
- `0x180039815`: `Install common performance counters`
- `0x180039a58`: `Install common performance counters`
- `0x18003982d`: `InstallGenericPerfCounters`
- `0x180039a67`: `InstallGenericPerfCounters`
- `0x18003996b`: `SYSTEM\CurrentControlSet\Services\ASP.NET\Performance`

## pseudocode

```c
__int64 InstallGenericPerfCounters(void)
{
  __int64 v0; // rdx
  signed __int64 v1; // rdi
  WCHAR *v2; // rcx
  WCHAR v3; // ax
  WCHAR *v4; // rax
  int PerfCounterTextStringsW; // ebx
  __int64 v6; // rdx
  WCHAR *v7; // rcx
  WCHAR v8; // ax
  WCHAR *v9; // rax
  int v10; // eax
  const unsigned __int16 *v11; // r8
  unsigned int v12; // eax
  unsigned __int16 *v14[4]; // [rsp+38h] [rbp-D0h] BYREF
  WCHAR CommandLine[520]; // [rsp+58h] [rbp-B0h] BYREF

  v14[0] = L"OpenGenericCounters";
  v14[1] = L"CloseGenericCounters";
  v14[2] = L"CollectGenericCounters";
  CSetupLogging::Log(1, "InstallGenericPerfCounters", 0, "Install common performance counters", 0);
  v0 = 520;
  v1 = (char *)L"u " - (char *)CommandLine;
  v2 = CommandLine;
  do
  {
    if ( v0 == -2147483126 )
      break;
    v3 = *(WCHAR *)((char *)v2 + v1);
    if ( !v3 )
      break;
    *v2++ = v3;
    --v0;
  }
  while ( v0 );
  v4 = v2 - 1;
  if ( v0 )
    v4 = v2;
  *v4 = 0;
  PerfCounterTextStringsW = v0 == 0 ? 0x8007007A : 0;
  if ( v0 )
  {
    PerfCounterTextStringsW = StringCchCatW(CommandLine, 0x208u, L"ASP.NET");
    if ( !PerfCounterTextStringsW )
    {
      UnloadPerfCounterTextStringsW(CommandLine, 1);
      v6 = 520;
      v7 = CommandLine;
      do
      {
        if ( v6 == -2147483126 )
          break;
        v8 = *(WCHAR *)((char *)v7 + v1);
        if ( !v8 )
          break;
        *v7++ = v8;
        --v6;
      }
      while ( v6 );
      v9 = v7 - 1;
      if ( v6 )
        v9 = v7;
      *v9 = 0;
      PerfCounterTextStringsW = v6 == 0 ? 0x8007007A : 0;
      if ( v6 )
      {
        PerfCounterTextStringsW = StringCchCatW(CommandLine, 0x208u, L"ASP.NET_64");
        if ( !PerfCounterTextStringsW )
        {
          UnloadPerfCounterTextStringsW(CommandLine, 1);
          DeletePerfKey(L"ASP.NET_64");
          CreatePerfCounterEntryPoints(
            L"SYSTEM\\CurrentControlSet\\Services\\ASP.NET\\Performance",
            (const unsigned __int16 **)v14);
          PerfCounterTextStringsW = WriteVersionToPerformanceContextKey(L"ASP.NET", L"4.0.30319.0");
          if ( !PerfCounterTextStringsW )
          {
            CommandLine[0] = 0;
            PerfCounterTextStringsW = StringCchCatW(CommandLine, 0x208u, L"l \"");
            if ( !PerfCounterTextStringsW )
            {
              v10 = IsWow64();
              v11 = &Names::s_wszInstallDirectory64;
              if ( !v10 )
                v11 = &Names::s_wszInstallDirectory;
              PerfCounterTextStringsW = StringCchCatW(CommandLine, 0x208u, v11);
              if ( !PerfCounterTextStringsW )
              {
                PerfCounterTextStringsW = StringCchCatW(CommandLine, 0x208u, L"\\aspnet_perf2.ini");
                if ( !PerfCounterTextStringsW )
                {
                  PerfCounterTextStringsW = StringCchCatW(CommandLine, 0x208u, L"\"");
                  if ( !PerfCounterTextStringsW )
                  {
                    if ( lstrlenW(CommandLine) - 4 < 260 )
                    {
                      PerfCounterTextStringsW = LoadPerfCounterTextStringsW(CommandLine, 1);
                      if ( PerfCounterTextStringsW )
                      {
                        v12 = (unsigned __int16)PerfCounterTextStringsW | 0x80070000;
                        if ( PerfCounterTextStringsW <= 0 )
                          v12 = PerfCounterTextStringsW;
                        PerfCounterTextStringsW = v12;
                      }
                    }
                    else
                    {
                      PerfCounterTextStringsW = -2147024690;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  CSetupLogging::Log(PerfCounterTextStringsW, "InstallGenericPerfCounters", 0, "Install common performance counters", 0);
  return (unsigned int)PerfCounterTextStringsW;
}

```

## disassembly

```asm
0x1800397d4  mov     rax, rsp
0x1800397d7  mov     [rax+8], rbx
0x1800397db  mov     [rax+10h], rsi
0x1800397df  mov     [rax+18h], rdi
0x1800397e3  mov     [rax+20h], r14
0x1800397e7  push    rbp
0x1800397e8  lea     rbp, [rax-378h]
0x1800397ef  sub     rsp, 470h
0x1800397f6  mov     rax, cs:__security_cookie
0x1800397fd  xor     rax, rsp
0x180039800  mov     [rbp+370h+var_10], rax
0x180039807  lea     rax, aOpengenericcou; "OpenGenericCounters"
0x18003980e  xor     esi, esi
0x180039810  mov     [rsp+470h+var_440], rax
0x180039815  lea     r9, aInstallCommonP; "Install common performance counters"
0x18003981c  lea     rax, aClosegenericco; "CloseGenericCounters"
0x180039823  mov     [rsp+470h+var_450], rsi; unsigned __int16 *
0x180039828  mov     [rsp+470h+var_438], rax
0x18003982d  lea     rdx, aInstallgeneric; "InstallGenericPerfCounters"
0x180039834  lea     rax, aCollectgeneric; "CollectGenericCounters"
0x18003983b  xor     r8d, r8d; unsigned int
0x18003983e  lea     ecx, [rsi+1]; int
0x180039841  mov     [rsp+470h+var_430], rax
0x180039846  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003984b  lea     rax, [rsp+470h+CommandLine]
0x180039850  mov     r14d, 208h
0x180039856  lea     rdi, aU_0; "u "
0x18003985d  mov     edx, r14d
0x180039860  sub     rdi, rax
0x180039863  lea     rcx, [rsp+470h+CommandLine]
0x180039868  lea     rax, [rdx+7FFFFDF6h]
0x18003986f  test    rax, rax
0x180039872  jz      short loc_18003988A
0x180039874  movzx   eax, word ptr [rdi+rcx]
0x180039878  test    ax, ax
0x18003987b  jz      short loc_18003988A
0x18003987d  mov     [rcx], ax
0x180039880  add     rcx, 2
0x180039884  sub     rdx, 1
0x180039888  jnz     short loc_180039868
0x18003988a  test    rdx, rdx
0x18003988d  lea     rax, [rcx-2]
0x180039891  cmovnz  rax, rcx
0x180039895  mov     [rax], si
0x180039898  mov     rax, rdx
0x18003989b  neg     rax
0x18003989e  sbb     ebx, ebx
0x1800398a0  not     ebx
0x1800398a2  and     ebx, 8007007Ah
0x1800398a8  test    rdx, rdx
0x1800398ab  jz      loc_180039A58
0x1800398b1  lea     r8, String1; "ASP.NET"
0x1800398b8  mov     rdx, r14; unsigned __int64
0x1800398bb  lea     rcx, [rsp+470h+CommandLine]; unsigned __int16 *
0x1800398c0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800398c5  mov     ebx, eax
0x1800398c7  test    eax, eax
0x1800398c9  jnz     loc_180039A58
0x1800398cf  lea     edx, [rax+1]; bQuietModeArg
0x1800398d2  lea     rcx, [rsp+470h+CommandLine]; lpCommandLine
0x1800398d7  call    cs:__imp_UnloadPerfCounterTextStringsW
0x1800398dd  mov     rdx, r14
0x1800398e0  lea     rcx, [rsp+470h+CommandLine]
0x1800398e5  lea     rax, [rdx+7FFFFDF6h]
0x1800398ec  test    rax, rax
0x1800398ef  jz      short loc_180039907
0x1800398f1  movzx   eax, word ptr [rdi+rcx]
0x1800398f5  test    ax, ax
0x1800398f8  jz      short loc_180039907
0x1800398fa  mov     [rcx], ax
0x1800398fd  add     rcx, 2
0x180039901  sub     rdx, 1
0x180039905  jnz     short loc_1800398E5
0x180039907  test    rdx, rdx
0x18003990a  lea     rax, [rcx-2]
0x18003990e  cmovnz  rax, rcx
0x180039912  mov     [rax], si
0x180039915  mov     rax, rdx
0x180039918  neg     rax
0x18003991b  sbb     ebx, ebx
0x18003991d  not     ebx
0x18003991f  and     ebx, 8007007Ah
0x180039925  test    rdx, rdx
0x180039928  jz      loc_180039A58
0x18003992e  lea     r8, aAspNet64; "ASP.NET_64"
0x180039935  mov     rdx, r14; unsigned __int64
0x180039938  lea     rcx, [rsp+470h+CommandLine]; unsigned __int16 *
0x18003993d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180039942  mov     ebx, eax
0x180039944  test    eax, eax
0x180039946  jnz     loc_180039A58
0x18003994c  lea     edx, [rax+1]; bQuietModeArg
0x18003994f  lea     rcx, [rsp+470h+CommandLine]; lpCommandLine
0x180039954  call    cs:__imp_UnloadPerfCounterTextStringsW
0x18003995a  lea     rcx, aAspNet64; "ASP.NET_64"
0x180039961  call    ?DeletePerfKey@@YAJPEBG@Z; DeletePerfKey(ushort const *)
0x180039966  lea     rdx, [rsp+470h+var_440]; unsigned __int16 **
0x18003996b  lea     rcx, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Services\\AS"...
0x180039972  call    ?CreatePerfCounterEntryPoints@@YAJPEBGPEAPEBG@Z; CreatePerfCounterEntryPoints(ushort const *,ushort const * *)
0x180039977  lea     rdx, a40303190; "4.0.30319.0"
0x18003997e  lea     rcx, String1; "ASP.NET"
0x180039985  call    ?WriteVersionToPerformanceContextKey@@YAJPEBG0@Z; WriteVersionToPerformanceContextKey(ushort const *,ushort const *)
0x18003998a  mov     ebx, eax
0x18003998c  test    eax, eax
0x18003998e  jnz     loc_180039A58
0x180039994  lea     r8, asc_180074000; "l \""
0x18003999b  mov     [rsp+470h+CommandLine], si
0x1800399a0  mov     rdx, r14; unsigned __int64
0x1800399a3  lea     rcx, [rsp+470h+CommandLine]; unsigned __int16 *
0x1800399a8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800399ad  mov     ebx, eax
0x1800399af  test    eax, eax
0x1800399b1  jnz     loc_180039A58
0x1800399b7  call    IsWow64
0x1800399bc  test    eax, eax
0x1800399be  lea     rcx, ?s_wszInstallDirectory@Names@@0PAGA; ushort near * Names::s_wszInstallDirectory
0x1800399c5  lea     r8, ?s_wszInstallDirectory64@Names@@0PAGA; ushort near * Names::s_wszInstallDirectory64
0x1800399cc  mov     rdx, r14; unsigned __int64
0x1800399cf  cmovz   r8, rcx; unsigned __int16 *
0x1800399d3  lea     rcx, [rsp+470h+CommandLine]; unsigned __int16 *
0x1800399d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800399dd  mov     ebx, eax
0x1800399df  test    eax, eax
0x1800399e1  jnz     short loc_180039A58
0x1800399e3  lea     r8, aAspnetPerf2Ini_0; "\\aspnet_perf2.ini"
0x1800399ea  mov     rdx, r14; unsigned __int64
0x1800399ed  lea     rcx, [rsp+470h+CommandLine]; unsigned __int16 *
0x1800399f2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800399f7  mov     ebx, eax
0x1800399f9  test    eax, eax
0x1800399fb  jnz     short loc_180039A58
0x1800399fd  lea     r8, asc_180073488; "\""
0x180039a04  mov     rdx, r14; unsigned __int64
0x180039a07  lea     rcx, [rsp+470h+CommandLine]; unsigned __int16 *
0x180039a0c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180039a11  mov     ebx, eax
0x180039a13  test    eax, eax
0x180039a15  jnz     short loc_180039A58
0x180039a17  lea     rcx, [rsp+470h+CommandLine]; lpString
0x180039a1c  call    cs:__imp_lstrlenW
0x180039a22  sub     eax, 4
0x180039a25  cmp     eax, 104h
0x180039a2a  jl      short loc_180039A33
0x180039a2c  mov     ebx, 800700CEh
0x180039a31  jmp     short loc_180039A58
0x180039a33  mov     edx, 1; bQuietModeArg
0x180039a38  lea     rcx, [rsp+470h+CommandLine]; lpCommandLine
0x180039a3d  call    cs:__imp_LoadPerfCounterTextStringsW
0x180039a43  mov     ebx, eax
0x180039a45  test    eax, eax
0x180039a47  jz      short loc_180039A58
0x180039a49  movzx   eax, bx
0x180039a4c  or      eax, 80070000h
0x180039a51  test    ebx, ebx
0x180039a53  cmovle  eax, ebx
0x180039a56  mov     ebx, eax
0x180039a58  lea     r9, aInstallCommonP; "Install common performance counters"
0x180039a5f  mov     [rsp+470h+var_450], rsi; unsigned __int16 *
0x180039a64  xor     r8d, r8d; unsigned int
0x180039a67  lea     rdx, aInstallgeneric; "InstallGenericPerfCounters"
0x180039a6e  mov     ecx, ebx; int
0x180039a70  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180039a75  mov     eax, ebx
0x180039a77  mov     rcx, [rbp+370h+var_10]
0x180039a7e  xor     rcx, rsp; StackCookie
0x180039a81  call    __security_check_cookie
0x180039a86  lea     r11, [rsp+470h+var_s0]
0x180039a8e  mov     rbx, [r11+10h]
0x180039a92  mov     rsi, [r11+18h]
0x180039a96  mov     rdi, [r11+20h]
0x180039a9a  mov     r14, [r11+28h]
0x180039a9e  mov     rsp, r11
0x180039aa1  pop     rbp
0x180039aa2  retn
```
