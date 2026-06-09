# CThemeManager2::_ApplyMousePointers(void)

- ea: `0x18001acc4`
- end: `0x18001b0ea`
- name: `?_ApplyMousePointers@CThemeManager2@@AEAAJXZ`
- size: `1062`
- prototype: `__int64 __fastcall(CThemeManager2 *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004f044`

## callees

- `0x180008dd8`
- `0x18000ab00`
- `0x18000ab10`
- `0x18001a2f8`
- `0x18001acc4`
- `0x180031034`
- `0x18003188c`
- `0x180033788`
- `0x1800358c0`
- `0x18003633c`
- `0x1800427dc`
- `0x180046658`
- `0x180060150`
- `0x18006d010`

## import_xrefs

- `SHCORE!SHGetValueW` at `0x18001adce`
- `SHCORE!SHGetValueW` at `0x18001adce`
- `SHCORE!SHSetValueW` at `0x18001aead`
- `SHCORE!SHSetValueW` at `0x18001af4f`
- `SHCORE!SHSetValueW` at `0x18001aead`
- `SHCORE!SHSetValueW` at `0x18001af4f`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18001ae09`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18001ae09`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001ae3e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001ae60`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001ae3e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001ae60`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18001b097`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18001b097`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad6c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001af9e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b001`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b0bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad6c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001af9e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b001`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b0bf`

## string_xrefs

- `0x18001b071`: `Software\Microsoft\Accessibility`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CThemeManager2::_ApplyMousePointers(CThemeManager2 *this)
{
  char v2; // r12
  int v3; // r14d
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _QWORD, LPCWCH *); // rbx
  _QWORD *v6; // rax
  LSTATUS v7; // eax
  bool v8; // sf
  __int64 v9; // rcx
  unsigned int v10; // eax
  HKEY v11; // rcx
  const WCHAR *v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, BSTR *); // rbx
  _QWORD *v16; // rax
  HKEY v17; // rcx
  HKEY v18; // rcx
  HKEY v19; // rcx
  HKEY v20; // rcx
  LPCWCH lpString2; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pdwType; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v24; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  BSTR bstrString[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String1[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 pvData[264]; // [rsp+280h] [rbp+180h] BYREF

  if ( *((_BYTE *)this + 2145) || CThemeManager2::_CanThemeChangeMouseCursors(this) )
  {
    v2 = 0;
    v3 = 0;
    if ( aArrow[0] )
    {
      do
      {
        lpString2 = 0;
        v4 = *((_QWORD *)this + 266);
        v5 = *(void (__fastcall **)(__int64, _QWORD, LPCWCH *))(*(_QWORD *)v4 + 304LL);
        v6 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, off_18006E940[v3]);
        v5(v4, *v6, &lpString2);
        SysFreeString(bstrString[0]);
        memset_0(pvData, 0, 0x208u);
        pdwType = 0;
        pcbData = 520;
        String1[0] = 0;
        v7 = SHGetValueW(HKEY_CURRENT_USER, L"Control Panel\\Cursors", off_18006E940[v3], &pdwType, pvData, &pcbData);
        v8 = v7 < 0;
        if ( v7 > 0 )
          v8 = 1;
        if ( v8 )
          goto LABEL_15;
        if ( pdwType - 1 <= 1 && !(unsigned int)SHExpandEnvironmentStringsW(pvData, String1, 260) )
          StringCchCopyW(String1, 0x104u, pvData);
        if ( CompareStringOrdinal(String1, -1, lpString2, -1, 1) != 2 )
        {
LABEL_15:
          v2 = 1;
          v10 = ATL::CComBSTR::Length((ATL::CComBSTR *)&lpString2);
          v12 = off_18006E940[v3];
          if ( v10 )
          {
            v13 = -1;
            do
              ++v13;
            while ( lpString2[v13] );
            SHSetValueW(HKEY_CURRENT_USER, L"Control Panel\\Cursors", v12, 1u, lpString2, 2 * v13 + 2);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                77,
                (unsigned int)WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
                (unsigned int)off_18006E940[v3],
                (__int64)lpString2);
          }
          else
          {
            HrRegDeleteValue(v11, L"Control Panel\\Cursors", v12);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                76,
                WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
                off_18006E940[v3]);
          }
        }
        else if ( CompareStringOrdinal(String1, -1, lpString2, -1, 1) == 2 )
        {
          v9 = -1;
          do
            ++v9;
          while ( lpString2[v9] );
          SHSetValueW(HKEY_CURRENT_USER, L"Control Panel\\Cursors", off_18006E940[v3], 1u, lpString2, 2 * v9 + 2);
        }
        SysFreeString((BSTR)lpString2);
        ++v3;
      }
      while ( *off_18006E940[v3] );
    }
    v24 = 0;
    v14 = *((_QWORD *)this + 266);
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)v14 + 304LL);
    v16 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"DefaultValue");
    LODWORD(v15) = v15(v14, *v16, &v24);
    SysFreeString(bstrString[0]);
    if ( (int)v15 >= 0 && ATL::CComBSTR::Length((ATL::CComBSTR *)&v24) )
    {
      HrRegSetValueString(v17, L"Control Panel\\Cursors", 0, v24);
      HrRegSetDWORD(v18, L"Control Panel\\Cursors", L"Scheme Source", 2u);
    }
    else
    {
      HrRegDeleteValue(v17, L"Control Panel\\Cursors", 0);
      HrRegDeleteValue(v20, L"Control Panel\\Cursors", L"Scheme Source");
    }
    HrRegDeleteValue(v19, L"Software\\Microsoft\\Accessibility", L"CursorType");
    if ( v2 )
    {
      if ( *((_BYTE *)this + 2145) )
        ClassicSystemParametersInfoW(87, 0, 0, 2);
      else
        SystemParametersInfoAsync(0x57u, 0, 0, 0, 2u, 0, 0);
    }
    SysFreeString(v24);
  }
  return 0;
}

```

## disassembly

```asm
0x18001acc4  push    rbp
0x18001acc6  push    rbx
0x18001acc7  push    rsi
0x18001acc8  push    rdi
0x18001acc9  push    r12
0x18001accb  push    r13
0x18001accd  push    r14
0x18001accf  push    r15
0x18001acd1  lea     rbp, [rsp-3A8h]
0x18001acd9  sub     rsp, 4A8h
0x18001ace0  mov     rax, cs:__security_cookie
0x18001ace7  xor     rax, rsp
0x18001acea  mov     [rbp+3E0h+var_50], rax
0x18001acf1  mov     rsi, rcx
0x18001acf4  xor     r13d, r13d
0x18001acf7  cmp     [rcx+861h], r13b
0x18001acfe  jnz     short loc_18001AD0D
0x18001ad00  call    ?_CanThemeChangeMouseCursors@CThemeManager2@@AEAA_NXZ; CThemeManager2::_CanThemeChangeMouseCursors(void)
0x18001ad05  test    al, al
0x18001ad07  jz      loc_18001B0C5
0x18001ad0d  mov     r12b, r13b
0x18001ad10  mov     r14d, r13d
0x18001ad13  mov     rax, cs:off_18006E940; "Arrow"
0x18001ad1a  cmp     [rax], r13w
0x18001ad1e  jz      loc_18001AFBF
0x18001ad24  lea     rcx, off_18006E940; "Arrow"
0x18001ad2b  mov     [rsp+4E0h+lpString2], r13
0x18001ad30  mov     rdi, [rsi+850h]
0x18001ad37  mov     rax, [rdi]
0x18001ad3a  mov     rbx, [rax+130h]
0x18001ad41  movsxd  r15, r14d
0x18001ad44  mov     rdx, [rcx+r15*8]; unsigned __int16 *
0x18001ad48  lea     rcx, [rsp+4E0h+bstrString]; this
0x18001ad4d  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001ad52  nop
0x18001ad53  lea     r8, [rsp+4E0h+lpString2]
0x18001ad58  mov     rdx, [rax]
0x18001ad5b  mov     rcx, rdi
0x18001ad5e  mov     rax, rbx
0x18001ad61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad66  nop
0x18001ad67  mov     rcx, [rsp+4E0h+bstrString]; bstrString
0x18001ad6c  call    cs:__imp_SysFreeString
0x18001ad72  mov     ebx, 208h
0x18001ad77  mov     r8d, ebx; Size
0x18001ad7a  xor     edx, edx; Val
0x18001ad7c  lea     rcx, [rbp+3E0h+var_260]; void *
0x18001ad83  call    memset_0
0x18001ad88  mov     [rsp+4E0h+pdwType], r13d
0x18001ad8d  mov     [rsp+4E0h+var_488], ebx
0x18001ad91  mov     [rsp+4E0h+String1], r13w
0x18001ad97  lea     rax, [rsp+4E0h+var_488]
0x18001ad9c  mov     [rsp+4E0h+pcbData], rax; pcbData
0x18001ada1  lea     rax, [rbp+3E0h+var_260]
0x18001ada8  mov     [rsp+4E0h+pvData], rax; pvData
0x18001adad  lea     r9, [rsp+4E0h+pdwType]; pdwType
0x18001adb2  lea     rax, off_18006E940; "Arrow"
0x18001adb9  mov     r8, [rax+r15*8]; pszValue
0x18001adbd  lea     rbx, pcszSubKey; "Control Panel\\Cursors"
0x18001adc4  mov     rdx, rbx; pszSubKey
0x18001adc7  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001adce  call    cs:__imp_SHGetValueW
0x18001add4  test    eax, eax
0x18001add6  jle     short loc_18001ADE2
0x18001add8  movzx   eax, ax
0x18001addb  or      eax, 80070000h
0x18001ade0  test    eax, eax
0x18001ade2  mov     edi, 1
0x18001ade7  js      loc_18001AEB8
0x18001aded  mov     eax, [rsp+4E0h+pdwType]
0x18001adf1  dec     eax
0x18001adf3  cmp     eax, edi
0x18001adf5  ja      short loc_18001AE29
0x18001adf7  mov     r8d, 104h
0x18001adfd  lea     rdx, [rsp+4E0h+String1]
0x18001ae02  lea     rcx, [rbp+3E0h+var_260]
0x18001ae09  call    cs:__imp_SHExpandEnvironmentStringsW
0x18001ae0f  test    eax, eax
0x18001ae11  jnz     short loc_18001AE29
0x18001ae13  lea     r8, [rbp+3E0h+var_260]; unsigned __int16 *
0x18001ae1a  mov     edx, 104h; unsigned __int64
0x18001ae1f  lea     rcx, [rsp+4E0h+String1]; unsigned __int16 *
0x18001ae24  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ae29  mov     dword ptr [rsp+4E0h+pvData], edi; bIgnoreCase
0x18001ae2d  or      r9d, 0FFFFFFFFh; cchCount2
0x18001ae31  mov     r8, [rsp+4E0h+lpString2]; lpString2
0x18001ae36  or      edx, r9d; cchCount1
0x18001ae39  lea     rcx, [rsp+4E0h+String1]; lpString1
0x18001ae3e  call    cs:__imp_CompareStringOrdinal
0x18001ae44  cmp     eax, 2
0x18001ae47  jnz     short loc_18001AEB8
0x18001ae49  mov     dword ptr [rsp+4E0h+pvData], edi; bIgnoreCase
0x18001ae4d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ae51  mov     r9d, ebx; cchCount2
0x18001ae54  mov     r8, [rsp+4E0h+lpString2]; lpString2
0x18001ae59  mov     edx, ebx; cchCount1
0x18001ae5b  lea     rcx, [rsp+4E0h+String1]; lpString1
0x18001ae60  call    cs:__imp_CompareStringOrdinal
0x18001ae66  cmp     eax, 2
0x18001ae69  jnz     loc_18001AF99
0x18001ae6f  mov     rax, [rsp+4E0h+lpString2]
0x18001ae74  mov     rcx, rbx
0x18001ae77  inc     rcx
0x18001ae7a  cmp     [rax+rcx*2], r13w
0x18001ae7f  jnz     short loc_18001AE77
0x18001ae81  lea     ecx, ds:2[rcx*2]
0x18001ae88  mov     dword ptr [rsp+4E0h+pcbData], ecx; cbData
0x18001ae8c  mov     [rsp+4E0h+pvData], rax; pvData
0x18001ae91  mov     r9d, edi; dwType
0x18001ae94  lea     rax, off_18006E940; "Arrow"
0x18001ae9b  mov     r8, [rax+r15*8]; pszValue
0x18001ae9f  lea     rdx, pcszSubKey; "Control Panel\\Cursors"
0x18001aea6  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001aead  call    cs:__imp_SHSetValueW
0x18001aeb3  jmp     loc_18001AF99
0x18001aeb8  mov     r12b, dil
0x18001aebb  lea     rcx, [rsp+4E0h+lpString2]; this
0x18001aec0  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x18001aec5  lea     r8, off_18006E940; "Arrow"
0x18001aecc  mov     r8, [r8+r15*8]; unsigned __int16 *
0x18001aed0  test    eax, eax
0x18001aed2  jnz     short loc_18001AF1F
0x18001aed4  mov     rdx, rbx; unsigned __int16 *
0x18001aed7  call    ?HrRegDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; HrRegDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x18001aedc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aee3  lea     rax, WPP_GLOBAL_Control
0x18001aeea  cmp     rcx, rax
0x18001aeed  jz      loc_18001AF99
0x18001aef3  test    byte ptr [rcx+1Ch], 8
0x18001aef7  jz      loc_18001AF99
0x18001aefd  mov     edx, 4Ch ; 'L'
0x18001af02  lea     rax, off_18006E940; "Arrow"
0x18001af09  mov     r9, [rax+r15*8]
0x18001af0d  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18001af14  mov     rcx, [rcx+10h]
0x18001af18  call    WPP_SF_S
0x18001af1d  jmp     short loc_18001AF99
0x18001af1f  mov     rax, [rsp+4E0h+lpString2]
0x18001af24  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001af28  inc     rcx
0x18001af2b  cmp     [rax+rcx*2], r13w
0x18001af30  jnz     short loc_18001AF28
0x18001af32  lea     ecx, ds:2[rcx*2]
0x18001af39  mov     dword ptr [rsp+4E0h+pcbData], ecx; cbData
0x18001af3d  mov     [rsp+4E0h+pvData], rax; pvData
0x18001af42  mov     r9d, edi; dwType
0x18001af45  mov     rdx, rbx; pszSubKey
0x18001af48  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001af4f  call    cs:__imp_SHSetValueW
0x18001af55  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af5c  lea     rax, WPP_GLOBAL_Control
0x18001af63  cmp     rcx, rax
0x18001af66  jz      short loc_18001AF99
0x18001af68  test    byte ptr [rcx+1Ch], 8
0x18001af6c  jz      short loc_18001AF99
0x18001af6e  mov     edx, 4Dh ; 'M'
0x18001af73  mov     rax, [rsp+4E0h+lpString2]
0x18001af78  mov     [rsp+4E0h+pvData], rax
0x18001af7d  lea     rax, off_18006E940; "Arrow"
0x18001af84  mov     r9, [rax+r15*8]
0x18001af88  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18001af8f  mov     rcx, [rcx+10h]
0x18001af93  call    WPP_SF_SS
0x18001af98  nop
0x18001af99  mov     rcx, [rsp+4E0h+lpString2]; bstrString
0x18001af9e  call    cs:__imp_SysFreeString
0x18001afa4  add     r14d, edi
0x18001afa7  movsxd  rax, r14d
0x18001afaa  lea     rcx, off_18006E940; "Arrow"
0x18001afb1  mov     rax, [rcx+rax*8]
0x18001afb5  cmp     [rax], r13w
0x18001afb9  jnz     loc_18001AD2B
0x18001afbf  mov     [rsp+4E0h+var_490], r13
0x18001afc4  mov     rdi, [rsi+850h]
0x18001afcb  mov     rax, [rdi]
0x18001afce  mov     rbx, [rax+130h]
0x18001afd5  lea     rdx, aDefaultvalue; "DefaultValue"
0x18001afdc  lea     rcx, [rsp+4E0h+bstrString]; this
0x18001afe1  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001afe6  nop
0x18001afe7  lea     r8, [rsp+4E0h+var_490]
0x18001afec  mov     rdx, [rax]
0x18001afef  mov     rcx, rdi
0x18001aff2  mov     rax, rbx
0x18001aff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001affa  mov     ebx, eax
0x18001affc  mov     rcx, [rsp+4E0h+bstrString]; bstrString
0x18001b001  call    cs:__imp_SysFreeString
0x18001b007  test    ebx, ebx
0x18001b009  js      short loc_18001B048
0x18001b00b  lea     rcx, [rsp+4E0h+var_490]; this
0x18001b010  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x18001b015  test    eax, eax
0x18001b017  jz      short loc_18001B048
0x18001b019  mov     r9, [rsp+4E0h+var_490]; unsigned __int16 *
0x18001b01e  xor     r8d, r8d; unsigned __int16 *
0x18001b021  lea     rdx, pcszSubKey; "Control Panel\\Cursors"
0x18001b028  call    ?HrRegSetValueString@@YAJPEAUHKEY__@@PEBG11@Z; HrRegSetValueString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001b02d  mov     r9d, 2; unsigned int
0x18001b033  lea     r8, aSchemeSource; "Scheme Source"
0x18001b03a  lea     rdx, pcszSubKey; "Control Panel\\Cursors"
0x18001b041  call    ?HrRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; HrRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001b046  jmp     short loc_18001B06A
0x18001b048  xor     r8d, r8d; unsigned __int16 *
0x18001b04b  lea     rdx, pcszSubKey; "Control Panel\\Cursors"
0x18001b052  call    ?HrRegDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; HrRegDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x18001b057  lea     r8, aSchemeSource; "Scheme Source"
0x18001b05e  lea     rdx, pcszSubKey; "Control Panel\\Cursors"
0x18001b065  call    ?HrRegDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; HrRegDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x18001b06a  lea     r8, aCursortype; "CursorType"
0x18001b071  lea     rdx, aSoftwareMicros_22; "Software\\Microsoft\\Accessibility"
0x18001b078  call    ?HrRegDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; HrRegDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x18001b07d  test    r12b, r12b
0x18001b080  jz      short loc_18001B0BA
0x18001b082  xor     r8d, r8d; void *
0x18001b085  xor     edx, edx; unsigned int
0x18001b087  lea     ecx, [rdx+57h]; unsigned int
0x18001b08a  cmp     [rsi+861h], r13b
0x18001b091  jz      short loc_18001B09F
0x18001b093  lea     r9d, [r8+2]
0x18001b097  call    cs:__imp_ClassicSystemParametersInfoW
0x18001b09d  jmp     short loc_18001B0BA
0x18001b09f  mov     [rsp+4E0h+var_4B0], r13; void **
0x18001b0a4  mov     [rsp+4E0h+pcbData], r13; struct CDimmedWindow *
0x18001b0a9  mov     dword ptr [rsp+4E0h+pvData], 2; unsigned int
0x18001b0b1  xor     r9d, r9d; unsigned int
0x18001b0b4  call    ?SystemParametersInfoAsync@@YAXIIPEAXKIPEAVCDimmedWindow@@PEAPEAX@Z; SystemParametersInfoAsync(uint,uint,void *,ulong,uint,CDimmedWindow *,void * *)
0x18001b0b9  nop
0x18001b0ba  mov     rcx, [rsp+4E0h+var_490]; bstrString
0x18001b0bf  call    cs:__imp_SysFreeString
0x18001b0c5  xor     eax, eax
0x18001b0c7  mov     rcx, [rbp+3E0h+var_50]
0x18001b0ce  xor     rcx, rsp; StackCookie
0x18001b0d1  call    __security_check_cookie
0x18001b0d6  add     rsp, 4A8h
0x18001b0dd  pop     r15
0x18001b0df  pop     r14
0x18001b0e1  pop     r13
0x18001b0e3  pop     r12
0x18001b0e5  pop     rdi
0x18001b0e6  pop     rsi
0x18001b0e7  pop     rbx
0x18001b0e8  pop     rbp
0x18001b0e9  retn
```
