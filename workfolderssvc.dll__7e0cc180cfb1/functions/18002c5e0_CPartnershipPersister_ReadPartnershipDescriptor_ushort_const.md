# CPartnershipPersister::ReadPartnershipDescriptor(ushort const *)

- ea: `0x18002c5e0`
- end: `0x18002d05b`
- name: `?ReadPartnershipDescriptor@CPartnershipPersister@@UEAA?AVClientPartnershipDescriptor@@PEBG@Z`
- size: `2683`
- prototype: `__int64 __fastcall(CPartnershipPersister *, __int64, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007e10`
- `0x180009384`
- `0x18000a694`
- `0x180010ee0`
- `0x180011314`
- `0x18001137c`
- `0x180015904`
- `0x180023c90`
- `0x180028fcc`
- `0x18002bf00`
- `0x18002c070`
- `0x18002c5e0`
- `0x18002d664`
- `0x18002dad0`
- `0x18002e12c`
- `0x18004edb8`
- `0x180061b18`
- `0x1800b178c`
- `0x1800b1a5c`
- `0x1800b1a88`
- `0x1800b1e44`
- `0x1800b2090`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002ca07`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002ca07`

## string_xrefs

- `0x18002cacd`: `ConfiguredByPolicy`
- `0x18002c6a7`: `CPartnershipPersister::ReadPartnershipDescriptor`
- `0x18002c921`: `StagingPath`
- `0x18002c968`: `StagingDownloadPath`

## pseudocode

```c
__int64 __fastcall CPartnershipPersister::ReadPartnershipDescriptor(
        CPartnershipPersister *a1,
        __int64 a2,
        const unsigned __int16 *a3)
{
  _BYTE *v6; // rax
  char v7; // al
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r10
  __int64 String; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  const OLECHAR *v18; // rax
  HRESULT v19; // eax
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  struct IUnknown *v24; // rdx
  char v25; // r13
  __int64 v26; // r12
  char v27; // r15
  __int64 v28; // r14
  __int64 v29; // rsi
  char v30; // r8
  char v31; // dl
  char v32; // di
  __int64 v33; // rbx
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r10
  __int64 v39; // r11
  __int64 v40; // rbx
  int v41; // r9d
  __int64; // rax
  char v43; // [rsp+B0h] [rbp-168h]
  char v44; // [rsp+B4h] [rbp-164h]
  __int64 v45; // [rsp+B8h] [rbp-160h] BYREF
  int v46; // [rsp+C0h] [rbp-158h] BYREF
  int v47; // [rsp+C4h] [rbp-154h]
  char v48; // [rsp+C8h] [rbp-150h]
  const char *v49; // [rsp+D0h] [rbp-148h]
  __int64 v50; // [rsp+D8h] [rbp-140h]
  int v51; // [rsp+E0h] [rbp-138h]
  int v52; // [rsp+E4h] [rbp-134h]
  int v53; // [rsp+E8h] [rbp-130h]
  int v54; // [rsp+F0h] [rbp-128h] BYREF
  __int64 v55; // [rsp+F8h] [rbp-120h]
  __int64 v56; // [rsp+100h] [rbp-118h]
  const unsigned __int16 *v57; // [rsp+108h] [rbp-110h]
  int pExceptionObject; // [rsp+110h] [rbp-108h] BYREF
  int v59; // [rsp+114h] [rbp-104h] BYREF
  HRESULT v60; // [rsp+118h] [rbp-100h] BYREF
  int v61; // [rsp+120h] [rbp-F8h] BYREF
  int v62; // [rsp+128h] [rbp-F0h] BYREF
  int v63; // [rsp+130h] [rbp-E8h] BYREF
  int v64; // [rsp+134h] [rbp-E4h] BYREF
  _BYTE v65[8]; // [rsp+138h] [rbp-E0h] BYREF
  __int64 v66; // [rsp+140h] [rbp-D8h]
  __int64 v67; // [rsp+148h] [rbp-D0h]
  __int64 v68; // [rsp+150h] [rbp-C8h]
  __int64 v69; // [rsp+158h] [rbp-C0h]
  __int64 v70; // [rsp+160h] [rbp-B8h]
  const unsigned __int16 *v71; // [rsp+168h] [rbp-B0h]
  const ATL::CAtlException *v72; // [rsp+170h] [rbp-A8h] BYREF
  _BYTE v73[32]; // [rsp+178h] [rbp-A0h] BYREF
  _BYTE v74[16]; // [rsp+198h] [rbp-80h] BYREF
  __int64 v75; // [rsp+1A8h] [rbp-70h]
  _BYTE v76[32]; // [rsp+1B8h] [rbp-60h] BYREF

  v71 = a3;
  v55 = a2;
  v56 = a2;
  v57 = a3;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, &WPP_979727760fef30a0e91810ffe65e0bbf_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( (v6[68] & 8) != 0 && v6[65] >= 6u )
  {
    v7 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v7 = 0;
LABEL_9:
  v46 = 0;
  v47 = 168;
  v48 = v7;
  v49 = "CPartnershipPersister::ReadPartnershipDescriptor";
  v50 = 0;
  if ( !a3 )
  {
    v46 = -2147024809;
    HIWORD(v47) = 170;
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  v46 = 0;
  LOWORD(v47) = 170;
  v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a1 + 8);
  CEcsPath::ConcatenatePaths(v76, v8, a3, 0);
  v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v76);
  v10 = CEcsRegKey::CurrentUserKeyForService(v65);
  CEcsRegKey::Get((HKEY *)&v45, (HKEY *)v10, (const WCHAR *)v9, 131097, 0, 0, 0, 0);
  CEcsRegKey::Close((CEcsRegKey *)v65);
  if ( !v45 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v76);
      WPP_SF_S(*(_QWORD *)(v12 + 56), 19, &WPP_979727760fef30a0e91810ffe65e0bbf_Traceguids, v11);
    }
    v46 = -2147023728;
    HIWORD(v47) = 182;
    v59 = -2147023728;
    throw (long *)&v59;
  }
  ClientPartnershipDescriptor::ClientPartnershipDescriptor((ClientPartnershipDescriptor *)a2);
  v44 = 1;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    std::wstring::operator=(a2 + 416, a3);
    String = CEcsRegKey::GetString((HKEY *)&v45, (__int64)v73, L"ServerUrl", (__int64)&Format, 0);
    v67 = a2 + 136;
    std::wstring::operator=(a2 + 136, String);
    std::wstring::~wstring(v73);
    v14 = CEcsRegKey::GetString((HKEY *)&v45, (__int64)v73, L"DiscoveryUrl", (__int64)&Format, 0);
    std::wstring::operator=(a2 + 448, v14);
    std::wstring::~wstring(v73);
    v15 = CEcsRegKey::GetString((HKEY *)&v45, (__int64)v73, L"LocalFolder", (__int64)&Format, 0);
    v70 = a2 + 40;
    std::wstring::operator=(a2 + 40, v15);
    std::wstring::~wstring(v73);
    v16 = CEcsRegKey::GetString((HKEY *)&v45, (__int64)v73, c_pcwszEcsStagingPathRegItem, (__int64)&Format, 0);
    v69 = a2 + 72;
    std::wstring::operator=(a2 + 72, v16);
    std::wstring::~wstring(v73);
    v17 = CEcsRegKey::GetString((HKEY *)&v45, (__int64)v73, c_pcwszEcsStagingDownloadPathRegItem, (__int64)&Format, 0);
    v68 = a2 + 104;
    std::wstring::operator=(a2 + 104, v17);
    std::wstring::~wstring(v73);
    v66 = a2 + 328;
    *(GUID *)(a2 + 328) = GUID_NULL;
    CEcsRegKey::GetString((HKEY *)&v45, (__int64)v74, L"ChangeTrackingId", (__int64)&Format, 0);
    if ( v75 )
    {
      v18 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v74);
      v19 = CLSIDFromString(v18, (LPCLSID)(a2 + 328));
      v46 = v19;
      if ( v19 < 0 )
      {
        HIWORD(v47) = 204;
        v60 = v19;
        throw (long *)&v60;
      }
      LOWORD(v47) = 204;
    }
    v20 = CEcsRegKey::GetString((HKEY *)&v45, (__int64)v73, L"ServerPartnershipId", (__int64)&Format, 0);
    v21 = a2 + 200;
    std::wstring::operator=(a2 + 200, v20);
    std::wstring::~wstring(v73);
    v61 = 0;
    v51 = 0;
    ((void (__fastcall *)(__int64 *, const unsigned __int16 *, int *))CEcsRegKey::GetGenericValue<unsigned long,unsigned long>)(
      &v45,
      L"ConfiguredByPolicy",
      &v61);
    *(_BYTE *)(a2 + 392) = v51 != 0;
    v62 = 0;
    v52 = 0;
    ((void (__fastcall *)(__int64 *, const unsigned __int16 *, int *))CEcsRegKey::GetGenericValue<unsigned long,unsigned long>)(
      &v45,
      L"ActivationState",
      &v62);
    *(_DWORD *)(a2 + 360) = v52;
    v54 = 0;
    v53 = 0;
    ((void (__fastcall *)(__int64 *, const unsigned __int16 *, int *))CEcsRegKey::GetGenericValue<unsigned long,unsigned long>)(
      &v45,
      L"SearchIndexAdded",
      &v54);
    *(_BYTE *)(a2 + 394) = v53 != 0;
    v22 = (*(__int64 (__fastcall **)(CPartnershipPersister *, _BYTE *, const unsigned __int16 *))(*(_QWORD *)a1 + 96LL))(
            a1,
            v73,
            a3);
    std::wstring::operator=(a2 + 168, v22);
    std::wstring::~wstring(v73);
    v23 = (*(__int64 (__fastcall **)(CPartnershipPersister *, _BYTE *, const unsigned __int16 *))(*(_QWORD *)a1 + 120LL))(
            a1,
            v73,
            a3);
    std::wstring::operator=(a2 + 480, v23);
    std::wstring::~wstring(v73);
    *(_BYTE *)(a2 + 395) = (*(__int64 (__fastcall **)(CPartnershipPersister *, const unsigned __int16 *))(*(_QWORD *)a1 + 128LL))(
                             a1,
                             a3);
    *(_QWORD *)(a2 + 400) = (*(__int64 (__fastcall **)(CPartnershipPersister *, const unsigned __int16 *))(*(_QWORD *)a1 + 160LL))(
                              a1,
                              a3);
    *(_BYTE *)(a2 + 380) = (*(__int64 (__fastcall **)(CPartnershipPersister *, const unsigned __int16 *))(*(_QWORD *)a1 + 104LL))(
                             a1,
                             a3);
    *(_DWORD *)(a2 + 384) = (*(__int64 (__fastcall **)(CPartnershipPersister *, const unsigned __int16 *))(*(_QWORD *)a1 + 208LL))(
                              a1,
                              a3);
    *(_QWORD *)(a2 + 408) = (*(__int64 (__fastcall **)(CPartnershipPersister *, const unsigned __int16 *))(*(_QWORD *)a1 + 176LL))(
                              a1,
                              a3);
    *(_QWORD *)(a2 + 344) = (*(__int64 (__fastcall **)(CPartnershipPersister *, const unsigned __int16 *))(*(_QWORD *)a1 + 192LL))(
                              a1,
                              a3);
    v24 = (struct IUnknown *)*((_QWORD *)a1 + 5);
    if ( *(struct IUnknown **)(a2 + 368) != v24 )
      ATL::AtlComPtrAssign((struct IUnknown **)(a2 + 368), v24);
    *(_BYTE *)(a2 + 396) = (unsigned int)CPartnershipPersister::ReadDWORDWithVerify(
                                           a1,
                                           a3,
                                           L"SyncOnMeteredNetwork",
                                           1,
                                           2u) != 0;
    *(_BYTE *)(a2 + 397) = (unsigned int)CPartnershipPersister::ReadDWORDWithVerify(a1, a3, L"SyncWhenRoaming", 0, 2u) != 0;
    *(_DWORD *)(a2 + 376) = CPartnershipPersister::ReadDWORD(a1, a3, L"LastSyncHResult", 0);
    BasePartnershipDescriptor::Validate((BasePartnershipDescriptor *)a2, 1);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      v54 = *(_DWORD *)(a2 + 376);
      v43 = *(_BYTE *)(a2 + 397) != 0 ? 89 : 78;
      v25 = *(_BYTE *)(a2 + 396) != 0 ? 89 : 78;
      v26 = *(_QWORD *)(a2 + 400);
      v27 = *(_BYTE *)(a2 + 395) != 0 ? 89 : 78;
      v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 480);
      v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 168);
      v32 = v31 + (*(_BYTE *)(v55 + 394) != 0 ? v30 : 0);
      v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
      v34 = CEcsGuid::ToString(v73, v66);
      v44 = 3;
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v67);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v68);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
      v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v70);
      WPP_SF_SSSScSSdcSSciiccdD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        v36,
        v37,
        v35,
        v36,
        v37,
        v38,
        *(_BYTE *)(v55 + 392) != 0 ? 89 : 78,
        v39,
        v33,
        *(_DWORD *)(v55 + 360),
        v32,
        v29,
        v28,
        v27,
        v26,
        *(_QWORD *)(v55 + 408),
        v25,
        v43,
        v54,
        *(_DWORD *)(v55 + 384));
    }
    if ( (v44 & 2) != 0 )
      std::wstring::~wstring(v73);
    std::wstring::~wstring(v74);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v64) )
    {
      v46 = v64;
      v41 = (int)v57;
      v40 = v56;
      __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_18002CF63);
      goto LABEL_32;
    }
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      HIWORD(v47) = 273;
      v46 = -2147024882;
      v41 = (int)v57;
      v40 = v56;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18002CF65);
      goto LABEL_32;
    }
    if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', 0) )
    {
      HIWORD(v47) = 273;
      v46 = -2147418113;
      v41 = (int)v57;
      v40 = v56;
      __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_18002CF67);
      goto LABEL_32;
    }
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v72) )
    {
      HIWORD(v47) = 273;
      v46 = *(_DWORD *)v72;
      v41 = (int)v57;
      v40 = v56;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18002CF69);
LABEL_32:
      if ( v46 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            21,
            (unsigned int)&WPP_979727760fef30a0e91810ffe65e0bbf_Traceguids,
            v41,
            v46);
        }
        v46 = -2134375676;
        HIWORD(v47) = 278;
        v63 = -2134375676;
        throw (long *)&v63;
      }
      CEcsRegKey::Close((CEcsRegKey *)&v45);
      std::wstring::~wstring(v76);
      CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v46);
       = v40;
    }
  }
  v40 = v55;
  v41 = (int)v71;
  goto LABEL_32;
}

```

## disassembly

```asm
0x18002c5e0  push    rbx
0x18002c5e2  push    rsi
0x18002c5e3  push    rdi
0x18002c5e4  push    r12
0x18002c5e6  push    r13
0x18002c5e8  push    r14
0x18002c5ea  push    r15
0x18002c5ec  sub     rsp, 1E0h
0x18002c5f3  mov     rax, cs:__security_cookie
0x18002c5fa  xor     rax, rsp
0x18002c5fd  mov     [rsp+218h+var_40], rax
0x18002c605  mov     r14, r8
0x18002c608  mov     [rsp+218h+var_B0], r8
0x18002c610  mov     rsi, rdx
0x18002c613  mov     [rsp+218h+var_120], rdx
0x18002c61b  mov     r12, rcx
0x18002c61e  mov     [rsp+218h+var_118], rdx
0x18002c626  mov     [rsp+218h+var_110], r8
0x18002c62e  mov     r13d, 1
0x18002c634  mov     [rsp+218h+var_164], r13d
0x18002c63c  lea     r15, WPP_GLOBAL_Control
0x18002c643  mov     rax, cs:WPP_GLOBAL_Control
0x18002c64a  cmp     rax, r15
0x18002c64d  jz      short loc_18002C676
0x18002c64f  test    byte ptr [rax+44h], 8
0x18002c653  jz      short loc_18002C689
0x18002c655  cmp     byte ptr [rax+41h], 6
0x18002c659  jb      short loc_18002C676
0x18002c65b  lea     edx, [r13+11h]
0x18002c65f  lea     r8, WPP_979727760fef30a0e91810ffe65e0bbf_Traceguids
0x18002c666  mov     rcx, [rax+38h]
0x18002c66a  call    WPP_SF_
0x18002c66f  mov     rax, cs:WPP_GLOBAL_Control
0x18002c676  test    byte ptr [rax+44h], 8
0x18002c67a  jz      short loc_18002C689
0x18002c67c  cmp     byte ptr [rax+41h], 6
0x18002c680  jb      short loc_18002C689
0x18002c682  mov     al, r13b
0x18002c685  xor     edi, edi
0x18002c687  jmp     short loc_18002C68E
0x18002c689  xor     edi, edi
0x18002c68b  mov     al, dil
0x18002c68e  mov     [rsp+218h+var_158], edi
0x18002c695  mov     [rsp+218h+var_154], 0A8h
0x18002c6a0  mov     [rsp+218h+var_150], al
0x18002c6a7  lea     rax, aCpartnershippe_0; "CPartnershipPersister::ReadPartnershipD"...
0x18002c6ae  mov     [rsp+218h+var_148], rax
0x18002c6b6  mov     [rsp+218h+var_140], rdi
0x18002c6be  mov     eax, [rsp+218h+var_158]
0x18002c6c5  mov     [rsp+218h+var_158], eax
0x18002c6cc  mov     eax, 0AAh
0x18002c6d1  test    r14, r14
0x18002c6d4  jnz     short loc_18002C706
0x18002c6d6  mov     ecx, 80070057h
0x18002c6db  mov     [rsp+218h+var_158], ecx
0x18002c6e2  mov     word ptr [rsp+218h+var_154+2], ax
0x18002c6ea  mov     [rsp+218h+pExceptionObject], ecx
0x18002c6f1  lea     rdx, _TI1J; pThrowInfo
0x18002c6f8  lea     rcx, [rsp+218h+pExceptionObject]; pExceptionObject
0x18002c700  call    _CxxThrowException_0
0x18002c706  mov     [rsp+218h+var_158], edi
0x18002c70d  mov     word ptr [rsp+218h+var_154], ax
0x18002c715  lea     rcx, [r12+8]
0x18002c71a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002c71f  xor     r9d, r9d
0x18002c722  mov     r8, r14
0x18002c725  mov     rdx, rax
0x18002c728  lea     rcx, [rsp+218h+var_60]
0x18002c730  call    ?ConcatenatePaths@CEcsPath@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG00000000@Z; CEcsPath::ConcatenatePaths(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18002c735  nop
0x18002c736  lea     rcx, [rsp+218h+var_60]
0x18002c73e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002c743  mov     rbx, rax
0x18002c746  lea     rcx, [rsp+218h+var_E0]
0x18002c74e  call    ?CurrentUserKeyForService@CEcsRegKey@@SA?AV1@XZ; CEcsRegKey::CurrentUserKeyForService(void)
0x18002c753  nop
0x18002c754  mov     byte ptr [rsp+218h+var_1E0], dil
0x18002c759  mov     [rsp+218h+var_1E8], rdi
0x18002c75e  mov     [rsp+218h+var_1F0], rdi
0x18002c763  mov     byte ptr [rsp+218h+var_1F8], dil
0x18002c768  mov     r9d, 20019h
0x18002c76e  mov     r8, rbx
0x18002c771  mov     rdx, rax
0x18002c774  lea     rcx, [rsp+218h+var_160]
0x18002c77c  call    ?Get@CEcsRegKey@@SA?AV1@AEBV1@PEBGK_NPEAU_SECURITY_ATTRIBUTES@@PEA_N2@Z; CEcsRegKey::Get(CEcsRegKey const &,ushort const *,ulong,bool,_SECURITY_ATTRIBUTES *,bool *,bool)
0x18002c781  nop
0x18002c782  lea     rcx, [rsp+218h+var_E0]; this
0x18002c78a  call    ?Close@CEcsRegKey@@QEAAXXZ; CEcsRegKey::Close(void)
0x18002c78f  cmp     [rsp+218h+var_160], rdi
0x18002c797  jnz     loc_18002C81F
0x18002c79d  mov     r10, cs:WPP_GLOBAL_Control
0x18002c7a4  cmp     r10, r15
0x18002c7a7  jz      short loc_18002C7DC
0x18002c7a9  test    byte ptr [r10+44h], 8
0x18002c7ae  jz      short loc_18002C7DC
0x18002c7b0  cmp     byte ptr [r10+41h], 2
0x18002c7b5  jb      short loc_18002C7DC
0x18002c7b7  lea     rcx, [rsp+218h+var_60]
0x18002c7bf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002c7c4  mov     r9, rax
0x18002c7c7  mov     edx, 13h
0x18002c7cc  lea     r8, WPP_979727760fef30a0e91810ffe65e0bbf_Traceguids
0x18002c7d3  mov     rcx, [r10+38h]
0x18002c7d7  call    WPP_SF_S
0x18002c7dc  mov     eax, [rsp+218h+var_158]
0x18002c7e3  mov     [rsp+218h+var_158], eax
0x18002c7ea  mov     ecx, 80070490h
0x18002c7ef  mov     [rsp+218h+var_158], ecx
0x18002c7f6  mov     eax, 0B6h
0x18002c7fb  mov     word ptr [rsp+218h+var_154+2], ax
0x18002c803  mov     [rsp+218h+var_104], ecx
0x18002c80a  lea     rdx, _TI1J; pThrowInfo
0x18002c811  lea     rcx, [rsp+218h+var_104]; pExceptionObject
0x18002c819  call    _CxxThrowException_0
0x18002c81f  mov     rcx, rsi; this
0x18002c822  call    ??0ClientPartnershipDescriptor@@QEAA@XZ; ClientPartnershipDescriptor::ClientPartnershipDescriptor(void)
0x18002c827  nop
0x18002c828  mov     [rsp+218h+var_164], r13d
0x18002c830  lea     rcx, [rsi+1A0h]
0x18002c837  mov     rdx, r14
0x18002c83a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18002c83f  mov     qword ptr [rsp+218h+var_1F8], rdi
0x18002c844  lea     rbx, Format
0x18002c84b  mov     r9, rbx
0x18002c84e  lea     r8, aServerurl; "ServerUrl"
0x18002c855  lea     rdx, [rsp+218h+var_A0]
0x18002c85d  lea     rcx, [rsp+218h+var_160]
0x18002c865  call    ?GetString@CEcsRegKey@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0PEA_N_N@Z; CEcsRegKey::GetString(ushort const *,ushort const *,bool *,bool)
0x18002c86a  nop
0x18002c86b  lea     rcx, [rsi+88h]
0x18002c872  mov     [rsp+218h+var_D0], rcx
0x18002c87a  mov     rdx, rax
0x18002c87d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c882  nop
0x18002c883  lea     rcx, [rsp+218h+var_A0]
0x18002c88b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c890  mov     qword ptr [rsp+218h+var_1F8], rdi
0x18002c895  mov     r9, rbx
0x18002c898  lea     r8, aDiscoveryurl; "DiscoveryUrl"
0x18002c89f  lea     rdx, [rsp+218h+var_A0]
0x18002c8a7  lea     rcx, [rsp+218h+var_160]
0x18002c8af  call    ?GetString@CEcsRegKey@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0PEA_N_N@Z; CEcsRegKey::GetString(ushort const *,ushort const *,bool *,bool)
0x18002c8b4  nop
0x18002c8b5  lea     rcx, [rsi+1C0h]
0x18002c8bc  mov     rdx, rax
0x18002c8bf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c8c4  nop
0x18002c8c5  lea     rcx, [rsp+218h+var_A0]
0x18002c8cd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c8d2  mov     qword ptr [rsp+218h+var_1F8], rdi
0x18002c8d7  mov     r9, rbx
0x18002c8da  lea     r8, aLocalfolder; "LocalFolder"
0x18002c8e1  lea     rdx, [rsp+218h+var_A0]
0x18002c8e9  lea     rcx, [rsp+218h+var_160]
0x18002c8f1  call    ?GetString@CEcsRegKey@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0PEA_N_N@Z; CEcsRegKey::GetString(ushort const *,ushort const *,bool *,bool)
0x18002c8f6  nop
0x18002c8f7  lea     rcx, [rsi+28h]
0x18002c8fb  mov     [rsp+218h+var_B8], rcx
0x18002c903  mov     rdx, rax
0x18002c906  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c90b  nop
0x18002c90c  lea     rcx, [rsp+218h+var_A0]
0x18002c914  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c919  mov     qword ptr [rsp+218h+var_1F8], rdi
0x18002c91e  mov     r9, rbx
0x18002c921  lea     r8, ?c_pcwszEcsStagingPathRegItem@@3PAGA; "StagingPath"
0x18002c928  lea     rdx, [rsp+218h+var_A0]
0x18002c930  lea     rcx, [rsp+218h+var_160]
0x18002c938  call    ?GetString@CEcsRegKey@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0PEA_N_N@Z; CEcsRegKey::GetString(ushort const *,ushort const *,bool *,bool)
0x18002c93d  nop
0x18002c93e  lea     rcx, [rsi+48h]
0x18002c942  mov     [rsp+218h+var_C0], rcx
0x18002c94a  mov     rdx, rax
0x18002c94d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c952  nop
0x18002c953  lea     rcx, [rsp+218h+var_A0]
0x18002c95b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c960  mov     qword ptr [rsp+218h+var_1F8], rdi
0x18002c965  mov     r9, rbx
0x18002c968  lea     r8, ?c_pcwszEcsStagingDownloadPathRegItem@@3PAGA; "StagingDownloadPath"
0x18002c96f  lea     rdx, [rsp+218h+var_A0]
0x18002c977  lea     rcx, [rsp+218h+var_160]
0x18002c97f  call    ?GetString@CEcsRegKey@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0PEA_N_N@Z; CEcsRegKey::GetString(ushort const *,ushort const *,bool *,bool)
0x18002c984  nop
0x18002c985  lea     rcx, [rsi+68h]
0x18002c989  mov     [rsp+218h+var_C8], rcx
0x18002c991  mov     rdx, rax
0x18002c994  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c999  nop
0x18002c99a  lea     rcx, [rsp+218h+var_A0]
0x18002c9a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c9a7  lea     rbx, [rsi+148h]
0x18002c9ae  mov     [rsp+218h+var_D8], rbx
0x18002c9b6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002c9bd  movdqu  xmmword ptr [rbx], xmm0
0x18002c9c1  mov     qword ptr [rsp+218h+var_1F8], rdi
0x18002c9c6  lea     r9, Format
0x18002c9cd  lea     r8, aChangetracking; "ChangeTrackingId"
0x18002c9d4  lea     rdx, [rsp+218h+var_80]
0x18002c9dc  lea     rcx, [rsp+218h+var_160]
0x18002c9e4  call    ?GetString@CEcsRegKey@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0PEA_N_N@Z; CEcsRegKey::GetString(ushort const *,ushort const *,bool *,bool)
0x18002c9e9  nop
0x18002c9ea  cmp     [rsp+218h+var_70], rdi
0x18002c9f2  jz      short loc_18002CA4F
0x18002c9f4  lea     rcx, [rsp+218h+var_80]
0x18002c9fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ca01  mov     rcx, rax; lpsz
0x18002ca04  mov     rdx, rbx; pclsid
0x18002ca07  call    cs:__imp_CLSIDFromString
0x18002ca0d  mov     [rsp+218h+var_158], eax
0x18002ca14  mov     [rsp+218h+var_158], eax
0x18002ca1b  mov     ecx, 0CCh
0x18002ca20  test    eax, eax
0x18002ca22  jns     short loc_18002CA47
0x18002ca24  mov     word ptr [rsp+218h+var_154+2], cx
0x18002ca2c  mov     [rsp+218h+var_100], eax
0x18002ca33  lea     rdx, _TI1J; pThrowInfo
0x18002ca3a  lea     rcx, [rsp+218h+var_100]; pExceptionObject
0x18002ca42  call    _CxxThrowException_0
0x18002ca47  mov     word ptr [rsp+218h+var_154], cx
0x18002ca4f  mov     qword ptr [rsp+218h+var_1F8], rdi
0x18002ca54  lea     r9, Format
0x18002ca5b  lea     r8, aServerpartners_0; "ServerPartnershipId"
0x18002ca62  lea     rdx, [rsp+218h+var_A0]
0x18002ca6a  lea     rcx, [rsp+218h+var_160]
0x18002ca72  call    ?GetString@CEcsRegKey@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0PEA_N_N@Z; CEcsRegKey::GetString(ushort const *,ushort const *,bool *,bool)
0x18002ca77  nop
0x18002ca78  lea     rbx, [rsi+0C8h]
0x18002ca7f  mov     rdx, rax
0x18002ca82  mov     rcx, rbx
0x18002ca85  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002ca8a  nop
0x18002ca8b  lea     rcx, [rsp+218h+var_A0]
0x18002ca93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ca98  mov     [rsp+218h+var_F8], edi
0x18002ca9f  mov     [rsp+218h+var_138], edi
0x18002caa6  mov     [rsp+218h+var_1E0], rdi
0x18002caab  lea     rax, [rsp+218h+var_138]
0x18002cab3  mov     [rsp+218h+var_1F0], rax
0x18002cab8  lea     rax, [rsp+218h+var_138]
0x18002cac0  mov     qword ptr [rsp+218h+var_1F8], rax
0x18002cac5  lea     r8, [rsp+218h+var_F8]
0x18002cacd  lea     rdx, aConfiguredbypo; "ConfiguredByPolicy"
0x18002cad4  lea     rcx, [rsp+218h+var_160]
0x18002cadc  call    ??$GetGenericValue@KK@CEcsRegKey@@AEBA_NPEBGAEBKKAEAKPEAXKPEA_N@Z; CEcsRegKey::GetGenericValue<ulong,ulong>(ushort const *,ulong const &,ulong,ulong &,void *,ulong,bool *)
0x18002cae1  cmp     [rsp+218h+var_138], edi
0x18002cae8  setnz   al
0x18002caeb  mov     [rsi+188h], al
0x18002caf1  mov     [rsp+218h+var_F0], edi
0x18002caf8  mov     [rsp+218h+var_134], edi
0x18002caff  mov     [rsp+218h+var_1E0], rdi
0x18002cb04  lea     rax, [rsp+218h+var_134]
0x18002cb0c  mov     [rsp+218h+var_1F0], rax
0x18002cb11  lea     rax, [rsp+218h+var_134]
0x18002cb19  mov     qword ptr [rsp+218h+var_1F8], rax
0x18002cb1e  lea     r8, [rsp+218h+var_F0]
0x18002cb26  lea     rdx, aActivationstat; "ActivationState"
0x18002cb2d  lea     rcx, [rsp+218h+var_160]
0x18002cb35  call    ??$GetGenericValue@KK@CEcsRegKey@@AEBA_NPEBGAEBKKAEAKPEAXKPEA_N@Z; CEcsRegKey::GetGenericValue<ulong,ulong>(ushort const *,ulong const &,ulong,ulong &,void *,ulong,bool *)
0x18002cb3a  mov     eax, [rsp+218h+var_134]
0x18002cb41  mov     [rsi+168h], eax
0x18002cb47  mov     [rsp+218h+var_128], edi
0x18002cb4e  mov     [rsp+218h+var_130], edi
0x18002cb55  mov     [rsp+218h+var_1E0], rdi
0x18002cb5a  lea     rax, [rsp+218h+var_130]
0x18002cb62  mov     [rsp+218h+var_1F0], rax
0x18002cb67  lea     rax, [rsp+218h+var_130]
0x18002cb6f  mov     qword ptr [rsp+218h+var_1F8], rax
0x18002cb74  lea     r8, [rsp+218h+var_128]
0x18002cb7c  lea     rdx, aSearchindexadd; "SearchIndexAdded"
0x18002cb83  lea     rcx, [rsp+218h+var_160]
0x18002cb8b  call    ??$GetGenericValue@KK@CEcsRegKey@@AEBA_NPEBGAEBKKAEAKPEAXKPEA_N@Z; CEcsRegKey::GetGenericValue<ulong,ulong>(ushort const *,ulong const &,ulong,ulong &,void *,ulong,bool *)
0x18002cb90  cmp     [rsp+218h+var_130], edi
0x18002cb97  setnz   al
0x18002cb9a  mov     [rsi+18Ah], al
0x18002cba0  mov     rax, [r12]
0x18002cba4  mov     r8, r14
0x18002cba7  lea     rdx, [rsp+218h+var_A0]
0x18002cbaf  mov     rcx, r12
0x18002cbb2  mov     rax, [rax+60h]
0x18002cbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbbb  nop
0x18002cbbc  lea     rcx, [rsi+0A8h]
0x18002cbc3  mov     rdx, rax
0x18002cbc6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002cbcb  nop
0x18002cbcc  lea     rcx, [rsp+218h+var_A0]
0x18002cbd4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002cbd9  mov     rax, [r12]
0x18002cbdd  mov     r8, r14
0x18002cbe0  lea     rdx, [rsp+218h+var_A0]
0x18002cbe8  mov     rcx, r12
0x18002cbeb  mov     rax, [rax+78h]
0x18002cbef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbf4  nop
0x18002cbf5  lea     rcx, [rsi+1E0h]
0x18002cbfc  mov     rdx, rax
0x18002cbff  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002cc04  nop
0x18002cc05  lea     rcx, [rsp+218h+var_A0]
  ... truncated ...
```
