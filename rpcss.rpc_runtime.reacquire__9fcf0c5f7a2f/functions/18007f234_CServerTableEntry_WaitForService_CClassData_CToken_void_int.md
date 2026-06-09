# CServerTableEntry::WaitForService(CClassData *,CToken *,void *,int)

- ea: `0x18007f234`
- end: `0x18007f600`
- name: `?WaitForService@CServerTableEntry@@QEAAJPEAVCClassData@@PEAVCToken@@PEAXH@Z`
- size: `972`
- prototype: `int(CServerTableEntry *__hidden this, struct CClassData *, struct CToken *, void *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006c680`

## callees

- `0x18001c624`
- `0x1800210f8`
- `0x180025950`
- `0x18002f5a0`
- `0x18002f670`
- `0x180034260`
- `0x18007f234`
- `0x18008172c`
- `0x1800855d8`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007f26d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007f26d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f3aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f4c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f4dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f59b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f3aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f4c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f4dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f59b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f3f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f524`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f3f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f524`

## string_xrefs

- `0x18007f30d`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18007f40e`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18007f489`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18007f540`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18007f567`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18007f5ad`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18007f5d4`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18007f302`: `CServerTableEntry::WaitForService`
- `0x18007f402`: `CServerTableEntry::WaitForService`
- `0x18007f47e`: `CServerTableEntry::WaitForService`
- `0x18007f534`: `CServerTableEntry::WaitForService`
- `0x18007f547`: `Wait for NT service server timed out ClassIdentifier:%ws PID:%x`
- `0x18007f415`: `Stopping NT service server ClassIdentifier:%ws PID:%x`

## pseudocode

```c
__int64 __fastcall CServerTableEntry::WaitForService(
        CServerTableEntry *this,
        struct CClassData *a2,
        struct CToken *a3,
        void *a4,
        int a5)
{
  int v5; // esi
  int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  int v13; // ecx
  __int64 v14; // rax
  void (__fastcall *v15)(CServerTableEntry *, HSTRING *); // rbx
  __int64 v16; // rax
  unsigned int v17; // r10d
  __int64 v18; // rax
  void (__fastcall *v19)(CServerTableEntry *, HSTRING *); // rbx
  unsigned int v21[2]; // [rsp+20h] [rbp-48h]
  __int64 v22; // [rsp+28h] [rbp-40h]
  char *v23; // [rsp+40h] [rbp-28h] BYREF
  int v24; // [rsp+48h] [rbp-20h] BYREF
  int v25; // [rsp+4Ch] [rbp-1Ch] BYREF
  HSTRING string[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  v23 = (char *)2147943462LL;
  v5 = 0;
  while ( WaitForSingleObject(a4, 0x7530u) )
  {
    v24 = 0;
    v10 = CToken::Impersonate(a3, 1, &v24);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5D,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (const char *)(unsigned int)v10,
        v21[0]);
      return v11;
    }
    v12 = (*(__int64 (__fastcall **)(struct CClassData *, __int64, char *, char **))(*(_QWORD *)a2 + 40LL))(
            a2,
            4,
            (char *)&v23 + 4,
            &v23);
    if ( v12 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xD62,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
              (const char *)v12,
              v21[0]);
      CToken::Revert(a3, v24);
      return v11;
    }
    CToken::Revert(a3, v24);
    v13 = (int)v23;
    if ( (int)v23 >= 0 )
      goto LABEL_17;
    if ( (unsigned int)((_DWORD)v23 + 2147023835) > 1 )
    {
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        LODWORD(v22) = (_DWORD)v23;
        ComTraceMessageT<long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (unsigned int)"CServerTableEntry::WaitForService",
          3432,
          0,
          (__int64)L"hr=%!HRESULT!",
          v22);
      }
      v13 = (int)v23;
    }
    if ( v13 >= 0 )
    {
LABEL_17:
      if ( HIDWORD(v23) != 2 && HIDWORD(v23) != 4 && HIDWORD(v23) != 5 )
      {
        if ( (unsigned int)(HIDWORD(v23) - 6) <= 1 && !a5 )
        {
          v25 = 0;
          if ( (int)CToken::Impersonate(a3, 1, &v25) >= 0 )
          {
            v14 = *(_QWORD *)this;
            string[0] = 0;
            v15 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v14 + 32);
            WindowsDeleteString(0);
            string[0] = 0;
            v15(this, string);
            if ( dword_1801574B8
              || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_1801574B8 + 1)) )
            {
              WindowsGetStringRawBuffer(string[0], 0);
              ComTraceMessageT<unsigned __int64,unsigned long>(
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                (unsigned int)"CServerTableEntry::WaitForService",
                3489,
                1,
                (__int64)L"Stopping NT service server ClassIdentifier:%ws PID:%x");
            }
            v16 = *(_QWORD *)a2;
            v24 = 0;
            v17 = (*(__int64 (__fastcall **)(struct CClassData *, __int64, char *, int *))(v16 + 40))(
                    a2,
                    1,
                    (char *)&v23 + 4,
                    &v24);
            if ( (v17 || v24 < 0)
              && (dword_1801574B8 || gfEnableTracing
                                  && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
            {
              v21[0] = 0;
              ComTraceMessage(
                v17,
                "onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                "CServerTableEntry::WaitForService",
                3498,
                *(_QWORD *)v21,
                L"rpcstatus=%!WINERROR! hr=%!HRESULT!",
                v17,
                v24);
            }
            CToken::Revert(a3, v25);
            WindowsDeleteString(string[0]);
          }
        }
LABEL_34:
        v18 = *(_QWORD *)this;
        string[0] = 0;
        v19 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v18 + 32);
        WindowsDeleteString(0);
        string[0] = 0;
        v19(this, string);
        if ( dword_1801574B8
          || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_1801574B8 + 1)) )
        {
          WindowsGetStringRawBuffer(string[0], 0);
          ComTraceMessageT<unsigned __int64,unsigned long>(
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
            (unsigned int)"CServerTableEntry::WaitForService",
            3511,
            1,
            (__int64)L"Wait for NT service server timed out ClassIdentifier:%ws PID:%x");
        }
        v11 = (unsigned int)v23;
        if ( (int)v23 >= 0 )
          v11 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xDBA,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                  (const char *)0x5B4,
                  v21[0]);
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDB9,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
            (const char *)(unsigned int)v23,
            v21[0]);
        WindowsDeleteString(string[0]);
        return v11;
      }
    }
    else if ( (unsigned int)(v13 + 2147023835) > 1 )
    {
      goto LABEL_34;
    }
    if ( (unsigned int)++v5 >= 4 )
      goto LABEL_34;
  }
  return 0;
}

```

## disassembly

```asm
0x18007f234  push    rbp
0x18007f236  push    rbx
0x18007f237  push    rsi
0x18007f238  push    rdi
0x18007f239  push    r12
0x18007f23b  push    r13
0x18007f23d  push    r14
0x18007f23f  push    r15
0x18007f241  mov     rbp, rsp
0x18007f244  sub     rsp, 68h
0x18007f248  xor     r13d, r13d
0x18007f24b  mov     dword ptr [rbp+var_28], 80070426h
0x18007f252  mov     dword ptr [rbp+var_28+4], r13d
0x18007f256  mov     esi, r13d
0x18007f259  mov     r12, r9
0x18007f25c  mov     rdi, r8
0x18007f25f  mov     r15, rdx
0x18007f262  mov     r14, rcx
0x18007f265  mov     edx, 7530h; dwMilliseconds
0x18007f26a  mov     rcx, r12; hHandle
0x18007f26d  call    cs:__imp_WaitForSingleObject
0x18007f274  nop     dword ptr [rax+rax+00h]
0x18007f279  test    eax, eax
0x18007f27b  jz      loc_18007F5EC
0x18007f281  lea     r8, [rbp+var_20]; int *
0x18007f285  mov     [rbp+var_20], r13d
0x18007f289  mov     edx, 1; int
0x18007f28e  mov     rcx, rdi; this
0x18007f291  call    ?Impersonate@CToken@@UEAAJHPEAH@Z; CToken::Impersonate(int,int *)
0x18007f296  mov     ebx, eax
0x18007f298  test    eax, eax
0x18007f29a  js      loc_18007F5D0
0x18007f2a0  mov     rax, [r15]
0x18007f2a3  lea     r9, [rbp+var_28]
0x18007f2a7  lea     r8, [rbp+var_28+4]
0x18007f2ab  mov     edx, 4
0x18007f2b0  mov     rcx, r15
0x18007f2b3  mov     rax, [rax+28h]
0x18007f2b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f2bc  test    eax, eax
0x18007f2be  jnz     loc_18007F5A9
0x18007f2c4  mov     edx, [rbp+var_20]; int
0x18007f2c7  mov     rcx, rdi; this
0x18007f2ca  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x18007f2cf  mov     ecx, dword ptr [rbp+var_28]
0x18007f2d2  test    ecx, ecx
0x18007f2d4  jns     short loc_18007F346
0x18007f2d6  lea     eax, [rcx+7FF8FBDBh]
0x18007f2dc  cmp     eax, 1
0x18007f2df  jbe     short loc_18007F331
0x18007f2e1  mov     eax, cs:dword_1801574B8
0x18007f2e7  test    eax, eax
0x18007f2e9  jnz     short loc_18007F2FF
0x18007f2eb  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x18007f2f2  jz      short loc_18007F32E
0x18007f2f4  xor     ecx, ecx
0x18007f2f6  call    IsWppLevelEnabled
0x18007f2fb  test    al, al
0x18007f2fd  jz      short loc_18007F32E
0x18007f2ff  mov     eax, dword ptr [rbp+var_28]
0x18007f302  lea     rdx, aCservertableen_7; "CServerTableEntry::WaitForService"
0x18007f309  mov     dword ptr [rsp+68h+var_40], eax
0x18007f30d  lea     rcx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18007f314  lea     rax, aHrHresult_0; "hr=%!HRESULT!"
0x18007f31b  xor     r9d, r9d
0x18007f31e  mov     r8d, 0D68h
0x18007f324  mov     qword ptr [rsp+68h+var_48], rax
0x18007f329  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18007f32e  mov     ecx, dword ptr [rbp+var_28]
0x18007f331  test    ecx, ecx
0x18007f333  jns     short loc_18007F346
0x18007f335  lea     eax, [rcx+7FF8FBDBh]
0x18007f33b  cmp     eax, 1
0x18007f33e  ja      loc_18007F4CF
0x18007f344  jmp     short loc_18007F358
0x18007f346  mov     eax, dword ptr [rbp+var_28+4]
0x18007f349  sub     eax, 2
0x18007f34c  jz      short loc_18007F358
0x18007f34e  sub     eax, 2
0x18007f351  jz      short loc_18007F358
0x18007f353  sub     eax, 1
0x18007f356  jnz     short loc_18007F368
0x18007f358  inc     esi
0x18007f35a  cmp     esi, 4
0x18007f35d  jb      loc_18007F265
0x18007f363  jmp     loc_18007F4CF
0x18007f368  sub     eax, 1
0x18007f36b  jz      short loc_18007F376
0x18007f36d  cmp     eax, 1
0x18007f370  jnz     loc_18007F4CF
0x18007f376  cmp     [rbp+arg_20], r13d
0x18007f37a  jnz     loc_18007F4CF
0x18007f380  lea     r8, [rbp+var_1C]; int *
0x18007f384  mov     [rbp+var_1C], r13d
0x18007f388  mov     edx, 1; int
0x18007f38d  mov     rcx, rdi; this
0x18007f390  call    ?Impersonate@CToken@@UEAAJHPEAH@Z; CToken::Impersonate(int,int *)
0x18007f395  test    eax, eax
0x18007f397  js      loc_18007F4CF
0x18007f39d  mov     rax, [r14]
0x18007f3a0  xor     ecx, ecx; string
0x18007f3a2  mov     [rbp+string], r13
0x18007f3a6  mov     rbx, [rax+20h]
0x18007f3aa  call    cs:__imp_WindowsDeleteString
0x18007f3b1  nop     dword ptr [rax+rax+00h]
0x18007f3b6  lea     rdx, [rbp+string]
0x18007f3ba  mov     [rbp+string], r13
0x18007f3be  mov     rcx, r14
0x18007f3c1  mov     rax, rbx
0x18007f3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f3c9  mov     eax, cs:dword_1801574B8
0x18007f3cf  test    eax, eax
0x18007f3d1  jnz     short loc_18007F3E8
0x18007f3d3  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x18007f3da  jz      short loc_18007F432
0x18007f3dc  lea     ecx, [rax+1]
0x18007f3df  call    IsWppLevelEnabled
0x18007f3e4  test    al, al
0x18007f3e6  jz      short loc_18007F432
0x18007f3e8  mov     rcx, [rbp+string]; string
0x18007f3ec  xor     edx, edx; length
0x18007f3ee  mov     ebx, [r14+10h]
0x18007f3f2  call    cs:__imp_WindowsGetStringRawBuffer
0x18007f3f9  nop     dword ptr [rax+rax+00h]
0x18007f3fe  mov     [rsp+68h+var_38], ebx
0x18007f402  lea     rdx, aCservertableen_7; "CServerTableEntry::WaitForService"
0x18007f409  mov     [rsp+68h+var_40], rax
0x18007f40e  lea     rcx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18007f415  lea     rax, aStoppingNtServ; "Stopping NT service server ClassIdentif"...
0x18007f41c  mov     r9d, 1
0x18007f422  mov     r8d, 0DA1h
0x18007f428  mov     qword ptr [rsp+68h+var_48], rax
0x18007f42d  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x18007f432  mov     rax, [r15]
0x18007f435  lea     r9, [rbp+var_20]
0x18007f439  lea     r8, [rbp+var_28+4]
0x18007f43d  mov     [rbp+var_20], r13d
0x18007f441  mov     edx, 1
0x18007f446  mov     rcx, r15
0x18007f449  mov     rax, [rax+28h]
0x18007f44d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f452  mov     r10d, eax
0x18007f455  test    eax, eax
0x18007f457  jnz     short loc_18007F45F
0x18007f459  cmp     [rbp+var_20], r13d
0x18007f45d  jge     short loc_18007F4B4
0x18007f45f  mov     ecx, cs:dword_1801574B8
0x18007f465  test    ecx, ecx
0x18007f467  jnz     short loc_18007F47B
0x18007f469  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x18007f470  jz      short loc_18007F4B4
0x18007f472  call    IsWppLevelEnabled
0x18007f477  test    al, al
0x18007f479  jz      short loc_18007F4B4
0x18007f47b  mov     eax, [rbp+var_20]
0x18007f47e  lea     r8, aCservertableen_7; "CServerTableEntry::WaitForService"
0x18007f485  mov     [rsp+68h+var_30], eax
0x18007f489  lea     rdx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18007f490  mov     [rsp+68h+var_38], r10d
0x18007f495  lea     rax, aRpcstatusWiner; "rpcstatus=%!WINERROR! hr=%!HRESULT!"
0x18007f49c  mov     [rsp+68h+var_40], rax
0x18007f4a1  mov     r9d, 0DAAh
0x18007f4a7  mov     ecx, r10d
0x18007f4aa  mov     [rsp+68h+var_48], r13d
0x18007f4af  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18007f4b4  mov     edx, [rbp+var_1C]; int
0x18007f4b7  mov     rcx, rdi; this
0x18007f4ba  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x18007f4bf  mov     rcx, [rbp+string]; string
0x18007f4c3  call    cs:__imp_WindowsDeleteString
0x18007f4ca  nop     dword ptr [rax+rax+00h]
0x18007f4cf  mov     rax, [r14]
0x18007f4d2  xor     ecx, ecx; string
0x18007f4d4  mov     [rbp+string], r13
0x18007f4d8  mov     rbx, [rax+20h]
0x18007f4dc  call    cs:__imp_WindowsDeleteString
0x18007f4e3  nop     dword ptr [rax+rax+00h]
0x18007f4e8  lea     rdx, [rbp+string]
0x18007f4ec  mov     [rbp+string], r13
0x18007f4f0  mov     rcx, r14
0x18007f4f3  mov     rax, rbx
0x18007f4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f4fb  mov     eax, cs:dword_1801574B8
0x18007f501  test    eax, eax
0x18007f503  jnz     short loc_18007F51A
0x18007f505  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x18007f50c  jz      short loc_18007F564
0x18007f50e  lea     ecx, [rax+1]
0x18007f511  call    IsWppLevelEnabled
0x18007f516  test    al, al
0x18007f518  jz      short loc_18007F564
0x18007f51a  mov     rcx, [rbp+string]; string
0x18007f51e  xor     edx, edx; length
0x18007f520  mov     ebx, [r14+10h]
0x18007f524  call    cs:__imp_WindowsGetStringRawBuffer
0x18007f52b  nop     dword ptr [rax+rax+00h]
0x18007f530  mov     [rsp+68h+var_38], ebx
0x18007f534  lea     rdx, aCservertableen_7; "CServerTableEntry::WaitForService"
0x18007f53b  mov     [rsp+68h+var_40], rax
0x18007f540  lea     rcx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18007f547  lea     rax, aWaitForNtServi; "Wait for NT service server timed out Cl"...
0x18007f54e  mov     r9d, 1
0x18007f554  mov     r8d, 0DB7h
0x18007f55a  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x18007f55f  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x18007f564  mov     ebx, dword ptr [rbp+var_28]
0x18007f567  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18007f56e  mov     rcx, [rbp+40h]; this
0x18007f572  test    ebx, ebx
0x18007f574  jns     short loc_18007F585
0x18007f576  mov     r9d, ebx; char *
0x18007f579  mov     edx, 0DB9h; void *
0x18007f57e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f583  jmp     short loc_18007F597
0x18007f585  mov     r9d, 5B4h; char *
0x18007f58b  mov     edx, 0DBAh; void *
0x18007f590  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007f595  mov     ebx, eax
0x18007f597  mov     rcx, [rbp+string]; string
0x18007f59b  call    cs:__imp_WindowsDeleteString
0x18007f5a2  nop     dword ptr [rax+rax+00h]
0x18007f5a7  jmp     short loc_18007F5E8
0x18007f5a9  mov     rcx, [rbp+40h]; this
0x18007f5ad  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18007f5b4  mov     r9d, eax; char *
0x18007f5b7  mov     edx, 0D62h; void *
0x18007f5bc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007f5c1  mov     edx, [rbp+var_20]; int
0x18007f5c4  mov     rcx, rdi; this
0x18007f5c7  mov     ebx, eax
0x18007f5c9  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x18007f5ce  jmp     short loc_18007F5E8
0x18007f5d0  mov     rcx, [rbp+40h]; this
0x18007f5d4  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18007f5db  mov     r9d, ebx; char *
0x18007f5de  mov     edx, 0D5Dh; void *
0x18007f5e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f5e8  mov     eax, ebx
0x18007f5ea  jmp     short loc_18007F5EE
0x18007f5ec  xor     eax, eax
0x18007f5ee  add     rsp, 68h
0x18007f5f2  pop     r15
0x18007f5f4  pop     r14
0x18007f5f6  pop     r13
0x18007f5f8  pop     r12
0x18007f5fa  pop     rdi
0x18007f5fb  pop     rsi
0x18007f5fc  pop     rbx
0x18007f5fd  pop     rbp
0x18007f5fe  retn
```
