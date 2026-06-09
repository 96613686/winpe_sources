# CServerTableEntry::WaitForService(CClassData *,CToken *,void *,int)

- ea: `0x18007a9c4`
- end: `0x18007adca`
- name: `?WaitForService@CServerTableEntry@@QEAAJPEAVCClassData@@PEAVCToken@@PEAXH@Z`
- size: `1030`
- prototype: `int(CServerTableEntry *__hidden this, struct CClassData *, struct CToken *, void *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180067898`

## callees

- `0x180018344`
- `0x180025250`
- `0x180025310`
- `0x18002ba28`
- `0x18002f8cc`
- `0x180034540`
- `0x18007a9c4`
- `0x18007e3d4`
- `0x180081210`
- `0x1800a1e98`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007aa2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007aa2b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18007aa1f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18007aa1f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007a9fb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007a9fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ab9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007aca3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007acb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ad68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ab9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007aca3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007acb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ad68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007abdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007acf7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007abdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007acf7`

## string_xrefs

- `0x18007aa6e`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18007aafd`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18007abf1`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18007ac6a`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18007ad0d`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18007ad34`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18007ad74`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18007ad9f`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18007aa67`: `CToken::Impersonate`
- `0x18007abf8`: `Stopping NT service server ClassIdentifier:%ws PID:%x`
- `0x18007aaf2`: `CServerTableEntry::WaitForService`
- `0x18007abe5`: `CServerTableEntry::WaitForService`
- `0x18007ac5f`: `CServerTableEntry::WaitForService`
- `0x18007ad01`: `CServerTableEntry::WaitForService`
- `0x18007ad14`: `Wait for NT service server timed out ClassIdentifier:%ws PID:%x`

## pseudocode

```c
__int64 __fastcall CServerTableEntry::WaitForService(
        CServerTableEntry *this,
        struct CClassData *a2,
        HANDLE *a3,
        void *a4,
        int a5)
{
  int v5; // r15d
  BOOL v10; // edi
  signed int LastError; // ebx
  bool v12; // sf
  unsigned int v13; // eax
  int v14; // ecx
  __int64 v15; // rax
  void (__fastcall *v16)(CServerTableEntry *, HSTRING *); // rbx
  __int64 v17; // rax
  unsigned int v18; // r10d
  __int64 v19; // rax
  void (__fastcall *v20)(CServerTableEntry *, HSTRING *); // rbx
  unsigned int v22; // [rsp+20h] [rbp-48h]
  __int64 v23; // [rsp+28h] [rbp-40h]
  char *v24; // [rsp+40h] [rbp-28h] BYREF
  int v25; // [rsp+48h] [rbp-20h] BYREF
  int v26; // [rsp+4Ch] [rbp-1Ch] BYREF
  HSTRING string[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  v24 = (char *)2147943462LL;
  v5 = 0;
  while ( WaitForSingleObject(a4, 0x7530u) )
  {
    if ( NtCurrentTeb()->IsImpersonating )
    {
      LastError = -2147418113;
LABEL_52:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5D,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (const char *)(unsigned int)LastError,
        v22);
      return (unsigned int)LastError;
    }
    v10 = SetThreadToken(0, a3[9]);
    if ( !v10 )
    {
      LastError = GetLastError();
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
      {
        LODWORD(v23) = LastError;
        ComTraceMessageT<int>(
          (__int64)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
          (__int64)"CToken::Impersonate",
          0x525u,
          0,
          (__int64)L"%!WINERROR!",
          v23);
      }
      v12 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v12 = LastError < 0;
      }
      if ( v12 )
        goto LABEL_52;
    }
    v13 = (*(__int64 (__fastcall **)(struct CClassData *, __int64, char *, char **))(*(_QWORD *)a2 + 40LL))(
            a2,
            4,
            (char *)&v24 + 4,
            &v24);
    if ( v13 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xD62,
                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                    (const char *)v13,
                    v22);
      CToken::Revert((CToken *)a3, v10);
      return (unsigned int)LastError;
    }
    CToken::Revert((CToken *)a3, v10);
    v14 = (int)v24;
    if ( (int)v24 >= 0 )
      goto LABEL_25;
    if ( (unsigned int)((_DWORD)v24 + 2147023835) > 1 )
    {
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        ComTraceMessageT<long>(
          (__int64)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (__int64)"CServerTableEntry::WaitForService",
          0xD68u,
          0,
          (__int64)L"hr=%!HRESULT!",
          (unsigned int)v24);
      v14 = (int)v24;
    }
    if ( v14 >= 0 )
    {
LABEL_25:
      if ( HIDWORD(v24) != 2 && HIDWORD(v24) != 4 && HIDWORD(v24) != 5 )
      {
        if ( (unsigned int)(HIDWORD(v24) - 6) <= 1 && !a5 )
        {
          v26 = 0;
          if ( (int)CToken::Impersonate((CToken *)a3, 1, &v26) >= 0 )
          {
            v15 = *(_QWORD *)this;
            string[0] = 0;
            v16 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v15 + 32);
            WindowsDeleteString(0);
            string[0] = 0;
            v16(this, string);
            if ( dword_18014E4B8
              || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_18014E4B8 + 1)) )
            {
              WindowsGetStringRawBuffer(string[0], 0);
              ComTraceMessageT<unsigned __int64,unsigned long>(
                (__int64)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                (__int64)"CServerTableEntry::WaitForService",
                0xDA1u,
                1,
                (__int64)L"Stopping NT service server ClassIdentifier:%ws PID:%x");
            }
            v17 = *(_QWORD *)a2;
            v25 = 0;
            v18 = (*(__int64 (__fastcall **)(struct CClassData *, __int64, char *, int *))(v17 + 40))(
                    a2,
                    1,
                    (char *)&v24 + 4,
                    &v25);
            if ( (v18 || v25 < 0)
              && (dword_18014E4B8 || gfEnableTracing
                                  && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
            {
              v22 = 0;
              ComTraceMessage(
                v18,
                "onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                "CServerTableEntry::WaitForService",
                3498);
            }
            CToken::Revert((CToken *)a3, v26);
            WindowsDeleteString(string[0]);
          }
        }
LABEL_42:
        v19 = *(_QWORD *)this;
        string[0] = 0;
        v20 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v19 + 32);
        WindowsDeleteString(0);
        string[0] = 0;
        v20(this, string);
        if ( dword_18014E4B8
          || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_18014E4B8 + 1)) )
        {
          WindowsGetStringRawBuffer(string[0], 0);
          ComTraceMessageT<unsigned __int64,unsigned long>(
            (__int64)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
            (__int64)"CServerTableEntry::WaitForService",
            0xDB7u,
            1,
            (__int64)L"Wait for NT service server timed out ClassIdentifier:%ws PID:%x");
        }
        LastError = (int)v24;
        if ( (int)v24 >= 0 )
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0xDBA,
                        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                        (const char *)0x5B4,
                        v22);
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDB9,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
            (const char *)(unsigned int)v24,
            v22);
        WindowsDeleteString(string[0]);
        return (unsigned int)LastError;
      }
    }
    else if ( (unsigned int)(v14 + 2147023835) > 1 )
    {
      goto LABEL_42;
    }
    if ( (unsigned int)++v5 >= 4 )
      goto LABEL_42;
  }
  return 0;
}

```

## disassembly

```asm
0x18007a9c4  push    rbp
0x18007a9c6  push    rbx
0x18007a9c7  push    rsi
0x18007a9c8  push    rdi
0x18007a9c9  push    r12
0x18007a9cb  push    r13
0x18007a9cd  push    r14
0x18007a9cf  push    r15
0x18007a9d1  mov     rbp, rsp
0x18007a9d4  sub     rsp, 68h
0x18007a9d8  xor     edi, edi
0x18007a9da  mov     dword ptr [rbp+var_28], 80070426h
0x18007a9e1  mov     dword ptr [rbp+var_28+4], edi
0x18007a9e4  mov     r15d, edi
0x18007a9e7  mov     r13, r9
0x18007a9ea  mov     rsi, r8
0x18007a9ed  mov     r12, rdx
0x18007a9f0  mov     r14, rcx
0x18007a9f3  mov     edx, 7530h; dwMilliseconds
0x18007a9f8  mov     rcx, r13; hHandle
0x18007a9fb  call    cs:__imp_WaitForSingleObject
0x18007aa01  test    eax, eax
0x18007aa03  jz      loc_18007ADB7
0x18007aa09  mov     eax, gs:179Ch
0x18007aa11  test    eax, eax
0x18007aa13  jnz     loc_18007AD96
0x18007aa19  mov     rdx, [rsi+48h]; Token
0x18007aa1d  xor     ecx, ecx; Thread
0x18007aa1f  call    cs:__imp_SetThreadToken
0x18007aa25  mov     edi, eax
0x18007aa27  test    eax, eax
0x18007aa29  jnz     short loc_18007AA8F
0x18007aa2b  call    cs:__imp_GetLastError
0x18007aa31  mov     ecx, cs:dword_18014E4B8
0x18007aa37  mov     ebx, eax
0x18007aa39  test    ecx, ecx
0x18007aa3b  jnz     short loc_18007AA4E
0x18007aa3d  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x18007aa43  jz      short loc_18007AA7A
0x18007aa45  call    IsWppLevelEnabled
0x18007aa4a  test    al, al
0x18007aa4c  jz      short loc_18007AA7A
0x18007aa4e  lea     rax, aWinerror; "%!WINERROR!"
0x18007aa55  mov     dword ptr [rsp+68h+var_40], ebx
0x18007aa59  xor     r9d, r9d
0x18007aa5c  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x18007aa61  mov     r8d, 525h
0x18007aa67  lea     rdx, aCtokenImperson; "CToken::Impersonate"
0x18007aa6e  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18007aa75  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x18007aa7a  test    ebx, ebx
0x18007aa7c  jle     short loc_18007AA89
0x18007aa7e  movzx   ebx, bx
0x18007aa81  or      ebx, 80070000h
0x18007aa87  test    ebx, ebx
0x18007aa89  js      loc_18007AD9B
0x18007aa8f  mov     rax, [r12]
0x18007aa93  lea     r9, [rbp+var_28]
0x18007aa97  lea     r8, [rbp+var_28+4]
0x18007aa9b  mov     edx, 4
0x18007aaa0  mov     rcx, r12
0x18007aaa3  mov     rax, [rax+28h]
0x18007aaa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aaac  test    eax, eax
0x18007aaae  jnz     loc_18007AD70
0x18007aab4  mov     edx, edi; int
0x18007aab6  mov     rcx, rsi; this
0x18007aab9  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x18007aabe  mov     ecx, dword ptr [rbp+var_28]
0x18007aac1  xor     edi, edi
0x18007aac3  test    ecx, ecx
0x18007aac5  jns     short loc_18007AB36
0x18007aac7  lea     eax, [rcx+7FF8FBDBh]
0x18007aacd  cmp     eax, 1
0x18007aad0  jbe     short loc_18007AB21
0x18007aad2  mov     eax, cs:dword_18014E4B8
0x18007aad8  test    eax, eax
0x18007aada  jnz     short loc_18007AAEF
0x18007aadc  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18007aae2  jz      short loc_18007AB1E
0x18007aae4  xor     ecx, ecx
0x18007aae6  call    IsWppLevelEnabled
0x18007aaeb  test    al, al
0x18007aaed  jz      short loc_18007AB1E
0x18007aaef  mov     eax, dword ptr [rbp+var_28]
0x18007aaf2  lea     rdx, aCservertableen_7; "CServerTableEntry::WaitForService"
0x18007aaf9  mov     dword ptr [rsp+68h+var_40], eax
0x18007aafd  lea     rcx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18007ab04  lea     rax, aHrHresult_0; "hr=%!HRESULT!"
0x18007ab0b  xor     r9d, r9d
0x18007ab0e  mov     r8d, 0D68h
0x18007ab14  mov     qword ptr [rsp+68h+var_48], rax
0x18007ab19  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18007ab1e  mov     ecx, dword ptr [rbp+var_28]
0x18007ab21  test    ecx, ecx
0x18007ab23  jns     short loc_18007AB36
0x18007ab25  lea     eax, [rcx+7FF8FBDBh]
0x18007ab2b  cmp     eax, 1
0x18007ab2e  ja      loc_18007ACA9
0x18007ab34  jmp     short loc_18007AB48
0x18007ab36  mov     eax, dword ptr [rbp+var_28+4]
0x18007ab39  sub     eax, 2
0x18007ab3c  jz      short loc_18007AB48
0x18007ab3e  sub     eax, 2
0x18007ab41  jz      short loc_18007AB48
0x18007ab43  sub     eax, 1
0x18007ab46  jnz     short loc_18007AB5A
0x18007ab48  inc     r15d
0x18007ab4b  cmp     r15d, 4
0x18007ab4f  jb      loc_18007A9F3
0x18007ab55  jmp     loc_18007ACA9
0x18007ab5a  sub     eax, 1
0x18007ab5d  jz      short loc_18007AB68
0x18007ab5f  cmp     eax, 1
0x18007ab62  jnz     loc_18007ACA9
0x18007ab68  cmp     [rbp+arg_20], edi
0x18007ab6b  jnz     loc_18007ACA9
0x18007ab71  lea     r8, [rbp+var_1C]; int *
0x18007ab75  mov     [rbp+var_1C], edi
0x18007ab78  mov     edx, 1; int
0x18007ab7d  mov     rcx, rsi; this
0x18007ab80  call    ?Impersonate@CToken@@UEAAJHPEAH@Z; CToken::Impersonate(int,int *)
0x18007ab85  test    eax, eax
0x18007ab87  js      loc_18007ACA9
0x18007ab8d  mov     rax, [r14]
0x18007ab90  xor     ecx, ecx; string
0x18007ab92  mov     [rbp+string], rdi
0x18007ab96  mov     rbx, [rax+20h]
0x18007ab9a  call    cs:__imp_WindowsDeleteString
0x18007aba0  lea     rdx, [rbp+string]
0x18007aba4  mov     [rbp+string], rdi
0x18007aba8  mov     rcx, r14
0x18007abab  mov     rax, rbx
0x18007abae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007abb3  mov     eax, cs:dword_18014E4B8
0x18007abb9  test    eax, eax
0x18007abbb  jnz     short loc_18007ABD1
0x18007abbd  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18007abc3  jz      short loc_18007AC15
0x18007abc5  lea     ecx, [rax+1]
0x18007abc8  call    IsWppLevelEnabled
0x18007abcd  test    al, al
0x18007abcf  jz      short loc_18007AC15
0x18007abd1  mov     rcx, [rbp+string]; string
0x18007abd5  xor     edx, edx; length
0x18007abd7  mov     ebx, [r14+10h]
0x18007abdb  call    cs:__imp_WindowsGetStringRawBuffer
0x18007abe1  mov     [rsp+68h+var_38], ebx
0x18007abe5  lea     rdx, aCservertableen_7; "CServerTableEntry::WaitForService"
0x18007abec  mov     [rsp+68h+var_40], rax
0x18007abf1  lea     rcx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18007abf8  lea     rax, aStoppingNtServ; "Stopping NT service server ClassIdentif"...
0x18007abff  mov     r9d, 1
0x18007ac05  mov     r8d, 0DA1h
0x18007ac0b  mov     qword ptr [rsp+68h+var_48], rax
0x18007ac10  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x18007ac15  mov     rax, [r12]
0x18007ac19  lea     r9, [rbp+var_20]
0x18007ac1d  lea     r8, [rbp+var_28+4]
0x18007ac21  mov     [rbp+var_20], edi
0x18007ac24  mov     edx, 1
0x18007ac29  mov     rcx, r12
0x18007ac2c  mov     rax, [rax+28h]
0x18007ac30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ac35  mov     r10d, eax
0x18007ac38  test    eax, eax
0x18007ac3a  jnz     short loc_18007AC41
0x18007ac3c  cmp     [rbp+var_20], edi
0x18007ac3f  jge     short loc_18007AC94
0x18007ac41  mov     ecx, cs:dword_18014E4B8
0x18007ac47  test    ecx, ecx
0x18007ac49  jnz     short loc_18007AC5C
0x18007ac4b  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18007ac51  jz      short loc_18007AC94
0x18007ac53  call    IsWppLevelEnabled
0x18007ac58  test    al, al
0x18007ac5a  jz      short loc_18007AC94
0x18007ac5c  mov     eax, [rbp+var_20]
0x18007ac5f  lea     r8, aCservertableen_7; "CServerTableEntry::WaitForService"
0x18007ac66  mov     [rsp+68h+var_30], eax
0x18007ac6a  lea     rdx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18007ac71  mov     [rsp+68h+var_38], r10d
0x18007ac76  lea     rax, aRpcstatusWiner; "rpcstatus=%!WINERROR! hr=%!HRESULT!"
0x18007ac7d  mov     [rsp+68h+var_40], rax
0x18007ac82  mov     r9d, 0DAAh
0x18007ac88  mov     ecx, r10d
0x18007ac8b  mov     [rsp+68h+var_48], edi
0x18007ac8f  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18007ac94  mov     edx, [rbp+var_1C]; int
0x18007ac97  mov     rcx, rsi; this
0x18007ac9a  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x18007ac9f  mov     rcx, [rbp+string]; string
0x18007aca3  call    cs:__imp_WindowsDeleteString
0x18007aca9  mov     rax, [r14]
0x18007acac  xor     ecx, ecx; string
0x18007acae  mov     [rbp+string], rdi
0x18007acb2  mov     rbx, [rax+20h]
0x18007acb6  call    cs:__imp_WindowsDeleteString
0x18007acbc  lea     rdx, [rbp+string]
0x18007acc0  mov     [rbp+string], rdi
0x18007acc4  mov     rcx, r14
0x18007acc7  mov     rax, rbx
0x18007acca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007accf  mov     eax, cs:dword_18014E4B8
0x18007acd5  test    eax, eax
0x18007acd7  jnz     short loc_18007ACED
0x18007acd9  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18007acdf  jz      short loc_18007AD31
0x18007ace1  lea     ecx, [rax+1]
0x18007ace4  call    IsWppLevelEnabled
0x18007ace9  test    al, al
0x18007aceb  jz      short loc_18007AD31
0x18007aced  mov     rcx, [rbp+string]; string
0x18007acf1  xor     edx, edx; length
0x18007acf3  mov     ebx, [r14+10h]
0x18007acf7  call    cs:__imp_WindowsGetStringRawBuffer
0x18007acfd  mov     [rsp+68h+var_38], ebx
0x18007ad01  lea     rdx, aCservertableen_7; "CServerTableEntry::WaitForService"
0x18007ad08  mov     [rsp+68h+var_40], rax
0x18007ad0d  lea     rcx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18007ad14  lea     rax, aWaitForNtServi; "Wait for NT service server timed out Cl"...
0x18007ad1b  mov     r9d, 1
0x18007ad21  mov     r8d, 0DB7h
0x18007ad27  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x18007ad2c  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x18007ad31  mov     ebx, dword ptr [rbp+var_28]
0x18007ad34  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18007ad3b  mov     rcx, [rbp+40h]; this
0x18007ad3f  test    ebx, ebx
0x18007ad41  jns     short loc_18007AD52
0x18007ad43  mov     r9d, ebx; char *
0x18007ad46  mov     edx, 0DB9h; void *
0x18007ad4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ad50  jmp     short loc_18007AD64
0x18007ad52  mov     r9d, 5B4h; char *
0x18007ad58  mov     edx, 0DBAh; void *
0x18007ad5d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007ad62  mov     ebx, eax
0x18007ad64  mov     rcx, [rbp+string]; string
0x18007ad68  call    cs:__imp_WindowsDeleteString
0x18007ad6e  jmp     short loc_18007ADB3
0x18007ad70  mov     rcx, [rbp+40h]; this
0x18007ad74  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18007ad7b  mov     r9d, eax; char *
0x18007ad7e  mov     edx, 0D62h; void *
0x18007ad83  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007ad88  mov     edx, edi; int
0x18007ad8a  mov     rcx, rsi; this
0x18007ad8d  mov     ebx, eax
0x18007ad8f  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x18007ad94  jmp     short loc_18007ADB3
0x18007ad96  mov     ebx, 8000FFFFh
0x18007ad9b  mov     rcx, [rbp+40h]; this
0x18007ad9f  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18007ada6  mov     r9d, ebx; char *
0x18007ada9  mov     edx, 0D5Dh; void *
0x18007adae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007adb3  mov     eax, ebx
0x18007adb5  jmp     short loc_18007ADB9
0x18007adb7  xor     eax, eax
0x18007adb9  add     rsp, 68h
0x18007adbd  pop     r15
0x18007adbf  pop     r14
0x18007adc1  pop     r13
0x18007adc3  pop     r12
0x18007adc5  pop     rdi
0x18007adc6  pop     rsi
0x18007adc7  pop     rbx
0x18007adc8  pop     rbp
0x18007adc9  retn
```
