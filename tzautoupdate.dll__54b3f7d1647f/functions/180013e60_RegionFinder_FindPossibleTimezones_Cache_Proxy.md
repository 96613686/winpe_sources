# RegionFinder::FindPossibleTimezones(Cache::Proxy &)

- ea: `0x180013e60`
- end: `0x180014038`
- name: `?FindPossibleTimezones@RegionFinder@@UEAA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAVProxy@Cache@@@Z`
- size: `472`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800011e4`
- `0x18000166c`
- `0x1800018fc`
- `0x18000da78`
- `0x18000e968`
- `0x18000e9cc`
- `0x180013de0`
- `0x180013e60`
- `0x18001b150`

## import_xrefs

- `msvcrt!bsearch` at `0x180013ed9`
- `msvcrt!bsearch` at `0x180013ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fc6`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x180013e98`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x180013e98`

## pseudocode

```c
_QWORD *__fastcall RegionFinder::FindPossibleTimezones(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  _QWORD *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  signed int LastError; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v17; // [rsp+30h] [rbp-29h] BYREF
  WCHAR *v18; // [rsp+38h] [rbp-21h] BYREF
  __int128 v19; // [rsp+40h] [rbp-19h] BYREF
  __int64 v20; // [rsp+50h] [rbp-9h]
  WCHAR *Key; // [rsp+60h] [rbp+7h] BYREF
  __int128 v22; // [rsp+68h] [rbp+Fh]
  _QWORD v23[4]; // [rsp+78h] [rbp+1Fh] BYREF
  WCHAR geoName[4]; // [rsp+98h] [rbp+3Fh] BYREF

  v17 = (__int64)a2;
  *(_QWORD *)geoName = 0;
  if ( !GetUserDefaultGeoName(geoName, 4) )
  {
    if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v18) = LastError;
      v17 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v13,
        (__int64)byte_1800299B3,
        v14,
        v15,
        (__int64)&v17,
        (__int64)&v18);
    }
    goto LABEL_12;
  }
  v22 = 0;
  Key = geoName;
  v5 = bsearch(&Key, off_18001EE00, 0xFAu, 0x18u, GeoTimeZone_bsearch_callback);
  if ( !v5 )
  {
    if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7) )
    {
      v18 = geoName;
      v17 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        v9,
        (__int64)byte_1800299FB,
        v10,
        v11,
        (__int64)&v17,
        (const unsigned __int16 **)&v18);
    }
LABEL_12:
    *a2 = 0;
    a2[1] = 0;
    a2[2] = 0;
    return a2;
  }
  v19 = 0;
  v20 = 0;
  v8 = std::wstring::wstring(v23, v5[1]);
  std::vector<std::wstring>::push_back(&v19, v8);
  std::wstring::_Tidy(v23, 1, 0);
  *(_OWORD *)a2 = v19;
  a2[2] = v20;
  v19 = 0;
  v20 = 0;
  std::vector<std::wstring>::_Tidy(&v19);
  return a2;
}

```

## disassembly

```asm
0x180013e60  mov     [rsp-8+arg_0], rbx
0x180013e65  push    rbp
0x180013e66  lea     rbp, [rsp-57h]
0x180013e6b  sub     rsp, 0B0h
0x180013e72  mov     rax, cs:__security_cookie
0x180013e79  xor     rax, rsp
0x180013e7c  mov     [rbp+57h+var_10], rax
0x180013e80  mov     rbx, rdx
0x180013e83  mov     [rbp+57h+var_80], rdx
0x180013e87  mov     qword ptr [rbp+57h+geoName], 0
0x180013e8f  mov     edx, 4; geoNameCount
0x180013e94  lea     rcx, [rbp+57h+geoName]; geoName
0x180013e98  call    cs:__imp_GetUserDefaultGeoName
0x180013e9e  test    eax, eax
0x180013ea0  jz      loc_180013FA8
0x180013ea6  xorps   xmm0, xmm0
0x180013ea9  movdqu  [rbp+57h+var_48], xmm0
0x180013eae  lea     rax, [rbp+57h+geoName]
0x180013eb2  mov     [rbp+57h+Key], rax
0x180013eb6  lea     rax, ?GeoTimeZone_bsearch_callback@@YAHPEBX0@Z; GeoTimeZone_bsearch_callback(void const *,void const *)
0x180013ebd  mov     [rsp+0B0h+CompareFunction], rax; CompareFunction
0x180013ec2  mov     r9d, 18h; SizeOfElements
0x180013ec8  mov     r8d, 0FAh; NumOfElements
0x180013ece  lea     rdx, off_18001EE00; Base
0x180013ed5  lea     rcx, [rbp+57h+Key]; Key
0x180013ed9  call    cs:__imp_bsearch
0x180013edf  test    rax, rax
0x180013ee2  jz      short loc_180013F52
0x180013ee4  xorps   xmm0, xmm0
0x180013ee7  movdqu  [rbp+57h+var_70], xmm0
0x180013eec  mov     [rbp+57h+var_60], 0
0x180013ef4  mov     rdx, [rax+8]
0x180013ef8  lea     rcx, [rbp+57h+var_38]
0x180013efc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013f01  nop
0x180013f02  mov     rdx, rax
0x180013f05  lea     rcx, [rbp+57h+var_70]
0x180013f09  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x180013f0e  nop
0x180013f0f  xor     r8d, r8d
0x180013f12  mov     dl, 1
0x180013f14  lea     rcx, [rbp+57h+var_38]
0x180013f18  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013f1d  mov     rcx, qword ptr [rbp+57h+var_70]
0x180013f21  mov     [rbx], rcx
0x180013f24  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x180013f28  mov     [rbx+8], rcx
0x180013f2c  mov     rcx, [rbp+57h+var_60]
0x180013f30  mov     [rbx+10h], rcx
0x180013f34  xorps   xmm0, xmm0
0x180013f37  movdqu  [rbp+57h+var_70], xmm0
0x180013f3c  mov     [rbp+57h+var_60], 0
0x180013f44  lea     rcx, [rbp+57h+var_70]
0x180013f48  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180013f4d  jmp     loc_180014018
0x180013f52  mov     eax, cs:dword_180030000
0x180013f58  cmp     eax, 5
0x180013f5b  jbe     loc_180014001
0x180013f61  mov     rdx, 400000000000h
0x180013f6b  call    _tlgKeywordOn
0x180013f70  test    al, al
0x180013f72  jz      loc_180014001
0x180013f78  lea     rax, [rbp+57h+geoName]
0x180013f7c  mov     [rbp+57h+var_78], rax
0x180013f80  mov     [rbp+57h+var_80], 1000000h
0x180013f88  lea     rax, [rbp+57h+var_78]
0x180013f8c  mov     [rsp+0B0h+var_88], rax
0x180013f91  lea     rax, [rbp+57h+var_80]
0x180013f95  mov     [rsp+0B0h+CompareFunction], rax
0x180013f9a  lea     rdx, byte_1800299FB
0x180013fa1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180013fa6  jmp     short loc_180014001
0x180013fa8  mov     eax, cs:dword_180030000
0x180013fae  cmp     eax, 5
0x180013fb1  jbe     short loc_180014001
0x180013fb3  mov     rdx, 400000000000h
0x180013fbd  call    _tlgKeywordOn
0x180013fc2  test    al, al
0x180013fc4  jz      short loc_180014001
0x180013fc6  call    cs:__imp_GetLastError
0x180013fcc  test    eax, eax
0x180013fce  jle     short loc_180013FD8
0x180013fd0  movzx   eax, ax
0x180013fd3  or      eax, 80070000h
0x180013fd8  mov     dword ptr [rbp+57h+var_78], eax
0x180013fdb  mov     [rbp+57h+var_80], 1000000h
0x180013fe3  lea     rax, [rbp+57h+var_78]
0x180013fe7  mov     [rsp+0B0h+var_88], rax
0x180013fec  lea     rax, [rbp+57h+var_80]
0x180013ff0  mov     [rsp+0B0h+CompareFunction], rax
0x180013ff5  lea     rdx, byte_1800299B3
0x180013ffc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180014001  mov     qword ptr [rbx], 0
0x180014008  mov     qword ptr [rbx+8], 0
0x180014010  mov     qword ptr [rbx+10h], 0
0x180014018  mov     rax, rbx
0x18001401b  mov     rcx, [rbp+57h+var_10]
0x18001401f  xor     rcx, rsp; StackCookie
0x180014022  call    __security_check_cookie
0x180014027  mov     rbx, [rsp+0B0h+arg_0]
0x18001402f  add     rsp, 0B0h
0x180014036  pop     rbp
0x180014037  retn
```
