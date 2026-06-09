# CountryCodeFinder::FindPossibleTimezones(Cache::Proxy &)

- ea: `0x18000dc80`
- end: `0x18000ded4`
- name: `?FindPossibleTimezones@CountryCodeFinder@@UEAA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAVProxy@Cache@@@Z`
- size: `596`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800011e4`
- `0x18000166c`
- `0x18000173c`
- `0x180001838`
- `0x18000dc80`
- `0x18000dedc`
- `0x18000e25c`
- `0x18000e33c`
- `0x18000e968`
- `0x18000e9cc`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall CountryCodeFinder::FindPossibleTimezones(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  unsigned int *Value; // rax
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rdx
  int v9; // r8d
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rcx
  __int64 v13; // r8
  int v14; // r9d
  __int128 v15; // rdi
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  wchar_t *v19; // rax
  __int64 v21; // [rsp+40h] [rbp-29h] BYREF
  const wchar_t *v22; // [rsp+48h] [rbp-21h] BYREF
  int v23; // [rsp+50h] [rbp-19h] BYREF
  __int64 v24; // [rsp+58h] [rbp-11h] BYREF
  __int128 v25; // [rsp+60h] [rbp-9h] BYREF
  __int64 v26; // [rsp+70h] [rbp+7h]
  wchar_t Source[8]; // [rsp+80h] [rbp+17h] BYREF
  __int64 v28; // [rsp+90h] [rbp+27h]
  unsigned __int64 v29; // [rsp+98h] [rbp+2Fh]

  v21 = a2;
  v4 = a3 + 80;
  if ( *(_BYTE *)(*(_QWORD *)(a3 + 80) + 4LL) )
  {
    v29 = 7;
    v28 = 0;
    Source[0] = 0;
    Value = (unsigned int *)Cache::ValueProxy<int>::GetValue(a3 + 80);
    v6 = Iso3166CountryCodeFromMcc(*Value, (__int64)Source);
    if ( v6 >= 0 )
    {
      v25 = 0;
      v26 = 0;
      if ( (int)FindTimeZonesFromCountryCode(Source) < 0
        && (unsigned int)dword_180030000 > 5
        && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13) )
      {
        v21 = (__int64)L"CountryCodeFinder failed finding time zone";
        v22 = (const wchar_t *)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          v12,
          (int)byte_180028A8D,
          v13,
          v14,
          (__int64)&v22,
          (__int64)&v21);
      }
      v15 = v25;
      if ( (_QWORD)v25 == *((_QWORD *)&v25 + 1)
        && (unsigned int)dword_180030000 > 5
        && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13) )
      {
        v19 = Source;
        if ( v29 >= 8 )
          v19 = *(wchar_t **)Source;
        v21 = (__int64)v19;
        v22 = L"CountryCodeFinder missing country code";
        v24 = 16779264;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v16,
          (unsigned int)word_180028A2A,
          v17,
          v18,
          (__int64)&v24,
          (__int64)&v22,
          (__int64)&v21);
      }
      *(_OWORD *)a2 = v15;
      *(_QWORD *)(a2 + 16) = v26;
      v25 = 0;
      v26 = 0;
      std::vector<std::wstring>::_Tidy(&v25);
    }
    else
    {
      v8 = (unsigned int)dword_180030000;
      if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL, (unsigned int)v6) )
      {
        v23 = v9;
        LODWORD(v24) = *(_DWORD *)Cache::ValueProxy<int>::GetValue(v4);
        v22 = L"CountryCodeFinder failed converting mcc to country code";
        v21 = 16779264;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v24,
          (unsigned int)word_180028ADA,
          v10,
          v11,
          (__int64)&v21,
          (__int64)&v22,
          (__int64)&v24,
          (__int64)&v23);
      }
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_QWORD *)(a2 + 16) = 0;
    }
    LOBYTE(v8) = 1;
    std::wstring::_Tidy(Source, v8, 0);
  }
  else
  {
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_QWORD *)(a2 + 16) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18000dc80  mov     [rsp-8+arg_0], rbx
0x18000dc85  push    rbp
0x18000dc86  push    rsi
0x18000dc87  push    rdi
0x18000dc88  lea     rbp, [rsp-47h]
0x18000dc8d  sub     rsp, 0B0h
0x18000dc94  mov     rax, cs:__security_cookie
0x18000dc9b  xor     rax, rsp
0x18000dc9e  mov     [rbp+57h+var_20], rax
0x18000dca2  mov     rbx, rdx
0x18000dca5  mov     [rbp+57h+var_80], rdx
0x18000dca9  lea     rdi, [r8+50h]
0x18000dcad  mov     rcx, [rdi]
0x18000dcb0  cmp     byte ptr [rcx+4], 0
0x18000dcb4  jnz     short loc_18000DCD2
0x18000dcb6  mov     qword ptr [rdx], 0
0x18000dcbd  mov     qword ptr [rdx+8], 0
0x18000dcc5  mov     qword ptr [rdx+10h], 0
0x18000dccd  jmp     loc_18000DEB2
0x18000dcd2  mov     [rbp+57h+var_28], 7
0x18000dcda  mov     [rbp+57h+var_30], 0
0x18000dce2  xor     eax, eax
0x18000dce4  mov     [rbp+57h+Source], ax
0x18000dce8  mov     rcx, rdi
0x18000dceb  call    ?GetValue@?$ValueProxy@H@Cache@@QEBAAEBHXZ; Cache::ValueProxy<int>::GetValue(void)
0x18000dcf0  lea     rdx, [rbp+57h+Source]
0x18000dcf4  mov     ecx, [rax]
0x18000dcf6  call    ?Iso3166CountryCodeFromMcc@@YAJHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Iso3166CountryCodeFromMcc(int,std::wstring &)
0x18000dcfb  mov     r8d, eax
0x18000dcfe  test    eax, eax
0x18000dd00  jns     loc_18000DD94
0x18000dd06  mov     edx, cs:dword_180030000
0x18000dd0c  cmp     edx, 5
0x18000dd0f  jbe     short loc_18000DD78
0x18000dd11  mov     rdx, 400000000000h
0x18000dd1b  call    _tlgKeywordOn
0x18000dd20  test    al, al
0x18000dd22  jz      short loc_18000DD78
0x18000dd24  mov     [rbp+57h+var_70], r8d
0x18000dd28  mov     rcx, rdi
0x18000dd2b  call    ?GetValue@?$ValueProxy@H@Cache@@QEBAAEBHXZ; Cache::ValueProxy<int>::GetValue(void)
0x18000dd30  mov     ecx, [rax]
0x18000dd32  mov     dword ptr [rbp+57h+var_68], ecx
0x18000dd35  lea     rax, aCountrycodefin_1; "CountryCodeFinder failed converting mcc"...
0x18000dd3c  mov     [rbp+57h+var_78], rax
0x18000dd40  mov     [rbp+57h+var_80], 1000800h
0x18000dd48  lea     rax, [rbp+57h+var_70]
0x18000dd4c  mov     [rsp+0C0h+var_88], rax
0x18000dd51  lea     rax, [rbp+57h+var_68]
0x18000dd55  mov     [rsp+0C0h+var_90], rax
0x18000dd5a  lea     rax, [rbp+57h+var_78]
0x18000dd5e  mov     [rsp+0C0h+var_98], rax
0x18000dd63  lea     rax, [rbp+57h+var_80]
0x18000dd67  mov     [rsp+0C0h+var_A0], rax
0x18000dd6c  lea     rdx, word_180028ADA
0x18000dd73  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000dd78  mov     qword ptr [rbx], 0
0x18000dd7f  mov     qword ptr [rbx+8], 0
0x18000dd87  mov     qword ptr [rbx+10h], 0
0x18000dd8f  jmp     loc_18000DEA4
0x18000dd94  xorps   xmm0, xmm0
0x18000dd97  movdqu  [rbp+57h+var_60], xmm0
0x18000dd9c  mov     [rbp+57h+var_50], 0
0x18000dda4  lea     rdx, [rbp+57h+var_60]
0x18000dda8  lea     rcx, [rbp+57h+Source]; Source
0x18000ddac  call    ?FindTimeZonesFromCountryCode@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@Z; FindTimeZonesFromCountryCode(std::wstring const &,std::vector<std::wstring> &)
0x18000ddb1  test    eax, eax
0x18000ddb3  jns     short loc_18000DE04
0x18000ddb5  mov     eax, cs:dword_180030000
0x18000ddbb  cmp     eax, 5
0x18000ddbe  jbe     short loc_18000DE04
0x18000ddc0  mov     rdx, 400000000000h
0x18000ddca  call    _tlgKeywordOn
0x18000ddcf  test    al, al
0x18000ddd1  jz      short loc_18000DE04
0x18000ddd3  lea     rax, aCountrycodefin_0; "CountryCodeFinder failed finding time z"...
0x18000ddda  mov     [rbp+57h+var_80], rax
0x18000ddde  mov     [rbp+57h+var_78], 1000000h
0x18000dde6  lea     rax, [rbp+57h+var_80]
0x18000ddea  mov     [rsp+0C0h+var_98], rax
0x18000ddef  lea     rax, [rbp+57h+var_78]
0x18000ddf3  mov     [rsp+0C0h+var_A0], rax
0x18000ddf8  lea     rdx, byte_180028A8D
0x18000ddff  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000de04  mov     rdi, qword ptr [rbp+57h+var_60]
0x18000de08  mov     rsi, qword ptr [rbp+57h+var_60+8]
0x18000de0c  cmp     rdi, rsi
0x18000de0f  jnz     short loc_18000DE7B
0x18000de11  mov     eax, cs:dword_180030000
0x18000de17  cmp     eax, 5
0x18000de1a  jbe     short loc_18000DE7B
0x18000de1c  mov     rdx, 400000000000h
0x18000de26  call    _tlgKeywordOn
0x18000de2b  test    al, al
0x18000de2d  jz      short loc_18000DE7B
0x18000de2f  lea     rax, [rbp+57h+Source]
0x18000de33  cmp     [rbp+57h+var_28], 8
0x18000de38  cmovnb  rax, qword ptr [rbp+57h+Source]
0x18000de3d  mov     [rbp+57h+var_80], rax
0x18000de41  lea     rax, aCountrycodefin; "CountryCodeFinder missing country code"
0x18000de48  mov     [rbp+57h+var_78], rax
0x18000de4c  mov     [rbp+57h+var_68], 1000800h
0x18000de54  lea     rax, [rbp+57h+var_80]
0x18000de58  mov     [rsp+0C0h+var_90], rax
0x18000de5d  lea     rax, [rbp+57h+var_78]
0x18000de61  mov     [rsp+0C0h+var_98], rax
0x18000de66  lea     rax, [rbp+57h+var_68]
0x18000de6a  mov     [rsp+0C0h+var_A0], rax
0x18000de6f  lea     rdx, word_180028A2A
0x18000de76  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000de7b  mov     [rbx], rdi
0x18000de7e  mov     [rbx+8], rsi
0x18000de82  mov     rax, [rbp+57h+var_50]
0x18000de86  mov     [rbx+10h], rax
0x18000de8a  xorps   xmm0, xmm0
0x18000de8d  movdqu  [rbp+57h+var_60], xmm0
0x18000de92  mov     [rbp+57h+var_50], 0
0x18000de9a  lea     rcx, [rbp+57h+var_60]
0x18000de9e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000dea3  nop
0x18000dea4  xor     r8d, r8d
0x18000dea7  mov     dl, 1
0x18000dea9  lea     rcx, [rbp+57h+Source]
0x18000dead  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000deb2  mov     rax, rbx
0x18000deb5  mov     rcx, [rbp+57h+var_20]
0x18000deb9  xor     rcx, rsp; StackCookie
0x18000debc  call    __security_check_cookie
0x18000dec1  mov     rbx, [rsp+0C0h+arg_0]
0x18000dec9  add     rsp, 0B0h
0x18000ded0  pop     rdi
0x18000ded1  pop     rsi
0x18000ded2  pop     rbp
0x18000ded3  retn
```
