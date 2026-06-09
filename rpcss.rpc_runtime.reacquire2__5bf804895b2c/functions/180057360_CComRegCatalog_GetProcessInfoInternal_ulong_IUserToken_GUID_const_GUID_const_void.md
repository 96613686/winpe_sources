# CComRegCatalog::GetProcessInfoInternal(ulong,IUserToken *,_GUID const &,_GUID const &,void * *)

- ea: `0x180057360`
- end: `0x180057bad`
- name: `?GetProcessInfoInternal@CComRegCatalog@@UEAAJKPEAUIUserToken@@AEBU_GUID@@1PEAPEAX@Z`
- size: `2125`
- prototype: `int(CComRegCatalog *__hidden this, unsigned int, struct IUserToken *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800d2920`

## callees

- `0x180009e9c`
- `0x18001a374`
- `0x18001c624`
- `0x1800210f8`
- `0x180024790`
- `0x180034260`
- `0x180057360`
- `0x18005ad10`
- `0x1800782dc`
- `0x180081158`
- `0x18008172c`
- `0x1800b7ac0`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005790a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005790a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057899`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057b11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057899`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057b11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800577b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800577b7`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18005778a`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x1800577d2`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18005778a`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x1800577d2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005761e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005761e`

## string_xrefs

- `0x18005743c`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180057582`: `onecore\com\combase\catalog\regcat.cxx`
- `0x1800578e2`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180057b87`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180057443`: `CComRegCatalog::GetProcessInfoInternal`
- `0x18005757b`: `CComRegCatalog::GetProcessInfoInternal`
- `0x180057b7b`: `CComRegCatalog::GetProcessInfoInternal`

## pseudocode

```c
__int64 __fastcall CComRegCatalog::GetProcessInfoInternal(
        CComRegCatalog *this,
        int a2,
        struct IUserToken *a3,
        struct _GUID *a4,
        const struct _GUID *a5,
        void **a6)
{
  struct _GUID *v7; // r13
  struct IUserToken *v8; // rsi
  int v10; // ecx
  HKEY *v12; // rdi
  int v13; // r12d
  int v14; // eax
  signed int v15; // ebx
  int v16; // r9d
  __int64 (__fastcall **v17)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v18; // rcx
  const unsigned __int16 *v19; // r8
  __int64 v20; // rdx
  WCHAR *v21; // rax
  WCHAR *v22; // rcx
  __int64 *v23; // r9
  struct _GUID *v24; // r10
  unsigned int v25; // eax
  unsigned __int8 Data1; // dl
  __int64 v27; // r8
  WCHAR v28; // ax
  WCHAR v29; // ax
  int v30; // r15d
  unsigned __int16 v31; // r13
  HKEY v32; // rbx
  int v33; // eax
  HKEY v34; // rax
  int v35; // eax
  LPVOID v36; // rax
  char v37; // al
  HKEY v38; // rcx
  char v39; // al
  HKEY v40; // rcx
  char v41; // al
  HKEY v42; // rcx
  char v43; // al
  HKEY v44; // rcx
  char v45; // al
  HKEY v46; // rcx
  char v47; // al
  HKEY v48; // rcx
  char v49; // r12
  bool v50; // r13
  char v51; // r15
  char v52; // r14
  char v53; // si
  char v54; // bl
  int v55; // edi
  HKEY v56; // rax
  CComProcessInfo *v57; // rdi
  unsigned int v58; // edx
  CGuidStr *v59; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-100h]
  int phkResulta; // [rsp+20h] [rbp-100h]
  HKEY v62; // [rsp+28h] [rbp-F8h]
  int v63; // [rsp+30h] [rbp-F0h]
  bool v64; // [rsp+40h] [rbp-E0h]
  bool v65[4]; // [rsp+A0h] [rbp-80h] BYREF
  int v66; // [rsp+A4h] [rbp-7Ch] BYREF
  bool v67; // [rsp+A8h] [rbp-78h]
  bool v68; // [rsp+A9h] [rbp-77h]
  bool v69; // [rsp+AAh] [rbp-76h]
  bool v70; // [rsp+ABh] [rbp-75h]
  bool v71; // [rsp+ACh] [rbp-74h]
  bool v72[8]; // [rsp+B0h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp-68h] BYREF
  int v74; // [rsp+C0h] [rbp-60h]
  HKEY v75; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v76; // [rsp+D0h] [rbp-50h] BYREF
  unsigned int v77; // [rsp+D8h] [rbp-48h] BYREF
  PSID pSid1; // [rsp+E0h] [rbp-40h] BYREF
  HKEY *v79; // [rsp+E8h] [rbp-38h]
  struct _GUID *v80; // [rsp+F0h] [rbp-30h]
  struct IUserToken *v81; // [rsp+F8h] [rbp-28h]
  void **v82; // [rsp+100h] [rbp-20h]
  const struct _GUID *v83; // [rsp+108h] [rbp-18h]
  unsigned __int16 v84[8]; // [rsp+110h] [rbp-10h] BYREF
  __int128 v85; // [rsp+120h] [rbp+0h]
  wchar_t v86; // [rsp+130h] [rbp+10h]
  __int128 v87; // [rsp+132h] [rbp+12h]
  _BYTE v88[30]; // [rsp+142h] [rbp+22h] BYREF
  WCHAR SubKey[48]; // [rsp+160h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+F8h]

  v7 = a4;
  v80 = a4;
  v8 = a3;
  v81 = a3;
  v83 = a5;
  v82 = a6;
  v75 = 0;
  hKey = 0;
  v76 = 0;
  v77 = 0;
  if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    *(_OWORD *)v84 = *(_OWORD *)L"Guid unavailable";
    memset(v88, 0, sizeof(v88));
    v86 = aGuidUnavailabl[16];
    v85 = *(_OWORD *)L"vailable";
    v87 = 0;
    wStringFromGUID2(a4, v84, 40);
    LODWORD(phkResult) = 3;
    ComTraceMessage(
      0xFFFFFFFFLL,
      "onecore\\com\\combase\\catalog\\regcat.cxx",
      "CComRegCatalog::GetProcessInfoInternal",
      552,
      phkResult,
      L"AppID %ws",
      v84);
  }
  *a6 = 0;
  v10 = a2 & 0x10000;
  v66 = a2 & 0x10000;
  if ( (a2 & 0x10000) != 0 )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this - 1) + 168LL))((char *)this - 8) )
      return 2147746132LL;
    v10 = v66;
  }
  v74 = 0;
  v12 = (HKEY *)((char *)this - 8);
  v79 = (HKEY *)((char *)this - 8);
  v13 = 0;
  if ( !v8 )
  {
    hKey = v12[3];
    goto LABEL_33;
  }
  if ( v10 )
  {
    hKey = v12[3];
  }
  else
  {
    v14 = (*((__int64 (__fastcall **)(char *, struct IUserToken *, HKEY *))*v12 + 15))((char *)this - 8, v8, &hKey);
    v15 = v14;
    if ( v14 == -2147024894 )
    {
      if ( !(*((unsigned __int8 (__fastcall **)(char *))*v12 + 21))((char *)this - 8) )
      {
        v15 = -2147221164;
        goto LABEL_14;
      }
      hKey = (HKEY)*((_QWORD *)this + 2);
      v66 = 1;
      goto LABEL_28;
    }
    if ( v14 < 0 )
      goto LABEL_14;
    if ( !hKey )
    {
      v15 = -2147418113;
      goto LABEL_14;
    }
    v10 = v66;
    v13 = 1;
    v74 = 1;
  }
  if ( !v10 )
    goto LABEL_30;
LABEL_28:
  if ( (a2 & 0x20000) != 0
    || (v17 = *(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v8,
        pSid1 = 0,
        *(_WORD *)v72 = 0,
        ((__int64 (__fastcall **)(struct IUserToken *, PSID *, bool *))v17)[5](v8, &pSid1, v72),
        !EqualSid(pSid1, gSidAnonymous)) )
  {
LABEL_30:
    v15 = (**(__int64 (__fastcall ***)(struct IUserToken *, GUID *, __int64 *))v8)(
            v8,
            &GUID_000001fc_0000_0000_cfff_123045660046,
            &v76);
    if ( v15 < 0 )
      goto LABEL_14;
  }
LABEL_33:
  if ( v76 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v76 + 96LL))(v76, 0, &v77);
    if ( v15 < 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
      v76 = 0;
      goto LABEL_16;
    }
  }
  while ( 1 )
  {
    v18 = 2147483646;
    v19 = L"AppID\\{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}";
    v20 = 45;
    v21 = SubKey;
    do
    {
      if ( !v18 )
        break;
      if ( !*v19 )
        break;
      *v21++ = *v19++;
      --v18;
      --v20;
    }
    while ( v20 );
    v22 = v21 - 1;
    if ( v20 )
      v22 = v21;
    *v22 = 0;
    v15 = v20 == 0 ? 0x8007007A : 0;
    if ( !v20 )
      goto LABEL_14;
    v23 = qword_180123960;
    v24 = v7;
    v25 = 6;
    do
    {
      Data1 = v24->Data1;
      v23 = (__int64 *)((char *)v23 + 4);
      v27 = v25;
      v24 = (struct _GUID *)((char *)v24 + 1);
      v28 = (Data1 >> 4) + 55;
      if ( (unsigned __int16)((Data1 >> 4) + 48) <= 0x39u )
        v28 = (Data1 >> 4) + 48;
      SubKey[v27 + 7] = v28;
      v29 = (Data1 & 0xF) + 55;
      if ( (unsigned __int16)((Data1 & 0xF) + 48) <= 0x39u )
        v29 = (Data1 & 0xF) + 48;
      SubKey[v27 + 8] = v29;
      v25 = *(_DWORD *)v23;
    }
    while ( *(int *)v23 >= 0 );
    v30 = *((_DWORD *)this + 2);
    v31 = 0;
    v32 = hKey;
    SubKey[15] = 45;
    SubKey[20] = 45;
    SubKey[25] = 45;
    SubKey[30] = 45;
    if ( v30 == 512 )
      v31 = Wow64SetThreadDefaultGuestMachine(*((unsigned __int16 *)this + 6));
    v15 = RegOpenKeyExW(v32, SubKey, 0, v30 | 0x20019, &v75);
    if ( v30 == 512 )
      Wow64SetThreadDefaultGuestMachine(v31);
    if ( v15 )
      break;
    v33 = v66;
    if ( !v66 )
    {
      v15 = (*((__int64 (__fastcall **)(char *, HKEY, int *))*v12 + 20))((char *)this - 8, v75, &v66);
      if ( v15 < 0 )
        goto LABEL_75;
      v33 = v66;
    }
    if ( !g_bInSCM || v33 )
      goto LABEL_66;
    v15 = (*((__int64 (__fastcall **)(char *, HKEY, int *))*v12 + 46))((char *)this - 8, v75, &v66);
    if ( v15 < 0 )
      goto LABEL_75;
    if ( !v66 )
    {
LABEL_66:
      v34 = *v12;
      v65[0] = 0;
      v35 = (*((__int64 (__fastcall **)(char *, struct IUserToken *, bool *))v34 + 29))((char *)this - 8, v8, v65);
      v15 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2AC,
          (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
          (const char *)(unsigned int)v35,
          phkResulta);
        return (unsigned int)v15;
      }
      v36 = HeapAlloc(g_hHeap, 0, 0x118u);
      if ( v36 && (pSid1 = (PSID)CComProcessInfo::CComProcessInfo(v36, *((unsigned int *)this + 6))) != 0 )
      {
        v37 = (*((__int64 (__fastcall **)(char *))*v12 + 39))((char *)this - 8);
        v38 = *v12;
        v67 = v37;
        v39 = (*((__int64 (__fastcall **)(char *))v38 + 37))((char *)this - 8);
        v40 = *v12;
        v68 = v39;
        v41 = (*((__int64 (__fastcall **)(char *))v40 + 35))((char *)this - 8);
        v42 = *v12;
        v69 = v41;
        v43 = (*((__int64 (__fastcall **)(char *))v42 + 34))((char *)this - 8);
        v44 = *v12;
        v70 = v43;
        v45 = (*((__int64 (__fastcall **)(char *))v44 + 33))((char *)this - 8);
        v46 = *v12;
        v71 = v45;
        v47 = (*((__int64 (__fastcall **)(char *))v46 + 32))((char *)this - 8);
        v48 = *v12;
        v72[0] = v47;
        v49 = (*((__int64 (__fastcall **)(char *))v48 + 31))((char *)this - 8);
        v50 = v65[0];
        v51 = (*((__int64 (__fastcall **)(char *))*v12 + 28))((char *)this - 8);
        v52 = (*((__int64 (__fastcall **)(char *))*v12 + 27))((char *)this - 8);
        v53 = (*((__int64 (__fastcall **)(HKEY *))*v12 + 26))(v12);
        v54 = (*((__int64 (__fastcall **)(HKEY *))*v12 + 25))(v12);
        v55 = v66;
        v56 = (HKEY)(*((__int64 (__fastcall **)(HKEY *, HKEY))*v79 + 30))(v79, hKey);
        v64 = v53;
        v8 = v81;
        v63 = v55;
        v57 = (CComProcessInfo *)pSid1;
        v15 = CComProcessInfo::FinalConstruct(
                (CComProcessInfo *)pSid1,
                v81,
                v80,
                SubKey,
                v75,
                v56,
                v63,
                v54,
                v64,
                v52,
                v51,
                v50,
                v49,
                v72[0],
                v71,
                v70,
                v69,
                v68,
                v67);
        if ( v15 < 0 )
        {
          CComProcessInfo::`scalar deleting destructor'(v57, v58);
        }
        else
        {
          (*(void (__fastcall **)(CComProcessInfo *))(*(_QWORD *)v57 + 8LL))(v57);
          v15 = (**(__int64 (__fastcall ***)(CComProcessInfo *, const struct _GUID *, void **))v57)(v57, v83, v82);
          (*(void (__fastcall **)(CComProcessInfo *))(*(_QWORD *)v57 + 16LL))(v57);
        }
        v12 = v79;
      }
      else
      {
        v15 = -2147024882;
      }
      goto LABEL_75;
    }
    if ( !(*((unsigned __int8 (__fastcall **)(char *))*v12 + 21))((char *)this - 8) )
    {
      v15 = -2147221161;
LABEL_75:
      RegCloseKey(v75);
      goto LABEL_14;
    }
    if ( v13 )
    {
      (*((void (__fastcall **)(char *, struct IUserToken *))*v12 + 16))((char *)this - 8, v8);
      v13 = 0;
      v74 = 0;
    }
    hKey = (HKEY)*((_QWORD *)this + 2);
    RegCloseKey(v75);
    v7 = v80;
  }
  if ( v15 == 2 )
  {
    v15 = -2147221164;
  }
  else if ( v15 > 0 )
  {
    v15 = (unsigned __int16)v15 | 0x80070000;
  }
  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
  {
    v59 = CGuidStr::CGuidStr((CGuidStr *)v84, v80);
    ComTraceMessageT<unsigned short *,unsigned short *,long>(
      (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
      (unsigned int)"CComRegCatalog::GetProcessInfoInternal",
      738,
      0,
      (__int64)L"APPID:%wsValue:%ws %!HRESULT!",
      v59,
      SubKey,
      v15);
  }
LABEL_14:
  if ( v76 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v76 + 104LL))(v76, v77);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
  }
LABEL_16:
  if ( v74 )
    (*((void (__fastcall **)(HKEY *, struct IUserToken *))*v12 + 16))(v12, v8);
  if ( gfEnableTracing )
  {
    if ( (unsigned __int8)IsWppLevelEnabled(3) )
    {
      LODWORD(v62) = v15;
      ComTraceMessageT<long>(
        (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
        (unsigned int)"CComRegCatalog::GetProcessInfoInternal",
        750,
        v16,
        (__int64)L"Returning %!HRESULT!",
        v62);
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180057360  push    rbp
0x180057362  push    rbx
0x180057363  push    rsi
0x180057364  push    rdi
0x180057365  push    r12
0x180057367  push    r13
0x180057369  push    r14
0x18005736b  push    r15
0x18005736d  lea     rbp, [rsp-0B8h]
0x180057375  sub     rsp, 1D8h
0x18005737c  mov     rax, cs:__security_cookie
0x180057383  xor     rax, rsp
0x180057386  mov     [rbp+0F0h+var_50], rax
0x18005738d  mov     rax, [rbp+0F0h+arg_20]
0x180057394  mov     r15d, edx
0x180057397  mov     rbx, [rbp+0F0h+arg_28]
0x18005739e  xor     edx, edx
0x1800573a0  cmp     cs:?gfEnableTracing@@3HA, edx; int gfEnableTracing
0x1800573a6  mov     r13, r9
0x1800573a9  mov     [rbp+0F0h+var_120], r9
0x1800573ad  mov     rsi, r8
0x1800573b0  mov     [rbp+0F0h+var_118], r8
0x1800573b4  mov     r14, rcx
0x1800573b7  mov     [rbp+0F0h+var_108], rax
0x1800573bb  mov     [rbp+0F0h+var_110], rbx
0x1800573bf  mov     [rbp+0F0h+var_148], rdx
0x1800573c3  mov     [rbp+0F0h+hKey], rdx
0x1800573c7  mov     [rbp+0F0h+var_140], rdx
0x1800573cb  mov     [rbp+0F0h+var_138], edx
0x1800573ce  jz      loc_18005745C
0x1800573d4  mov     rax, cs:WPP_GLOBAL_Control
0x1800573db  test    byte ptr [rax+1Ch], 8
0x1800573df  jz      short loc_18005745C
0x1800573e1  movups  xmm0, xmmword ptr cs:aGuidUnavailabl; "Guid unavailable"
0x1800573e8  movzx   eax, word ptr cs:aGuidUnavailabl+20h; ""
0x1800573ef  lea     r8d, [rdx+28h]; int
0x1800573f3  movups  xmm1, xmmword ptr cs:aGuidUnavailabl+10h; "vailable"
0x1800573fa  lea     rdx, [rbp+0F0h+var_100]; unsigned __int16 *
0x1800573fe  mov     rcx, r9; struct _GUID *
0x180057401  movaps  xmmword ptr [rbp+0F0h+var_100], xmm0
0x180057405  xorps   xmm0, xmm0
0x180057408  movups  xmmword ptr [rbp+0F0h+var_CE], xmm0
0x18005740c  mov     [rbp+0F0h+var_E0], ax
0x180057410  movups  xmmword ptr [rbp+0F0h+var_CE+0Eh], xmm0
0x180057414  movaps  [rbp+0F0h+var_F0], xmm1
0x180057418  movups  [rbp+0F0h+var_DE], xmm0
0x18005741c  call    ?wStringFromGUID2@@YAHAEBU_GUID@@PEAGH@Z; wStringFromGUID2(_GUID const &,ushort *,int)
0x180057421  lea     rdx, [rbp+0F0h+var_100]
0x180057425  mov     r9d, 228h
0x18005742b  mov     qword ptr [rsp+210h+var_1E0], rdx
0x180057430  lea     rax, aAppidWs; "AppID %ws"
0x180057437  mov     [rsp+210h+var_1E8], rax
0x18005743c  lea     rdx, aOnecoreComComb_50; "onecore\\com\\combase\\catalog\\regcat."...
0x180057443  lea     r8, aCcomregcatalog; "CComRegCatalog::GetProcessInfoInternal"
0x18005744a  mov     dword ptr [rsp+210h+phkResult], 3
0x180057452  or      ecx, 0FFFFFFFFh
0x180057455  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18005745a  xor     edx, edx
0x18005745c  mov     ecx, r15d
0x18005745f  mov     [rbx], rdx
0x180057462  and     ecx, 10000h
0x180057468  mov     [rbp+0F0h+var_16C], ecx
0x18005746b  jz      short loc_180057493
0x18005746d  lea     rcx, [r14-8]
0x180057471  mov     rax, [rcx]
0x180057474  mov     rax, [rax+0A8h]
0x18005747b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057480  xor     edx, edx
0x180057482  test    al, al
0x180057484  jnz     short loc_180057490
0x180057486  mov     eax, 80040154h
0x18005748b  jmp     loc_180057590
0x180057490  mov     ecx, [rbp+0F0h+var_16C]
0x180057493  mov     [rbp+0F0h+var_150], edx
0x180057496  lea     rdi, [r14-8]
0x18005749a  mov     [rbp+0F0h+var_128], rdi
0x18005749e  mov     r12d, edx
0x1800574a1  test    rsi, rsi
0x1800574a4  jz      loc_180057658
0x1800574aa  test    ecx, ecx
0x1800574ac  jnz     loc_1800575DD
0x1800574b2  mov     rax, [rdi]
0x1800574b5  lea     r8, [rbp+0F0h+hKey]
0x1800574b9  mov     rdx, rsi
0x1800574bc  mov     rcx, rdi
0x1800574bf  mov     rax, [rax+78h]
0x1800574c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800574c8  mov     ebx, eax
0x1800574ca  cmp     eax, 80070002h
0x1800574cf  jnz     loc_1800575B4
0x1800574d5  mov     rax, [rdi]
0x1800574d8  mov     rcx, rdi
0x1800574db  mov     rax, [rax+0A8h]
0x1800574e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800574e7  test    al, al
0x1800574e9  jz      short loc_1800574FF
0x1800574eb  mov     rax, [r14+10h]
0x1800574ef  mov     [rbp+0F0h+hKey], rax
0x1800574f3  mov     [rbp+0F0h+var_16C], 1
0x1800574fa  jmp     loc_1800575E9
0x1800574ff  mov     ebx, 80040154h
0x180057504  xor     r15d, r15d
0x180057507  mov     rcx, [rbp+0F0h+var_140]
0x18005750b  test    rcx, rcx
0x18005750e  jz      short loc_18005752F
0x180057510  mov     rax, [rcx]
0x180057513  mov     edx, [rbp+0F0h+var_138]
0x180057516  mov     rax, [rax+68h]
0x18005751a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005751f  mov     rcx, [rbp+0F0h+var_140]
0x180057523  mov     rax, [rcx]
0x180057526  mov     rax, [rax+10h]
0x18005752a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005752f  cmp     [rbp+0F0h+var_150], r15d
0x180057533  jz      short loc_18005754A
0x180057535  mov     rax, [rdi]
0x180057538  mov     rdx, rsi
0x18005753b  mov     rcx, rdi
0x18005753e  mov     rax, [rax+80h]
0x180057545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005754a  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180057551  jz      short loc_18005758E
0x180057553  mov     r9d, 3
0x180057559  mov     ecx, r9d
0x18005755c  call    IsWppLevelEnabled
0x180057561  test    al, al
0x180057563  jz      short loc_18005758E
0x180057565  lea     rax, aReturningHresu; "Returning %!HRESULT!"
0x18005756c  mov     dword ptr [rsp+210h+var_1E8], ebx
0x180057570  mov     r8d, 2EEh
0x180057576  mov     [rsp+210h+phkResult], rax
0x18005757b  lea     rdx, aCcomregcatalog; "CComRegCatalog::GetProcessInfoInternal"
0x180057582  lea     rcx, aOnecoreComComb_50; "onecore\\com\\combase\\catalog\\regcat."...
0x180057589  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18005758e  mov     eax, ebx
0x180057590  mov     rcx, [rbp+0F0h+var_50]
0x180057597  xor     rcx, rsp; StackCookie
0x18005759a  call    __security_check_cookie
0x18005759f  add     rsp, 1D8h
0x1800575a6  pop     r15
0x1800575a8  pop     r14
0x1800575aa  pop     r13
0x1800575ac  pop     r12
0x1800575ae  pop     rdi
0x1800575af  pop     rsi
0x1800575b0  pop     rbx
0x1800575b1  pop     rbp
0x1800575b2  retn
0x1800575b4  xor     edx, edx
0x1800575b6  test    eax, eax
0x1800575b8  js      loc_180057504
0x1800575be  cmp     [rbp+0F0h+hKey], rdx
0x1800575c2  jnz     short loc_1800575CE
0x1800575c4  mov     ebx, 8000FFFFh
0x1800575c9  jmp     loc_180057504
0x1800575ce  mov     ecx, [rbp+0F0h+var_16C]
0x1800575d1  mov     r12d, 1
0x1800575d7  mov     [rbp+0F0h+var_150], r12d
0x1800575db  jmp     short loc_1800575E5
0x1800575dd  mov     rax, [rdi+18h]
0x1800575e1  mov     [rbp+0F0h+hKey], rax
0x1800575e5  test    ecx, ecx
0x1800575e7  jz      short loc_180057630
0x1800575e9  bt      r15d, 11h
0x1800575ee  jb      short loc_180057630
0x1800575f0  mov     rax, [rsi]
0x1800575f3  lea     r8, [rbp+0F0h+var_160]
0x1800575f7  xor     r15d, r15d
0x1800575fa  lea     rdx, [rbp+0F0h+pSid1]
0x1800575fe  mov     rcx, rsi
0x180057601  mov     [rbp+0F0h+pSid1], r15
0x180057605  mov     word ptr [rbp+0F0h+var_160], r15w
0x18005760a  mov     rax, [rax+28h]
0x18005760e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057613  mov     rdx, cs:?gSidAnonymous@@3PEAXEA; pSid2
0x18005761a  mov     rcx, [rbp+0F0h+pSid1]; pSid1
0x18005761e  call    cs:__imp_EqualSid
0x180057625  nop     dword ptr [rax+rax+00h]
0x18005762a  test    eax, eax
0x18005762c  jnz     short loc_180057663
0x18005762e  jmp     short loc_180057633
0x180057630  xor     r15d, r15d
0x180057633  mov     rax, [rsi]
0x180057636  lea     r8, [rbp+0F0h+var_140]
0x18005763a  lea     rdx, _GUID_000001fc_0000_0000_cfff_123045660046
0x180057641  mov     rcx, rsi
0x180057644  mov     rax, [rax]
0x180057647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005764c  mov     ebx, eax
0x18005764e  test    eax, eax
0x180057650  js      loc_180057507
0x180057656  jmp     short loc_180057663
0x180057658  mov     rax, [rdi+18h]
0x18005765c  xor     r15d, r15d
0x18005765f  mov     [rbp+0F0h+hKey], rax
0x180057663  mov     rcx, [rbp+0F0h+var_140]
0x180057667  test    rcx, rcx
0x18005766a  jz      short loc_18005769D
0x18005766c  mov     rax, [rcx]
0x18005766f  lea     r8, [rbp+0F0h+var_138]
0x180057673  xor     edx, edx
0x180057675  mov     rax, [rax+60h]
0x180057679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005767e  mov     ebx, eax
0x180057680  test    eax, eax
0x180057682  jns     short loc_18005769D
0x180057684  mov     rcx, [rbp+0F0h+var_140]
0x180057688  mov     rax, [rcx]
0x18005768b  mov     rax, [rax+10h]
0x18005768f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057694  mov     [rbp+0F0h+var_140], r15
0x180057698  jmp     loc_18005752F
0x18005769d  mov     r11d, 2Dh ; '-'
0x1800576a3  mov     ecx, 7FFFFFFEh
0x1800576a8  lea     r8, aAppidXxxxxxxxX; "AppID\\{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxx"...
0x1800576af  mov     edx, r11d
0x1800576b2  lea     rax, [rbp+0F0h+SubKey]
0x1800576b6  test    rcx, rcx
0x1800576b9  jz      short loc_1800576DA
0x1800576bb  movzx   r9d, word ptr [r8]
0x1800576bf  test    r9w, r9w
0x1800576c3  jz      short loc_1800576DA
0x1800576c5  mov     [rax], r9w
0x1800576c9  add     r8, 2
0x1800576cd  add     rax, 2
0x1800576d1  dec     rcx
0x1800576d4  sub     rdx, 1
0x1800576d8  jnz     short loc_1800576B6
0x1800576da  test    rdx, rdx
0x1800576dd  lea     rcx, [rax-2]
0x1800576e1  cmovnz  rcx, rax
0x1800576e5  mov     rax, rdx
0x1800576e8  neg     rax
0x1800576eb  sbb     ebx, ebx
0x1800576ed  not     ebx
0x1800576ef  mov     [rcx], r15w
0x1800576f3  and     ebx, 8007007Ah
0x1800576f9  test    rdx, rdx
0x1800576fc  jz      loc_180057507
0x180057702  lea     r9, qword_180123960
0x180057709  mov     r10, r13
0x18005770c  mov     eax, 6
0x180057711  mov     dl, [r10]
0x180057714  lea     r9, [r9+4]
0x180057718  mov     r8d, eax
0x18005771b  inc     r10
0x18005771e  mov     al, dl
0x180057720  shr     al, 4
0x180057723  movzx   ecx, al
0x180057726  add     cx, 30h ; '0'
0x18005772a  cmp     cx, 39h ; '9'
0x18005772e  lea     eax, [rcx+7]
0x180057731  cmovbe  ax, cx
0x180057735  and     dl, 0Fh
0x180057738  mov     [rbp+r8*2+0F0h+var_A2], ax
0x18005773e  movzx   ecx, dl
0x180057741  add     cx, 30h ; '0'
0x180057745  cmp     cx, 39h ; '9'
0x180057749  lea     eax, [rcx+7]
0x18005774c  cmovbe  ax, cx
0x180057750  mov     [rbp+r8*2+0F0h+var_A0], ax
0x180057756  mov     eax, [r9]
0x180057759  test    eax, eax
0x18005775b  jns     short loc_180057711
0x18005775d  mov     r15d, [r14+8]
0x180057761  xor     r13d, r13d
0x180057764  mov     rbx, [rbp+0F0h+hKey]
0x180057768  mov     [rbp+0F0h+var_92], r11w
0x18005776d  mov     [rbp+0F0h+var_88], r11w
0x180057772  mov     [rbp+0F0h+var_7E], r11w
0x180057777  mov     [rbp+0F0h+var_74], r11w
0x18005777c  cmp     r15d, 200h
0x180057783  jnz     short loc_18005779A
0x180057785  movzx   ecx, word ptr [r14+0Ch]
0x18005778a  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x180057791  nop     dword ptr [rax+rax+00h]
0x180057796  movzx   r13d, ax
0x18005779a  mov     r9d, r15d
0x18005779d  lea     rax, [rbp+0F0h+var_148]
0x1800577a1  or      r9d, 20019h; samDesired
0x1800577a8  mov     [rsp+210h+phkResult], rax; int
0x1800577ad  xor     r8d, r8d; ulOptions
0x1800577b0  lea     rdx, [rbp+0F0h+SubKey]; lpSubKey
0x1800577b4  mov     rcx, rbx; hKey
0x1800577b7  call    cs:__imp_RegOpenKeyExW
0x1800577be  nop     dword ptr [rax+rax+00h]
0x1800577c3  mov     ebx, eax
0x1800577c5  cmp     r15d, 200h
0x1800577cc  jnz     short loc_1800577DE
0x1800577ce  movzx   ecx, r13w
0x1800577d2  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x1800577d9  nop     dword ptr [rax+rax+00h]
0x1800577de  xor     r15d, r15d
0x1800577e1  test    ebx, ebx
0x1800577e3  jnz     loc_180057B22
0x1800577e9  mov     eax, [rbp+0F0h+var_16C]
0x1800577ec  test    eax, eax
0x1800577ee  jnz     short loc_180057817
0x1800577f0  mov     rax, [rdi]
0x1800577f3  lea     r8, [rbp+0F0h+var_16C]
  ... truncated ...
```
