# SystemTimezoneSetter(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180014704`
- end: `0x1800149c8`
- name: `?SystemTimezoneSetter@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `708`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014ec0`
- `0x180015bd0`

## callees

- `0x1800010bc`
- `0x1800011e4`
- `0x18000166c`
- `0x18000173c`
- `0x180001ab0`
- `0x18000d048`
- `0x18000d07c`
- `0x1800145cc`
- `0x180014704`
- `0x18001b0f6`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SetDynamicTimeZoneInformation` at `0x18001486f`
- `api-ms-win-core-timezone-l1-1-0!SetDynamicTimeZoneInformation` at `0x1800148da`
- `api-ms-win-core-timezone-l1-1-0!SetDynamicTimeZoneInformation` at `0x18001486f`
- `api-ms-win-core-timezone-l1-1-0!SetDynamicTimeZoneInformation` at `0x1800148da`
- `api-ms-win-core-timezone-l1-1-0!GetDynamicTimeZoneInformation` at `0x18001474f`
- `api-ms-win-core-timezone-l1-1-0!GetDynamicTimeZoneInformation` at `0x18001474f`

## string_xrefs

- `0x180014952`: `Attempted to automatically set system time zone`

## pseudocode

```c
__int64 __fastcall SystemTimezoneSetter(_QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 result; // rax
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  unsigned __int16 *v13; // rcx
  BOOL v14; // edi
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  unsigned __int16 *v21; // rcx
  int v22; // r9d
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h] BYREF
  DYNAMIC_TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+60h] [rbp-A0h] BYREF
  struct _TIME_DYNAMIC_ZONE_INFORMATION pTimeZoneInformation; // [rsp+210h] [rbp+110h] BYREF

  memset_0(&pTimeZoneInformation, 0, sizeof(pTimeZoneInformation));
  if ( GetDynamicTimeZoneInformation(&pTimeZoneInformation) == -1 )
  {
    result = (unsigned int)dword_180030000;
    if ( (unsigned int)dword_180030000 > 5 )
    {
      result = tlgKeywordOn(v2, 0x400000000000LL, v3);
      if ( (_BYTE)result )
      {
        v28 = 0x1000000;
        v27 = L"Failed getting current system time zone";
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
                 v5,
                 (unsigned int)byte_180029D5B,
                 v6,
                 v7,
                 (__int64)&v28,
                 (__int64)&v27);
      }
    }
    return result;
  }
  result = std::operator==<unsigned short>(a1, pTimeZoneInformation.TimeZoneKeyName);
  if ( (_BYTE)result )
    return result;
  memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
  if ( (int)DynamicTimeZoneInformationFromTimeZoneKeyName(a1, &TimeZoneInformation) < 0 )
  {
    result = (unsigned int)dword_180030000;
    if ( (unsigned int)dword_180030000 > 5 )
    {
      result = tlgKeywordOn(v8, 0x400000000000LL, v9);
      if ( (_BYTE)result )
      {
        if ( a1[3] >= 8u )
          a1 = (_QWORD *)*a1;
        v28 = (__int64)a1;
        v27 = L"Failed getting DYNAMIC_TIME_ZONE_INFORMATION from key name";
        v26 = 16779264;
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                 v10,
                 (unsigned int)&unk_180029C68,
                 v11,
                 v12,
                 (__int64)&v26,
                 (__int64)&v27,
                 (__int64)&v28);
      }
    }
    return result;
  }
  v14 = SetDynamicTimeZoneInformation(&TimeZoneInformation);
  if ( !v14 )
  {
    if ( (int)ModifyPrivilegeState(v13, 1) < 0 )
    {
      result = (unsigned int)dword_180030000;
      if ( (unsigned int)dword_180030000 > 5 )
      {
        result = tlgKeywordOn(v16, 0x200000000000LL, v17);
        if ( (_BYTE)result )
        {
          v26 = 0x1000000;
          return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
                   v18,
                   (unsigned int)byte_180029B6B,
                   v19,
                   v20,
                   (__int64)&v26);
        }
      }
      return result;
    }
    v14 = SetDynamicTimeZoneInformation(&TimeZoneInformation);
    if ( (int)ModifyPrivilegeState(v21, 0) < 0
      && (unsigned int)dword_180030000 > 5
      && (unsigned __int8)tlgKeywordOn(v13, 0x200000000000LL, v15) )
    {
      v26 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        (_DWORD)v13,
        (unsigned int)&unk_180029D08,
        v15,
        v22,
        (__int64)&v26);
    }
  }
  result = (unsigned int)dword_180030000;
  if ( (unsigned int)dword_180030000 > 5 )
  {
    result = tlgKeywordOn(v13, 0x400000000000LL, v15);
    if ( (_BYTE)result )
    {
      if ( a1[3] >= 8u )
        a1 = (_QWORD *)*a1;
      v26 = (__int64)a1;
      v28 = (__int64)L"Attempted to automatically set system time zone";
      LODWORD(v27) = v14;
      v29 = 16779264;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
               v23,
               (unsigned int)byte_180029BBD,
               v24,
               v25,
               (__int64)&v29,
               (__int64)&v28,
               (__int64)&v27,
               (__int64)&v26);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014704  mov     [rsp-8+arg_8], rbx
0x180014709  mov     [rsp-8+arg_10], rdi
0x18001470e  push    rbp
0x18001470f  lea     rbp, [rsp-2D0h]
0x180014717  sub     rsp, 3D0h
0x18001471e  mov     rax, cs:__security_cookie
0x180014725  xor     rax, rsp
0x180014728  mov     [rbp+2D0h+var_10], rax
0x18001472f  mov     rbx, rcx
0x180014732  mov     edi, 1B0h
0x180014737  mov     r8d, edi; Size
0x18001473a  lea     rcx, [rbp+2D0h+pTimeZoneInformation]; void *
0x180014741  xor     edx, edx; Val
0x180014743  call    memset_0
0x180014748  lea     rcx, [rbp+2D0h+pTimeZoneInformation]; pTimeZoneInformation
0x18001474f  call    cs:__imp_GetDynamicTimeZoneInformation
0x180014755  cmp     eax, 0FFFFFFFFh
0x180014758  jnz     short loc_1800147BA
0x18001475a  mov     eax, cs:dword_180030000
0x180014760  cmp     eax, 5
0x180014763  jbe     loc_1800149A4
0x180014769  mov     rdx, 400000000000h
0x180014773  call    _tlgKeywordOn
0x180014778  test    al, al
0x18001477a  jz      loc_1800149A4
0x180014780  lea     rax, aFailedGettingC; "Failed getting current system time zone"
0x180014787  mov     [rsp+3D0h+var_380], 1000000h
0x180014790  mov     [rsp+3D0h+var_388], rax
0x180014795  lea     rdx, byte_180029D5B
0x18001479c  lea     rax, [rsp+3D0h+var_388]
0x1800147a1  mov     [rsp+3D0h+var_3A8], rax
0x1800147a6  lea     rax, [rsp+3D0h+var_380]
0x1800147ab  mov     [rsp+3D0h+var_3B0], rax
0x1800147b0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x1800147b5  jmp     loc_1800149A4
0x1800147ba  lea     rdx, [rbp+2D0h+pTimeZoneInformation.TimeZoneKeyName]
0x1800147c1  mov     rcx, rbx
0x1800147c4  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x1800147c9  test    al, al
0x1800147cb  jnz     loc_1800149A4
0x1800147d1  mov     r8, rdi; Size
0x1800147d4  lea     rcx, [rsp+3D0h+TimeZoneInformation]; void *
0x1800147d9  xor     edx, edx; Val
0x1800147db  call    memset_0
0x1800147e0  lea     rdx, [rsp+3D0h+TimeZoneInformation]
0x1800147e5  mov     rcx, rbx
0x1800147e8  call    ?DynamicTimeZoneInformationFromTimeZoneKeyName@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TIME_DYNAMIC_ZONE_INFORMATION@@@Z; DynamicTimeZoneInformationFromTimeZoneKeyName(std::wstring const &,_TIME_DYNAMIC_ZONE_INFORMATION *)
0x1800147ed  test    eax, eax
0x1800147ef  jns     short loc_18001486A
0x1800147f1  mov     eax, cs:dword_180030000
0x1800147f7  cmp     eax, 5
0x1800147fa  jbe     loc_1800149A4
0x180014800  mov     rdx, 400000000000h
0x18001480a  call    _tlgKeywordOn
0x18001480f  test    al, al
0x180014811  jz      loc_1800149A4
0x180014817  cmp     qword ptr [rbx+18h], 8
0x18001481c  jb      short loc_180014821
0x18001481e  mov     rbx, [rbx]
0x180014821  lea     rax, aFailedGettingD; "Failed getting DYNAMIC_TIME_ZONE_INFORM"...
0x180014828  mov     [rsp+3D0h+var_380], rbx
0x18001482d  mov     [rsp+3D0h+var_388], rax
0x180014832  lea     rdx, unk_180029C68
0x180014839  lea     rax, [rsp+3D0h+var_380]
0x18001483e  mov     [rsp+3D0h+var_390], 1000800h
0x180014847  mov     [rsp+3D0h+var_3A0], rax
0x18001484c  lea     rax, [rsp+3D0h+var_388]
0x180014851  mov     [rsp+3D0h+var_3A8], rax
0x180014856  lea     rax, [rsp+3D0h+var_390]
0x18001485b  mov     [rsp+3D0h+var_3B0], rax
0x180014860  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180014865  jmp     loc_1800149A4
0x18001486a  lea     rcx, [rsp+3D0h+TimeZoneInformation]; lpTimeZoneInformation
0x18001486f  call    cs:__imp_SetDynamicTimeZoneInformation
0x180014875  mov     edi, eax
0x180014877  test    eax, eax
0x180014879  jnz     loc_18001492A
0x18001487f  lea     edx, [rax+1]; int
0x180014882  call    ?ModifyPrivilegeState@@YAJPEAGH@Z; ModifyPrivilegeState(ushort *,int)
0x180014887  test    eax, eax
0x180014889  jns     short loc_1800148D5
0x18001488b  mov     eax, cs:dword_180030000
0x180014891  cmp     eax, 5
0x180014894  jbe     loc_1800149A4
0x18001489a  mov     rdx, 200000000000h
0x1800148a4  call    _tlgKeywordOn
0x1800148a9  test    al, al
0x1800148ab  jz      loc_1800149A4
0x1800148b1  lea     rax, [rsp+3D0h+var_390]
0x1800148b6  mov     [rsp+3D0h+var_390], 1000000h
0x1800148bf  lea     rdx, byte_180029B6B
0x1800148c6  mov     [rsp+3D0h+var_3B0], rax
0x1800148cb  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800148d0  jmp     loc_1800149A4
0x1800148d5  lea     rcx, [rsp+3D0h+TimeZoneInformation]; lpTimeZoneInformation
0x1800148da  call    cs:__imp_SetDynamicTimeZoneInformation
0x1800148e0  xor     edx, edx; int
0x1800148e2  mov     edi, eax
0x1800148e4  call    ?ModifyPrivilegeState@@YAJPEAGH@Z; ModifyPrivilegeState(ushort *,int)
0x1800148e9  test    eax, eax
0x1800148eb  jns     short loc_18001492A
0x1800148ed  mov     eax, cs:dword_180030000
0x1800148f3  cmp     eax, 5
0x1800148f6  jbe     short loc_18001492A
0x1800148f8  mov     rdx, 200000000000h
0x180014902  call    _tlgKeywordOn
0x180014907  test    al, al
0x180014909  jz      short loc_18001492A
0x18001490b  lea     rax, [rsp+3D0h+var_390]
0x180014910  mov     [rsp+3D0h+var_390], 1000000h
0x180014919  lea     rdx, unk_180029D08
0x180014920  mov     [rsp+3D0h+var_3B0], rax
0x180014925  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18001492a  mov     eax, cs:dword_180030000
0x180014930  cmp     eax, 5
0x180014933  jbe     short loc_1800149A4
0x180014935  mov     rdx, 400000000000h
0x18001493f  call    _tlgKeywordOn
0x180014944  test    al, al
0x180014946  jz      short loc_1800149A4
0x180014948  cmp     qword ptr [rbx+18h], 8
0x18001494d  jb      short loc_180014952
0x18001494f  mov     rbx, [rbx]
0x180014952  lea     rax, aAttemptedToAut; "Attempted to automatically set system t"...
0x180014959  mov     [rsp+3D0h+var_390], rbx
0x18001495e  mov     [rsp+3D0h+var_380], rax
0x180014963  lea     rdx, byte_180029BBD
0x18001496a  lea     rax, [rsp+3D0h+var_390]
0x18001496f  mov     dword ptr [rsp+3D0h+var_388], edi
0x180014973  mov     [rsp+3D0h+var_398], rax
0x180014978  lea     rax, [rsp+3D0h+var_388]
0x18001497d  mov     [rsp+3D0h+var_3A0], rax
0x180014982  lea     rax, [rsp+3D0h+var_380]
0x180014987  mov     [rsp+3D0h+var_3A8], rax
0x18001498c  lea     rax, [rsp+3D0h+var_378]
0x180014991  mov     [rsp+3D0h+var_3B0], rax
0x180014996  mov     [rsp+3D0h+var_378], 1000800h
0x18001499f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800149a4  mov     rcx, [rbp+2D0h+var_10]
0x1800149ab  xor     rcx, rsp; StackCookie
0x1800149ae  call    __security_check_cookie
0x1800149b3  lea     r11, [rsp+3D0h+var_s0]
0x1800149bb  mov     rbx, [r11+18h]
0x1800149bf  mov     rdi, [r11+20h]
0x1800149c3  mov     rsp, r11
0x1800149c6  pop     rbp
0x1800149c7  retn
```
