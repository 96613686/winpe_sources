# CToken::CompareCapabilitySids(CToken *,bool)

- ea: `0x18008ab28`
- end: `0x18008aeb9`
- name: `?CompareCapabilitySids@CToken@@QEAAJPEAV1@_N@Z`
- size: `913`
- prototype: `__int64 __fastcall(CToken *__hidden this, struct CToken *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180090af8`

## callees

- `0x1800210f8`
- `0x180034260`
- `0x1800669a0`
- `0x18008172c`
- `0x18008ab28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ac55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008acec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008add0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ac55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008acec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008add0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008ab63`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008ac45`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008ace0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008adbc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008ab63`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008ac45`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008ace0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008adbc`
- `KERNELBASE!LocalAlloc` at `0x18008ac0a`
- `KERNELBASE!LocalAlloc` at `0x18008ad81`
- `KERNELBASE!LocalAlloc` at `0x18008ac0a`
- `KERNELBASE!LocalAlloc` at `0x18008ad81`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18008ae51`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18008ae86`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18008ae97`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18008ae51`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18008ae86`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18008ae97`

## string_xrefs

- `0x18008abd2`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18008abf0`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18008acaa`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18008ad49`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18008ad67`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18008ae25`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18008ae3a`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18008abcb`: `CToken::CompareCapabilitySids`
- `0x18008aca3`: `CToken::CompareCapabilitySids`
- `0x18008ad42`: `CToken::CompareCapabilitySids`
- `0x18008ae1e`: `CToken::CompareCapabilitySids`

## pseudocode

```c
__int64 __fastcall CToken::CompareCapabilitySids(HANDLE *this, HANDLE *a2)
{
  signed int LastError; // eax
  signed int v5; // ebx
  __int64 v6; // rdx
  unsigned int *v7; // rsi
  signed int v8; // eax
  __int64 v9; // rdx
  signed int v10; // eax
  unsigned int *v11; // rdi
  signed int v12; // eax
  unsigned int *v13; // rcx
  char v14; // al
  int ReturnLength; // [rsp+20h] [rbp-28h]
  int ReturnLengtha; // [rsp+20h] [rbp-28h]
  int ReturnLengthb; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  SIZE_T uBytes; // [rsp+60h] [rbp+18h] BYREF

  LODWORD(uBytes) = 0;
  GetTokenInformation(this[9], TokenCapabilities, 0, 0, (PDWORD)&uBytes);
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 == -2147024774 )
  {
    v7 = (unsigned int *)LocalAlloc(0, (unsigned int)uBytes);
    if ( !v7 )
    {
      v5 = -2147024882;
      v6 = 523;
      goto LABEL_10;
    }
    if ( GetTokenInformation(this[9], TokenCapabilities, v7, uBytes, (PDWORD)&uBytes) )
    {
      GetTokenInformation(a2[9], TokenCapabilities, 0, 0, (PDWORD)&uBytes);
      v10 = GetLastError();
      v5 = v10;
      if ( v10 > 0 )
        v5 = (unsigned __int16)v10 | 0x80070000;
      if ( v5 == -2147024774 )
      {
        v11 = (unsigned int *)LocalAlloc(0, (unsigned int)uBytes);
        if ( v11 )
        {
          if ( GetTokenInformation(a2[9], TokenCapabilities, v11, uBytes, (PDWORD)&uBytes) )
          {
            v5 = 1;
            LOBYTE(ReturnLengthb) = 0;
            v14 = CompareSidAndAttributeArrays(v7 + 2, *v7, v11 + 2, *v11, ReturnLengthb, 1);
            v13 = v11;
            if ( v14 )
            {
              LocalFree(v11);
              v5 = 0;
              goto LABEL_47;
            }
          }
          else
          {
            v12 = GetLastError();
            v5 = v12;
            if ( v12 > 0 )
              v5 = (unsigned __int16)v12 | 0x80070000;
            if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
              ComTraceMessageT<long>(
                (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
                (unsigned int)"CToken::CompareCapabilitySids",
                547,
                0,
                (__int64)L"%!HRESULT!",
                v5);
            if ( v5 < 0 )
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x224,
                (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
                (const char *)(unsigned int)v5,
                ReturnLengthb);
            v13 = v11;
          }
          LocalFree(v13);
LABEL_47:
          LocalFree(v7);
          return (unsigned int)v5;
        }
        v5 = -2147024882;
        v9 = 542;
      }
      else
      {
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          ComTraceMessageT<long>(
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
            (unsigned int)"CToken::CompareCapabilitySids",
            536,
            0,
            (__int64)L"%!HRESULT!",
            v5);
        if ( v5 >= 0 )
          goto LABEL_47;
        v9 = 537;
      }
    }
    else
    {
      v8 = GetLastError();
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        ComTraceMessageT<long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
          (unsigned int)"CToken::CompareCapabilitySids",
          528,
          0,
          (__int64)L"%!HRESULT!",
          v5);
      if ( v5 >= 0 )
        goto LABEL_47;
      v9 = 529;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
      (const char *)(unsigned int)v5,
      ReturnLengtha);
    goto LABEL_47;
  }
  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    ComTraceMessageT<long>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
      (unsigned int)"CToken::CompareCapabilitySids",
      517,
      0,
      (__int64)L"%!HRESULT!",
      v5);
  if ( v5 < 0 )
  {
    v6 = 518;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
      (const char *)(unsigned int)v5,
      ReturnLength);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18008ab28  mov     rax, rsp
0x18008ab2b  mov     [rax+8], rbx
0x18008ab2f  mov     [rax+10h], rbp
0x18008ab33  mov     [rax+18h], r8b
0x18008ab37  push    rsi
0x18008ab38  push    rdi
0x18008ab39  push    r15
0x18008ab3b  sub     rsp, 30h
0x18008ab3f  xor     r9d, r9d; TokenInformationLength
0x18008ab42  mov     dword ptr [rax+18h], 0
0x18008ab49  mov     rbp, rdx
0x18008ab4c  lea     rax, [rax+18h]
0x18008ab50  mov     rdi, rcx
0x18008ab53  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18008ab58  mov     rcx, [rcx+48h]; TokenHandle
0x18008ab5c  xor     r8d, r8d; TokenInformation
0x18008ab5f  lea     edx, [r9+1Eh]; TokenInformationClass
0x18008ab63  call    cs:__imp_GetTokenInformation
0x18008ab6a  nop     dword ptr [rax+rax+00h]
0x18008ab6f  call    cs:__imp_GetLastError
0x18008ab76  nop     dword ptr [rax+rax+00h]
0x18008ab7b  mov     ebx, eax
0x18008ab7d  mov     r15d, 80070000h
0x18008ab83  test    eax, eax
0x18008ab85  jle     short loc_18008AB8D
0x18008ab87  movzx   ebx, ax
0x18008ab8a  or      ebx, r15d
0x18008ab8d  cmp     ebx, 8007007Ah
0x18008ab93  jz      short loc_18008AC04
0x18008ab95  mov     eax, cs:dword_1801574B8
0x18008ab9b  test    eax, eax
0x18008ab9d  jnz     short loc_18008ABB2
0x18008ab9f  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18008aba5  jz      short loc_18008ABDE
0x18008aba7  xor     ecx, ecx
0x18008aba9  call    IsWppLevelEnabled
0x18008abae  test    al, al
0x18008abb0  jz      short loc_18008ABDE
0x18008abb2  lea     rax, aHresult; "%!HRESULT!"
0x18008abb9  mov     [rsp+48h+var_20], ebx
0x18008abbd  xor     r9d, r9d
0x18008abc0  mov     [rsp+48h+ReturnLength], rax; int
0x18008abc5  mov     r8d, 205h
0x18008abcb  lea     rdx, aCtokenComparec; "CToken::CompareCapabilitySids"
0x18008abd2  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18008abd9  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18008abde  test    ebx, ebx
0x18008abe0  jns     loc_18008AEA3
0x18008abe6  mov     edx, 206h; void *
0x18008abeb  mov     rcx, [rsp+48h]; this
0x18008abf0  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18008abf7  mov     r9d, ebx; char *
0x18008abfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008abff  jmp     loc_18008AEA3
0x18008ac04  mov     edx, dword ptr [rsp+48h+uBytes]; uBytes
0x18008ac08  xor     ecx, ecx; uFlags
0x18008ac0a  call    cs:__imp_LocalAlloc
0x18008ac11  nop     dword ptr [rax+rax+00h]
0x18008ac16  mov     rsi, rax
0x18008ac19  test    rax, rax
0x18008ac1c  jnz     short loc_18008AC2A
0x18008ac1e  mov     ebx, 8007000Eh
0x18008ac23  mov     edx, 20Bh
0x18008ac28  jmp     short loc_18008ABEB
0x18008ac2a  mov     r9d, dword ptr [rsp+48h+uBytes]; TokenInformationLength
0x18008ac2f  lea     rax, [rsp+48h+uBytes]
0x18008ac34  mov     rcx, [rdi+48h]; TokenHandle
0x18008ac38  mov     r8, rsi; TokenInformation
0x18008ac3b  mov     edx, 1Eh; TokenInformationClass
0x18008ac40  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18008ac45  call    cs:__imp_GetTokenInformation
0x18008ac4c  nop     dword ptr [rax+rax+00h]
0x18008ac51  test    eax, eax
0x18008ac53  jnz     short loc_18008ACC8
0x18008ac55  call    cs:__imp_GetLastError
0x18008ac5c  nop     dword ptr [rax+rax+00h]
0x18008ac61  mov     ebx, eax
0x18008ac63  test    eax, eax
0x18008ac65  jle     short loc_18008AC6D
0x18008ac67  movzx   ebx, ax
0x18008ac6a  or      ebx, r15d
0x18008ac6d  mov     eax, cs:dword_1801574B8
0x18008ac73  test    eax, eax
0x18008ac75  jnz     short loc_18008AC8A
0x18008ac77  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18008ac7d  jz      short loc_18008ACB6
0x18008ac7f  xor     ecx, ecx
0x18008ac81  call    IsWppLevelEnabled
0x18008ac86  test    al, al
0x18008ac88  jz      short loc_18008ACB6
0x18008ac8a  lea     rax, aHresult; "%!HRESULT!"
0x18008ac91  mov     [rsp+48h+var_20], ebx
0x18008ac95  xor     r9d, r9d
0x18008ac98  mov     [rsp+48h+ReturnLength], rax
0x18008ac9d  mov     r8d, 210h
0x18008aca3  lea     rdx, aCtokenComparec; "CToken::CompareCapabilitySids"
0x18008acaa  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18008acb1  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18008acb6  test    ebx, ebx
0x18008acb8  jns     loc_18008AE94
0x18008acbe  mov     edx, 211h
0x18008acc3  jmp     loc_18008AD62
0x18008acc8  mov     rcx, [rbp+48h]; TokenHandle
0x18008accc  lea     rax, [rsp+48h+uBytes]
0x18008acd1  xor     r9d, r9d; TokenInformationLength
0x18008acd4  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18008acd9  xor     r8d, r8d; TokenInformation
0x18008acdc  lea     edx, [r9+1Eh]; TokenInformationClass
0x18008ace0  call    cs:__imp_GetTokenInformation
0x18008ace7  nop     dword ptr [rax+rax+00h]
0x18008acec  call    cs:__imp_GetLastError
0x18008acf3  nop     dword ptr [rax+rax+00h]
0x18008acf8  mov     ebx, eax
0x18008acfa  test    eax, eax
0x18008acfc  jle     short loc_18008AD04
0x18008acfe  movzx   ebx, ax
0x18008ad01  or      ebx, r15d
0x18008ad04  cmp     ebx, 8007007Ah
0x18008ad0a  jz      short loc_18008AD7B
0x18008ad0c  mov     eax, cs:dword_1801574B8
0x18008ad12  test    eax, eax
0x18008ad14  jnz     short loc_18008AD29
0x18008ad16  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18008ad1c  jz      short loc_18008AD55
0x18008ad1e  xor     ecx, ecx
0x18008ad20  call    IsWppLevelEnabled
0x18008ad25  test    al, al
0x18008ad27  jz      short loc_18008AD55
0x18008ad29  lea     rax, aHresult; "%!HRESULT!"
0x18008ad30  mov     [rsp+48h+var_20], ebx
0x18008ad34  xor     r9d, r9d
0x18008ad37  mov     [rsp+48h+ReturnLength], rax; int
0x18008ad3c  mov     r8d, 218h
0x18008ad42  lea     rdx, aCtokenComparec; "CToken::CompareCapabilitySids"
0x18008ad49  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18008ad50  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18008ad55  test    ebx, ebx
0x18008ad57  jns     loc_18008AE94
0x18008ad5d  mov     edx, 219h; void *
0x18008ad62  mov     rcx, [rsp+48h]; this
0x18008ad67  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18008ad6e  mov     r9d, ebx; char *
0x18008ad71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ad76  jmp     loc_18008AE94
0x18008ad7b  mov     edx, dword ptr [rsp+48h+uBytes]; uBytes
0x18008ad7f  xor     ecx, ecx; uFlags
0x18008ad81  call    cs:__imp_LocalAlloc
0x18008ad88  nop     dword ptr [rax+rax+00h]
0x18008ad8d  mov     rdi, rax
0x18008ad90  test    rax, rax
0x18008ad93  jnz     short loc_18008ADA1
0x18008ad95  mov     ebx, 8007000Eh
0x18008ad9a  mov     edx, 21Eh
0x18008ad9f  jmp     short loc_18008AD62
0x18008ada1  mov     r9d, dword ptr [rsp+48h+uBytes]; TokenInformationLength
0x18008ada6  lea     rax, [rsp+48h+uBytes]
0x18008adab  mov     rcx, [rbp+48h]; TokenHandle
0x18008adaf  mov     r8, rdi; TokenInformation
0x18008adb2  mov     edx, 1Eh; TokenInformationClass
0x18008adb7  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18008adbc  call    cs:__imp_GetTokenInformation
0x18008adc3  nop     dword ptr [rax+rax+00h]
0x18008adc8  test    eax, eax
0x18008adca  jnz     loc_18008AE5F
0x18008add0  call    cs:__imp_GetLastError
0x18008add7  nop     dword ptr [rax+rax+00h]
0x18008addc  mov     ebx, eax
0x18008adde  test    eax, eax
0x18008ade0  jle     short loc_18008ADE8
0x18008ade2  movzx   ebx, ax
0x18008ade5  or      ebx, r15d
0x18008ade8  mov     eax, cs:dword_1801574B8
0x18008adee  test    eax, eax
0x18008adf0  jnz     short loc_18008AE05
0x18008adf2  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18008adf8  jz      short loc_18008AE31
0x18008adfa  xor     ecx, ecx
0x18008adfc  call    IsWppLevelEnabled
0x18008ae01  test    al, al
0x18008ae03  jz      short loc_18008AE31
0x18008ae05  lea     rax, aHresult; "%!HRESULT!"
0x18008ae0c  mov     [rsp+48h+var_20], ebx
0x18008ae10  xor     r9d, r9d
0x18008ae13  mov     [rsp+48h+ReturnLength], rax; int
0x18008ae18  mov     r8d, 223h
0x18008ae1e  lea     rdx, aCtokenComparec; "CToken::CompareCapabilitySids"
0x18008ae25  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18008ae2c  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18008ae31  test    ebx, ebx
0x18008ae33  jns     short loc_18008AE4E
0x18008ae35  mov     rcx, [rsp+48h]; this
0x18008ae3a  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18008ae41  mov     r9d, ebx; char *
0x18008ae44  mov     edx, 224h; void *
0x18008ae49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ae4e  mov     rcx, rdi; hMem
0x18008ae51  call    cs:__imp_LocalFree
0x18008ae58  nop     dword ptr [rax+rax+00h]
0x18008ae5d  jmp     short loc_18008AE94
0x18008ae5f  mov     r9d, [rdi]
0x18008ae62  lea     r8, [rdi+8]
0x18008ae66  mov     edx, [rsi]
0x18008ae68  lea     rcx, [rsi+8]
0x18008ae6c  mov     ebx, 1
0x18008ae71  mov     [rsp+48h+var_20], ebx
0x18008ae75  mov     byte ptr [rsp+48h+ReturnLength], 0
0x18008ae7a  call    ?CompareSidAndAttributeArrays@@YA_NPEAU_SID_AND_ATTRIBUTES@@K0K_NW4RuntimeBehavior@AppModel@@@Z; CompareSidAndAttributeArrays(_SID_AND_ATTRIBUTES *,ulong,_SID_AND_ATTRIBUTES *,ulong,bool,AppModel::RuntimeBehavior)
0x18008ae7f  mov     rcx, rdi; hMem
0x18008ae82  test    al, al
0x18008ae84  jz      short loc_18008AE51
0x18008ae86  call    cs:__imp_LocalFree
0x18008ae8d  nop     dword ptr [rax+rax+00h]
0x18008ae92  xor     ebx, ebx
0x18008ae94  mov     rcx, rsi; hMem
0x18008ae97  call    cs:__imp_LocalFree
0x18008ae9e  nop     dword ptr [rax+rax+00h]
0x18008aea3  mov     rbp, [rsp+48h+arg_8]
0x18008aea8  mov     eax, ebx
0x18008aeaa  mov     rbx, [rsp+48h+arg_0]
0x18008aeaf  add     rsp, 30h
0x18008aeb3  pop     r15
0x18008aeb5  pop     rdi
0x18008aeb6  pop     rsi
0x18008aeb7  retn
```
