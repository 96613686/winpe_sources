# PersistUpdateCallbackInfo(_GUID const &,_GUID const &,void const *,ulong,int)

- ea: `0x1800934e8`
- end: `0x1800937ef`
- name: `?PersistUpdateCallbackInfo@@YAJAEBU_GUID@@0PEBXKH@Z`
- size: `775`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, const void *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180093404`

## callees

- `0x180006ac4`
- `0x18002ded8`
- `0x180090bc8`
- `0x180092748`
- `0x180092878`
- `0x1800934e8`
- `0x180093cf4`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009356c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009358d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009356c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009358d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180093763`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180093763`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180093728`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180093728`

## string_xrefs

- `0x1800937ae`: `PersistUpdateCallbackInfo: idSrv=%ws, UpdateId=%ws, callback info length=%u`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PersistUpdateCallbackInfo(const struct _GUID *a1, const struct _GUID *a2, const void *a3, int a4)
{
  int v6; // ebx
  __int64 v7; // rdx
  __int64 RegKeyPath; // rax
  wchar_t *v10; // rdx
  __int64 v11; // r9
  __int64 v12; // r8
  wchar_t v13; // ax
  wchar_t *v14; // rax
  signed int v15; // edi
  __int64 v16; // rdx
  __int64 v17; // rdx
  WCHAR *v18; // rcx
  WCHAR v19; // ax
  WCHAR *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // r8
  struct _FILETIME *p_SystemTimeAsFileTime; // [rsp+20h] [rbp-E0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR v26[40]; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[264]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t v29[264]; // [rsp+310h] [rbp+210h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+568h] [rbp+468h]

  if ( !a3 )
  {
    v6 = -2147467261;
    v7 = 3671;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\RegUtil\\RegUtil.cpp",
      (const char *)(unsigned int)v6,
      (int)p_SystemTimeAsFileTime);
    return (unsigned int)v6;
  }
  if ( !a4 )
  {
    v6 = -2147024809;
    v7 = 3672;
    goto LABEL_3;
  }
  SystemTimeAsFileTime = 0;
  if ( !StringFromGUID2(a1, sz, 39) )
  {
    v6 = -2147024774;
    v7 = 3681;
    goto LABEL_3;
  }
  if ( !StringFromGUID2(a2, v26, 39) )
  {
    v6 = -2147024774;
    v7 = 3683;
    goto LABEL_3;
  }
  RegKeyPath = GetRegKeyPath(23);
  v10 = v29;
  v11 = RegKeyPath - (_QWORD)v29;
  v12 = 260;
  do
  {
    if ( v12 == -2147483386 )
      break;
    v13 = *(wchar_t *)((char *)v10 + v11);
    if ( !v13 )
      break;
    *v10++ = v13;
    --v12;
  }
  while ( v12 );
  v14 = v10 - 1;
  if ( v12 )
    v14 = v10;
  *v14 = 0;
  v15 = v12 == 0 ? 0x8007007A : 0;
  if ( !v12 )
  {
    v16 = 3686;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\RegUtil\\RegUtil.cpp",
      (const char *)(unsigned int)v15,
      (int)p_SystemTimeAsFileTime);
    return (unsigned int)v15;
  }
  v15 = StringCchCatW(v29, 0x104u, L"\\");
  if ( v15 < 0 )
  {
    v16 = 3687;
    goto LABEL_18;
  }
  v15 = StringCchCatW(v29, 0x104u, sz);
  if ( v15 < 0 )
  {
    v16 = 3688;
    goto LABEL_18;
  }
  v17 = 260;
  v18 = SubKey;
  do
  {
    if ( v17 == -2147483386 )
      break;
    v19 = v18[264];
    if ( !v19 )
      break;
    *v18++ = v19;
    --v17;
  }
  while ( v17 );
  v20 = v18 - 1;
  if ( v17 )
    v20 = v18;
  *v20 = 0;
  v15 = v17 == 0 ? 0x8007007A : 0;
  if ( !v17 )
  {
    v16 = 3689;
    goto LABEL_18;
  }
  v6 = StringCchCatW(SubKey, 0x104u, L"\\");
  if ( v6 < 0 )
  {
    v7 = 3690;
    goto LABEL_3;
  }
  v6 = StringCchCatW(SubKey, 0x104u, v26);
  if ( v6 < 0 )
  {
    v7 = 3691;
    goto LABEL_3;
  }
  RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
  LODWORD(p_SystemTimeAsFileTime) = 3;
  v6 = RegSetValue_Helper(v21, SubKey, 0, 0);
  if ( v6 < 0 )
  {
    v7 = 3697;
    goto LABEL_3;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  p_SystemTimeAsFileTime = &SystemTimeAsFileTime;
  v6 = RegSetFileTimeValue_Helper(v22, SubKey, v23, L"LastRefreshTime");
  if ( v6 < 0 )
  {
    v7 = 3702;
    goto LABEL_3;
  }
  WUTrace(0, 0, 32, 5, 0, L"PersistUpdateCallbackInfo: idSrv=%ws, UpdateId=%ws, callback info length=%u", sz, v26, a4);
  return 0;
}

```

## disassembly

```asm
0x1800934e8  push    rbp
0x1800934ea  push    rbx
0x1800934eb  push    rsi
0x1800934ec  push    rdi
0x1800934ed  push    r12
0x1800934ef  push    r14
0x1800934f1  push    r15
0x1800934f3  lea     rbp, [rsp-430h]
0x1800934fb  sub     rsp, 530h
0x180093502  mov     rax, cs:__security_cookie
0x180093509  xor     rax, rsp
0x18009350c  mov     [rbp+460h+var_40], rax
0x180093513  xor     r15d, r15d
0x180093516  mov     esi, r9d
0x180093519  mov     r14, r8
0x18009351c  mov     rbx, rdx
0x18009351f  test    r8, r8
0x180093522  jnz     short loc_18009354B
0x180093524  mov     ebx, 80004003h
0x180093529  mov     edx, 0E57h; void *
0x18009352e  mov     rcx, [rbp+468h]; this
0x180093535  lea     r8, aCW1SSrcClientL_7; "C:\\__w\\1\\s\\src\\Client\\lib\\RegUti"...
0x18009353c  mov     r9d, ebx; char *
0x18009353f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093544  mov     eax, ebx
0x180093546  jmp     loc_1800937CE
0x18009354b  test    esi, esi
0x18009354d  jnz     short loc_18009355B
0x18009354f  mov     ebx, 80070057h
0x180093554  mov     edx, 0E58h
0x180093559  jmp     short loc_18009352E
0x18009355b  mov     edi, 27h ; '''
0x180093560  mov     qword ptr [rsp+560h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180093565  mov     r8d, edi; cchMax
0x180093568  lea     rdx, [rbp+460h+sz]; lpsz
0x18009356c  call    cs:__imp_StringFromGUID2
0x180093572  test    eax, eax
0x180093574  jnz     short loc_180093582
0x180093576  mov     ebx, 8007007Ah
0x18009357b  mov     edx, 0E61h
0x180093580  jmp     short loc_18009352E
0x180093582  mov     r8d, edi; cchMax
0x180093585  lea     rdx, [rsp+560h+var_500]; lpsz
0x18009358a  mov     rcx, rbx; rguid
0x18009358d  call    cs:__imp_StringFromGUID2
0x180093593  test    eax, eax
0x180093595  jnz     short loc_1800935A3
0x180093597  mov     ebx, 8007007Ah
0x18009359c  mov     edx, 0E63h
0x1800935a1  jmp     short loc_18009352E
0x1800935a3  mov     ecx, 17h
0x1800935a8  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x1800935ad  mov     r9, rax
0x1800935b0  lea     rdx, [rbp+460h+var_250]
0x1800935b7  lea     rax, [rbp+460h+var_250]
0x1800935be  mov     r12d, 104h
0x1800935c4  sub     r9, rax
0x1800935c7  mov     r8d, r12d
0x1800935ca  lea     rcx, [r8+7FFFFEFAh]
0x1800935d1  test    rcx, rcx
0x1800935d4  jz      short loc_1800935ED
0x1800935d6  movzx   eax, word ptr [rdx+r9]
0x1800935db  test    ax, ax
0x1800935de  jz      short loc_1800935ED
0x1800935e0  mov     [rdx], ax
0x1800935e3  add     rdx, 2
0x1800935e7  sub     r8, 1
0x1800935eb  jnz     short loc_1800935CA
0x1800935ed  test    r8, r8
0x1800935f0  lea     rax, [rdx-2]
0x1800935f4  mov     ebx, 8007007Ah
0x1800935f9  cmovnz  rax, rdx
0x1800935fd  mov     [rax], r15w
0x180093601  mov     rax, r8
0x180093604  neg     rax
0x180093607  sbb     edi, edi
0x180093609  not     edi
0x18009360b  and     edi, ebx
0x18009360d  test    r8, r8
0x180093610  jnz     short loc_180093634
0x180093612  mov     edx, 0E66h; void *
0x180093617  mov     rcx, [rbp+468h]; this
0x18009361e  lea     r8, aCW1SSrcClientL_7; "C:\\__w\\1\\s\\src\\Client\\lib\\RegUti"...
0x180093625  mov     r9d, edi; char *
0x180093628  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009362d  mov     eax, edi
0x18009362f  jmp     loc_1800937CE
0x180093634  lea     r8, SubBlock; "\\"
0x18009363b  mov     rdx, r12; unsigned __int64
0x18009363e  lea     rcx, [rbp+460h+var_250]; wchar_t *
0x180093645  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18009364a  mov     edi, eax
0x18009364c  test    eax, eax
0x18009364e  jns     short loc_180093657
0x180093650  mov     edx, 0E67h
0x180093655  jmp     short loc_180093617
0x180093657  lea     r8, [rbp+460h+sz]; wchar_t *
0x18009365b  mov     rdx, r12; unsigned __int64
0x18009365e  lea     rcx, [rbp+460h+var_250]; wchar_t *
0x180093665  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18009366a  mov     edi, eax
0x18009366c  test    eax, eax
0x18009366e  jns     short loc_180093677
0x180093670  mov     edx, 0E68h
0x180093675  jmp     short loc_180093617
0x180093677  lea     r8, [rbp+460h+var_250]
0x18009367e  mov     rdx, r12
0x180093681  lea     rax, [rbp+460h+SubKey]
0x180093685  sub     r8, rax
0x180093688  lea     rcx, [rbp+460h+SubKey]
0x18009368c  lea     rax, [rdx+7FFFFEFAh]
0x180093693  test    rax, rax
0x180093696  jz      short loc_1800936AF
0x180093698  movzx   eax, word ptr [r8+rcx]
0x18009369d  test    ax, ax
0x1800936a0  jz      short loc_1800936AF
0x1800936a2  mov     [rcx], ax
0x1800936a5  add     rcx, 2
0x1800936a9  sub     rdx, 1
0x1800936ad  jnz     short loc_18009368C
0x1800936af  test    rdx, rdx
0x1800936b2  lea     rax, [rcx-2]
0x1800936b6  cmovnz  rax, rcx
0x1800936ba  mov     [rax], r15w
0x1800936be  mov     rax, rdx
0x1800936c1  neg     rax
0x1800936c4  sbb     edi, edi
0x1800936c6  not     edi
0x1800936c8  and     edi, ebx
0x1800936ca  test    rdx, rdx
0x1800936cd  jnz     short loc_1800936D9
0x1800936cf  mov     edx, 0E69h
0x1800936d4  jmp     loc_180093617
0x1800936d9  lea     r8, SubBlock; "\\"
0x1800936e0  mov     rdx, r12; unsigned __int64
0x1800936e3  lea     rcx, [rbp+460h+SubKey]; wchar_t *
0x1800936e7  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800936ec  mov     ebx, eax
0x1800936ee  test    eax, eax
0x1800936f0  jns     short loc_1800936FC
0x1800936f2  mov     edx, 0E6Ah
0x1800936f7  jmp     loc_18009352E
0x1800936fc  lea     r8, [rsp+560h+var_500]; wchar_t *
0x180093701  mov     rdx, r12; unsigned __int64
0x180093704  lea     rcx, [rbp+460h+SubKey]; wchar_t *
0x180093708  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18009370d  mov     ebx, eax
0x18009370f  test    eax, eax
0x180093711  jns     short loc_18009371D
0x180093713  mov     edx, 0E6Bh
0x180093718  jmp     loc_18009352E
0x18009371d  lea     rdx, [rbp+460h+SubKey]; lpSubKey
0x180093721  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180093728  call    cs:__imp_RegDeleteKeyW
0x18009372e  mov     dword ptr [rsp+560h+var_530], esi
0x180093732  lea     rdx, [rbp+460h+SubKey]
0x180093736  mov     [rsp+560h+var_538], r14
0x18009373b  xor     r9d, r9d
0x18009373e  xor     r8d, r8d
0x180093741  mov     dword ptr [rsp+560h+var_540], 3
0x180093749  call    RegSetValue_Helper
0x18009374e  mov     ebx, eax
0x180093750  test    eax, eax
0x180093752  jns     short loc_18009375E
0x180093754  mov     edx, 0E71h
0x180093759  jmp     loc_18009352E
0x18009375e  lea     rcx, [rsp+560h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180093763  call    cs:__imp_GetSystemTimeAsFileTime
0x180093769  lea     rax, [rsp+560h+SystemTimeAsFileTime]
0x18009376e  lea     r9, aLastrefreshtim; "LastRefreshTime"
0x180093775  mov     [rsp+560h+var_540], rax
0x18009377a  lea     rdx, [rbp+460h+SubKey]
0x18009377e  call    ?RegSetFileTimeValue_Helper@@YAJPEAUHKEY__@@PEB_W11AEBU_FILETIME@@W4RegistryHiveType@@@Z; RegSetFileTimeValue_Helper(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,_FILETIME const &,RegistryHiveType)
0x180093783  mov     ebx, eax
0x180093785  test    eax, eax
0x180093787  jns     short loc_180093793
0x180093789  mov     edx, 0E76h
0x18009378e  jmp     loc_18009352E
0x180093793  mov     [rsp+560h+var_520], esi
0x180093797  lea     rax, [rsp+560h+var_500]
0x18009379c  mov     [rsp+560h+var_528], rax
0x1800937a1  xor     edx, edx
0x1800937a3  lea     rax, [rbp+460h+sz]
0x1800937a7  xor     ecx, ecx
0x1800937a9  mov     [rsp+560h+var_530], rax
0x1800937ae  lea     rax, aPersistupdatec; "PersistUpdateCallbackInfo: idSrv=%ws, U"...
0x1800937b5  mov     [rsp+560h+var_538], rax
0x1800937ba  lea     r9d, [rdx+5]
0x1800937be  mov     [rsp+560h+var_540], r15
0x1800937c3  lea     r8d, [rdx+20h]
0x1800937c7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800937cc  xor     eax, eax
0x1800937ce  mov     rcx, [rbp+460h+var_40]
0x1800937d5  xor     rcx, rsp; StackCookie
0x1800937d8  call    __security_check_cookie
0x1800937dd  add     rsp, 530h
0x1800937e4  pop     r15
0x1800937e6  pop     r14
0x1800937e8  pop     r12
0x1800937ea  pop     rdi
0x1800937eb  pop     rsi
0x1800937ec  pop     rbx
0x1800937ed  pop     rbp
0x1800937ee  retn
```
