# UserInstanceNameInit(wchar_t const *,wchar_t const *)

- ea: `0x100419c70`
- end: `0x100419fc6`
- name: `?UserInstanceNameInit@@YAXPEB_W0@Z`
- size: `854`
- prototype: `void(const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1004115f0`
- `0x100416770`

## callees

- `0x100401580`
- `0x100401aa0`
- `0x1004198e0`
- `0x100419c70`
- `0x10041eac0`
- `0x10044a2c0`
- `0x10044aad0`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x100419e81`
- `KERNEL32!GetComputerNameExW` at `0x100419e81`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100419d72`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100419ed8`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100419d72`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100419ed8`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100419cd7`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100419d78`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100419e9d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100419ede`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100419cd7`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100419d78`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100419e9d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100419ede`
- `VCRUNTIME140!wcsrchr` at `0x100419cc9`
- `VCRUNTIME140!wcsrchr` at `0x100419cc9`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x100419cea`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x100419cea`
- `instapi160!GetInstanceNameFromID` at `0x100419e4f`
- `instapi160!GetInstanceNameFromID` at `0x100419e4f`
- `instapi160!GetSQLServiceByName` at `0x100419f8b`
- `instapi160!GetSQLServiceByName` at `0x100419f8b`
- `instapi160!GetSvcInstanceIDFromName` at `0x100419e17`
- `instapi160!GetSvcInstanceIDFromName` at `0x100419e17`

## string_xrefs

- `0x100419f5b`: `GetComputerNameEx() initialization failed. Aborting Initialization`
- `0x100419f95`: `Unable to obtain service name.`
- `0x100419d89`: `String Copy Failure (instance name)`

## pseudocode

```c
void __fastcall UserInstanceNameInit(const wchar_t *a1, const wchar_t *a2)
{
  wchar_t *v4; // rsi
  __crt_locale_pointers *DefaultLocale; // rax
  BOOL v6; // ecx
  __int64 v7; // rdx
  _WORD *v8; // rcx
  signed __int64 v9; // r8
  __int16 v10; // ax
  _WORD *v11; // rax
  unsigned int v12; // esi
  struct __crt_locale_pointers *v13; // rax
  int v14; // eax
  char *v15; // rcx
  __int64 v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rax
  RESOURCE *v19; // rbx
  char *v20; // rdi
  struct __crt_locale_pointers *v21; // rax
  signed int v22; // eax
  signed int v23; // ebx
  struct __crt_locale_pointers *v24; // rax
  int v25; // eax
  char *v26; // rcx
  char *v27; // rcx
  __int64 v28; // [rsp+28h] [rbp-540h]
  int v29; // [rsp+30h] [rbp-538h] BYREF
  DWORD nSize[3]; // [rsp+34h] [rbp-534h] BYREF
  WCHAR Buffer[136]; // [rsp+40h] [rbp-528h] BYREF
  char v32[512]; // [rsp+150h] [rbp-418h] BYREF
  char v33[512]; // [rsp+350h] [rbp-218h] BYREF

  if ( !a1 || !a2 )
    FailAndExit("SQL Server User Instance Name not set. Aborting Initialization.");
  *((_DWORD *)qword_10049F360 + 3637) = 1;
  v4 = wcsrchr(a2, 0x2Eu);
  if ( v4 )
  {
    DefaultLocale = GetDefaultLocale();
    v6 = _wcsicmp_l(v4, L".LOCALDB", DefaultLocale) == 0;
  }
  else
  {
    v6 = 0;
  }
  v7 = 261;
  *((_DWORD *)qword_10049F360 + 3638) = v6;
  v8 = (_WORD *)((char *)qword_10049F360 + 43778);
  v9 = (char *)a1 - ((char *)qword_10049F360 + 43778);
  do
  {
    if ( v7 == -2147483385 )
      break;
    v10 = *(_WORD *)((char *)v8 + v9);
    if ( !v10 )
      break;
    *v8++ = v10;
    --v7;
  }
  while ( v7 );
  v11 = v8 - 1;
  v12 = -2147024774;
  if ( v7 )
  {
    v11 = v8;
    v12 = 0;
  }
  *v11 = 0;
  if ( !v7 )
  {
    _mm_lfence();
    SetWin32ExitCode(v12);
    v13 = GetDefaultLocale();
    v14 = StringCchPrintf_lA(v32, 0x200u, "%hs (HRESULT 0x%x)", v13, "String Copy Failure (instance name)", v12);
    v15 = "String Copy Failure (instance name)";
    if ( v14 >= 0 )
      v15 = v32;
    FailAndExit(v15);
  }
  InitSharedBins(v8, v7, v9);
  v16 = -1;
  v17 = -1;
  do
    ++v17;
  while ( a1[v17] );
  if ( (unsigned int)v17 > 0x10 )
    FailAndExit("Error: Instance name exceeds maximum length.");
  v18 = -1;
  do
    ++v18;
  while ( a2[v18] );
  if ( (unsigned int)v18 > 0x10 )
    FailAndExit("Error: Parent iInstance name exceeds maximum length.");
  if ( !(unsigned int)GetSvcInstanceIDFromName(a2, 0, &GlobalInstanceId) )
    FailAndExit("Error getting instance ID from name.");
  v29 = 261;
  if ( !(unsigned int)GetInstanceNameFromID(&GlobalInstanceId, (char *)qword_10049F360 + 45866, &v29) )
    FailAndExit("Error getting instance name.");
  InitRegistryEntries();
  nSize[0] = 129;
  if ( GetComputerNameExW(ComputerNameDnsHostname, Buffer, nSize) )
  {
    v19 = qword_10049F360;
    v20 = (char *)qword_10049F360 + 43778;
    v21 = GetDefaultLocale();
    v22 = StringCchPrintf_lW((wchar_t *)v19 + 22672, 0x105u, L"%ls\\%ls", v21, Buffer, v20);
    v23 = v22;
    if ( v22 < 0 )
    {
      _mm_lfence();
      SetWin32ExitCode(v22);
      v24 = GetDefaultLocale();
      LODWORD(v28) = v23;
      v25 = StringCchPrintf_lA(
              v33,
              0x200u,
              "%hs (HRESULT 0x%x)",
              v24,
              "String Format Failure (full instance name)",
              v28);
      v26 = "String Format Failure (full instance name)";
      if ( v25 >= 0 )
        v26 = v33;
      FailAndExit(v26);
    }
    v27 = (char *)qword_10049F360 + 45344;
    *((_QWORD *)qword_10049F360 + 1466) = (char *)qword_10049F360 + 45344;
    do
      ++v16;
    while ( *(_WORD *)&v27[2 * v16] );
    *((_DWORD *)qword_10049F360 + 2934) = 2 * v16;
  }
  else
  {
    FailAndExit("GetComputerNameEx() initialization failed. Aborting Initialization");
  }
  v29 = 261;
  if ( !(unsigned int)GetSQLServiceByName((char *)qword_10049F360 + 43778, 0, (char *)qword_10049F360 + 46388, &v29) )
    FailAndExit("Unable to obtain service name.");
}

```

## disassembly

```asm
0x100419c70  mov     [rsp+arg_0], rbx
0x100419c75  mov     [rsp+arg_10], rsi
0x100419c7a  push    rdi
0x100419c7b  sub     rsp, 560h
0x100419c82  mov     rax, cs:__security_cookie
0x100419c89  xor     rax, rsp
0x100419c8c  mov     [rsp+568h+var_18], rax
0x100419c94  mov     rbx, rdx
0x100419c97  mov     rdi, rcx
0x100419c9a  test    rcx, rcx
0x100419c9d  jz      short loc_100419CA4
0x100419c9f  test    rdx, rdx
0x100419ca2  jnz     short loc_100419CB0
0x100419ca4  lea     rcx, aSqlServerUserI_0; "SQL Server User Instance Name not set. "...
0x100419cab  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419cb0  mov     rax, cs:qword_10049F360
0x100419cb7  mov     edx, 2Eh ; '.'; Ch
0x100419cbc  mov     rcx, rbx; Str
0x100419cbf  mov     dword ptr [rax+38D4h], 1
0x100419cc9  call    cs:__imp_wcsrchr
0x100419ccf  mov     rsi, rax
0x100419cd2  test    rax, rax
0x100419cd5  jz      short loc_100419CFD
0x100419cd7  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100419cdd  lea     rdx, aLocaldb; ".LOCALDB"
0x100419ce4  mov     rcx, rsi; String1
0x100419ce7  mov     r8, rax; Locale
0x100419cea  call    cs:__imp__wcsicmp_l
0x100419cf0  xor     r9d, r9d
0x100419cf3  test    eax, eax
0x100419cf5  mov     ecx, r9d
0x100419cf8  setz    cl
0x100419cfb  jmp     short loc_100419D03
0x100419cfd  xor     r9d, r9d
0x100419d00  mov     ecx, r9d
0x100419d03  mov     rax, cs:qword_10049F360
0x100419d0a  mov     r8, rdi
0x100419d0d  mov     edx, 105h
0x100419d12  mov     [rax+38D8h], ecx
0x100419d18  mov     rcx, cs:qword_10049F360
0x100419d1f  add     rcx, 0AB02h
0x100419d26  sub     r8, rcx
0x100419d29  nop     dword ptr [rax+00000000h]
0x100419d30  lea     rax, [rdx+7FFFFEF9h]
0x100419d37  test    rax, rax
0x100419d3a  jz      short loc_100419D53
0x100419d3c  movzx   eax, word ptr [r8+rcx]
0x100419d41  test    ax, ax
0x100419d44  jz      short loc_100419D53
0x100419d46  mov     [rcx], ax
0x100419d49  add     rcx, 2
0x100419d4d  sub     rdx, 1
0x100419d51  jnz     short loc_100419D30
0x100419d53  test    rdx, rdx
0x100419d56  lea     rax, [rcx-2]
0x100419d5a  mov     esi, 8007007Ah
0x100419d5f  cmovnz  rax, rcx
0x100419d63  cmovnz  esi, r9d
0x100419d67  mov     [rax], r9w
0x100419d6b  jnz     short loc_100419DBE
0x100419d6d  lfence
0x100419d70  mov     ecx, esi
0x100419d72  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x100419d78  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100419d7e  mov     dword ptr [rsp+568h+var_540], esi
0x100419d82  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x100419d89  lea     rsi, aStringCopyFail_1; "String Copy Failure (instance name)"
0x100419d90  mov     r9, rax; struct __crt_locale_pointers *
0x100419d93  mov     edx, 200h; unsigned __int64
0x100419d98  mov     [rsp+568h+var_548], rsi
0x100419d9d  lea     rcx, [rsp+568h+var_418]; Buffer
0x100419da5  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x100419daa  mov     rcx, rsi
0x100419dad  test    eax, eax
0x100419daf  js      short loc_100419DB9
0x100419db1  lea     rcx, [rsp+568h+var_418]; char *
0x100419db9  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419dbe  call    InitSharedBins
0x100419dc3  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x100419dca  mov     rax, rsi
0x100419dcd  nop     dword ptr [rax]
0x100419dd0  inc     rax
0x100419dd3  cmp     word ptr [rdi+rax*2], 0
0x100419dd8  jnz     short loc_100419DD0
0x100419dda  cmp     eax, 10h
0x100419ddd  jbe     short loc_100419DEB
0x100419ddf  lea     rcx, aErrorInstanceN; "Error: Instance name exceeds maximum le"...
0x100419de6  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419deb  mov     rax, rsi
0x100419dee  xchg    ax, ax
0x100419df0  inc     rax
0x100419df3  cmp     word ptr [rbx+rax*2], 0
0x100419df8  jnz     short loc_100419DF0
0x100419dfa  cmp     eax, 10h
0x100419dfd  jbe     short loc_100419E0B
0x100419dff  lea     rcx, aErrorParentIin; "Error: Parent iInstance name exceeds ma"...
0x100419e06  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419e0b  lea     r8, ?GlobalInstanceId@@3U_INST_ID@@A; _INST_ID GlobalInstanceId
0x100419e12  xor     edx, edx
0x100419e14  mov     rcx, rbx
0x100419e17  call    cs:__imp_GetSvcInstanceIDFromName
0x100419e1d  test    eax, eax
0x100419e1f  jnz     short loc_100419E2D
0x100419e21  lea     rcx, aErrorGettingIn_0; "Error getting instance ID from name."
0x100419e28  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419e2d  mov     rdx, cs:qword_10049F360
0x100419e34  lea     r8, [rsp+568h+var_538]
0x100419e39  add     rdx, 0B32Ah
0x100419e40  mov     [rsp+568h+var_538], 105h
0x100419e48  lea     rcx, ?GlobalInstanceId@@3U_INST_ID@@A; _INST_ID GlobalInstanceId
0x100419e4f  call    cs:__imp_GetInstanceNameFromID
0x100419e55  test    eax, eax
0x100419e57  jnz     short loc_100419E65
0x100419e59  lea     rcx, aErrorGettingIn; "Error getting instance name."
0x100419e60  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419e65  call    ?InitRegistryEntries@@YAXXZ; InitRegistryEntries(void)
0x100419e6a  lea     r8, [rsp+568h+nSize]; nSize
0x100419e6f  mov     [rsp+568h+nSize], 81h
0x100419e77  lea     rdx, [rsp+568h+Buffer]; lpBuffer
0x100419e7c  mov     ecx, 1; NameType
0x100419e81  call    cs:__imp_GetComputerNameExW
0x100419e87  test    eax, eax
0x100419e89  jz      loc_100419F5B
0x100419e8f  mov     rbx, cs:qword_10049F360
0x100419e96  lea     rdi, [rbx+0AB02h]
0x100419e9d  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100419ea3  lea     rcx, [rbx+0B120h]; Buffer
0x100419eaa  mov     [rsp+568h+var_540], rdi
0x100419eaf  mov     r9, rax; struct __crt_locale_pointers *
0x100419eb2  lea     r8, aLsLs_1; "%ls\\%ls"
0x100419eb9  lea     rax, [rsp+568h+Buffer]
0x100419ebe  mov     edx, 105h; unsigned __int64
0x100419ec3  mov     [rsp+568h+var_548], rax
0x100419ec8  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100419ecd  mov     ebx, eax
0x100419ecf  test    eax, eax
0x100419ed1  jns     short loc_100419F24
0x100419ed3  lfence
0x100419ed6  mov     ecx, eax
0x100419ed8  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x100419ede  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100419ee4  mov     dword ptr [rsp+568h+var_540], ebx
0x100419ee8  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x100419eef  lea     rbx, aStringFormatFa; "String Format Failure (full instance na"...
0x100419ef6  mov     r9, rax; struct __crt_locale_pointers *
0x100419ef9  mov     edx, 200h; unsigned __int64
0x100419efe  mov     [rsp+568h+var_548], rbx
0x100419f03  lea     rcx, [rsp+568h+var_218]; Buffer
0x100419f0b  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x100419f10  mov     rcx, rbx
0x100419f13  test    eax, eax
0x100419f15  js      short loc_100419F1F
0x100419f17  lea     rcx, [rsp+568h+var_218]; char *
0x100419f1f  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419f24  mov     rax, cs:qword_10049F360
0x100419f2b  lea     rcx, [rax+0B120h]
0x100419f32  mov     [rax+2DD0h], rcx
0x100419f39  nop     dword ptr [rax+00000000h]
0x100419f40  inc     rsi
0x100419f43  cmp     word ptr [rcx+rsi*2], 0
0x100419f48  jnz     short loc_100419F40
0x100419f4a  mov     rax, cs:qword_10049F360
0x100419f51  add     esi, esi
0x100419f53  mov     [rax+2DD8h], esi
0x100419f59  jmp     short loc_100419F67
0x100419f5b  lea     rcx, aGetcomputernam; "GetComputerNameEx() initialization fail"...
0x100419f62  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419f67  mov     rcx, cs:qword_10049F360
0x100419f6e  lea     r9, [rsp+568h+var_538]
0x100419f73  xor     edx, edx
0x100419f75  mov     [rsp+568h+var_538], 105h
0x100419f7d  lea     r8, [rcx+0B534h]
0x100419f84  add     rcx, 0AB02h
0x100419f8b  call    cs:__imp_GetSQLServiceByName
0x100419f91  test    eax, eax
0x100419f93  jnz     short loc_100419FA1
0x100419f95  lea     rcx, aUnableToObtain; "Unable to obtain service name."
0x100419f9c  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419fa1  mov     rcx, [rsp+568h+var_18]
0x100419fa9  xor     rcx, rsp; StackCookie
0x100419fac  call    __security_check_cookie
0x100419fb1  lea     r11, [rsp+568h+var_8]
0x100419fb9  mov     rbx, [r11+10h]
0x100419fbd  mov     rsi, [r11+20h]
0x100419fc1  mov     rsp, r11
0x100419fc4  pop     rdi
0x100419fc5  retn
```
