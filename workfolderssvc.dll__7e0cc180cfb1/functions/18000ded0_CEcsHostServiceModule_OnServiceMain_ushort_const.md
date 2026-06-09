# CEcsHostServiceModule::OnServiceMain(ushort const *)

- ea: `0x18000ded0`
- end: `0x18000e2d0`
- name: `?OnServiceMain@CEcsHostServiceModule@@QEAAXPEBG@Z`
- size: `1024`
- prototype: `void(CEcsHostServiceModule *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006a50`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x18000ce40`
- `0x18000ded0`
- `0x18000f5d4`
- `0x18000f958`
- `0x18000fb80`
- `0x18000ffd8`
- `0x180011314`
- `0x18001133c`
- `0x1800b178c`
- `0x1800b1a5c`
- `0x1800b1e44`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x18000e1bd`
- `KERNEL32!DebugBreak` at `0x18000e1bd`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x18000df83`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x18000df83`
- `ext-ms-win-ntuser-powermanagement-l1-1-0!RegisterPowerSettingNotification` at `0x18000dff6`
- `ext-ms-win-ntuser-powermanagement-l1-1-0!RegisterPowerSettingNotification` at `0x18000dff6`
- `USER32!RegisterDeviceNotificationW` at `0x18000e09c`
- `USER32!RegisterDeviceNotificationW` at `0x18000e09c`

## string_xrefs

- `0x18000df56`: `CEcsHostServiceModule::OnServiceMain`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CEcsHostServiceModule::OnServiceMain(CEcsHostServiceModule *this, const unsigned __int16 *a2)
{
  _BYTE *v3; // rax
  bool v4; // cf
  char v5; // al
  CEcsHostServiceModule *v6; // rcx
  const unsigned __int16 *v7; // rdx
  CEcsHostServiceModule *v8; // rcx
  signed int v9; // r9d
  CEcsHostServiceModule *v10; // rcx
  CEcsHostServiceModule *v11; // rcx
  CEcsHostServiceModule *v12; // rcx
  DWORD v13; // eax
  CEcsHostServiceModule *v14; // rcx
  CEcsHostServiceModule *v15; // rcx
  __int64 v16; // [rsp+30h] [rbp-A8h]
  int v17; // [rsp+40h] [rbp-98h] BYREF
  int v18; // [rsp+44h] [rbp-94h]
  char v19; // [rsp+48h] [rbp-90h]
  const char *v20; // [rsp+50h] [rbp-88h]
  __int64 v21; // [rsp+58h] [rbp-80h]
  int v22; // [rsp+60h] [rbp-78h] BYREF
  int v23; // [rsp+64h] [rbp-74h]
  int pExceptionObject; // [rsp+68h] [rbp-70h] BYREF
  int LastFailureAsHRESULT; // [rsp+6Ch] [rbp-6Ch] BYREF
  int v26; // [rsp+70h] [rbp-68h] BYREF
  int v27; // [rsp+78h] [rbp-60h] BYREF
  HKEY v28; // [rsp+80h] [rbp-58h] BYREF
  __int64 v29; // [rsp+88h] [rbp-50h] BYREF
  int v30; // [rsp+90h] [rbp-48h] BYREF
  const ATL::CAtlException *v31; // [rsp+98h] [rbp-40h] BYREF
  int NotificationFilter; // [rsp+A0h] [rbp-38h] BYREF
  __int64 NotificationFilter_4; // [rsp+A4h] [rbp-34h]
  GUID NotificationFilter_12; // [rsp+ACh] [rbp-2Ch]
  int v35; // [rsp+BCh] [rbp-1Ch]

  v23 = 0;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_7:
      v5 = 0;
      goto LABEL_8;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
      v3 = WPP_GLOBAL_Control;
    }
  }
  if ( (v3[68] & 8) == 0 )
    goto LABEL_7;
  v4 = v3[65] < 6u;
  v5 = 1;
  if ( v4 )
    goto LABEL_7;
LABEL_8:
  v17 = 0;
  v18 = 152;
  v19 = v5;
  v20 = "CEcsHostServiceModule::OnServiceMain";
  v21 = 0;
  try
  {
    CEcsHostServiceModule::Reset(this);
    ServiceStatus.dwCurrentState = 2;
    hServiceStatus = RegisterServiceCtrlHandlerExW(a2, CEcsHostServiceModule::_Handler, 0);
    if ( !hServiceStatus )
    {
      HIWORD(v18) = 162;
      pExceptionObject = EcsGetLastFailureAsHRESULT();
      throw (long *)&pExceptionObject;
    }
    v17 = 0;
    LOWORD(v18) = 162;
    CEcsHostServiceModule::Initialize((CEcsHostServiceModule *)&_ServiceModule, a2);
    RegistrationHandle = RegisterPowerSettingNotification(hServiceStatus, &GUID_CONSOLE_DISPLAY_STATE, 1u);
    if ( !RegistrationHandle )
    {
      HIWORD(v18) = 171;
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      throw (long *)&LastFailureAsHRESULT;
    }
    v17 = 0;
    LOWORD(v18) = 171;
    NotificationFilter_4 = 5;
    NotificationFilter = 32;
    NotificationFilter_12 = GUID_DEVINTERFACE_VOLUME;
    v35 = 0;
    Handle = RegisterDeviceNotificationW(hServiceStatus, &NotificationFilter, 1u);
    if ( !Handle )
    {
      HIWORD(v18) = 182;
      v26 = EcsGetLastFailureAsHRESULT();
      throw (long *)&v26;
    }
    v17 = 0;
    LOWORD(v18) = 182;
    CEcsHostServiceModule::SetServiceStatus((CEcsHostServiceModule *)0xB6, 2u, 1);
    ServiceStatus.dwControlsAccepted = 197;
    CEcsHostServiceModule::SetServiceStatus(v6, 4u, 1);
    v29 = -2147483646;
    CEcsRegKey::Get(
      &v28,
      (HKEY *)&v29,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\WorkFolders",
      131097,
      0,
      0,
      0,
      0);
    v23 = 0;
    CEcsRegKey::Close((CEcsRegKey *)&v29);
    if ( v28 )
    {
      v27 = 0;
      v22 = 0;
      CEcsRegKey::GetGenericValue<unsigned long,unsigned long>(&v28, L"BreakOnInitialize", &v27, v9, &v22, &v22, v16, 0);
      if ( v22 )
        DebugBreak();
    }
    CEcsHostServiceModule::Run(v8, v7);
    CEcsHostServiceModule::SetServiceStatus(v10, 3u, 1);
    CEcsHostServiceModule::Stop(v11);
    CEcsHostServiceModule::SetServiceStatus(v12, 1u, 1);
    CEcsRegKey::Close((CEcsRegKey *)&v28);
  }
  catch ( long v30 )
  {
    v17 = v30;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v18) = 220;
    v17 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v18) = 220;
    v17 = -2147418113;
  }
  catch ( const ATL::CAtlException *v31 )
  {
    HIWORD(v18) = 220;
    v17 = *(_DWORD *)v31;
  }
  v13 = v17;
  if ( v17 < 0 )
  {
    v14 = (CEcsHostServiceModule *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
      v13 = v17;
    }
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = v13;
    CEcsHostServiceModule::Stop(v14);
    if ( hServiceStatus )
    {
      CEcsHostServiceModule::SetServiceStatus(v15, 1u, 0);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
    }
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v17);
}

```

## disassembly

```asm
0x18000ded0  mov     [rsp+arg_0], rbx
0x18000ded5  mov     [rsp+arg_10], rsi
0x18000deda  push    rdi
0x18000dedb  sub     rsp, 0D0h
0x18000dee2  mov     rax, cs:__security_cookie
0x18000dee9  xor     rax, rsp
0x18000deec  mov     [rsp+0D8h+var_18], rax
0x18000def4  mov     rsi, rdx
0x18000def7  xor     ebx, ebx
0x18000def9  mov     [rsp+0D8h+var_74], ebx
0x18000defd  lea     rdi, WPP_GLOBAL_Control
0x18000df04  mov     rax, cs:WPP_GLOBAL_Control
0x18000df0b  cmp     rax, rdi
0x18000df0e  jz      short loc_18000DF36
0x18000df10  test    byte ptr [rax+44h], 8
0x18000df14  jz      short loc_18000DF44
0x18000df16  cmp     byte ptr [rax+41h], 6
0x18000df1a  jb      short loc_18000DF36
0x18000df1c  lea     edx, [rbx+0Bh]
0x18000df1f  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000df26  mov     rcx, [rax+38h]
0x18000df2a  call    WPP_SF_
0x18000df2f  mov     rax, cs:WPP_GLOBAL_Control
0x18000df36  test    byte ptr [rax+44h], 8
0x18000df3a  jz      short loc_18000DF44
0x18000df3c  cmp     byte ptr [rax+41h], 6
0x18000df40  mov     al, 1
0x18000df42  jnb     short loc_18000DF46
0x18000df44  mov     al, bl
0x18000df46  mov     [rsp+0D8h+var_98], ebx
0x18000df4a  mov     [rsp+0D8h+var_94], 98h
0x18000df52  mov     [rsp+0D8h+var_90], al
0x18000df56  lea     rax, aCecshostservic_10; "CEcsHostServiceModule::OnServiceMain"
0x18000df5d  mov     [rsp+0D8h+var_88], rax
0x18000df62  mov     [rsp+0D8h+var_80], rbx
0x18000df67  call    ?Reset@CEcsHostServiceModule@@AEAAXXZ; CEcsHostServiceModule::Reset(void)
0x18000df6c  mov     cs:ServiceStatus.dwCurrentState, 2
0x18000df76  xor     r8d, r8d; lpContext
0x18000df79  lea     rdx, ?_Handler@CEcsHostServiceModule@@CAKKKPEAX0@Z; lpHandlerProc
0x18000df80  mov     rcx, rsi; lpServiceName
0x18000df83  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000df89  mov     cs:hServiceStatus, rax
0x18000df90  mov     ecx, [rsp+0D8h+var_98]
0x18000df94  mov     [rsp+0D8h+var_98], ecx
0x18000df98  test    rax, rax
0x18000df9b  jnz     short loc_18000DFC5
0x18000df9d  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18000dfa2  mov     [rsp+0D8h+var_98], eax
0x18000dfa6  mov     ecx, 0A2h
0x18000dfab  mov     word ptr [rsp+0D8h+var_94+2], cx
0x18000dfb0  mov     [rsp+0D8h+pExceptionObject], eax
0x18000dfb4  lea     rdx, _TI1J; pThrowInfo
0x18000dfbb  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18000dfc0  call    _CxxThrowException_0
0x18000dfc5  mov     [rsp+0D8h+var_98], ebx
0x18000dfc9  mov     ecx, 0A2h
0x18000dfce  mov     word ptr [rsp+0D8h+var_94], cx
0x18000dfd3  mov     rdx, rsi; unsigned __int16 *
0x18000dfd6  lea     rcx, ?_ServiceModule@@3VCEcsHostServiceModule@@A; this
0x18000dfdd  call    ?Initialize@CEcsHostServiceModule@@AEAAXPEBG@Z; CEcsHostServiceModule::Initialize(ushort const *)
0x18000dfe2  mov     r8d, 1; Flags
0x18000dfe8  lea     rdx, GUID_CONSOLE_DISPLAY_STATE; PowerSettingGuid
0x18000dfef  mov     rcx, cs:hServiceStatus; hRecipient
0x18000dff6  call    cs:__imp_RegisterPowerSettingNotification
0x18000dffc  mov     cs:RegistrationHandle, rax
0x18000e003  mov     ecx, [rsp+0D8h+var_98]
0x18000e007  mov     [rsp+0D8h+var_98], ecx
0x18000e00b  test    rax, rax
0x18000e00e  jnz     short loc_18000E038
0x18000e010  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18000e015  mov     [rsp+0D8h+var_98], eax
0x18000e019  mov     ecx, 0ABh
0x18000e01e  mov     word ptr [rsp+0D8h+var_94+2], cx
0x18000e023  mov     [rsp+0D8h+var_6C], eax
0x18000e027  lea     rdx, _TI1J; pThrowInfo
0x18000e02e  lea     rcx, [rsp+0D8h+var_6C]; pExceptionObject
0x18000e033  call    _CxxThrowException_0
0x18000e038  mov     [rsp+0D8h+var_98], ebx
0x18000e03c  mov     ecx, 0ABh
0x18000e041  mov     word ptr [rsp+0D8h+var_94], cx
0x18000e046  xorps   xmm0, xmm0
0x18000e049  movups  [rsp+0D8h+NotificationFilter], xmm0
0x18000e051  movups  [rsp+0D8h+var_28], xmm0
0x18000e059  mov     dword ptr [rsp+0D8h+NotificationFilter+4], 5
0x18000e064  mov     dword ptr [rsp+0D8h+NotificationFilter], 20h ; ' '
0x18000e06f  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_VOLUME.Data1
0x18000e076  movdqu  [rsp+0D8h+NotificationFilter+0Ch], xmm0
0x18000e07f  mov     word ptr [rsp+0D8h+var_28+0Ch], bx
0x18000e087  mov     r8d, 1; Flags
0x18000e08d  lea     rdx, [rsp+0D8h+NotificationFilter]; NotificationFilter
0x18000e095  mov     rcx, cs:hServiceStatus; hRecipient
0x18000e09c  call    cs:__imp_RegisterDeviceNotificationW
0x18000e0a2  mov     cs:Handle, rax
0x18000e0a9  mov     ecx, [rsp+0D8h+var_98]
0x18000e0ad  mov     [rsp+0D8h+var_98], ecx
0x18000e0b1  test    rax, rax
0x18000e0b4  jnz     short loc_18000E0DE
0x18000e0b6  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18000e0bb  mov     [rsp+0D8h+var_98], eax
0x18000e0bf  mov     ecx, 0B6h
0x18000e0c4  mov     word ptr [rsp+0D8h+var_94+2], cx
0x18000e0c9  mov     [rsp+0D8h+var_68], eax
0x18000e0cd  lea     rdx, _TI1J; pThrowInfo
0x18000e0d4  lea     rcx, [rsp+0D8h+var_68]; pExceptionObject
0x18000e0d9  call    _CxxThrowException_0
0x18000e0de  mov     [rsp+0D8h+var_98], ebx
0x18000e0e2  mov     ecx, 0B6h; this
0x18000e0e7  mov     word ptr [rsp+0D8h+var_94], cx
0x18000e0ec  mov     r8b, 1; bool
0x18000e0ef  mov     edx, 2; unsigned int
0x18000e0f4  call    ?SetServiceStatus@CEcsHostServiceModule@@AEAAXK_N@Z; CEcsHostServiceModule::SetServiceStatus(ulong,bool)
0x18000e0f9  mov     cs:ServiceStatus.dwControlsAccepted, 0C5h
0x18000e103  mov     r8b, 1; bool
0x18000e106  mov     edx, 4; unsigned int
0x18000e10b  call    ?SetServiceStatus@CEcsHostServiceModule@@AEAAXK_N@Z; CEcsHostServiceModule::SetServiceStatus(ulong,bool)
0x18000e110  nop
0x18000e111  mov     [rsp+0D8h+var_50], 0FFFFFFFF80000002h
0x18000e11d  mov     [rsp+0D8h+var_74], 1
0x18000e125  mov     byte ptr [rsp+0D8h+var_A0], bl
0x18000e129  mov     [rsp+0D8h+var_A8], rbx
0x18000e12e  mov     [rsp+0D8h+var_B0], rbx
0x18000e133  mov     byte ptr [rsp+0D8h+var_B8], bl
0x18000e137  mov     r9d, 20019h
0x18000e13d  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e144  lea     rdx, [rsp+0D8h+var_50]
0x18000e14c  lea     rcx, [rsp+0D8h+var_58]
0x18000e154  call    ?Get@CEcsRegKey@@SA?AV1@AEBV1@PEBGK_NPEAU_SECURITY_ATTRIBUTES@@PEA_N2@Z; CEcsRegKey::Get(CEcsRegKey const &,ushort const *,ulong,bool,_SECURITY_ATTRIBUTES *,bool *,bool)
0x18000e159  nop
0x18000e15a  mov     eax, 1
0x18000e15f  and     eax, 0FFFFFFFEh
0x18000e162  mov     [rsp+0D8h+var_74], eax
0x18000e166  lea     rcx, [rsp+0D8h+var_50]; this
0x18000e16e  call    ?Close@CEcsRegKey@@QEAAXXZ; CEcsRegKey::Close(void)
0x18000e173  cmp     [rsp+0D8h+var_58], rbx
0x18000e17b  jz      short loc_18000E1C3
0x18000e17d  mov     [rsp+0D8h+var_60], ebx
0x18000e181  mov     [rsp+0D8h+var_78], ebx
0x18000e185  mov     [rsp+0D8h+var_A0], rbx
0x18000e18a  lea     rax, [rsp+0D8h+var_78]
0x18000e18f  mov     [rsp+0D8h+var_B0], rax
0x18000e194  lea     rax, [rsp+0D8h+var_78]
0x18000e199  mov     [rsp+0D8h+var_B8], rax
0x18000e19e  lea     r8, [rsp+0D8h+var_60]
0x18000e1a3  lea     rdx, aBreakoninitial; "BreakOnInitialize"
0x18000e1aa  lea     rcx, [rsp+0D8h+var_58]
0x18000e1b2  call    ??$GetGenericValue@KK@CEcsRegKey@@AEBA_NPEBGAEBKKAEAKPEAXKPEA_N@Z; CEcsRegKey::GetGenericValue<ulong,ulong>(ushort const *,ulong const &,ulong,ulong &,void *,ulong,bool *)
0x18000e1b7  cmp     [rsp+0D8h+var_78], ebx
0x18000e1bb  jbe     short loc_18000E1C3
0x18000e1bd  call    cs:__imp_DebugBreak
0x18000e1c3  call    ?Run@CEcsHostServiceModule@@AEAAXPEBG@Z; CEcsHostServiceModule::Run(ushort const *)
0x18000e1c8  mov     r8b, 1; bool
0x18000e1cb  mov     edx, 3; unsigned int
0x18000e1d0  call    ?SetServiceStatus@CEcsHostServiceModule@@AEAAXK_N@Z; CEcsHostServiceModule::SetServiceStatus(ulong,bool)
0x18000e1d5  call    ?Stop@CEcsHostServiceModule@@AEAAXXZ; CEcsHostServiceModule::Stop(void)
0x18000e1da  mov     r8b, 1; bool
0x18000e1dd  mov     edx, 1; unsigned int
0x18000e1e2  call    ?SetServiceStatus@CEcsHostServiceModule@@AEAAXK_N@Z; CEcsHostServiceModule::SetServiceStatus(ulong,bool)
0x18000e1e7  nop
0x18000e1e8  lea     rcx, [rsp+0D8h+var_58]; this
0x18000e1f0  call    ?Close@CEcsRegKey@@QEAAXXZ; CEcsRegKey::Close(void)
0x18000e1f5  nop
0x18000e1f6  jmp     short loc_18000E207
0x18000e1f8  jmp     short loc_18000E1FE
0x18000e1fa  jmp     short loc_18000E1FE
0x18000e1fc  jmp     short $+2
0x18000e1fe  lea     rdi, WPP_GLOBAL_Control
0x18000e205  xor     ebx, ebx
0x18000e207  mov     eax, [rsp+0D8h+var_98]
0x18000e20b  test    eax, eax
0x18000e20d  jns     loc_18000E2A1
0x18000e213  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e21a  cmp     rcx, rdi
0x18000e21d  jz      short loc_18000E247
0x18000e21f  test    byte ptr [rcx+44h], 8
0x18000e223  jz      short loc_18000E247
0x18000e225  cmp     byte ptr [rcx+41h], 2
0x18000e229  jb      short loc_18000E247
0x18000e22b  mov     edx, 0Ch
0x18000e230  mov     r9d, eax
0x18000e233  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000e23a  mov     rcx, [rcx+38h]
0x18000e23e  call    WPP_SF_d
0x18000e243  mov     eax, [rsp+0D8h+var_98]
0x18000e247  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x18000e251  mov     cs:ServiceStatus.dwServiceSpecificExitCode, eax
0x18000e257  call    ?Stop@CEcsHostServiceModule@@AEAAXXZ; CEcsHostServiceModule::Stop(void)
0x18000e25c  cmp     cs:hServiceStatus, rbx
0x18000e263  jz      short loc_18000E273
0x18000e265  xor     r8d, r8d; bool
0x18000e268  lea     edx, [r8+1]; unsigned int
0x18000e26c  call    ?SetServiceStatus@CEcsHostServiceModule@@AEAAXK_N@Z; CEcsHostServiceModule::SetServiceStatus(ulong,bool)
0x18000e271  jmp     short loc_18000E2A1
0x18000e273  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e27a  cmp     rcx, rdi
0x18000e27d  jz      short loc_18000E2A1
0x18000e27f  test    byte ptr [rcx+44h], 8
0x18000e283  jz      short loc_18000E2A1
0x18000e285  cmp     byte ptr [rcx+41h], 2
0x18000e289  jb      short loc_18000E2A1
0x18000e28b  mov     edx, 0Dh
0x18000e290  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000e297  mov     rcx, [rcx+38h]
0x18000e29b  call    WPP_SF_
0x18000e2a0  nop
0x18000e2a1  lea     rcx, [rsp+0D8h+var_98]; this
0x18000e2a6  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18000e2ab  mov     rcx, [rsp+0D8h+var_18]
0x18000e2b3  xor     rcx, rsp; StackCookie
0x18000e2b6  call    __security_check_cookie
0x18000e2bb  lea     r11, [rsp+0D8h+var_8]
0x18000e2c3  mov     rbx, [r11+10h]
0x18000e2c7  mov     rsi, [r11+20h]
0x18000e2cb  mov     rsp, r11
0x18000e2ce  pop     rdi
0x18000e2cf  retn
```
