# sndPlaySoundI(ushort const *,HINSTANCE__ *,ulong)

- ea: `0x180004e0c`
- end: `0x180005564`
- name: `?sndPlaySoundI@@YAHPEBGPEAUHINSTANCE__@@K@Z`
- size: `1880`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HINSTANCE hModule, WPARAM wParam)`
- caller_count: `3`
- callee_count: `19`
- tags: `loader_planting`

## callers

- `0x180004d90`
- `0x180019de0`
- `0x18001a1e0`

## callees

- `0x1800027a0`
- `0x180003720`
- `0x1800039b8`
- `0x180003a2c`
- `0x180003fa0`
- `0x180004700`
- `0x180004e0c`
- `0x18000556c`
- `0x180005650`
- `0x180007020`
- `0x18000a170`
- `0x18000b6d4`
- `0x18000c990`
- `0x180012cec`
- `0x180015eb4`
- `0x180019358`
- `0x180019f1c`
- `0x180019fb4`
- `0x18001a811`

## import_xrefs

- `ntdll!wcsstr` at `0x1800051e4`
- `ntdll!wcsstr` at `0x1800051e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x1800051d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x1800051d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005019`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005462`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005019`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005462`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005198`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005198`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800053c3`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800053c3`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800053b4`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800053b4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000509e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000509e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800053a6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800053a6`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180005320`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18000533b`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180005320`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18000533b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180005248`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18000526d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180005298`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180005248`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18000526d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180005298`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x1800054d0`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x180005559`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x1800054d0`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x180005559`

## pseudocode

```c
int __fastcall sndPlaySoundI(unsigned __int16 *a1, HINSTANCE hModule, WPARAM wParam)
{
  unsigned __int16 *v4; // rbx
  LPCWSTR v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rdx
  int v8; // esi
  HLOCAL v9; // rax
  void *v10; // rdi
  unsigned int v11; // edx
  LPCWSTR v12; // rcx
  __int64 v13; // r8
  UINT v14; // eax
  LPCWSTR v15; // rcx
  __int64 v16; // rdx
  SIZE_T v17; // rdx
  __int64 v19; // rdx
  __int64 v20; // rcx
  DWORD v21; // r8d
  wchar_t *v22; // rax
  shregmin *v23; // rcx
  const unsigned __int16 *v24; // r8
  const unsigned __int16 *v25; // r9
  const unsigned __int16 *v26; // r14
  __int64 v27; // rbx
  HRSRC ResourceW; // rdi
  HGLOBAL Resource; // rax
  DWORD v30; // eax
  unsigned int v31; // r15d
  unsigned __int16 *v32; // rax
  unsigned __int16 *v33; // r14
  unsigned int v34; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v35; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t SubStr[8]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[256]; // [rsp+50h] [rbp-B0h] BYREF

  v34 = wParam;
  v4 = a1;
  if ( (wParam & 0xFF80DF20) != 0 )
    return 0;
  if ( (wParam & 4) != 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v6 = 12;
LABEL_17:
      WPP_SF_qD(*((_QWORD *)v5 + 2), v6, wParam, v4, wParam);
      goto LABEL_18;
    }
  }
  else if ( (unsigned __int64)a1 < 0x10000 )
  {
    if ( !a1 )
    {
LABEL_19:
      v5 = WPP_GLOBAL_Control;
      goto LABEL_20;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v6 = 14;
      goto LABEL_17;
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids,
        (_DWORD)v4,
        wParam);
LABEL_18:
      wParam = v34;
      goto LABEL_19;
    }
  }
LABEL_20:
  if ( (wParam & 0x10) != 0 && lpWavHdr )
  {
    if ( v5 == (LPCWSTR)&WPP_GLOBAL_Control || (*((_DWORD *)v5 + 7) & 0x400000) == 0 || !*((_BYTE *)v5 + 25) )
      return 0;
    v7 = 15;
    goto LABEL_97;
  }
  v8 = 1;
  szLastSoundPlayed = 0;
  if ( (wParam & 1) != 0 )
  {
    if ( (unsigned int)CreatehwndNotify() )
    {
      v5 = WPP_GLOBAL_Control;
      wParam = v34;
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids);
        v5 = WPP_GLOBAL_Control;
      }
      wParam = v34 & 0xFFFFFFFE;
      v34 &= ~1u;
    }
  }
  if ( !v4 && (wParam & 5) == 5 )
  {
    if ( v5 != (LPCWSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x400000) != 0 && *((_BYTE *)v5 + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)v5 + 2), 17, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids);
      v5 = WPP_GLOBAL_Control;
      LODWORD(wParam) = v34;
    }
    wParam = (unsigned int)wParam & 0xFFFFFFFE;
    v34 = wParam;
  }
  if ( (wParam & 4) == 0 && v4 )
  {
    v9 = LocalAlloc(0x40u, 0x200u);
    v10 = v9;
    if ( !v9 )
      return 0;
    v11 = v34 | 0x80000000;
    v34 |= 0x80000000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids, v9);
      v12 = WPP_GLOBAL_Control;
      v11 = v34;
    }
    v13 = 1114112;
    if ( (v11 & 0x110000) == 0x110000 )
    {
      v14 = TransAlias((unsigned int)v4);
      if ( !LoadStringW(ghInst, v14, (LPWSTR)v10, 256) )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        {
          goto LABEL_69;
        }
        v16 = 19;
LABEL_68:
        WPP_SF_q(*((_QWORD *)v15 + 2), v16, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids, v10);
LABEL_69:
        v8 = 0;
LABEL_70:
        LocalFree(v10);
        return v8;
      }
      v4 = (unsigned __int16 *)v10;
      v12 = WPP_GLOBAL_Control;
      v11 = v34 & 0xFFEFFFFF;
      v34 &= ~0x100000u;
    }
    if ( !*v4 )
    {
      if ( v12 != (LPCWSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x400000) != 0 && *((_BYTE *)v12 + 25) >= 3u )
        WPP_SF_q(*((_QWORD *)v12 + 2), 20, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids, v10);
      goto LABEL_70;
    }
    if ( (v11 & 0x10000) != 0 )
      StringCbCopyW(&szLastSoundPlayed, 0x208u, v4);
    if ( !GetSoundName(v4, (size_t *)v10, v13, &v34) )
    {
      wParam = v34;
      if ( (v34 & 2) != 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        {
          goto LABEL_69;
        }
        v16 = 21;
        goto LABEL_68;
      }
      goto LABEL_86;
    }
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVSTest>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_HVSTest>::GetImpl'::`2'::impl);
    if ( !mmRegQueryUserValue(v20, v19, v21, pszPath)
      || (wcscpy(SubStr, L"\\media\\"),
          _wcslwr_s((wchar_t *)v10, 0x100u),
          (v22 = wcsstr((const wchar_t *)v10, SubStr)) == 0) )
    {
LABEL_85:
      wParam = v34;
LABEL_86:
      v4 = (unsigned __int16 *)v10;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
LABEL_116:
        if ( v10 )
        {
          LODWORD(wParam) = wParam | 0x80000000;
          v34 = wParam;
        }
        goto LABEL_118;
      }
      WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, wParam, (_DWORD)v10, (char)v10);
      wParam = v34;
LABEL_115:
      v5 = WPP_GLOBAL_Control;
      goto LABEL_116;
    }
    v26 = v22 + 6;
    v35 = 0;
    if ( (int)shregmin::SHRegGetBOOLWithREGSAM(v23, (HKEY)v17, v24, v25, &v35) < 0 || !v35 )
    {
      v27 = -1;
      do
        ++v27;
      while ( pszPath[v27] );
      if ( StringCbCatW(pszPath, 0x200u, L"\\dm") >= 0
        && PathFileExistsW(pszPath)
        && StringCbCatW(pszPath, 0x200u, v26) >= 0
        && PathFileExistsW(pszPath) )
      {
LABEL_84:
        StringCchCopyW((unsigned __int16 *)v10, 0x100u, pszPath);
        goto LABEL_85;
      }
      pszPath[v27] = 0;
    }
    if ( StringCbCatW(pszPath, 0x200u, v26) < 0 || !PathFileExistsW(pszPath) )
      goto LABEL_85;
    goto LABEL_84;
  }
  v17 = 0;
  if ( (wParam & 0x40004) == 0x40004 )
  {
    ResourceW = FindResourceW(hModule, v4, L"SOUND");
    if ( !ResourceW )
    {
      ResourceW = FindResourceW(hModule, v4, L"WAVE");
      if ( !ResourceW )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          return 0;
        }
        v7 = 24;
        goto LABEL_97;
      }
    }
    Resource = LoadResource(hModule, ResourceW);
    if ( !Resource )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        return 0;
      }
      v7 = 23;
LABEL_97:
      WPP_SF_(*((_QWORD *)v5 + 2), v7, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids);
      return 0;
    }
    v4 = (unsigned __int16 *)LockResource(Resource);
    v30 = SizeofResource(hModule, ResourceW);
    wParam = v34;
    v5 = WPP_GLOBAL_Control;
    LODWORD(wParam) = v34 & 0xFFFBFFFF;
    v34 &= ~0x40000u;
    v17 = v30;
  }
  v10 = 0;
  if ( (wParam & 1) != 0 )
  {
    if ( (wParam & 4) != 0 )
    {
      if ( *(_DWORD *)v4 != 1179011410 )
        return 0;
      if ( *((_DWORD *)v4 + 2) != 1163280727 )
        return 0;
      v17 = (unsigned int)(*((_DWORD *)v4 + 1) + 8);
      if ( *((_DWORD *)v4 + 1) >= 0xFFFFFFF8 )
        return 0;
    }
    else if ( !(_DWORD)v17 )
    {
      goto LABEL_118;
    }
    if ( (unsigned int)v17 < 0x200000 )
    {
      v31 = v17;
      v32 = (unsigned __int16 *)LocalAlloc(0x40u, v17);
      v33 = v32;
      if ( !v32 )
        return 0;
      memcpy_0(v32, v4, v31);
      wParam = v34;
      LODWORD(wParam) = v34 | 0x40000000;
      v4 = v33;
      v34 |= 0x40000000u;
      goto LABEL_115;
    }
  }
LABEL_118:
  if ( (wParam & 1) != 0 )
  {
    if ( v5 != (LPCWSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x400000) != 0 && *((_BYTE *)v5 + 25) >= 4u )
    {
      WPP_SF_SqD(*((_QWORD *)v5 + 2), v17, wParam, (_DWORD)v4, (char)v4, wParam);
      LODWORD(wParam) = v34;
    }
    return PostMessageW(hwndNotify, 0x3CCu, (unsigned int)wParam, (LPARAM)v4);
  }
  else
  {
    if ( hwndNotify )
    {
      PostMessageW(hwndNotify, 0x3CDu, 0, 0);
      v5 = WPP_GLOBAL_Control;
      wParam = v34;
    }
    if ( v5 != (LPCWSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x400000) != 0 && *((_BYTE *)v5 + 25) >= 4u )
      WPP_SF_qD(*((_QWORD *)v5 + 2), 25, wParam, v4, wParam);
    return sndMessage(v4);
  }
}

```

## disassembly

```asm
0x180004e0c  mov     [rsp-8+arg_18], rbx
0x180004e11  push    rbp
0x180004e12  push    rsi
0x180004e13  push    rdi
0x180004e14  push    r12
0x180004e16  push    r13
0x180004e18  push    r14
0x180004e1a  push    r15
0x180004e1c  lea     rbp, [rsp-160h]
0x180004e24  sub     rsp, 260h
0x180004e2b  mov     rax, cs:__security_cookie
0x180004e32  xor     rax, rsp
0x180004e35  mov     [rbp+190h+var_40], rax
0x180004e3c  mov     [rsp+290h+var_260], r8d
0x180004e41  mov     r14, rdx
0x180004e44  mov     rbx, rcx
0x180004e47  test    r8d, 0FF80DF20h
0x180004e4e  jnz     loc_180005374
0x180004e54  xor     r12d, r12d
0x180004e57  lea     rdi, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids
0x180004e5e  lea     r15, WPP_GLOBAL_Control
0x180004e65  mov     r13d, 400000h
0x180004e6b  test    r8b, 4
0x180004e6f  jz      short loc_180004E9C
0x180004e71  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e78  cmp     rcx, r15
0x180004e7b  jz      loc_180004F17
0x180004e81  test    [rcx+1Ch], r13d
0x180004e85  jz      loc_180004F17
0x180004e8b  cmp     byte ptr [rcx+19h], 4
0x180004e8f  jb      loc_180004F17
0x180004e95  lea     edx, [r12+0Ch]
0x180004e9a  jmp     short loc_180004EFA
0x180004e9c  cmp     rbx, 10000h
0x180004ea3  jb      short loc_180004ED8
0x180004ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180004eac  cmp     rcx, r15
0x180004eaf  jz      short loc_180004F17
0x180004eb1  test    [rcx+1Ch], r13d
0x180004eb5  jz      short loc_180004F17
0x180004eb7  cmp     byte ptr [rcx+19h], 4
0x180004ebb  jb      short loc_180004F17
0x180004ebd  mov     rcx, [rcx+10h]
0x180004ec1  mov     edx, 0Dh
0x180004ec6  mov     [rsp+290h+var_270], r8d
0x180004ecb  mov     r9, rbx
0x180004ece  mov     r8, rdi
0x180004ed1  call    WPP_SF_Sd
0x180004ed6  jmp     short loc_180004F0B
0x180004ed8  test    rbx, rbx
0x180004edb  jz      short loc_180004F10
0x180004edd  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ee4  cmp     rcx, r15
0x180004ee7  jz      short loc_180004F17
0x180004ee9  test    [rcx+1Ch], r13d
0x180004eed  jz      short loc_180004F17
0x180004eef  cmp     byte ptr [rcx+19h], 4
0x180004ef3  jb      short loc_180004F17
0x180004ef5  mov     edx, 0Eh
0x180004efa  mov     rcx, [rcx+10h]
0x180004efe  mov     r9, rbx
0x180004f01  mov     [rsp+290h+var_270], r8d
0x180004f06  call    WPP_SF_qD
0x180004f0b  mov     r8d, [rsp+290h+var_260]
0x180004f10  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f17  test    r8b, 10h
0x180004f1b  jz      short loc_180004F53
0x180004f1d  cmp     cs:lpWavHdr, r12
0x180004f24  jz      short loc_180004F53
0x180004f26  cmp     rcx, r15
0x180004f29  jz      loc_180005374
0x180004f2f  test    [rcx+1Ch], r13d
0x180004f33  jz      loc_180005374
0x180004f39  mov     esi, 1
0x180004f3e  cmp     [rcx+19h], sil
0x180004f42  jb      loc_180005374
0x180004f48  lea     edx, [rsi+0Eh]
0x180004f4b  mov     r8, rdi
0x180004f4e  jmp     loc_18000536B
0x180004f53  mov     esi, 1
0x180004f58  mov     cs:?szLastSoundPlayed@@3PAGA, r12w; ushort near * szLastSoundPlayed
0x180004f60  test    sil, r8b
0x180004f63  jz      short loc_180004FB8
0x180004f65  call    CreatehwndNotify
0x180004f6a  test    eax, eax
0x180004f6c  jnz     short loc_180004FAC
0x180004f6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f75  cmp     rcx, r15
0x180004f78  jz      short loc_180004F9C
0x180004f7a  test    [rcx+1Ch], r13d
0x180004f7e  jz      short loc_180004F9C
0x180004f80  cmp     byte ptr [rcx+19h], 4
0x180004f84  jb      short loc_180004F9C
0x180004f86  mov     rcx, [rcx+10h]
0x180004f8a  lea     edx, [rsi+0Fh]
0x180004f8d  mov     r8, rdi
0x180004f90  call    WPP_SF_
0x180004f95  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f9c  mov     r8d, [rsp+290h+var_260]
0x180004fa1  and     r8d, 0FFFFFFFEh
0x180004fa5  mov     [rsp+290h+var_260], r8d
0x180004faa  jmp     short loc_180004FB8
0x180004fac  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fb3  mov     r8d, [rsp+290h+var_260]
0x180004fb8  test    rbx, rbx
0x180004fbb  jnz     short loc_180004FFC
0x180004fbd  mov     eax, r8d
0x180004fc0  and     eax, 5
0x180004fc3  cmp     al, 5
0x180004fc5  jnz     short loc_180004FFC
0x180004fc7  cmp     rcx, r15
0x180004fca  jz      short loc_180004FF3
0x180004fcc  test    [rcx+1Ch], r13d
0x180004fd0  jz      short loc_180004FF3
0x180004fd2  cmp     byte ptr [rcx+19h], 4
0x180004fd6  jb      short loc_180004FF3
0x180004fd8  mov     rcx, [rcx+10h]
0x180004fdc  lea     edx, [rbx+11h]
0x180004fdf  mov     r8, rdi
0x180004fe2  call    WPP_SF_
0x180004fe7  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fee  mov     r8d, [rsp+290h+var_260]
0x180004ff3  and     r8d, 0FFFFFFFEh
0x180004ff7  mov     [rsp+290h+var_260], r8d
0x180004ffc  test    r8b, 4
0x180005000  jnz     loc_1800052FB
0x180005006  test    rbx, rbx
0x180005009  jz      loc_1800052FB
0x18000500f  mov     edx, 200h; uBytes
0x180005014  mov     ecx, 40h ; '@'; uFlags
0x180005019  call    cs:__imp_LocalAlloc
0x18000501f  mov     rdi, rax
0x180005022  test    rax, rax
0x180005025  jz      loc_180005374
0x18000502b  mov     edx, [rsp+290h+var_260]
0x18000502f  bts     edx, 1Fh
0x180005033  mov     [rsp+290h+var_260], edx
0x180005037  mov     rcx, cs:WPP_GLOBAL_Control
0x18000503e  cmp     rcx, r15
0x180005041  jz      short loc_180005072
0x180005043  test    [rcx+1Ch], r13d
0x180005047  jz      short loc_180005072
0x180005049  cmp     byte ptr [rcx+19h], 4
0x18000504d  jb      short loc_180005072
0x18000504f  mov     rcx, [rcx+10h]
0x180005053  lea     r8, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids
0x18000505a  mov     edx, 12h
0x18000505f  mov     r9, rax
0x180005062  call    WPP_SF_q
0x180005067  mov     rcx, cs:WPP_GLOBAL_Control
0x18000506e  mov     edx, [rsp+290h+var_260]
0x180005072  mov     r8d, 110000h
0x180005078  mov     eax, edx
0x18000507a  and     eax, r8d
0x18000507d  mov     r14d, 100h
0x180005083  cmp     eax, r8d
0x180005086  jnz     short loc_1800050EA
0x180005088  mov     ecx, ebx; unsigned int
0x18000508a  call    ?TransAlias@@YAII@Z; TransAlias(uint)
0x18000508f  mov     rcx, cs:ghInst; hInstance
0x180005096  mov     edx, eax; uID
0x180005098  mov     r9d, r14d; cchBufferMax
0x18000509b  mov     r8, rdi; lpBuffer
0x18000509e  call    cs:__imp_LoadStringW
0x1800050a4  test    eax, eax
0x1800050a6  jnz     short loc_1800050D4
0x1800050a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050af  cmp     rcx, r15
0x1800050b2  jz      loc_180005192
0x1800050b8  test    [rcx+1Ch], r13d
0x1800050bc  jz      loc_180005192
0x1800050c2  cmp     byte ptr [rcx+19h], 3
0x1800050c6  jb      loc_180005192
0x1800050cc  lea     edx, [rax+13h]
0x1800050cf  jmp     loc_18000517F
0x1800050d4  mov     edx, [rsp+290h+var_260]
0x1800050d8  mov     rbx, rdi
0x1800050db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050e2  btr     edx, 14h
0x1800050e6  mov     [rsp+290h+var_260], edx
0x1800050ea  cmp     [rbx], r12w
0x1800050ee  jnz     short loc_180005127
0x1800050f0  cmp     rcx, r15
0x1800050f3  jz      loc_180005195
0x1800050f9  test    [rcx+1Ch], r13d
0x1800050fd  jz      loc_180005195
0x180005103  cmp     byte ptr [rcx+19h], 3
0x180005107  jb      loc_180005195
0x18000510d  mov     rcx, [rcx+10h]
0x180005111  lea     r8, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids
0x180005118  mov     edx, 14h
0x18000511d  mov     r9, rdi
0x180005120  call    WPP_SF_q
0x180005125  jmp     short loc_180005195
0x180005127  bt      edx, 10h
0x18000512b  jnb     short loc_180005141
0x18000512d  mov     r8, rbx; unsigned __int16 *
0x180005130  lea     rcx, ?szLastSoundPlayed@@3PAGA; unsigned __int16 *
0x180005137  mov     edx, 208h; unsigned __int64
0x18000513c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180005141  lea     r9, [rsp+290h+var_260]; unsigned int *
0x180005146  mov     rdx, rdi; unsigned __int16 *
0x180005149  mov     rcx, rbx; unsigned __int16 *
0x18000514c  call    ?GetSoundName@@YAHPEBGPEAGKAEAK@Z; GetSoundName(ushort const *,ushort *,ulong,ulong &)
0x180005151  test    eax, eax
0x180005153  jnz     short loc_1800051A5
0x180005155  mov     r8d, [rsp+290h+var_260]
0x18000515a  test    r8b, 2
0x18000515e  jz      loc_1800052B9
0x180005164  mov     rcx, cs:WPP_GLOBAL_Control
0x18000516b  cmp     rcx, r15
0x18000516e  jz      short loc_180005192
0x180005170  test    [rcx+1Ch], r13d
0x180005174  jz      short loc_180005192
0x180005176  cmp     byte ptr [rcx+19h], 3
0x18000517a  jb      short loc_180005192
0x18000517c  lea     edx, [rax+15h]
0x18000517f  mov     rcx, [rcx+10h]
0x180005183  lea     r8, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids
0x18000518a  mov     r9, rdi
0x18000518d  call    WPP_SF_q
0x180005192  mov     esi, r12d
0x180005195  mov     rcx, rdi; hMem
0x180005198  call    cs:__imp_LocalFree
0x18000519e  mov     eax, esi
0x1800051a0  jmp     loc_180005376
0x1800051a5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HVSTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HVSTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVSTest> `wil::Feature<__WilFeatureTraits_Feature_HVSTest>::GetImpl(void)'::`2'::impl
0x1800051ac  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_HVSTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVSTest>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x1800051b1  lea     r9, [rsp+290h+pszPath]
0x1800051b6  call    mmRegQueryUserValue
0x1800051bb  test    eax, eax
0x1800051bd  jz      loc_1800052B4
0x1800051c3  movups  xmm0, xmmword ptr cs:aMedia; "\\media\\"
0x1800051ca  mov     rdx, r14; SizeInWords
0x1800051cd  mov     rcx, rdi; String
0x1800051d0  movdqu  xmmword ptr [rsp+290h+SubStr], xmm0
0x1800051d6  call    cs:__imp__wcslwr_s
0x1800051dc  lea     rdx, [rsp+290h+SubStr]; SubStr
0x1800051e1  mov     rcx, rdi; Str
0x1800051e4  call    cs:__imp_wcsstr
0x1800051ea  test    rax, rax
0x1800051ed  jz      loc_1800052B4
0x1800051f3  lea     r14, [rax+0Ch]
0x1800051f7  mov     [rsp+290h+var_258], r12d
0x1800051fc  lea     rax, [rsp+290h+var_258]
0x180005201  mov     qword ptr [rsp+290h+var_270], rax; unsigned int
0x180005206  call    ?SHRegGetBOOLWithREGSAM@shregmin@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; shregmin::SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18000520b  test    eax, eax
0x18000520d  js      short loc_180005216
0x18000520f  cmp     [rsp+290h+var_258], r12d
0x180005214  jnz     short loc_18000527D
0x180005216  lea     rax, [rsp+290h+pszPath]
0x18000521b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000521f  inc     rbx
0x180005222  cmp     [rax+rbx*2], r12w
0x180005227  jnz     short loc_18000521F
0x180005229  lea     r8, aDm; "\\dm"
0x180005230  mov     edx, 200h; unsigned __int64
0x180005235  lea     rcx, [rsp+290h+pszPath]; unsigned __int16 *
0x18000523a  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18000523f  test    eax, eax
0x180005241  js      short loc_180005277
0x180005243  lea     rcx, [rsp+290h+pszPath]; pszPath
0x180005248  call    cs:__imp_PathFileExistsW
0x18000524e  test    eax, eax
0x180005250  jz      short loc_180005277
0x180005252  mov     r8, r14; unsigned __int16 *
0x180005255  lea     rcx, [rsp+290h+pszPath]; unsigned __int16 *
0x18000525a  mov     edx, 200h; unsigned __int64
0x18000525f  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180005264  test    eax, eax
0x180005266  js      short loc_180005277
0x180005268  lea     rcx, [rsp+290h+pszPath]; pszPath
0x18000526d  call    cs:__imp_PathFileExistsW
0x180005273  test    eax, eax
0x180005275  jnz     short loc_1800052A2
0x180005277  mov     [rsp+rbx*2+290h+pszPath], r12w
0x18000527d  mov     r8, r14; unsigned __int16 *
0x180005280  lea     rcx, [rsp+290h+pszPath]; unsigned __int16 *
0x180005285  mov     edx, 200h; unsigned __int64
0x18000528a  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18000528f  test    eax, eax
0x180005291  js      short loc_1800052B4
0x180005293  lea     rcx, [rsp+290h+pszPath]; pszPath
0x180005298  call    cs:__imp_PathFileExistsW
0x18000529e  test    eax, eax
0x1800052a0  jz      short loc_1800052B4
0x1800052a2  lea     r8, [rsp+290h+pszPath]; unsigned __int16 *
0x1800052a7  mov     edx, 100h; unsigned __int64
0x1800052ac  mov     rcx, rdi; unsigned __int16 *
0x1800052af  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800052b4  mov     r8d, [rsp+290h+var_260]
0x1800052b9  mov     rbx, rdi
0x1800052bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052c3  cmp     rcx, r15
0x1800052c6  jz      loc_1800054A2
0x1800052cc  test    [rcx+1Ch], r13d
0x1800052d0  jz      loc_1800054A2
0x1800052d6  cmp     byte ptr [rcx+19h], 4
0x1800052da  jb      loc_1800054A2
  ... truncated ...
```
