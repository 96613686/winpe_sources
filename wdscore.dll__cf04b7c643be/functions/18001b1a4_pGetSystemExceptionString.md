# pGetSystemExceptionString

- ea: `0x18001b1a4`
- end: `0x18001b33e`
- name: `pGetSystemExceptionString`
- size: `410`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ae10`
- `0x18001c830`

## callees

- `0x18001b1a4`

## string_xrefs

- `0x18001b1e2`: `ACCESS_VIOLATION`

## pseudocode

```c
const wchar_t *__fastcall pGetSystemExceptionString(unsigned int a1)
{
  const wchar_t *v1; // rax
  bool v2; // zf
  const wchar_t *result; // rax
  const wchar_t *v4; // rdx

  if ( a1 <= 0xC000008D )
  {
    if ( a1 == -1073741683 )
      return L"FLT_DENORMAL_OPERAND";
    if ( a1 > 0xC0000006 )
    {
      switch ( a1 )
      {
        case 0xC0000008:
          return L"INVALID_HANDLE";
        case 0xC000001D:
          return L"ILLEGAL_INSTRUCTION";
        case 0xC0000025:
          return L"NONCONTINUABLE_EXCEPTION";
        case 0xC0000026:
          return L"INVALID_DISPOSITION";
      }
      v1 = L"ARRAY_BOUNDS_EXCEEDED";
      v2 = a1 == -1073741684;
    }
    else
    {
      switch ( a1 )
      {
        case 0xC0000006:
          return L"IN_PAGE_ERROR";
        case 0x80000001:
          return L"GUARD_PAGE";
        case 0x80000002:
          return L"DATATYPE_MISALIGNMENT";
        case 0x80000003:
          return L"BREAKPOINT";
        case 0x80000004:
          return L"SINGLE_STEP";
      }
      v1 = L"ACCESS_VIOLATION";
      v2 = a1 == -1073741819;
    }
LABEL_32:
    v4 = L"<unknown>";
    if ( v2 )
      return v1;
    return v4;
  }
  if ( a1 <= 0xC0000093 )
  {
    switch ( a1 )
    {
      case 0xC0000093:
        return L"FLT_UNDERFLOW";
      case 0xC000008E:
        return L"FLT_DIVIDE_BY_ZERO";
      case 0xC000008F:
        return L"FLT_INEXACT_RESULT";
      case 0xC0000090:
        return L"FLT_INVALID_OPERATION";
      case 0xC0000091:
        return L"FLT_OVERFLOW";
    }
    v1 = L"FLT_STACK_CHECK";
    v2 = a1 == -1073741678;
    goto LABEL_32;
  }
  switch ( a1 )
  {
    case 0xC0000094:
      return L"INT_DIVIDE_BY_ZERO";
    case 0xC0000095:
      return L"INT_OVERFLOW";
    case 0xC0000096:
      return L"PRIV_INSTRUCTION";
  }
  result = L"STACK_OVERFLOW";
  if ( a1 != -1073741571 )
    return L"<unknown>";
  return result;
}

```

## disassembly

```asm
0x18001b1a4  mov     eax, 0C000008Dh
0x18001b1a9  cmp     ecx, eax
0x18001b1ab  ja      loc_18001B27D
0x18001b1b1  jz      loc_18001B274
0x18001b1b7  mov     eax, 0C0000006h
0x18001b1bc  cmp     ecx, eax
0x18001b1be  ja      short loc_18001B221
0x18001b1c0  jz      short loc_18001B218
0x18001b1c2  cmp     ecx, 80000001h
0x18001b1c8  jz      short loc_18001B20F
0x18001b1ca  cmp     ecx, 80000002h
0x18001b1d0  jz      short loc_18001B206
0x18001b1d2  cmp     ecx, 80000003h
0x18001b1d8  jz      short loc_18001B1FD
0x18001b1da  cmp     ecx, 80000004h
0x18001b1e0  jz      short loc_18001B1F4
0x18001b1e2  lea     rax, aAccessViolatio; "ACCESS_VIOLATION"
0x18001b1e9  cmp     ecx, 0C0000005h
0x18001b1ef  jmp     loc_18001B2B5
0x18001b1f4  lea     rax, aSingleStep; "SINGLE_STEP"
0x18001b1fb  retn
0x18001b1fd  lea     rax, aBreakpoint; "BREAKPOINT"
0x18001b204  retn
0x18001b206  lea     rax, aDatatypeMisali; "DATATYPE_MISALIGNMENT"
0x18001b20d  retn
0x18001b20f  lea     rax, aGuardPage; "GUARD_PAGE"
0x18001b216  retn
0x18001b218  lea     rax, aInPageError; "IN_PAGE_ERROR"
0x18001b21f  retn
0x18001b221  cmp     ecx, 0C0000008h
0x18001b227  jz      short loc_18001B26B
0x18001b229  cmp     ecx, 0C000001Dh
0x18001b22f  jz      short loc_18001B262
0x18001b231  cmp     ecx, 0C0000025h
0x18001b237  jz      short loc_18001B259
0x18001b239  cmp     ecx, 0C0000026h
0x18001b23f  jz      short loc_18001B250
0x18001b241  lea     rax, aArrayBoundsExc; "ARRAY_BOUNDS_EXCEEDED"
0x18001b248  cmp     ecx, 0C000008Ch
0x18001b24e  jmp     short loc_18001B2B5
0x18001b250  lea     rax, aInvalidDisposi; "INVALID_DISPOSITION"
0x18001b257  retn
0x18001b259  lea     rax, aNoncontinuable; "NONCONTINUABLE_EXCEPTION"
0x18001b260  retn
0x18001b262  lea     rax, aIllegalInstruc; "ILLEGAL_INSTRUCTION"
0x18001b269  retn
0x18001b26b  lea     rax, aInvalidHandle; "INVALID_HANDLE"
0x18001b272  retn
0x18001b274  lea     rax, aFltDenormalOpe; "FLT_DENORMAL_OPERAND"
0x18001b27b  retn
0x18001b27d  mov     eax, 0C0000093h
0x18001b282  cmp     ecx, eax
0x18001b284  ja      short loc_18001B2F2
0x18001b286  jz      short loc_18001B2E9
0x18001b288  cmp     ecx, 0C000008Eh
0x18001b28e  jz      short loc_18001B2E0
0x18001b290  cmp     ecx, 0C000008Fh
0x18001b296  jz      short loc_18001B2D7
0x18001b298  cmp     ecx, 0C0000090h
0x18001b29e  jz      short loc_18001B2CE
0x18001b2a0  cmp     ecx, 0C0000091h
0x18001b2a6  jz      short loc_18001B2C5
0x18001b2a8  lea     rax, aFltStackCheck; "FLT_STACK_CHECK"
0x18001b2af  cmp     ecx, 0C0000092h
0x18001b2b5  lea     rdx, aUnknown; "<unknown>"
0x18001b2bc  cmovz   rdx, rax
0x18001b2c0  mov     rax, rdx
0x18001b2c3  retn
0x18001b2c5  lea     rax, aFltOverflow; "FLT_OVERFLOW"
0x18001b2cc  retn
0x18001b2ce  lea     rax, aFltInvalidOper; "FLT_INVALID_OPERATION"
0x18001b2d5  retn
0x18001b2d7  lea     rax, aFltInexactResu; "FLT_INEXACT_RESULT"
0x18001b2de  retn
0x18001b2e0  lea     rax, aFltDivideByZer; "FLT_DIVIDE_BY_ZERO"
0x18001b2e7  retn
0x18001b2e9  lea     rax, aFltUnderflow; "FLT_UNDERFLOW"
0x18001b2f0  retn
0x18001b2f2  cmp     ecx, 0C0000094h
0x18001b2f8  jz      short loc_18001B336
0x18001b2fa  cmp     ecx, 0C0000095h
0x18001b300  jz      short loc_18001B32D
0x18001b302  cmp     ecx, 0C0000096h
0x18001b308  jz      short loc_18001B324
0x18001b30a  cmp     ecx, 0C00000FDh
0x18001b310  lea     rdx, aUnknown; "<unknown>"
0x18001b317  lea     rax, aStackOverflow; "STACK_OVERFLOW"
0x18001b31e  cmovnz  rax, rdx
0x18001b322  retn
0x18001b324  lea     rax, aPrivInstructio; "PRIV_INSTRUCTION"
0x18001b32b  retn
0x18001b32d  lea     rax, aIntOverflow; "INT_OVERFLOW"
0x18001b334  retn
0x18001b336  lea     rax, aIntDivideByZer; "INT_DIVIDE_BY_ZERO"
0x18001b33d  retn
```
