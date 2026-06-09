# WpnParseVarDateRelative(ushort const *,double *)

- ea: `0x1800850d4`
- end: `0x1800852cc`
- name: `?WpnParseVarDateRelative@@YAJPEBGPEAN@Z`
- size: `504`
- prototype: `__int64 __fastcall(wchar_t *String, DOUBLE *pvtime)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180077820`

## callees

- `0x180007440`
- `0x18000fddc`
- `0x18000fe54`
- `0x18001c06c`
- `0x180084760`
- `0x1800850d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180085121`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180085121`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18008510c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180085129`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18008510c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180085129`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085209`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180085150`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180085150`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180085188`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180085188`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x1800851fb`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x1800851fb`

## string_xrefs

- `0x1800851b1`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180085227`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180085260`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
__int64 __fastcall WpnParseVarDateRelative(wchar_t *String, DOUBLE *pvtime)
{
  __int64 v4; // rsi
  unsigned int v5; // ebx
  __int64 v6; // r8
  signed int LastError; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  signed int v11; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-38h] BYREF
  FILETIME FileTime; // [rsp+28h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !String )
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
  if ( !pvtime )
    MicrosoftTelemetryAssertTriggeredNoArgs(String);
  *(_DWORD *)_o__errno() = 0;
  v4 = wcstoul(String, 0, 10);
  if ( *(_DWORD *)_o__errno() == 34 || (unsigned int)(v4 - 1) > 0xFFFFFFFD )
  {
    v5 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1DC,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)0x80070057LL,
      SystemTimeAsFileTime.dwLowDateTime);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v9 = 20;
      v10 = 2147942487LL;
      goto LABEL_25;
    }
  }
  else
  {
    v5 = 0;
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    FileTime = wil::FileTime::Add((wil::FileTime *)&SystemTimeAsFileTime, (const struct _FILETIME *)(10000000 * v4), v6);
    SystemTime = 0;
    if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
      goto LABEL_20;
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (v5 & 0x80000000) == 0 )
    {
LABEL_20:
      if ( !SystemTimeToVariantTime(&SystemTime, pvtime) )
      {
        v11 = GetLastError();
        v5 = v11;
        if ( v11 > 0 )
          v5 = (unsigned __int16)v11 | 0x80070000;
        if ( (v5 & 0x80000000) != 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1EA,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
            (const char *)v5,
            SystemTimeAsFileTime.dwLowDateTime);
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v9 = 22;
            goto LABEL_14;
          }
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1E6,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
        (const char *)v5,
        SystemTimeAsFileTime.dwLowDateTime);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v9 = 21;
LABEL_14:
        v10 = v5;
LABEL_25:
        WPP_SF_d(v8[2], v9, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids, v10);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800850d4  mov     [rsp+arg_10], rbx
0x1800850d9  mov     [rsp+arg_18], rsi
0x1800850de  push    rdi
0x1800850df  sub     rsp, 50h
0x1800850e3  mov     rax, cs:__security_cookie
0x1800850ea  xor     rax, rsp
0x1800850ed  mov     [rsp+58h+var_18], rax
0x1800850f2  mov     rdi, rdx
0x1800850f5  mov     rbx, rcx
0x1800850f8  test    rcx, rcx
0x1800850fb  jnz     short loc_180085102
0x1800850fd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180085102  test    rdi, rdi
0x180085105  jnz     short loc_18008510C
0x180085107  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008510c  call    cs:__imp__o__errno
0x180085112  xor     edx, edx; EndPtr
0x180085114  mov     rcx, rbx; String
0x180085117  mov     dword ptr [rax], 0
0x18008511d  lea     r8d, [rdx+0Ah]; Radix
0x180085121  call    cs:__imp_wcstoul
0x180085127  mov     esi, eax
0x180085129  call    cs:__imp__o__errno
0x18008512f  cmp     dword ptr [rax], 22h ; '"'
0x180085132  jz      loc_18008525B
0x180085138  lea     ecx, [rsi-1]
0x18008513b  cmp     ecx, 0FFFFFFFDh
0x18008513e  ja      loc_18008525B
0x180085144  xor     ebx, ebx
0x180085146  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18008514b  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180085150  call    cs:__imp_GetSystemTimeAsFileTime
0x180085156  mov     rcx, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x18008515b  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], rcx; int
0x180085160  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; this
0x180085165  imul    rdx, rsi, 989680h; struct _FILETIME *
0x18008516c  call    ?Add@FileTime@wil@@YA?AU_FILETIME@@AEBU3@_J@Z; wil::FileTime::Add(_FILETIME const &,__int64)
0x180085171  xorps   xmm0, xmm0
0x180085174  mov     qword ptr [rsp+58h+FileTime.dwLowDateTime], rax
0x180085179  lea     rcx, [rsp+58h+FileTime]; lpFileTime
0x18008517e  lea     rdx, [rsp+58h+SystemTime]; lpSystemTime
0x180085183  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x180085188  call    cs:__imp_FileTimeToSystemTime
0x18008518e  mov     esi, 80070000h
0x180085193  test    eax, eax
0x180085195  jnz     short loc_1800851F3
0x180085197  call    cs:__imp_GetLastError
0x18008519d  mov     ebx, eax
0x18008519f  test    eax, eax
0x1800851a1  jle     short loc_1800851A8
0x1800851a3  movzx   ebx, ax
0x1800851a6  or      ebx, esi
0x1800851a8  test    ebx, ebx
0x1800851aa  jns     short loc_1800851F3
0x1800851ac  mov     rcx, [rsp+58h]; this
0x1800851b1  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800851b8  mov     r9d, ebx; char *
0x1800851bb  mov     edx, 1E6h; void *
0x1800851c0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800851c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800851cc  lea     rax, WPP_GLOBAL_Control
0x1800851d3  cmp     rcx, rax
0x1800851d6  jz      loc_1800852AD
0x1800851dc  test    byte ptr [rcx+1Ch], 80h
0x1800851e0  jz      loc_1800852AD
0x1800851e6  mov     edx, 15h
0x1800851eb  mov     r9d, ebx
0x1800851ee  jmp     loc_18008529D
0x1800851f3  mov     rdx, rdi; pvtime
0x1800851f6  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x1800851fb  call    cs:__imp_SystemTimeToVariantTime
0x180085201  test    eax, eax
0x180085203  jnz     loc_1800852AD
0x180085209  call    cs:__imp_GetLastError
0x18008520f  mov     ebx, eax
0x180085211  test    eax, eax
0x180085213  jle     short loc_18008521A
0x180085215  movzx   ebx, ax
0x180085218  or      ebx, esi
0x18008521a  test    ebx, ebx
0x18008521c  jns     loc_1800852AD
0x180085222  mov     rcx, [rsp+58h]; this
0x180085227  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008522e  mov     r9d, ebx; char *
0x180085231  mov     edx, 1EAh; void *
0x180085236  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008523b  mov     rcx, cs:WPP_GLOBAL_Control
0x180085242  lea     rax, WPP_GLOBAL_Control
0x180085249  cmp     rcx, rax
0x18008524c  jz      short loc_1800852AD
0x18008524e  test    byte ptr [rcx+1Ch], 80h
0x180085252  jz      short loc_1800852AD
0x180085254  mov     edx, 16h
0x180085259  jmp     short loc_1800851EB
0x18008525b  mov     rcx, [rsp+58h]; this
0x180085260  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085267  mov     ebx, 80070057h
0x18008526c  mov     edx, 1DCh; void *
0x180085271  mov     r9d, ebx; char *
0x180085274  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180085279  mov     rcx, cs:WPP_GLOBAL_Control
0x180085280  lea     rax, WPP_GLOBAL_Control
0x180085287  cmp     rcx, rax
0x18008528a  jz      short loc_1800852AD
0x18008528c  test    byte ptr [rcx+1Ch], 80h
0x180085290  jz      short loc_1800852AD
0x180085292  mov     edx, 14h
0x180085297  mov     r9d, 80070057h
0x18008529d  mov     rcx, [rcx+10h]
0x1800852a1  lea     r8, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids
0x1800852a8  call    WPP_SF_d
0x1800852ad  mov     eax, ebx
0x1800852af  mov     rcx, [rsp+58h+var_18]
0x1800852b4  xor     rcx, rsp; StackCookie
0x1800852b7  call    __security_check_cookie
0x1800852bc  mov     rbx, [rsp+58h+arg_10]
0x1800852c1  mov     rsi, [rsp+58h+arg_18]
0x1800852c6  add     rsp, 50h
0x1800852ca  pop     rdi
0x1800852cb  retn
```
