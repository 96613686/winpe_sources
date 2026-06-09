# LocalVersionOK(HKEY__ *,CLocalComponentInfo *,_GUID *,ulong,ulong,int)

- ea: `0x18007d014`
- end: `0x18007d41d`
- name: `?LocalVersionOK@@YAJPEAUHKEY__@@PEAVCLocalComponentInfo@@PEAU_GUID@@KKH@Z`
- size: `1033`
- prototype: `__int64 __fastcall(HKEY hKey, struct CLocalComponentInfo *, unsigned __int64, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18007bd9c`
- `0x18007c900`

## callees

- `0x18001db50`
- `0x18002fee0`
- `0x1800775e0`
- `0x18007d014`
- `0x18008e5d8`
- `0x1800a25dc`
- `0x1800d1710`
- `0x1800d1b6c`
- `0x1801197fc`
- `0x1801285e6`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18007d262`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18007d262`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18007d285`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18007d285`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18007d238`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18007d238`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007d16c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007d16c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007d123`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007d123`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d3e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d3e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d1d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d1d0`

## pseudocode

```c
__int64 __fastcall LocalVersionOK(
        HKEY hKey,
        struct CLocalComponentInfo *a2,
        const struct _GUID *a3,
        unsigned int a4,
        unsigned int a5,
        int a6)
{
  const struct _GUID *v7; // rsi
  int FileVersionFromCache; // ebx
  void *v11; // rcx
  unsigned int v12; // ebx
  char *v13; // rax
  signed int LastError; // eax
  const char *v15; // r9
  unsigned int v16; // eax
  unsigned int v17; // ecx
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v20; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v23[2]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKeya; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v19 = 0;
  v7 = a3;
  v20 = 0;
  v22[0] = 0;
  v21[0] = 0;
  v23[0] = 0;
  hKeya = 0;
  if ( a3 )
    v7 = (const struct _GUID *)(-(__int64)(memcmp_0(a3, &GUID_NULL, 0x10u) != 0) & (unsigned __int64)a3);
  FileVersionFromCache = 0;
  if ( *(_BYTE *)a2 )
  {
    v11 = (void *)*((_QWORD *)a2 + 34);
    v12 = *((_DWORD *)a2 + 66) - (_DWORD)a2;
    if ( v11 )
    {
      operator delete(v11);
      *((_QWORD *)a2 + 34) = 0;
    }
    v13 = (char *)operator new(v12 + 1);
    *((_QWORD *)a2 + 34) = v13;
    if ( !v13 )
    {
      FileVersionFromCache = -2147024882;
      goto LABEL_49;
    }
    FileVersionFromCache = StringCchCopyNA(v13, v12, (char *)a2, v12 - 1);
  }
  if ( FileVersionFromCache >= 0
    && (a4 || a5 || hKey && !RegOpenKeyExA(hKey, "LanguageCheckPeriod", 0, 0x20019u, &hKeya)) )
  {
    WideCharStr[0] = 0;
    if ( !v7 )
      goto LABEL_22;
    if ( !*(_BYTE *)a2 )
      goto LABEL_34;
    if ( MultiByteToWideChar(0, 0, (LPCCH)a2, -1, WideCharStr, 260) )
    {
      FileVersionFromCache = Ext_GetFileVersionFromCache(v7, WideCharStr, &v19, &v20, v22, v21, v23);
      if ( FileVersionFromCache >= 0 )
      {
        *((_DWORD *)a2 + 76) = v23[0];
        goto LABEL_34;
      }
    }
    else
    {
      LastError = GetLastError();
      FileVersionFromCache = LastError;
      if ( LastError > 0 )
        FileVersionFromCache = (unsigned __int16)LastError | 0x80070000;
    }
    if ( FileVersionFromCache < 0 )
    {
LABEL_22:
      FileVersionFromCache = GetFileVersion(a2, &v19, &v20, v22, v21);
      if ( FileVersionFromCache >= 0 && v7 && WideCharStr[0] )
      {
        if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x759,
            (int)"onecoreuap\\inetcore\\urlmon\\download\\isctrl.cxx",
            v15);
        if ( IsProtectedModeProcess() )
        {
          Ext_SetFileVersionInCache(v7, WideCharStr, v19, v20, v22[0], v21[0], *((_DWORD *)a2 + 76));
        }
        else
        {
          *(_QWORD *)v21 = 0;
          *(_QWORD *)v22 = 0;
          FileVersionFromCache = CoCreateUserBroker((struct IEUserBroker **)v22);
          if ( FileVersionFromCache >= 0 )
          {
            *(_QWORD *)v23 = 0;
            FileVersionFromCache = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, unsigned int *))(**(_QWORD **)v22 + 48LL))(
                                     *(_QWORD *)v22,
                                     &CLSID_CShdocvwBroker,
                                     &IID_IUnknown,
                                     v23);
            if ( FileVersionFromCache >= 0 )
            {
              FileVersionFromCache = (***(__int64 (__fastcall ****)(_QWORD, GUID *, unsigned int *))v23)(
                                       *(_QWORD *)v23,
                                       &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                                       v21);
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 16LL))(*(_QWORD *)v23);
            }
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v22 + 16LL))(*(_QWORD *)v22);
            if ( FileVersionFromCache >= 0 )
            {
              FileVersionFromCache = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *, WCHAR *))(**(_QWORD **)v21 + 152LL))(
                                       *(_QWORD *)v21,
                                       v7,
                                       WideCharStr);
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 16LL))(*(_QWORD *)v21);
            }
          }
        }
      }
    }
LABEL_34:
    if ( FileVersionFromCache )
      goto LABEL_39;
    v16 = v19;
    v17 = v20;
    *((_DWORD *)a2 + 70) = v19;
    *((_DWORD *)a2 + 71) = v17;
    if ( a6 )
    {
      if ( a4 != v16 || a5 != v17 )
      {
LABEL_38:
        FileVersionFromCache = 1;
        goto LABEL_39;
      }
    }
    else if ( a4 > v19 || a4 == v19 && a5 > v20 )
    {
      goto LABEL_38;
    }
    IsRightLanguageLocallyInstalled(a2);
LABEL_39:
    if ( a4 )
    {
      if ( a4 == -1 && a5 == -1 )
        FileVersionFromCache = 1;
    }
    else if ( !a5 )
    {
      FileVersionFromCache = 0;
    }
  }
LABEL_49:
  if ( hKeya )
    RegCloseKey(hKeya);
  return (unsigned int)FileVersionFromCache;
}

```

## disassembly

```asm
0x18007d014  mov     [rsp-8+arg_18], rbx
0x18007d019  push    rbp
0x18007d01a  push    rsi
0x18007d01b  push    rdi
0x18007d01c  push    r12
0x18007d01e  push    r13
0x18007d020  push    r14
0x18007d022  push    r15
0x18007d024  lea     rbp, [rsp-190h]
0x18007d02c  sub     rsp, 290h
0x18007d033  mov     rax, cs:__security_cookie
0x18007d03a  xor     rax, rsp
0x18007d03d  mov     [rbp+1C0h+var_40], rax
0x18007d044  xor     r13d, r13d
0x18007d047  mov     r15d, r9d
0x18007d04a  mov     [rsp+2C0h+var_280], r13d
0x18007d04f  mov     rsi, r8
0x18007d052  mov     [rsp+2C0h+var_27C], r13d
0x18007d057  mov     rdi, rdx
0x18007d05a  mov     [rsp+2C0h+var_270], r13d
0x18007d05f  mov     r12, rcx
0x18007d062  mov     [rsp+2C0h+var_278], r13d
0x18007d067  mov     [rsp+2C0h+var_268], r13d
0x18007d06c  mov     [rsp+2C0h+hKey], r13
0x18007d071  test    r8, r8
0x18007d074  jz      short loc_18007D091
0x18007d076  lea     r8d, [r13+10h]; Size
0x18007d07a  mov     rcx, rsi; Buf1
0x18007d07d  lea     rdx, GUID_NULL; Buf2
0x18007d084  call    memcmp_0
0x18007d089  neg     eax
0x18007d08b  sbb     rcx, rcx
0x18007d08e  and     rsi, rcx
0x18007d091  mov     ebx, r13d
0x18007d094  cmp     [rdi], r13b
0x18007d097  jz      short loc_18007D0E4
0x18007d099  mov     ebx, [rdi+108h]
0x18007d09f  mov     rcx, [rdi+110h]; void *
0x18007d0a6  sub     ebx, edi
0x18007d0a8  test    rcx, rcx
0x18007d0ab  jz      short loc_18007D0B9
0x18007d0ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007d0b2  mov     [rdi+110h], r13
0x18007d0b9  lea     ecx, [rbx+1]; Size
0x18007d0bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007d0c1  mov     [rdi+110h], rax
0x18007d0c8  test    rax, rax
0x18007d0cb  jz      loc_18007D1C6
0x18007d0d1  lea     r9d, [rbx-1]; unsigned __int64
0x18007d0d5  mov     edx, ebx; unsigned __int64
0x18007d0d7  mov     r8, rdi; char *
0x18007d0da  mov     rcx, rax; char *
0x18007d0dd  call    ?StringCchCopyNA@@YAJPEAD_KPEBD1@Z; StringCchCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x18007d0e2  mov     ebx, eax
0x18007d0e4  test    ebx, ebx
0x18007d0e6  js      loc_18007D3DA
0x18007d0ec  mov     r14d, [rbp+1C0h+arg_20]
0x18007d0f3  test    r15d, r15d
0x18007d0f6  jnz     short loc_18007D137
0x18007d0f8  test    r14d, r14d
0x18007d0fb  jnz     short loc_18007D137
0x18007d0fd  test    r12, r12
0x18007d100  jz      loc_18007D3DA
0x18007d106  lea     rax, [rsp+2C0h+hKey]
0x18007d10b  mov     r9d, 20019h; samDesired
0x18007d111  xor     r8d, r8d; ulOptions
0x18007d114  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18007d119  lea     rdx, aLanguagecheckp; "LanguageCheckPeriod"
0x18007d120  mov     rcx, r12; hKey
0x18007d123  call    cs:__imp_RegOpenKeyExA
0x18007d12a  nop     dword ptr [rax+rax+00h]
0x18007d12f  test    eax, eax
0x18007d131  jnz     loc_18007D3DA
0x18007d137  mov     [rsp+2C0h+WideCharStr], r13w
0x18007d13d  test    rsi, rsi
0x18007d140  jz      loc_18007D1F3
0x18007d146  cmp     [rdi], r13b
0x18007d149  jz      loc_18007D370
0x18007d14f  lea     rax, [rsp+2C0h+WideCharStr]
0x18007d154  mov     [rsp+2C0h+cchWideChar], 104h; cchWideChar
0x18007d15c  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18007d160  mov     [rsp+2C0h+phkResult], rax; lpWideCharStr
0x18007d165  mov     r8, rdi; lpMultiByteStr
0x18007d168  xor     edx, edx; dwFlags
0x18007d16a  xor     ecx, ecx; CodePage
0x18007d16c  call    cs:__imp_MultiByteToWideChar
0x18007d173  nop     dword ptr [rax+rax+00h]
0x18007d178  test    eax, eax
0x18007d17a  jz      short loc_18007D1D0
0x18007d17c  lea     rax, [rsp+2C0h+var_268]
0x18007d181  mov     rcx, rsi; struct _GUID *
0x18007d184  mov     [rsp+2C0h+var_290], rax; unsigned int *
0x18007d189  lea     r9, [rsp+2C0h+var_27C]; unsigned int *
0x18007d18e  lea     rax, [rsp+2C0h+var_278]
0x18007d193  mov     qword ptr [rsp+2C0h+cchWideChar], rax; unsigned int *
0x18007d198  lea     r8, [rsp+2C0h+var_280]; unsigned int *
0x18007d19d  lea     rax, [rsp+2C0h+var_270]
0x18007d1a2  lea     rdx, [rsp+2C0h+WideCharStr]; unsigned __int16 *
0x18007d1a7  mov     [rsp+2C0h+phkResult], rax; unsigned int *
0x18007d1ac  call    ?Ext_GetFileVersionFromCache@@YAJAEBU_GUID@@PEBGPEAK2222@Z; Ext_GetFileVersionFromCache(_GUID const &,ushort const *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x18007d1b1  mov     ebx, eax
0x18007d1b3  test    eax, eax
0x18007d1b5  js      short loc_18007D1EB
0x18007d1b7  mov     ecx, [rsp+2C0h+var_268]
0x18007d1bb  mov     [rdi+130h], ecx
0x18007d1c1  jmp     loc_18007D370
0x18007d1c6  mov     ebx, 8007000Eh
0x18007d1cb  jmp     loc_18007D3DA
0x18007d1d0  call    cs:__imp_GetLastError
0x18007d1d7  nop     dword ptr [rax+rax+00h]
0x18007d1dc  mov     ebx, eax
0x18007d1de  test    eax, eax
0x18007d1e0  jle     short loc_18007D1EB
0x18007d1e2  movzx   ebx, ax
0x18007d1e5  or      ebx, 80070000h
0x18007d1eb  test    ebx, ebx
0x18007d1ed  jns     loc_18007D370
0x18007d1f3  lea     rax, [rsp+2C0h+var_278]
0x18007d1f8  mov     rcx, rdi; struct CLocalComponentInfo *
0x18007d1fb  lea     r9, [rsp+2C0h+var_270]; unsigned int *
0x18007d200  mov     [rsp+2C0h+phkResult], rax; unsigned int *
0x18007d205  lea     r8, [rsp+2C0h+var_27C]; unsigned int *
0x18007d20a  lea     rdx, [rsp+2C0h+var_280]; unsigned int *
0x18007d20f  call    ?GetFileVersion@@YAJPEAVCLocalComponentInfo@@PEAK111@Z; GetFileVersion(CLocalComponentInfo *,ulong *,ulong *,ulong *,ulong *)
0x18007d214  mov     ebx, eax
0x18007d216  test    eax, eax
0x18007d218  js      loc_18007D370
0x18007d21e  test    rsi, rsi
0x18007d221  jz      loc_18007D370
0x18007d227  cmp     [rsp+2C0h+WideCharStr], r13w
0x18007d22d  jz      loc_18007D370
0x18007d233  mov     ecx, 1000002Dh
0x18007d238  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18007d23f  nop     dword ptr [rax+rax+00h]
0x18007d244  cmp     eax, 2
0x18007d247  jnz     short loc_18007D262
0x18007d249  mov     rcx, [rbp+1C8h]; this
0x18007d250  lea     r8, aOnecoreuapInet_21; "onecoreuap\\inetcore\\urlmon\\download"...
0x18007d257  mov     edx, 759h; void *
0x18007d25c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18007d262  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x18007d269  nop     dword ptr [rax+rax+00h]
0x18007d26e  test    eax, eax
0x18007d270  jnz     loc_18007D33F
0x18007d276  lea     rcx, [rsp+2C0h+var_270]
0x18007d27b  mov     qword ptr [rsp+2C0h+var_278], r13
0x18007d280  mov     qword ptr [rsp+2C0h+var_270], r13
0x18007d285  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18007d28c  nop     dword ptr [rax+rax+00h]
0x18007d291  mov     ebx, eax
0x18007d293  test    eax, eax
0x18007d295  js      loc_18007D370
0x18007d29b  mov     rcx, qword ptr [rsp+2C0h+var_270]
0x18007d2a0  lea     r9, [rsp+2C0h+var_268]
0x18007d2a5  mov     qword ptr [rsp+2C0h+var_268], r13
0x18007d2aa  lea     r8, IID_IUnknown
0x18007d2b1  lea     rdx, CLSID_CShdocvwBroker
0x18007d2b8  mov     rax, [rcx]
0x18007d2bb  mov     rax, [rax+30h]
0x18007d2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d2c4  mov     ebx, eax
0x18007d2c6  test    eax, eax
0x18007d2c8  js      short loc_18007D2F9
0x18007d2ca  mov     rcx, qword ptr [rsp+2C0h+var_268]
0x18007d2cf  lea     r8, [rsp+2C0h+var_278]
0x18007d2d4  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x18007d2db  mov     rax, [rcx]
0x18007d2de  mov     rax, [rax]
0x18007d2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d2e6  mov     rcx, qword ptr [rsp+2C0h+var_268]
0x18007d2eb  mov     ebx, eax
0x18007d2ed  mov     rax, [rcx]
0x18007d2f0  mov     rax, [rax+10h]
0x18007d2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d2f9  mov     rcx, qword ptr [rsp+2C0h+var_270]
0x18007d2fe  mov     rax, [rcx]
0x18007d301  mov     rax, [rax+10h]
0x18007d305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d30a  test    ebx, ebx
0x18007d30c  js      short loc_18007D370
0x18007d30e  mov     rcx, qword ptr [rsp+2C0h+var_278]
0x18007d313  lea     r8, [rsp+2C0h+WideCharStr]
0x18007d318  mov     rdx, rsi
0x18007d31b  mov     rax, [rcx]
0x18007d31e  mov     rax, [rax+98h]
0x18007d325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d32a  mov     rcx, qword ptr [rsp+2C0h+var_278]
0x18007d32f  mov     ebx, eax
0x18007d331  mov     rax, [rcx]
0x18007d334  mov     rax, [rax+10h]
0x18007d338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d33d  jmp     short loc_18007D370
0x18007d33f  mov     eax, [rdi+130h]
0x18007d345  lea     rdx, [rsp+2C0h+WideCharStr]; unsigned __int16 *
0x18007d34a  mov     r9d, [rsp+2C0h+var_27C]; unsigned int
0x18007d34f  mov     rcx, rsi; struct _GUID *
0x18007d352  mov     r8d, [rsp+2C0h+var_280]; unsigned int
0x18007d357  mov     dword ptr [rsp+2C0h+var_290], eax; unsigned int
0x18007d35b  mov     eax, [rsp+2C0h+var_278]
0x18007d35f  mov     [rsp+2C0h+cchWideChar], eax; unsigned int
0x18007d363  mov     eax, [rsp+2C0h+var_270]
0x18007d367  mov     dword ptr [rsp+2C0h+phkResult], eax; unsigned int
0x18007d36b  call    ?Ext_SetFileVersionInCache@@YAJAEBU_GUID@@PEBGKKKKK@Z; Ext_SetFileVersionInCache(_GUID const &,ushort const *,ulong,ulong,ulong,ulong,ulong)
0x18007d370  mov     esi, 1
0x18007d375  test    ebx, ebx
0x18007d377  jnz     short loc_18007D3A2
0x18007d379  mov     eax, [rsp+2C0h+var_280]
0x18007d37d  mov     ecx, [rsp+2C0h+var_27C]
0x18007d381  mov     [rdi+118h], eax
0x18007d387  mov     [rdi+11Ch], ecx
0x18007d38d  cmp     [rbp+1C0h+arg_28], r13d
0x18007d394  jz      short loc_18007D3B1
0x18007d396  cmp     r15d, eax
0x18007d399  jnz     short loc_18007D3A0
0x18007d39b  cmp     r14d, ecx
0x18007d39e  jz      short loc_18007D3C1
0x18007d3a0  mov     ebx, esi
0x18007d3a2  test    r15d, r15d
0x18007d3a5  jnz     short loc_18007D3CB
0x18007d3a7  test    r14d, r14d
0x18007d3aa  jnz     short loc_18007D3DA
0x18007d3ac  mov     ebx, r13d
0x18007d3af  jmp     short loc_18007D3DA
0x18007d3b1  cmp     r15d, [rsp+2C0h+var_280]
0x18007d3b6  ja      short loc_18007D3A0
0x18007d3b8  jnz     short loc_18007D3C1
0x18007d3ba  cmp     r14d, [rsp+2C0h+var_27C]
0x18007d3bf  ja      short loc_18007D3A0
0x18007d3c1  mov     rcx, rdi; struct CLocalComponentInfo *
0x18007d3c4  call    ?IsRightLanguageLocallyInstalled@@YAJPEAVCLocalComponentInfo@@@Z; IsRightLanguageLocallyInstalled(CLocalComponentInfo *)
0x18007d3c9  jmp     short loc_18007D3A2
0x18007d3cb  or      eax, 0FFFFFFFFh
0x18007d3ce  cmp     r15d, eax
0x18007d3d1  jnz     short loc_18007D3DA
0x18007d3d3  cmp     r14d, eax
0x18007d3d6  jnz     short loc_18007D3DA
0x18007d3d8  mov     ebx, esi
0x18007d3da  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18007d3df  test    rcx, rcx
0x18007d3e2  jz      short loc_18007D3F0
0x18007d3e4  call    cs:__imp_RegCloseKey
0x18007d3eb  nop     dword ptr [rax+rax+00h]
0x18007d3f0  mov     eax, ebx
0x18007d3f2  mov     rcx, [rbp+1C0h+var_40]
0x18007d3f9  xor     rcx, rsp; StackCookie
0x18007d3fc  call    __security_check_cookie
0x18007d401  mov     rbx, [rsp+2C0h+arg_18]
0x18007d409  add     rsp, 290h
0x18007d410  pop     r15
0x18007d412  pop     r14
0x18007d414  pop     r13
0x18007d416  pop     r12
0x18007d418  pop     rdi
0x18007d419  pop     rsi
0x18007d41a  pop     rbp
0x18007d41b  retn
```
