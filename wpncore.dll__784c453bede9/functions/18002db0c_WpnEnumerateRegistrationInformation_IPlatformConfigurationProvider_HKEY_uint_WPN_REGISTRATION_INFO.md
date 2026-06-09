# WpnEnumerateRegistrationInformation(IPlatformConfigurationProvider *,HKEY__ *,uint *,WPN_REGISTRATION_INFO * *)

- ea: `0x18002db0c`
- end: `0x18002de94`
- name: `?WpnEnumerateRegistrationInformation@@YAJPEAUIPlatformConfigurationProvider@@PEAUHKEY__@@PEAIPEAPEAUWPN_REGISTRATION_INFO@@@Z`
- size: `904`
- prototype: `int(struct IPlatformConfigurationProvider *, HKEY, unsigned int *, struct WPN_REGISTRATION_INFO **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e620`
- `0x18007a74c`

## callees

- `0x18002db0c`
- `0x18002e790`
- `0x18002ee38`
- `0x1800a0b2c`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dc7c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dc7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dc6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002de7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dc6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002de7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002de89`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002de89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002db9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002db9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002dc40`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002dc40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dbb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dbb8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002dcd2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002dcd2`

## string_xrefs

- `0x18002dd44`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x18002ddc5`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x18002de0b`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
__int64 __fastcall WpnEnumerateRegistrationInformation(
        struct IPlatformConfigurationProvider *a1,
        HKEY a2,
        unsigned int *a3,
        struct WPN_REGISTRATION_INFO **a4)
{
  DWORD v4; // r15d
  struct WPN_REGISTRATION_INFO *v9; // r14
  __int64 v10; // rax
  const WCHAR *v11; // rax
  LSTATUS v12; // eax
  unsigned int v13; // edi
  LSTATUS v15; // eax
  SIZE_T v16; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v18; // esi
  LSTATUS v19; // eax
  int ApplicationRegistrationInformation; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  HANDLE v24; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[136]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v4 = 0;
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  *a3 = 0;
  *a4 = 0;
  v9 = 0;
  v10 = *(_QWORD *)a1;
  hKey = 0;
  cSubKeys = 0;
  cchName[0] = 0;
  v11 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IPlatformConfigurationProvider *))(v10 + 32))(a1);
  v12 = RegOpenKeyExW(a2, v11, 0, 0x20019u, &hKey);
  v13 = v12;
  if ( v12 == 2 )
    goto LABEL_6;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( (v13 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3CD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)v13,
      phkResult);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v22 = 37;
    goto LABEL_32;
  }
  v15 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v13 = v15;
  if ( v15 > 0 )
    v13 = (unsigned __int16)v15 | 0x80070000;
  if ( (v13 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3DA,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)v13,
      phkResulta);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v22 = 38;
LABEL_32:
    v23 = v13;
    goto LABEL_33;
  }
  if ( !cSubKeys )
  {
    v13 = 0;
    goto LABEL_7;
  }
  v16 = 4632LL * cSubKeys;
  ProcessHeap = GetProcessHeap();
  v9 = (struct WPN_REGISTRATION_INFO *)HeapAlloc(ProcessHeap, 8u, v16);
  if ( !v9 )
  {
    v13 = -2147024882;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3E7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)0x8007000ELL,
      phkResulta);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v22 = 39;
    v23 = 2147942414LL;
LABEL_33:
    WPP_SF_d(v21[2], v22, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids, v23);
    goto LABEL_7;
  }
  v18 = 0;
  while ( v4 < cSubKeys )
  {
    cchName[0] = 130;
    Name[0] = 0;
    v19 = RegEnumKeyExW(hKey, v4, Name, cchName, 0, 0, 0, 0);
    if ( v19 == 259 )
      break;
    if ( !v19 )
    {
      ApplicationRegistrationInformation = WpnGetApplicationRegistrationInformation(hKey, Name, (BYTE *)v9 + 4632 * v18);
      v13 = ApplicationRegistrationInformation;
      if ( ApplicationRegistrationInformation < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            40,
            WPP_dc39e499189d3acee5756cf962abbe12_Traceguids,
            (unsigned int)ApplicationRegistrationInformation);
        v13 = 0;
      }
      else
      {
        ++v18;
      }
    }
    ++v4;
  }
  if ( !v18 )
  {
LABEL_6:
    v13 = 1;
    goto LABEL_7;
  }
  *a4 = v9;
  v9 = 0;
  *a3 = v18;
LABEL_7:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v9 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v9);
  }
  return v13;
}

```

## disassembly

```asm
0x18002db0c  push    rbp
0x18002db0e  push    rbx
0x18002db0f  push    rsi
0x18002db10  push    rdi
0x18002db11  push    r12
0x18002db13  push    r13
0x18002db15  push    r14
0x18002db17  push    r15
0x18002db19  lea     rbp, [rsp-0A8h]
0x18002db21  sub     rsp, 1A8h
0x18002db28  mov     rax, cs:__security_cookie
0x18002db2f  xor     rax, rsp
0x18002db32  mov     [rbp+0E0h+var_50], rax
0x18002db39  xor     r15d, r15d
0x18002db3c  mov     r12, r9
0x18002db3f  mov     r13, r8
0x18002db42  mov     rdi, rdx
0x18002db45  mov     rbx, rcx
0x18002db48  test    r8, r8
0x18002db4b  jz      loc_18002DD80
0x18002db51  test    r12, r12
0x18002db54  jz      loc_18002DD8A
0x18002db5a  mov     [r13+0], r15d
0x18002db5e  mov     rcx, rbx
0x18002db61  mov     [r12], r15
0x18002db65  mov     r14, r15
0x18002db68  mov     rax, [rbx]
0x18002db6b  mov     [rsp+1E0h+hKey], r15
0x18002db70  mov     [rsp+1E0h+cSubKeys], r15d
0x18002db75  mov     [rsp+1E0h+cchName], r15d
0x18002db7a  mov     rax, [rax+20h]
0x18002db7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db83  mov     rdx, rax; lpSubKey
0x18002db86  mov     r9d, 20019h; samDesired
0x18002db8c  lea     rax, [rsp+1E0h+hKey]
0x18002db91  xor     r8d, r8d; ulOptions
0x18002db94  mov     rcx, rdi; hKey
0x18002db97  mov     [rsp+1E0h+phkResult], rax; int
0x18002db9c  call    cs:__imp_RegOpenKeyExW
0x18002dba2  mov     edi, eax
0x18002dba4  cmp     eax, 2
0x18002dba7  jnz     short loc_18002DBF1
0x18002dba9  mov     edi, 1
0x18002dbae  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18002dbb3  test    rcx, rcx
0x18002dbb6  jz      short loc_18002DBC3
0x18002dbb8  call    cs:__imp_RegCloseKey
0x18002dbbe  mov     [rsp+1E0h+hKey], r15
0x18002dbc3  test    r14, r14
0x18002dbc6  jnz     loc_18002DE7B
0x18002dbcc  mov     eax, edi
0x18002dbce  mov     rcx, [rbp+0E0h+var_50]
0x18002dbd5  xor     rcx, rsp; StackCookie
0x18002dbd8  call    __security_check_cookie
0x18002dbdd  add     rsp, 1A8h
0x18002dbe4  pop     r15
0x18002dbe6  pop     r14
0x18002dbe8  pop     r13
0x18002dbea  pop     r12
0x18002dbec  pop     rdi
0x18002dbed  pop     rsi
0x18002dbee  pop     rbx
0x18002dbef  pop     rbp
0x18002dbf0  retn
0x18002dbf1  mov     ebx, 80070000h
0x18002dbf6  test    eax, eax
0x18002dbf8  jg      loc_18002DD29
0x18002dbfe  test    edi, edi
0x18002dc00  js      loc_18002DD3D
0x18002dc06  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18002dc0b  lea     rax, [rsp+1E0h+cSubKeys]
0x18002dc10  mov     [rsp+1E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002dc15  xor     r9d, r9d; lpReserved
0x18002dc18  mov     [rsp+1E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002dc1d  xor     r8d, r8d; lpcchClass
0x18002dc20  mov     [rsp+1E0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18002dc25  xor     edx, edx; lpClass
0x18002dc27  mov     [rsp+1E0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18002dc2c  mov     [rsp+1E0h+lpcValues], r15; lpcValues
0x18002dc31  mov     [rsp+1E0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002dc36  mov     [rsp+1E0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18002dc3b  mov     [rsp+1E0h+phkResult], rax; int
0x18002dc40  call    cs:__imp_RegQueryInfoKeyW
0x18002dc46  mov     edi, eax
0x18002dc48  test    eax, eax
0x18002dc4a  jg      loc_18002DD33
0x18002dc50  test    edi, edi
0x18002dc52  js      loc_18002DDBE
0x18002dc58  mov     eax, [rsp+1E0h+cSubKeys]
0x18002dc5c  test    eax, eax
0x18002dc5e  jz      loc_18002DDFC
0x18002dc64  imul    rbx, rax, 1218h
0x18002dc6b  call    cs:__imp_GetProcessHeap
0x18002dc71  mov     r8, rbx; dwBytes
0x18002dc74  mov     edx, 8; dwFlags
0x18002dc79  mov     rcx, rax; hHeap
0x18002dc7c  call    cs:__imp_HeapAlloc
0x18002dc82  mov     r14, rax
0x18002dc85  test    rax, rax
0x18002dc88  jz      loc_18002DE04
0x18002dc8e  mov     esi, r15d
0x18002dc91  lea     rbx, WPP_GLOBAL_Control
0x18002dc98  cmp     r15d, [rsp+1E0h+cSubKeys]
0x18002dc9d  jnb     short loc_18002DD0E
0x18002dc9f  xor     ecx, ecx
0x18002dca1  mov     [rsp+1E0h+cchName], 82h
0x18002dca9  mov     [rsp+1E0h+lpcValues], rcx; lpftLastWriteTime
0x18002dcae  lea     r9, [rsp+1E0h+cchName]; lpcchName
0x18002dcb3  mov     [rsp+1E0h+lpcbMaxClassLen], rcx; lpcchClass
0x18002dcb8  lea     r8, [rbp+0E0h+Name]; lpName
0x18002dcbc  mov     [rsp+1E0h+lpcbMaxSubKeyLen], rcx; lpClass
0x18002dcc1  mov     edx, r15d; dwIndex
0x18002dcc4  mov     [rsp+1E0h+phkResult], rcx; lpReserved
0x18002dcc9  mov     [rbp+0E0h+Name], cx
0x18002dccd  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18002dcd2  call    cs:__imp_RegEnumKeyExW
0x18002dcd8  cmp     eax, 103h
0x18002dcdd  jz      short loc_18002DD0E
0x18002dcdf  test    eax, eax
0x18002dce1  jnz     short loc_18002DD09
0x18002dce3  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18002dce8  lea     rdx, [rbp+0E0h+Name]; lpSubKey
0x18002dcec  mov     eax, esi
0x18002dcee  imul    r8, rax, 1218h
0x18002dcf5  add     r8, r14; struct WPN_REGISTRATION_INFO *
0x18002dcf8  call    ?WpnGetApplicationRegistrationInformation@@YAJPEAUHKEY__@@PEBGPEAUWPN_REGISTRATION_INFO@@@Z; WpnGetApplicationRegistrationInformation(HKEY__ *,ushort const *,WPN_REGISTRATION_INFO *)
0x18002dcfd  mov     edi, eax
0x18002dcff  test    eax, eax
0x18002dd01  js      loc_18002DE4A
0x18002dd07  inc     esi
0x18002dd09  inc     r15d
0x18002dd0c  jmp     short loc_18002DC98
0x18002dd0e  xor     r15d, r15d
0x18002dd11  test    esi, esi
0x18002dd13  jz      loc_18002DBA9
0x18002dd19  mov     [r12], r14
0x18002dd1d  mov     r14d, r15d
0x18002dd20  mov     [r13+0], esi
0x18002dd24  jmp     loc_18002DBAE
0x18002dd29  movzx   edi, ax
0x18002dd2c  or      edi, ebx
0x18002dd2e  jmp     loc_18002DBFE
0x18002dd33  movzx   edi, ax
0x18002dd36  or      edi, ebx
0x18002dd38  jmp     loc_18002DC50
0x18002dd3d  mov     rcx, [rbp+0E8h]; this
0x18002dd44  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002dd4b  mov     r9d, edi; char *
0x18002dd4e  mov     edx, 3CDh; void *
0x18002dd53  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002dd58  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd5f  lea     rbx, WPP_GLOBAL_Control
0x18002dd66  cmp     rcx, rbx
0x18002dd69  jz      loc_18002DBAE
0x18002dd6f  test    byte ptr [rcx+1Ch], 80h
0x18002dd73  jz      loc_18002DBAE
0x18002dd79  mov     edx, 25h ; '%'
0x18002dd7e  jmp     short loc_18002DD99
0x18002dd80  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "Count != NULL")
0x18002dd85  jmp     loc_18002DB51
0x18002dd8a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "Info!= NULL")
0x18002dd8f  jmp     loc_18002DB5A
0x18002dd94  mov     edx, 26h ; '&'
0x18002dd99  mov     r9d, edi
0x18002dd9c  jmp     short loc_18002DDA9
0x18002dd9e  mov     edx, 27h ; '''
0x18002dda3  mov     r9d, 8007000Eh
0x18002dda9  mov     rcx, [rcx+10h]
0x18002ddad  lea     r8, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids
0x18002ddb4  call    WPP_SF_d
0x18002ddb9  jmp     loc_18002DBAE
0x18002ddbe  mov     rcx, [rbp+0E8h]; this
0x18002ddc5  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002ddcc  mov     r9d, edi; char *
0x18002ddcf  mov     edx, 3DAh; void *
0x18002ddd4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ddd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dde0  lea     rbx, WPP_GLOBAL_Control
0x18002dde7  cmp     rcx, rbx
0x18002ddea  jz      loc_18002DBAE
0x18002ddf0  test    byte ptr [rcx+1Ch], 80h
0x18002ddf4  jz      loc_18002DBAE
0x18002ddfa  jmp     short loc_18002DD94
0x18002ddfc  mov     edi, r15d
0x18002ddff  jmp     loc_18002DBAE
0x18002de04  mov     rcx, [rbp+0E8h]; this
0x18002de0b  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002de12  mov     edi, 8007000Eh
0x18002de17  mov     edx, 3E7h; void *
0x18002de1c  mov     r9d, edi; char *
0x18002de1f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002de24  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de2b  lea     rbx, WPP_GLOBAL_Control
0x18002de32  cmp     rcx, rbx
0x18002de35  jz      loc_18002DBAE
0x18002de3b  test    byte ptr [rcx+1Ch], 80h
0x18002de3f  jz      loc_18002DBAE
0x18002de45  jmp     loc_18002DD9E
0x18002de4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de51  cmp     rcx, rbx
0x18002de54  jz      short loc_18002DE74
0x18002de56  test    byte ptr [rcx+1Ch], 80h
0x18002de5a  jz      short loc_18002DE74
0x18002de5c  mov     rcx, [rcx+10h]
0x18002de60  lea     r8, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids
0x18002de67  mov     edx, 28h ; '('
0x18002de6c  mov     r9d, eax
0x18002de6f  call    WPP_SF_d
0x18002de74  xor     edi, edi
0x18002de76  jmp     loc_18002DD09
0x18002de7b  call    cs:__imp_GetProcessHeap
0x18002de81  mov     r8, r14; lpMem
0x18002de84  xor     edx, edx; dwFlags
0x18002de86  mov     rcx, rax; hHeap
0x18002de89  call    cs:__imp_HeapFree
0x18002de8f  jmp     loc_18002DBCC
```
