# StartList::HandleFirstTime(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)

- ea: `0x140015720`
- end: `0x140015b8d`
- name: `?HandleFirstTime@StartList@@AEAAJAEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@AEAVCRegKey@3@@Z`
- size: `1133`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140015fb8`

## callees

- `0x140002480`
- `0x140002fa0`
- `0x14000d75c`
- `0x14000ea8c`
- `0x14000ecdc`
- `0x14000f5f4`
- `0x1400136e4`
- `0x140013b44`
- `0x140013bac`
- `0x140013fa8`
- `0x140014058`
- `0x140014290`
- `0x140014490`
- `0x1400151e0`
- `0x140015720`
- `0x1400169b8`
- `0x140016ab4`
- `0x1400171ec`
- `0x14001804c`
- `0x14001827c`
- `0x140018ac8`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140015a4b`
- `KERNEL32!DeleteFileW` at `0x140015aa7`
- `KERNEL32!DeleteFileW` at `0x140015b04`
- `KERNEL32!DeleteFileW` at `0x140015a4b`
- `KERNEL32!DeleteFileW` at `0x140015aa7`
- `KERNEL32!DeleteFileW` at `0x140015b04`
- `KERNEL32!GetFileAttributesW` at `0x140015a19`
- `KERNEL32!GetFileAttributesW` at `0x140015a7f`
- `KERNEL32!GetFileAttributesW` at `0x140015adb`
- `KERNEL32!GetFileAttributesW` at `0x140015a19`
- `KERNEL32!GetFileAttributesW` at `0x140015a7f`
- `KERNEL32!GetFileAttributesW` at `0x140015adb`

## string_xrefs

- `0x140015849`: `Configuration`
- `0x14001576e`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StartList::HandleFirstTime(__int64 a1, LPCWSTR *a2, _QWORD *a3, ATL::CRegKey *a4)
{
  unsigned int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // ebx
  const unsigned __int16 **Next; // rbx
  LPCWSTR v13; // rbx
  unsigned int v14; // r9d
  unsigned int v15; // eax
  __int64 v16; // r8
  signed int v17; // edi
  unsigned int v18; // eax
  __int64 v19; // r8
  ATL::CStringData *v20; // r12
  int *v21; // rdi
  __int64 v22; // rbx
  const WCHAR *v23; // rsi
  const WCHAR *v24; // rdi
  const WCHAR *v25; // rbx
  HKEY v26; // [rsp+30h] [rbp-D0h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v28; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR v29; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v30[3]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v31; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  int v34; // [rsp+98h] [rbp-68h]
  unsigned __int16 v35[264]; // [rsp+A0h] [rbp-60h] BYREF

  v7 = ATL::CRegKey::Create(
         a4,
         HKEY_CURRENT_USER,
         StartList::_accessibilityKeyString,
         (unsigned __int16 *)a4,
         0,
         3u,
         v26,
         (unsigned int *)&lpFileName);
  v10 = v7;
  if ( !v7 )
  {
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 10;
    lpFileName = *a2;
    while ( lpFileName )
    {
      Next = (const unsigned __int16 **)ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNext(
                                          v8,
                                          &lpFileName);
      if ( *((_DWORD *)Accommodation::Open(*Next) + 20) != 1 )
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          &v31,
          *Next);
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
    StartList::BuildConfigString(&lpFileName, &v31);
    v13 = lpFileName;
    v15 = ATL::CRegKey::SetStringValue(a4, StartList::_configuration, lpFileName, v14);
    v17 = v15;
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, v16, v15);
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
    }
    else
    {
      memset(v30, 0, sizeof(v30));
      v18 = ATL::CRegKey::Open(
              (ATL::CRegKey *)v30,
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders",
              0x20019u);
      v17 = v18;
      if ( !v18 )
      {
        memset_0(v35, 0, 0x208u);
        LODWORD(lpFileName) = 260;
        ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v30, L"Startup", v35, (unsigned int *)&lpFileName);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &lpFileName,
          v35);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v28,
          v35);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v29,
          v35);
        ATL::CSimpleStringT<unsigned short,0>::Append(&lpFileName, L"\\On-Screen Keyboard.lnk", 23);
        ATL::CSimpleStringT<unsigned short,0>::Append(&v28, L"\\Narrator.lnk", 13);
        ATL::CSimpleStringT<unsigned short,0>::Append(&v29, L"\\Magnifier.lnk", 14);
        v20 = (ATL::CStringData *)(v13 - 12);
        v21 = (int *)(*a3 - 24LL);
        if ( v13 - 12 != (LPCWSTR)v21 )
        {
          if ( v21[4] >= 0 && *(_QWORD *)v20 == *(_QWORD *)v21 )
          {
            v22 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v13 - 12);
            ATL::CStringData::Release((ATL::CStringData *)v21);
            *a3 = v22 + 24;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v13, *((unsigned int *)v13 - 4));
          }
        }
        v23 = lpFileName;
        if ( GetFileAttributesW(lpFileName) != -1 )
        {
          ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",osk", 4);
          DeleteFileW(v23);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44);
        }
        v24 = v28;
        if ( GetFileAttributesW(v28) != -1 )
        {
          ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",Narrator", 9);
          DeleteFileW(v24);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45);
        }
        v25 = v29;
        if ( GetFileAttributesW(v29) != -1 )
        {
          ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",magnifierpane", 14);
          DeleteFileW(v25);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46);
        }
        ATL::CStringData::Release((ATL::CStringData *)(v25 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(v24 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(v23 - 12));
        ATL::CRegKey::Close((ATL::CRegKey *)v30);
        ATL::CStringData::Release(v20);
        v17 = 0;
        goto LABEL_44;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, v19, v18);
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      ATL::CRegKey::Close((ATL::CRegKey *)v30);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
LABEL_44:
    ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v31);
    return (unsigned int)v17;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v9, v7);
  if ( v10 > 0 )
    return (unsigned __int16)v10 | 0x80070000;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140015720  push    rbp
0x140015722  push    rbx
0x140015723  push    rsi
0x140015724  push    rdi
0x140015725  push    r12
0x140015727  push    r14
0x140015729  push    r15
0x14001572b  lea     rbp, [rsp-1C0h]
0x140015733  sub     rsp, 2C0h
0x14001573a  mov     rax, cs:__security_cookie
0x140015741  xor     rax, rsp
0x140015744  mov     [rbp+1F0h+var_40], rax
0x14001574b  mov     rdi, r9
0x14001574e  mov     r15, r8
0x140015751  mov     rsi, rdx
0x140015754  lea     rax, [rsp+2F0h+lpFileName]
0x140015759  mov     [rsp+2F0h+var_2B8], rax; unsigned int *
0x14001575e  mov     [rsp+2F0h+var_2C8], 3; REGSAM
0x140015766  mov     [rsp+2F0h+var_2D0], 0; DWORD
0x14001576e  lea     r8, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140015775  mov     r14, 0FFFFFFFF80000001h
0x14001577c  mov     rdx, r14; hKey
0x14001577f  mov     rcx, r9; this
0x140015782  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140015787  mov     ebx, eax
0x140015789  test    eax, eax
0x14001578b  jz      short loc_1400157CB
0x14001578d  lea     r14, WPP_GLOBAL_Control
0x140015794  mov     rcx, cs:WPP_GLOBAL_Control
0x14001579b  cmp     rcx, r14
0x14001579e  jz      short loc_1400157B7
0x1400157a0  test    byte ptr [rcx+1Ch], 8
0x1400157a4  jz      short loc_1400157B7
0x1400157a6  mov     edx, 29h ; ')'
0x1400157ab  mov     r9d, eax
0x1400157ae  mov     rcx, [rcx+10h]
0x1400157b2  call    WPP_SF_d
0x1400157b7  test    ebx, ebx
0x1400157b9  jle     short loc_1400157C4
0x1400157bb  movzx   ebx, bx
0x1400157be  or      ebx, 80070000h
0x1400157c4  mov     eax, ebx
0x1400157c6  jmp     loc_140015B6B
0x1400157cb  xorps   xmm0, xmm0
0x1400157ce  movdqu  [rsp+2F0h+var_280], xmm0
0x1400157d4  mov     [rbp+1F0h+var_270], 0
0x1400157dc  xorps   xmm1, xmm1
0x1400157df  movdqu  [rbp+1F0h+var_268], xmm1
0x1400157e4  mov     [rbp+1F0h+var_258], 0Ah
0x1400157eb  mov     rax, [rsi]
0x1400157ee  mov     [rsp+2F0h+lpFileName], rax
0x1400157f3  test    rax, rax
0x1400157f6  jz      short loc_140015828
0x1400157f8  lea     rdx, [rsp+2F0h+lpFileName]
0x1400157fd  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x140015802  mov     rbx, rax
0x140015805  mov     rcx, [rax]; unsigned __int16 *
0x140015808  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x14001580d  cmp     dword ptr [rax+50h], 1
0x140015811  jz      short loc_140015820
0x140015813  mov     rdx, [rbx]
0x140015816  lea     rcx, [rsp+2F0h+var_280]
0x14001581b  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x140015820  cmp     [rsp+2F0h+lpFileName], 0
0x140015826  jnz     short loc_1400157F8
0x140015828  lea     rcx, [rsp+2F0h+lpFileName]
0x14001582d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x140015832  lea     rdx, [rsp+2F0h+var_280]
0x140015837  lea     rcx, [rsp+2F0h+lpFileName]
0x14001583c  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x140015841  mov     rbx, [rsp+2F0h+lpFileName]
0x140015846  mov     r8, rbx; unsigned __int16 *
0x140015849  lea     rdx, ?_configuration@StartList@@0PAGA; "Configuration"
0x140015850  mov     rcx, rdi; this
0x140015853  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x140015858  mov     edi, eax
0x14001585a  test    eax, eax
0x14001585c  jz      short loc_14001589B
0x14001585e  lea     r14, WPP_GLOBAL_Control
0x140015865  mov     rcx, cs:WPP_GLOBAL_Control
0x14001586c  cmp     rcx, r14
0x14001586f  jz      short loc_140015888
0x140015871  test    byte ptr [rcx+1Ch], 8
0x140015875  jz      short loc_140015888
0x140015877  mov     edx, 2Ah ; '*'
0x14001587c  mov     r9d, eax
0x14001587f  mov     rcx, [rcx+10h]
0x140015883  call    WPP_SF_d
0x140015888  test    edi, edi
0x14001588a  jle     loc_140015917
0x140015890  movzx   edi, di
0x140015893  or      edi, 80070000h
0x140015899  jmp     short loc_140015917
0x14001589b  mov     [rsp+2F0h+var_298], 0
0x1400158a4  mov     [rsp+2F0h+var_290], 0
0x1400158ad  mov     [rsp+2F0h+var_288], 0
0x1400158b6  mov     r9d, 20019h; unsigned int
0x1400158bc  lea     r8, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400158c3  mov     rdx, r14; hKey
0x1400158c6  lea     rcx, [rsp+2F0h+var_298]; this
0x1400158cb  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400158d0  mov     edi, eax
0x1400158d2  test    eax, eax
0x1400158d4  jz      short loc_140015925
0x1400158d6  lea     r14, WPP_GLOBAL_Control
0x1400158dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400158e4  cmp     rcx, r14
0x1400158e7  jz      short loc_140015900
0x1400158e9  test    byte ptr [rcx+1Ch], 8
0x1400158ed  jz      short loc_140015900
0x1400158ef  mov     edx, 2Bh ; '+'
0x1400158f4  mov     r9d, eax
0x1400158f7  mov     rcx, [rcx+10h]
0x1400158fb  call    WPP_SF_d
0x140015900  test    edi, edi
0x140015902  jle     short loc_14001590D
0x140015904  movzx   edi, di
0x140015907  or      edi, 80070000h
0x14001590d  lea     rcx, [rsp+2F0h+var_298]; this
0x140015912  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140015917  lea     rcx, [rbx-18h]; this
0x14001591b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140015920  jmp     loc_140015B5F
0x140015925  xor     edx, edx; Val
0x140015927  mov     r8d, 208h; Size
0x14001592d  lea     rcx, [rbp+1F0h+var_250]; void *
0x140015931  call    memset_0
0x140015936  mov     dword ptr [rsp+2F0h+lpFileName], 104h
0x14001593e  lea     r9, [rsp+2F0h+lpFileName]; unsigned int *
0x140015943  lea     r8, [rbp+1F0h+var_250]; unsigned __int16 *
0x140015947  lea     rdx, aStartup; "Startup"
0x14001594e  lea     rcx, [rsp+2F0h+var_298]; this
0x140015953  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x140015958  lea     rdx, [rbp+1F0h+var_250]
0x14001595c  lea     rcx, [rsp+2F0h+lpFileName]
0x140015961  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140015966  lea     rdx, [rbp+1F0h+var_250]
0x14001596a  lea     rcx, [rsp+2F0h+var_2A8]
0x14001596f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140015974  lea     rdx, [rbp+1F0h+var_250]
0x140015978  lea     rcx, [rsp+2F0h+var_2A0]
0x14001597d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140015982  mov     r8d, 17h
0x140015988  lea     rdx, aOnScreenKeyboa; "\\On-Screen Keyboard.lnk"
0x14001598f  lea     rcx, [rsp+2F0h+lpFileName]
0x140015994  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x140015999  mov     r8d, 0Dh
0x14001599f  lea     rdx, aNarratorLnk; "\\Narrator.lnk"
0x1400159a6  lea     rcx, [rsp+2F0h+var_2A8]
0x1400159ab  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400159b0  mov     r8d, 0Eh
0x1400159b6  lea     rdx, aMagnifierLnk; "\\Magnifier.lnk"
0x1400159bd  lea     rcx, [rsp+2F0h+var_2A0]
0x1400159c2  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400159c7  lea     r12, [rbx-18h]
0x1400159cb  mov     rdi, [r15]
0x1400159ce  add     rdi, 0FFFFFFFFFFFFFFE8h
0x1400159d2  cmp     r12, rdi
0x1400159d5  jz      short loc_140015A11
0x1400159d7  cmp     dword ptr [rdi+10h], 0
0x1400159db  jl      short loc_140015A02
0x1400159dd  mov     rax, [rdi]
0x1400159e0  cmp     [r12], rax
0x1400159e4  jnz     short loc_140015A02
0x1400159e6  mov     rcx, r12
0x1400159e9  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1400159ee  mov     rbx, rax
0x1400159f1  mov     rcx, rdi; this
0x1400159f4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400159f9  lea     rax, [rbx+18h]
0x1400159fd  mov     [r15], rax
0x140015a00  jmp     short loc_140015A11
0x140015a02  mov     r8d, [rbx-10h]
0x140015a06  mov     rdx, rbx
0x140015a09  mov     rcx, r15
0x140015a0c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140015a11  mov     rsi, [rsp+2F0h+lpFileName]
0x140015a16  mov     rcx, rsi; lpFileName
0x140015a19  call    cs:__imp_GetFileAttributesW
0x140015a20  nop     dword ptr [rax+rax+00h]
0x140015a25  lea     r14, WPP_GLOBAL_Control
0x140015a2c  or      ebx, 0FFFFFFFFh
0x140015a2f  cmp     eax, ebx
0x140015a31  jz      short loc_140015A77
0x140015a33  mov     r8d, 4
0x140015a39  lea     rdx, aOsk_0; ",osk"
0x140015a40  mov     rcx, r15
0x140015a43  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x140015a48  mov     rcx, rsi; lpFileName
0x140015a4b  call    cs:__imp_DeleteFileW
0x140015a52  nop     dword ptr [rax+rax+00h]
0x140015a57  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a5e  cmp     rcx, r14
0x140015a61  jz      short loc_140015A77
0x140015a63  test    byte ptr [rcx+1Ch], 10h
0x140015a67  jz      short loc_140015A77
0x140015a69  mov     edx, 2Ch ; ','
0x140015a6e  mov     rcx, [rcx+10h]
0x140015a72  call    WPP_SF_
0x140015a77  mov     rdi, [rsp+2F0h+var_2A8]
0x140015a7c  mov     rcx, rdi; lpFileName
0x140015a7f  call    cs:__imp_GetFileAttributesW
0x140015a86  nop     dword ptr [rax+rax+00h]
0x140015a8b  cmp     eax, ebx
0x140015a8d  jz      short loc_140015AD3
0x140015a8f  mov     r8d, 9
0x140015a95  lea     rdx, aNarrator_0; ",Narrator"
0x140015a9c  mov     rcx, r15
0x140015a9f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x140015aa4  mov     rcx, rdi; lpFileName
0x140015aa7  call    cs:__imp_DeleteFileW
0x140015aae  nop     dword ptr [rax+rax+00h]
0x140015ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x140015aba  cmp     rcx, r14
0x140015abd  jz      short loc_140015AD3
0x140015abf  test    byte ptr [rcx+1Ch], 10h
0x140015ac3  jz      short loc_140015AD3
0x140015ac5  mov     edx, 2Dh ; '-'
0x140015aca  mov     rcx, [rcx+10h]
0x140015ace  call    WPP_SF_
0x140015ad3  mov     rbx, [rsp+2F0h+var_2A0]
0x140015ad8  mov     rcx, rbx; lpFileName
0x140015adb  call    cs:__imp_GetFileAttributesW
0x140015ae2  nop     dword ptr [rax+rax+00h]
0x140015ae7  cmp     eax, 0FFFFFFFFh
0x140015aea  jz      short loc_140015B30
0x140015aec  mov     r8d, 0Eh
0x140015af2  lea     rdx, aMagnifierpane_0; ",magnifierpane"
0x140015af9  mov     rcx, r15
0x140015afc  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x140015b01  mov     rcx, rbx; lpFileName
0x140015b04  call    cs:__imp_DeleteFileW
0x140015b0b  nop     dword ptr [rax+rax+00h]
0x140015b10  mov     rcx, cs:WPP_GLOBAL_Control
0x140015b17  cmp     rcx, r14
0x140015b1a  jz      short loc_140015B30
0x140015b1c  test    byte ptr [rcx+1Ch], 10h
0x140015b20  jz      short loc_140015B30
0x140015b22  mov     edx, 2Eh ; '.'
0x140015b27  mov     rcx, [rcx+10h]
0x140015b2b  call    WPP_SF_
0x140015b30  lea     rcx, [rbx-18h]; this
0x140015b34  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140015b39  lea     rcx, [rdi-18h]; this
0x140015b3d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140015b42  lea     rcx, [rsi-18h]; this
0x140015b46  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140015b4b  lea     rcx, [rsp+2F0h+var_298]; this
0x140015b50  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140015b55  mov     rcx, r12; this
0x140015b58  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140015b5d  xor     edi, edi
0x140015b5f  lea     rcx, [rsp+2F0h+var_280]
0x140015b64  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x140015b69  mov     eax, edi
0x140015b6b  mov     rcx, [rbp+1F0h+var_40]
0x140015b72  xor     rcx, rsp; StackCookie
0x140015b75  call    __security_check_cookie
0x140015b7a  add     rsp, 2C0h
0x140015b81  pop     r15
0x140015b83  pop     r14
0x140015b85  pop     r12
0x140015b87  pop     rdi
0x140015b88  pop     rsi
0x140015b89  pop     rbx
0x140015b8a  pop     rbp
0x140015b8b  retn
```
