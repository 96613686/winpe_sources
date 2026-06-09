# SetSystemTimeZoneDisplayName(void)

- ea: `0x10043ce60`
- end: `0x10043d22c`
- name: `?SetSystemTimeZoneDisplayName@@YAJXZ`
- size: `972`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100416770`

## callees

- `0x100401580`
- `0x10043ce60`
- `0x1004534f8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x10043cf5b`
- `ADVAPI32!RegCloseKey` at `0x10043d185`
- `ADVAPI32!RegCloseKey` at `0x10043cf5b`
- `ADVAPI32!RegCloseKey` at `0x10043d185`
- `ADVAPI32!RegOpenKeyExW` at `0x10043cee0`
- `ADVAPI32!RegOpenKeyExW` at `0x10043d108`
- `ADVAPI32!RegOpenKeyExW` at `0x10043cee0`
- `ADVAPI32!RegOpenKeyExW` at `0x10043d108`
- `ADVAPI32!RegQueryValueExW` at `0x10043cf12`
- `ADVAPI32!RegQueryValueExW` at `0x10043cf49`
- `ADVAPI32!RegQueryValueExW` at `0x10043d13a`
- `ADVAPI32!RegQueryValueExW` at `0x10043d173`
- `ADVAPI32!RegQueryValueExW` at `0x10043cf12`
- `ADVAPI32!RegQueryValueExW` at `0x10043cf49`
- `ADVAPI32!RegQueryValueExW` at `0x10043d13a`
- `ADVAPI32!RegQueryValueExW` at `0x10043d173`
- `sqlmin!GetXdbServerGlobals` at `0x10043ce95`
- `sqlmin!GetXdbServerGlobals` at `0x10043cf77`
- `sqlmin!GetXdbServerGlobals` at `0x10043d05a`
- `sqlmin!GetXdbServerGlobals` at `0x10043d199`
- `sqlmin!GetXdbServerGlobals` at `0x10043ce95`
- `sqlmin!GetXdbServerGlobals` at `0x10043cf77`
- `sqlmin!GetXdbServerGlobals` at `0x10043d05a`
- `sqlmin!GetXdbServerGlobals` at `0x10043d199`

## pseudocode

```c
__int64 __fastcall SetSystemTimeZoneDisplayName(__int64 a1, __int64 a2)
{
  unsigned int v2; // esi
  __int64 v3; // rdx
  LSTATUS v4; // ebx
  HKEY v5; // rcx
  unsigned __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 result; // rax
  unsigned __int64 v9; // rdx
  BYTE *v10; // r8
  __int16 v11; // ax
  _WORD *v12; // rax
  LSTATUS v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 XdbServerGlobals; // rax
  __int64 v17; // rdx
  BYTE *v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // eax
  BYTE *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r9
  __int16 v25; // r8
  BYTE *v26; // rax
  HKEY v27; // rcx
  unsigned __int64 v28; // rbx
  __int64 v29; // rcx
  unsigned __int64 v30; // rdi
  BYTE *v31; // rdx
  __int16 v32; // ax
  _WORD *v33; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v37; // [rsp+50h] [rbp-B0h]
  __int128 v38; // [rsp+60h] [rbp-A0h]
  __int128 v39; // [rsp+70h] [rbp-90h]
  __int128 v40; // [rsp+80h] [rbp-80h]
  __int128 v41; // [rsp+90h] [rbp-70h]
  __int128 v42; // [rsp+A0h] [rbp-60h]
  wchar_t v43; // [rsp+B0h] [rbp-50h]
  char v44[398]; // [rsp+B2h] [rbp-4Eh] BYREF
  BYTE v45[512]; // [rsp+240h] [rbp+140h] BYREF

  v2 = -2147024809;
  if ( *(_BYTE *)(GetXdbServerGlobals(a1, a2) + 22940) )
    goto LABEL_22;
  hKey = 0;
  cbData = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\TimeZoneInformation\\",
         0,
         0x20119u,
         &hKey);
  if ( !v4 )
  {
    v5 = hKey;
    if ( !hKey )
      goto LABEL_9;
    v4 = RegQueryValueExW(hKey, L"TimeZoneKeyName", 0, 0, 0, &cbData);
    if ( !v4 )
    {
      v5 = hKey;
      if ( !hKey )
        goto LABEL_9;
      v4 = RegQueryValueExW(hKey, L"TimeZoneKeyName", 0, 0, Data, &cbData);
    }
  }
  v5 = hKey;
  if ( hKey )
    RegCloseKey(hKey);
LABEL_9:
  if ( !cbData || v4 )
    return 2147500037LL;
  v6 = (unsigned __int64)cbData >> 1;
  v7 = GetXdbServerGlobals(v5, v3) + 22942;
  if ( v6 )
  {
    v9 = 2147483646 - v6;
    v10 = &Data[-v7];
    do
    {
      if ( !(v9 + v6) )
        break;
      v11 = *(_WORD *)&v10[v7];
      if ( !v11 )
        break;
      *(_WORD *)v7 = v11;
      v7 += 2;
      --v6;
    }
    while ( v6 );
    v12 = (_WORD *)(v7 - 2);
    if ( v6 )
      v12 = (_WORD *)v7;
    *v12 = 0;
    result = 2147942522LL;
    if ( v6 )
      result = 0;
  }
  else
  {
    result = 2147942487LL;
  }
  if ( !(_DWORD)result )
  {
LABEL_22:
    *(_OWORD *)Data = *(_OWORD *)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Time Zones\\";
    v13 = 0;
    v38 = *(_OWORD *)L"ft\\Windows NT\\CurrentVersion\\Time Zones\\";
    v37 = *(_OWORD *)L"\\Microsoft\\Windows NT\\CurrentVersion\\Time Zones\\";
    v40 = *(_OWORD *)L"rrentVersion\\Time Zones\\";
    v39 = *(_OWORD *)L"ws NT\\CurrentVersion\\Time Zones\\";
    v42 = *(_OWORD *)L"e Zones\\";
    hKey = 0;
    cbData = 0;
    v41 = *(_OWORD *)L"sion\\Time Zones\\";
    v43 = aSoftwareMicros[56];
    memset_0(v44, 0, sizeof(v44));
    XdbServerGlobals = GetXdbServerGlobals(v15, v14);
    v17 = 256;
    v18 = Data;
    v19 = 256;
    v20 = XdbServerGlobals + 22942;
    do
    {
      if ( !*(_WORD *)v18 )
        break;
      v18 += 2;
      --v19;
    }
    while ( v19 );
    v21 = -2147024809;
    if ( v19 )
    {
      v17 = v19;
      v22 = &Data[2 * (256 - v19)];
      v23 = 2147483646;
      v24 = v20 - (_QWORD)v22;
      do
      {
        if ( !v23 )
          break;
        v25 = *(_WORD *)&v22[v24];
        if ( !v25 )
          break;
        *(_WORD *)v22 = v25;
        --v23;
        v22 += 2;
        --v17;
      }
      while ( v17 );
      v26 = v22 - 2;
      if ( v17 )
        v26 = v22;
      *(_WORD *)v26 = 0;
      v21 = -2147024774;
      if ( v17 )
        v21 = 0;
    }
    if ( !v21 )
    {
      v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)Data, 0, 0x20119u, &hKey);
      if ( !v13 )
      {
        v27 = hKey;
        if ( !hKey )
          goto LABEL_43;
        v13 = RegQueryValueExW(hKey, L"Display", 0, 0, 0, &cbData);
        if ( !v13 )
        {
          v27 = hKey;
          if ( !hKey )
            goto LABEL_43;
          v13 = RegQueryValueExW(hKey, L"Display", 0, 0, v45, &cbData);
        }
      }
    }
    v27 = hKey;
    if ( hKey )
      RegCloseKey(hKey);
LABEL_43:
    if ( cbData && !v13 )
    {
      v28 = (unsigned __int64)cbData >> 1;
      v29 = GetXdbServerGlobals(v27, v17) + 23464;
      if ( v28 )
      {
        v30 = 2147483646 - v28;
        v31 = &v45[-v29];
        do
        {
          if ( !(v30 + v28) )
            break;
          v32 = *(_WORD *)&v31[v29];
          if ( !v32 )
            break;
          *(_WORD *)v29 = v32;
          v29 += 2;
          --v28;
        }
        while ( v28 );
        v33 = (_WORD *)(v29 - 2);
        v2 = -2147024774;
        if ( v28 )
        {
          v33 = (_WORD *)v29;
          v2 = 0;
        }
        *v33 = 0;
      }
      return v2;
    }
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x10043ce60  mov     [rsp-8+arg_0], rbx
0x10043ce65  mov     [rsp-8+arg_8], rsi
0x10043ce6a  mov     [rsp-8+arg_10], rdi
0x10043ce6f  mov     [rsp-8+arg_18], r14
0x10043ce74  push    rbp
0x10043ce75  lea     rbp, [rsp-350h]
0x10043ce7d  sub     rsp, 450h
0x10043ce84  mov     rax, cs:__security_cookie
0x10043ce8b  xor     rax, rsp
0x10043ce8e  mov     [rbp+350h+var_10], rax
0x10043ce95  call    cs:__imp_GetXdbServerGlobals
0x10043ce9b  xor     r14d, r14d
0x10043ce9e  mov     esi, 80070057h
0x10043cea3  mov     edi, 7FFFFFFEh
0x10043cea8  cmp     [rax+599Ch], r14b
0x10043ceaf  jnz     loc_10043CFE0
0x10043ceb5  lea     rax, [rsp+450h+hKey]
0x10043ceba  mov     [rsp+450h+hKey], r14
0x10043cebf  mov     r9d, 20119h; samDesired
0x10043cec5  mov     [rsp+450h+phkResult], rax; phkResult
0x10043ceca  xor     r8d, r8d; ulOptions
0x10043cecd  mov     [rsp+450h+cbData], r14d
0x10043ced2  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Tim"...
0x10043ced9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x10043cee0  call    cs:__imp_RegOpenKeyExW
0x10043cee6  mov     ebx, eax
0x10043cee8  test    eax, eax
0x10043ceea  jnz     short loc_10043CF51
0x10043ceec  mov     rcx, [rsp+450h+hKey]; hKey
0x10043cef1  test    rcx, rcx
0x10043cef4  jz      short loc_10043CF61
0x10043cef6  lea     rax, [rsp+450h+cbData]
0x10043cefb  xor     r9d, r9d; lpType
0x10043cefe  mov     [rsp+450h+lpcbData], rax; lpcbData
0x10043cf03  lea     rdx, aTimezonekeynam; "TimeZoneKeyName"
0x10043cf0a  xor     r8d, r8d; lpReserved
0x10043cf0d  mov     [rsp+450h+phkResult], r14; lpData
0x10043cf12  call    cs:__imp_RegQueryValueExW
0x10043cf18  mov     ebx, eax
0x10043cf1a  test    eax, eax
0x10043cf1c  jnz     short loc_10043CF51
0x10043cf1e  mov     rcx, [rsp+450h+hKey]; hKey
0x10043cf23  test    rcx, rcx
0x10043cf26  jz      short loc_10043CF61
0x10043cf28  lea     rax, [rsp+450h+cbData]
0x10043cf2d  xor     r9d, r9d; lpType
0x10043cf30  mov     [rsp+450h+lpcbData], rax; lpcbData
0x10043cf35  lea     rdx, aTimezonekeynam; "TimeZoneKeyName"
0x10043cf3c  lea     rax, [rsp+450h+Data]
0x10043cf41  xor     r8d, r8d; lpReserved
0x10043cf44  mov     [rsp+450h+phkResult], rax; lpData
0x10043cf49  call    cs:__imp_RegQueryValueExW
0x10043cf4f  mov     ebx, eax
0x10043cf51  mov     rcx, [rsp+450h+hKey]; hKey
0x10043cf56  test    rcx, rcx
0x10043cf59  jz      short loc_10043CF61
0x10043cf5b  call    cs:__imp_RegCloseKey
0x10043cf61  mov     eax, [rsp+450h+cbData]
0x10043cf65  test    eax, eax
0x10043cf67  jz      loc_10043D1FB
0x10043cf6d  test    ebx, ebx
0x10043cf6f  jnz     loc_10043D1FB
0x10043cf75  mov     ebx, eax
0x10043cf77  call    cs:__imp_GetXdbServerGlobals
0x10043cf7d  shr     rbx, 1
0x10043cf80  lea     rcx, [rax+599Eh]
0x10043cf87  jnz     short loc_10043CF8D
0x10043cf89  mov     eax, esi
0x10043cf8b  jmp     short loc_10043CFD8
0x10043cf8d  mov     rdx, rdi
0x10043cf90  lea     r8, [rsp+450h+Data]
0x10043cf95  sub     rdx, rbx
0x10043cf98  sub     r8, rcx
0x10043cf9b  nop     dword ptr [rax+rax+00h]
0x10043cfa0  lea     rax, [rdx+rbx]
0x10043cfa4  test    rax, rax
0x10043cfa7  jz      short loc_10043CFC0
0x10043cfa9  movzx   eax, word ptr [r8+rcx]
0x10043cfae  test    ax, ax
0x10043cfb1  jz      short loc_10043CFC0
0x10043cfb3  mov     [rcx], ax
0x10043cfb6  add     rcx, 2
0x10043cfba  sub     rbx, 1
0x10043cfbe  jnz     short loc_10043CFA0
0x10043cfc0  test    rbx, rbx
0x10043cfc3  lea     rax, [rcx-2]
0x10043cfc7  cmovnz  rax, rcx
0x10043cfcb  mov     [rax], r14w
0x10043cfcf  mov     eax, 8007007Ah
0x10043cfd4  cmovnz  eax, r14d
0x10043cfd8  test    eax, eax
0x10043cfda  jnz     loc_10043D200
0x10043cfe0  movaps  xmm0, xmmword ptr cs:aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x10043cfe7  lea     rcx, [rbp+350h+var_39E]; void *
0x10043cfeb  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+10h; "\\Microsoft\\Windows NT\\CurrentVersion"...
0x10043cff2  xor     edx, edx; Val
0x10043cff4  movzx   eax, word ptr cs:aSoftwareMicros+70h; ""
0x10043cffb  mov     r8d, 18Eh; Size
0x10043d001  movaps  xmmword ptr [rsp+450h+Data], xmm0
0x10043d006  mov     ebx, r14d
0x10043d009  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+20h; "ft\\Windows NT\\CurrentVersion\\Time Zo"...
0x10043d010  movaps  [rsp+450h+var_3F0], xmm0
0x10043d015  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+40h; "rrentVersion\\Time Zones\\"
0x10043d01c  movaps  [rsp+450h+var_400], xmm1
0x10043d021  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+30h; "ws NT\\CurrentVersion\\Time Zones\\"
0x10043d028  movaps  [rbp+350h+var_3D0], xmm0
0x10043d02c  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+60h; "e Zones\\"
0x10043d033  movaps  [rsp+450h+var_3E0], xmm1
0x10043d038  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+50h; "sion\\Time Zones\\"
0x10043d03f  movaps  [rbp+350h+var_3B0], xmm0
0x10043d043  mov     [rsp+450h+hKey], r14
0x10043d048  mov     [rsp+450h+cbData], r14d
0x10043d04d  movaps  [rbp+350h+var_3C0], xmm1
0x10043d051  mov     [rbp+350h+var_3A0], ax
0x10043d055  call    memset_0
0x10043d05a  call    cs:__imp_GetXdbServerGlobals
0x10043d060  mov     edx, 100h
0x10043d065  lea     rcx, [rsp+450h+Data]
0x10043d06a  mov     r8d, edx
0x10043d06d  lea     r9, [rax+599Eh]
0x10043d074  cmp     [rcx], bx
0x10043d077  jz      short loc_10043D083
0x10043d079  add     rcx, 2
0x10043d07d  sub     r8, 1
0x10043d081  jnz     short loc_10043D074
0x10043d083  mov     rcx, rdx
0x10043d086  mov     eax, esi
0x10043d088  sub     rcx, r8
0x10043d08b  test    r8, r8
0x10043d08e  cmovz   rcx, r14
0x10043d092  cmovnz  eax, r14d
0x10043d096  jz      short loc_10043D0E1
0x10043d098  sub     rdx, rcx
0x10043d09b  lea     rcx, [rsp+rcx*2+450h+Data]
0x10043d0a0  jz      short loc_10043D0C9
0x10043d0a2  mov     rax, rdi
0x10043d0a5  sub     r9, rcx
0x10043d0a8  test    rax, rax
0x10043d0ab  jz      short loc_10043D0C9
0x10043d0ad  movzx   r8d, word ptr [r9+rcx]
0x10043d0b2  test    r8w, r8w
0x10043d0b6  jz      short loc_10043D0C9
0x10043d0b8  mov     [rcx], r8w
0x10043d0bc  dec     rax
0x10043d0bf  add     rcx, 2
0x10043d0c3  sub     rdx, 1
0x10043d0c7  jnz     short loc_10043D0A8
0x10043d0c9  test    rdx, rdx
0x10043d0cc  lea     rax, [rcx-2]
0x10043d0d0  cmovnz  rax, rcx
0x10043d0d4  mov     [rax], r14w
0x10043d0d8  mov     eax, 8007007Ah
0x10043d0dd  cmovnz  eax, r14d
0x10043d0e1  test    eax, eax
0x10043d0e3  jnz     loc_10043D17B
0x10043d0e9  lea     rax, [rsp+450h+hKey]
0x10043d0ee  mov     r9d, 20119h; samDesired
0x10043d0f4  xor     r8d, r8d; ulOptions
0x10043d0f7  mov     [rsp+450h+phkResult], rax; phkResult
0x10043d0fc  lea     rdx, [rsp+450h+Data]; lpSubKey
0x10043d101  mov     rcx, 0FFFFFFFF80000002h; hKey
0x10043d108  call    cs:__imp_RegOpenKeyExW
0x10043d10e  mov     ebx, eax
0x10043d110  test    eax, eax
0x10043d112  jnz     short loc_10043D17B
0x10043d114  mov     rcx, [rsp+450h+hKey]; hKey
0x10043d119  test    rcx, rcx
0x10043d11c  jz      short loc_10043D18B
0x10043d11e  lea     rax, [rsp+450h+cbData]
0x10043d123  xor     r9d, r9d; lpType
0x10043d126  mov     [rsp+450h+lpcbData], rax; lpcbData
0x10043d12b  lea     rdx, ValueName; "Display"
0x10043d132  xor     r8d, r8d; lpReserved
0x10043d135  mov     [rsp+450h+phkResult], r14; lpData
0x10043d13a  call    cs:__imp_RegQueryValueExW
0x10043d140  mov     ebx, eax
0x10043d142  test    eax, eax
0x10043d144  jnz     short loc_10043D17B
0x10043d146  mov     rcx, [rsp+450h+hKey]; hKey
0x10043d14b  test    rcx, rcx
0x10043d14e  jz      short loc_10043D18B
0x10043d150  lea     rax, [rsp+450h+cbData]
0x10043d155  xor     r9d, r9d; lpType
0x10043d158  mov     [rsp+450h+lpcbData], rax; lpcbData
0x10043d15d  lea     rdx, ValueName; "Display"
0x10043d164  lea     rax, [rbp+350h+var_210]
0x10043d16b  xor     r8d, r8d; lpReserved
0x10043d16e  mov     [rsp+450h+phkResult], rax; lpData
0x10043d173  call    cs:__imp_RegQueryValueExW
0x10043d179  mov     ebx, eax
0x10043d17b  mov     rcx, [rsp+450h+hKey]; hKey
0x10043d180  test    rcx, rcx
0x10043d183  jz      short loc_10043D18B
0x10043d185  call    cs:__imp_RegCloseKey
0x10043d18b  mov     eax, [rsp+450h+cbData]
0x10043d18f  test    eax, eax
0x10043d191  jz      short loc_10043D1FB
0x10043d193  test    ebx, ebx
0x10043d195  jnz     short loc_10043D1FB
0x10043d197  mov     ebx, eax
0x10043d199  call    cs:__imp_GetXdbServerGlobals
0x10043d19f  shr     rbx, 1
0x10043d1a2  lea     rcx, [rax+5BA8h]
0x10043d1a9  jz      short loc_10043D1F7
0x10043d1ab  sub     rdi, rbx
0x10043d1ae  lea     rdx, [rbp+350h+var_210]
0x10043d1b5  sub     rdx, rcx
0x10043d1b8  nop     dword ptr [rax+rax+00000000h]
0x10043d1c0  lea     rax, [rdi+rbx]
0x10043d1c4  test    rax, rax
0x10043d1c7  jz      short loc_10043D1DF
0x10043d1c9  movzx   eax, word ptr [rdx+rcx]
0x10043d1cd  test    ax, ax
0x10043d1d0  jz      short loc_10043D1DF
0x10043d1d2  mov     [rcx], ax
0x10043d1d5  add     rcx, 2
0x10043d1d9  sub     rbx, 1
0x10043d1dd  jnz     short loc_10043D1C0
0x10043d1df  test    rbx, rbx
0x10043d1e2  lea     rax, [rcx-2]
0x10043d1e6  mov     esi, 8007007Ah
0x10043d1eb  cmovnz  rax, rcx
0x10043d1ef  cmovnz  esi, r14d
0x10043d1f3  mov     [rax], r14w
0x10043d1f7  mov     eax, esi
0x10043d1f9  jmp     short loc_10043D200
0x10043d1fb  mov     eax, 80004005h
0x10043d200  mov     rcx, [rbp+350h+var_10]
0x10043d207  xor     rcx, rsp; StackCookie
0x10043d20a  call    __security_check_cookie
0x10043d20f  lea     r11, [rsp+450h+var_s0]
0x10043d217  mov     rbx, [r11+10h]
0x10043d21b  mov     rsi, [r11+18h]
0x10043d21f  mov     rdi, [r11+20h]
0x10043d223  mov     r14, [r11+28h]
0x10043d227  mov     rsp, r11
0x10043d22a  pop     rbp
0x10043d22b  retn
```
