# SendTimezoneChangeToast(ushort const *,bool,unsigned __int64)

- ea: `0x1800169f8`
- end: `0x180016bba`
- name: `?SendTimezoneChangeToast@@YAXPEBG_N_K@Z`
- size: `450`
- prototype: `void __fastcall(const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180014ec0`

## callees

- `0x18000166c`
- `0x18000173c`
- `0x1800018fc`
- `0x180015ea8`
- `0x180015f68`
- `0x180016880`
- `0x1800169f8`
- `0x180016bc0`
- `0x180016d18`

## string_xrefs

- `0x180016a41`: `Using low confidence data detected time zone matches the previously cached time zone. Skip sending notification.`

## pseudocode

```c
void __fastcall SendTimezoneChangeToast(const unsigned __int16 *a1, bool a2, unsigned __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int v11; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int *v15; // rdx
  int v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // eax
  int updated; // eax
  const unsigned __int16 *v22; // [rsp+40h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+48h] [rbp-10h] BYREF
  const wchar_t *v24; // [rsp+98h] [rbp+40h] BYREF

  if ( MatchesCachedTimeZone(a1) && a2 )
  {
    if ( (unsigned int)dword_180030000 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7) )
      {
        v22 = a1;
        v24 = L"Using low confidence data detected time zone matches the previously cached time zone. Skip sending notification.";
        v23[0] = 16779264;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v8,
          (unsigned int)&byte_180029F6F,
          v9,
          v10,
          (__int64)v23,
          (__int64)&v22,
          (__int64)&v24);
      }
    }
    return;
  }
  v11 = RegisterSystemToast(a3);
  if ( v11 < 0 )
  {
    if ( (unsigned int)dword_180030000 <= 5
      || !(unsigned __int8)tlgKeywordOn((unsigned int)dword_180030000, 0x200000000000LL, (unsigned int)v11) )
    {
      return;
    }
    v15 = &dword_18002A17C;
    goto LABEL_22;
  }
  v16 = PostSystemToast(a1, a2, a3);
  if ( v16 >= 0 )
  {
    updated = UpdateTimeZoneCache((const BYTE *)a1);
    if ( updated >= 0
      || (unsigned int)dword_180030000 <= 5
      || !(unsigned __int8)tlgKeywordOn((unsigned int)dword_180030000, 0x200000000000LL, (unsigned int)updated) )
    {
      return;
    }
    v15 = &dword_180029FE4;
LABEL_22:
    LODWORD(v24) = v13;
    v23[0] = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v12,
      (_DWORD)v15,
      v13,
      v14,
      (__int64)v23,
      (__int64)&v24);
    return;
  }
  if ( (unsigned int)dword_180030000 > 5
    && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180030000, 0x200000000000LL, (unsigned int)v16) )
  {
    LODWORD(v24) = v18;
    v23[0] = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)&unk_18002A0D0,
      v18,
      v19,
      (__int64)v23,
      (__int64)&v24);
  }
  v20 = UnregisterSystemToast(a3);
  if ( v20 < 0
    && (unsigned int)dword_180030000 > 5
    && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180030000, 0x200000000000LL, (unsigned int)v20) )
  {
    v15 = (int *)word_18002A03A;
    goto LABEL_22;
  }
}

```

## disassembly

```asm
0x1800169f8  push    rbp
0x1800169fa  push    rbx
0x1800169fb  push    rsi
0x1800169fc  push    rdi
0x1800169fd  mov     rbp, rsp
0x180016a00  sub     rsp, 58h
0x180016a04  mov     rdi, r8
0x180016a07  mov     sil, dl
0x180016a0a  mov     rbx, rcx
0x180016a0d  call    ?MatchesCachedTimeZone@@YA_NPEBG@Z; MatchesCachedTimeZone(ushort const *)
0x180016a12  test    al, al
0x180016a14  jz      short loc_180016A84
0x180016a16  test    sil, sil
0x180016a19  jz      short loc_180016A84
0x180016a1b  mov     eax, cs:dword_180030000
0x180016a21  cmp     eax, 5
0x180016a24  jbe     loc_180016BB1
0x180016a2a  mov     rdx, 400000000000h
0x180016a34  call    _tlgKeywordOn
0x180016a39  test    al, al
0x180016a3b  jz      loc_180016BB1
0x180016a41  lea     rax, aUsingLowConfid; "Using low confidence data detected time"...
0x180016a48  mov     [rbp+var_18], rbx
0x180016a4c  mov     [rbp+arg_18], rax
0x180016a50  lea     rdx, byte_180029F6F
0x180016a57  lea     rax, [rbp+arg_18]
0x180016a5b  mov     [rbp+var_10], 1000800h
0x180016a63  mov     [rsp+58h+var_28], rax
0x180016a68  lea     rax, [rbp+var_18]
0x180016a6c  mov     [rsp+58h+var_30], rax
0x180016a71  lea     rax, [rbp+var_10]
0x180016a75  mov     [rsp+58h+var_38], rax
0x180016a7a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180016a7f  jmp     loc_180016BB1
0x180016a84  mov     rcx, rdi; unsigned __int64
0x180016a87  call    ?RegisterSystemToast@@YAJ_K@Z; RegisterSystemToast(unsigned __int64)
0x180016a8c  mov     r8d, eax
0x180016a8f  test    eax, eax
0x180016a91  jns     short loc_180016AC5
0x180016a93  mov     ecx, cs:dword_180030000
0x180016a99  cmp     ecx, 5
0x180016a9c  jbe     loc_180016BB1
0x180016aa2  mov     rdx, 200000000000h
0x180016aac  call    _tlgKeywordOn
0x180016ab1  test    al, al
0x180016ab3  jz      loc_180016BB1
0x180016ab9  lea     rdx, dword_18002A17C
0x180016ac0  jmp     loc_180016B8D
0x180016ac5  mov     r8, rdi; unsigned __int64
0x180016ac8  mov     dl, sil; bool
0x180016acb  mov     rcx, rbx; unsigned __int16 *
0x180016ace  call    ?PostSystemToast@@YAJPEBG_N_K@Z; PostSystemToast(ushort const *,bool,unsigned __int64)
0x180016ad3  mov     r8d, eax
0x180016ad6  test    eax, eax
0x180016ad8  jns     short loc_180016B59
0x180016ada  mov     ecx, cs:dword_180030000
0x180016ae0  mov     ebx, 1000000h
0x180016ae5  cmp     ecx, 5
0x180016ae8  jbe     short loc_180016B23
0x180016aea  mov     rdx, 200000000000h
0x180016af4  call    _tlgKeywordOn
0x180016af9  test    al, al
0x180016afb  jz      short loc_180016B23
0x180016afd  lea     rax, [rbp+arg_18]
0x180016b01  mov     dword ptr [rbp+arg_18], r8d
0x180016b05  mov     [rsp+58h+var_30], rax
0x180016b0a  lea     rdx, unk_18002A0D0
0x180016b11  lea     rax, [rbp+var_10]
0x180016b15  mov     [rbp+var_10], rbx
0x180016b19  mov     [rsp+58h+var_38], rax
0x180016b1e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180016b23  mov     rcx, rdi; unsigned __int64
0x180016b26  call    ?UnregisterSystemToast@@YAJ_K@Z; UnregisterSystemToast(unsigned __int64)
0x180016b2b  mov     r8d, eax
0x180016b2e  test    eax, eax
0x180016b30  jns     short loc_180016BB1
0x180016b32  mov     ecx, cs:dword_180030000
0x180016b38  cmp     ecx, 5
0x180016b3b  jbe     short loc_180016BB1
0x180016b3d  mov     rdx, 200000000000h
0x180016b47  call    _tlgKeywordOn
0x180016b4c  test    al, al
0x180016b4e  jz      short loc_180016BB1
0x180016b50  lea     rdx, word_18002A03A
0x180016b57  jmp     short loc_180016B92
0x180016b59  mov     rcx, rbx; unsigned __int16 *
0x180016b5c  call    ?UpdateTimeZoneCache@@YAJPEBG@Z; UpdateTimeZoneCache(ushort const *)
0x180016b61  mov     r8d, eax
0x180016b64  test    eax, eax
0x180016b66  jns     short loc_180016BB1
0x180016b68  mov     ecx, cs:dword_180030000
0x180016b6e  cmp     ecx, 5
0x180016b71  jbe     short loc_180016BB1
0x180016b73  mov     rdx, 200000000000h
0x180016b7d  call    _tlgKeywordOn
0x180016b82  test    al, al
0x180016b84  jz      short loc_180016BB1
0x180016b86  lea     rdx, dword_180029FE4
0x180016b8d  mov     ebx, 1000000h
0x180016b92  lea     rax, [rbp+arg_18]
0x180016b96  mov     [rsp+58h+var_30], rax
0x180016b9b  lea     rax, [rbp+var_10]
0x180016b9f  mov     [rsp+58h+var_38], rax
0x180016ba4  mov     dword ptr [rbp+arg_18], r8d
0x180016ba8  mov     [rbp+var_10], rbx
0x180016bac  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180016bb1  add     rsp, 58h
0x180016bb5  pop     rdi
0x180016bb6  pop     rsi
0x180016bb7  pop     rbx
0x180016bb8  pop     rbp
0x180016bb9  retn
```
