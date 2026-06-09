# CWMIDataBlock::MapReturnCode(ulong)

- ea: `0x18000ac5c`
- end: `0x18000adfd`
- name: `?MapReturnCode@CWMIDataBlock@@IEAAJK@Z`
- size: `417`
- prototype: `__int64 __fastcall(CWMIDataBlock *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000abc0`
- `0x18001c9d4`
- `0x18001ca7c`

## callees

- `0x180003b08`
- `0x180004120`
- `0x18000ac5c`
- `0x18000cbd0`
- `0x18001c1a8`

## import_xrefs

- `wbemcomn!ErrorTrace` at `0x18000ac7d`
- `wbemcomn!ErrorTrace` at `0x18000ac7d`

## string_xrefs

- `0x18000ad7a`: `WDM specific error code: 4209 (Driver specific error, driver could not complete request)`
- `0x18000ad8c`: `WDM specific error code: 4209 (Driver specific error, driver could not complete request)`
- `0x18000ad61`: `WDM specific error code: 4213 (The WDM data item or data block is read-only)`
- `0x18000ade0`: `Access Denied`

## pseudocode

```c
__int64 __fastcall CWMIDataBlock::MapReturnCode(CWMIDataBlock *this, unsigned int a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // ebx
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  char *v10; // rdx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  CWMIDataBlock *v18; // rcx

  if ( a2 )
    ErrorTrace(10, "WDM call returned error: %lu\n", a2);
  StringCchPrintfW((unsigned __int16 *)this + 74, 0x200u, L"WDM specific return code: %lu\n", a2);
  if ( a2 <= 0x51B )
  {
    if ( a2 != 1307 )
    {
      if ( !a2 )
        return 0;
      v4 = a2 - 1;
      if ( v4 )
      {
        v5 = v4 - 1;
        if ( v5 )
        {
          v6 = v5 - 3;
          if ( v6 )
          {
            v7 = v6 - 1;
            if ( !v7 )
              return 2147749897LL;
            v8 = v7 - 7;
            if ( !v8 )
            {
              StringCchCopyW((unsigned __int16 *)this + 74, 0x200u, L"Array is the wrong size");
              v10 = "Invalid Data";
              goto LABEL_14;
            }
            v9 = v8 - 37;
            if ( v9 )
            {
              if ( v9 == 37 )
              {
                v10 = "Invalid Parameter";
LABEL_14:
                CWMIDataBlock::DumpWnodeInfo((const void **)this, v10);
                return 2147749896LL;
              }
              return 2147749889LL;
            }
            return 2147749900LL;
          }
          goto LABEL_31;
        }
        return 0;
      }
      return 2147749900LL;
    }
LABEL_31:
    CWMIDataBlock::DumpWnodeInfo((const void **)this, "Access Denied");
    return 2147749891LL;
  }
  v12 = a2 - 1308;
  if ( !v12 )
    goto LABEL_31;
  v13 = v12 - 2892;
  if ( !v13 )
    return 2147749900LL;
  v14 = v13 - 1;
  if ( !v14 )
  {
    StringCchCopyW((unsigned __int16 *)this + 74, 0x200u, L"The instance name passed was not recognized as valid");
    CWMIDataBlock::DumpWnodeMsg(v18, "The instance name passed was not recognized as valid");
    return 2147749890LL;
  }
  v15 = v14 - 6;
  if ( !v15 )
  {
    StringCchCopyW((unsigned __int16 *)this + 74, 0x200u, L"The WDM data block is no longer available.");
    return 2147749900LL;
  }
  v16 = v15 - 1;
  if ( !v16 )
    return 2147749900LL;
  v17 = v16 - 1;
  if ( v17 )
  {
    if ( v17 != 4 )
      return 2147749889LL;
    StringCchCopyW(
      (unsigned __int16 *)this + 74,
      0x200u,
      L"WDM specific error code: 4213 (The WDM data item or data block is read-only)");
    return 2147749923LL;
  }
  else
  {
    StringCchCopyW(
      (unsigned __int16 *)this + 74,
      0x200u,
      L"WDM specific error code: 4209 (Driver specific error, driver could not complete request)");
    CWMIDataBlock::DumpWnodeInfo(
      (const void **)this,
      "WDM specific error code: 4209 (Driver specific error, driver could not complete request)");
    return 2147749910LL;
  }
}

```

## disassembly

```asm
0x18000ac5c  push    rbx
0x18000ac5e  push    rbp
0x18000ac5f  push    rsi
0x18000ac60  push    rdi
0x18000ac61  sub     rsp, 28h
0x18000ac65  mov     ebx, edx
0x18000ac67  mov     rsi, rcx
0x18000ac6a  test    edx, edx
0x18000ac6c  jz      short loc_18000AC83
0x18000ac6e  mov     r8d, edx
0x18000ac71  mov     ecx, 0Ah
0x18000ac76  lea     rdx, aWdmCallReturne; "WDM call returned error: %lu\n"
0x18000ac7d  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x18000ac83  lea     rdi, [rsi+94h]
0x18000ac8a  mov     ebp, 200h
0x18000ac8f  mov     edx, ebp; unsigned __int64
0x18000ac91  lea     r8, aWdmSpecificRet; "WDM specific return code: %lu\n"
0x18000ac98  mov     rcx, rdi; unsigned __int16 *
0x18000ac9b  mov     r9d, ebx
0x18000ac9e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000aca3  mov     eax, 51Bh
0x18000aca8  cmp     ebx, eax
0x18000acaa  ja      short loc_18000AD2A
0x18000acac  jz      loc_18000ADE0
0x18000acb2  test    ebx, ebx
0x18000acb4  jz      short loc_18000AD23
0x18000acb6  sub     ebx, 1
0x18000acb9  jz      loc_18000ADB4
0x18000acbf  sub     ebx, 1
0x18000acc2  jz      short loc_18000AD23
0x18000acc4  sub     ebx, 3
0x18000acc7  jz      loc_18000ADE0
0x18000accd  sub     ebx, 1
0x18000acd0  jz      short loc_18000AD19
0x18000acd2  sub     ebx, 7
0x18000acd5  jz      short loc_18000ACFE
0x18000acd7  sub     ebx, 25h ; '%'
0x18000acda  jz      loc_18000ADB4
0x18000ace0  cmp     ebx, 25h ; '%'
0x18000ace3  jnz     short loc_18000AD57
0x18000ace5  lea     rdx, aInvalidParamet; "Invalid Parameter"
0x18000acec  mov     rcx, rsi; this
0x18000acef  call    ?DumpWnodeInfo@CWMIDataBlock@@IEAAJPEAD@Z; CWMIDataBlock::DumpWnodeInfo(char *)
0x18000acf4  mov     eax, 80041008h
0x18000acf9  jmp     loc_18000ADF4
0x18000acfe  lea     r8, aArrayIsTheWron; "Array is the wrong size"
0x18000ad05  mov     rdx, rbp; unsigned __int64
0x18000ad08  mov     rcx, rdi; unsigned __int16 *
0x18000ad0b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ad10  lea     rdx, aInvalidData; "Invalid Data"
0x18000ad17  jmp     short loc_18000ACEC
0x18000ad19  mov     eax, 80041009h
0x18000ad1e  jmp     loc_18000ADF4
0x18000ad23  xor     eax, eax
0x18000ad25  jmp     loc_18000ADF4
0x18000ad2a  sub     ebx, 51Ch
0x18000ad30  jz      loc_18000ADE0
0x18000ad36  sub     ebx, 0B4Ch
0x18000ad3c  jz      short loc_18000ADB4
0x18000ad3e  sub     ebx, 1
0x18000ad41  jz      short loc_18000ADBB
0x18000ad43  sub     ebx, 6
0x18000ad46  jz      short loc_18000ADA2
0x18000ad48  sub     ebx, 1
0x18000ad4b  jz      short loc_18000ADB4
0x18000ad4d  sub     ebx, 1
0x18000ad50  jz      short loc_18000AD7A
0x18000ad52  cmp     ebx, 4
0x18000ad55  jz      short loc_18000AD61
0x18000ad57  mov     eax, 80041001h
0x18000ad5c  jmp     loc_18000ADF4
0x18000ad61  lea     r8, aWdmSpecificErr; "WDM specific error code: 4213 (The WDM "...
0x18000ad68  mov     rdx, rbp; unsigned __int64
0x18000ad6b  mov     rcx, rdi; unsigned __int16 *
0x18000ad6e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ad73  mov     eax, 80041023h
0x18000ad78  jmp     short loc_18000ADF4
0x18000ad7a  lea     r8, aWdmSpecificErr_0; "WDM specific error code: 4209 (Driver s"...
0x18000ad81  mov     rdx, rbp; unsigned __int64
0x18000ad84  mov     rcx, rdi; unsigned __int16 *
0x18000ad87  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ad8c  lea     rdx, aWdmSpecificErr_1; "WDM specific error code: 4209 (Driver s"...
0x18000ad93  mov     rcx, rsi; this
0x18000ad96  call    ?DumpWnodeInfo@CWMIDataBlock@@IEAAJPEAD@Z; CWMIDataBlock::DumpWnodeInfo(char *)
0x18000ad9b  mov     eax, 80041016h
0x18000ada0  jmp     short loc_18000ADF4
0x18000ada2  lea     r8, aTheWdmDataBloc; "The WDM data block is no longer availab"...
0x18000ada9  mov     rdx, rbp; unsigned __int64
0x18000adac  mov     rcx, rdi; unsigned __int16 *
0x18000adaf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000adb4  mov     eax, 8004100Ch
0x18000adb9  jmp     short loc_18000ADF4
0x18000adbb  lea     r8, aTheInstanceNam_0; "The instance name passed was not recogn"...
0x18000adc2  mov     rdx, rbp; unsigned __int64
0x18000adc5  mov     rcx, rdi; unsigned __int16 *
0x18000adc8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000adcd  lea     rdx, aTheInstanceNam; "The instance name passed was not recogn"...
0x18000add4  call    ?DumpWnodeMsg@CWMIDataBlock@@IEAAXPEAD@Z; CWMIDataBlock::DumpWnodeMsg(char *)
0x18000add9  mov     eax, 80041002h
0x18000adde  jmp     short loc_18000ADF4
0x18000ade0  lea     rdx, aAccessDenied; "Access Denied"
0x18000ade7  mov     rcx, rsi; this
0x18000adea  call    ?DumpWnodeInfo@CWMIDataBlock@@IEAAJPEAD@Z; CWMIDataBlock::DumpWnodeInfo(char *)
0x18000adef  mov     eax, 80041003h
0x18000adf4  add     rsp, 28h
0x18000adf8  pop     rdi
0x18000adf9  pop     rsi
0x18000adfa  pop     rbp
0x18000adfb  pop     rbx
0x18000adfc  retn
```
