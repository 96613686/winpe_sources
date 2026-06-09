# CHstsContainerProps::RebuildHstsBloomFilter(void)

- ea: `0x1800ab018`
- end: `0x1800ab4a5`
- name: `?RebuildHstsBloomFilter@CHstsContainerProps@@QEAAJXZ`
- size: `1165`
- prototype: `__int64 __fastcall(CHstsContainerProps *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800aa730`

## callees

- `0x180021360`
- `0x180025910`
- `0x18007ec9c`
- `0x180081d90`
- `0x180083dc4`
- `0x1800861f8`
- `0x1800ab018`
- `0x1800aca44`
- `0x1800acab8`
- `0x1800ace84`
- `0x18014a7a0`
- `0x1801abdac`
- `0x1801e1790`
- `0x1801e25fc`
- `0x1801e490c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab0bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab3ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab0bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab3ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab089`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab089`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ab0ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ab0ca`
- `ESENT!JetRetrieveColumn` at `0x1800ab1eb`
- `ESENT!JetRetrieveColumn` at `0x1800ab2d1`
- `ESENT!JetRetrieveColumn` at `0x1800ab1eb`
- `ESENT!JetRetrieveColumn` at `0x1800ab2d1`
- `ESENT!JetRollback` at `0x1800ab384`
- `ESENT!JetRollback` at `0x1800ab384`
- `ESENT!JetBeginTransaction` at `0x1800ab10d`
- `ESENT!JetBeginTransaction` at `0x1800ab10d`
- `ESENT!JetMove` at `0x1800ab158`
- `ESENT!JetMove` at `0x1800ab158`

## pseudocode

```c
__int64 __fastcall CHstsContainerProps::RebuildHstsBloomFilter(CHstsContainerProps *this)
{
  int v2; // r12d
  unsigned int *v3; // rdi
  __int64 *v4; // rbx
  unsigned __int8 *v5; // r15
  unsigned int v6; // r13d
  int v7; // eax
  unsigned int v8; // r9d
  JET_SESID *v9; // rdi
  int StringColumn; // ebx
  JET_ERR v11; // eax
  int i; // ebx
  JET_ERR v13; // eax
  JET_ERR v14; // eax
  JET_ERR v15; // eax
  unsigned int v16; // r8d
  int v18; // [rsp+40h] [rbp-49h]
  unsigned __int8 *v19; // [rsp+48h] [rbp-41h] BYREF
  struct CJetContext *v20; // [rsp+50h] [rbp-39h] BYREF
  int v21; // [rsp+5Ch] [rbp-2Dh]
  unsigned int pcbActual; // [rsp+60h] [rbp-29h] BYREF
  int v23; // [rsp+64h] [rbp-25h]
  unsigned int v24; // [rsp+68h] [rbp-21h] BYREF
  unsigned __int64 pvData; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int16 *v26; // [rsp+78h] [rbp-11h] BYREF
  unsigned int v27[2]; // [rsp+80h] [rbp-9h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-1h] BYREF

  v26 = (unsigned __int16 *)&Data;
  v23 = 0;
  v2 = 0;
  *(_QWORD *)v27 = 0;
  v24 = 0;
  v20 = 0;
  pvData = 0;
  SystemTimeAsFileTime = 0;
  v3 = (unsigned int *)((char *)this + 112);
  v4 = (__int64 *)((char *)this + 104);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qqD(1036, 23, (unsigned int)WPP_ae00b7117931323f1bc64bef90768346_Traceguids, (_DWORD)this, *v4);
  if ( this != (CHstsContainerProps *)-16LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v2 = 1;
  }
  v5 = (unsigned __int8 *)*v4;
  if ( *v4 )
  {
    v6 = *v3;
    *v3 = 0;
    v18 = 0;
    v19 = v5;
    *v4 = 0;
    if ( this != (CHstsContainerProps *)-16LL && v2 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      v2 = 0;
    }
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v7 = CJetContextList::AcquireContext(*((CJetContextList **)this + 11), &v20, 0);
    v9 = (JET_SESID *)v20;
    StringColumn = v7;
    if ( v7 < 0 )
    {
      v23 = 792;
    }
    else
    {
      StringColumn = CJetContext::SetCurrentIndex(v20, 0, L"EntryIdIndex", v8);
      if ( StringColumn < 0 )
      {
        v23 = 793;
      }
      else
      {
        v11 = JetBeginTransaction(v9[2]);
        StringColumn = HRESULTFromJET_ERR(v11, 1);
        if ( StringColumn >= 0 )
        {
          v18 = 1;
          for ( i = 0x80000000; ; i = 1 )
          {
            if ( (unsigned int)CCacheStore::IsTerminating(*(CCacheStore **)(*((_QWORD *)this + 9) + 16LL))
              || (v13 = JetMove(v9[2], v9[4], i, 0), v13 == -1603) )
            {
              CBloomFilterPartition::CommitUpdate(*((CBloomFilterPartition **)this + 12), &v19, v6);
              v5 = v19;
              StringColumn = 0;
              goto LABEL_39;
            }
            StringColumn = HRESULTFromJET_ERR(v13, 1);
            if ( StringColumn < 0 )
              goto LABEL_39;
            v21 = 0;
            pcbActual = 0;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_dqd(1036, 17, (unsigned int)WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 5, (__int64)&pvData);
            v14 = JetRetrieveColumn(
                    v9[2],
                    v9[4],
                    *(_DWORD *)(*(_QWORD *)(v9[5] + 8) + 20LL),
                    &pvData,
                    8u,
                    &pcbActual,
                    0,
                    0);
            StringColumn = HRESULTFromJET_ERR(v14, 1);
            if ( StringColumn >= 0 )
            {
              if ( pcbActual == 8 )
              {
                StringColumn = 0;
              }
              else
              {
                StringColumn = -2147418113;
                v21 = 214;
              }
            }
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 18, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)StringColumn);
            if ( StringColumn < 0 )
              break;
            if ( pvData >= *(_QWORD *)&SystemTimeAsFileTime )
            {
              StringColumn = CJetContext::GetStringColumn((CJetContext *)v9, 2u, (struct CWxString *)&v26);
              if ( StringColumn < 0 )
              {
                v23 = 822;
                goto LABEL_39;
              }
              v24 = 0;
              v21 = 0;
              pcbActual = 0;
              if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
                WPP_SF_dqd(1036, 17, (unsigned int)WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 3, (__int64)&v24);
              v15 = JetRetrieveColumn(
                      v9[2],
                      v9[4],
                      *(_DWORD *)(*(_QWORD *)(v9[5] + 8) + 12LL),
                      &v24,
                      4u,
                      &pcbActual,
                      0,
                      0);
              StringColumn = HRESULTFromJET_ERR(v15, 1);
              if ( StringColumn >= 0 )
              {
                if ( pcbActual == 4 )
                {
                  StringColumn = 0;
                }
                else
                {
                  StringColumn = -2147418113;
                  v21 = 214;
                }
              }
              if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
                WPP_SF_d(1036, 18, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)StringColumn);
              if ( StringColumn < 0 )
              {
                v23 = 827;
                goto LABEL_39;
              }
              v16 = v24;
              if ( v24 > v27[0] )
              {
                v16 = v27[0];
                v24 = v27[0];
              }
              StringColumn = CHstsContainerProps::AddHstsEntryToBloomFilter(this, v26, v16, v5, v6);
              if ( StringColumn < 0 )
              {
                v23 = 834;
                goto LABEL_39;
              }
            }
          }
          v23 = 815;
        }
      }
    }
LABEL_39:
    if ( v5 )
      CBloomFilterPartition::AbortUpdate(*((CBloomFilterPartition **)this + 12), &v19);
    if ( v18 )
      JetRollback(v9[2], 0);
  }
  else
  {
    StringColumn = 0;
  }
  CJetContextList::ReleaseContext(*((CJetContextList **)this + 11), &v20);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 24, WPP_ae00b7117931323f1bc64bef90768346_Traceguids, (unsigned int)StringColumn);
  if ( v2 && this != (CHstsContainerProps *)-16LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CWxString::_Release((CWxString *)&v26);
  return (unsigned int)StringColumn;
}

```

## disassembly

```asm
0x1800ab018  push    rbp
0x1800ab01a  push    rbx
0x1800ab01b  push    rsi
0x1800ab01c  push    rdi
0x1800ab01d  push    r12
0x1800ab01f  push    r13
0x1800ab021  push    r14
0x1800ab023  push    r15
0x1800ab025  lea     rbp, [rsp-1Fh]
0x1800ab02a  sub     rsp, 0A8h
0x1800ab031  mov     rax, cs:__security_cookie
0x1800ab038  xor     rax, rsp
0x1800ab03b  mov     [rbp+57h+var_50], rax
0x1800ab03f  mov     rsi, rcx
0x1800ab042  lea     rax, Data
0x1800ab049  xor     ecx, ecx
0x1800ab04b  mov     [rbp+57h+var_68], rax
0x1800ab04f  mov     [rbp+57h+var_7C], ecx
0x1800ab052  mov     r12d, ecx
0x1800ab055  mov     qword ptr [rbp+57h+var_60], rcx
0x1800ab059  lea     r14, [rsi+10h]
0x1800ab05d  mov     [rbp+57h+var_78], ecx
0x1800ab060  mov     [rbp+57h+var_90], rcx
0x1800ab064  mov     [rbp+57h+pvData], rcx
0x1800ab068  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x1800ab06c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ab073  lea     rdi, [rsi+70h]
0x1800ab077  lea     rbx, [rsi+68h]
0x1800ab07b  jnz     loc_1800AB3FB
0x1800ab081  test    r14, r14
0x1800ab084  jz      short loc_1800AB095
0x1800ab086  mov     rcx, r14; lpCriticalSection
0x1800ab089  call    cs:__imp_EnterCriticalSection
0x1800ab08f  xor     ecx, ecx
0x1800ab091  lea     r12d, [rcx+1]
0x1800ab095  mov     r15, [rbx]
0x1800ab098  test    r15, r15
0x1800ab09b  jz      loc_1800AB38C
0x1800ab0a1  mov     r13d, [rdi]
0x1800ab0a4  mov     [rdi], ecx
0x1800ab0a6  mov     [rbp+57h+var_A0], ecx
0x1800ab0a9  mov     [rbp+57h+var_98], r15
0x1800ab0ad  mov     [rbx], rcx
0x1800ab0b0  test    r14, r14
0x1800ab0b3  jz      short loc_1800AB0C6
0x1800ab0b5  test    r12d, r12d
0x1800ab0b8  jz      short loc_1800AB0C6
0x1800ab0ba  mov     rcx, r14; lpCriticalSection
0x1800ab0bd  call    cs:__imp_LeaveCriticalSection
0x1800ab0c3  xor     r12d, r12d
0x1800ab0c6  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800ab0ca  call    cs:__imp_GetSystemTimeAsFileTime
0x1800ab0d0  mov     rcx, [rsi+58h]; this
0x1800ab0d4  lea     rdx, [rbp+57h+var_90]; struct CJetContext **
0x1800ab0d8  xor     r8d, r8d; int *
0x1800ab0db  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800ab0e0  mov     rdi, [rbp+57h+var_90]
0x1800ab0e4  mov     ebx, eax
0x1800ab0e6  test    eax, eax
0x1800ab0e8  js      loc_1800AB457
0x1800ab0ee  lea     r8, aEntryidindex; "EntryIdIndex"
0x1800ab0f5  xor     edx, edx; unsigned int
0x1800ab0f7  mov     rcx, rdi; this
0x1800ab0fa  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1800ab0ff  mov     ebx, eax
0x1800ab101  test    eax, eax
0x1800ab103  js      loc_1800AB463
0x1800ab109  mov     rcx, [rdi+10h]; sesid
0x1800ab10d  call    cs:__imp_JetBeginTransaction
0x1800ab113  mov     ecx, eax; int
0x1800ab115  mov     edx, 1; int
0x1800ab11a  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ab11f  mov     ebx, eax
0x1800ab121  test    eax, eax
0x1800ab123  js      loc_1800AB36F
0x1800ab129  mov     [rbp+57h+var_A0], 1
0x1800ab130  mov     ebx, 80000000h
0x1800ab135  mov     rcx, [rsi+48h]
0x1800ab139  mov     rcx, [rcx+10h]; this
0x1800ab13d  call    ?IsTerminating@CCacheStore@@QEAAHXZ; CCacheStore::IsTerminating(void)
0x1800ab142  test    eax, eax
0x1800ab144  jnz     loc_1800AB359
0x1800ab14a  mov     rdx, [rdi+20h]; tableid
0x1800ab14e  xor     r9d, r9d; grbit
0x1800ab151  mov     rcx, [rdi+10h]; sesid
0x1800ab155  mov     r8d, ebx; cRow
0x1800ab158  call    cs:__imp_JetMove
0x1800ab15e  cmp     eax, 0FFFFF9BDh
0x1800ab163  jz      loc_1800AB359
0x1800ab169  mov     edx, 1; int
0x1800ab16e  mov     ecx, eax; int
0x1800ab170  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ab175  mov     ebx, eax
0x1800ab177  test    eax, eax
0x1800ab179  js      loc_1800AB36F
0x1800ab17f  xor     ebx, ebx
0x1800ab181  mov     [rbp+57h+var_84], ebx
0x1800ab184  mov     [rbp+57h+var_80], ebx
0x1800ab187  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ab18e  jz      short loc_1800AB1B9
0x1800ab190  lea     rax, [rbp+57h+pvData]
0x1800ab194  mov     dword ptr [rsp+0E0h+pcbActual], 8
0x1800ab19c  lea     edx, [rbx+11h]
0x1800ab19f  mov     qword ptr [rsp+0E0h+cbData], rax
0x1800ab1a4  mov     ecx, 40Ch
0x1800ab1a9  lea     r9d, [rbx+5]
0x1800ab1ad  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ab1b4  call    WPP_SF_dqd
0x1800ab1b9  mov     rax, [rdi+28h]
0x1800ab1bd  lea     r9, [rbp+57h+pvData]; pvData
0x1800ab1c1  mov     rdx, [rdi+20h]; tableid
0x1800ab1c5  mov     rcx, [rdi+10h]; sesid
0x1800ab1c9  mov     [rsp+0E0h+pretinfo], rbx; pretinfo
0x1800ab1ce  mov     r8, [rax+8]
0x1800ab1d2  lea     rax, [rbp+57h+var_80]
0x1800ab1d6  mov     [rsp+0E0h+grbit], ebx; grbit
0x1800ab1da  mov     [rsp+0E0h+pcbActual], rax; pcbActual
0x1800ab1df  mov     [rsp+0E0h+cbData], 8; cbData
0x1800ab1e7  mov     r8d, [r8+14h]; columnid
0x1800ab1eb  call    cs:__imp_JetRetrieveColumn
0x1800ab1f1  mov     ecx, eax; int
0x1800ab1f3  mov     edx, 1; int
0x1800ab1f8  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ab1fd  mov     ebx, eax
0x1800ab1ff  test    eax, eax
0x1800ab201  js      short loc_1800AB20F
0x1800ab203  cmp     [rbp+57h+var_80], 8
0x1800ab207  jnz     loc_1800AB435
0x1800ab20d  xor     ebx, ebx
0x1800ab20f  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ab216  jz      short loc_1800AB231
0x1800ab218  mov     edx, 12h
0x1800ab21d  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ab224  mov     ecx, 40Ch
0x1800ab229  mov     r9d, ebx
0x1800ab22c  call    WPP_SF_d
0x1800ab231  test    ebx, ebx
0x1800ab233  js      loc_1800AB487
0x1800ab239  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800ab23d  cmp     [rbp+57h+pvData], rax
0x1800ab241  jb      loc_1800AB34F
0x1800ab247  lea     r8, [rbp+57h+var_68]; struct CWxString *
0x1800ab24b  mov     edx, 2; unsigned int
0x1800ab250  mov     rcx, rdi; this
0x1800ab253  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x1800ab258  mov     ebx, eax
0x1800ab25a  test    eax, eax
0x1800ab25c  js      loc_1800AB47B
0x1800ab262  xor     ebx, ebx
0x1800ab264  mov     [rbp+57h+var_78], ebx
0x1800ab267  mov     [rbp+57h+var_84], ebx
0x1800ab26a  mov     [rbp+57h+var_80], ebx
0x1800ab26d  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ab274  jz      short loc_1800AB29F
0x1800ab276  lea     rax, [rbp+57h+var_78]
0x1800ab27a  mov     dword ptr [rsp+0E0h+pcbActual], 4
0x1800ab282  lea     edx, [rbx+11h]
0x1800ab285  mov     qword ptr [rsp+0E0h+cbData], rax
0x1800ab28a  mov     ecx, 40Ch
0x1800ab28f  lea     r9d, [rbx+3]
0x1800ab293  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ab29a  call    WPP_SF_dqd
0x1800ab29f  mov     rax, [rdi+28h]
0x1800ab2a3  lea     r9, [rbp+57h+var_78]; pvData
0x1800ab2a7  mov     rdx, [rdi+20h]; tableid
0x1800ab2ab  mov     rcx, [rdi+10h]; sesid
0x1800ab2af  mov     [rsp+0E0h+pretinfo], rbx; pretinfo
0x1800ab2b4  mov     r8, [rax+8]
0x1800ab2b8  lea     rax, [rbp+57h+var_80]
0x1800ab2bc  mov     [rsp+0E0h+grbit], ebx; grbit
0x1800ab2c0  mov     [rsp+0E0h+pcbActual], rax; pcbActual
0x1800ab2c5  mov     [rsp+0E0h+cbData], 4; cbData
0x1800ab2cd  mov     r8d, [r8+0Ch]; columnid
0x1800ab2d1  call    cs:__imp_JetRetrieveColumn
0x1800ab2d7  mov     ecx, eax; int
0x1800ab2d9  mov     edx, 1; int
0x1800ab2de  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ab2e3  mov     ebx, eax
0x1800ab2e5  test    eax, eax
0x1800ab2e7  js      short loc_1800AB2F5
0x1800ab2e9  cmp     [rbp+57h+var_80], 4
0x1800ab2ed  jnz     loc_1800AB446
0x1800ab2f3  xor     ebx, ebx
0x1800ab2f5  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ab2fc  jz      short loc_1800AB317
0x1800ab2fe  mov     edx, 12h
0x1800ab303  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ab30a  mov     ecx, 40Ch
0x1800ab30f  mov     r9d, ebx
0x1800ab312  call    WPP_SF_d
0x1800ab317  test    ebx, ebx
0x1800ab319  js      loc_1800AB429
0x1800ab31f  mov     r8d, [rbp+57h+var_78]
0x1800ab323  cmp     r8d, [rbp+57h+var_60]
0x1800ab327  jbe     short loc_1800AB331
0x1800ab329  mov     r8d, [rbp+57h+var_60]; unsigned int
0x1800ab32d  mov     [rbp+57h+var_78], r8d
0x1800ab331  mov     rdx, [rbp+57h+var_68]; unsigned __int16 *
0x1800ab335  mov     r9, r15; unsigned __int8 *
0x1800ab338  mov     rcx, rsi; this
0x1800ab33b  mov     [rsp+0E0h+cbData], r13d; unsigned int
0x1800ab340  call    ?AddHstsEntryToBloomFilter@CHstsContainerProps@@AEAAJPEBGKPEAEK@Z; CHstsContainerProps::AddHstsEntryToBloomFilter(ushort const *,ulong,uchar *,ulong)
0x1800ab345  mov     ebx, eax
0x1800ab347  test    eax, eax
0x1800ab349  js      loc_1800AB46F
0x1800ab34f  mov     ebx, 1
0x1800ab354  jmp     loc_1800AB135
0x1800ab359  mov     rcx, [rsi+60h]; this
0x1800ab35d  lea     rdx, [rbp+57h+var_98]; unsigned __int8 **
0x1800ab361  mov     r8d, r13d; unsigned int
0x1800ab364  call    ?CommitUpdate@CBloomFilterPartition@@QEAAXPEAPEAEK@Z; CBloomFilterPartition::CommitUpdate(uchar * *,ulong)
0x1800ab369  mov     r15, [rbp+57h+var_98]
0x1800ab36d  xor     ebx, ebx
0x1800ab36f  test    r15, r15
0x1800ab372  jnz     loc_1800AB493
0x1800ab378  cmp     [rbp+57h+var_A0], 0
0x1800ab37c  jz      short loc_1800AB38E
0x1800ab37e  mov     rcx, [rdi+10h]; sesid
0x1800ab382  xor     edx, edx; grbit
0x1800ab384  call    cs:__imp_JetRollback
0x1800ab38a  jmp     short loc_1800AB38E
0x1800ab38c  mov     ebx, ecx
0x1800ab38e  mov     rcx, [rsi+58h]; this
0x1800ab392  lea     rdx, [rbp+57h+var_90]; struct CJetContext **
0x1800ab396  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1800ab39b  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ab3a2  jz      short loc_1800AB3BD
0x1800ab3a4  mov     edx, 18h
0x1800ab3a9  lea     r8, WPP_ae00b7117931323f1bc64bef90768346_Traceguids
0x1800ab3b0  mov     ecx, 40Ch
0x1800ab3b5  mov     r9d, ebx
0x1800ab3b8  call    WPP_SF_d
0x1800ab3bd  test    r12d, r12d
0x1800ab3c0  jz      short loc_1800AB3D0
0x1800ab3c2  test    r14, r14
0x1800ab3c5  jz      short loc_1800AB3D0
0x1800ab3c7  mov     rcx, r14; lpCriticalSection
0x1800ab3ca  call    cs:__imp_LeaveCriticalSection
0x1800ab3d0  lea     rcx, [rbp+57h+var_68]; this
0x1800ab3d4  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800ab3d9  mov     eax, ebx
0x1800ab3db  mov     rcx, [rbp+57h+var_50]
0x1800ab3df  xor     rcx, rsp; StackCookie
0x1800ab3e2  call    __security_check_cookie
0x1800ab3e7  add     rsp, 0A8h
0x1800ab3ee  pop     r15
0x1800ab3f0  pop     r14
0x1800ab3f2  pop     r13
0x1800ab3f4  pop     r12
0x1800ab3f6  pop     rdi
0x1800ab3f7  pop     rsi
0x1800ab3f8  pop     rbx
0x1800ab3f9  pop     rbp
0x1800ab3fa  retn
0x1800ab3fb  mov     eax, [rdi]
0x1800ab3fd  lea     r8, WPP_ae00b7117931323f1bc64bef90768346_Traceguids
0x1800ab404  mov     dword ptr [rsp+0E0h+pcbActual], eax
0x1800ab408  mov     edx, 17h
0x1800ab40d  mov     rax, [rbx]
0x1800ab410  mov     ecx, 40Ch
0x1800ab415  mov     r9, rsi
0x1800ab418  mov     qword ptr [rsp+0E0h+cbData], rax
0x1800ab41d  call    WPP_SF_qqD
0x1800ab422  xor     ecx, ecx
0x1800ab424  jmp     loc_1800AB081
0x1800ab429  mov     [rbp+57h+var_7C], 33Bh
0x1800ab430  jmp     loc_1800AB36F
0x1800ab435  mov     ebx, 8000FFFFh
0x1800ab43a  mov     [rbp+57h+var_84], 0D6h
0x1800ab441  jmp     loc_1800AB20F
0x1800ab446  mov     ebx, 8000FFFFh
0x1800ab44b  mov     [rbp+57h+var_84], 0D6h
0x1800ab452  jmp     loc_1800AB2F5
0x1800ab457  mov     [rbp+57h+var_7C], 318h
0x1800ab45e  jmp     loc_1800AB36F
0x1800ab463  mov     [rbp+57h+var_7C], 319h
0x1800ab46a  jmp     loc_1800AB36F
0x1800ab46f  mov     [rbp+57h+var_7C], 342h
0x1800ab476  jmp     loc_1800AB36F
0x1800ab47b  mov     [rbp+57h+var_7C], 336h
0x1800ab482  jmp     loc_1800AB36F
0x1800ab487  mov     [rbp+57h+var_7C], 32Fh
0x1800ab48e  jmp     loc_1800AB36F
0x1800ab493  mov     rcx, [rsi+60h]; this
0x1800ab497  lea     rdx, [rbp+57h+var_98]; unsigned __int8 **
0x1800ab49b  call    ?AbortUpdate@CBloomFilterPartition@@QEAAXPEAPEAE@Z; CBloomFilterPartition::AbortUpdate(uchar * *)
0x1800ab4a0  jmp     loc_1800AB378
```
