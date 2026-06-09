# PurchaseAppNotPresentTelemetry(uint,ushort const *,ushort const *)

- ea: `0x18001835c`
- end: `0x18001846b`
- name: `?PurchaseAppNotPresentTelemetry@@YAXIPEBG0@Z`
- size: `271`
- prototype: `void __fastcall(unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005914`

## callees

- `0x180001478`
- `0x180001958`
- `0x18001835c`

## string_xrefs

- `0x1800183d6`: `Purchase Appp Not Present. Using Legacy UI inplace of Smart Install dialog`
- `0x1800183a3`: `ShowSmartInstallAppRecommendation`

## pseudocode

```c
void __fastcall PurchaseAppNotPresentTelemetry(int a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  const wchar_t *v6; // [rsp+78h] [rbp+27h] BYREF
  const wchar_t *v7; // [rsp+80h] [rbp+2Fh] BYREF
  const WCHAR *v8; // [rsp+88h] [rbp+37h] BYREF
  const wchar_t *v9; // [rsp+90h] [rbp+3Fh] BYREF
  const wchar_t *v10; // [rsp+98h] [rbp+47h] BYREF
  __int64 v11; // [rsp+A0h] [rbp+4Fh] BYREF
  int v12; // [rsp+B8h] [rbp+67h] BYREF
  const unsigned __int16 *v13; // [rsp+C0h] [rbp+6Fh] BYREF
  const unsigned __int16 *v14; // [rsp+C8h] [rbp+77h] BYREF
  int v15; // [rsp+D0h] [rbp+7Fh] BYREF

  v14 = a3;
  v13 = a2;
  v12 = a1;
  if ( (unsigned int)dword_180038080 > 2 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_180038080, 0x800000000000LL) )
    {
      LOBYTE(v12) = 0;
      v6 = L"ShowSmartInstallAppRecommendation";
      LODWORD(v14) = 2533;
      v7 = L"shell\\shdocvw\\download.cpp";
      v8 = &Class;
      v9 = L"Purchase Appp Not Present. Using Legacy UI inplace of Smart Install dialog";
      v10 = L"PurchaseAppNotPresent";
      v11 = 0x80000000LL;
      LODWORD(v13) = 0;
      v15 = 3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v3,
        (unsigned int)byte_18002FD95,
        v4,
        v5,
        (__int64)&v11,
        (__int64)&v10,
        (__int64)&v9,
        (__int64)&v15,
        (__int64)&v8,
        (__int64)&v13,
        (__int64)&v14,
        (__int64)&v12,
        (__int64)&v7,
        (__int64)&v6);
    }
  }
}

```

## disassembly

```asm
0x18001835c  mov     rax, rsp
0x18001835f  mov     [rax+18h], r8
0x180018363  mov     [rax+10h], rdx
0x180018367  mov     [rax+8], ecx
0x18001836a  push    rbp
0x18001836b  lea     rbp, [rax-5Fh]
0x18001836f  sub     rsp, 0A0h
0x180018376  mov     eax, cs:dword_180038080
0x18001837c  cmp     eax, 2
0x18001837f  jbe     loc_180018462
0x180018385  mov     rdx, 800000000000h
0x18001838f  lea     rcx, dword_180038080
0x180018396  call    _tlgKeywordOn
0x18001839b  test    al, al
0x18001839d  jz      loc_180018462
0x1800183a3  lea     rax, aShowsmartinsta; "ShowSmartInstallAppRecommendation"
0x1800183aa  mov     byte ptr [rbp+57h+arg_0], 0
0x1800183ae  mov     [rbp+57h+var_30], rax
0x1800183b2  lea     rdx, byte_18002FD95
0x1800183b9  lea     rax, aShellShdocvwDo; "shell\\shdocvw\\download.cpp"
0x1800183c0  mov     dword ptr [rbp+57h+arg_10], 9E5h
0x1800183c7  mov     [rbp+57h+var_28], rax
0x1800183cb  lea     rax, Class
0x1800183d2  mov     [rbp+57h+var_20], rax
0x1800183d6  lea     rax, aPurchaseApppNo; "Purchase Appp Not Present. Using Legacy"...
0x1800183dd  mov     [rbp+57h+var_18], rax
0x1800183e1  lea     rax, aPurchaseappnot; "PurchaseAppNotPresent"
0x1800183e8  mov     [rbp+57h+var_10], rax
0x1800183ec  mov     eax, 80000000h
0x1800183f1  mov     [rbp+57h+var_8], rax
0x1800183f5  lea     rax, [rbp+57h+var_30]
0x1800183f9  mov     [rsp+68h], rax
0x1800183fe  lea     rax, [rbp+57h+var_28]
0x180018402  mov     [rsp+0A0h+var_40], rax
0x180018407  lea     rax, [rbp+57h+arg_0]
0x18001840b  mov     [rsp+0A0h+var_48], rax
0x180018410  lea     rax, [rbp+57h+arg_10]
0x180018414  mov     [rsp+0A0h+var_50], rax
0x180018419  lea     rax, [rbp+57h+arg_8]
0x18001841d  mov     [rsp+0A0h+var_58], rax
0x180018422  lea     rax, [rbp+57h+var_20]
0x180018426  mov     [rsp+0A0h+var_60], rax
0x18001842b  lea     rax, [rbp+57h+arg_18]
0x18001842f  mov     [rsp+0A0h+var_68], rax
0x180018434  lea     rax, [rbp+57h+var_18]
0x180018438  mov     [rsp+0A0h+var_70], rax
0x18001843d  lea     rax, [rbp+57h+var_10]
0x180018441  mov     [rsp+0A0h+var_78], rax
0x180018446  lea     rax, [rbp+57h+var_8]
0x18001844a  mov     [rsp+0A0h+var_80], rax
0x18001844f  mov     dword ptr [rbp+57h+arg_8], 0
0x180018456  mov     [rbp+57h+arg_18], 3
0x18001845d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U2@U3@U3@U?$_tlgWrapperByVal@$00@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@455AEBU?$_tlgWrapperByVal@$00@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180018462  add     rsp, 0A0h
0x180018469  pop     rbp
0x18001846a  retn
```
