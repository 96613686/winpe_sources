# BinXmlVariantHolder::InitFromString(BinXmlVarType,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x18001d954`
- end: `0x18001df67`
- name: `?InitFromString@BinXmlVariantHolder@@QEAA_NW4BinXmlVarType@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z`
- size: `1555`
- prototype: `char __fastcall(PSID *Sid, unsigned int, const wchar_t **)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e178`
- `0x18001d47c`
- `0x180037d68`
- `0x1800432c0`

## callees

- `0x180016250`
- `0x18001c310`
- `0x18001c320`
- `0x18001d890`
- `0x18001d954`
- `0x18002590c`
- `0x1800271c8`
- `0x180054848`
- `0x180054a30`
- `0x180076cbc`
- `0x180092008`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18001db71`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18001de45`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18001db71`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18001de45`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x18001dbb4`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x18001dd75`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x18001dbb4`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x18001dd75`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001d9d6`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001db39`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001db9b`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001d9d6`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001db39`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001db9b`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18001db7c`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18001db8d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18001db7c`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18001db8d`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001d9cb`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001dba9`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001d9cb`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001dba9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001db2b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001db2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de75`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001da25`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001da63`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001da25`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001da63`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001deef`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001deef`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001df49`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001df49`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001de56`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001de56`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
char __fastcall BinXmlVariantHolder::InitFromString(PSID *Sid, unsigned int a2, const wchar_t **a3)
{
  char v6; // al
  unsigned int v8; // eax
  void *lpMultiByteStr; // rax
  const WCHAR *v10; // r8
  int v11; // eax
  DWORD LastError; // ebx
  DWORD LengthSid; // eax
  __int64 v14; // rcx
  void *v15; // rax
  const wchar_t *v16; // r8
  __int64 v17; // rdx
  __int16 v18; // ax
  __int64 v19; // r8
  void *v20; // rax
  int v21; // eax
  float v22; // xmm1_4
  _OWORD *v23; // rax
  _WORD *v24; // rax
  const wchar_t *v25; // rax
  unsigned int v26; // eax
  unsigned int v27; // eax
  void *v28; // rax
  unsigned int v29; // r9d
  unsigned int v30; // r10d
  const wchar_t *v31; // r11
  unsigned int v32; // eax
  __int64 v33; // rdx
  __int128 v34; // xmm0
  DWORD v35; // ebx
  struct _SYSTEMTIME *v36; // rax
  int cbMultiByte; // [rsp+28h] [rbp-31h]
  const wchar_t *v38; // [rsp+40h] [rbp-19h] BYREF
  __int64 v39; // [rsp+48h] [rbp-11h]
  __int128 v40; // [rsp+50h] [rbp-9h] BYREF
  __int128 pExceptionObject; // [rsp+60h] [rbp+7h] BYREF
  __int64 v42; // [rsp+70h] [rbp+17h]
  int v43; // [rsp+78h] [rbp+1Fh]
  int v44; // [rsp+7Ch] [rbp+23h]
  int v45; // [rsp+80h] [rbp+27h]
  FILETIME FileTime; // [rsp+D8h] [rbp+7Fh] BYREF

  BinXmlVariantHolder::Clear((BinXmlVariantHolder *)Sid);
  if ( a2 <= 0xB )
  {
    if ( a2 == 11 )
    {
      v22 = _wtof(*a3);
      *(float *)Sid = v22;
      goto LABEL_12;
    }
    if ( a2 <= 5 )
    {
      if ( a2 != 5 )
      {
        if ( !a2 )
        {
LABEL_12:
          *((_DWORD *)Sid + 3) = a2;
          return 1;
        }
        if ( a2 == 1 )
        {
          v14 = *((unsigned int *)a3 + 2);
          *((_DWORD *)Sid + 2) = v14;
          v15 = operator new(saturated_mul(v14 + 1, 2u));
          v16 = *a3;
          v17 = *((unsigned int *)Sid + 2) + 1LL;
          *Sid = v15;
          _o_wcscpy_s(v15, v17, v16);
          goto LABEL_12;
        }
        if ( a2 != 2 )
        {
          if ( a2 == 3 )
            v6 = _o__wtoi(*a3);
          else
            v6 = _o__wtol(*a3);
          *(_BYTE *)Sid = v6;
          goto LABEL_12;
        }
        v8 = WideCharToMultiByte(0, 0x400u, *a3, -1, 0, 0, 0, 0);
        *((_DWORD *)Sid + 2) = v8;
        if ( v8 )
        {
          lpMultiByteStr = operator new(v8);
          v10 = *a3;
          cbMultiByte = *((_DWORD *)Sid + 2);
          *Sid = lpMultiByteStr;
          v11 = WideCharToMultiByte(0, 0x400u, v10, -1, (LPSTR)lpMultiByteStr, cbMultiByte, 0, 0);
          *((_DWORD *)Sid + 2) = v11;
          if ( !v11 )
          {
            operator delete(*Sid);
            LastError = GetLastError();
            if ( !LastError )
              LastError = 1287;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                11,
                WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids,
                LastError);
            }
            v42 = 0;
            v43 = LastError;
            v44 = -1;
            pExceptionObject = 0;
            v45 = 241;
            throw (EvtException *)&pExceptionObject;
          }
          LengthSid = v11 - 1;
          goto LABEL_23;
        }
        return 0;
      }
      v18 = _o__wtoi(*a3);
LABEL_26:
      *(_WORD *)Sid = v18;
      goto LABEL_12;
    }
    switch ( a2 )
    {
      case 6u:
        v18 = _o__wtol(*a3);
        goto LABEL_26;
      case 7u:
        v21 = _o__wtoi(*a3);
        break;
      case 8u:
        v21 = _wtoi64(*a3);
        break;
      case 9u:
        v20 = (void *)_wtoi64(*a3);
        goto LABEL_34;
      default:
        v19 = 10;
LABEL_32:
        v20 = (void *)_o__wcstoui64(*a3, 0, v19);
LABEL_34:
        *Sid = v20;
        goto LABEL_12;
    }
    goto LABEL_68;
  }
  if ( a2 <= 0x11 )
  {
    if ( a2 == 17 )
    {
      v38 = *a3;
      v39 = (__int64)a3[1];
      if ( (unsigned __int8)StringToFileTime(&v38, Sid) )
        goto LABEL_12;
      return 0;
    }
    if ( a2 == 12 )
    {
      *(double *)Sid = _wtof(*a3);
      goto LABEL_12;
    }
    if ( a2 != 13 )
    {
      if ( a2 == 14 )
      {
        v26 = *((_DWORD *)a3 + 2);
        *((_DWORD *)Sid + 2) = v26;
        if ( (v26 & 1) == 0 )
        {
          v27 = v26 >> 1;
          *((_DWORD *)Sid + 2) = v27;
          v28 = operator new(v27);
          v29 = *((_DWORD *)Sid + 2);
          v30 = 0;
          *Sid = v28;
          if ( v29 )
          {
            v31 = *a3;
            do
            {
              v32 = tlx::hex_to_u8<wchar_t>(&v31[2 * v30]);
              if ( v32 > 0xFF )
                break;
              v33 = v30++;
              *((_BYTE *)*Sid + v33) = v32;
              v29 = *((_DWORD *)Sid + 2);
            }
            while ( v30 < v29 );
          }
          if ( v30 == v29 )
            goto LABEL_12;
          operator delete(*Sid);
        }
      }
      else
      {
        if ( a2 != 15 )
          goto LABEL_12;
        v23 = operator new(0x10u);
        if ( v23 )
          *v23 = 0;
        else
          v23 = 0;
        *Sid = v23;
        v24 = (_WORD *)tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(v23, a3);
        if ( v24 && !*v24 )
        {
          v25 = *a3;
          if ( **a3 == 123 )
          {
            if ( v25[9] == 45 )
              goto LABEL_12;
          }
          else if ( v25[8] == 45 )
          {
            goto LABEL_12;
          }
        }
        utl::_RefCountVtable<utl::_RefCountStored<PublisherManifestResource,utl::allocator<int>,0>,0>::_FreeRefCount(
          *Sid,
          16);
      }
      return 0;
    }
    v34 = *(_OWORD *)a3;
    v38 = L"true";
    v40 = v34;
    v39 = 4;
    if ( (unsigned __int8)tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(&v40, &v38)
      || (v39 = 1, v38 = L"1",
                   v40 = v34,
                   (unsigned __int8)tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(&v40, &v38)) )
    {
      v21 = 1;
    }
    else
    {
      v40 = v34;
      if ( !(unsigned __int8)tlx::operator==<wchar_t,utl::char_traits<wchar_t>,wchar_t const (&)[6],0>(&v40) )
      {
        v39 = 1;
        v38 = L"0";
        v40 = v34;
        if ( !(unsigned __int8)tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(&v40, &v38) )
          return 0;
      }
      v21 = 0;
    }
    goto LABEL_68;
  }
  if ( a2 == 18 )
  {
    v38 = *a3;
    v39 = (__int64)a3[1];
    FileTime = 0;
    if ( (unsigned __int8)StringToFileTime(&v38, &FileTime) )
    {
      v36 = (struct _SYSTEMTIME *)operator new(0x10u);
      if ( v36 )
        *v36 = 0;
      else
        v36 = 0;
      *Sid = v36;
      if ( FileTimeToSystemTime(&FileTime, v36) )
        goto LABEL_12;
      utl::_RefCountVtable<utl::_RefCountStored<PublisherManifestResource,utl::allocator<int>,0>,0>::_FreeRefCount(
        *Sid,
        16);
      *Sid = 0;
    }
    return 0;
  }
  if ( a2 != 19 )
  {
    if ( a2 != 20 )
    {
      if ( a2 != 21 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, 13);
        }
        v42 = 0;
        v43 = 13;
        v44 = -1;
        pExceptionObject = 0;
        v45 = 307;
        throw (EvtException *)&pExceptionObject;
      }
      v19 = 16;
      goto LABEL_32;
    }
    v21 = _o__wcstoui64(*a3, 0, 16);
LABEL_68:
    *(_DWORD *)Sid = v21;
    goto LABEL_12;
  }
  if ( ConvertStringSidToSidW(*a3, Sid) )
  {
    LengthSid = GetLengthSid(*Sid);
LABEL_23:
    *((_DWORD *)Sid + 2) = LengthSid;
    goto LABEL_12;
  }
  if ( GetLastError() != 1337 )
  {
    v35 = GetLastError();
    if ( !v35 )
      v35 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, v35);
    }
    v42 = 0;
    v43 = v35;
    v44 = -1;
    pExceptionObject = 0;
    v45 = 286;
    throw (EvtException *)&pExceptionObject;
  }
  return 0;
}

```

## disassembly

```asm
0x18001d954  mov     [rsp-8+arg_0], rbx
0x18001d959  mov     [rsp-8+arg_8], rsi
0x18001d95e  push    rbp
0x18001d95f  push    rdi
0x18001d960  push    r12
0x18001d962  push    r14
0x18001d964  push    r15
0x18001d966  lea     rbp, [rsp-37h]
0x18001d96b  sub     rsp, 90h
0x18001d972  mov     rdi, r8
0x18001d975  mov     esi, edx
0x18001d977  mov     rbx, rcx
0x18001d97a  call    ?Clear@BinXmlVariantHolder@@QEAAXXZ; BinXmlVariantHolder::Clear(void)
0x18001d97f  xor     r15d, r15d
0x18001d982  mov     r12d, 1
0x18001d988  cmp     esi, 0Bh
0x18001d98b  ja      loc_18001DBCA
0x18001d991  jz      loc_18001DBB1
0x18001d997  cmp     esi, 5
0x18001d99a  ja      loc_18001DB47
0x18001d9a0  jz      loc_18001DB36
0x18001d9a6  mov     eax, esi
0x18001d9a8  test    esi, esi
0x18001d9aa  jz      short loc_18001D9DE
0x18001d9ac  sub     eax, r12d
0x18001d9af  jz      loc_18001DAF8
0x18001d9b5  sub     eax, r12d
0x18001d9b8  jz      short loc_18001DA00
0x18001d9ba  sub     eax, r12d
0x18001d9bd  jz      short loc_18001D9D3
0x18001d9bf  cmp     eax, r12d
0x18001d9c2  jnz     loc_18001DDCA
0x18001d9c8  mov     rcx, [rdi]
0x18001d9cb  call    cs:__imp__o__wtol
0x18001d9d1  jmp     short loc_18001D9DC
0x18001d9d3  mov     rcx, [rdi]
0x18001d9d6  call    cs:__imp__o__wtoi
0x18001d9dc  mov     [rbx], al
0x18001d9de  mov     [rbx+0Ch], esi
0x18001d9e1  mov     al, r12b
0x18001d9e4  lea     r11, [rsp+0B0h+var_20]
0x18001d9ec  mov     rbx, [r11+30h]
0x18001d9f0  mov     rsi, [r11+38h]
0x18001d9f4  mov     rsp, r11
0x18001d9f7  pop     r15
0x18001d9f9  pop     r14
0x18001d9fb  pop     r12
0x18001d9fd  pop     rdi
0x18001d9fe  pop     rbp
0x18001d9ff  retn
0x18001da00  mov     r8, [rdi]; lpWideCharStr
0x18001da03  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001da07  mov     [rsp+0B0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18001da0c  mov     r9d, r14d; cchWideChar
0x18001da0f  mov     [rsp+0B0h+lpDefaultChar], r15; lpDefaultChar
0x18001da14  mov     edx, 400h; dwFlags
0x18001da19  mov     [rsp+0B0h+cbMultiByte], r15d; cbMultiByte
0x18001da1e  xor     ecx, ecx; CodePage
0x18001da20  mov     [rsp+0B0h+lpMultiByteStr], r15; lpMultiByteStr
0x18001da25  call    cs:__imp_WideCharToMultiByte
0x18001da2b  mov     [rbx+8], eax
0x18001da2e  test    eax, eax
0x18001da30  jz      loc_18001DF1E
0x18001da36  mov     ecx, eax; dwBytes
0x18001da38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001da3d  mov     ecx, [rbx+8]
0x18001da40  mov     r9d, r14d; cchWideChar
0x18001da43  mov     r8, [rdi]; lpWideCharStr
0x18001da46  mov     edx, 400h; dwFlags
0x18001da4b  mov     [rsp+0B0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18001da50  mov     [rsp+0B0h+lpDefaultChar], r15; lpDefaultChar
0x18001da55  mov     [rsp+0B0h+cbMultiByte], ecx; cbMultiByte
0x18001da59  xor     ecx, ecx; CodePage
0x18001da5b  mov     [rbx], rax
0x18001da5e  mov     [rsp+0B0h+lpMultiByteStr], rax; lpMultiByteStr
0x18001da63  call    cs:__imp_WideCharToMultiByte
0x18001da69  mov     [rbx+8], eax
0x18001da6c  test    eax, eax
0x18001da6e  jnz     short loc_18001DAEE
0x18001da70  mov     rcx, [rbx]; void *
0x18001da73  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001da78  call    cs:__imp_GetLastError
0x18001da7e  mov     ebx, eax
0x18001da80  mov     eax, 507h
0x18001da85  test    ebx, ebx
0x18001da87  cmovz   ebx, eax
0x18001da8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da91  lea     r8, WPP_GLOBAL_Control
0x18001da98  cmp     rcx, r8
0x18001da9b  jz      short loc_18001DAC0
0x18001da9d  test    byte ptr [rcx+1Ch], 2
0x18001daa1  jz      short loc_18001DAC0
0x18001daa3  cmp     byte ptr [rcx+19h], 2
0x18001daa7  jb      short loc_18001DAC0
0x18001daa9  mov     rcx, [rcx+10h]
0x18001daad  lea     edx, [r14+0Ch]
0x18001dab1  mov     r9d, ebx
0x18001dab4  lea     r8, WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids
0x18001dabb  call    WPP_SF_d
0x18001dac0  xorps   xmm0, xmm0
0x18001dac3  mov     [rbp+57h+var_40], r15
0x18001dac7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001dace  mov     [rbp+57h+var_38], ebx
0x18001dad1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001dad5  mov     [rbp+57h+var_34], 0FFFFFFFFh
0x18001dadc  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18001dae1  mov     [rbp+57h+var_30], 0F1h
0x18001dae8  call    _CxxThrowException_0
0x18001daee  dec     eax
0x18001daf0  mov     [rbx+8], eax
0x18001daf3  jmp     loc_18001D9DE
0x18001daf8  mov     ecx, [rdi+8]
0x18001dafb  mov     eax, 2
0x18001db00  mov     [rbx+8], ecx
0x18001db03  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001db0a  add     rcx, r12
0x18001db0d  mul     rcx
0x18001db10  cmovb   rax, r14
0x18001db14  mov     rcx, rax; dwBytes
0x18001db17  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001db1c  mov     edx, [rbx+8]
0x18001db1f  mov     rcx, rax
0x18001db22  mov     r8, [rdi]
0x18001db25  add     rdx, r12
0x18001db28  mov     [rbx], rax
0x18001db2b  call    cs:__imp__o_wcscpy_s
0x18001db31  jmp     loc_18001D9DE
0x18001db36  mov     rcx, [rdi]
0x18001db39  call    cs:__imp__o__wtoi
0x18001db3f  mov     [rbx], ax
0x18001db42  jmp     loc_18001D9DE
0x18001db47  mov     eax, esi
0x18001db49  sub     eax, 6
0x18001db4c  jz      short loc_18001DBA6
0x18001db4e  sub     eax, r12d
0x18001db51  jz      short loc_18001DB98
0x18001db53  sub     eax, r12d
0x18001db56  jz      short loc_18001DB8A
0x18001db58  sub     eax, r12d
0x18001db5b  jz      short loc_18001DB79
0x18001db5d  cmp     eax, r12d
0x18001db60  jnz     loc_18001DDCA
0x18001db66  mov     r8d, 0Ah
0x18001db6c  mov     rcx, [rdi]
0x18001db6f  xor     edx, edx
0x18001db71  call    cs:__imp__o__wcstoui64
0x18001db77  jmp     short loc_18001DB82
0x18001db79  mov     rcx, [rdi]; String
0x18001db7c  call    cs:__imp__wtoi64
0x18001db82  mov     [rbx], rax
0x18001db85  jmp     loc_18001D9DE
0x18001db8a  mov     rcx, [rdi]; String
0x18001db8d  call    cs:__imp__wtoi64
0x18001db93  jmp     loc_18001DD6B
0x18001db98  mov     rcx, [rdi]
0x18001db9b  call    cs:__imp__o__wtoi
0x18001dba1  jmp     loc_18001DD6B
0x18001dba6  mov     rcx, [rdi]
0x18001dba9  call    cs:__imp__o__wtol
0x18001dbaf  jmp     short loc_18001DB3F
0x18001dbb1  mov     rcx, [rdi]; String
0x18001dbb4  call    cs:__imp__wtof
0x18001dbba  xorps   xmm1, xmm1
0x18001dbbd  cvtsd2ss xmm1, xmm0
0x18001dbc1  movss   dword ptr [rbx], xmm1
0x18001dbc5  jmp     loc_18001D9DE
0x18001dbca  cmp     esi, 11h
0x18001dbcd  ja      loc_18001DDAC
0x18001dbd3  jz      loc_18001DD84
0x18001dbd9  mov     eax, esi
0x18001dbdb  sub     eax, 0Ch
0x18001dbde  jz      loc_18001DD72
0x18001dbe4  sub     eax, r12d
0x18001dbe7  jz      loc_18001DCD7
0x18001dbed  sub     eax, r12d
0x18001dbf0  jz      short loc_18001DC6B
0x18001dbf2  sub     eax, r12d
0x18001dbf5  jz      short loc_18001DC05
0x18001dbf7  cmp     eax, r12d
0x18001dbfa  jnz     loc_18001DDCA
0x18001dc00  jmp     loc_18001D9DE
0x18001dc05  mov     ecx, 10h; dwBytes
0x18001dc0a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dc0f  test    rax, rax
0x18001dc12  jz      short loc_18001DC1C
0x18001dc14  xorps   xmm0, xmm0
0x18001dc17  movups  xmmword ptr [rax], xmm0
0x18001dc1a  jmp     short loc_18001DC1F
0x18001dc1c  mov     rax, r15
0x18001dc1f  mov     rdx, rdi
0x18001dc22  mov     [rbx], rax
0x18001dc25  mov     rcx, rax
0x18001dc28  call    ??$string_to_guid@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@@Z; tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(_GUID *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18001dc2d  test    rax, rax
0x18001dc30  jz      short loc_18001DC59
0x18001dc32  cmp     [rax], r15w
0x18001dc36  jnz     short loc_18001DC59
0x18001dc38  mov     rax, [rdi]
0x18001dc3b  cmp     word ptr [rax], 7Bh ; '{'
0x18001dc3f  jnz     short loc_18001DC4E
0x18001dc41  cmp     word ptr [rax+12h], 2Dh ; '-'
0x18001dc46  jz      loc_18001D9DE
0x18001dc4c  jmp     short loc_18001DC59
0x18001dc4e  cmp     word ptr [rax+10h], 2Dh ; '-'
0x18001dc53  jz      loc_18001D9DE
0x18001dc59  mov     rcx, [rbx]
0x18001dc5c  mov     edx, 10h
0x18001dc61  call    ?_FreeRefCount@?$_RefCountVtable@V?$_RefCountStored@VPublisherManifestResource@@V?$allocator@H@utl@@$0A@@utl@@$0A@@utl@@UEAAXXZ; utl::_RefCountVtable<utl::_RefCountStored<PublisherManifestResource,utl::allocator<int>,0>,0>::_FreeRefCount(void)
0x18001dc66  jmp     loc_18001DF1E
0x18001dc6b  mov     eax, [rdi+8]
0x18001dc6e  mov     [rbx+8], eax
0x18001dc71  test    r12b, al
0x18001dc74  jnz     loc_18001DF1E
0x18001dc7a  shr     eax, 1
0x18001dc7c  mov     ecx, eax; dwBytes
0x18001dc7e  mov     [rbx+8], ecx
0x18001dc81  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dc86  mov     r9d, [rbx+8]
0x18001dc8a  mov     r10d, r15d
0x18001dc8d  mov     [rbx], rax
0x18001dc90  test    r9d, r9d
0x18001dc93  jz      short loc_18001DCC1
0x18001dc95  mov     r11, [rdi]
0x18001dc98  lea     eax, [r10+r10]
0x18001dc9c  lea     rcx, [r11+rax*2]
0x18001dca0  call    ??$hex_to_u8@_W@tlx@@YAIPEB_W@Z; tlx::hex_to_u8<wchar_t>(wchar_t const *)
0x18001dca5  cmp     eax, 0FFh
0x18001dcaa  ja      short loc_18001DCC1
0x18001dcac  mov     rcx, [rbx]
0x18001dcaf  mov     edx, r10d
0x18001dcb2  add     r10d, r12d
0x18001dcb5  mov     [rdx+rcx], al
0x18001dcb8  mov     r9d, [rbx+8]
0x18001dcbc  cmp     r10d, r9d
0x18001dcbf  jb      short loc_18001DC98
0x18001dcc1  cmp     r10d, r9d
0x18001dcc4  jz      loc_18001D9DE
0x18001dcca  mov     rcx, [rbx]; void *
0x18001dccd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dcd2  jmp     loc_18001DF1E
0x18001dcd7  movaps  xmm0, xmmword ptr [rdi]
0x18001dcda  lea     rax, aTrue; "true"
0x18001dce1  lea     rdx, [rbp+57h+var_70]
0x18001dce5  mov     [rbp+57h+var_70], rax
0x18001dce9  lea     rcx, [rbp+57h+var_60]
0x18001dced  movdqa  [rbp+57h+var_60], xmm0
0x18001dcf2  mov     [rbp+57h+var_68], 4
0x18001dcfa  call    ??$?8_WU?$char_traits@_W@utl@@@tlx@@YA_NV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@0@Z; tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x18001dcff  test    al, al
0x18001dd01  jnz     short loc_18001DD68
0x18001dd03  lea     rax, a1; "1"
0x18001dd0a  mov     [rbp+57h+var_68], r12
0x18001dd0e  lea     rdx, [rbp+57h+var_70]
0x18001dd12  mov     [rbp+57h+var_70], rax
0x18001dd16  lea     rcx, [rbp+57h+var_60]
0x18001dd1a  movdqa  [rbp+57h+var_60], xmm0
0x18001dd1f  call    ??$?8_WU?$char_traits@_W@utl@@@tlx@@YA_NV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@0@Z; tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x18001dd24  test    al, al
0x18001dd26  jnz     short loc_18001DD68
0x18001dd28  lea     rcx, [rbp+57h+var_60]
0x18001dd2c  movdqa  [rbp+57h+var_60], xmm0
0x18001dd31  call    ??$?8_WU?$char_traits@_W@utl@@AEAY05$$CB_W$0A@@tlx@@YA_NV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@AEAY05$$CB_W@Z; tlx::operator==<wchar_t,utl::char_traits<wchar_t>,wchar_t const (&)[6],0>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t const (&)[6])
0x18001dd36  test    al, al
0x18001dd38  jnz     short loc_18001DD63
0x18001dd3a  lea     rax, a0_0; "0"
0x18001dd41  mov     [rbp+57h+var_68], r12
0x18001dd45  lea     rdx, [rbp+57h+var_70]
0x18001dd49  mov     [rbp+57h+var_70], rax
0x18001dd4d  lea     rcx, [rbp+57h+var_60]
0x18001dd51  movdqa  [rbp+57h+var_60], xmm0
0x18001dd56  call    ??$?8_WU?$char_traits@_W@utl@@@tlx@@YA_NV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@0@Z; tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x18001dd5b  test    al, al
0x18001dd5d  jz      loc_18001DF1E
0x18001dd63  mov     eax, r15d
0x18001dd66  jmp     short loc_18001DD6B
0x18001dd68  mov     eax, r12d
0x18001dd6b  mov     [rbx], eax
0x18001dd6d  jmp     loc_18001D9DE
0x18001dd72  mov     rcx, [rdi]; String
0x18001dd75  call    cs:__imp__wtof
0x18001dd7b  movsd   qword ptr [rbx], xmm0
0x18001dd7f  jmp     loc_18001D9DE
0x18001dd84  mov     rax, [rdi]
0x18001dd87  lea     rcx, [rbp+57h+var_70]
0x18001dd8b  mov     [rbp+57h+var_70], rax
0x18001dd8f  mov     rdx, rbx
0x18001dd92  mov     rax, [rdi+8]
0x18001dd96  mov     [rbp+57h+var_68], rax
0x18001dd9a  call    ?StringToFileTime@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAU_FILETIME@@@Z; StringToFileTime(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_FILETIME *)
0x18001dd9f  test    al, al
0x18001dda1  jnz     loc_18001D9DE
0x18001dda7  jmp     loc_18001DF1E
0x18001ddac  mov     eax, esi
0x18001ddae  sub     eax, 12h
0x18001ddb1  jz      loc_18001DEFA
0x18001ddb7  sub     eax, r12d
0x18001ddba  jz      loc_18001DE50
0x18001ddc0  sub     eax, r12d
0x18001ddc3  jz      short loc_18001DE3C
0x18001ddc5  cmp     eax, r12d
  ... truncated ...
```
