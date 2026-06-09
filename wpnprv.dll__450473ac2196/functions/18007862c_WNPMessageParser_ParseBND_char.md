# WNPMessageParser::ParseBND(char * *)

- ea: `0x18007862c`
- end: `0x180078c37`
- name: `?ParseBND@WNPMessageParser@@QEAAJPEAPEAD@Z`
- size: `1547`
- prototype: `__int64 __fastcall(WNPMessageParser *__hidden this, char **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180070300`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001cc10`
- `0x180076f44`
- `0x18007862c`
- `0x18007b718`
- `0x180091630`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078a14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078a14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078a06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078a06`
- `XmlLite!CreateXmlReader` at `0x1800787f6`
- `XmlLite!CreateXmlReader` at `0x1800787f6`

## pseudocode

```c
__int64 __fastcall WNPMessageParser::ParseBND(WNPMessageParser *this, char **a2)
{
  char *v4; // rsi
  int v5; // eax
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  int v8; // eax
  struct IStream *v9; // rdi
  __int64 v10; // rdx
  HRESULT v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  HANDLE ProcessHeap; // rax
  int v17; // eax
  int v18; // eax
  char *v19; // [rsp+20h] [rbp-20h] BYREF
  LPCWCH lpWideCharStr; // [rsp+28h] [rbp-18h] BYREF
  struct IStream *v21; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  int v23; // [rsp+88h] [rbp+48h] BYREF
  void *ppvObject; // [rsp+90h] [rbp+50h] BYREF
  wchar_t *String2; // [rsp+98h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, WPP_21a3201469733e5c8660b272590c09d0_Traceguids);
  }
  v4 = 0;
  v21 = 0;
  v19 = 0;
  *a2 = 0;
  ppvObject = 0;
  v23 = 0;
  String2 = 0;
  lpWideCharStr = 0;
  v5 = WNPMessageParser::ScanHeaders(this);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        178,
        WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
        (unsigned int)v5);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x428,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
      (const char *)v6,
      (int)v19);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, v6);
      goto LABEL_57;
    }
    goto LABEL_58;
  }
  if ( *((_DWORD *)this + 4) == *((_QWORD *)this + 3) )
    goto LABEL_57;
  v8 = WNPMessageParser::CreatePayloadStream(this, &v21);
  v9 = v21;
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        180,
        WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
        (unsigned int)v8);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x433,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
      (const char *)v6,
      (int)v19);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_55;
    v10 = 181;
LABEL_22:
    WPP_SF_d(v7[2], v10, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, v6);
LABEL_23:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_55;
  }
  v11 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v6 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        182,
        WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
        (unsigned int)v11);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x437,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
      (const char *)v6,
      (int)v19);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_55;
    v10 = 183;
    goto LABEL_22;
  }
  v12 = (*(__int64 (__fastcall **)(void *, struct IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v9);
  v6 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        184,
        WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
        (unsigned int)v12);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x43B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
      (const char *)v6,
      (int)v19);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_55;
    v10 = 185;
    goto LABEL_22;
  }
  v6 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v23);
LABEL_41:
  v7 = (PVOID *)WPP_GLOBAL_Control;
  while ( 1 )
  {
    if ( v6 )
      goto LABEL_54;
    if ( v23 == 1 )
      break;
    if ( v23 == 3 )
    {
      if ( String2 )
      {
        v13 = (*(__int64 (__fastcall **)(void *, LPCWCH *, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                ppvObject,
                &lpWideCharStr,
                0);
        v6 = v13;
        if ( v13 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              188,
              WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
              (unsigned int)v13);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x44E,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
            (const char *)v6,
            (int)v19);
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v10 = 189;
            goto LABEL_22;
          }
          goto LABEL_55;
        }
        if ( !wcscmp_0(L"nonce", String2) )
        {
          v14 = WpnUtf16ToUtf8(lpWideCharStr, &v19);
          v6 = v14;
          if ( v14 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                190,
                WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
                (unsigned int)v14);
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x454,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
              (const char *)v6,
              (int)v19);
            v7 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 191, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, v6);
              v4 = v19;
              goto LABEL_23;
            }
            v4 = v19;
            goto LABEL_55;
          }
          v4 = v19;
        }
        if ( v4 )
        {
          v7 = (PVOID *)WPP_GLOBAL_Control;
          v6 = 1;
LABEL_54:
          *a2 = v4;
          v4 = 0;
          goto LABEL_55;
        }
      }
    }
    else if ( v23 == 15 )
    {
      String2 = 0;
      lpWideCharStr = 0;
    }
LABEL_68:
    v18 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v23);
    v6 = v18;
    if ( v18 >= 0 )
      goto LABEL_41;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        192,
        WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
        (unsigned int)v18);
      goto LABEL_41;
    }
  }
  v17 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(ppvObject, &String2, 0);
  v6 = v17;
  if ( v17 >= 0 )
    goto LABEL_68;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      186,
      WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
      (unsigned int)v17);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x446,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
    (const char *)v6,
    (int)v19);
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v10 = 187;
    goto LABEL_22;
  }
LABEL_55:
  if ( v9 )
  {
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v9 + 16LL))(v9);
LABEL_57:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_58:
  if ( ppvObject )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    ppvObject = 0;
  }
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 2) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 193, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18007862c  push    rbp
0x18007862e  push    rbx
0x18007862f  push    rsi
0x180078630  push    rdi
0x180078631  push    r12
0x180078633  push    r13
0x180078635  push    r14
0x180078637  mov     rbp, rsp
0x18007863a  sub     rsp, 40h
0x18007863e  mov     r14, rdx
0x180078641  mov     rdi, rcx
0x180078644  mov     rcx, cs:WPP_GLOBAL_Control
0x18007864b  lea     r13, WPP_GLOBAL_Control
0x180078652  mov     r12d, 2
0x180078658  cmp     rcx, r13
0x18007865b  jz      short loc_18007867E
0x18007865d  test    [rcx+1Ch], r12b
0x180078661  jz      short loc_18007867E
0x180078663  cmp     byte ptr [rcx+19h], 6
0x180078667  jb      short loc_18007867E
0x180078669  mov     rcx, [rcx+10h]
0x18007866d  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180078674  mov     edx, 0B1h
0x180078679  call    WPP_SF_
0x18007867e  xor     esi, esi
0x180078680  mov     [rbp+var_10], 0
0x180078688  mov     rcx, rdi; this
0x18007868b  mov     [rbp+var_20], rsi
0x18007868f  mov     [r14], rsi
0x180078692  mov     [rbp+ppvObject], 0
0x18007869a  mov     [rbp+arg_8], 0
0x1800786a1  mov     [rbp+String2], 0
0x1800786a9  mov     [rbp+lpWideCharStr], 0
0x1800786b1  call    ?ScanHeaders@WNPMessageParser@@AEAAJXZ; WNPMessageParser::ScanHeaders(void)
0x1800786b6  mov     ebx, eax
0x1800786b8  test    eax, eax
0x1800786ba  jns     short loc_18007873B
0x1800786bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800786c3  cmp     rcx, r13
0x1800786c6  jz      short loc_1800786EC
0x1800786c8  test    [rcx+1Ch], r12b
0x1800786cc  jz      short loc_1800786EC
0x1800786ce  cmp     [rcx+19h], r12b
0x1800786d2  jb      short loc_1800786EC
0x1800786d4  mov     rcx, [rcx+10h]
0x1800786d8  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x1800786df  mov     edx, 0B2h
0x1800786e4  mov     r9d, eax
0x1800786e7  call    WPP_SF_d
0x1800786ec  mov     rcx, [rbp+38h]; this
0x1800786f0  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800786f7  mov     r9d, ebx; char *
0x1800786fa  mov     edx, 428h; void *
0x1800786ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180078704  mov     rcx, cs:WPP_GLOBAL_Control
0x18007870b  cmp     rcx, r13
0x18007870e  jz      loc_1800789DA
0x180078714  test    byte ptr [rcx+1Ch], 80h
0x180078718  jz      loc_1800789DA
0x18007871e  mov     rcx, [rcx+10h]
0x180078722  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180078729  mov     edx, 0B3h
0x18007872e  mov     r9d, ebx
0x180078731  call    WPP_SF_d
0x180078736  jmp     loc_1800789D3
0x18007873b  mov     eax, [rdi+10h]
0x18007873e  cmp     rax, [rdi+18h]
0x180078742  jz      loc_1800789D3
0x180078748  lea     rdx, [rbp+var_10]; struct IStream **
0x18007874c  mov     rcx, rdi; this
0x18007874f  call    ?CreatePayloadStream@WNPMessageParser@@AEAAJPEAPEAUIStream@@@Z; WNPMessageParser::CreatePayloadStream(IStream * *)
0x180078754  mov     rdi, [rbp+var_10]
0x180078758  mov     ebx, eax
0x18007875a  test    eax, eax
0x18007875c  jns     loc_1800787E8
0x180078762  mov     rcx, cs:WPP_GLOBAL_Control
0x180078769  cmp     rcx, r13
0x18007876c  jz      short loc_180078792
0x18007876e  test    [rcx+1Ch], r12b
0x180078772  jz      short loc_180078792
0x180078774  cmp     [rcx+19h], r12b
0x180078778  jb      short loc_180078792
0x18007877a  mov     rcx, [rcx+10h]
0x18007877e  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180078785  mov     edx, 0B4h
0x18007878a  mov     r9d, eax
0x18007878d  call    WPP_SF_d
0x180078792  mov     rcx, [rbp+38h]; this
0x180078796  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007879d  mov     r9d, ebx; char *
0x1800787a0  mov     edx, 433h; void *
0x1800787a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800787aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800787b1  cmp     rcx, r13
0x1800787b4  jz      loc_1800789BF
0x1800787ba  test    byte ptr [rcx+1Ch], 80h
0x1800787be  jz      loc_1800789BF
0x1800787c4  mov     edx, 0B5h
0x1800787c9  mov     rcx, [rcx+10h]
0x1800787cd  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x1800787d4  mov     r9d, ebx
0x1800787d7  call    WPP_SF_d
0x1800787dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800787e3  jmp     loc_1800789BF
0x1800787e8  xor     r8d, r8d; pMalloc
0x1800787eb  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800787ef  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800787f6  call    cs:__imp_CreateXmlReader
0x1800787fc  mov     ebx, eax
0x1800787fe  test    eax, eax
0x180078800  jns     short loc_18007886E
0x180078802  mov     rcx, cs:WPP_GLOBAL_Control
0x180078809  cmp     rcx, r13
0x18007880c  jz      short loc_180078832
0x18007880e  test    [rcx+1Ch], r12b
0x180078812  jz      short loc_180078832
0x180078814  cmp     [rcx+19h], r12b
0x180078818  jb      short loc_180078832
0x18007881a  mov     rcx, [rcx+10h]
0x18007881e  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180078825  mov     edx, 0B6h
0x18007882a  mov     r9d, eax
0x18007882d  call    WPP_SF_d
0x180078832  mov     rcx, [rbp+38h]; this
0x180078836  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007883d  mov     r9d, ebx; char *
0x180078840  mov     edx, 437h; void *
0x180078845  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007884a  mov     rcx, cs:WPP_GLOBAL_Control
0x180078851  cmp     rcx, r13
0x180078854  jz      loc_1800789BF
0x18007885a  test    byte ptr [rcx+1Ch], 80h
0x18007885e  jz      loc_1800789BF
0x180078864  mov     edx, 0B7h
0x180078869  jmp     loc_1800787C9
0x18007886e  mov     rcx, [rbp+ppvObject]
0x180078872  mov     rdx, rdi
0x180078875  mov     rax, [rcx]
0x180078878  mov     rax, [rax+18h]
0x18007887c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078881  mov     ebx, eax
0x180078883  test    eax, eax
0x180078885  jns     short loc_1800788F3
0x180078887  mov     rcx, cs:WPP_GLOBAL_Control
0x18007888e  cmp     rcx, r13
0x180078891  jz      short loc_1800788B7
0x180078893  test    [rcx+1Ch], r12b
0x180078897  jz      short loc_1800788B7
0x180078899  cmp     [rcx+19h], r12b
0x18007889d  jb      short loc_1800788B7
0x18007889f  mov     rcx, [rcx+10h]
0x1800788a3  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x1800788aa  mov     edx, 0B8h
0x1800788af  mov     r9d, eax
0x1800788b2  call    WPP_SF_d
0x1800788b7  mov     rcx, [rbp+38h]; this
0x1800788bb  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800788c2  mov     r9d, ebx; char *
0x1800788c5  mov     edx, 43Bh; void *
0x1800788ca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800788cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800788d6  cmp     rcx, r13
0x1800788d9  jz      loc_1800789BF
0x1800788df  test    byte ptr [rcx+1Ch], 80h
0x1800788e3  jz      loc_1800789BF
0x1800788e9  mov     edx, 0B9h
0x1800788ee  jmp     loc_1800787C9
0x1800788f3  mov     rcx, [rbp+ppvObject]
0x1800788f7  lea     rdx, [rbp+arg_8]
0x1800788fb  mov     rax, [rcx]
0x1800788fe  mov     rax, [rax+30h]
0x180078902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078907  mov     ebx, eax
0x180078909  mov     rcx, cs:WPP_GLOBAL_Control
0x180078910  test    ebx, ebx
0x180078912  jnz     loc_1800789BA
0x180078918  mov     ecx, [rbp+arg_8]
0x18007891b  sub     ecx, 1
0x18007891e  jz      loc_180078A5B
0x180078924  sub     ecx, r12d
0x180078927  jz      short loc_180078947
0x180078929  cmp     ecx, 0Ch
0x18007892c  jnz     loc_180078A7C
0x180078932  mov     [rbp+String2], 0
0x18007893a  mov     [rbp+lpWideCharStr], 0
0x180078942  jmp     loc_180078A7C
0x180078947  cmp     [rbp+String2], 0
0x18007894c  jz      loc_180078A7C
0x180078952  mov     rcx, [rbp+ppvObject]
0x180078956  lea     rdx, [rbp+lpWideCharStr]
0x18007895a  xor     r8d, r8d
0x18007895d  mov     rax, [rcx]
0x180078960  mov     rax, [rax+80h]
0x180078967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007896c  mov     ebx, eax
0x18007896e  test    eax, eax
0x180078970  js      loc_180078B5F
0x180078976  mov     rdx, [rbp+String2]; String2
0x18007897a  lea     rcx, aNonce; "nonce"
0x180078981  call    wcscmp_0
0x180078986  test    eax, eax
0x180078988  jnz     short loc_1800789A5
0x18007898a  mov     rcx, [rbp+lpWideCharStr]; lpWideCharStr
0x18007898e  lea     rdx, [rbp+var_20]; char **
0x180078992  call    ?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z; WpnUtf16ToUtf8(ushort const *,char * *)
0x180078997  mov     ebx, eax
0x180078999  test    eax, eax
0x18007899b  js      loc_180078ADB
0x1800789a1  mov     rsi, [rbp+var_20]
0x1800789a5  test    rsi, rsi
0x1800789a8  jz      loc_180078A7C
0x1800789ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800789b5  mov     ebx, 1
0x1800789ba  mov     [r14], rsi
0x1800789bd  xor     esi, esi
0x1800789bf  test    rdi, rdi
0x1800789c2  jz      short loc_1800789DA
0x1800789c4  mov     rax, [rdi]
0x1800789c7  mov     rcx, rdi
0x1800789ca  mov     rax, [rax+10h]
0x1800789ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800789d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800789da  mov     rdx, [rbp+ppvObject]
0x1800789de  test    rdx, rdx
0x1800789e1  jz      short loc_180078A01
0x1800789e3  mov     rax, [rdx]
0x1800789e6  mov     rcx, rdx
0x1800789e9  mov     rax, [rax+10h]
0x1800789ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800789f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800789f9  mov     [rbp+ppvObject], 0
0x180078a01  test    rsi, rsi
0x180078a04  jz      short loc_180078A21
0x180078a06  call    cs:__imp_GetProcessHeap
0x180078a0c  mov     r8, rsi; lpMem
0x180078a0f  xor     edx, edx; dwFlags
0x180078a11  mov     rcx, rax; hHeap
0x180078a14  call    cs:__imp_HeapFree
0x180078a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180078a21  cmp     rcx, r13
0x180078a24  jz      short loc_180078A4A
0x180078a26  test    [rcx+1Ch], r12b
0x180078a2a  jz      short loc_180078A4A
0x180078a2c  cmp     byte ptr [rcx+19h], 6
0x180078a30  jb      short loc_180078A4A
0x180078a32  mov     rcx, [rcx+10h]
0x180078a36  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180078a3d  mov     edx, 0C1h
0x180078a42  mov     r9d, ebx
0x180078a45  call    WPP_SF_d
0x180078a4a  mov     eax, ebx
0x180078a4c  add     rsp, 40h
0x180078a50  pop     r14
0x180078a52  pop     r13
0x180078a54  pop     r12
0x180078a56  pop     rdi
0x180078a57  pop     rsi
0x180078a58  pop     rbx
0x180078a59  pop     rbp
0x180078a5a  retn
0x180078a5b  mov     rcx, [rbp+ppvObject]
0x180078a5f  lea     rdx, [rbp+String2]
0x180078a63  xor     r8d, r8d
0x180078a66  mov     rax, [rcx]
0x180078a69  mov     rax, [rax+70h]
0x180078a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a72  mov     ebx, eax
0x180078a74  test    eax, eax
0x180078a76  js      loc_180078BCB
0x180078a7c  mov     rcx, [rbp+ppvObject]
0x180078a80  lea     rdx, [rbp+arg_8]
0x180078a84  mov     rax, [rcx]
0x180078a87  mov     rax, [rax+30h]
0x180078a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a90  mov     ebx, eax
0x180078a92  test    eax, eax
0x180078a94  jns     loc_180078909
0x180078a9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180078aa1  cmp     rcx, r13
0x180078aa4  jz      loc_180078910
0x180078aaa  test    [rcx+1Ch], r12b
0x180078aae  jz      loc_180078910
0x180078ab4  cmp     [rcx+19h], r12b
0x180078ab8  jb      loc_180078910
0x180078abe  mov     rcx, [rcx+10h]
0x180078ac2  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180078ac9  mov     edx, 0C0h
0x180078ace  mov     r9d, eax
0x180078ad1  call    WPP_SF_d
0x180078ad6  jmp     loc_180078909
0x180078adb  mov     rcx, cs:WPP_GLOBAL_Control
0x180078ae2  cmp     rcx, r13
0x180078ae5  jz      short loc_180078B0B
0x180078ae7  test    [rcx+1Ch], r12b
0x180078aeb  jz      short loc_180078B0B
0x180078aed  cmp     [rcx+19h], r12b
0x180078af1  jb      short loc_180078B0B
0x180078af3  mov     rcx, [rcx+10h]
0x180078af7  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180078afe  mov     edx, 0BEh
  ... truncated ...
```
