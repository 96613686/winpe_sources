# CComRegCatalog::GetProcessInfoInternal(ulong,IUserToken *,_GUID const &,_GUID const &,void * *)

- ea: `0x18004b560`
- end: `0x18004bd82`
- name: `?GetProcessInfoInternal@CComRegCatalog@@UEAAJKPEAUIUserToken@@AEBU_GUID@@1PEAPEAX@Z`
- size: `2082`
- prototype: `__int64 __fastcall(CComRegCatalog *this, int, struct IUserToken *, struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800cc720`

## callees

- `0x180009470`
- `0x18000e4a8`
- `0x180016160`
- `0x180018344`
- `0x18002ba28`
- `0x180034540`
- `0x18004b560`
- `0x180054b7c`
- `0x180073bd4`
- `0x18007ced0`
- `0x18007e3d4`
- `0x1800b27e0`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004baeb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004baeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ba80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bcec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ba80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bcec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b9aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b9aa`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18004b983`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18004b9bf`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18004b983`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18004b9bf`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004b81d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004b81d`

## string_xrefs

- `0x18004b63c`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18004b782`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18004bac3`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18004bd5c`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18004b643`: `CComRegCatalog::GetProcessInfoInternal`
- `0x18004b77b`: `CComRegCatalog::GetProcessInfoInternal`
- `0x18004bd50`: `CComRegCatalog::GetProcessInfoInternal`

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
  int phkResult; // [rsp+20h] [rbp-100h]
  HKEY v61; // [rsp+28h] [rbp-F8h]
  int v62; // [rsp+30h] [rbp-F0h]
  bool v63; // [rsp+40h] [rbp-E0h]
  bool v64[4]; // [rsp+A0h] [rbp-80h] BYREF
  int v65; // [rsp+A4h] [rbp-7Ch] BYREF
  bool v66; // [rsp+A8h] [rbp-78h]
  bool v67; // [rsp+A9h] [rbp-77h]
  bool v68; // [rsp+AAh] [rbp-76h]
  bool v69; // [rsp+ABh] [rbp-75h]
  bool v70; // [rsp+ACh] [rbp-74h]
  bool v71[8]; // [rsp+B0h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp-68h] BYREF
  int v73; // [rsp+C0h] [rbp-60h]
  HKEY v74; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v75; // [rsp+D0h] [rbp-50h] BYREF
  unsigned int v76; // [rsp+D8h] [rbp-48h] BYREF
  PSID pSid1; // [rsp+E0h] [rbp-40h] BYREF
  HKEY *v78; // [rsp+E8h] [rbp-38h]
  struct _GUID *v79; // [rsp+F0h] [rbp-30h]
  struct IUserToken *v80; // [rsp+F8h] [rbp-28h]
  void **v81; // [rsp+100h] [rbp-20h]
  const struct _GUID *v82; // [rsp+108h] [rbp-18h]
  unsigned __int16 v83[8]; // [rsp+110h] [rbp-10h] BYREF
  __int128 v84; // [rsp+120h] [rbp+0h]
  wchar_t v85; // [rsp+130h] [rbp+10h]
  __int128 v86; // [rsp+132h] [rbp+12h]
  _BYTE v87[30]; // [rsp+142h] [rbp+22h] BYREF
  WCHAR SubKey[48]; // [rsp+160h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+F8h]

  v7 = a4;
  v79 = a4;
  v8 = a3;
  v80 = a3;
  v82 = a5;
  v81 = a6;
  v74 = 0;
  hKey = 0;
  v75 = 0;
  v76 = 0;
  if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    *(_OWORD *)v83 = *(_OWORD *)L"Guid unavailable";
    memset(v87, 0, sizeof(v87));
    v85 = aGuidUnavailabl[16];
    v84 = *(_OWORD *)L"vailable";
    v86 = 0;
    wStringFromGUID2(a4, v83, 40);
    v61 = (HKEY)L"AppID %ws";
    ComTraceMessage(
      0xFFFFFFFFLL,
      "onecore\\com\\combase\\catalog\\regcat.cxx",
      "CComRegCatalog::GetProcessInfoInternal",
      552);
  }
  *a6 = 0;
  v10 = a2 & 0x10000;
  v65 = a2 & 0x10000;
  if ( (a2 & 0x10000) != 0 )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this - 1) + 168LL))((char *)this - 8) )
      return 2147746132LL;
    v10 = v65;
  }
  v73 = 0;
  v12 = (HKEY *)((char *)this - 8);
  v78 = (HKEY *)((char *)this - 8);
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
      v65 = 1;
      goto LABEL_28;
    }
    if ( v14 < 0 )
      goto LABEL_14;
    if ( !hKey )
    {
      v15 = -2147418113;
      goto LABEL_14;
    }
    v10 = v65;
    v13 = 1;
    v73 = 1;
  }
  if ( !v10 )
    goto LABEL_30;
LABEL_28:
  if ( (a2 & 0x20000) != 0
    || (v17 = *(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v8,
        pSid1 = 0,
        *(_WORD *)v71 = 0,
        ((__int64 (__fastcall **)(struct IUserToken *, PSID *, bool *))v17)[5](v8, &pSid1, v71),
        !EqualSid(pSid1, gSidAnonymous)) )
  {
LABEL_30:
    v15 = (**(__int64 (__fastcall ***)(struct IUserToken *, GUID *, __int64 *))v8)(
            v8,
            &GUID_000001fc_0000_0000_cfff_123045660046,
            &v75);
    if ( v15 < 0 )
      goto LABEL_14;
  }
LABEL_33:
  if ( v75 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v75 + 96LL))(v75, 0, &v76);
    if ( v15 < 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
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
    v23 = qword_18011A860;
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
    v15 = RegOpenKeyExW(v32, SubKey, 0, v30 | 0x20019, &v74);
    if ( v30 == 512 )
      Wow64SetThreadDefaultGuestMachine(v31);
    if ( v15 )
      break;
    v33 = v65;
    if ( !v65 )
    {
      v15 = (*((__int64 (__fastcall **)(char *, HKEY, int *))*v12 + 20))((char *)this - 8, v74, &v65);
      if ( v15 < 0 )
        goto LABEL_75;
      v33 = v65;
    }
    if ( !g_bInSCM || v33 )
      goto LABEL_66;
    v15 = (*((__int64 (__fastcall **)(char *, HKEY, int *))*v12 + 46))((char *)this - 8, v74, &v65);
    if ( v15 < 0 )
      goto LABEL_75;
    if ( !v65 )
    {
LABEL_66:
      v34 = *v12;
      v64[0] = 0;
      v35 = (*((__int64 (__fastcall **)(char *, struct IUserToken *, bool *))v34 + 29))((char *)this - 8, v8, v64);
      v15 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2AC,
          (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
          (const char *)(unsigned int)v35,
          phkResult);
        return (unsigned int)v15;
      }
      v36 = HeapAlloc(g_hHeap, 0, 0x118u);
      if ( v36 && (pSid1 = (PSID)CComProcessInfo::CComProcessInfo(v36, *((unsigned int *)this + 6))) != 0 )
      {
        v37 = (*((__int64 (__fastcall **)(char *))*v12 + 39))((char *)this - 8);
        v38 = *v12;
        v66 = v37;
        v39 = (*((__int64 (__fastcall **)(char *))v38 + 37))((char *)this - 8);
        v40 = *v12;
        v67 = v39;
        v41 = (*((__int64 (__fastcall **)(char *))v40 + 35))((char *)this - 8);
        v42 = *v12;
        v68 = v41;
        v43 = (*((__int64 (__fastcall **)(char *))v42 + 34))((char *)this - 8);
        v44 = *v12;
        v69 = v43;
        v45 = (*((__int64 (__fastcall **)(char *))v44 + 33))((char *)this - 8);
        v46 = *v12;
        v70 = v45;
        v47 = (*((__int64 (__fastcall **)(char *))v46 + 32))((char *)this - 8);
        v48 = *v12;
        v71[0] = v47;
        v49 = (*((__int64 (__fastcall **)(char *))v48 + 31))((char *)this - 8);
        v50 = v64[0];
        v51 = (*((__int64 (__fastcall **)(char *))*v12 + 28))((char *)this - 8);
        v52 = (*((__int64 (__fastcall **)(char *))*v12 + 27))((char *)this - 8);
        v53 = (*((__int64 (__fastcall **)(HKEY *))*v12 + 26))(v12);
        v54 = (*((__int64 (__fastcall **)(HKEY *))*v12 + 25))(v12);
        v55 = v65;
        v56 = (HKEY)(*((__int64 (__fastcall **)(HKEY *, HKEY))*v78 + 30))(v78, hKey);
        v63 = v53;
        v8 = v80;
        v62 = v55;
        v57 = (CComProcessInfo *)pSid1;
        v15 = CComProcessInfo::FinalConstruct(
                (CComProcessInfo *)pSid1,
                v80,
                v79,
                SubKey,
                v74,
                v56,
                v62,
                v54,
                v63,
                v52,
                v51,
                v50,
                v49,
                v71[0],
                v70,
                v69,
                v68,
                v67,
                v66);
        if ( v15 < 0 )
        {
          CComProcessInfo::`scalar deleting destructor'(v57, v58);
        }
        else
        {
          (*(void (__fastcall **)(CComProcessInfo *))(*(_QWORD *)v57 + 8LL))(v57);
          v15 = (**(__int64 (__fastcall ***)(CComProcessInfo *, const struct _GUID *, void **))v57)(v57, v82, v81);
          (*(void (__fastcall **)(CComProcessInfo *))(*(_QWORD *)v57 + 16LL))(v57);
        }
        v12 = v78;
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
      RegCloseKey(v74);
      goto LABEL_14;
    }
    if ( v13 )
    {
      (*((void (__fastcall **)(char *, struct IUserToken *))*v12 + 16))((char *)this - 8, v8);
      v13 = 0;
      v73 = 0;
    }
    hKey = (HKEY)*((_QWORD *)this + 2);
    RegCloseKey(v74);
    v7 = v79;
  }
  if ( v15 == 2 )
  {
    v15 = -2147221164;
  }
  else if ( v15 > 0 )
  {
    v15 = (unsigned __int16)v15 | 0x80070000;
  }
  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
  {
    v59 = CGuidStr::CGuidStr((CGuidStr *)v83, v79);
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
  if ( v75 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v75 + 104LL))(v75, v76);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
  }
LABEL_16:
  if ( v73 )
    (*((void (__fastcall **)(HKEY *, struct IUserToken *))*v12 + 16))(v12, v8);
  if ( gfEnableTracing )
  {
    if ( (unsigned __int8)IsWppLevelEnabled(3) )
    {
      LODWORD(v61) = v15;
      ComTraceMessageT<long>(
        (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
        (unsigned int)"CComRegCatalog::GetProcessInfoInternal",
        750,
        v16,
        (__int64)L"Returning %!HRESULT!",
        v61);
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18004b560  push    rbp
0x18004b562  push    rbx
0x18004b563  push    rsi
0x18004b564  push    rdi
0x18004b565  push    r12
0x18004b567  push    r13
0x18004b569  push    r14
0x18004b56b  push    r15
0x18004b56d  lea     rbp, [rsp-0B8h]
0x18004b575  sub     rsp, 1D8h
0x18004b57c  mov     rax, cs:__security_cookie
0x18004b583  xor     rax, rsp
0x18004b586  mov     [rbp+0F0h+var_50], rax
0x18004b58d  mov     rax, [rbp+0F0h+arg_20]
0x18004b594  mov     r15d, edx
0x18004b597  mov     rbx, [rbp+0F0h+arg_28]
0x18004b59e  xor     edx, edx
0x18004b5a0  cmp     cs:?gfEnableTracing@@3HA, edx; int gfEnableTracing
0x18004b5a6  mov     r13, r9
0x18004b5a9  mov     [rbp+0F0h+var_120], r9
0x18004b5ad  mov     rsi, r8
0x18004b5b0  mov     [rbp+0F0h+var_118], r8
0x18004b5b4  mov     r14, rcx
0x18004b5b7  mov     [rbp+0F0h+var_108], rax
0x18004b5bb  mov     [rbp+0F0h+var_110], rbx
0x18004b5bf  mov     [rbp+0F0h+var_148], rdx
0x18004b5c3  mov     [rbp+0F0h+hKey], rdx
0x18004b5c7  mov     [rbp+0F0h+var_140], rdx
0x18004b5cb  mov     [rbp+0F0h+var_138], edx
0x18004b5ce  jz      loc_18004B65C
0x18004b5d4  mov     rax, cs:WPP_GLOBAL_Control
0x18004b5db  test    byte ptr [rax+1Ch], 8
0x18004b5df  jz      short loc_18004B65C
0x18004b5e1  movups  xmm0, xmmword ptr cs:aGuidUnavailabl; "Guid unavailable"
0x18004b5e8  movzx   eax, word ptr cs:aGuidUnavailabl+20h; ""
0x18004b5ef  lea     r8d, [rdx+28h]; int
0x18004b5f3  movups  xmm1, xmmword ptr cs:aGuidUnavailabl+10h; "vailable"
0x18004b5fa  lea     rdx, [rbp+0F0h+var_100]; unsigned __int16 *
0x18004b5fe  mov     rcx, r9; struct _GUID *
0x18004b601  movaps  xmmword ptr [rbp+0F0h+var_100], xmm0
0x18004b605  xorps   xmm0, xmm0
0x18004b608  movups  xmmword ptr [rbp+0F0h+var_CE], xmm0
0x18004b60c  mov     [rbp+0F0h+var_E0], ax
0x18004b610  movups  xmmword ptr [rbp+0F0h+var_CE+0Eh], xmm0
0x18004b614  movaps  [rbp+0F0h+var_F0], xmm1
0x18004b618  movups  [rbp+0F0h+var_DE], xmm0
0x18004b61c  call    ?wStringFromGUID2@@YAHAEBU_GUID@@PEAGH@Z; wStringFromGUID2(_GUID const &,ushort *,int)
0x18004b621  lea     rdx, [rbp+0F0h+var_100]
0x18004b625  mov     r9d, 228h
0x18004b62b  mov     qword ptr [rsp+210h+var_1E0], rdx
0x18004b630  lea     rax, aAppidWs; "AppID %ws"
0x18004b637  mov     [rsp+210h+var_1E8], rax
0x18004b63c  lea     rdx, aOnecoreComComb_50; "onecore\\com\\combase\\catalog\\regcat."...
0x18004b643  lea     r8, aCcomregcatalog; "CComRegCatalog::GetProcessInfoInternal"
0x18004b64a  mov     dword ptr [rsp+210h+phkResult], 3
0x18004b652  or      ecx, 0FFFFFFFFh
0x18004b655  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18004b65a  xor     edx, edx
0x18004b65c  mov     ecx, r15d
0x18004b65f  mov     [rbx], rdx
0x18004b662  and     ecx, 10000h
0x18004b668  mov     [rbp+0F0h+var_16C], ecx
0x18004b66b  jz      short loc_18004B693
0x18004b66d  lea     rcx, [r14-8]
0x18004b671  mov     rax, [rcx]
0x18004b674  mov     rax, [rax+0A8h]
0x18004b67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b680  xor     edx, edx
0x18004b682  test    al, al
0x18004b684  jnz     short loc_18004B690
0x18004b686  mov     eax, 80040154h
0x18004b68b  jmp     loc_18004B790
0x18004b690  mov     ecx, [rbp+0F0h+var_16C]
0x18004b693  mov     [rbp+0F0h+var_150], edx
0x18004b696  lea     rdi, [r14-8]
0x18004b69a  mov     [rbp+0F0h+var_128], rdi
0x18004b69e  mov     r12d, edx
0x18004b6a1  test    rsi, rsi
0x18004b6a4  jz      loc_18004B851
0x18004b6aa  test    ecx, ecx
0x18004b6ac  jnz     loc_18004B7DC
0x18004b6b2  mov     rax, [rdi]
0x18004b6b5  lea     r8, [rbp+0F0h+hKey]
0x18004b6b9  mov     rdx, rsi
0x18004b6bc  mov     rcx, rdi
0x18004b6bf  mov     rax, [rax+78h]
0x18004b6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b6c8  mov     ebx, eax
0x18004b6ca  cmp     eax, 80070002h
0x18004b6cf  jnz     loc_18004B7B3
0x18004b6d5  mov     rax, [rdi]
0x18004b6d8  mov     rcx, rdi
0x18004b6db  mov     rax, [rax+0A8h]
0x18004b6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b6e7  test    al, al
0x18004b6e9  jz      short loc_18004B6FF
0x18004b6eb  mov     rax, [r14+10h]
0x18004b6ef  mov     [rbp+0F0h+hKey], rax
0x18004b6f3  mov     [rbp+0F0h+var_16C], 1
0x18004b6fa  jmp     loc_18004B7E8
0x18004b6ff  mov     ebx, 80040154h
0x18004b704  xor     r15d, r15d
0x18004b707  mov     rcx, [rbp+0F0h+var_140]
0x18004b70b  test    rcx, rcx
0x18004b70e  jz      short loc_18004B72F
0x18004b710  mov     rax, [rcx]
0x18004b713  mov     edx, [rbp+0F0h+var_138]
0x18004b716  mov     rax, [rax+68h]
0x18004b71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b71f  mov     rcx, [rbp+0F0h+var_140]
0x18004b723  mov     rax, [rcx]
0x18004b726  mov     rax, [rax+10h]
0x18004b72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b72f  cmp     [rbp+0F0h+var_150], r15d
0x18004b733  jz      short loc_18004B74A
0x18004b735  mov     rax, [rdi]
0x18004b738  mov     rdx, rsi
0x18004b73b  mov     rcx, rdi
0x18004b73e  mov     rax, [rax+80h]
0x18004b745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b74a  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18004b751  jz      short loc_18004B78E
0x18004b753  mov     r9d, 3
0x18004b759  mov     ecx, r9d
0x18004b75c  call    IsWppLevelEnabled
0x18004b761  test    al, al
0x18004b763  jz      short loc_18004B78E
0x18004b765  lea     rax, aReturningHresu; "Returning %!HRESULT!"
0x18004b76c  mov     dword ptr [rsp+210h+var_1E8], ebx
0x18004b770  mov     r8d, 2EEh
0x18004b776  mov     [rsp+210h+phkResult], rax
0x18004b77b  lea     rdx, aCcomregcatalog; "CComRegCatalog::GetProcessInfoInternal"
0x18004b782  lea     rcx, aOnecoreComComb_50; "onecore\\com\\combase\\catalog\\regcat."...
0x18004b789  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18004b78e  mov     eax, ebx
0x18004b790  mov     rcx, [rbp+0F0h+var_50]
0x18004b797  xor     rcx, rsp; StackCookie
0x18004b79a  call    __security_check_cookie
0x18004b79f  add     rsp, 1D8h
0x18004b7a6  pop     r15
0x18004b7a8  pop     r14
0x18004b7aa  pop     r13
0x18004b7ac  pop     r12
0x18004b7ae  pop     rdi
0x18004b7af  pop     rsi
0x18004b7b0  pop     rbx
0x18004b7b1  pop     rbp
0x18004b7b2  retn
0x18004b7b3  xor     edx, edx
0x18004b7b5  test    eax, eax
0x18004b7b7  js      loc_18004B704
0x18004b7bd  cmp     [rbp+0F0h+hKey], rdx
0x18004b7c1  jnz     short loc_18004B7CD
0x18004b7c3  mov     ebx, 8000FFFFh
0x18004b7c8  jmp     loc_18004B704
0x18004b7cd  mov     ecx, [rbp+0F0h+var_16C]
0x18004b7d0  mov     r12d, 1
0x18004b7d6  mov     [rbp+0F0h+var_150], r12d
0x18004b7da  jmp     short loc_18004B7E4
0x18004b7dc  mov     rax, [rdi+18h]
0x18004b7e0  mov     [rbp+0F0h+hKey], rax
0x18004b7e4  test    ecx, ecx
0x18004b7e6  jz      short loc_18004B829
0x18004b7e8  bt      r15d, 11h
0x18004b7ed  jb      short loc_18004B829
0x18004b7ef  mov     rax, [rsi]
0x18004b7f2  lea     r8, [rbp+0F0h+var_160]
0x18004b7f6  xor     r15d, r15d
0x18004b7f9  lea     rdx, [rbp+0F0h+pSid1]
0x18004b7fd  mov     rcx, rsi
0x18004b800  mov     [rbp+0F0h+pSid1], r15
0x18004b804  mov     word ptr [rbp+0F0h+var_160], r15w
0x18004b809  mov     rax, [rax+28h]
0x18004b80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b812  mov     rdx, cs:?gSidAnonymous@@3PEAXEA; pSid2
0x18004b819  mov     rcx, [rbp+0F0h+pSid1]; pSid1
0x18004b81d  call    cs:__imp_EqualSid
0x18004b823  test    eax, eax
0x18004b825  jnz     short loc_18004B85C
0x18004b827  jmp     short loc_18004B82C
0x18004b829  xor     r15d, r15d
0x18004b82c  mov     rax, [rsi]
0x18004b82f  lea     r8, [rbp+0F0h+var_140]
0x18004b833  lea     rdx, _GUID_000001fc_0000_0000_cfff_123045660046
0x18004b83a  mov     rcx, rsi
0x18004b83d  mov     rax, [rax]
0x18004b840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b845  mov     ebx, eax
0x18004b847  test    eax, eax
0x18004b849  js      loc_18004B707
0x18004b84f  jmp     short loc_18004B85C
0x18004b851  mov     rax, [rdi+18h]
0x18004b855  xor     r15d, r15d
0x18004b858  mov     [rbp+0F0h+hKey], rax
0x18004b85c  mov     rcx, [rbp+0F0h+var_140]
0x18004b860  test    rcx, rcx
0x18004b863  jz      short loc_18004B896
0x18004b865  mov     rax, [rcx]
0x18004b868  lea     r8, [rbp+0F0h+var_138]
0x18004b86c  xor     edx, edx
0x18004b86e  mov     rax, [rax+60h]
0x18004b872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b877  mov     ebx, eax
0x18004b879  test    eax, eax
0x18004b87b  jns     short loc_18004B896
0x18004b87d  mov     rcx, [rbp+0F0h+var_140]
0x18004b881  mov     rax, [rcx]
0x18004b884  mov     rax, [rax+10h]
0x18004b888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b88d  mov     [rbp+0F0h+var_140], r15
0x18004b891  jmp     loc_18004B72F
0x18004b896  mov     r11d, 2Dh ; '-'
0x18004b89c  mov     ecx, 7FFFFFFEh
0x18004b8a1  lea     r8, aAppidXxxxxxxxX; "AppID\\{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxx"...
0x18004b8a8  mov     edx, r11d
0x18004b8ab  lea     rax, [rbp+0F0h+SubKey]
0x18004b8af  test    rcx, rcx
0x18004b8b2  jz      short loc_18004B8D3
0x18004b8b4  movzx   r9d, word ptr [r8]
0x18004b8b8  test    r9w, r9w
0x18004b8bc  jz      short loc_18004B8D3
0x18004b8be  mov     [rax], r9w
0x18004b8c2  add     r8, 2
0x18004b8c6  add     rax, 2
0x18004b8ca  dec     rcx
0x18004b8cd  sub     rdx, 1
0x18004b8d1  jnz     short loc_18004B8AF
0x18004b8d3  test    rdx, rdx
0x18004b8d6  lea     rcx, [rax-2]
0x18004b8da  cmovnz  rcx, rax
0x18004b8de  mov     rax, rdx
0x18004b8e1  neg     rax
0x18004b8e4  sbb     ebx, ebx
0x18004b8e6  not     ebx
0x18004b8e8  mov     [rcx], r15w
0x18004b8ec  and     ebx, 8007007Ah
0x18004b8f2  test    rdx, rdx
0x18004b8f5  jz      loc_18004B707
0x18004b8fb  lea     r9, qword_18011A860
0x18004b902  mov     r10, r13
0x18004b905  mov     eax, 6
0x18004b90a  mov     dl, [r10]
0x18004b90d  lea     r9, [r9+4]
0x18004b911  mov     r8d, eax
0x18004b914  inc     r10
0x18004b917  mov     al, dl
0x18004b919  shr     al, 4
0x18004b91c  movzx   ecx, al
0x18004b91f  add     cx, 30h ; '0'
0x18004b923  cmp     cx, 39h ; '9'
0x18004b927  lea     eax, [rcx+7]
0x18004b92a  cmovbe  ax, cx
0x18004b92e  and     dl, 0Fh
0x18004b931  mov     [rbp+r8*2+0F0h+var_A2], ax
0x18004b937  movzx   ecx, dl
0x18004b93a  add     cx, 30h ; '0'
0x18004b93e  cmp     cx, 39h ; '9'
0x18004b942  lea     eax, [rcx+7]
0x18004b945  cmovbe  ax, cx
0x18004b949  mov     [rbp+r8*2+0F0h+var_A0], ax
0x18004b94f  mov     eax, [r9]
0x18004b952  test    eax, eax
0x18004b954  jns     short loc_18004B90A
0x18004b956  mov     r15d, [r14+8]
0x18004b95a  xor     r13d, r13d
0x18004b95d  mov     rbx, [rbp+0F0h+hKey]
0x18004b961  mov     [rbp+0F0h+var_92], r11w
0x18004b966  mov     [rbp+0F0h+var_88], r11w
0x18004b96b  mov     [rbp+0F0h+var_7E], r11w
0x18004b970  mov     [rbp+0F0h+var_74], r11w
0x18004b975  cmp     r15d, 200h
0x18004b97c  jnz     short loc_18004B98D
0x18004b97e  movzx   ecx, word ptr [r14+0Ch]
0x18004b983  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x18004b989  movzx   r13d, ax
0x18004b98d  mov     r9d, r15d
0x18004b990  lea     rax, [rbp+0F0h+var_148]
0x18004b994  or      r9d, 20019h; samDesired
0x18004b99b  mov     [rsp+210h+phkResult], rax; int
0x18004b9a0  xor     r8d, r8d; ulOptions
0x18004b9a3  lea     rdx, [rbp+0F0h+SubKey]; lpSubKey
0x18004b9a7  mov     rcx, rbx; hKey
0x18004b9aa  call    cs:__imp_RegOpenKeyExW
0x18004b9b0  mov     ebx, eax
0x18004b9b2  cmp     r15d, 200h
0x18004b9b9  jnz     short loc_18004B9C5
0x18004b9bb  movzx   ecx, r13w
0x18004b9bf  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x18004b9c5  xor     r15d, r15d
0x18004b9c8  test    ebx, ebx
0x18004b9ca  jnz     loc_18004BCF7
0x18004b9d0  mov     eax, [rbp+0F0h+var_16C]
0x18004b9d3  test    eax, eax
0x18004b9d5  jnz     short loc_18004B9FE
0x18004b9d7  mov     rax, [rdi]
0x18004b9da  lea     r8, [rbp+0F0h+var_16C]
0x18004b9de  mov     rdx, [rbp+0F0h+var_148]
0x18004b9e2  mov     rcx, rdi
0x18004b9e5  mov     rax, [rax+0A0h]
0x18004b9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
