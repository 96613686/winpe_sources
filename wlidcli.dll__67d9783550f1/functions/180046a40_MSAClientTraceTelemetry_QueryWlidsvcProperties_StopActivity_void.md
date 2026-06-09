# MSAClientTraceTelemetry::QueryWlidsvcProperties::StopActivity(void)

- ea: `0x180046a40`
- end: `0x180046c6a`
- name: `?StopActivity@QueryWlidsvcProperties@MSAClientTraceTelemetry@@MEAAXXZ`
- size: `554`
- prototype: `void __fastcall(MSAClientTraceTelemetry::QueryWlidsvcProperties *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180001458`
- `0x1800017dc`
- `0x180045b38`
- `0x180045fc8`
- `0x180046a40`
- `0x180050bd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046c0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046c0a`

## pseudocode

```c
void __fastcall MSAClientTraceTelemetry::QueryWlidsvcProperties::StopActivity(
        MSAClientTraceTelemetry::QueryWlidsvcProperties *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const CHAR *v6; // rcx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  int v11; // ecx
  __int64 v12; // r9
  int v13; // [rsp+C0h] [rbp-80h] BYREF
  int v14; // [rsp+C4h] [rbp-7Ch] BYREF
  int v15; // [rsp+C8h] [rbp-78h] BYREF
  int v16; // [rsp+CCh] [rbp-74h] BYREF
  const CHAR *v17; // [rsp+D0h] [rbp-70h] BYREF
  const WCHAR *v18; // [rsp+D8h] [rbp-68h] BYREF
  const CHAR *v19; // [rsp+E0h] [rbp-60h] BYREF
  const WCHAR *v20; // [rsp+E8h] [rbp-58h] BYREF
  const CHAR *v21; // [rsp+F0h] [rbp-50h] BYREF
  const CHAR *v22; // [rsp+F8h] [rbp-48h] BYREF
  const WCHAR *v23; // [rsp+100h] [rbp-40h] BYREF
  const CHAR *v24; // [rsp+108h] [rbp-38h] BYREF
  const CHAR *v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  __int64 v27[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v28; // [rsp+150h] [rbp+10h] BYREF
  int v29; // [rsp+158h] [rbp+18h] BYREF
  __int64 v30; // [rsp+160h] [rbp+20h] BYREF
  int v31; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = MSAClientTraceTelemetry::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v6 = (const CHAR *)*((_QWORD *)v4 + 6);
      v19 = (const CHAR *)*((_QWORD *)v4 + 14);
      LODWORD(v30) = v4[26];
      v7 = *((_QWORD *)this + 34);
      v20 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v21 = (const CHAR *)*((_QWORD *)v4 + 11);
      v31 = v4[20];
      v22 = (const CHAR *)*((_QWORD *)v4 + 9);
      v13 = v4[8];
      v23 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v14 = *v4;
      v24 = (const CHAR *)*((_QWORD *)v4 + 16);
      v15 = v4[16];
      v25 = (const CHAR *)*((_QWORD *)v4 + 7);
      v16 = v4[2];
      v26 = 0x1000000;
      v27[0] = 0x1000000;
      v17 = v6;
      v28 = v4[17];
      v29 = v4[4];
      v18 = (const WCHAR *)*((_QWORD *)v4 + 15);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)byte_180085159,
        v7 + 8,
        (__int64)v5,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v16,
        &v25,
        (__int64)&v15,
        &v24,
        (__int64)&v14,
        &v23,
        (__int64)&v13,
        &v22,
        (__int64)&v31,
        &v21,
        &v20,
        (__int64)&v30,
        &v19,
        &v18,
        (__int64)&v29,
        (__int64)&v28,
        &v17);
    }
  }
  else
  {
    wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = MSAClientTraceTelemetry::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v11 = *(_DWORD *)(v10 + 72);
      v30 = 0x1000000;
      v29 = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (__int64)&byte_180085EB7,
        v10 + 8,
        v12,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180046a40  push    rbp
0x180046a42  push    rbx
0x180046a43  push    rdi
0x180046a44  lea     rbp, [rsp+10h]
0x180046a49  sub     rsp, 130h
0x180046a50  mov     rdi, [rcx+110h]
0x180046a57  mov     rbx, rcx
0x180046a5a  mov     eax, [rdi+48h]
0x180046a5d  test    eax, eax
0x180046a5f  jns     loc_180046BF6
0x180046a65  add     rdi, 50h ; 'P'
0x180046a69  cmp     eax, [rdi+8]
0x180046a6c  jnz     loc_180046BF6
0x180046a72  test    rdi, rdi
0x180046a75  jz      loc_180046BF6
0x180046a7b  call    ?zInternalStop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180046a80  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x180046a85  mov     r9, rax
0x180046a88  mov     ecx, [rax]
0x180046a8a  cmp     ecx, 5
0x180046a8d  jbe     loc_180046C58
0x180046a93  mov     rax, [rdi+70h]
0x180046a97  lea     rdx, byte_180085159
0x180046a9e  mov     rcx, [rdi+30h]
0x180046aa2  mov     [rbp+var_60], rax
0x180046aa6  mov     eax, [rdi+68h]
0x180046aa9  mov     dword ptr [rbp+arg_10], eax
0x180046aac  mov     rax, [rdi+60h]
0x180046ab0  mov     r8, [rbx+110h]
0x180046ab7  mov     [rbp+var_58], rax
0x180046abb  add     r8, 8
0x180046abf  mov     rax, [rdi+58h]
0x180046ac3  mov     [rbp+var_50], rax
0x180046ac7  mov     eax, [rdi+50h]
0x180046aca  mov     [rbp+arg_18], eax
0x180046acd  mov     rax, [rdi+48h]
0x180046ad1  mov     [rbp+var_48], rax
0x180046ad5  mov     eax, [rdi+20h]
0x180046ad8  mov     [rbp+var_80], eax
0x180046adb  mov     rax, [rdi+18h]
0x180046adf  mov     [rbp+var_40], rax
0x180046ae3  mov     eax, [rdi]
0x180046ae5  mov     [rbp+var_7C], eax
0x180046ae8  mov     rax, [rdi+80h]
0x180046aef  mov     [rbp+var_38], rax
0x180046af3  mov     eax, [rdi+40h]
0x180046af6  mov     [rbp+var_78], eax
0x180046af9  mov     rax, [rdi+38h]
0x180046afd  mov     [rbp+var_30], rax
0x180046b01  mov     eax, [rdi+8]
0x180046b04  mov     [rbp+var_74], eax
0x180046b07  mov     eax, 1000000h
0x180046b0c  mov     [rbp+var_28], rax
0x180046b10  mov     [rbp+var_20], rax
0x180046b14  lea     rax, [rbp+var_70]
0x180046b18  mov     [rsp+140h+var_90], rax
0x180046b20  lea     rax, [rbp+arg_0]
0x180046b24  mov     [rsp+140h+var_98], rax
0x180046b2c  lea     rax, [rbp+arg_8]
0x180046b30  mov     [rsp+140h+var_A0], rax
0x180046b38  lea     rax, [rbp+var_68]
0x180046b3c  mov     [rsp+140h+var_A8], rax
0x180046b44  lea     rax, [rbp+var_60]
0x180046b48  mov     [rsp+140h+var_B0], rax
0x180046b50  lea     rax, [rbp+arg_10]
0x180046b54  mov     [rsp+140h+var_B8], rax
0x180046b5c  lea     rax, [rbp+var_58]
0x180046b60  mov     [rsp+140h+var_C0], rax
0x180046b68  lea     rax, [rbp+var_50]
0x180046b6c  mov     [rsp+140h+var_C8], rax
0x180046b71  lea     rax, [rbp+arg_18]
0x180046b75  mov     [rsp+140h+var_D0], rax
0x180046b7a  lea     rax, [rbp+var_48]
0x180046b7e  mov     [rsp+140h+var_D8], rax
0x180046b83  lea     rax, [rbp+var_80]
0x180046b87  mov     [rsp+140h+var_E0], rax
0x180046b8c  lea     rax, [rbp+var_40]
0x180046b90  mov     [rsp+140h+var_E8], rax
0x180046b95  lea     rax, [rbp+var_7C]
0x180046b99  mov     [rsp+140h+var_F0], rax
0x180046b9e  lea     rax, [rbp+var_38]
0x180046ba2  mov     [rsp+140h+var_F8], rax
0x180046ba7  lea     rax, [rbp+var_78]
0x180046bab  mov     [rsp+140h+var_100], rax
0x180046bb0  lea     rax, [rbp+var_30]
0x180046bb4  mov     [rsp+140h+var_108], rax
0x180046bb9  lea     rax, [rbp+var_74]
0x180046bbd  mov     [rbp+var_70], rcx
0x180046bc1  mov     ecx, [rdi+44h]
0x180046bc4  mov     [rsp+140h+var_110], rax
0x180046bc9  lea     rax, [rbp+var_28]
0x180046bcd  mov     [rbp+arg_0], ecx
0x180046bd0  mov     ecx, [rdi+10h]
0x180046bd3  mov     [rbp+arg_8], ecx
0x180046bd6  mov     rcx, [rdi+78h]
0x180046bda  mov     [rsp+140h+var_118], rax
0x180046bdf  lea     rax, [rbp+var_20]
0x180046be3  mov     [rbp+var_68], rcx
0x180046be7  mov     rcx, r9
0x180046bea  mov     [rsp+140h+var_120], rax
0x180046bef  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180046bf4  jmp     short loc_180046C58
0x180046bf6  call    ?zInternalStop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180046bfb  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x180046c00  mov     rdi, rax
0x180046c03  mov     ecx, [rax]
0x180046c05  cmp     ecx, 5
0x180046c08  jbe     short loc_180046C58
0x180046c0a  call    cs:__imp_GetCurrentThreadId
0x180046c10  mov     r8, [rbx+110h]
0x180046c17  lea     rdx, byte_180085EB7
0x180046c1e  mov     [rbp+arg_0], eax
0x180046c21  mov     eax, 1000000h
0x180046c26  mov     ecx, [r8+48h]
0x180046c2a  add     r8, 8
0x180046c2e  mov     [rbp+arg_10], rax
0x180046c32  lea     rax, [rbp+arg_0]
0x180046c36  mov     [rsp+140h+var_110], rax
0x180046c3b  lea     rax, [rbp+arg_8]
0x180046c3f  mov     [rsp+140h+var_118], rax
0x180046c44  lea     rax, [rbp+arg_10]
0x180046c48  mov     [rbp+arg_8], ecx
0x180046c4b  mov     rcx, rdi
0x180046c4e  mov     [rsp+140h+var_120], rax
0x180046c53  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180046c58  mov     rcx, rbx
0x180046c5b  add     rsp, 130h
0x180046c62  pop     rdi
0x180046c63  pop     rbx
0x180046c64  pop     rbp
0x180046c65  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
