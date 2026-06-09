# CTSSyncWaitResult::WaitForCompletion(TSWaitType,ITSThread *)

- ea: `0x18003fa50`
- end: `0x18003fcac`
- name: `?WaitForCompletion@CTSSyncWaitResult@@QEAAJW4TSWaitType@@PEAVITSThread@@@Z`
- size: `604`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003d93c`

## callees

- `0x1800010b0`
- `0x1800011c8`
- `0x1800014c0`
- `0x18000abc0`
- `0x18003fa50`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003fa78`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003fc0a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003fa78`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003fc0a`

## string_xrefs

- `0x18003fb1d`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x18003fba2`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x18003fc60`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x18003fb04`: `WaitForCompletion`
- `0x18003fb89`: `WaitForCompletion`
- `0x18003fc47`: `WaitForCompletion`
- `0x18003fb2d`: `ThreadWaitForSingleObject timed out`
- `0x18003fbb2`: `ThreadWaitForSingleObject failed with 0x%x`

## pseudocode

```c
__int64 __fastcall CTSSyncWaitResult::WaitForCompletion(__int64 a1, unsigned int a2, __int64 a3)
{
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  int v9; // ebx
  int v11; // r8d
  int v12; // r9d
  __int64 *v13; // rdx
  const char **v14; // rax
  DWORD v15; // eax
  const char **v16; // [rsp+30h] [rbp-50h]
  const char **v17; // [rsp+40h] [rbp-40h]
  const char *v18; // [rsp+50h] [rbp-30h] BYREF
  const char *v19; // [rsp+58h] [rbp-28h] BYREF
  const char *v20; // [rsp+60h] [rbp-20h] BYREF
  const char *v21; // [rsp+68h] [rbp-18h] BYREF
  __int64 v22; // [rsp+70h] [rbp-10h] BYREF
  const char *v23; // [rsp+A0h] [rbp+20h] BYREF
  int v24; // [rsp+B8h] [rbp+38h] BYREF

  v22 = 0;
  if ( !WaitForSingleObject(*(HANDLE *)(a1 + 88), 0) )
  {
    if ( (unsigned int)dword_18005C008 > 5 )
    {
      v23 = "Event signaled, no need to wait";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v6,
        (unsigned int)&word_180055AD6,
        v7,
        v8,
        (__int64)&v23);
    }
    goto LABEL_4;
  }
  if ( a2 != 4 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)a3 + 72LL))(
           a3,
           *(_QWORD *)(a1 + 88),
           a2,
           0xFFFFFFFFLL);
    if ( v9 == -2092630012 )
    {
      if ( (unsigned int)dword_18005C008 > 2 )
      {
        LODWORD(v23) = 268;
        v18 = "WaitForCompletion";
        v19 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
        v20 = "ThreadWaitForSingleObject timed out";
        v24 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          -2147467259,
          (unsigned int)byte_180055A91,
          v11,
          v12,
          (__int64)&v20,
          (__int64)&v24,
          (__int64)&v19,
          (__int64)&v23,
          (__int64)&v18);
      }
      goto LABEL_5;
    }
    if ( v9 < 0 )
    {
      if ( (unsigned int)dword_18005C008 <= 2 )
        goto LABEL_5;
      v24 = 272;
      v20 = "WaitForCompletion";
      v13 = qword_180055A48;
      v19 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
      v21 = "ThreadWaitForSingleObject failed with 0x%x";
      v17 = &v20;
      v16 = &v19;
      v14 = &v21;
LABEL_13:
      LODWORD(v18) = -2147467259;
      LODWORD(v23) = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        -2147467259,
        (_DWORD)v13,
        v11,
        v12,
        (__int64)v14,
        (__int64)&v18,
        (__int64)v16,
        (__int64)&v24,
        (__int64)v17,
        (__int64)&v23);
      goto LABEL_5;
    }
LABEL_4:
    v9 = 0;
    goto LABEL_5;
  }
  v15 = WaitForSingleObject(*(HANDLE *)(a1 + 88), 0xFFFFFFFF);
  if ( !v15 )
    goto LABEL_4;
  if ( v15 == 128 )
  {
    v9 = -2092629814;
  }
  else
  {
    v9 = -2092629813;
    if ( v15 != 258 )
      v9 = -2147467259;
  }
  if ( (unsigned int)dword_18005C008 > 2 )
  {
    v24 = 287;
    v21 = "WaitForCompletion";
    v13 = (__int64 *)&byte_1800559FF;
    v20 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
    v19 = "PAL_System_SingleCondWait failed with 0x%x";
    v17 = &v21;
    v16 = &v20;
    v14 = &v19;
    goto LABEL_13;
  }
LABEL_5:
  TCntPtr<IDispatch>::SafeRelease(&v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003fa50  mov     [rsp-18h+arg_8], rbx
0x18003fa55  push    rbp
0x18003fa56  push    rsi
0x18003fa57  push    rdi
0x18003fa58  mov     rbp, rsp
0x18003fa5b  sub     rsp, 80h
0x18003fa62  mov     rsi, r8
0x18003fa65  mov     [rbp+var_10], 0
0x18003fa6d  mov     edi, edx
0x18003fa6f  mov     rbx, rcx
0x18003fa72  mov     rcx, [rcx+58h]; hHandle
0x18003fa76  xor     edx, edx; dwMilliseconds
0x18003fa78  call    cs:__imp_WaitForSingleObject
0x18003fa7e  test    eax, eax
0x18003fa80  jnz     short loc_18003FACD
0x18003fa82  mov     eax, cs:dword_18005C008
0x18003fa88  cmp     eax, 5
0x18003fa8b  jbe     short loc_18003FAAD
0x18003fa8d  lea     rax, aEventSignaledN; "Event signaled, no need to wait"
0x18003fa94  mov     [rbp+arg_0], rax
0x18003fa98  lea     rdx, word_180055AD6
0x18003fa9f  lea     rax, [rbp+arg_0]
0x18003faa3  mov     [rsp+80h+var_60], rax
0x18003faa8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003faad  xor     ebx, ebx
0x18003faaf  lea     rcx, [rbp+var_10]
0x18003fab3  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18003fab8  mov     eax, ebx
0x18003faba  mov     rbx, [rsp+80h+arg_8]
0x18003fac2  add     rsp, 80h
0x18003fac9  pop     rdi
0x18003faca  pop     rsi
0x18003facb  pop     rbp
0x18003facc  retn
0x18003facd  cmp     edi, 4
0x18003fad0  jz      loc_18003FC03
0x18003fad6  mov     rax, [rsi]
0x18003fad9  or      r9d, 0FFFFFFFFh
0x18003fadd  mov     rdx, [rbx+58h]
0x18003fae1  mov     r8d, edi
0x18003fae4  mov     rcx, rsi
0x18003fae7  mov     rax, [rax+48h]
0x18003faeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003faf0  mov     ebx, eax
0x18003faf2  cmp     eax, 83450004h
0x18003faf7  jnz     short loc_18003FB72
0x18003faf9  mov     ecx, cs:dword_18005C008
0x18003faff  cmp     ecx, 2
0x18003fb02  jbe     short loc_18003FAAF
0x18003fb04  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x18003fb0b  mov     dword ptr [rbp+arg_0], 10Ch
0x18003fb12  mov     [rbp+var_30], rax
0x18003fb16  lea     rdx, byte_180055A91
0x18003fb1d  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003fb24  mov     ecx, 80004005h
0x18003fb29  mov     [rbp+var_28], rax
0x18003fb2d  lea     rax, aThreadwaitfors_0; "ThreadWaitForSingleObject timed out"
0x18003fb34  mov     [rbp+var_20], rax
0x18003fb38  lea     rax, [rbp+var_30]
0x18003fb3c  mov     [rsp+80h+var_40], rax
0x18003fb41  lea     rax, [rbp+arg_0]
0x18003fb45  mov     [rsp+80h+var_48], rax
0x18003fb4a  lea     rax, [rbp+var_28]
0x18003fb4e  mov     [rsp+80h+var_50], rax
0x18003fb53  lea     rax, [rbp+arg_18]
0x18003fb57  mov     [rsp+80h+var_58], rax
0x18003fb5c  lea     rax, [rbp+var_20]
0x18003fb60  mov     [rsp+80h+var_60], rax
0x18003fb65  mov     [rbp+arg_18], ecx
0x18003fb68  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003fb6d  jmp     loc_18003FAAF
0x18003fb72  test    ebx, ebx
0x18003fb74  jns     loc_18003FAAD
0x18003fb7a  mov     eax, cs:dword_18005C008
0x18003fb80  cmp     eax, 2
0x18003fb83  jbe     loc_18003FAAF
0x18003fb89  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x18003fb90  mov     [rbp+arg_18], 110h
0x18003fb97  mov     [rbp+var_20], rax
0x18003fb9b  lea     rdx, qword_180055A48
0x18003fba2  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003fba9  mov     ecx, 80004005h
0x18003fbae  mov     [rbp+var_28], rax
0x18003fbb2  lea     rax, aThreadwaitfors; "ThreadWaitForSingleObject failed with 0"...
0x18003fbb9  mov     [rbp+var_18], rax
0x18003fbbd  lea     rax, [rbp+arg_0]
0x18003fbc1  mov     [rsp+80h+var_38], rax
0x18003fbc6  lea     rax, [rbp+var_20]
0x18003fbca  mov     [rsp+80h+var_40], rax
0x18003fbcf  lea     rax, [rbp+arg_18]
0x18003fbd3  mov     [rsp+80h+var_48], rax
0x18003fbd8  lea     rax, [rbp+var_28]
0x18003fbdc  mov     [rsp+80h+var_50], rax
0x18003fbe1  lea     rax, [rbp+var_30]
0x18003fbe5  mov     [rsp+80h+var_58], rax
0x18003fbea  lea     rax, [rbp+var_18]
0x18003fbee  mov     [rsp+80h+var_60], rax
0x18003fbf3  mov     dword ptr [rbp+var_30], ecx
0x18003fbf6  mov     dword ptr [rbp+arg_0], ebx
0x18003fbf9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003fbfe  jmp     loc_18003FAAF
0x18003fc03  mov     rcx, [rbx+58h]; hHandle
0x18003fc07  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003fc0a  call    cs:__imp_WaitForSingleObject
0x18003fc10  test    eax, eax
0x18003fc12  jz      loc_18003FAAD
0x18003fc18  mov     ecx, 80004005h
0x18003fc1d  cmp     eax, 80h
0x18003fc22  jz      short loc_18003FC33
0x18003fc24  cmp     eax, 102h
0x18003fc29  mov     ebx, 834500CBh
0x18003fc2e  cmovnz  ebx, ecx
0x18003fc31  jmp     short loc_18003FC38
0x18003fc33  mov     ebx, 834500CAh
0x18003fc38  mov     eax, cs:dword_18005C008
0x18003fc3e  cmp     eax, 2
0x18003fc41  jbe     loc_18003FAAF
0x18003fc47  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x18003fc4e  mov     [rbp+arg_18], 11Fh
0x18003fc55  mov     [rbp+var_18], rax
0x18003fc59  lea     rdx, byte_1800559FF
0x18003fc60  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003fc67  mov     [rbp+var_20], rax
0x18003fc6b  lea     rax, aPalSystemSingl; "PAL_System_SingleCondWait failed with 0"...
0x18003fc72  mov     [rbp+var_28], rax
0x18003fc76  lea     rax, [rbp+arg_0]
0x18003fc7a  mov     [rsp+80h+var_38], rax
0x18003fc7f  lea     rax, [rbp+var_18]
0x18003fc83  mov     [rsp+80h+var_40], rax
0x18003fc88  lea     rax, [rbp+arg_18]
0x18003fc8c  mov     [rsp+80h+var_48], rax
0x18003fc91  lea     rax, [rbp+var_20]
0x18003fc95  mov     [rsp+80h+var_50], rax
0x18003fc9a  lea     rax, [rbp+var_30]
0x18003fc9e  mov     [rsp+80h+var_58], rax
0x18003fca3  lea     rax, [rbp+var_28]
0x18003fca7  jmp     loc_18003FBEE
```
