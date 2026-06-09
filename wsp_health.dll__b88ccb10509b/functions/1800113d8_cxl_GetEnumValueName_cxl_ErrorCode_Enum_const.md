# cxl::GetEnumValueName(cxl::ErrorCode::Enum const &)

- ea: `0x1800113d8`
- end: `0x180011641`
- name: `?GetEnumValueName@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4Enum@ErrorCode@1@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180011a80`

## callees

- `0x18000c9a8`
- `0x18000c9f0`
- `0x1800113d8`

## string_xrefs

- `0x180011445`: `AlreadyExists`
- `0x18001162c`: `PartialWrite`
- `0x1800115c1`: `PartialRead`
- `0x180011623`: `DeserializeError`

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
0x1800113d8  push    rbx
0x1800113da  sub     rsp, 30h
0x1800113de  mov     r8d, [rdx]
0x1800113e1  mov     eax, 1719h
0x1800113e6  mov     rbx, rcx
0x1800113e9  cmp     r8d, eax
0x1800113ec  jg      loc_180011536
0x1800113f2  jz      loc_18001152A
0x1800113f8  mov     eax, 12Ah
0x1800113fd  cmp     r8d, eax
0x180011400  jg      loc_180011499
0x180011406  jz      loc_18001148D
0x18001140c  test    r8d, r8d
0x18001140f  jz      short loc_180011481
0x180011411  sub     r8d, 2
0x180011415  jz      short loc_180011475
0x180011417  sub     r8d, 13h
0x18001141b  jz      short loc_180011469
0x18001141d  sub     r8d, 42h ; 'B'
0x180011421  jz      short loc_18001145D
0x180011423  sub     r8d, 21h ; '!'
0x180011427  jz      short loc_180011451
0x180011429  sub     r8d, 3Fh ; '?'
0x18001142d  jz      short loc_180011445
0x18001142f  cmp     r8d, 69h ; 'i'
0x180011433  jnz     loc_1800115F1
0x180011439  lea     rdx, aNotowner; "NotOwner"
0x180011440  jmp     loc_180011633
0x180011445  lea     rdx, aAlreadyexists; "AlreadyExists"
0x18001144c  jmp     loc_180011633
0x180011451  lea     rdx, aNotyetimplemen; "NotYetImplemented"
0x180011458  jmp     loc_180011633
0x18001145d  lea     rdx, aArgumentinvali; "ArgumentInvalid"
0x180011464  jmp     loc_180011633
0x180011469  lea     rdx, aInvalidstate; "InvalidState"
0x180011470  jmp     loc_180011633
0x180011475  lea     rdx, aNotfound; "NotFound"
0x18001147c  jmp     loc_180011633
0x180011481  lea     rdx, aNone; "None"
0x180011488  jmp     loc_180011633
0x18001148d  lea     rdx, aToomany; "TooMany"
0x180011494  jmp     loc_180011633
0x180011499  sub     r8d, 216h
0x1800114a0  jz      short loc_18001151E
0x1800114a2  sub     r8d, 86h
0x1800114a9  jz      short loc_180011512
0x1800114ab  sub     r8d, 22Eh
0x1800114b2  jz      short loc_180011506
0x1800114b4  sub     r8d, 0Ah
0x1800114b8  jz      short loc_1800114FA
0x1800114ba  sub     r8d, 7Bh ; '{'
0x1800114be  jz      short loc_1800114EE
0x1800114c0  sub     r8d, 10Eh
0x1800114c7  jz      short loc_1800114E2
0x1800114c9  cmp     r8d, 10BBh
0x1800114d0  jnz     loc_1800115F1
0x1800114d6  lea     rdx, aMethodisnotsup; "MethodIsNotSupported"
0x1800114dd  jmp     loc_180011633
0x1800114e2  lea     rdx, aTypemismatch; "TypeMismatch"
0x1800114e9  jmp     loc_180011633
0x1800114ee  lea     rdx, aInternalerror; "InternalError"
0x1800114f5  jmp     loc_180011633
0x1800114fa  lea     rdx, aClosed; "Closed"
0x180011501  jmp     loc_180011633
0x180011506  lea     rdx, aGracefulclose; "GracefulClose"
0x18001150d  jmp     loc_180011633
0x180011512  lea     rdx, aAssertionfaile; "AssertionFailed"
0x180011519  jmp     loc_180011633
0x18001151e  lea     rdx, aIntegeroverflo; "IntegerOverflow"
0x180011525  jmp     loc_180011633
0x18001152a  lea     rdx, aArgumentoutofb; "ArgumentOutOfBounds"
0x180011531  jmp     loc_180011633
0x180011536  mov     eax, 1721h
0x18001153b  cmp     r8d, eax
0x18001153e  jg      loc_1800115CA
0x180011544  jz      short loc_1800115C1
0x180011546  sub     r8d, 171Ah
0x18001154d  jz      short loc_1800115B8
0x18001154f  sub     r8d, 1
0x180011553  jz      short loc_1800115AF
0x180011555  sub     r8d, 1
0x180011559  jz      short loc_1800115A3
0x18001155b  sub     r8d, 1
0x18001155f  jz      short loc_180011597
0x180011561  sub     r8d, 1
0x180011565  jz      short loc_18001158B
0x180011567  sub     r8d, 1
0x18001156b  jz      short loc_18001157F
0x18001156d  cmp     r8d, 1
0x180011571  jnz     short loc_1800115F1
0x180011573  lea     rdx, aNullpointer; "NullPointer"
0x18001157a  jmp     loc_180011633
0x18001157f  lea     rdx, aTransactionnot; "TransactionNotInProgress"
0x180011586  jmp     loc_180011633
0x18001158b  lea     rdx, aTransactioninp; "TransactionInProgress"
0x180011592  jmp     loc_180011633
0x180011597  lea     rdx, aBadformat; "BadFormat"
0x18001159e  jmp     loc_180011633
0x1800115a3  lea     rdx, aBadstring; "BadString"
0x1800115aa  jmp     loc_180011633
0x1800115af  lea     rdx, aInvaliddmdispa; "InvalidDmDispatch"
0x1800115b6  jmp     short loc_180011633
0x1800115b8  lea     rdx, aPartialsend; "PartialSend"
0x1800115bf  jmp     short loc_180011633
0x1800115c1  lea     rdx, aPartialread; "PartialRead"
0x1800115c8  jmp     short loc_180011633
0x1800115ca  sub     r8d, 1722h
0x1800115d1  jz      short loc_18001162C
0x1800115d3  sub     r8d, 1
0x1800115d7  jz      short loc_180011623
0x1800115d9  sub     r8d, 44h ; 'D'
0x1800115dd  jz      short loc_18001161A
0x1800115df  sub     r8d, 1
0x1800115e3  jz      short loc_180011611
0x1800115e5  sub     r8d, 1
0x1800115e9  jz      short loc_180011608
0x1800115eb  cmp     r8d, 1
0x1800115ef  jz      short loc_1800115FF
0x1800115f1  lea     rdx, ?EmptyLiteral@cxl@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const cxl::EmptyLiteral
0x1800115f8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800115fd  jmp     short loc_180011638
0x1800115ff  lea     rdx, aSimulatedfailu; "SimulatedFailure"
0x180011606  jmp     short loc_180011633
0x180011608  lea     rdx, aTesttimeout; "TestTimeout"
0x18001160f  jmp     short loc_180011633
0x180011611  lea     rdx, aDifferent; "Different"
0x180011618  jmp     short loc_180011633
0x18001161a  lea     rdx, aExceptionexpec; "ExceptionExpected"
0x180011621  jmp     short loc_180011633
0x180011623  lea     rdx, aDeserializeerr; "DeserializeError"
0x18001162a  jmp     short loc_180011633
0x18001162c  lea     rdx, aPartialwrite; "PartialWrite"
0x180011633  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180011638  mov     rax, rbx
0x18001163b  add     rsp, 30h
0x18001163f  pop     rbx
0x180011640  retn
```
