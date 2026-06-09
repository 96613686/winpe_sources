# CCookieContainerProps::GetCookies(ushort const *,ulong *,_RPC_COOKIE * *)

- ea: `0x1800fcdcc`
- end: `0x1800fd338`
- name: `?GetCookies@CCookieContainerProps@@QEAAJPEBGPEAKPEAPEAU_RPC_COOKIE@@@Z`
- size: `1388`
- prototype: `int(CCookieContainerProps *__hidden this, const unsigned __int16 *, unsigned int *, struct _RPC_COOKIE **)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800fcbe0`

## callees

- `0x180021cd0`
- `0x180025910`
- `0x180025980`
- `0x18007ec9c`
- `0x180083dc4`
- `0x1800861f8`
- `0x180091d90`
- `0x1800acab8`
- `0x1800c8d74`
- `0x1800e1c38`
- `0x1800e22b0`
- `0x1800e2538`
- `0x1800fcdcc`
- `0x18014a7a0`
- `0x1801c9c19`
- `0x1801e0660`
- `0x1801e1790`
- `0x1801e1b60`
- `0x1801e25fc`
- `0x1801e3c78`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800fcef6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800fcef6`
- `ESENT!JetSetCurrentIndex2W` at `0x1800fcf75`
- `ESENT!JetSetCurrentIndex2W` at `0x1800fcf75`
- `ESENT!JetRetrieveColumn` at `0x1800fd11d`
- `ESENT!JetRetrieveColumn` at `0x1800fd11d`
- `ESENT!JetRollback` at `0x1800fd2c8`
- `ESENT!JetRollback` at `0x1800fd2c8`
- `ESENT!JetBeginTransaction` at `0x1800fcfca`
- `ESENT!JetBeginTransaction` at `0x1800fcfca`
- `ESENT!JetMove` at `0x1800fd1bc`
- `ESENT!JetMove` at `0x1800fd1bc`

## pseudocode

```c
__int64 __fastcall CCookieContainerProps::GetCookies(
        CCookieContainerProps *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        struct _RPC_COOKIE **a4)
{
  struct _RPC_COOKIE **v5; // rax
  unsigned int v7; // r15d
  __int64 v8; // r12
  __int64 v9; // r8
  unsigned int v10; // esi
  const WCHAR *v11; // r10
  unsigned int v12; // r14d
  int v13; // edx
  int v14; // r9d
  unsigned int i; // r9d
  __int64 v16; // rax
  int v17; // edx
  int v18; // ecx
  int StringColumn; // ebx
  int v20; // r8d
  struct CJetContext *v21; // rdi
  JET_TABLEID v22; // rdx
  JET_SESID v23; // rcx
  JET_ERR v24; // eax
  JET_ERR v25; // eax
  int v26; // eax
  __int64 v27; // rcx
  struct _RPC_COOKIE *Heap; // rax
  struct _RPC_COOKIE *v29; // rsi
  int v30; // eax
  int v31; // r14d
  JET_ERR v32; // eax
  JET_ERR v33; // eax
  struct _RPC_COOKIE *v34; // rax
  int v36; // [rsp+40h] [rbp-59h] BYREF
  int v37; // [rsp+44h] [rbp-55h]
  struct _RPC_COOKIE *v38; // [rsp+48h] [rbp-51h] BYREF
  int v39; // [rsp+54h] [rbp-45h]
  struct CJetContext *v40; // [rsp+58h] [rbp-41h] BYREF
  CCookieContainerProps *v41; // [rsp+60h] [rbp-39h]
  struct _RPC_COOKIE **v42; // [rsp+68h] [rbp-31h]
  unsigned int *v43; // [rsp+70h] [rbp-29h]
  int pvData; // [rsp+78h] [rbp-21h] BYREF
  unsigned int pcbActual; // [rsp+80h] [rbp-19h] BYREF
  int v46; // [rsp+84h] [rbp-15h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-11h] BYREF
  wchar_t *String1[2]; // [rsp+90h] [rbp-9h] BYREF

  v41 = this;
  v37 = 0;
  v43 = a3;
  String1[1] = 0;
  v5 = a4;
  String1[0] = (wchar_t *)&Data;
  v42 = a4;
  v40 = 0;
  v7 = 0;
  v38 = 0;
  SystemTimeAsFileTime = 0;
  v36 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
  {
    WPP_SF_qS(1036, 23, (unsigned int)WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids, (_DWORD)this, (__int64)a2);
    v5 = v42;
  }
  if ( a3 )
    *a3 = 0;
  if ( v5 )
    *v5 = 0;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = 0;
  v11 = &UnicodeCharStr;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  do
  {
    v13 = *((_DWORD *)qword_180226530 + ((unsigned __int64)*v11 >> 8))
        ^ __ROL4__(*((_DWORD *)qword_180226530 + (unsigned __int8)*v11) ^ __ROL4__(v13, 1), 1);
    if ( !*v11 )
      break;
    ++v11;
    ++v14;
  }
  while ( !v14 );
  if ( a2 )
  {
    for ( i = 0;
          i < (unsigned int)v9;
          v10 = *((_DWORD *)qword_180226530 + ((unsigned __int64)a2[v16] >> 8))
              ^ __ROL4__(*((_DWORD *)qword_180226530 + (unsigned __int8)a2[v16]) ^ __ROL4__(v10, 1), 1) )
    {
      v16 = i++;
    }
    v12 = v13;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  StringColumn = CJetContextList::AcquireContext(*((CJetContextList **)v41 + 9), &v40, 0);
  if ( StringColumn < 0 )
  {
    v37 = 869;
    goto LABEL_78;
  }
  v21 = v40;
  v39 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qdSD(v18, v17, v20, (_DWORD)v40, 1, (__int64)L"MinimizedRDomainHashCookieHashIndex", 0);
  if ( *((_DWORD *)v21 + 12) == 1 )
  {
    StringColumn = 0;
  }
  else
  {
    v22 = *((_QWORD *)v21 + 4);
    v23 = *((_QWORD *)v21 + 2);
    *((_DWORD *)v21 + 12) = -1;
    v24 = JetSetCurrentIndex2W(v23, v22, L"MinimizedRDomainHashCookieHashIndex", 0);
    StringColumn = HRESULTFromJET_ERR(v24, 1);
    if ( StringColumn >= 0 )
      *((_DWORD *)v21 + 12) = 1;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 14, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)StringColumn);
  if ( StringColumn < 0 )
  {
    v37 = 870;
    goto LABEL_78;
  }
  v25 = JetBeginTransaction(*((_QWORD *)v21 + 2));
  StringColumn = HRESULTFromJET_ERR(v25, 1);
  if ( StringColumn >= 0 )
  {
    v26 = SeekToMinimizedRDomainHash(v21, v12 ^ ((unsigned __int64)v10 << 31));
    StringColumn = v26;
    if ( v26 < 0 )
    {
      v37 = 880;
      goto LABEL_77;
    }
    if ( v26 == 1 )
    {
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
        WPP_SF_(1036, 24, WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids);
      StringColumn = 0;
LABEL_77:
      JetRollback(*((_QWORD *)v21 + 2), 0);
      goto LABEL_78;
    }
    v46 = 0;
    Heap = (struct _RPC_COOKIE *)WxAllocateHeapEx(v27, 2048);
    v29 = Heap;
    if ( !Heap )
    {
      v46 = 52;
      StringColumn = -2147024882;
      v37 = 890;
      goto LABEL_77;
    }
    v38 = Heap;
    do
      ++v8;
    while ( a2[v8] );
    StringColumn = CWxString::ExtendBuffer((CWxString *)String1, 0x101u);
    if ( StringColumn < 0 )
    {
      v37 = 903;
      goto LABEL_77;
    }
    v30 = 1;
    v31 = 32;
    while ( 1 )
    {
      v46 = 0;
      pvData = 0;
      if ( !v30 )
        goto LABEL_55;
      do
      {
        v39 = 0;
        pcbActual = 0;
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_dqd(1036, 17, (unsigned int)WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 4, (__int64)&pvData);
        v32 = JetRetrieveColumn(
                *((_QWORD *)v21 + 2),
                *((_QWORD *)v21 + 4),
                *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v21 + 5) + 8LL) + 16LL),
                &pvData,
                4u,
                &pcbActual,
                0,
                0);
        StringColumn = HRESULTFromJET_ERR(v32, 1);
        if ( StringColumn >= 0 )
        {
          if ( pcbActual == 4 )
          {
            StringColumn = 0;
          }
          else
          {
            StringColumn = -2147418113;
            v39 = 214;
          }
        }
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_d(1036, 18, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)StringColumn);
        if ( StringColumn < 0 )
        {
          v46 = 804;
          break;
        }
        if ( (_DWORD)v8 == pvData )
        {
          StringColumn = CJetContext::GetStringColumn(v21, 3u, (struct CWxString *)String1);
          if ( StringColumn < 0 )
          {
            v46 = 815;
            break;
          }
          if ( !wcsncmp_0(String1[0], a2, (unsigned int)v8) )
          {
            StringColumn = 0;
            break;
          }
        }
LABEL_55:
        v33 = JetMove(*((_QWORD *)v21 + 2), *((_QWORD *)v21 + 4), 1, 0);
        if ( v33 == -1603 )
        {
          StringColumn = 1;
          break;
        }
        StringColumn = HRESULTFromJET_ERR(v33, 1);
      }
      while ( StringColumn >= 0 );
      if ( StringColumn == 1 )
      {
        StringColumn = 0;
        v38 = 0;
        *v42 = v29;
        *v43 = v7;
        v7 = 0;
        goto LABEL_77;
      }
      if ( StringColumn < 0 )
      {
        v37 = 918;
        goto LABEL_77;
      }
      StringColumn = CCookieContainerProps::CheckForExpiredCookie(
                       v41,
                       v21,
                       (union FILETIMEEX *)&SystemTimeAsFileTime,
                       &v36);
      if ( StringColumn < 0 )
      {
        v37 = 924;
        goto LABEL_77;
      }
      if ( !v36 )
      {
        if ( v7 == v31 )
        {
          v31 *= 2;
          v39 = 0;
          v34 = (struct _RPC_COOKIE *)WxHeapAllocator::ReAllocEx(0, (unsigned int)(v31 << 6), v29);
          v29 = v34;
          if ( !v34 )
          {
            v39 = 100;
            StringColumn = -2147024882;
            v37 = 933;
            goto LABEL_77;
          }
          v38 = v34;
        }
        StringColumn = GetCookieAtCursor(v21, (struct _RPC_COOKIE *)((char *)v29 + 64 * (unsigned __int64)v7));
        if ( StringColumn < 0 )
        {
          v37 = 936;
          goto LABEL_77;
        }
        ++v7;
      }
      v30 = 0;
    }
  }
LABEL_78:
  CJetContextList::ReleaseContext(*((CJetContextList **)v41 + 9), &v40);
  FreeRpcCookies(v7, &v38);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 25, WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids, (unsigned int)StringColumn);
  CWxString::_Release((CWxString *)String1);
  return (unsigned int)StringColumn;
}

```

## disassembly

```asm
0x1800fcdcc  push    rbp
0x1800fcdce  push    rbx
0x1800fcdcf  push    rsi
0x1800fcdd0  push    rdi
0x1800fcdd1  push    r12
0x1800fcdd3  push    r13
0x1800fcdd5  push    r14
0x1800fcdd7  push    r15
0x1800fcdd9  lea     rbp, [rsp-1Fh]
0x1800fcdde  sub     rsp, 0B8h
0x1800fcde5  mov     rax, cs:__security_cookie
0x1800fcdec  xor     rax, rsp
0x1800fcdef  mov     [rbp+57h+var_50], rax
0x1800fcdf3  xor     edi, edi
0x1800fcdf5  mov     [rbp+57h+var_90], rcx
0x1800fcdf9  mov     rbx, r8
0x1800fcdfc  mov     [rbp+57h+var_AC], edi
0x1800fcdff  mov     r8, rcx
0x1800fce02  mov     [rbp+57h+var_80], rbx
0x1800fce06  lea     rcx, Data
0x1800fce0d  mov     [rbp+57h+var_58], rdi
0x1800fce11  mov     rax, r9
0x1800fce14  mov     [rbp+57h+String1], rcx
0x1800fce18  mov     [rbp+57h+var_88], rax
0x1800fce1c  mov     r13, rdx
0x1800fce1f  mov     [rbp+57h+var_98], rdi
0x1800fce23  mov     r15d, edi
0x1800fce26  mov     [rbp+57h+var_A8], rdi
0x1800fce2a  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x1800fce2e  mov     [rbp+57h+var_B0], edi
0x1800fce31  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800fce38  jz      short loc_1800FCE5A
0x1800fce3a  mov     r9, r8
0x1800fce3d  mov     qword ptr [rsp+0F0h+cbData], r13
0x1800fce42  lea     r8, WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids
0x1800fce49  mov     ecx, 40Ch
0x1800fce4e  lea     edx, [rdi+17h]
0x1800fce51  call    WPP_SF_qS
0x1800fce56  mov     rax, [rbp+57h+var_88]
0x1800fce5a  test    rbx, rbx
0x1800fce5d  jz      short loc_1800FCE61
0x1800fce5f  mov     [rbx], edi
0x1800fce61  test    rax, rax
0x1800fce64  jz      short loc_1800FCE69
0x1800fce66  mov     [rax], rdi
0x1800fce69  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800fce6d  mov     r8, r12
0x1800fce70  inc     r8
0x1800fce73  cmp     [r13+r8*2+0], di
0x1800fce79  jnz     short loc_1800FCE70
0x1800fce7b  mov     esi, edi
0x1800fce7d  lea     r10, UnicodeCharStr
0x1800fce84  mov     r14d, edi
0x1800fce87  lea     r11, qword_180226530
0x1800fce8e  mov     edx, edi
0x1800fce90  mov     r9d, edi
0x1800fce93  movzx   ecx, word ptr [r10]
0x1800fce97  rol     edx, 1
0x1800fce99  movzx   eax, cl
0x1800fce9c  xor     edx, [r11+rax*4]
0x1800fcea0  mov     eax, ecx
0x1800fcea2  shr     rax, 8
0x1800fcea6  rol     edx, 1
0x1800fcea8  xor     edx, [r11+rax*4]
0x1800fceac  test    cx, cx
0x1800fceaf  jz      short loc_1800FCEBE
0x1800fceb1  add     r10, 2
0x1800fceb5  inc     r9d
0x1800fceb8  cmp     r9d, 1
0x1800fcebc  jb      short loc_1800FCE93
0x1800fcebe  test    r13, r13
0x1800fcec1  jz      short loc_1800FCEF2
0x1800fcec3  mov     r9d, edi
0x1800fcec6  test    r8d, r8d
0x1800fcec9  jz      short loc_1800FCEEF
0x1800fcecb  rol     esi, 1
0x1800fcecd  mov     eax, r9d
0x1800fced0  inc     r9d
0x1800fced3  movzx   ecx, word ptr [r13+rax*2+0]
0x1800fced9  movzx   eax, cl
0x1800fcedc  shr     rcx, 8
0x1800fcee0  xor     esi, [r11+rax*4]
0x1800fcee4  rol     esi, 1
0x1800fcee6  xor     esi, [r11+rcx*4]
0x1800fceea  cmp     r9d, r8d
0x1800fceed  jb      short loc_1800FCECB
0x1800fceef  mov     r14d, edx
0x1800fcef2  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800fcef6  call    cs:__imp_GetSystemTimeAsFileTime
0x1800fcefc  mov     rcx, [rbp+57h+var_90]
0x1800fcf00  lea     rdx, [rbp+57h+var_98]; struct CJetContext **
0x1800fcf04  xor     r8d, r8d; int *
0x1800fcf07  mov     rcx, [rcx+48h]; this
0x1800fcf0b  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800fcf10  mov     ebx, eax
0x1800fcf12  test    eax, eax
0x1800fcf14  jns     short loc_1800FCF22
0x1800fcf16  mov     [rbp+57h+var_AC], 365h
0x1800fcf1d  jmp     loc_1800FD2CE
0x1800fcf22  mov     rdi, [rbp+57h+var_98]
0x1800fcf26  xor     eax, eax
0x1800fcf28  mov     [rbp+57h+var_9C], eax
0x1800fcf2b  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800fcf32  lea     rbx, aMinimizedrdoma_2; "MinimizedRDomainHashCookieHashIndex"
0x1800fcf39  jz      short loc_1800FCF56
0x1800fcf3b  mov     [rsp+0F0h+grbit], eax
0x1800fcf3f  mov     r9, rdi
0x1800fcf42  mov     [rsp+0F0h+pcbActual], rbx
0x1800fcf47  mov     [rsp+0F0h+cbData], 1
0x1800fcf4f  call    WPP_SF_qdSD
0x1800fcf54  xor     eax, eax
0x1800fcf56  cmp     dword ptr [rdi+30h], 1
0x1800fcf5a  jnz     short loc_1800FCF60
0x1800fcf5c  mov     ebx, eax
0x1800fcf5e  jmp     short loc_1800FCF94
0x1800fcf60  mov     rdx, [rdi+20h]; tableid
0x1800fcf64  xor     r9d, r9d; grbit
0x1800fcf67  mov     rcx, [rdi+10h]; sesid
0x1800fcf6b  mov     r8, rbx; szIndexName
0x1800fcf6e  mov     dword ptr [rdi+30h], 0FFFFFFFFh
0x1800fcf75  call    cs:__imp_JetSetCurrentIndex2W
0x1800fcf7b  mov     ecx, eax; int
0x1800fcf7d  mov     edx, 1; int
0x1800fcf82  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800fcf87  mov     ebx, eax
0x1800fcf89  test    eax, eax
0x1800fcf8b  js      short loc_1800FCF94
0x1800fcf8d  mov     dword ptr [rdi+30h], 1
0x1800fcf94  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800fcf9b  jz      short loc_1800FCFB6
0x1800fcf9d  mov     edx, 0Eh
0x1800fcfa2  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800fcfa9  mov     ecx, 40Ch
0x1800fcfae  mov     r9d, ebx
0x1800fcfb1  call    WPP_SF_d
0x1800fcfb6  test    ebx, ebx
0x1800fcfb8  jns     short loc_1800FCFC6
0x1800fcfba  mov     [rbp+57h+var_AC], 366h
0x1800fcfc1  jmp     loc_1800FD2CE
0x1800fcfc6  mov     rcx, [rdi+10h]; sesid
0x1800fcfca  call    cs:__imp_JetBeginTransaction
0x1800fcfd0  mov     ecx, eax; int
0x1800fcfd2  mov     edx, 1; int
0x1800fcfd7  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800fcfdc  mov     ebx, eax
0x1800fcfde  test    eax, eax
0x1800fcfe0  js      loc_1800FD2CE
0x1800fcfe6  mov     eax, r14d
0x1800fcfe9  mov     rcx, rdi; struct CJetContext *
0x1800fcfec  mov     edx, esi
0x1800fcfee  shl     rdx, 1Fh
0x1800fcff2  xor     rdx, rax; unsigned __int64
0x1800fcff5  call    ?SeekToMinimizedRDomainHash@@YAJPEAVCJetContext@@_K@Z; SeekToMinimizedRDomainHash(CJetContext *,unsigned __int64)
0x1800fcffa  xor     r14d, r14d
0x1800fcffd  mov     ebx, eax
0x1800fcfff  test    eax, eax
0x1800fd001  jns     short loc_1800FD00F
0x1800fd003  mov     [rbp+57h+var_AC], 370h
0x1800fd00a  jmp     loc_1800FD2C2
0x1800fd00f  cmp     eax, 1
0x1800fd012  jnz     short loc_1800FD039
0x1800fd014  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800fd01b  jz      short loc_1800FD031
0x1800fd01d  lea     edx, [rax+17h]
0x1800fd020  mov     ecx, 40Ch
0x1800fd025  lea     r8, WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids
0x1800fd02c  call    WPP_SF_
0x1800fd031  mov     ebx, r14d
0x1800fd034  jmp     loc_1800FD2C2
0x1800fd039  mov     edx, 800h
0x1800fd03e  mov     [rbp+57h+var_6C], r14d
0x1800fd042  call    WxAllocateHeapEx
0x1800fd047  mov     rsi, rax
0x1800fd04a  test    rax, rax
0x1800fd04d  jnz     short loc_1800FD067
0x1800fd04f  mov     [rbp+57h+var_6C], 34h ; '4'
0x1800fd056  mov     ebx, 8007000Eh
0x1800fd05b  mov     [rbp+57h+var_AC], 37Ah
0x1800fd062  jmp     loc_1800FD2C2
0x1800fd067  mov     [rbp+57h+var_A8], rax
0x1800fd06b  inc     r12
0x1800fd06e  cmp     [r13+r12*2+0], r14w
0x1800fd074  jnz     short loc_1800FD06B
0x1800fd076  mov     edx, 101h; unsigned int
0x1800fd07b  lea     rcx, [rbp+57h+String1]; this
0x1800fd07f  call    ?ExtendBuffer@CWxString@@QEAAJK@Z; CWxString::ExtendBuffer(ulong)
0x1800fd084  xor     ecx, ecx
0x1800fd086  mov     ebx, eax
0x1800fd088  test    eax, eax
0x1800fd08a  jns     short loc_1800FD098
0x1800fd08c  mov     [rbp+57h+var_AC], 387h
0x1800fd093  jmp     loc_1800FD2C2
0x1800fd098  mov     eax, 1
0x1800fd09d  lea     r14d, [rax+1Fh]
0x1800fd0a1  mov     [rbp+57h+var_6C], ecx
0x1800fd0a4  mov     [rbp+57h+pvData], ecx
0x1800fd0a7  test    eax, eax
0x1800fd0a9  jz      loc_1800FD1AD
0x1800fd0af  mov     [rbp+57h+var_9C], ecx
0x1800fd0b2  mov     [rbp+57h+var_70], ecx
0x1800fd0b5  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800fd0bc  jz      short loc_1800FD0EB
0x1800fd0be  mov     edx, 11h
0x1800fd0c3  mov     dword ptr [rsp+0F0h+pcbActual], 4
0x1800fd0cb  lea     rax, [rbp+57h+pvData]
0x1800fd0cf  mov     ecx, 40Ch
0x1800fd0d4  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800fd0db  mov     qword ptr [rsp+0F0h+cbData], rax
0x1800fd0e0  lea     r9d, [rdx-0Dh]
0x1800fd0e4  call    WPP_SF_dqd
0x1800fd0e9  xor     ecx, ecx
0x1800fd0eb  mov     rax, [rdi+28h]
0x1800fd0ef  lea     r9, [rbp+57h+pvData]; pvData
0x1800fd0f3  mov     rdx, [rdi+20h]; tableid
0x1800fd0f7  mov     [rsp+0F0h+pretinfo], rcx; pretinfo
0x1800fd0fc  mov     [rsp+0F0h+grbit], ecx; grbit
0x1800fd100  mov     r8, [rax+8]
0x1800fd104  lea     rax, [rbp+57h+var_70]
0x1800fd108  mov     rcx, [rdi+10h]; sesid
0x1800fd10c  mov     [rsp+0F0h+pcbActual], rax; pcbActual
0x1800fd111  mov     [rsp+0F0h+cbData], 4; cbData
0x1800fd119  mov     r8d, [r8+10h]; columnid
0x1800fd11d  call    cs:__imp_JetRetrieveColumn
0x1800fd123  mov     ecx, eax; int
0x1800fd125  mov     edx, 1; int
0x1800fd12a  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800fd12f  xor     ecx, ecx
0x1800fd131  mov     ebx, eax
0x1800fd133  test    eax, eax
0x1800fd135  js      short loc_1800FD14D
0x1800fd137  cmp     [rbp+57h+var_70], 4
0x1800fd13b  jz      short loc_1800FD14B
0x1800fd13d  mov     ebx, 8000FFFFh
0x1800fd142  mov     [rbp+57h+var_9C], 0D6h
0x1800fd149  jmp     short loc_1800FD14D
0x1800fd14b  mov     ebx, ecx
0x1800fd14d  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800fd154  jz      short loc_1800FD171
0x1800fd156  mov     edx, 12h
0x1800fd15b  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800fd162  mov     ecx, 40Ch
0x1800fd167  mov     r9d, ebx
0x1800fd16a  call    WPP_SF_d
0x1800fd16f  xor     ecx, ecx
0x1800fd171  test    ebx, ebx
0x1800fd173  js      loc_1800FD1F9
0x1800fd179  cmp     r12d, [rbp+57h+pvData]
0x1800fd17d  jnz     short loc_1800FD1AD
0x1800fd17f  lea     r8, [rbp+57h+String1]; struct CWxString *
0x1800fd183  mov     edx, 3; unsigned int
0x1800fd188  mov     rcx, rdi; this
0x1800fd18b  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x1800fd190  xor     ecx, ecx
0x1800fd192  mov     ebx, eax
0x1800fd194  test    eax, eax
0x1800fd196  js      short loc_1800FD1F0
0x1800fd198  mov     rcx, [rbp+57h+String1]; String1
0x1800fd19c  mov     r8d, r12d; MaxCount
0x1800fd19f  mov     rdx, r13; String2
0x1800fd1a2  call    wcsncmp_0
0x1800fd1a7  xor     ecx, ecx
0x1800fd1a9  test    eax, eax
0x1800fd1ab  jz      short loc_1800FD1EC
0x1800fd1ad  mov     rdx, [rdi+20h]; tableid
0x1800fd1b1  xor     r9d, r9d; grbit
0x1800fd1b4  mov     rcx, [rdi+10h]; sesid
0x1800fd1b8  lea     r8d, [r9+1]; cRow
0x1800fd1bc  call    cs:__imp_JetMove
0x1800fd1c2  cmp     eax, 0FFFFF9BDh
0x1800fd1c7  jz      short loc_1800FD1E3
0x1800fd1c9  mov     edx, 1; int
0x1800fd1ce  mov     ecx, eax; int
0x1800fd1d0  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800fd1d5  xor     ecx, ecx
0x1800fd1d7  mov     ebx, eax
0x1800fd1d9  test    eax, eax
0x1800fd1db  jns     loc_1800FD0AF
0x1800fd1e1  jmp     short loc_1800FD200
0x1800fd1e3  mov     ebx, 1
0x1800fd1e8  xor     ecx, ecx
0x1800fd1ea  jmp     short loc_1800FD200
0x1800fd1ec  mov     ebx, ecx
0x1800fd1ee  jmp     short loc_1800FD200
0x1800fd1f0  mov     [rbp+57h+var_6C], 32Fh
0x1800fd1f7  jmp     short loc_1800FD200
0x1800fd1f9  mov     [rbp+57h+var_6C], 324h
0x1800fd200  cmp     ebx, 1
0x1800fd203  jz      loc_1800FD2AB
0x1800fd209  test    ebx, ebx
0x1800fd20b  js      loc_1800FD2A2
0x1800fd211  mov     rcx, [rbp+57h+var_90]; this
0x1800fd215  lea     r9, [rbp+57h+var_B0]; int *
0x1800fd219  lea     r8, [rbp+57h+SystemTimeAsFileTime]; union FILETIMEEX *
0x1800fd21d  mov     rdx, rdi; struct CJetContext *
0x1800fd220  call    ?CheckForExpiredCookie@CCookieContainerProps@@AEAAJPEAVCJetContext@@PEATFILETIMEEX@@PEAH@Z; CCookieContainerProps::CheckForExpiredCookie(CJetContext *,FILETIMEEX *,int *)
0x1800fd225  xor     ecx, ecx; dwFlags
0x1800fd227  mov     ebx, eax
0x1800fd229  test    eax, eax
0x1800fd22b  js      short loc_1800FD299
0x1800fd22d  cmp     [rbp+57h+var_B0], ecx
  ... truncated ...
```
