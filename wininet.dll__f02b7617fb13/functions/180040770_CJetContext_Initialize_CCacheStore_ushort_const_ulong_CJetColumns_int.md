# CJetContext::Initialize(CCacheStore *,ushort const *,ulong,CJetColumns *,int *)

- ea: `0x180040770`
- end: `0x180040ced`
- name: `?Initialize@CJetContext@@QEAAJPEAVCCacheStore@@PEBGKPEAVCJetColumns@@PEAH@Z`
- size: `1405`
- prototype: `__int64 __fastcall(CJetContext *__hidden this, struct CCacheStore *, const unsigned __int16 *, unsigned int, struct CJetColumns *, int *)`
- caller_count: `10`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x180041020`
- `0x180083dc4`
- `0x1800ed2ec`
- `0x180119f50`
- `0x18011a1f8`
- `0x1801ba648`
- `0x1801bab64`
- `0x1801bb05c`
- `0x1801bbaa0`
- `0x1801bc00c`

## callees

- `0x18003f5d4`
- `0x180040770`
- `0x180040cf4`
- `0x180040e6c`
- `0x18007ec9c`
- `0x18007fbc4`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x180154882`
- `0x1801a90c8`
- `0x1801e1790`
- `0x1801e2a6c`
- `0x1801e3180`
- `0x1801e4fd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040ac3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040ac3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040a23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040a23`
- `ESENT!JetCloseTable` at `0x180040c7d`
- `ESENT!JetCloseTable` at `0x180040cc8`
- `ESENT!JetCloseTable` at `0x180040c7d`
- `ESENT!JetCloseTable` at `0x180040cc8`
- `ESENT!JetOpenTableW` at `0x180040a58`
- `ESENT!JetOpenTableW` at `0x180040cba`
- `ESENT!JetOpenTableW` at `0x180040a58`
- `ESENT!JetOpenTableW` at `0x180040cba`
- `ESENT!JetCreateTableColumnIndexW` at `0x180040c1d`
- `ESENT!JetCreateTableColumnIndexW` at `0x180040c1d`

## pseudocode

```c
__int64 __fastcall CJetContext::Initialize(
        CJetContext *this,
        struct CCacheStore *a2,
        WCHAR *a3,
        unsigned int a4,
        struct CJetColumns *a5,
        int *a6)
{
  CJetContext *v8; // rdi
  __int64 v9; // r13
  int v10; // edx
  int v11; // ecx
  int v12; // r8d
  __int64 v13; // rcx
  int v14; // esi
  __int64 v15; // rbx
  size_t v16; // rdi
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  int Instance; // eax
  int v22; // edx
  int v23; // r8d
  JET_DBID v24; // r14d
  JET_SESID v25; // rbx
  JET_ERR v26; // eax
  int v27; // r14d
  CJetColumns **v28; // rbx
  unsigned int v29; // ebx
  int v31; // eax
  JET_ERR v32; // eax
  int v33; // eax
  int grbit; // [rsp+28h] [rbp-D8h]
  int v35; // [rsp+38h] [rbp-C8h]
  unsigned int v36; // [rsp+50h] [rbp-B0h]
  int v37; // [rsp+50h] [rbp-B0h]
  int v38; // [rsp+54h] [rbp-ACh]
  int v39; // [rsp+54h] [rbp-ACh]
  JET_TABLEID ptableid; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v42; // [rsp+70h] [rbp-90h] BYREF
  int v43[2]; // [rsp+78h] [rbp-88h] BYREF
  JET_TABLECREATE_W szTableName; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v45[240]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v46[1408]; // [rsp+1C0h] [rbp+C0h] BYREF

  *(_QWORD *)v43 = this;
  v8 = this;
  v9 = a4;
  HIDWORD(ptableid) = 0;
  memset_0(&szTableName, 0, sizeof(szTableName));
  v42 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qqSdqq(v11, v10, v12, (_DWORD)v8, (__int64)a2, (__int64)a3, v9, (__int64)a5, (__int64)a6);
  HIDWORD(ptableid) = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_Sddqdqq(v11, v10, v12, (_DWORD)a3, v9, grbit, (__int64)v46, v35, (__int64)v45, (__int64)&szTableName);
  if ( (unsigned int)(v9 - 1) > 0xB )
  {
    HIDWORD(ptableid) = 625;
  }
  else
  {
    v13 = LODWORD(qword_1801EF300[10 * v9 - 5]);
    v38 = v13;
    if ( (unsigned int)v13 > 0x19 )
    {
      HIDWORD(ptableid) = 633;
    }
    else
    {
      v36 = qword_1801EF300[10 * v9 - 3];
      if ( v36 <= 3 )
      {
        v14 = 0;
        v15 = 56 * v13;
        memcpy_0(v46, (const void *)qword_1801EF300[10 * v9 - 6], 56 * v13);
        v16 = 80LL * LODWORD(qword_1801EF300[10 * v9 - 3]);
        memcpy_0(v45, (const void *)qword_1801EF300[10 * v9 - 4], v16);
        memset_0(&v46[v15], 0, 56LL * (unsigned int)(25 - v38));
        memset_0(&v45[v16], 0, 80LL * (3 - v36));
        v8 = *(CJetContext **)v43;
        v17 = *(_OWORD *)&qword_1801EF300[10 * v9 - 8];
        *(_OWORD *)&szTableName.cbStruct = *(_OWORD *)&qword_1801EF300[10 * v9 - 10];
        v18 = *(_OWORD *)&qword_1801EF300[10 * v9 - 6];
        *(_OWORD *)&szTableName.szTemplateTableName = v17;
        v19 = *(_OWORD *)&qword_1801EF300[10 * v9 - 4];
        *(_OWORD *)&szTableName.rgcolumncreate = v18;
        v20 = *(_OWORD *)&qword_1801EF300[10 * v9 - 2];
        szTableName.szTableName = a3;
        szTableName.rgcolumncreate = (JET_COLUMNCREATE_W *)v46;
        *(_QWORD *)&szTableName.cIndexes = *((_QWORD *)&v19 + 1);
        szTableName.rgindexcreate = (JET_INDEXCREATE_W *)v45;
        *(_OWORD *)&szTableName.tableid = v20;
        goto LABEL_9;
      }
      HIDWORD(ptableid) = 634;
    }
  }
  v14 = -2147024809;
LABEL_9:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 11, WPP_0b67bf9c5025321f7ac79c83f89f8edf_Traceguids, (unsigned int)v14);
  if ( v14 < 0 )
  {
    HIDWORD(ptableid) = 84;
LABEL_34:
    v29 = v14;
    goto LABEL_35;
  }
  Instance = CCacheStore::NewLocalSession(a2, (unsigned __int64 *)v8 + 2, (unsigned int *)v8 + 6);
  v14 = Instance;
  if ( Instance < 0 )
  {
    HIDWORD(ptableid) = 86;
LABEL_32:
    v29 = Instance;
    goto LABEL_35;
  }
  v24 = *((_DWORD *)v8 + 6);
  v25 = *((_QWORD *)v8 + 2);
  ptableid = -1;
  v39 = 0;
  v37 = 0;
  v43[0] = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qidqqq(
      (unsigned int)&v42,
      v22,
      v23,
      (_DWORD)a2,
      v25,
      v24,
      (__int64)&szTableName,
      (__int64)v8 + 32,
      (__int64)&v42);
  v42 = 0;
  if ( a2 != (struct CCacheStore *)-48LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 48));
    v39 = 1;
  }
  v26 = JetOpenTableW(v25, v24, szTableName.szTableName, 0, 0, 8u, &ptableid);
  if ( v26 == -1305 )
  {
    v31 = 0;
    v43[1] = 0;
    v43[0] = 0;
    if ( (_DWORD)v9 == 9 )
    {
      CCacheStore::MigratePartitionTable(a2, v43);
      v31 = v43[0];
    }
    if ( !v31 )
    {
      v32 = JetCreateTableColumnIndexW(v25, v24, &szTableName);
      v33 = HRESULTFromJET_ERR(v32, 1);
      v14 = v33;
      if ( v33 < 0 )
      {
        v27 = v33;
        goto LABEL_19;
      }
      JetCloseTable(v25, szTableName.tableid);
      szTableName.tableid = -1;
      v37 = 1;
    }
    v26 = JetOpenTableW(v25, v24, szTableName.szTableName, 0, 0, 8u, &ptableid);
  }
  v27 = HRESULTFromJET_ERR(v26, 1);
  v14 = v27;
  if ( v27 >= 0 )
  {
    *((_QWORD *)v8 + 4) = ptableid;
    v42 = v37;
    goto LABEL_44;
  }
LABEL_19:
  if ( ptableid == -1 )
    goto LABEL_20;
  JetCloseTable(v25, ptableid);
LABEL_44:
  ptableid = -1;
LABEL_20:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 31, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, (unsigned int)v27);
  if ( v39 && a2 != (struct CCacheStore *)-48LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 48));
  if ( v14 < 0 )
  {
    HIDWORD(ptableid) = 87;
    goto LABEL_34;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 11, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, v42);
  v28 = (CJetColumns **)((char *)v8 + 40);
  if ( !a5 )
  {
    Instance = CClientLock::CreateInstance((struct CClientLock **)v8 + 5);
    v14 = Instance;
    if ( Instance < 0 )
    {
      HIDWORD(ptableid) = 103;
    }
    else
    {
      Instance = GetColumnIdsByType(*((_QWORD *)v8 + 2), *((_DWORD *)v8 + 6), a3, v9, (unsigned int **)*v28 + 1);
      v14 = Instance;
      if ( Instance < 0 )
        HIDWORD(ptableid) = 104;
    }
    goto LABEL_32;
  }
  _InterlockedIncrement((volatile signed __int32 *)a5);
  if ( *v28 )
    CJetColumns::Release(*v28);
  v14 = 0;
  *v28 = a5;
  v29 = 0;
LABEL_35:
  if ( a6 )
    *a6 = v42;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 12, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)v14);
  return v29;
}

```

## disassembly

```asm
0x180040770  push    rbp
0x180040772  push    rbx
0x180040773  push    rsi
0x180040774  push    rdi
0x180040775  push    r12
0x180040777  push    r13
0x180040779  push    r14
0x18004077b  push    r15
0x18004077d  lea     rbp, [rsp-658h]
0x180040785  sub     rsp, 758h
0x18004078c  mov     rax, cs:__security_cookie
0x180040793  xor     rax, rsp
0x180040796  mov     [rbp+690h+var_50], rax
0x18004079d  mov     rsi, [rbp+690h+arg_28]
0x1800407a4  mov     rbx, r8
0x1800407a7  mov     r12, [rbp+690h+arg_20]
0x1800407ae  mov     r15, rdx
0x1800407b1  mov     qword ptr [rsp+790h+var_718], rcx
0x1800407b6  xor     edx, edx; Val
0x1800407b8  mov     rdi, rcx
0x1800407bb  mov     r13d, r9d
0x1800407be  lea     rcx, [rbp+690h+szTableName]; void *
0x1800407c2  mov     [rsp+790h+var_738], rbx
0x1800407c7  mov     [rsp+790h+var_730], rsi
0x1800407cc  lea     r8d, [rdx+50h]; Size
0x1800407d0  mov     dword ptr [rsp+790h+var_728+4], 0
0x1800407d8  call    memset_0
0x1800407dd  mov     [rsp+790h+var_720], 0
0x1800407e5  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800407ec  jz      short loc_18004080F
0x1800407ee  mov     [rsp+790h+var_750], rsi
0x1800407f3  mov     r9, rdi
0x1800407f6  mov     [rsp+790h+var_758], r12
0x1800407fb  mov     dword ptr [rsp+790h+ptableid], r13d
0x180040800  mov     qword ptr [rsp+790h+grbit], rbx
0x180040805  mov     qword ptr [rsp+790h+cbParameters], r15
0x18004080a  call    WPP_SF_qqSdqq
0x18004080f  mov     dword ptr [rsp+790h+var_728+4], 0
0x180040817  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18004081e  jz      short loc_18004084B
0x180040820  lea     rax, [rbp+690h+szTableName]
0x180040824  mov     r9, rbx
0x180040827  mov     [rsp+790h+var_748], rax
0x18004082c  lea     rax, [rbp+690h+var_6C0]
0x180040830  mov     [rsp+790h+var_750], rax
0x180040835  lea     rax, [rbp+690h+var_5D0]
0x18004083c  mov     [rsp+790h+ptableid], rax
0x180040841  mov     [rsp+790h+cbParameters], r13d
0x180040846  call    WPP_SF_Sddqdqq
0x18004084b  lea     eax, [r13-1]
0x18004084f  cmp     eax, 0Bh
0x180040852  ja      loc_180040C51
0x180040858  lea     r14, ds:0[r13*4]
0x180040860  add     r14, r13
0x180040863  lea     rdx, qword_1801EF300
0x18004086a  add     r14, r14
0x18004086d  mov     ecx, [rdx+r14*8-28h]
0x180040872  mov     [rsp+790h+var_73C], ecx
0x180040876  cmp     ecx, 19h
0x180040879  ja      loc_180040C3D
0x18004087f  mov     eax, [rdx+r14*8-18h]
0x180040884  mov     [rsp+790h+var_740], eax
0x180040888  cmp     eax, 3
0x18004088b  ja      loc_180040C47
0x180040891  mov     rdx, [rdx+r14*8-30h]; Src
0x180040896  xor     esi, esi
0x180040898  imul    rbx, rcx, 38h ; '8'
0x18004089c  lea     rcx, [rbp+690h+var_5D0]; void *
0x1800408a3  mov     r8, rbx; Size
0x1800408a6  call    memcpy_0
0x1800408ab  lea     rdx, qword_1801EF300
0x1800408b2  mov     eax, [rdx+r14*8-18h]
0x1800408b7  lea     rcx, [rbp+690h+var_6C0]; void *
0x1800408bb  mov     rdx, [rdx+r14*8-20h]; Src
0x1800408c0  lea     rdi, [rax+rax*4]
0x1800408c4  shl     rdi, 4
0x1800408c8  mov     r8, rdi; Size
0x1800408cb  call    memcpy_0
0x1800408d0  lea     eax, [rsi+19h]
0x1800408d3  xor     edx, edx; Val
0x1800408d5  sub     eax, [rsp+790h+var_73C]
0x1800408d9  lea     rcx, [rbp+690h+var_5D0]
0x1800408e0  imul    r8, rax, 38h ; '8'; Size
0x1800408e4  add     rcx, rbx; void *
0x1800408e7  call    memset_0
0x1800408ec  lea     eax, [rsi+3]
0x1800408ef  xor     edx, edx; Val
0x1800408f1  sub     eax, [rsp+790h+var_740]
0x1800408f5  lea     rcx, [rbp+690h+var_6C0]
0x1800408f9  add     rcx, rdi; void *
0x1800408fc  lea     r8, [rax+rax*4]
0x180040900  shl     r8, 4; Size
0x180040904  call    memset_0
0x180040909  mov     rdi, qword ptr [rsp+790h+var_718]
0x18004090e  lea     rax, qword_1801EF300
0x180040915  movups  xmm0, xmmword ptr [rax+r14*8-50h]
0x18004091b  movups  xmm1, xmmword ptr [rax+r14*8-40h]
0x180040921  movaps  xmmword ptr [rbp+690h+szTableName], xmm0
0x180040925  movups  xmm0, xmmword ptr [rax+r14*8-30h]
0x18004092b  movaps  [rbp+690h+var_700], xmm1
0x18004092f  movups  xmm1, xmmword ptr [rax+r14*8-20h]
0x180040935  movaps  [rbp+690h+var_6F0], xmm0
0x180040939  movups  xmm0, xmmword ptr [rax+r14*8-10h]
0x18004093f  mov     rax, [rsp+790h+var_738]
0x180040944  mov     [rbp+690h+szTableName+8], rax
0x180040948  lea     rax, [rbp+690h+var_5D0]
0x18004094f  mov     qword ptr [rbp+690h+var_6F0], rax
0x180040953  lea     rax, [rbp+690h+var_6C0]
0x180040957  movaps  [rbp+690h+var_6E0], xmm1
0x18004095b  mov     qword ptr [rbp+690h+var_6E0], rax
0x18004095f  movaps  xmmword ptr [rbp+690h+tableid], xmm0
0x180040963  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18004096a  jz      short loc_180040985
0x18004096c  mov     edx, 0Bh
0x180040971  lea     r8, WPP_0b67bf9c5025321f7ac79c83f89f8edf_Traceguids
0x180040978  mov     ecx, 40Ch
0x18004097d  mov     r9d, esi
0x180040980  call    WPP_SF_d
0x180040985  test    esi, esi
0x180040987  js      loc_180040B42
0x18004098d  lea     rdx, [rdi+10h]; unsigned __int64 *
0x180040991  mov     rcx, r15; this
0x180040994  lea     r8, [rdi+18h]; unsigned int *
0x180040998  call    ?NewLocalSession@CCacheStore@@QEAAJPEA_KPEAK@Z; CCacheStore::NewLocalSession(unsigned __int64 *,ulong *)
0x18004099d  mov     esi, eax
0x18004099f  test    eax, eax
0x1800409a1  js      loc_180040BEA
0x1800409a7  mov     r14d, [rdi+18h]
0x1800409ab  lea     rax, [rdi+20h]
0x1800409af  mov     rbx, [rdi+10h]
0x1800409b3  lea     rsi, [r15+30h]
0x1800409b7  mov     dword ptr [rsp+790h+var_728+4], 0
0x1800409bf  mov     qword ptr [rsp+68h], 0FFFFFFFFFFFFFFFFh
0x1800409c8  mov     [rsp+790h+var_73C], 0
0x1800409d0  mov     [rsp+790h+var_740], 0
0x1800409d8  mov     [rsp+790h+var_718], 0
0x1800409e0  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800409e7  jz      short loc_180040A13
0x1800409e9  lea     rcx, [rsp+790h+var_720]
0x1800409ee  mov     r9, r15
0x1800409f1  mov     [rsp+790h+var_750], rcx
0x1800409f6  mov     [rsp+790h+var_758], rax
0x1800409fb  lea     rax, [rbp+690h+szTableName]
0x1800409ff  mov     [rsp+790h+ptableid], rax
0x180040a04  mov     [rsp+790h+grbit], r14d
0x180040a09  mov     qword ptr [rsp+790h+cbParameters], rbx
0x180040a0e  call    WPP_SF_qidqqq
0x180040a13  mov     [rsp+790h+var_720], 0
0x180040a1b  test    rsi, rsi
0x180040a1e  jz      short loc_180040A31
0x180040a20  mov     rcx, rsi; lpCriticalSection
0x180040a23  call    cs:__imp_EnterCriticalSection
0x180040a29  mov     [rsp+790h+var_73C], 1
0x180040a31  mov     r8, [rbp+690h+szTableName+8]; szTableName
0x180040a35  lea     rax, [rsp+790h+var_728]
0x180040a3a  mov     [rsp+790h+ptableid], rax; ptableid
0x180040a3f  xor     r9d, r9d; pvParameters
0x180040a42  mov     [rsp+790h+grbit], 8; grbit
0x180040a4a  mov     edx, r14d; dbid
0x180040a4d  mov     rcx, rbx; sesid
0x180040a50  mov     [rsp+790h+cbParameters], 0; cbParameters
0x180040a58  call    cs:__imp_JetOpenTableW
0x180040a5e  cmp     eax, 0FFFFFAE7h
0x180040a63  jz      loc_180040BF7
0x180040a69  mov     edx, 1; int
0x180040a6e  mov     ecx, eax; int
0x180040a70  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180040a75  mov     r14d, eax
0x180040a78  mov     esi, eax
0x180040a7a  test    eax, eax
0x180040a7c  jns     loc_180040BBE
0x180040a82  mov     rdx, [rsp+790h+var_728]; tableid
0x180040a87  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180040a8b  jnz     loc_180040CC5
0x180040a91  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180040a98  jz      short loc_180040AB3
0x180040a9a  mov     edx, 1Fh
0x180040a9f  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x180040aa6  mov     ecx, 40Ch
0x180040aab  mov     r9d, r14d
0x180040aae  call    WPP_SF_d
0x180040ab3  cmp     [rsp+790h+var_73C], 0
0x180040ab8  jz      short loc_180040AC9
0x180040aba  lea     rcx, [r15+30h]; lpCriticalSection
0x180040abe  test    rcx, rcx
0x180040ac1  jz      short loc_180040AC9
0x180040ac3  call    cs:__imp_LeaveCriticalSection
0x180040ac9  test    esi, esi
0x180040acb  js      loc_180040BDD
0x180040ad1  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180040ad8  jz      short loc_180040AF5
0x180040ada  mov     r9d, [rsp+790h+var_720]
0x180040adf  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x180040ae6  mov     edx, 0Bh
0x180040aeb  mov     ecx, 40Ch
0x180040af0  call    WPP_SF_d
0x180040af5  lea     rbx, [rdi+28h]
0x180040af9  test    r12, r12
0x180040afc  jnz     loc_180040BA3
0x180040b02  mov     rcx, rbx; struct CClientLock **
0x180040b05  call    ?CreateInstance@CClientLock@@SAJPEAPEAV1@@Z; CClientLock::CreateInstance(CClientLock * *)
0x180040b0a  mov     esi, eax
0x180040b0c  test    eax, eax
0x180040b0e  js      loc_180040CD3
0x180040b14  mov     rax, [rbx]
0x180040b17  mov     r9d, r13d; unsigned int
0x180040b1a  mov     r8, [rsp+790h+var_738]; unsigned __int16 *
0x180040b1f  add     rax, 8
0x180040b23  mov     edx, [rdi+18h]; dbid
0x180040b26  mov     rcx, [rdi+10h]; sesid
0x180040b2a  mov     qword ptr [rsp+790h+cbParameters], rax; unsigned int **
0x180040b2f  call    ?GetColumnIdsByType@@YAJ_KKPEBGKPEAPEAK@Z; GetColumnIdsByType(unsigned __int64,ulong,ushort const *,ulong,ulong * *)
0x180040b34  mov     esi, eax
0x180040b36  test    eax, eax
0x180040b38  js      loc_180040CE0
0x180040b3e  mov     ebx, eax
0x180040b40  jmp     short loc_180040B4C
0x180040b42  mov     dword ptr [rsp+790h+var_728+4], 54h ; 'T'
0x180040b4a  mov     ebx, esi
0x180040b4c  mov     rax, [rsp+790h+var_730]
0x180040b51  test    rax, rax
0x180040b54  jz      short loc_180040B5C
0x180040b56  mov     edx, [rsp+790h+var_720]
0x180040b5a  mov     [rax], edx
0x180040b5c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180040b63  jz      short loc_180040B7E
0x180040b65  mov     edx, 0Ch
0x180040b6a  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x180040b71  mov     ecx, 40Ch
0x180040b76  mov     r9d, esi
0x180040b79  call    WPP_SF_d
0x180040b7e  mov     eax, ebx
0x180040b80  mov     rcx, [rbp+690h+var_50]
0x180040b87  xor     rcx, rsp; StackCookie
0x180040b8a  call    __security_check_cookie
0x180040b8f  add     rsp, 758h
0x180040b96  pop     r15
0x180040b98  pop     r14
0x180040b9a  pop     r13
0x180040b9c  pop     r12
0x180040b9e  pop     rdi
0x180040b9f  pop     rsi
0x180040ba0  pop     rbx
0x180040ba1  pop     rbp
0x180040ba2  retn
0x180040ba3  lock inc dword ptr [r12]
0x180040ba8  mov     rcx, [rbx]; this
0x180040bab  test    rcx, rcx
0x180040bae  jz      short loc_180040BB5
0x180040bb0  call    ?Release@CJetColumns@@QEAAKXZ; CJetColumns::Release(void)
0x180040bb5  xor     esi, esi
0x180040bb7  mov     [rbx], r12
0x180040bba  xor     ebx, ebx
0x180040bbc  jmp     short loc_180040B4C
0x180040bbe  mov     rax, [rsp+790h+var_728]
0x180040bc3  mov     [rdi+20h], rax
0x180040bc7  mov     eax, [rsp+790h+var_740]
0x180040bcb  mov     [rsp+790h+var_720], eax
0x180040bcf  mov     [rsp+790h+var_728], 0FFFFFFFFFFFFFFFFh
0x180040bd8  jmp     loc_180040A91
0x180040bdd  mov     dword ptr [rsp+790h+var_728+4], 57h ; 'W'
0x180040be5  jmp     loc_180040B4A
0x180040bea  mov     dword ptr [rsp+790h+var_728+4], 56h ; 'V'
0x180040bf2  jmp     loc_180040B3E
0x180040bf7  xor     eax, eax
0x180040bf9  mov     [rsp+790h+var_718+4], 0
0x180040c01  mov     [rsp+790h+var_718], eax
0x180040c05  cmp     r13d, 9
0x180040c09  jz      short loc_180040C63
0x180040c0b  test    eax, eax
0x180040c0d  jnz     loc_180040C93
0x180040c13  lea     r8, [rbp+690h+szTableName]; ptablecreate
0x180040c17  mov     edx, r14d; dbid
0x180040c1a  mov     rcx, rbx; sesid
0x180040c1d  call    cs:__imp_JetCreateTableColumnIndexW
0x180040c23  mov     ecx, eax; int
0x180040c25  mov     edx, 1; int
0x180040c2a  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180040c2f  mov     esi, eax
0x180040c31  test    eax, eax
0x180040c33  jns     short loc_180040C76
0x180040c35  mov     r14d, eax
0x180040c38  jmp     loc_180040A82
0x180040c3d  mov     dword ptr [rsp+790h+var_728+4], 279h
0x180040c45  jmp     short loc_180040C59
0x180040c47  mov     dword ptr [rsp+790h+var_728+4], 27Ah
0x180040c4f  jmp     short loc_180040C59
0x180040c51  mov     dword ptr [rsp+790h+var_728+4], 271h
0x180040c59  mov     esi, 80070057h
0x180040c5e  jmp     loc_180040963
0x180040c63  lea     rdx, [rsp+790h+var_718]; int *
0x180040c68  mov     rcx, r15; this
0x180040c6b  call    ?MigratePartitionTable@CCacheStore@@QEAAJPEAH@Z; CCacheStore::MigratePartitionTable(int *)
0x180040c70  mov     eax, [rsp+790h+var_718]
0x180040c74  jmp     short loc_180040C0B
0x180040c76  mov     rdx, [rbp+690h+tableid]; tableid
0x180040c7a  mov     rcx, rbx; sesid
0x180040c7d  call    cs:__imp_JetCloseTable
0x180040c83  mov     [rbp+690h+tableid], 0FFFFFFFFFFFFFFFFh
0x180040c8b  mov     [rsp+790h+var_740], 1
  ... truncated ...
```
