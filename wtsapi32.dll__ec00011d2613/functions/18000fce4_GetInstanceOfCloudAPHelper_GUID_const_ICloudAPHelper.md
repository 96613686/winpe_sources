# GetInstanceOfCloudAPHelper(_GUID const &,ICloudAPHelper * *)

- ea: `0x18000fce4`
- end: `0x18000feba`
- name: `?GetInstanceOfCloudAPHelper@@YAJAEBU_GUID@@PEAPEAVICloudAPHelper@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(const struct _GUID *, struct ICloudAPHelper **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c010`

## callees

- `0x1800013bc`
- `0x1800014c4`
- `0x180007a64`
- `0x18000fce4`
- `0x1800104b0`
- `0x180016010`

## string_xrefs

- `0x18000fe57`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`

## pseudocode

```c
__int64 __fastcall GetInstanceOfCloudAPHelper(const struct _GUID *a1, struct ICloudAPHelper **a2)
{
  CloudAPHelper *v4; // rax
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  CloudAPHelper *v8; // rbx
  int v9; // eax
  int v10; // r8d
  int v11; // r9d
  unsigned int v12; // edi
  const char *v14; // [rsp+50h] [rbp-20h] BYREF
  const char *v15; // [rsp+58h] [rbp-18h] BYREF
  const char *v16; // [rsp+60h] [rbp-10h] BYREF
  const char *v17; // [rsp+68h] [rbp-8h] BYREF
  int v18; // [rsp+A0h] [rbp+30h] BYREF
  const char *v19; // [rsp+A8h] [rbp+38h] BYREF

  v4 = (CloudAPHelper *)operator new(0x98u);
  v8 = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = &ICloudAPHelper::`vftable';
    *((_QWORD *)v4 + 3) = "CloudAPHelper";
    *((_QWORD *)v4 + 1) = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v4 + 2) = &CTSUnknown::`vftable'{for `CTSObject'};
    *((_DWORD *)v4 + 8) = -607474739;
    *((_DWORD *)v4 + 9) = 1;
    *((_DWORD *)v4 + 12) = 0;
    *((_QWORD *)v4 + 5) = (char *)v4 + 8;
    *((_QWORD *)v4 + 1) = &CloudAPHelper::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v4 + 2) = &CloudAPHelper::`vftable'{for `CTSObject'};
    *(_QWORD *)v4 = &CloudAPHelper::`vftable';
    *((_QWORD *)v4 + 7) = 0;
    *((_QWORD *)v4 + 8) = 0;
    ValuesArray::AddRef(v4);
    v9 = CloudAPHelper::Initialize(v8, a1);
    v12 = v9;
    if ( v9 >= 0 )
    {
      *a2 = v8;
    }
    else
    {
      if ( (unsigned int)dword_18001F000 > 3 )
      {
        v18 = v9;
        v19 = "GetInstanceOfCloudAPHelper";
        v14 = "spCloudAPHelper->Initialize failed";
        v15 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          dword_18001F000,
          (unsigned int)byte_180019F9D,
          v10,
          v11,
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&v18,
          (__int64)&v19);
      }
      (*(void (__fastcall **)(CloudAPHelper *))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  else
  {
    v12 = -2147024882;
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v18 = 503;
      v15 = "CloudAPHelper allocation failed";
      LODWORD(v19) = -2147024882;
      v14 = "GetInstanceOfCloudAPHelper";
      v16 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v17 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)&byte_180019F4F,
        v6,
        v7,
        (__int64)&v17,
        (__int64)&v19,
        (__int64)&v16,
        (__int64)&v18,
        (__int64)&v14,
        (__int64)&v15);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18000fce4  mov     [rsp-18h+arg_0], rbx
0x18000fce9  push    rbp
0x18000fcea  push    rsi
0x18000fceb  push    rdi
0x18000fcec  mov     rbp, rsp
0x18000fcef  sub     rsp, 70h
0x18000fcf3  mov     rdi, rcx
0x18000fcf6  mov     rsi, rdx
0x18000fcf9  mov     ecx, 98h; Size
0x18000fcfe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fd03  mov     rbx, rax
0x18000fd06  test    rax, rax
0x18000fd09  jz      loc_18000FE20
0x18000fd0f  lea     r8, [rbx+8]
0x18000fd13  mov     rcx, rbx
0x18000fd16  lea     rdx, ??_7CloudAPHelper@@6B@; const CloudAPHelper::`vftable'
0x18000fd1d  lea     rax, ??_7ICloudAPHelper@@6B@; const ICloudAPHelper::`vftable'
0x18000fd24  mov     [rbx], rax
0x18000fd27  lea     rax, aCloudaphelper; "CloudAPHelper"
0x18000fd2e  mov     [r8+10h], rax
0x18000fd32  lea     rax, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x18000fd39  mov     [r8], rax
0x18000fd3c  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x18000fd43  mov     [r8+8], rax
0x18000fd47  lea     rax, ??_7CloudAPHelper@@6BINonDelegatingUnknown@@@; const CloudAPHelper::`vftable'{for `INonDelegatingUnknown'}
0x18000fd4e  mov     dword ptr [r8+18h], 0DBCAABCDh
0x18000fd56  mov     dword ptr [r8+1Ch], 1
0x18000fd5e  mov     dword ptr [r8+28h], 0
0x18000fd66  mov     [r8+20h], r8
0x18000fd6a  mov     [r8], rax
0x18000fd6d  lea     rax, ??_7CloudAPHelper@@6BCTSObject@@@; const CloudAPHelper::`vftable'{for `CTSObject'}
0x18000fd74  mov     [rbx+10h], rax
0x18000fd78  mov     rax, [rdx+8]
0x18000fd7c  mov     [rbx], rdx
0x18000fd7f  mov     qword ptr [rbx+38h], 0
0x18000fd87  mov     qword ptr [rbx+40h], 0
0x18000fd8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd94  mov     rdx, rdi; struct _GUID *
0x18000fd97  mov     rcx, rbx; this
0x18000fd9a  call    ?Initialize@CloudAPHelper@@QEAAJAEBU_GUID@@@Z; CloudAPHelper::Initialize(_GUID const &)
0x18000fd9f  mov     edi, eax
0x18000fda1  test    eax, eax
0x18000fda3  jns     short loc_18000FE18
0x18000fda5  mov     ecx, cs:dword_18001F000
0x18000fdab  cmp     ecx, 3
0x18000fdae  jbe     short loc_18000FE04
0x18000fdb0  lea     rax, aGetinstanceofc; "GetInstanceOfCloudAPHelper"
0x18000fdb7  mov     [rbp+arg_10], edi
0x18000fdba  mov     [rbp+arg_18], rax
0x18000fdbe  lea     rdx, byte_180019F9D
0x18000fdc5  lea     rax, aSpcloudaphelpe; "spCloudAPHelper->Initialize failed"
0x18000fdcc  mov     [rbp+var_20], rax
0x18000fdd0  lea     rax, aWarningHresult; "Warning HResult failed"
0x18000fdd7  mov     [rbp+var_18], rax
0x18000fddb  lea     rax, [rbp+arg_18]
0x18000fddf  mov     [rsp+70h+var_38], rax
0x18000fde4  lea     rax, [rbp+arg_10]
0x18000fde8  mov     [rsp+70h+var_40], rax
0x18000fded  lea     rax, [rbp+var_20]
0x18000fdf1  mov     [rsp+70h+var_48], rax
0x18000fdf6  lea     rax, [rbp+var_18]
0x18000fdfa  mov     [rsp+70h+var_50], rax
0x18000fdff  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000fe04  mov     rax, [rbx]
0x18000fe07  mov     rcx, rbx
0x18000fe0a  mov     rax, [rax+10h]
0x18000fe0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe13  jmp     loc_18000FEA8
0x18000fe18  mov     [rsi], rbx
0x18000fe1b  jmp     loc_18000FEA8
0x18000fe20  mov     eax, cs:dword_18001F000
0x18000fe26  mov     edi, 8007000Eh
0x18000fe2b  cmp     eax, 2
0x18000fe2e  jbe     short loc_18000FEA8
0x18000fe30  lea     rax, aCloudaphelperA; "CloudAPHelper allocation failed"
0x18000fe37  mov     [rbp+arg_10], 1F7h
0x18000fe3e  mov     [rbp+var_18], rax
0x18000fe42  lea     rdx, byte_180019F4F
0x18000fe49  lea     rax, aGetinstanceofc; "GetInstanceOfCloudAPHelper"
0x18000fe50  mov     dword ptr [rbp+arg_18], edi
0x18000fe53  mov     [rbp+var_20], rax
0x18000fe57  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18000fe5e  mov     [rbp+var_10], rax
0x18000fe62  lea     rax, aErrorCondition; "Error condition failed"
0x18000fe69  mov     [rbp+var_8], rax
0x18000fe6d  lea     rax, [rbp+var_18]
0x18000fe71  mov     [rsp+70h+var_28], rax
0x18000fe76  lea     rax, [rbp+var_20]
0x18000fe7a  mov     [rsp+70h+var_30], rax
0x18000fe7f  lea     rax, [rbp+arg_10]
0x18000fe83  mov     [rsp+70h+var_38], rax
0x18000fe88  lea     rax, [rbp+var_10]
0x18000fe8c  mov     [rsp+70h+var_40], rax
0x18000fe91  lea     rax, [rbp+arg_18]
0x18000fe95  mov     [rsp+70h+var_48], rax
0x18000fe9a  lea     rax, [rbp+var_8]
0x18000fe9e  mov     [rsp+70h+var_50], rax
0x18000fea3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000fea8  mov     rbx, [rsp+70h+arg_0]
0x18000feb0  mov     eax, edi
0x18000feb2  add     rsp, 70h
0x18000feb6  pop     rdi
0x18000feb7  pop     rsi
0x18000feb8  pop     rbp
0x18000feb9  retn
```
