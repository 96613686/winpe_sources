# cxl::GetEnumValueName(cxl::ErrorCode::Enum const &)

- ea: `0x1800118fc`
- end: `0x180011b66`
- name: `?GetEnumValueName@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4Enum@ErrorCode@1@@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180011fe0`

## callees

- `0x18000cd54`
- `0x18000cd9c`
- `0x1800118fc`

## string_xrefs

- `0x180011969`: `AlreadyExists`
- `0x180011b50`: `PartialWrite`
- `0x180011ae5`: `PartialRead`
- `0x180011b47`: `DeserializeError`

## pseudocode

```c
__int64 __fastcall cxl::GetEnumValueName(__int64 a1, int *a2)
{
  int v2; // r8d
  int v4; // r8d
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  const wchar_t *v9; // rdx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  int v15; // r8d
  int v16; // r8d
  int v17; // r8d
  int v18; // r8d
  int v19; // r8d
  int v20; // r8d
  int v21; // r8d
  int v22; // r8d
  int v23; // r8d
  int v24; // r8d
  int v25; // r8d
  int v26; // r8d

  v2 = *a2;
  if ( *a2 > 5913 )
  {
    if ( v2 > 5921 )
    {
      v22 = v2 - 5922;
      if ( !v22 )
      {
        v9 = L"PartialWrite";
        goto LABEL_65;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        v9 = L"DeserializeError";
        goto LABEL_65;
      }
      v24 = v23 - 68;
      if ( !v24 )
      {
        v9 = L"ExceptionExpected";
        goto LABEL_65;
      }
      v25 = v24 - 1;
      if ( !v25 )
      {
        v9 = L"Different";
        goto LABEL_65;
      }
      v26 = v25 - 1;
      if ( !v26 )
      {
        v9 = L"TestTimeout";
        goto LABEL_65;
      }
      if ( v26 == 1 )
      {
        v9 = L"SimulatedFailure";
        goto LABEL_65;
      }
    }
    else
    {
      if ( v2 == 5921 )
      {
        v9 = L"PartialRead";
        goto LABEL_65;
      }
      v16 = v2 - 5914;
      if ( !v16 )
      {
        v9 = L"PartialSend";
        goto LABEL_65;
      }
      v17 = v16 - 1;
      if ( !v17 )
      {
        v9 = L"InvalidDmDispatch";
        goto LABEL_65;
      }
      v18 = v17 - 1;
      if ( !v18 )
      {
        v9 = L"BadString";
        goto LABEL_65;
      }
      v19 = v18 - 1;
      if ( !v19 )
      {
        v9 = L"BadFormat";
        goto LABEL_65;
      }
      v20 = v19 - 1;
      if ( !v20 )
      {
        v9 = L"TransactionInProgress";
        goto LABEL_65;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        v9 = L"TransactionNotInProgress";
        goto LABEL_65;
      }
      if ( v21 == 1 )
      {
        v9 = L"NullPointer";
        goto LABEL_65;
      }
    }
  }
  else
  {
    if ( v2 == 5913 )
    {
      v9 = L"ArgumentOutOfBounds";
      goto LABEL_65;
    }
    if ( v2 > 298 )
    {
      v10 = v2 - 534;
      if ( !v10 )
      {
        v9 = L"IntegerOverflow";
        goto LABEL_65;
      }
      v11 = v10 - 134;
      if ( !v11 )
      {
        v9 = L"AssertionFailed";
        goto LABEL_65;
      }
      v12 = v11 - 558;
      if ( !v12 )
      {
        v9 = L"GracefulClose";
        goto LABEL_65;
      }
      v13 = v12 - 10;
      if ( !v13 )
      {
        v9 = L"Closed";
        goto LABEL_65;
      }
      v14 = v13 - 123;
      if ( !v14 )
      {
        v9 = L"InternalError";
        goto LABEL_65;
      }
      v15 = v14 - 270;
      if ( !v15 )
      {
        v9 = L"TypeMismatch";
        goto LABEL_65;
      }
      if ( v15 == 4283 )
      {
        v9 = L"MethodIsNotSupported";
        goto LABEL_65;
      }
    }
    else
    {
      if ( v2 == 298 )
      {
        v9 = L"TooMany";
        goto LABEL_65;
      }
      if ( !v2 )
      {
        v9 = L"None";
        goto LABEL_65;
      }
      v4 = v2 - 2;
      if ( !v4 )
      {
        v9 = L"NotFound";
        goto LABEL_65;
      }
      v5 = v4 - 19;
      if ( !v5 )
      {
        v9 = L"InvalidState";
        goto LABEL_65;
      }
      v6 = v5 - 66;
      if ( !v6 )
      {
        v9 = L"ArgumentInvalid";
        goto LABEL_65;
      }
      v7 = v6 - 33;
      if ( !v7 )
      {
        v9 = L"NotYetImplemented";
        goto LABEL_65;
      }
      v8 = v7 - 63;
      if ( !v8 )
      {
        v9 = L"AlreadyExists";
        goto LABEL_65;
      }
      if ( v8 == 105 )
      {
        v9 = L"NotOwner";
LABEL_65:
        std::wstring::wstring(a1, v9);
        return a1;
      }
    }
  }
  std::wstring::wstring(a1, cxl::EmptyLiteral);
  return a1;
}

```

## disassembly

```asm
0x1800118fc  push    rbx
0x1800118fe  sub     rsp, 30h
0x180011902  mov     r8d, [rdx]
0x180011905  mov     eax, 1719h
0x18001190a  mov     rbx, rcx
0x18001190d  cmp     r8d, eax
0x180011910  jg      loc_180011A5A
0x180011916  jz      loc_180011A4E
0x18001191c  mov     eax, 12Ah
0x180011921  cmp     r8d, eax
0x180011924  jg      loc_1800119BD
0x18001192a  jz      loc_1800119B1
0x180011930  test    r8d, r8d
0x180011933  jz      short loc_1800119A5
0x180011935  sub     r8d, 2
0x180011939  jz      short loc_180011999
0x18001193b  sub     r8d, 13h
0x18001193f  jz      short loc_18001198D
0x180011941  sub     r8d, 42h ; 'B'
0x180011945  jz      short loc_180011981
0x180011947  sub     r8d, 21h ; '!'
0x18001194b  jz      short loc_180011975
0x18001194d  sub     r8d, 3Fh ; '?'
0x180011951  jz      short loc_180011969
0x180011953  cmp     r8d, 69h ; 'i'
0x180011957  jnz     loc_180011B15
0x18001195d  lea     rdx, aNotowner; "NotOwner"
0x180011964  jmp     loc_180011B57
0x180011969  lea     rdx, aAlreadyexists; "AlreadyExists"
0x180011970  jmp     loc_180011B57
0x180011975  lea     rdx, aNotyetimplemen; "NotYetImplemented"
0x18001197c  jmp     loc_180011B57
0x180011981  lea     rdx, aArgumentinvali; "ArgumentInvalid"
0x180011988  jmp     loc_180011B57
0x18001198d  lea     rdx, aInvalidstate; "InvalidState"
0x180011994  jmp     loc_180011B57
0x180011999  lea     rdx, aNotfound; "NotFound"
0x1800119a0  jmp     loc_180011B57
0x1800119a5  lea     rdx, aNone; "None"
0x1800119ac  jmp     loc_180011B57
0x1800119b1  lea     rdx, aToomany; "TooMany"
0x1800119b8  jmp     loc_180011B57
0x1800119bd  sub     r8d, 216h
0x1800119c4  jz      short loc_180011A42
0x1800119c6  sub     r8d, 86h
0x1800119cd  jz      short loc_180011A36
0x1800119cf  sub     r8d, 22Eh
0x1800119d6  jz      short loc_180011A2A
0x1800119d8  sub     r8d, 0Ah
0x1800119dc  jz      short loc_180011A1E
0x1800119de  sub     r8d, 7Bh ; '{'
0x1800119e2  jz      short loc_180011A12
0x1800119e4  sub     r8d, 10Eh
0x1800119eb  jz      short loc_180011A06
0x1800119ed  cmp     r8d, 10BBh
0x1800119f4  jnz     loc_180011B15
0x1800119fa  lea     rdx, aMethodisnotsup; "MethodIsNotSupported"
0x180011a01  jmp     loc_180011B57
0x180011a06  lea     rdx, aTypemismatch; "TypeMismatch"
0x180011a0d  jmp     loc_180011B57
0x180011a12  lea     rdx, aInternalerror; "InternalError"
0x180011a19  jmp     loc_180011B57
0x180011a1e  lea     rdx, aClosed; "Closed"
0x180011a25  jmp     loc_180011B57
0x180011a2a  lea     rdx, aGracefulclose; "GracefulClose"
0x180011a31  jmp     loc_180011B57
0x180011a36  lea     rdx, aAssertionfaile; "AssertionFailed"
0x180011a3d  jmp     loc_180011B57
0x180011a42  lea     rdx, aIntegeroverflo; "IntegerOverflow"
0x180011a49  jmp     loc_180011B57
0x180011a4e  lea     rdx, aArgumentoutofb; "ArgumentOutOfBounds"
0x180011a55  jmp     loc_180011B57
0x180011a5a  mov     eax, 1721h
0x180011a5f  cmp     r8d, eax
0x180011a62  jg      loc_180011AEE
0x180011a68  jz      short loc_180011AE5
0x180011a6a  sub     r8d, 171Ah
0x180011a71  jz      short loc_180011ADC
0x180011a73  sub     r8d, 1
0x180011a77  jz      short loc_180011AD3
0x180011a79  sub     r8d, 1
0x180011a7d  jz      short loc_180011AC7
0x180011a7f  sub     r8d, 1
0x180011a83  jz      short loc_180011ABB
0x180011a85  sub     r8d, 1
0x180011a89  jz      short loc_180011AAF
0x180011a8b  sub     r8d, 1
0x180011a8f  jz      short loc_180011AA3
0x180011a91  cmp     r8d, 1
0x180011a95  jnz     short loc_180011B15
0x180011a97  lea     rdx, aNullpointer; "NullPointer"
0x180011a9e  jmp     loc_180011B57
0x180011aa3  lea     rdx, aTransactionnot; "TransactionNotInProgress"
0x180011aaa  jmp     loc_180011B57
0x180011aaf  lea     rdx, aTransactioninp; "TransactionInProgress"
0x180011ab6  jmp     loc_180011B57
0x180011abb  lea     rdx, aBadformat; "BadFormat"
0x180011ac2  jmp     loc_180011B57
0x180011ac7  lea     rdx, aBadstring; "BadString"
0x180011ace  jmp     loc_180011B57
0x180011ad3  lea     rdx, aInvaliddmdispa; "InvalidDmDispatch"
0x180011ada  jmp     short loc_180011B57
0x180011adc  lea     rdx, aPartialsend; "PartialSend"
0x180011ae3  jmp     short loc_180011B57
0x180011ae5  lea     rdx, aPartialread; "PartialRead"
0x180011aec  jmp     short loc_180011B57
0x180011aee  sub     r8d, 1722h
0x180011af5  jz      short loc_180011B50
0x180011af7  sub     r8d, 1
0x180011afb  jz      short loc_180011B47
0x180011afd  sub     r8d, 44h ; 'D'
0x180011b01  jz      short loc_180011B3E
0x180011b03  sub     r8d, 1
0x180011b07  jz      short loc_180011B35
0x180011b09  sub     r8d, 1
0x180011b0d  jz      short loc_180011B2C
0x180011b0f  cmp     r8d, 1
0x180011b13  jz      short loc_180011B23
0x180011b15  lea     rdx, ?EmptyLiteral@cxl@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const cxl::EmptyLiteral
0x180011b1c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011b21  jmp     short loc_180011B5C
0x180011b23  lea     rdx, aSimulatedfailu; "SimulatedFailure"
0x180011b2a  jmp     short loc_180011B57
0x180011b2c  lea     rdx, aTesttimeout; "TestTimeout"
0x180011b33  jmp     short loc_180011B57
0x180011b35  lea     rdx, aDifferent; "Different"
0x180011b3c  jmp     short loc_180011B57
0x180011b3e  lea     rdx, aExceptionexpec; "ExceptionExpected"
0x180011b45  jmp     short loc_180011B57
0x180011b47  lea     rdx, aDeserializeerr; "DeserializeError"
0x180011b4e  jmp     short loc_180011B57
0x180011b50  lea     rdx, aPartialwrite; "PartialWrite"
0x180011b57  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180011b5c  mov     rax, rbx
0x180011b5f  add     rsp, 30h
0x180011b63  pop     rbx
0x180011b64  retn
```
