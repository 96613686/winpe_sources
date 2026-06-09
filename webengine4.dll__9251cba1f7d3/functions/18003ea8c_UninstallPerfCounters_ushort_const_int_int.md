# UninstallPerfCounters(ushort const *,int,int)

- ea: `0x18003ea8c`
- end: `0x18003ee56`
- name: `?UninstallPerfCounters@@YAJPEBGHH@Z`
- size: `970`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, int)`
- caller_count: `4`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180039aa4`
- `0x18003b2c8`
- `0x18003e744`
- `0x18003ef38`

## callees

- `0x180007824`
- `0x18000c534`
- `0x18000c598`
- `0x18000d1d4`
- `0x18000dd78`
- `0x180012b30`
- `0x18002b0e0`
- `0x1800370b4`
- `0x180038440`
- `0x18003abe4`
- `0x18003bcd0`
- `0x18003bf1c`
- `0x18003e6dc`
- `0x18003ea8c`
- `0x180040248`
- `0x180040fa0`
- `0x18004d030`
- `0x18004dc9c`

## import_xrefs

- `loadperf!UnloadPerfCounterTextStringsW` at `0x18003eb57`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x18003ebfb`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x18003eb57`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x18003ebfb`
- `SHLWAPI!SHDeleteKeyW` at `0x18003ec4d`
- `SHLWAPI!SHDeleteKeyW` at `0x18003edda`
- `SHLWAPI!SHDeleteKeyW` at `0x18003ec4d`
- `SHLWAPI!SHDeleteKeyW` at `0x18003edda`

## string_xrefs

- `0x18003ecf9`: `aspnet_perf.dll`
- `0x18003ead3`: `Uninstalling performance counters`
- `0x18003ee02`: `Uninstalling performance counters`
- `0x18003eae2`: `UninstallPerfCounters`
- `0x18003ee11`: `UninstallPerfCounters`
- `0x18003ec3f`: `SYSTEM\CurrentControlSet\Services\ASP.NET`
- `0x18003edcc`: `SYSTEM\CurrentControlSet\Services\ASP.NET\Linkage`

## pseudocode

```c
__int64 __fastcall UninstallPerfCounters(const unsigned __int16 *a1, int a2, int a3)
{
  unsigned int InstallDirectory64; // ebx
  __int64 v7; // rdx
  WCHAR *v8; // rcx
  WCHAR v9; // ax
  WCHAR *v10; // rax
  unsigned int inited; // eax
  LSTATUS v12; // eax
  unsigned __int16 *v13; // rdi
  unsigned __int16 *v14; // rcx
  signed __int64 v15; // r8
  __int64 v16; // rdx
  unsigned __int16 v17; // ax
  unsigned __int16 *v18; // rax
  int v19; // eax
  unsigned __int16 *v20; // rcx
  unsigned int v21; // eax
  unsigned __int16 *v23; // [rsp+20h] [rbp-E0h]
  _BYTE v24[40]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v25; // [rsp+68h] [rbp-98h]
  _BYTE v26[16]; // [rsp+C8h] [rbp-38h] BYREF
  int v27; // [rsp+D8h] [rbp-28h]
  WCHAR CommandLine[520]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v29[520]; // [rsp+4F0h] [rbp+3F0h] BYREF
  wchar_t Buffer[264]; // [rsp+900h] [rbp+800h] BYREF
  unsigned __int16 v31[520]; // [rsp+B10h] [rbp+A10h] BYREF

  CRegInfo::CRegInfo((CRegInfo *)v24);
  CSetupLogging::Log(1, "UninstallPerfCounters", 0, "Uninstalling performance counters", 0);
  CommandLine[0] = 0;
  InstallDirectory64 = StringCchCatW(CommandLine, 0x208u, L"u \"");
  if ( !InstallDirectory64 )
  {
    InstallDirectory64 = StringCchCatW(CommandLine, 0x208u, a1);
    if ( !InstallDirectory64 )
    {
      InstallDirectory64 = StringCchCatW(CommandLine, 0x208u, L"\"");
      if ( !InstallDirectory64 )
      {
        UnloadPerfCounterTextStringsW(CommandLine, 1);
        if ( a3 )
          DeletePerfKey(L"ASP.NET_4.0.30319");
        if ( a2 )
        {
          v7 = 520;
          v8 = CommandLine;
          do
          {
            if ( v7 == -2147483126 )
              break;
            v9 = *(WCHAR *)((char *)v8 + (char *)L"u " - (char *)CommandLine);
            if ( !v9 )
              break;
            *v8++ = v9;
            --v7;
          }
          while ( v7 );
          v10 = v8 - 1;
          if ( v7 )
            v10 = v8;
          *v10 = 0;
          InstallDirectory64 = v7 == 0 ? 0x8007007A : 0;
          if ( v7 )
          {
            InstallDirectory64 = StringCchCatW(CommandLine, 0x208u, L"ASP.NET");
            if ( !InstallDirectory64 )
            {
              UnloadPerfCounterTextStringsW(CommandLine, 1);
              inited = CRegInfo::InitHighestInfo((CRegInfo *)v24, (struct ASPNETVER *)&ASPNETVER::m_gThisVer);
              InstallDirectory64 = inited;
              if ( inited )
              {
                if ( inited == -2147023728 )
                  InstallDirectory64 = 0;
                else
                  XspLogEvent(0x80000402);
                v12 = SHDeleteKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\ASP.NET");
                if ( (v12 & 0xFFFFFFFC) != 0 || v12 == 1 )
                {
                  InstallDirectory64 = (unsigned __int16)v12 | 0x80070000;
                  if ( v12 <= 0 )
                    InstallDirectory64 = v12;
                }
                goto LABEL_45;
              }
              v13 = v25;
              v14 = v29;
              v15 = (char *)v25 - (char *)v29;
              v16 = 520;
              do
              {
                if ( v16 == -2147483126 )
                  break;
                v17 = *(unsigned __int16 *)((char *)v14 + v15);
                if ( !v17 )
                  break;
                *v14++ = v17;
                --v16;
              }
              while ( v16 );
              v18 = v14 - 1;
              if ( v16 )
                v18 = v14;
              *v18 = 0;
              InstallDirectory64 = v16 == 0 ? 0x8007007A : 0;
              if ( v16 )
              {
                InstallDirectory64 = StringCchCatW(v29, 0x208u, L"\\");
                if ( !InstallDirectory64 )
                {
                  InstallDirectory64 = StringCchCatW(v29, 0x208u, L"aspnet_perf.dll");
                  if ( !InstallDirectory64 )
                  {
                    if ( !(unsigned int)SupportsPerfShimModel(v29) )
                    {
                      SHDeleteKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\ASP.NET\\Linkage");
                      InstallDirectory64 = 0;
                      Recreate32BitPerfCountersKey((struct CRegInfo *)v24);
                      if ( !(unsigned int)RunningOn64Bit() )
                        goto LABEL_45;
                      v21 = Recreate64BitPerfCountersKey((struct CRegInfo *)v24);
                      goto LABEL_44;
                    }
                    if ( ((unsigned __int64)v26 & -(__int64)(v27 != 0)) == 0 )
                    {
                      InstallDirectory64 = -2147467259;
                      goto LABEL_45;
                    }
                    LODWORD(v23) = *(_DWORD *)(((unsigned __int64)v26 & -(__int64)(v27 != 0)) + 4);
                    InstallDirectory64 = StringCchPrintfW(
                                           Buffer,
                                           0x104u,
                                           L"%d.%d.%d.%d",
                                           *(unsigned int *)((unsigned __int64)v26 & -(__int64)(v27 != 0)),
                                           v23,
                                           *(_DWORD *)(((unsigned __int64)v26 & -(__int64)(v27 != 0)) + 8),
                                           *(_DWORD *)(((unsigned __int64)v26 & -(__int64)(v27 != 0)) + 0xC));
                    if ( !InstallDirectory64 )
                    {
                      InstallDirectory64 = WriteVersionToPerformanceContextKey(L"ASP.NET", (BYTE *)Buffer);
                      if ( !InstallDirectory64 )
                      {
                        v19 = IsWow64();
                        v20 = v13;
                        if ( v19 )
                        {
                          InstallDirectory64 = GetInstallDirectory64(v13, v31, 0x208u);
                          if ( InstallDirectory64 )
                            goto LABEL_45;
                          v20 = v31;
                        }
                        v21 = CallLoadPerfCounterTextStrings(v20);
LABEL_44:
                        InstallDirectory64 = v21;
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
  }
LABEL_45:
  CSetupLogging::Log(InstallDirectory64, "UninstallPerfCounters", 0, "Uninstalling performance counters", 0);
  CRegInfo::~CRegInfo((CRegInfo *)v24);
  return InstallDirectory64;
}

```

## disassembly

```asm
0x18003ea8c  mov     [rsp-8+arg_8], rbx
0x18003ea91  mov     [rsp-8+arg_10], rsi
0x18003ea96  push    rbp
0x18003ea97  push    rdi
0x18003ea98  push    r12
0x18003ea9a  push    r14
0x18003ea9c  push    r15
0x18003ea9e  lea     rbp, [rsp-0E30h]
0x18003eaa6  sub     rsp, 0F30h
0x18003eaad  mov     rax, cs:__security_cookie
0x18003eab4  xor     rax, rsp
0x18003eab7  mov     [rbp+0E50h+var_30], rax
0x18003eabe  mov     rsi, rcx
0x18003eac1  mov     r14d, r8d
0x18003eac4  lea     rcx, [rsp+0F50h+var_F10]; this
0x18003eac9  mov     edi, edx
0x18003eacb  call    ??0CRegInfo@@QEAA@XZ; CRegInfo::CRegInfo(void)
0x18003ead0  xor     r15d, r15d
0x18003ead3  lea     r9, aUninstallingPe; "Uninstalling performance counters"
0x18003eada  xor     r8d, r8d; unsigned int
0x18003eadd  mov     [rsp+0F50h+var_F30], r15; unsigned __int16 *
0x18003eae2  lea     rdx, aUninstallperfc; "UninstallPerfCounters"
0x18003eae9  lea     ecx, [r15+1]; int
0x18003eaed  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003eaf2  mov     r12d, 208h
0x18003eaf8  mov     [rbp+0E50h+CommandLine], r15w
0x18003eafd  mov     edx, r12d; unsigned __int64
0x18003eb00  lea     r8, aU; "u \""
0x18003eb07  lea     rcx, [rbp+0E50h+CommandLine]; unsigned __int16 *
0x18003eb0b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003eb10  mov     ebx, eax
0x18003eb12  test    eax, eax
0x18003eb14  jnz     loc_18003EE02
0x18003eb1a  mov     r8, rsi; unsigned __int16 *
0x18003eb1d  lea     rcx, [rbp+0E50h+CommandLine]; unsigned __int16 *
0x18003eb21  mov     edx, r12d; unsigned __int64
0x18003eb24  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003eb29  mov     ebx, eax
0x18003eb2b  test    eax, eax
0x18003eb2d  jnz     loc_18003EE02
0x18003eb33  lea     r8, asc_180073488; "\""
0x18003eb3a  mov     edx, r12d; unsigned __int64
0x18003eb3d  lea     rcx, [rbp+0E50h+CommandLine]; unsigned __int16 *
0x18003eb41  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003eb46  mov     ebx, eax
0x18003eb48  test    eax, eax
0x18003eb4a  jnz     loc_18003EE02
0x18003eb50  lea     edx, [rax+1]; bQuietModeArg
0x18003eb53  lea     rcx, [rbp+0E50h+CommandLine]; lpCommandLine
0x18003eb57  call    cs:__imp_UnloadPerfCounterTextStringsW
0x18003eb5d  test    r14d, r14d
0x18003eb60  jz      short loc_18003EB6E
0x18003eb62  lea     rcx, aAspNet4030319; "ASP.NET_4.0.30319"
0x18003eb69  call    ?DeletePerfKey@@YAJPEBG@Z; DeletePerfKey(ushort const *)
0x18003eb6e  test    edi, edi
0x18003eb70  jz      loc_18003EE02
0x18003eb76  lea     r8, aU_0; "u "
0x18003eb7d  mov     rdx, r12
0x18003eb80  lea     rax, [rbp+0E50h+CommandLine]
0x18003eb84  sub     r8, rax
0x18003eb87  lea     rcx, [rbp+0E50h+CommandLine]
0x18003eb8b  lea     rax, [rdx+7FFFFDF6h]
0x18003eb92  test    rax, rax
0x18003eb95  jz      short loc_18003EBAE
0x18003eb97  movzx   eax, word ptr [r8+rcx]
0x18003eb9c  test    ax, ax
0x18003eb9f  jz      short loc_18003EBAE
0x18003eba1  mov     [rcx], ax
0x18003eba4  add     rcx, 2
0x18003eba8  sub     rdx, 1
0x18003ebac  jnz     short loc_18003EB8B
0x18003ebae  test    rdx, rdx
0x18003ebb1  lea     rax, [rcx-2]
0x18003ebb5  mov     esi, 8007007Ah
0x18003ebba  cmovnz  rax, rcx
0x18003ebbe  mov     [rax], r15w
0x18003ebc2  mov     rax, rdx
0x18003ebc5  neg     rax
0x18003ebc8  sbb     ebx, ebx
0x18003ebca  not     ebx
0x18003ebcc  and     ebx, esi
0x18003ebce  test    rdx, rdx
0x18003ebd1  jz      loc_18003EE02
0x18003ebd7  lea     r8, String1; "ASP.NET"
0x18003ebde  mov     rdx, r12; unsigned __int64
0x18003ebe1  lea     rcx, [rbp+0E50h+CommandLine]; unsigned __int16 *
0x18003ebe5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003ebea  mov     ebx, eax
0x18003ebec  test    eax, eax
0x18003ebee  jnz     loc_18003EE02
0x18003ebf4  lea     edx, [rax+1]; bQuietModeArg
0x18003ebf7  lea     rcx, [rbp+0E50h+CommandLine]; lpCommandLine
0x18003ebfb  call    cs:__imp_UnloadPerfCounterTextStringsW
0x18003ec01  lea     rdx, ?m_gThisVer@ASPNETVER@@0V1@A; struct ASPNETVER *
0x18003ec08  lea     rcx, [rsp+0F50h+var_F10]; this
0x18003ec0d  call    ?InitHighestInfo@CRegInfo@@QEAAJPEAVASPNETVER@@@Z; CRegInfo::InitHighestInfo(ASPNETVER *)
0x18003ec12  mov     ebx, eax
0x18003ec14  test    eax, eax
0x18003ec16  jz      short loc_18003EC76
0x18003ec18  cmp     eax, 80070490h
0x18003ec1d  jz      short loc_18003EC3C
0x18003ec1f  mov     r9d, eax
0x18003ec22  lea     r8, a40303190; "4.0.30319.0"
0x18003ec29  lea     rdx, aPerfCounterS0x; "Perf Counter %s^0x%08x"
0x18003ec30  mov     ecx, 80000402h; dwEventID
0x18003ec35  call    XspLogEvent
0x18003ec3a  jmp     short loc_18003EC3F
0x18003ec3c  mov     ebx, r15d
0x18003ec3f  lea     rdx, pszSubKey; "SYSTEM\\CurrentControlSet\\Services\\AS"...
0x18003ec46  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003ec4d  call    cs:__imp_SHDeleteKeyW
0x18003ec53  test    eax, 0FFFFFFFCh
0x18003ec58  jnz     short loc_18003EC63
0x18003ec5a  cmp     eax, 1
0x18003ec5d  jnz     loc_18003EE02
0x18003ec63  movzx   ebx, ax
0x18003ec66  or      ebx, 80070000h
0x18003ec6c  test    eax, eax
0x18003ec6e  cmovle  ebx, eax
0x18003ec71  jmp     loc_18003EE02
0x18003ec76  mov     rdi, [rsp+0F50h+var_EE8]
0x18003ec7b  lea     rax, [rbp+0E50h+var_A60]
0x18003ec82  mov     r8, rdi
0x18003ec85  lea     rcx, [rbp+0E50h+var_A60]
0x18003ec8c  sub     r8, rax
0x18003ec8f  mov     rdx, r12
0x18003ec92  lea     rax, [rdx+7FFFFDF6h]
0x18003ec99  test    rax, rax
0x18003ec9c  jz      short loc_18003ECB5
0x18003ec9e  movzx   eax, word ptr [r8+rcx]
0x18003eca3  test    ax, ax
0x18003eca6  jz      short loc_18003ECB5
0x18003eca8  mov     [rcx], ax
0x18003ecab  add     rcx, 2
0x18003ecaf  sub     rdx, 1
0x18003ecb3  jnz     short loc_18003EC92
0x18003ecb5  test    rdx, rdx
0x18003ecb8  lea     rax, [rcx-2]
0x18003ecbc  cmovnz  rax, rcx
0x18003ecc0  mov     [rax], r15w
0x18003ecc4  mov     rax, rdx
0x18003ecc7  neg     rax
0x18003ecca  sbb     ebx, ebx
0x18003eccc  not     ebx
0x18003ecce  and     ebx, esi
0x18003ecd0  test    rdx, rdx
0x18003ecd3  jz      loc_18003EE02
0x18003ecd9  lea     r8, SubBlock; "\\"
0x18003ece0  mov     rdx, r12; unsigned __int64
0x18003ece3  lea     rcx, [rbp+0E50h+var_A60]; unsigned __int16 *
0x18003ecea  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003ecef  mov     ebx, eax
0x18003ecf1  test    eax, eax
0x18003ecf3  jnz     loc_18003EE02
0x18003ecf9  lea     r8, aAspnetPerfDll; "aspnet_perf.dll"
0x18003ed00  mov     rdx, r12; unsigned __int64
0x18003ed03  lea     rcx, [rbp+0E50h+var_A60]; unsigned __int16 *
0x18003ed0a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003ed0f  mov     ebx, eax
0x18003ed11  test    eax, eax
0x18003ed13  jnz     loc_18003EE02
0x18003ed19  lea     rcx, [rbp+0E50h+var_A60]; unsigned __int16 *
0x18003ed20  call    ?SupportsPerfShimModel@@YAHPEBG@Z; SupportsPerfShimModel(ushort const *)
0x18003ed25  test    eax, eax
0x18003ed27  jz      loc_18003EDCC
0x18003ed2d  mov     eax, [rbp+0E50h+var_E78]
0x18003ed30  neg     eax
0x18003ed32  lea     rax, [rbp+0E50h+var_E88]
0x18003ed36  sbb     rcx, rcx
0x18003ed39  and     rcx, rax
0x18003ed3c  jnz     short loc_18003ED48
0x18003ed3e  mov     ebx, 80004005h
0x18003ed43  jmp     loc_18003EE02
0x18003ed48  mov     eax, [rcx+0Ch]
0x18003ed4b  lea     r8, aDDDD_0; "%d.%d.%d.%d"
0x18003ed52  mov     r9d, [rcx]
0x18003ed55  mov     edx, 104h; unsigned __int64
0x18003ed5a  mov     [rsp+0F50h+var_F20], eax
0x18003ed5e  mov     eax, [rcx+8]
0x18003ed61  mov     [rsp+0F50h+var_F28], eax
0x18003ed65  mov     eax, [rcx+4]
0x18003ed68  lea     rcx, [rbp+0E50h+Buffer]; Buffer
0x18003ed6f  mov     dword ptr [rsp+0F50h+var_F30], eax
0x18003ed73  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ed78  mov     ebx, eax
0x18003ed7a  test    eax, eax
0x18003ed7c  jnz     loc_18003EE02
0x18003ed82  lea     rdx, [rbp+0E50h+Buffer]; lpData
0x18003ed89  lea     rcx, String1; "ASP.NET"
0x18003ed90  call    ?WriteVersionToPerformanceContextKey@@YAJPEBG0@Z; WriteVersionToPerformanceContextKey(ushort const *,ushort const *)
0x18003ed95  mov     ebx, eax
0x18003ed97  test    eax, eax
0x18003ed99  jnz     short loc_18003EE02
0x18003ed9b  call    IsWow64
0x18003eda0  mov     rcx, rdi; unsigned __int16 *
0x18003eda3  test    eax, eax
0x18003eda5  jnz     short loc_18003EDAE
0x18003eda7  call    ?CallLoadPerfCounterTextStrings@@YAJPEBG@Z; CallLoadPerfCounterTextStrings(ushort const *)
0x18003edac  jmp     short loc_18003EE00
0x18003edae  mov     r8, r12; unsigned __int64
0x18003edb1  lea     rdx, [rbp+0E50h+var_440]; unsigned __int16 *
0x18003edb8  call    ?GetInstallDirectory64@@YAJPEBGPEAG_K@Z; GetInstallDirectory64(ushort const *,ushort *,unsigned __int64)
0x18003edbd  mov     ebx, eax
0x18003edbf  test    eax, eax
0x18003edc1  jnz     short loc_18003EE02
0x18003edc3  lea     rcx, [rbp+0E50h+var_440]
0x18003edca  jmp     short loc_18003EDA7
0x18003edcc  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\AS"...
0x18003edd3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003edda  call    cs:__imp_SHDeleteKeyW
0x18003ede0  lea     rcx, [rsp+0F50h+var_F10]; struct CRegInfo *
0x18003ede5  mov     ebx, r15d
0x18003ede8  call    ?Recreate32BitPerfCountersKey@@YAJPEAVCRegInfo@@@Z; Recreate32BitPerfCountersKey(CRegInfo *)
0x18003eded  call    RunningOn64Bit
0x18003edf2  test    eax, eax
0x18003edf4  jz      short loc_18003EE02
0x18003edf6  lea     rcx, [rsp+0F50h+var_F10]; struct CRegInfo *
0x18003edfb  call    ?Recreate64BitPerfCountersKey@@YAJPEAVCRegInfo@@@Z; Recreate64BitPerfCountersKey(CRegInfo *)
0x18003ee00  mov     ebx, eax
0x18003ee02  lea     r9, aUninstallingPe; "Uninstalling performance counters"
0x18003ee09  mov     [rsp+0F50h+var_F30], r15; unsigned __int16 *
0x18003ee0e  xor     r8d, r8d; unsigned int
0x18003ee11  lea     rdx, aUninstallperfc; "UninstallPerfCounters"
0x18003ee18  mov     ecx, ebx; int
0x18003ee1a  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003ee1f  lea     rcx, [rsp+0F50h+var_F10]; this
0x18003ee24  call    ??1CRegInfo@@QEAA@XZ; CRegInfo::~CRegInfo(void)
0x18003ee29  mov     eax, ebx
0x18003ee2b  mov     rcx, [rbp+0E50h+var_30]
0x18003ee32  xor     rcx, rsp; StackCookie
0x18003ee35  call    __security_check_cookie
0x18003ee3a  lea     r11, [rsp+0F50h+var_20]
0x18003ee42  mov     rbx, [r11+38h]
0x18003ee46  mov     rsi, [r11+40h]
0x18003ee4a  mov     rsp, r11
0x18003ee4d  pop     r15
0x18003ee4f  pop     r14
0x18003ee51  pop     r12
0x18003ee53  pop     rdi
0x18003ee54  pop     rbp
0x18003ee55  retn
```
