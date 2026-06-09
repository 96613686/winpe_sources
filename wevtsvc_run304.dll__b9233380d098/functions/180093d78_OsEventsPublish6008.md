# OsEventsPublish6008

- ea: `0x180093d78`
- end: `0x1800940c7`
- name: `OsEventsPublish6008`
- size: `847`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18005e4e4`

## callees

- `0x180006fb0`
- `0x18005e984`
- `0x180074c48`
- `0x1800771dc`
- `0x180093d78`
- `0x1800940d0`
- `0x18009aee0`
- `0x1800c27d4`
- `0x1800c2a28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180093eaf`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180093eaf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180093e25`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180093e25`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009405e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009408c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009405e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009408c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180093e8a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180093e8a`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180093f42`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180093f79`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180093f42`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180093f79`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180093faf`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180093ff1`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180093faf`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180093ff1`

## pseudocode

```c
char __fastcall OsEventsPublish6008(__int64 a1)
{
  LSTATUS v1; // eax
  char v2; // bl
  int v3; // eax
  _BYTE *v4; // rcx
  unsigned int TimeFormat; // edi
  LPWSTR v6; // rbx
  __int64 DateFormat; // rdi
  __int64 v8; // r8
  LPWSTR v9; // rbx
  LPCWSTR lpCalendar; // [rsp+30h] [rbp-D0h]
  BYTE lpData[8]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  LPWSTR lpDateStr; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR lpTimeStr; // [rsp+58h] [rbp-A8h] BYREF
  SYSTEMTIME v17; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v18; // [rsp+70h] [rbp-90h]
  __int128 v19; // [rsp+80h] [rbp-80h]
  _OWORD Src[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v21; // [rsp+B0h] [rbp-50h]
  __int64 v22; // [rsp+B8h] [rbp-48h]
  __int128 v23; // [rsp+C0h] [rbp-40h]
  struct _SYSTEMTIME LocalTime; // [rsp+D0h] [rbp-30h] BYREF
  SYSTEMTIME UniversalTime; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v26[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v27; // [rsp+100h] [rbp+0h]
  __int128 v28; // [rsp+110h] [rbp+10h]
  const WCHAR *v29; // [rsp+120h] [rbp+20h]
  _BYTE v30[24]; // [rsp+128h] [rbp+28h] BYREF

  *(_DWORD *)lpData = 0;
  v29 = &pszFormat;
  LOBYTE(a1) = 1;
  *(__m128 *)v26 = _mm_movelh_ps((__m128)(unsigned __int64)&pszFormat, (__m128)(unsigned __int64)&pszFormat);
  v27 = *(_OWORD *)v26;
  v28 = *(_OWORD *)v26;
  LOBYTE(v1) = OsEventsGetBootTimeBias(a1, lpData);
  v2 = v1;
  if ( hKey )
  {
    LOBYTE(v1) = OsEventsSystemRestored();
    if ( (_BYTE)v1 != 1 )
    {
      *(_DWORD *)Data = 0;
      cbData = 4;
      v1 = RegQueryValueExW(hKey, L"LastAliveStamp", 0, 0, Data, &cbData);
      if ( !v1 && cbData == 4 && *(_DWORD *)Data == 195934928 )
      {
        v17 = 0;
        v18 = 0;
        v19 = 0;
        LOBYTE(v1) = OsEventsReadHeartbeatData((__int64)&v17);
        if ( (_BYTE)v1 )
        {
          UniversalTime = v17;
          LocalTime = 0;
          if ( !SystemTimeToTzSpecificLocalTime(0, &UniversalTime, &LocalTime) )
            LocalTime = UniversalTime;
          v3 = _o__ultow_s((unsigned int)v18, v30, 11);
          v4 = v30;
          if ( v3 )
            v4 = (_BYTE *)v28;
          v23 = 0;
          *(_QWORD *)&v28 = v4;
          v21 = *((_QWORD *)&v18 + 1);
          v22 = 0;
          Src[0] = LocalTime;
          Src[1] = UniversalTime;
          if ( (_DWORD)v19 )
          {
            *(_QWORD *)&v23 = __PAIR64__(v19, DWORD1(v18));
            LODWORD(v22) = 1;
            HIDWORD(v22) = DWORD2(v18);
          }
          if ( v2 )
          {
            HIDWORD(v23) = *(_DWORD *)lpData;
            DWORD2(v23) = 1;
          }
          TimeFormat = GetTimeFormatEx(L"!x-sys-default-locale", 0, &LocalTime, 0, 0, 0);
          utl::make_unique_for_overwrite<wchar_t [0],0>(&lpTimeStr, TimeFormat);
          v6 = lpTimeStr;
          if ( lpTimeStr )
          {
            GetTimeFormatEx(L"!x-sys-default-locale", 0, &LocalTime, 0, lpTimeStr, TimeFormat);
            v26[0] = (__int64)v6;
          }
          DateFormat = (unsigned int)GetDateFormatEx(L"!x-sys-default-locale", 0x40u, &LocalTime, 0, 0, 0, 0);
          utl::make_unique_for_overwrite<wchar_t [0],0>(&lpDateStr, DateFormat);
          v9 = lpDateStr;
          if ( lpDateStr )
          {
            GetDateFormatEx(L"!x-sys-default-locale", 0x40u, &LocalTime, 0, lpDateStr, DateFormat, 0);
            v26[1] = (__int64)v9;
          }
          LODWORD(lpCalendar) = 64;
          LogElfEvent(0x80001778, 1, v8, 7u, (__int64)v26, Src, (size_t)lpCalendar);
          OsEventsCleanShutdown();
          *(_DWORD *)lpData = 1;
          RegSetValueExW(hKey, L"DirtyShutdown", 0, 4u, lpData, 4u);
          RegSetValueExW(hKey, L"DirtyShutdownTime", 0, 3u, (const BYTE *)&UniversalTime, 0x10u);
          utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&lpDateStr);
          LOBYTE(v1) = utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&lpTimeStr);
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180093d78  mov     [rsp-8+arg_0], rbx
0x180093d7d  mov     [rsp-8+arg_8], rdi
0x180093d82  push    rbp
0x180093d83  lea     rbp, [rsp-50h]
0x180093d88  sub     rsp, 150h
0x180093d8f  mov     rax, cs:__security_cookie
0x180093d96  xor     rax, rsp
0x180093d99  mov     [rbp+50h+var_10], rax
0x180093d9d  lea     rax, pszFormat
0x180093da4  mov     dword ptr [rsp+150h+var_110], 0
0x180093dac  movq    xmm0, rax
0x180093db1  mov     [rbp+50h+var_30], rax
0x180093db5  movlhps xmm0, xmm0
0x180093db8  lea     rdx, [rsp+150h+var_110]
0x180093dbd  mov     cl, 1
0x180093dbf  movups  xmmword ptr [rbp+50h+var_60], xmm0
0x180093dc3  movups  [rbp+50h+var_50], xmm0
0x180093dc7  movups  [rbp+50h+var_40], xmm0
0x180093dcb  call    OsEventsGetBootTimeBias
0x180093dd0  cmp     cs:hKey, 0
0x180093dd8  mov     bl, al
0x180093dda  jz      loc_1800940A6
0x180093de0  call    OsEventsSystemRestored
0x180093de5  cmp     al, 1
0x180093de7  jz      loc_1800940A6
0x180093ded  mov     rcx, cs:hKey; hKey
0x180093df4  lea     rax, [rsp+150h+cbData]
0x180093df9  mov     [rsp+150h+lpcbData], rax; lpcbData
0x180093dfe  lea     rdx, aLastalivestamp; "LastAliveStamp"
0x180093e05  lea     rax, [rsp+150h+Data]
0x180093e0a  mov     dword ptr [rsp+150h+Data], 0
0x180093e12  xor     r9d, r9d; lpType
0x180093e15  mov     [rsp+150h+lpData], rax; lpData
0x180093e1a  xor     r8d, r8d; lpReserved
0x180093e1d  mov     [rsp+150h+cbData], 4
0x180093e25  call    cs:__imp_RegQueryValueExW
0x180093e2b  test    eax, eax
0x180093e2d  jnz     loc_1800940A6
0x180093e33  cmp     [rsp+150h+cbData], 4
0x180093e38  jnz     loc_1800940A6
0x180093e3e  cmp     dword ptr [rsp+150h+Data], 0BADBAD0h
0x180093e46  jnz     loc_1800940A6
0x180093e4c  xorps   xmm0, xmm0
0x180093e4f  lea     rcx, [rsp+150h+var_F0]
0x180093e54  movups  [rsp+150h+var_F0], xmm0
0x180093e59  movups  [rsp+150h+var_E0], xmm0
0x180093e5e  movups  [rbp+50h+var_D0], xmm0
0x180093e62  call    OsEventsReadHeartbeatData
0x180093e67  test    al, al
0x180093e69  jz      loc_1800940A6
0x180093e6f  movups  xmm0, [rsp+150h+var_F0]
0x180093e74  lea     r8, [rbp+50h+LocalTime]; lpLocalTime
0x180093e78  xor     ecx, ecx; lpTimeZoneInformation
0x180093e7a  xorps   xmm1, xmm1
0x180093e7d  lea     rdx, [rbp+50h+UniversalTime]; lpUniversalTime
0x180093e81  movdqu  xmmword ptr [rbp+50h+UniversalTime.wYear], xmm0
0x180093e86  movups  xmmword ptr [rbp+50h+LocalTime.wYear], xmm1
0x180093e8a  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180093e90  test    eax, eax
0x180093e92  jnz     short loc_180093E9D
0x180093e94  movaps  xmm0, xmmword ptr [rbp+50h+UniversalTime.wYear]
0x180093e98  movdqa  xmmword ptr [rbp+50h+LocalTime.wYear], xmm0
0x180093e9d  mov     ecx, dword ptr [rsp+150h+var_E0]
0x180093ea1  lea     rdx, [rbp+50h+var_28]
0x180093ea5  mov     r9d, 0Ah
0x180093eab  lea     r8d, [r9+1]
0x180093eaf  call    cs:__imp__o__ultow_s
0x180093eb5  movaps  xmm1, xmmword ptr [rbp+50h+LocalTime.wYear]
0x180093eb9  lea     rcx, [rbp+50h+var_28]
0x180093ebd  mov     edx, dword ptr [rbp+50h+var_D0]
0x180093ec0  test    eax, eax
0x180093ec2  mov     eax, dword ptr [rsp+150h+var_E0+0Ch]
0x180093ec6  xorps   xmm0, xmm0
0x180093ec9  cmovnz  rcx, qword ptr [rbp+50h+var_40]
0x180093ece  movdqa  [rbp+50h+var_90], xmm0
0x180093ed3  movaps  xmm0, xmmword ptr [rbp+50h+UniversalTime.wYear]
0x180093ed7  mov     qword ptr [rbp+50h+var_40], rcx
0x180093edb  mov     ecx, dword ptr [rsp+150h+var_E0+8]
0x180093edf  mov     dword ptr [rbp+50h+var_A0], ecx
0x180093ee2  mov     [rbp+50h+var_98], 0
0x180093eea  mov     dword ptr [rbp+50h+var_A0+4], eax
0x180093eed  movdqu  [rbp+50h+Src], xmm1
0x180093ef2  movdqu  [rbp+50h+var_B0], xmm0
0x180093ef7  test    edx, edx
0x180093ef9  jz      short loc_180093F0F
0x180093efb  mov     eax, dword ptr [rsp+150h+var_E0+4]
0x180093eff  mov     dword ptr [rbp+50h+var_90], eax
0x180093f02  mov     dword ptr [rbp+50h+var_98], 1
0x180093f09  mov     dword ptr [rbp+50h+var_98+4], ecx
0x180093f0c  mov     dword ptr [rbp+50h+var_90+4], edx
0x180093f0f  test    bl, bl
0x180093f11  jz      short loc_180093F21
0x180093f13  mov     eax, dword ptr [rsp+150h+var_110]
0x180093f17  mov     dword ptr [rbp+50h+var_90+0Ch], eax
0x180093f1a  mov     dword ptr [rbp+50h+var_90+8], 1
0x180093f21  mov     dword ptr [rsp+150h+lpcbData], 0; cchTime
0x180093f29  lea     r8, [rbp+50h+LocalTime]; lpTime
0x180093f2d  xor     r9d, r9d; lpFormat
0x180093f30  mov     [rsp+150h+lpData], 0; lpTimeStr
0x180093f39  xor     edx, edx; dwFlags
0x180093f3b  lea     rcx, LocaleName; "!x-sys-default-locale"
0x180093f42  call    cs:__imp_GetTimeFormatEx
0x180093f48  mov     edx, eax
0x180093f4a  lea     rcx, [rsp+150h+lpTimeStr]
0x180093f4f  mov     edi, eax
0x180093f51  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180093f56  mov     rbx, [rsp+150h+lpTimeStr]
0x180093f5b  test    rbx, rbx
0x180093f5e  jz      short loc_180093F83
0x180093f60  mov     dword ptr [rsp+150h+lpcbData], edi; cchTime
0x180093f64  lea     r8, [rbp+50h+LocalTime]; lpTime
0x180093f68  xor     r9d, r9d; lpFormat
0x180093f6b  mov     [rsp+150h+lpData], rbx; lpTimeStr
0x180093f70  xor     edx, edx; dwFlags
0x180093f72  lea     rcx, LocaleName; "!x-sys-default-locale"
0x180093f79  call    cs:__imp_GetTimeFormatEx
0x180093f7f  mov     [rbp+50h+var_60], rbx
0x180093f83  xor     r9d, r9d; lpFormat
0x180093f86  mov     [rsp+150h+lpCalendar], 0; lpCalendar
0x180093f8f  mov     dword ptr [rsp+150h+lpcbData], 0; cchDate
0x180093f97  lea     r8, [rbp+50h+LocalTime]; lpDate
0x180093f9b  lea     rcx, LocaleName; "!x-sys-default-locale"
0x180093fa2  mov     [rsp+150h+lpData], 0; lpDateStr
0x180093fab  lea     edx, [r9+40h]; dwFlags
0x180093faf  call    cs:__imp_GetDateFormatEx
0x180093fb5  mov     edx, eax
0x180093fb7  lea     rcx, [rsp+150h+lpDateStr]
0x180093fbc  mov     edi, eax
0x180093fbe  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180093fc3  mov     rbx, [rsp+150h+lpDateStr]
0x180093fc8  test    rbx, rbx
0x180093fcb  jz      short loc_180093FFB
0x180093fcd  xor     r9d, r9d; lpFormat
0x180093fd0  mov     [rsp+150h+lpCalendar], 0; lpCalendar
0x180093fd9  mov     dword ptr [rsp+150h+lpcbData], edi; cchDate
0x180093fdd  lea     r8, [rbp+50h+LocalTime]; lpDate
0x180093fe1  lea     rcx, LocaleName; "!x-sys-default-locale"
0x180093fe8  mov     [rsp+150h+lpData], rbx; lpDateStr
0x180093fed  lea     edx, [r9+40h]; dwFlags
0x180093ff1  call    cs:__imp_GetDateFormatEx
0x180093ff7  mov     [rbp+50h+var_60+8], rbx
0x180093ffb  mov     edx, 1; int
0x180094000  mov     dword ptr [rsp+150h+lpCalendar], 40h ; '@'; size_t
0x180094008  lea     rax, [rbp+50h+Src]
0x18009400c  mov     ecx, 80001778h; int
0x180094011  mov     [rsp+150h+lpcbData], rax; Src
0x180094016  lea     rax, [rbp+50h+var_60]
0x18009401a  mov     [rsp+150h+lpData], rax; __int64
0x18009401f  lea     r9d, [rdx+6]; int
0x180094023  call    LogElfEvent
0x180094028  call    OsEventsCleanShutdown
0x18009402d  mov     rcx, cs:hKey; hKey
0x180094034  lea     rax, [rsp+150h+var_110]
0x180094039  mov     dword ptr [rsp+150h+lpcbData], 4; cbData
0x180094041  lea     rdx, aDirtyshutdown; "DirtyShutdown"
0x180094048  mov     r9d, 4; dwType
0x18009404e  mov     [rsp+150h+lpData], rax; lpData
0x180094053  xor     r8d, r8d; Reserved
0x180094056  mov     dword ptr [rsp+150h+var_110], 1
0x18009405e  call    cs:__imp_RegSetValueExW
0x180094064  mov     rcx, cs:hKey; hKey
0x18009406b  lea     rax, [rbp+50h+UniversalTime]
0x18009406f  mov     dword ptr [rsp+150h+lpcbData], 10h; cbData
0x180094077  lea     rdx, aDirtyshutdownt; "DirtyShutdownTime"
0x18009407e  mov     r9d, 3; dwType
0x180094084  mov     [rsp+150h+lpData], rax; lpData
0x180094089  xor     r8d, r8d; Reserved
0x18009408c  call    cs:__imp_RegSetValueExW
0x180094092  lea     rcx, [rsp+150h+lpDateStr]
0x180094097  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x18009409c  lea     rcx, [rsp+150h+lpTimeStr]
0x1800940a1  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x1800940a6  mov     rcx, [rbp+50h+var_10]
0x1800940aa  xor     rcx, rsp; StackCookie
0x1800940ad  call    __security_check_cookie
0x1800940b2  lea     r11, [rsp+150h+var_s0]
0x1800940ba  mov     rbx, [r11+10h]
0x1800940be  mov     rdi, [r11+18h]
0x1800940c2  mov     rsp, r11
0x1800940c5  pop     rbp
0x1800940c6  retn
```
