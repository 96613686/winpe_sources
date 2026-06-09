# BuildCountryRegistryListFromRCW

- ea: `0x1800030a4`
- end: `0x180003492`
- name: `BuildCountryRegistryListFromRCW`
- size: `1006`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002b1c`

## callees

- `0x180001600`
- `0x1800030a4`
- `0x18001c490`
- `0x18001c8a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180003205`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180003225`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180003337`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180003357`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000339c`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180003205`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180003225`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180003337`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180003357`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000339c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003218`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003233`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003243`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003259`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003269`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000327f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000328f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000334a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003365`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003375`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000341a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003218`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003233`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003243`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003259`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003269`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000327f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000328f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000334a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003365`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003375`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000341a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003172`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000340c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003468`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003172`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000340c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003468`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003165`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003165`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003401`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003458`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003401`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003458`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003112`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800033d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003112`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800033d6`
- `USER32!LoadStringW` at `0x1800031ad`
- `USER32!LoadStringW` at `0x180003325`
- `USER32!LoadStringW` at `0x1800031ad`
- `USER32!LoadStringW` at `0x180003325`

## pseudocode

```c
__int64 BuildCountryRegistryListFromRCW()
{
  LSTATUS v0; // ebx
  int v1; // edi
  __int64 v2; // rdx
  __int64 v3; // r8
  int v4; // ecx
  int v5; // esi
  const wchar_t *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  const wchar_t *v9; // rbx
  wchar_t *v10; // rax
  const wchar_t *v11; // rbx
  wchar_t *v12; // rax
  const wchar_t *v13; // rbx
  int i; // ebx
  int v15; // edi
  __int64 v16; // rdx
  __int64 v17; // r8
  const wchar_t *v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // r8
  wchar_t *v21; // rbx
  __int64 v22; // rdx
  wchar_t *v23; // rsi
  __int64 v24; // r8
  const wchar_t *v25; // rbx
  unsigned int v26; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v29; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+64h] [rbp-9Ch] BYREF
  BYTE v32[8]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int128 v34; // [rsp+80h] [rbp-80h]
  const wchar_t *v35; // [rsp+90h] [rbp-70h]
  wchar_t pszDest[20]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Buffer[256]; // [rsp+C0h] [rbp-40h] BYREF

  v29 = 0;
  hKey = 0;
  dwDisposition = 0;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony",
          0,
          0x20019u,
          &hKey) )
  {
    v0 = RegCreateKeyExW(hKey, L"Country/region List", 0, 0, 0, 0xF003Fu, 0, &v29, &dwDisposition);
    RegCloseKey(hKey);
    if ( !v0 )
    {
      v1 = 1;
      while ( v1 )
      {
        if ( LoadStringW(ghInstance, v1 + 16000, Buffer, 256) <= 0 )
        {
          v1 = 0;
        }
        else
        {
          v33 = 0;
          v35 = 0;
          v4 = 0;
          v34 = 0;
          v5 = 1;
          while ( !v4 )
          {
            if ( v1 == gaTapiDialRulesDeletedIds )
            {
              v5 = 0;
              break;
            }
            v4 = 1;
          }
          LODWORD(v33) = v1;
          *((_QWORD *)&v33 + 1) = (unsigned int)(v1 + 27000);
          DWORD1(v33) = _o__wtol(Buffer, v2, v3);
          v6 = wcschr(Buffer, 0x2Cu) + 1;
          v1 = _o__wtol(v6, v7, v8);
          v9 = wcschr(v6, 0x22u) + 1;
          v10 = wcschr(v9, 0x22u);
          *v10 = 0;
          *(_QWORD *)&v34 = v9;
          v11 = wcschr(v10 + 1, 0x22u) + 1;
          v12 = wcschr(v11, 0x22u);
          *v12 = 0;
          *((_QWORD *)&v34 + 1) = v11;
          v13 = wcschr(v12 + 1, 0x22u) + 1;
          *wcschr(v13, 0x22u) = 0;
          v35 = v13;
          if ( v5 && !(unsigned int)StoreADialingRuleInReg(v29) )
            goto LABEL_29;
        }
      }
      for ( i = 0; i < g_numDialRulesInArray; ++i )
      {
        if ( !(unsigned int)StoreADialingRuleInReg(v29) )
          goto LABEL_29;
      }
      v15 = 1;
      while ( v15 )
      {
        if ( LoadStringW(ghInstance, v15 + 17000, Buffer, 256) <= 0 )
        {
          v15 = 0;
        }
        else
        {
          *(_DWORD *)Data = _o__wtol(Buffer, v16, v17);
          v18 = wcschr(Buffer, 0x2Cu) + 1;
          v15 = _o__wtol(v18, v19, v20);
          v21 = wcschr(v18, 0x22u);
          v23 = wcschr(v21 + 1, 0x22u);
          *v23 = 0;
          while ( v21 )
          {
            v25 = v21 + 1;
            if ( v25 >= v23 )
              break;
            v26 = _o__wtol(v25, v22, v24);
            StringCbPrintfW(pszDest, 0x28u, L"%ld", v26);
            if ( RegOpenKeyExW(v29, pszDest, 0, 0xF003Fu, &hKey) )
              goto LABEL_29;
            RegSetValueExW(hKey, L"CountryGroup", 0, 4u, Data, 4u);
            RegCloseKey(hKey);
            v21 = wcschr(v25, 0x2Cu);
          }
        }
      }
      *(_DWORD *)v32 = 289;
      RegSetValueExW(v29, L"CountryListVersion", 0, 4u, v32, 4u);
    }
  }
LABEL_29:
  if ( v29 )
    RegCloseKey(v29);
  return 1;
}

```

## disassembly

```asm
0x1800030a4  push    rbp
0x1800030a6  push    rbx
0x1800030a7  push    rsi
0x1800030a8  push    rdi
0x1800030a9  push    r12
0x1800030ab  push    r13
0x1800030ad  push    r15
0x1800030af  lea     rbp, [rsp-1D0h]
0x1800030b7  sub     rsp, 2D0h
0x1800030be  mov     rax, cs:__security_cookie
0x1800030c5  xor     rax, rsp
0x1800030c8  mov     [rbp+200h+var_40], rax
0x1800030cf  lea     rax, [rsp+300h+hKey]
0x1800030d4  mov     [rsp+300h+var_2A8], 0
0x1800030dd  mov     r9d, 20019h; samDesired
0x1800030e3  mov     [rsp+300h+phkResult], rax; phkResult
0x1800030e8  xor     r8d, r8d; ulOptions
0x1800030eb  mov     [rsp+300h+hKey], 0
0x1800030f4  lea     rdx, gszRegKeyTelephony; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800030fb  mov     [rsp+300h+dwDisposition], 0
0x180003103  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000310a  mov     dword ptr [rsp+300h+Data], 0
0x180003112  call    cs:__imp_RegOpenKeyExW
0x180003118  mov     r15d, 1
0x18000311e  test    eax, eax
0x180003120  jnz     loc_18000345E
0x180003126  mov     rcx, [rsp+300h+hKey]; hKey
0x18000312b  lea     rax, [rsp+300h+dwDisposition]
0x180003130  mov     [rsp+300h+lpdwDisposition], rax; lpdwDisposition
0x180003135  lea     rdx, SubKey; "Country/region List"
0x18000313c  lea     rax, [rsp+300h+var_2A8]
0x180003141  xor     r9d, r9d; lpClass
0x180003144  mov     [rsp+300h+var_2C8], rax; phkResult
0x180003149  xor     r8d, r8d; Reserved
0x18000314c  mov     [rsp+300h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180003155  mov     [rsp+300h+samDesired], 0F003Fh; samDesired
0x18000315d  mov     dword ptr [rsp+300h+phkResult], 0; dwOptions
0x180003165  call    cs:__imp_RegCreateKeyExW
0x18000316b  mov     rcx, [rsp+300h+hKey]; hKey
0x180003170  mov     ebx, eax
0x180003172  call    cs:__imp_RegCloseKey
0x180003178  test    ebx, ebx
0x18000317a  jnz     loc_18000345E
0x180003180  mov     edi, r15d
0x180003183  lea     r12, __ImageBase
0x18000318a  lea     r13d, [r15+21h]
0x18000318e  test    edi, edi
0x180003190  jz      loc_1800032C9
0x180003196  mov     rcx, cs:ghInstance; hInstance
0x18000319d  lea     edx, [rdi+3E80h]; uID
0x1800031a3  mov     r9d, 100h; cchBufferMax
0x1800031a9  lea     r8, [rbp+200h+Buffer]; lpBuffer
0x1800031ad  call    cs:__imp_LoadStringW
0x1800031b3  test    eax, eax
0x1800031b5  jle     loc_1800032C2
0x1800031bb  xorps   xmm0, xmm0
0x1800031be  xor     eax, eax
0x1800031c0  movups  [rsp+300h+var_290], xmm0
0x1800031c5  mov     [rbp+200h+var_270], rax
0x1800031c9  xor     ecx, ecx
0x1800031cb  movups  [rbp+200h+var_280], xmm0
0x1800031cf  mov     esi, r15d
0x1800031d2  cmp     ecx, r15d
0x1800031d5  jnb     short loc_1800031EB
0x1800031d7  movsxd  rax, ecx
0x1800031da  cmp     edi, ds:rva gaTapiDialRulesDeletedIds[r12+rax*4]
0x1800031e2  jz      short loc_1800031E9
0x1800031e4  add     ecx, r15d
0x1800031e7  jmp     short loc_1800031D2
0x1800031e9  xor     esi, esi
0x1800031eb  lea     eax, [rdi+6978h]
0x1800031f1  mov     dword ptr [rsp+300h+var_290], edi
0x1800031f5  lea     rcx, [rbp+200h+Buffer]
0x1800031f9  mov     dword ptr [rsp+300h+var_290+8], eax
0x1800031fd  mov     dword ptr [rsp+300h+var_290+0Ch], 0
0x180003205  call    cs:__imp__o__wtol
0x18000320b  mov     edx, 2Ch ; ','; Ch
0x180003210  lea     rcx, [rbp+200h+Buffer]; Str
0x180003214  mov     dword ptr [rsp+300h+var_290+4], eax
0x180003218  call    cs:__imp_wcschr
0x18000321e  lea     rbx, [rax+2]
0x180003222  mov     rcx, rbx
0x180003225  call    cs:__imp__o__wtol
0x18000322b  mov     edx, r13d; Ch
0x18000322e  mov     rcx, rbx; Str
0x180003231  mov     edi, eax
0x180003233  call    cs:__imp_wcschr
0x180003239  mov     edx, r13d; Ch
0x18000323c  lea     rbx, [rax+2]
0x180003240  mov     rcx, rbx; Str
0x180003243  call    cs:__imp_wcschr
0x180003249  xor     ecx, ecx
0x18000324b  mov     edx, r13d; Ch
0x18000324e  mov     [rax], cx
0x180003251  lea     rcx, [rax+2]; Str
0x180003255  mov     qword ptr [rbp+200h+var_280], rbx
0x180003259  call    cs:__imp_wcschr
0x18000325f  mov     edx, r13d; Ch
0x180003262  lea     rbx, [rax+2]
0x180003266  mov     rcx, rbx; Str
0x180003269  call    cs:__imp_wcschr
0x18000326f  xor     ecx, ecx
0x180003271  mov     edx, r13d; Ch
0x180003274  mov     [rax], cx
0x180003277  lea     rcx, [rax+2]; Str
0x18000327b  mov     qword ptr [rbp+200h+var_280+8], rbx
0x18000327f  call    cs:__imp_wcschr
0x180003285  mov     edx, r13d; Ch
0x180003288  lea     rbx, [rax+2]
0x18000328c  mov     rcx, rbx; Str
0x18000328f  call    cs:__imp_wcschr
0x180003295  xor     ecx, ecx
0x180003297  mov     [rax], cx
0x18000329a  mov     [rbp+200h+var_270], rbx
0x18000329e  test    esi, esi
0x1800032a0  jz      loc_18000318E
0x1800032a6  mov     rcx, [rsp+300h+var_2A8]; hKey
0x1800032ab  lea     rdx, [rsp+300h+var_290]
0x1800032b0  call    StoreADialingRuleInReg
0x1800032b5  test    eax, eax
0x1800032b7  jz      loc_18000345E
0x1800032bd  jmp     loc_18000318E
0x1800032c2  xor     edi, edi
0x1800032c4  jmp     loc_18000318E
0x1800032c9  xor     ebx, ebx
0x1800032cb  cmp     ebx, cs:g_numDialRulesInArray
0x1800032d1  jge     short loc_1800032FD
0x1800032d3  movsxd  rax, ebx
0x1800032d6  lea     rdx, rva gaTapiDialRules[r12]
0x1800032de  lea     rcx, [rax+rax*4]
0x1800032e2  lea     rdx, [rdx+rcx*8]
0x1800032e6  mov     rcx, [rsp+300h+var_2A8]; hKey
0x1800032eb  call    StoreADialingRuleInReg
0x1800032f0  test    eax, eax
0x1800032f2  jz      loc_18000345E
0x1800032f8  add     ebx, r15d
0x1800032fb  jmp     short loc_1800032CB
0x1800032fd  mov     edi, r15d
0x180003300  mov     r12d, 4
0x180003306  test    edi, edi
0x180003308  jz      loc_18000342F
0x18000330e  mov     rcx, cs:ghInstance; hInstance
0x180003315  lea     edx, [rdi+4268h]; uID
0x18000331b  mov     r9d, 100h; cchBufferMax
0x180003321  lea     r8, [rbp+200h+Buffer]; lpBuffer
0x180003325  call    cs:__imp_LoadStringW
0x18000332b  test    eax, eax
0x18000332d  jle     loc_180003428
0x180003333  lea     rcx, [rbp+200h+Buffer]
0x180003337  call    cs:__imp__o__wtol
0x18000333d  mov     edx, 2Ch ; ','; Ch
0x180003342  lea     rcx, [rbp+200h+Buffer]; Str
0x180003346  mov     dword ptr [rsp+300h+Data], eax
0x18000334a  call    cs:__imp_wcschr
0x180003350  lea     rbx, [rax+2]
0x180003354  mov     rcx, rbx
0x180003357  call    cs:__imp__o__wtol
0x18000335d  mov     edx, r13d; Ch
0x180003360  mov     rcx, rbx; Str
0x180003363  mov     edi, eax
0x180003365  call    cs:__imp_wcschr
0x18000336b  mov     edx, r13d; Ch
0x18000336e  mov     rbx, rax
0x180003371  lea     rcx, [rax+2]; Str
0x180003375  call    cs:__imp_wcschr
0x18000337b  xor     ecx, ecx
0x18000337d  mov     rsi, rax
0x180003380  mov     [rax], cx
0x180003383  test    rbx, rbx
0x180003386  jz      loc_180003306
0x18000338c  add     rbx, 2
0x180003390  cmp     rbx, rsi
0x180003393  jnb     loc_180003306
0x180003399  mov     rcx, rbx
0x18000339c  call    cs:__imp__o__wtol
0x1800033a2  lea     r8, aLd; "%ld"
0x1800033a9  mov     edx, 28h ; '('; cbDest
0x1800033ae  mov     r9d, eax
0x1800033b1  lea     rcx, [rbp+200h+pszDest]; pszDest
0x1800033b5  call    StringCbPrintfW
0x1800033ba  mov     rcx, [rsp+300h+var_2A8]; hKey
0x1800033bf  lea     rax, [rsp+300h+hKey]
0x1800033c4  mov     r9d, 0F003Fh; samDesired
0x1800033ca  mov     [rsp+300h+phkResult], rax; phkResult
0x1800033cf  xor     r8d, r8d; ulOptions
0x1800033d2  lea     rdx, [rbp+200h+pszDest]; lpSubKey
0x1800033d6  call    cs:__imp_RegOpenKeyExW
0x1800033dc  test    eax, eax
0x1800033de  jnz     short loc_18000345E
0x1800033e0  mov     rcx, [rsp+300h+hKey]; hKey
0x1800033e5  lea     rax, [rsp+300h+Data]
0x1800033ea  mov     [rsp+300h+samDesired], r12d; cbData
0x1800033ef  lea     rdx, gszCountryGroupW; "CountryGroup"
0x1800033f6  mov     r9d, r12d; dwType
0x1800033f9  mov     [rsp+300h+phkResult], rax; lpData
0x1800033fe  xor     r8d, r8d; Reserved
0x180003401  call    cs:__imp_RegSetValueExW
0x180003407  mov     rcx, [rsp+300h+hKey]; hKey
0x18000340c  call    cs:__imp_RegCloseKey
0x180003412  mov     edx, 2Ch ; ','; Ch
0x180003417  mov     rcx, rbx; Str
0x18000341a  call    cs:__imp_wcschr
0x180003420  mov     rbx, rax
0x180003423  jmp     loc_180003383
0x180003428  xor     edi, edi
0x18000342a  jmp     loc_180003306
0x18000342f  mov     rcx, [rsp+300h+var_2A8]; hKey
0x180003434  lea     rax, [rsp+300h+var_298]
0x180003439  mov     [rsp+300h+samDesired], r12d; cbData
0x18000343e  lea     rdx, gszCountryListVersionW; "CountryListVersion"
0x180003445  mov     r9d, r12d; dwType
0x180003448  mov     [rsp+300h+phkResult], rax; lpData
0x18000344d  xor     r8d, r8d; Reserved
0x180003450  mov     dword ptr [rsp+300h+var_298], 121h
0x180003458  call    cs:__imp_RegSetValueExW
0x18000345e  mov     rcx, [rsp+300h+var_2A8]; hKey
0x180003463  test    rcx, rcx
0x180003466  jz      short loc_18000346E
0x180003468  call    cs:__imp_RegCloseKey
0x18000346e  mov     eax, r15d
0x180003471  mov     rcx, [rbp+200h+var_40]
0x180003478  xor     rcx, rsp; StackCookie
0x18000347b  call    __security_check_cookie
0x180003480  add     rsp, 2D0h
0x180003487  pop     r15
0x180003489  pop     r13
0x18000348b  pop     r12
0x18000348d  pop     rdi
0x18000348e  pop     rsi
0x18000348f  pop     rbx
0x180003490  pop     rbp
0x180003491  retn
```
