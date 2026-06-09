# PAL_System_Win32_ThreadUnRegisterWindowClass(void)

- ea: `0x1800365d4`
- end: `0x18003681d`
- name: `?PAL_System_Win32_ThreadUnRegisterWindowClass@@YAJXZ`
- size: `585`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001a8f0`

## callees

- `0x1800011c8`
- `0x1800014c0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000f79c`
- `0x1800365d4`
- `0x180037208`
- `0x180047ebe`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800366e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800366e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036747`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800366d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800366d7`
- `USER32!UnregisterClassW` at `0x180036739`
- `USER32!UnregisterClassW` at `0x180036739`

## string_xrefs

- `0x180036786`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x180036622`: `Thread window class not registered. Skipping unregister.`
- `0x18003676f`: `PAL_System_Win32_ThreadUnRegisterWindowClass`

## pseudocode

```c
__int64 __fastcall PAL_System_Win32_ThreadUnRegisterWindowClass(int a1, __int64 a2, int a3, int a4)
{
  signed int ModuleSpecificClassName; // ebx
  const unsigned __int16 *v5; // rcx
  unsigned int v6; // r8d
  unsigned int v7; // eax
  DWORD LastError; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v10; // eax
  int v11; // r8d
  int v12; // r9d
  signed int v14; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+54h] [rbp-ACh] BYREF
  const char *v16; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-A0h] BYREF
  const char *v18; // [rsp+68h] [rbp-98h] BYREF
  const char *v19; // [rsp+70h] [rbp-90h] BYREF
  const char *v20; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ClassName[264]; // [rsp+80h] [rbp-80h] BYREF

  phModule = 0;
  if ( g_PAL_SYS_fThreadWndClassRegistered )
  {
    memset_0(ClassName, 0, 0x208u);
    ModuleSpecificClassName = PAL_System_Win32_GetModuleSpecificClassName(v5, ClassName, v6);
    if ( ModuleSpecificClassName >= 0 )
    {
      if ( !GetModuleHandleExW(2u, 0, &phModule) )
      {
        LastError = GetLastError();
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
            21,
            WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
            CurrentThreadActivityIdPrefix,
            LastError);
        }
      }
      if ( UnregisterClassW(ClassName, phModule) )
      {
        g_PAL_SYS_fThreadWndClassRegistered = 0;
      }
      else
      {
        v10 = GetLastError();
        if ( v10 > 0 )
          ModuleSpecificClassName = (unsigned __int16)v10 | 0x80070000;
        else
          ModuleSpecificClassName = v10;
        if ( (unsigned int)dword_18005C008 > 2 )
        {
          v14 = v10;
          v18 = "PAL_System_Win32_ThreadUnRegisterWindowClass";
          v15 = 599;
          v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v20 = "Failed to unregister window class [Win32err = %d]";
          LODWORD(v16) = ModuleSpecificClassName;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v10,
            (unsigned int)byte_1800546D5,
            v11,
            v12,
            (__int64)&v20,
            (__int64)&v16,
            (__int64)&v19,
            (__int64)&v15,
            (__int64)&v18,
            (__int64)&v14);
        }
      }
    }
    else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
           && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        20,
        (unsigned int)WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
        v7,
        (__int64)"Failed to get module specific class name",
        ModuleSpecificClassName);
    }
  }
  else
  {
    ModuleSpecificClassName = 0;
    if ( (unsigned int)dword_18005C008 > 4 )
    {
      v16 = "Thread window class not registered. Skipping unregister.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        a1,
        (unsigned int)byte_1800548A9,
        a3,
        a4,
        (__int64)&v16);
    }
  }
  return (unsigned int)ModuleSpecificClassName;
}

```

## disassembly

```asm
0x1800365d4  mov     [rsp-8+arg_0], rbx
0x1800365d9  mov     [rsp-8+arg_8], rdi
0x1800365de  push    rbp
0x1800365df  lea     rbp, [rsp-1A0h]
0x1800365e7  sub     rsp, 2A0h
0x1800365ee  mov     rax, cs:__security_cookie
0x1800365f5  xor     rax, rsp
0x1800365f8  mov     [rbp+1A0h+var_10], rax
0x1800365ff  cmp     cs:?g_PAL_SYS_fThreadWndClassRegistered@@3HA, 0; int g_PAL_SYS_fThreadWndClassRegistered
0x180036606  mov     [rsp+2A0h+phModule], 0
0x18003660f  jnz     short loc_180036649
0x180036611  mov     eax, cs:dword_18005C008
0x180036617  xor     ebx, ebx
0x180036619  cmp     eax, 4
0x18003661c  jbe     loc_1800367F7
0x180036622  lea     rax, aThreadWindowCl; "Thread window class not registered. Ski"...
0x180036629  mov     [rsp+2A0h+var_248], rax
0x18003662e  lea     rdx, byte_1800548A9
0x180036635  lea     rax, [rsp+2A0h+var_248]
0x18003663a  mov     [rsp+2A0h+var_280], rax
0x18003663f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180036644  jmp     loc_1800367F7
0x180036649  xor     edx, edx; Val
0x18003664b  lea     rcx, [rbp+1A0h+ClassName]; void *
0x18003664f  mov     r8d, 208h; Size
0x180036655  call    memset_0
0x18003665a  lea     rdx, [rbp+1A0h+ClassName]; unsigned __int16 *
0x18003665e  call    ?PAL_System_Win32_GetModuleSpecificClassName@@YAJPEBGPEAGK@Z; PAL_System_Win32_GetModuleSpecificClassName(ushort const *,ushort *,ulong)
0x180036663  mov     ebx, eax
0x180036665  test    eax, eax
0x180036667  jns     short loc_1800366CD
0x180036669  mov     rax, cs:WPP_GLOBAL_Control
0x180036670  lea     rcx, WPP_GLOBAL_Control
0x180036677  cmp     rax, rcx
0x18003667a  jz      loc_1800367F7
0x180036680  test    byte ptr [rax+1Ch], 8
0x180036684  jz      loc_1800367F7
0x18003668a  cmp     byte ptr [rax+19h], 2
0x18003668e  jb      loc_1800367F7
0x180036694  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180036699  lea     rcx, aFailedToGetMod; "Failed to get module specific class nam"...
0x1800366a0  mov     dword ptr [rsp+2A0h+var_278], ebx
0x1800366a4  mov     [rsp+2A0h+var_280], rcx
0x1800366a9  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x1800366b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366b7  mov     edx, 14h
0x1800366bc  mov     r9d, eax
0x1800366bf  mov     rcx, [rcx+10h]
0x1800366c3  call    WPP_SF_DsD
0x1800366c8  jmp     loc_1800367F7
0x1800366cd  xor     edx, edx; lpModuleName
0x1800366cf  lea     r8, [rsp+2A0h+phModule]; phModule
0x1800366d4  lea     ecx, [rdx+2]; dwFlags
0x1800366d7  call    cs:__imp_GetModuleHandleExW
0x1800366dd  test    eax, eax
0x1800366df  jnz     short loc_180036730
0x1800366e1  call    cs:__imp_GetLastError
0x1800366e7  mov     edi, eax
0x1800366e9  mov     rdx, cs:WPP_GLOBAL_Control
0x1800366f0  lea     rcx, WPP_GLOBAL_Control
0x1800366f7  cmp     rdx, rcx
0x1800366fa  jz      short loc_180036730
0x1800366fc  test    byte ptr [rdx+1Ch], 8
0x180036700  jz      short loc_180036730
0x180036702  cmp     byte ptr [rdx+19h], 2
0x180036706  jb      short loc_180036730
0x180036708  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003670d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036714  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x18003671b  mov     edx, 15h
0x180036720  mov     dword ptr [rsp+2A0h+var_280], edi
0x180036724  mov     r9d, eax
0x180036727  mov     rcx, [rcx+10h]
0x18003672b  call    WPP_SF_Dd
0x180036730  mov     rdx, [rsp+2A0h+phModule]; hInstance
0x180036735  lea     rcx, [rbp+1A0h+ClassName]; lpClassName
0x180036739  call    cs:__imp_UnregisterClassW
0x18003673f  test    eax, eax
0x180036741  jnz     loc_1800367ED
0x180036747  call    cs:__imp_GetLastError
0x18003674d  mov     ecx, eax
0x18003674f  test    eax, eax
0x180036751  jg      short loc_180036757
0x180036753  mov     ebx, eax
0x180036755  jmp     short loc_180036760
0x180036757  movzx   ebx, cx
0x18003675a  or      ebx, 80070000h
0x180036760  mov     eax, cs:dword_18005C008
0x180036766  cmp     eax, 2
0x180036769  jbe     loc_1800367F7
0x18003676f  lea     rax, aPalSystemWin32_0; "PAL_System_Win32_ThreadUnRegisterWindow"...
0x180036776  mov     [rsp+2A0h+var_250], ecx
0x18003677a  mov     [rsp+2A0h+var_238], rax
0x18003677f  lea     rdx, byte_1800546D5
0x180036786  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003678d  mov     [rsp+2A0h+var_24C], 257h
0x180036795  mov     [rsp+2A0h+var_230], rax
0x18003679a  lea     rax, aFailedToUnregi_1; "Failed to unregister window class [Win3"...
0x1800367a1  mov     [rsp+2A0h+var_228], rax
0x1800367a6  lea     rax, [rsp+2A0h+var_250]
0x1800367ab  mov     [rsp+2A0h+var_258], rax
0x1800367b0  lea     rax, [rsp+2A0h+var_238]
0x1800367b5  mov     [rsp+2A0h+var_260], rax
0x1800367ba  lea     rax, [rsp+2A0h+var_24C]
0x1800367bf  mov     [rsp+2A0h+var_268], rax
0x1800367c4  lea     rax, [rsp+2A0h+var_230]
0x1800367c9  mov     [rsp+2A0h+var_270], rax
0x1800367ce  lea     rax, [rsp+2A0h+var_248]
0x1800367d3  mov     [rsp+2A0h+var_278], rax
0x1800367d8  lea     rax, [rsp+2A0h+var_228]
0x1800367dd  mov     [rsp+2A0h+var_280], rax
0x1800367e2  mov     dword ptr [rsp+2A0h+var_248], ebx
0x1800367e6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800367eb  jmp     short loc_1800367F7
0x1800367ed  mov     cs:?g_PAL_SYS_fThreadWndClassRegistered@@3HA, 0; int g_PAL_SYS_fThreadWndClassRegistered
0x1800367f7  mov     eax, ebx
0x1800367f9  mov     rcx, [rbp+1A0h+var_10]
0x180036800  xor     rcx, rsp; StackCookie
0x180036803  call    __security_check_cookie
0x180036808  lea     r11, [rsp+2A0h+var_s0]
0x180036810  mov     rbx, [r11+10h]
0x180036814  mov     rdi, [r11+18h]
0x180036818  mov     rsp, r11
0x18003681b  pop     rbp
0x18003681c  retn
```
