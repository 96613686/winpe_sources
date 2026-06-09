# ProcessCmdLineAndRegistryParameters(void)

- ea: `0x100423500`
- end: `0x10042387b`
- name: `?ProcessCmdLineAndRegistryParameters@@YAXXZ`
- size: `891`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100416770`

## callees

- `0x100401580`
- `0x100401800`
- `0x1004021d0`
- `0x1004233a0`
- `0x100423500`
- `0x100440340`
- `0x100446ad0`

## import_xrefs

- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100423537`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100423550`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10042375c`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10042375c`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x10042379e`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004237ab`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004237d2`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004237df`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004237f9`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x100423806`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x100423813`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x100423820`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x10042382d`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x10042383a`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x10042379e`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004237ab`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004237d2`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004237df`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004237f9`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x100423806`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x100423813`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x100423820`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x10042382d`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x10042383a`
- `sqldk!?TurnOff@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004237b8`
- `sqldk!?TurnOff@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004237c5`
- `sqldk!?TurnOff@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004237ec`
- `sqldk!?TurnOff@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x100423847`
- `sqldk!?TurnOff@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004237b8`
- `sqldk!?TurnOff@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004237c5`
- `sqldk!?TurnOff@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1004237ec`
- `sqldk!?TurnOff@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x100423847`
- `sqldk!?GetParameterBySwitchChar@DkParametersProcessor@@QEBAPEBVDkParameter@@_W@Z` at `0x1004235e6`
- `sqldk!?GetParameterBySwitchChar@DkParametersProcessor@@QEBAPEBVDkParameter@@_W@Z` at `0x1004235e6`
- `sqldk!?Execute@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@W4DkParameterFlags@@@Z` at `0x10042359b`
- `sqldk!?Execute@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@W4DkParameterFlags@@@Z` at `0x1004235c0`
- `sqldk!?Execute@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@W4DkParameterFlags@@@Z` at `0x10042359b`
- `sqldk!?Execute@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@W4DkParameterFlags@@@Z` at `0x1004235c0`
- `sqldk!?ProcessBuffer@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@PEB_W_N@Z` at `0x10042357e`
- `sqldk!?ProcessBuffer@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@PEB_W_N@Z` at `0x10042357e`
- `sqldk!?sm_osStatus@SOS_PublicGlobals@@2KA` at `0x10042378a`
- `instapi160!GetSvcInstRootRegPathByName` at `0x1004236c2`
- `instapi160!GetSvcInstRootRegPathByName` at `0x1004236c2`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=2
void ProcessCmdLineAndRegistryParameters(void)
{
  int v0; // eax
  __int64 v1; // rbx
  __int64 v2; // r14
  __int64 v3; // rsi
  __int64 v4; // rbx
  unsigned int v5; // edi
  int v6; // ebx
  int i; // edi
  int v8; // eax
  HKEY v9; // [rsp+40h] [rbp-678h] BYREF
  DWORD v10; // [rsp+48h] [rbp-670h] BYREF
  int v11; // [rsp+4Ch] [rbp-66Ch] BYREF
  int v12; // [rsp+50h] [rbp-668h] BYREF
  HKEY v13[3]; // [rsp+58h] [rbp-660h] BYREF
  int v14[132]; // [rsp+70h] [rbp-648h] BYREF
  int v15[132]; // [rsp+280h] [rbp-438h] BYREF
  BYTE v16[528]; // [rsp+490h] [rbp-228h] BYREF

  v13[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  v0 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 56LL))(s_pServerConf);
  v1 = v0;
  if ( v0 > 0 )
  {
    v2 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 64LL))(s_pServerConf);
    v3 = v1;
    v4 = 0;
    while ( 1 )
    {
      v5 = DkParametersProcessor::ProcessBuffer(&qword_1004A1820, *(_QWORD *)(v2 + 8 * v4), 0);
      if ( v5 )
        break;
      if ( ++v4 >= v3 )
      {
        v5 = DkParametersProcessor::Execute(&qword_1004A1820, 0);
        if ( !v5 )
          goto LABEL_7;
        break;
      }
    }
    LogInvalidParameterInCommandLine(v5, &qword_1004A1820);
    goto LABEL_8;
  }
LABEL_7:
  v5 = DkParametersProcessor::Execute(&qword_1004A1720, 0);
  if ( v5 )
LABEL_8:
    LogInvalidParameterInCommandLine(v5, &qword_1004A1720);
  if ( DkParametersProcessor::GetParameterBySwitchChar((DkParametersProcessor *)&qword_1004A1720, 0x73u)
    || *((_DWORD *)qword_10049F360 + 3636)
    || *((_DWORD *)qword_10049F360 + 3624) )
  {
    goto LABEL_29;
  }
  v9 = 0;
  v6 = 0;
  if ( !(unsigned int)IniRegOpenKeyExW(
                        -2147483646,
                        (int)L"SOFTWARE\\Microsoft\\Microsoft SQL Server\\Instance Names\\SQL",
                        0,
                        131097,
                        &v9) )
  {
    for ( i = 0; ; ++i )
    {
      v11 = 260;
      v10 = 520;
      v8 = IniRegEnumValueW((int)v9, i, (int)v14, (int)&v11, 0, 0, v16, &v10);
      if ( v8 != 234 )
      {
        if ( v8 )
          break;
        v12 = 260;
        if ( (unsigned int)GetSvcInstRootRegPathByName(v14, 0, v15, &v12) )
        {
          v13[0] = 0;
          if ( !(unsigned int)IniRegOpenKeyExW(-2147483646, (int)v15, 0, 131097, v13) && (unsigned int)++v6 >= 2 )
          {
            if ( v13[0] )
              IniRegCloseKey(v13[0]);
            if ( v9 )
              IniRegCloseKey(v9);
            scierrlogwithstate(0xC2F5u, 1, 1);
            *((_DWORD *)qword_10049F360 + 10544) = 0;
            SQLExit(325);
            goto LABEL_29;
          }
          if ( v13[0] )
            IniRegCloseKey(v13[0]);
        }
      }
    }
  }
  if ( v9 )
    IniRegCloseKey(v9);
LABEL_29:
  if ( (*((_DWORD *)qword_10049F360 + 12127) & 0x2000) != 0 )
  {
    SOS_PublicGlobals::sm_osStatus |= 0x30000u;
    CGlobalTraceFlags::TurnOn(9038, 0);
    CGlobalTraceFlags::TurnOn(8076, 0);
    CGlobalTraceFlags::TurnOff(834, 0);
    CGlobalTraceFlags::TurnOff(878, 0);
    CGlobalTraceFlags::TurnOn(851, 0);
    CGlobalTraceFlags::TurnOn(835, 0);
    CGlobalTraceFlags::TurnOff(840, 0);
    CGlobalTraceFlags::TurnOn(8052, 0);
    CGlobalTraceFlags::TurnOn(833, 0);
    CGlobalTraceFlags::TurnOn(851, 0);
    CGlobalTraceFlags::TurnOn(3425, 0);
    CGlobalTraceFlags::TurnOn(822, 0);
    CGlobalTraceFlags::TurnOn(5504, 0);
    CGlobalTraceFlags::TurnOff(3513, 0);
  }
}

```

## disassembly

```asm
0x100423500  mov     rax, rsp
0x100423503  push    r14
0x100423505  sub     rsp, 6B0h
0x10042350c  mov     [rsp+6B8h+var_658], 0FFFFFFFFFFFFFFFEh
0x100423515  mov     [rax+8], rbx
0x100423519  mov     [rax+10h], rbp
0x10042351d  mov     [rax+18h], rsi
0x100423521  mov     [rax+20h], rdi
0x100423525  mov     rax, cs:__security_cookie
0x10042352c  xor     rax, rsp
0x10042352f  mov     [rsp+6B8h+var_18], rax
0x100423537  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x10042353e  mov     rcx, [rax]
0x100423541  mov     rax, [rcx]
0x100423544  call    qword ptr [rax+38h]
0x100423547  movsxd  rbx, eax
0x10042354a  xor     ebp, ebp
0x10042354c  test    eax, eax
0x10042354e  jle     short loc_1004235B7
0x100423550  mov     rcx, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100423557  mov     rcx, [rcx]
0x10042355a  mov     rdx, [rcx]
0x10042355d  call    qword ptr [rdx+40h]
0x100423560  mov     r14, rax
0x100423563  mov     rsi, rbx
0x100423566  test    ebx, ebx
0x100423568  jle     short loc_100423592
0x10042356a  mov     ebx, ebp
0x10042356c  nop     dword ptr [rax+00h]
0x100423570  xor     r8d, r8d
0x100423573  mov     rdx, [r14+rbx*8]
0x100423577  lea     rcx, qword_1004A1820
0x10042357e  call    cs:__imp_?ProcessBuffer@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@PEB_W_N@Z; DkParametersProcessor::ProcessBuffer(wchar_t const *,bool)
0x100423584  mov     edi, eax
0x100423586  test    eax, eax
0x100423588  jnz     short loc_1004235A7
0x10042358a  inc     rbx
0x10042358d  cmp     rbx, rsi
0x100423590  jl      short loc_100423570
0x100423592  xor     edx, edx
0x100423594  lea     rcx, qword_1004A1820
0x10042359b  call    cs:__imp_?Execute@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@W4DkParameterFlags@@@Z; DkParametersProcessor::Execute(DkParameterFlags)
0x1004235a1  mov     edi, eax
0x1004235a3  test    eax, eax
0x1004235a5  jz      short loc_1004235B7
0x1004235a7  lea     rdx, qword_1004A1820
0x1004235ae  mov     ecx, edi
0x1004235b0  call    ?LogInvalidParameterInCommandLine@@YAXW4DkParameterErrorEnum@@AEBVDkParametersProcessor@@@Z; LogInvalidParameterInCommandLine(DkParameterErrorEnum,DkParametersProcessor const &)
0x1004235b5  jmp     short loc_1004235CC
0x1004235b7  xor     edx, edx
0x1004235b9  lea     rcx, qword_1004A1720
0x1004235c0  call    cs:__imp_?Execute@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@W4DkParameterFlags@@@Z; DkParametersProcessor::Execute(DkParameterFlags)
0x1004235c6  mov     edi, eax
0x1004235c8  test    eax, eax
0x1004235ca  jz      short loc_1004235DA
0x1004235cc  lea     rdx, qword_1004A1720
0x1004235d3  mov     ecx, edi
0x1004235d5  call    ?LogInvalidParameterInCommandLine@@YAXW4DkParameterErrorEnum@@AEBVDkParametersProcessor@@@Z; LogInvalidParameterInCommandLine(DkParameterErrorEnum,DkParametersProcessor const &)
0x1004235da  mov     edx, 73h ; 's'
0x1004235df  lea     rcx, qword_1004A1720
0x1004235e6  call    cs:__imp_?GetParameterBySwitchChar@DkParametersProcessor@@QEBAPEBVDkParameter@@_W@Z; DkParametersProcessor::GetParameterBySwitchChar(wchar_t)
0x1004235ec  test    rax, rax
0x1004235ef  jnz     loc_100423773
0x1004235f5  mov     rax, cs:qword_10049F360
0x1004235fc  cmp     [rax+38D0h], ebp
0x100423602  jnz     loc_100423773
0x100423608  cmp     [rax+38A0h], ebp
0x10042360e  jnz     loc_100423773
0x100423614  mov     [rsp+6B8h+var_678], rbp
0x100423619  mov     ebx, ebp
0x10042361b  lea     rax, [rsp+6B8h+var_678]
0x100423620  mov     [rsp+6B8h+var_698], rax; PHKEY
0x100423625  mov     r9d, 20019h; int
0x10042362b  xor     r8d, r8d; int
0x10042362e  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Microsoft SQL Serv"...
0x100423635  mov     rcx, 0FFFFFFFF80000002h; int
0x10042363c  call    IniRegOpenKeyExW
0x100423641  test    eax, eax
0x100423643  jnz     loc_100423764
0x100423649  mov     edi, ebp
0x10042364b  nop     dword ptr [rax+rax+00h]
0x100423650  mov     [rsp+6B8h+var_66C], 104h
0x100423658  mov     [rsp+6B8h+var_670], 208h
0x100423660  lea     rax, [rsp+6B8h+var_670]
0x100423665  mov     [rsp+6B8h+var_680], rax; LPDWORD
0x10042366a  lea     rax, [rsp+6B8h+var_228]
0x100423672  mov     [rsp+6B8h+var_688], rax; LPBYTE
0x100423677  mov     [rsp+6B8h+var_690], rbp; LPDWORD
0x10042367c  mov     [rsp+6B8h+var_698], rbp; LPDWORD
0x100423681  lea     r9, [rsp+6B8h+var_66C]; int
0x100423686  lea     r8, [rsp+6B8h+var_648]; int
0x10042368b  mov     edx, edi; int
0x10042368d  mov     rcx, [rsp+6B8h+var_678]; int
0x100423692  call    IniRegEnumValueW
0x100423697  cmp     eax, 0EAh
0x10042369c  jz      short loc_100423712
0x10042369e  test    eax, eax
0x1004236a0  jnz     loc_100423764
0x1004236a6  mov     [rsp+6B8h+var_668], 104h
0x1004236ae  lea     r9, [rsp+6B8h+var_668]
0x1004236b3  lea     r8, [rsp+6B8h+var_438]
0x1004236bb  xor     edx, edx
0x1004236bd  lea     rcx, [rsp+6B8h+var_648]
0x1004236c2  call    cs:__imp_GetSvcInstRootRegPathByName
0x1004236c8  test    eax, eax
0x1004236ca  jz      short loc_100423712
0x1004236cc  mov     [rsp+6B8h+var_660], rbp
0x1004236d1  lea     rax, [rsp+6B8h+var_660]
0x1004236d6  mov     [rsp+6B8h+var_698], rax; PHKEY
0x1004236db  mov     r9d, 20019h; int
0x1004236e1  xor     r8d, r8d; int
0x1004236e4  lea     rdx, [rsp+6B8h+var_438]; int
0x1004236ec  mov     rcx, 0FFFFFFFF80000002h; int
0x1004236f3  call    IniRegOpenKeyExW
0x1004236f8  test    eax, eax
0x1004236fa  jnz     short loc_100423703
0x1004236fc  inc     ebx
0x1004236fe  cmp     ebx, 2
0x100423701  jnb     short loc_100423719
0x100423703  mov     rcx, [rsp+6B8h+var_660]
0x100423708  test    rcx, rcx
0x10042370b  jz      short loc_100423712
0x10042370d  call    IniRegCloseKey
0x100423712  inc     edi
0x100423714  jmp     loc_100423650
0x100423719  mov     rcx, [rsp+6B8h+var_660]
0x10042371e  test    rcx, rcx
0x100423721  jz      short loc_100423729
0x100423723  call    IniRegCloseKey
0x100423728  nop
0x100423729  mov     rcx, [rsp+6B8h+var_678]
0x10042372e  test    rcx, rcx
0x100423731  jz      short loc_100423738
0x100423733  call    IniRegCloseKey
0x100423738  mov     edx, 1; int
0x10042373d  mov     ecx, 0C2F5h; unsigned int
0x100423742  mov     r8d, edx; int
0x100423745  call    ?scierrlogwithstate@@YAXKHHZZ; scierrlogwithstate(ulong,int,int,...)
0x10042374a  mov     rax, cs:qword_10049F360
0x100423751  mov     [rax+0A4C0h], ebp
0x100423757  mov     ecx, 145h
0x10042375c  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@@Z; SQLExit(SQLEXITCODE)
0x100423762  jmp     short loc_100423773
0x100423764  mov     rcx, [rsp+6B8h+var_678]
0x100423769  test    rcx, rcx
0x10042376c  jz      short loc_100423773
0x10042376e  call    IniRegCloseKey
0x100423773  mov     rax, cs:qword_10049F360
0x10042377a  test    dword ptr [rax+0BD7Ch], 2000h
0x100423784  jz      loc_10042384D
0x10042378a  mov     rax, cs:__imp_?sm_osStatus@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStatus
0x100423791  or      dword ptr [rax], 30000h
0x100423797  mov     ecx, 234Eh
0x10042379c  xor     edx, edx
0x10042379e  call    cs:__imp_?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOn(ushort,CGlobalTraceFlags::FlagUsage)
0x1004237a4  mov     ecx, 1F8Ch
0x1004237a9  xor     edx, edx
0x1004237ab  call    cs:__imp_?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOn(ushort,CGlobalTraceFlags::FlagUsage)
0x1004237b1  mov     ecx, 342h
0x1004237b6  xor     edx, edx
0x1004237b8  call    cs:__imp_?TurnOff@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOff(ushort,CGlobalTraceFlags::FlagUsage)
0x1004237be  mov     ecx, 36Eh
0x1004237c3  xor     edx, edx
0x1004237c5  call    cs:__imp_?TurnOff@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOff(ushort,CGlobalTraceFlags::FlagUsage)
0x1004237cb  mov     ecx, 353h
0x1004237d0  xor     edx, edx
0x1004237d2  call    cs:__imp_?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOn(ushort,CGlobalTraceFlags::FlagUsage)
0x1004237d8  mov     ecx, 343h
0x1004237dd  xor     edx, edx
0x1004237df  call    cs:__imp_?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOn(ushort,CGlobalTraceFlags::FlagUsage)
0x1004237e5  mov     ecx, 348h
0x1004237ea  xor     edx, edx
0x1004237ec  call    cs:__imp_?TurnOff@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOff(ushort,CGlobalTraceFlags::FlagUsage)
0x1004237f2  mov     ecx, 1F74h
0x1004237f7  xor     edx, edx
0x1004237f9  call    cs:__imp_?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOn(ushort,CGlobalTraceFlags::FlagUsage)
0x1004237ff  mov     ecx, 341h
0x100423804  xor     edx, edx
0x100423806  call    cs:__imp_?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOn(ushort,CGlobalTraceFlags::FlagUsage)
0x10042380c  mov     ecx, 353h
0x100423811  xor     edx, edx
0x100423813  call    cs:__imp_?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOn(ushort,CGlobalTraceFlags::FlagUsage)
0x100423819  mov     ecx, 0D61h
0x10042381e  xor     edx, edx
0x100423820  call    cs:__imp_?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOn(ushort,CGlobalTraceFlags::FlagUsage)
0x100423826  mov     ecx, 336h
0x10042382b  xor     edx, edx
0x10042382d  call    cs:__imp_?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOn(ushort,CGlobalTraceFlags::FlagUsage)
0x100423833  mov     ecx, 1580h
0x100423838  xor     edx, edx
0x10042383a  call    cs:__imp_?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOn(ushort,CGlobalTraceFlags::FlagUsage)
0x100423840  mov     ecx, 0DB9h
0x100423845  xor     edx, edx
0x100423847  call    cs:__imp_?TurnOff@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOff(ushort,CGlobalTraceFlags::FlagUsage)
0x10042384d  mov     rcx, [rsp+6B8h+var_18]
0x100423855  xor     rcx, rsp; StackCookie
0x100423858  call    __security_check_cookie
0x10042385d  lea     r11, [rsp+6B8h+var_8]
0x100423865  mov     rbx, [r11+10h]
0x100423869  mov     rbp, [r11+18h]
0x10042386d  mov     rsi, [r11+20h]
0x100423871  mov     rdi, [r11+28h]
0x100423875  mov     rsp, r11
0x100423878  pop     r14
0x10042387a  retn
```
