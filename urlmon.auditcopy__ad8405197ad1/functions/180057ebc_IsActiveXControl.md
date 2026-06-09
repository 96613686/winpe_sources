# IsActiveXControl

- ea: `0x180057ebc`
- end: `0x180058300`
- name: `IsActiveXControl`
- size: `1092`
- prototype: `_BOOL8 __fastcall(char *, __int64, const CHAR *, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180057b44`

## callees

- `0x18000521c`
- `0x18005789c`
- `0x180057ebc`
- `0x1800920d0`
- `0x1800a9538`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180057f63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180057f9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180057f63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180057f9c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180058116`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800581db`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180058116`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800581db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180057fd9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18005804d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800580c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180057fd9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18005804d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800580c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058157`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005826c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058282`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058298`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800582ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800582c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058157`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005826c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058282`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058298`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800582ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800582c4`

## string_xrefs

- `0x180057fbd`: `CLSID`
- `0x1800580ad`: `CLSID`
- `0x180058195`: `CLSID`
- `0x180058250`: `clsid:%s`
- `0x1800581fc`: `CLSID\%s\Control`

## pseudocode

```c
_BOOL8 __fastcall IsActiveXControl(char *a1, __int64 a2, const CHAR *a3, const char *a4)
{
  int ValueA; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rax
  HKEY v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // r9
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v22; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v23; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data; // [rsp+70h] [rbp-90h] BYREF
  char v25[271]; // [rsp+71h] [rbp-8Fh] BYREF
  CHAR pvData[272]; // [rsp+180h] [rbp+80h] BYREF
  CHAR SubKey[272]; // [rsp+290h] [rbp+190h] BYREF
  CHAR v28[272]; // [rsp+3A0h] [rbp+2A0h] BYREF

  hKey = 0;
  hkey = 0;
  ValueA = 0;
  phkResult = 0;
  v22 = 0;
  cbData = 0;
  v23 = 0;
  if ( a4 && *a4 )
  {
    StringCchPrintfA(SubKey, 0x104u, "MIME\\Database\\Content Type\\%s", a4);
    ValueA = RegOpenKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey);
    if ( IsInternetExplorerApp() && ValueA == 2 )
      ValueA = RegOpenKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, 0x20219u, &hKey);
    if ( !ValueA )
    {
      cbData = 260;
      ValueA = RegQueryValueExA(hKey, "CLSID", 0, 0, &Data, &cbData);
      if ( !ValueA )
        goto LABEL_25;
    }
  }
  if ( a3 )
  {
    if ( *a3 )
    {
      ValueA = _RegOpenKeyWithWow6432Fallback(HKEY_CLASSES_ROOT, a3, (__int64)a3, (__int64)a4, &hkey);
      if ( !ValueA )
      {
        cbData = 260;
        if ( !RegQueryValueExA(hkey, "Content Type", 0, 0, (LPBYTE)pvData, &cbData) )
        {
          if ( cbData )
          {
            StringCchPrintfA((char *)&Data, 0x104u, "MIME\\Database\\Content Type\\%s", pvData);
            if ( !(unsigned int)_RegOpenKeyWithWow6432Fallback(HKEY_CLASSES_ROOT, (LPCSTR)&Data, v7, v8, &phkResult) )
            {
              cbData = 260;
              if ( !RegQueryValueExA(phkResult, "CLSID", 0, 0, &Data, &cbData) )
              {
                if ( cbData )
                  goto LABEL_25;
              }
            }
          }
        }
        cbData = 260;
        ValueA = RegGetValueA(hkey, 0, 0, 0x10000006u, 0, pvData, &cbData);
        if ( !ValueA )
        {
          if ( cbData )
          {
            v11 = cbData - 1;
            if ( (unsigned int)v11 >= 0x104uLL )
              goto LABEL_40;
            v12 = phkResult;
            pvData[v11] = 0;
            if ( v12 )
            {
              RegCloseKey(v12);
              phkResult = 0;
            }
            ValueA = _RegOpenKeyWithWow6432Fallback(HKEY_CLASSES_ROOT, pvData, v9, v10, &phkResult);
            if ( !ValueA )
            {
              ValueA = _RegOpenKeyWithWow6432Fallback(phkResult, "CLSID", v13, v14, &v22);
              if ( !ValueA )
              {
                cbData = 260;
                ValueA = RegGetValueA(v22, 0, 0, 0x10000006u, 0, &Data, &cbData);
                if ( !ValueA )
                {
                  if ( cbData )
                  {
LABEL_25:
                    StringCchPrintfA(v28, 0x104u, "CLSID\\%s\\Control", (const char *)&Data);
                    ValueA = _RegOpenKeyWithWow6432Fallback(HKEY_CLASSES_ROOT, v28, v15, v16, &v23);
                    if ( !ValueA && a1 )
                    {
                      if ( cbData - 2 < 0x104uLL )
                      {
                        *(&Data + cbData - 2) = 0;
                        StringCchPrintfA(a1, 0x104u, "clsid:%s", v25);
                        goto LABEL_29;
                      }
LABEL_40:
                      _report_rangecheckfailure();
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
LABEL_29:
  if ( v23 )
    RegCloseKey(v23);
  if ( v22 )
    RegCloseKey(v22);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  return ValueA == 0;
}

```

## disassembly

```asm
0x180057ebc  push    rbp
0x180057ebe  push    rbx
0x180057ebf  push    rsi
0x180057ec0  push    rdi
0x180057ec1  push    r12
0x180057ec3  push    r14
0x180057ec5  push    r15
0x180057ec7  lea     rbp, [rsp-3C0h]
0x180057ecf  sub     rsp, 4C0h
0x180057ed6  mov     rax, cs:__security_cookie
0x180057edd  xor     rax, rsp
0x180057ee0  mov     [rbp+3F0h+var_40], rax
0x180057ee7  xor     r14d, r14d
0x180057eea  mov     rdi, r8
0x180057eed  mov     [rsp+4F0h+hKey], r14
0x180057ef2  mov     rsi, rcx
0x180057ef5  mov     [rsp+4F0h+hkey], r14
0x180057efa  mov     ebx, r14d
0x180057efd  mov     [rsp+4F0h+var_4A8], r14
0x180057f02  mov     r15d, 104h
0x180057f08  mov     [rsp+4F0h+var_490], r14
0x180057f0d  mov     r12, 0FFFFFFFF80000000h
0x180057f14  mov     [rsp+4F0h+cbData], r14d
0x180057f19  mov     [rsp+4F0h+var_488], r14
0x180057f1e  test    r9, r9
0x180057f21  jz      loc_180057FEF
0x180057f27  cmp     [r9], r14b
0x180057f2a  jz      loc_180057FEF
0x180057f30  lea     r8, aMimeDatabaseCo; "MIME\\Database\\Content Type\\%s"
0x180057f37  mov     edx, r15d; unsigned __int64
0x180057f3a  lea     rcx, [rbp+3F0h+SubKey]; char *
0x180057f41  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180057f46  lea     rax, [rsp+4F0h+hKey]
0x180057f4b  mov     r9d, 20019h; samDesired
0x180057f51  xor     r8d, r8d; ulOptions
0x180057f54  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180057f59  lea     rdx, [rbp+3F0h+SubKey]; lpSubKey
0x180057f60  mov     rcx, r12; hKey
0x180057f63  call    cs:__imp_RegOpenKeyExA
0x180057f6a  nop     dword ptr [rax+rax+00h]
0x180057f6f  mov     ebx, eax
0x180057f71  call    ?IsInternetExplorerApp@@YAHXZ; IsInternetExplorerApp(void)
0x180057f76  test    eax, eax
0x180057f78  jz      short loc_180057FAA
0x180057f7a  cmp     ebx, 2
0x180057f7d  jnz     short loc_180057FAA
0x180057f7f  lea     rax, [rsp+4F0h+hKey]
0x180057f84  mov     r9d, 20219h; samDesired
0x180057f8a  xor     r8d, r8d; ulOptions
0x180057f8d  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180057f92  lea     rdx, [rbp+3F0h+SubKey]; lpSubKey
0x180057f99  mov     rcx, r12; hKey
0x180057f9c  call    cs:__imp_RegOpenKeyExA
0x180057fa3  nop     dword ptr [rax+rax+00h]
0x180057fa8  mov     ebx, eax
0x180057faa  test    ebx, ebx
0x180057fac  jnz     short loc_180057FEF
0x180057fae  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180057fb3  lea     rax, [rsp+4F0h+cbData]
0x180057fb8  mov     [rsp+4F0h+lpcbData], rax; lpcbData
0x180057fbd  lea     rdx, aClsid_3; "CLSID"
0x180057fc4  lea     rax, [rsp+4F0h+Data]
0x180057fc9  mov     [rsp+4F0h+cbData], r15d
0x180057fce  xor     r9d, r9d; lpType
0x180057fd1  mov     [rsp+4F0h+phkResult], rax; lpData
0x180057fd6  xor     r8d, r8d; lpReserved
0x180057fd9  call    cs:__imp_RegQueryValueExA
0x180057fe0  nop     dword ptr [rax+rax+00h]
0x180057fe5  mov     ebx, eax
0x180057fe7  test    eax, eax
0x180057fe9  jz      loc_1800581F4
0x180057fef  test    rdi, rdi
0x180057ff2  jz      loc_180058262
0x180057ff8  cmp     [rdi], r14b
0x180057ffb  jz      loc_180058262
0x180058001  lea     rax, [rsp+4F0h+hkey]
0x180058006  mov     rdx, rdi; lpSubKey
0x180058009  mov     rcx, r12; hKey
0x18005800c  mov     [rsp+4F0h+phkResult], rax; HKEY *
0x180058011  call    ?_RegOpenKeyWithWow6432Fallback@@YAJPEAUHKEY__@@PEBDKKPEAPEAU1@@Z; _RegOpenKeyWithWow6432Fallback(HKEY__ *,char const *,ulong,ulong,HKEY__ * *)
0x180058016  mov     ebx, eax
0x180058018  test    eax, eax
0x18005801a  jnz     loc_180058262
0x180058020  mov     rcx, [rsp+4F0h+hkey]; hKey
0x180058025  lea     rax, [rsp+4F0h+cbData]
0x18005802a  mov     [rsp+4F0h+lpcbData], rax; lpcbData
0x18005802f  lea     rdx, aContentType_0; "Content Type"
0x180058036  lea     rax, [rbp+3F0h+pvData]
0x18005803d  mov     [rsp+4F0h+cbData], r15d
0x180058042  xor     r9d, r9d; lpType
0x180058045  mov     [rsp+4F0h+phkResult], rax; lpData
0x18005804a  xor     r8d, r8d; lpReserved
0x18005804d  call    cs:__imp_RegQueryValueExA
0x180058054  nop     dword ptr [rax+rax+00h]
0x180058059  test    eax, eax
0x18005805b  jnz     loc_1800580E4
0x180058061  cmp     [rsp+4F0h+cbData], r14d
0x180058066  jbe     short loc_1800580E4
0x180058068  lea     r9, [rbp+3F0h+pvData]
0x18005806f  mov     rdx, r15; unsigned __int64
0x180058072  lea     r8, aMimeDatabaseCo; "MIME\\Database\\Content Type\\%s"
0x180058079  lea     rcx, [rsp+4F0h+Data]; char *
0x18005807e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180058083  lea     rax, [rsp+4F0h+var_4A8]
0x180058088  mov     rcx, r12; hKey
0x18005808b  lea     rdx, [rsp+4F0h+Data]; lpSubKey
0x180058090  mov     [rsp+4F0h+phkResult], rax; HKEY *
0x180058095  call    ?_RegOpenKeyWithWow6432Fallback@@YAJPEAUHKEY__@@PEBDKKPEAPEAU1@@Z; _RegOpenKeyWithWow6432Fallback(HKEY__ *,char const *,ulong,ulong,HKEY__ * *)
0x18005809a  test    eax, eax
0x18005809c  jnz     short loc_1800580E4
0x18005809e  mov     rcx, [rsp+4F0h+var_4A8]; hKey
0x1800580a3  lea     rax, [rsp+4F0h+cbData]
0x1800580a8  mov     [rsp+4F0h+lpcbData], rax; lpcbData
0x1800580ad  lea     rdx, aClsid_3; "CLSID"
0x1800580b4  lea     rax, [rsp+4F0h+Data]
0x1800580b9  mov     [rsp+4F0h+cbData], r15d
0x1800580be  xor     r9d, r9d; lpType
0x1800580c1  mov     [rsp+4F0h+phkResult], rax; lpData
0x1800580c6  xor     r8d, r8d; lpReserved
0x1800580c9  call    cs:__imp_RegQueryValueExA
0x1800580d0  nop     dword ptr [rax+rax+00h]
0x1800580d5  test    eax, eax
0x1800580d7  jnz     short loc_1800580E4
0x1800580d9  cmp     [rsp+4F0h+cbData], r14d
0x1800580de  ja      loc_1800581F4
0x1800580e4  mov     rcx, [rsp+4F0h+hkey]; hkey
0x1800580e9  lea     rax, [rsp+4F0h+cbData]
0x1800580ee  mov     [rsp+4F0h+pcbData], rax; pcbData
0x1800580f3  mov     edi, 10000006h
0x1800580f8  lea     rax, [rbp+3F0h+pvData]
0x1800580ff  mov     [rsp+4F0h+cbData], r15d
0x180058104  mov     [rsp+4F0h+lpcbData], rax; pvData
0x180058109  mov     r9d, edi; dwFlags
0x18005810c  xor     r8d, r8d; lpValue
0x18005810f  mov     [rsp+4F0h+phkResult], r14; pdwType
0x180058114  xor     edx, edx; lpSubKey
0x180058116  call    cs:__imp_RegGetValueA
0x18005811d  nop     dword ptr [rax+rax+00h]
0x180058122  mov     ebx, eax
0x180058124  test    eax, eax
0x180058126  jnz     loc_180058262
0x18005812c  mov     eax, [rsp+4F0h+cbData]
0x180058130  test    eax, eax
0x180058132  jz      loc_180058262
0x180058138  dec     eax
0x18005813a  mov     ecx, eax
0x18005813c  cmp     rcx, r15
0x18005813f  jnb     loc_1800582FA
0x180058145  mov     rcx, [rsp+4F0h+var_4A8]; hKey
0x18005814a  mov     [rbp+rax+3F0h+pvData], r14b
0x180058152  test    rcx, rcx
0x180058155  jz      short loc_180058168
0x180058157  call    cs:__imp_RegCloseKey
0x18005815e  nop     dword ptr [rax+rax+00h]
0x180058163  mov     [rsp+4F0h+var_4A8], r14
0x180058168  lea     rax, [rsp+4F0h+var_4A8]
0x18005816d  mov     rcx, r12; hKey
0x180058170  lea     rdx, [rbp+3F0h+pvData]; lpSubKey
0x180058177  mov     [rsp+4F0h+phkResult], rax; HKEY *
0x18005817c  call    ?_RegOpenKeyWithWow6432Fallback@@YAJPEAUHKEY__@@PEBDKKPEAPEAU1@@Z; _RegOpenKeyWithWow6432Fallback(HKEY__ *,char const *,ulong,ulong,HKEY__ * *)
0x180058181  mov     ebx, eax
0x180058183  test    eax, eax
0x180058185  jnz     loc_180058262
0x18005818b  mov     rcx, [rsp+4F0h+var_4A8]; hKey
0x180058190  lea     rax, [rsp+4F0h+var_490]
0x180058195  lea     rdx, aClsid_3; "CLSID"
0x18005819c  mov     [rsp+4F0h+phkResult], rax; HKEY *
0x1800581a1  call    ?_RegOpenKeyWithWow6432Fallback@@YAJPEAUHKEY__@@PEBDKKPEAPEAU1@@Z; _RegOpenKeyWithWow6432Fallback(HKEY__ *,char const *,ulong,ulong,HKEY__ * *)
0x1800581a6  mov     ebx, eax
0x1800581a8  test    eax, eax
0x1800581aa  jnz     loc_180058262
0x1800581b0  mov     rcx, [rsp+4F0h+var_490]; hkey
0x1800581b5  lea     rax, [rsp+4F0h+cbData]
0x1800581ba  mov     [rsp+4F0h+pcbData], rax; pcbData
0x1800581bf  mov     r9d, edi; dwFlags
0x1800581c2  lea     rax, [rsp+4F0h+Data]
0x1800581c7  mov     [rsp+4F0h+cbData], r15d
0x1800581cc  mov     [rsp+4F0h+lpcbData], rax; pvData
0x1800581d1  xor     r8d, r8d; lpValue
0x1800581d4  xor     edx, edx; lpSubKey
0x1800581d6  mov     [rsp+4F0h+phkResult], r14; pdwType
0x1800581db  call    cs:__imp_RegGetValueA
0x1800581e2  nop     dword ptr [rax+rax+00h]
0x1800581e7  mov     ebx, eax
0x1800581e9  test    eax, eax
0x1800581eb  jnz     short loc_180058262
0x1800581ed  cmp     [rsp+4F0h+cbData], r14d
0x1800581f2  jbe     short loc_180058262
0x1800581f4  lea     r9, [rsp+4F0h+Data]
0x1800581f9  mov     rdx, r15; unsigned __int64
0x1800581fc  lea     r8, aClsidSControl; "CLSID\\%s\\Control"
0x180058203  lea     rcx, [rbp+3F0h+var_150]; char *
0x18005820a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18005820f  lea     rax, [rsp+4F0h+var_488]
0x180058214  mov     rcx, r12; hKey
0x180058217  lea     rdx, [rbp+3F0h+var_150]; lpSubKey
0x18005821e  mov     [rsp+4F0h+phkResult], rax; HKEY *
0x180058223  call    ?_RegOpenKeyWithWow6432Fallback@@YAJPEAUHKEY__@@PEBDKKPEAPEAU1@@Z; _RegOpenKeyWithWow6432Fallback(HKEY__ *,char const *,ulong,ulong,HKEY__ * *)
0x180058228  mov     ebx, eax
0x18005822a  test    eax, eax
0x18005822c  jnz     short loc_180058262
0x18005822e  test    rsi, rsi
0x180058231  jz      short loc_180058262
0x180058233  mov     eax, [rsp+4F0h+cbData]
0x180058237  add     eax, 0FFFFFFFEh
0x18005823a  mov     r8d, eax
0x18005823d  cmp     r8, r15
0x180058240  jnb     loc_1800582FA
0x180058246  lea     r9, [rsp+4F0h+var_47F]
0x18005824b  mov     [rsp+rax+4F0h+Data], r14b
0x180058250  lea     r8, aClsidS_1; "clsid:%s"
0x180058257  mov     rdx, r15; unsigned __int64
0x18005825a  mov     rcx, rsi; char *
0x18005825d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180058262  mov     rcx, [rsp+4F0h+var_488]; hKey
0x180058267  test    rcx, rcx
0x18005826a  jz      short loc_180058278
0x18005826c  call    cs:__imp_RegCloseKey
0x180058273  nop     dword ptr [rax+rax+00h]
0x180058278  mov     rcx, [rsp+4F0h+var_490]; hKey
0x18005827d  test    rcx, rcx
0x180058280  jz      short loc_18005828E
0x180058282  call    cs:__imp_RegCloseKey
0x180058289  nop     dword ptr [rax+rax+00h]
0x18005828e  mov     rcx, [rsp+4F0h+var_4A8]; hKey
0x180058293  test    rcx, rcx
0x180058296  jz      short loc_1800582A4
0x180058298  call    cs:__imp_RegCloseKey
0x18005829f  nop     dword ptr [rax+rax+00h]
0x1800582a4  mov     rcx, [rsp+4F0h+hkey]; hKey
0x1800582a9  test    rcx, rcx
0x1800582ac  jz      short loc_1800582BA
0x1800582ae  call    cs:__imp_RegCloseKey
0x1800582b5  nop     dword ptr [rax+rax+00h]
0x1800582ba  mov     rcx, [rsp+4F0h+hKey]; hKey
0x1800582bf  test    rcx, rcx
0x1800582c2  jz      short loc_1800582D0
0x1800582c4  call    cs:__imp_RegCloseKey
0x1800582cb  nop     dword ptr [rax+rax+00h]
0x1800582d0  test    ebx, ebx
0x1800582d2  mov     eax, r14d
0x1800582d5  setz    al
0x1800582d8  mov     rcx, [rbp+3F0h+var_40]
0x1800582df  xor     rcx, rsp; StackCookie
0x1800582e2  call    __security_check_cookie
0x1800582e7  add     rsp, 4C0h
0x1800582ee  pop     r15
0x1800582f0  pop     r14
0x1800582f2  pop     r12
0x1800582f4  pop     rdi
0x1800582f5  pop     rsi
0x1800582f6  pop     rbx
0x1800582f7  pop     rbp
0x1800582f8  retn
0x1800582fa  call    __report_rangecheckfailure
```
