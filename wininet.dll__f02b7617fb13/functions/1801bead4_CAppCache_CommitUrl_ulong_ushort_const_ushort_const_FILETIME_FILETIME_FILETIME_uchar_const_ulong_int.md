# CAppCache::CommitUrl(ulong,ushort const *,ushort const *,_FILETIME,_FILETIME,_FILETIME,uchar const *,ulong,int)

- ea: `0x1801bead4`
- end: `0x1801bf104`
- name: `?CommitUrl@CAppCache@@QEAAJKPEBG0U_FILETIME@@11PEBEKH@Z`
- size: `1584`
- prototype: `__int64 __usercall@<rax>(CAppCache *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, struct _FILETIME, struct _FILETIME, struct _FILETIME, const unsigned __int8 *, unsigned int, int)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801bccc0`
- `0x1801bf6f0`

## callees

- `0x180021360`
- `0x1800701d0`
- `0x18007ec9c`
- `0x180083dc4`
- `0x1800861f8`
- `0x1800c9b40`
- `0x1800ee168`
- `0x1800eee94`
- `0x1800f05dc`
- `0x1800f0608`
- `0x1800f0640`
- `0x1800fa844`
- `0x180136748`
- `0x18014a7a0`
- `0x1801abe20`
- `0x1801bead4`
- `0x1801c25c4`
- `0x1801c2d6c`
- `0x1801c388c`
- `0x1801c570c`
- `0x1801c6784`
- `0x1801df0f8`
- `0x1801e1790`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1801bec53`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1801bec53`
- `ESENT!JetCommitTransaction` at `0x1801bf087`
- `ESENT!JetCommitTransaction` at `0x1801bf087`
- `ESENT!JetUpdate` at `0x1801bf046`
- `ESENT!JetUpdate` at `0x1801bf046`
- `ESENT!JetPrepareUpdate` at `0x1801becfe`
- `ESENT!JetPrepareUpdate` at `0x1801bee0b`
- `ESENT!JetPrepareUpdate` at `0x1801becfe`
- `ESENT!JetPrepareUpdate` at `0x1801bee0b`
- `ESENT!JetRollback` at `0x1801bed0f`
- `ESENT!JetRollback` at `0x1801bed0f`
- `ESENT!JetBeginTransaction` at `0x1801beddb`
- `ESENT!JetBeginTransaction` at `0x1801beddb`

## pseudocode

```c
__int64 __fastcall CAppCache::CommitUrl(
        CFileListMap **this,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct _FILETIME a5,
        struct _FILETIME a6,
        struct _FILETIME a7,
        unsigned __int8 *a8,
        unsigned int a9,
        int a10)
{
  JET_SESID *v13; // rdi
  signed int updated; // ebx
  int v15; // r14d
  int v16; // r15d
  int Entry; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  int LastError; // eax
  CFileListMap *v21; // rcx
  int v22; // eax
  unsigned int v23; // r9d
  JET_ERR v25; // eax
  JET_ERR v26; // eax
  JET_ERR v27; // eax
  JET_ERR v28; // eax
  int v29; // [rsp+80h] [rbp-80h]
  CJetContext *v30; // [rsp+88h] [rbp-78h] BYREF
  char *v31; // [rsp+90h] [rbp-70h] BYREF
  __int64 v32; // [rsp+98h] [rbp-68h]
  LPCWSTR lpFileName; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v34; // [rsp+A8h] [rbp-58h] BYREF
  int v35; // [rsp+B0h] [rbp-50h] BYREF
  int v36; // [rsp+B4h] [rbp-4Ch] BYREF
  int v37; // [rsp+B8h] [rbp-48h] BYREF
  CFileListEntry *v38; // [rsp+C0h] [rbp-40h] BYREF
  int v39; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v40; // [rsp+D0h] [rbp-30h] BYREF
  struct _FILETIME v41; // [rsp+D8h] [rbp-28h] BYREF
  struct _FILETIME v42; // [rsp+E0h] [rbp-20h] BYREF
  struct _FILETIME v43; // [rsp+E8h] [rbp-18h] BYREF
  __int128 FileInformation; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v45; // [rsp+100h] [rbp+0h]
  unsigned int v46; // [rsp+110h] [rbp+10h]

  v39 = a2;
  v41 = a5;
  v43 = a7;
  v31 = (char *)(this + 16);
  v42 = a6;
  v13 = 0;
  v46 = 0;
  lpFileName = a4;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  v35 = 0;
  v38 = 0;
  v36 = 0;
  v37 = 0;
  FileInformation = 0;
  v40 = 0;
  v45 = 0;
  v34 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qdSSiiiqdl(
      a7.dwLowDateTime,
      0,
      a6.dwLowDateTime,
      (_DWORD)this,
      a2,
      (__int64)a3,
      (__int64)a4,
      a5.dwLowDateTime,
      a6.dwLowDateTime,
      a7.dwLowDateTime,
      (__int64)a8,
      a9,
      a10);
  AutoSrw::LockExclusive((AutoSrw *)&v31);
  updated = CAppCache::VerifyDirectory((CAppCache *)this, a4, (const unsigned __int16 **)&v34);
  if ( updated < 0 )
    goto LABEL_4;
  if ( *((_DWORD *)this + 34) == 2 )
  {
    updated = -2147483636;
LABEL_4:
    v15 = 0;
    v16 = 0;
    goto LABEL_19;
  }
  Entry = CFileListMap::FindEntry(this[5], a3, &v38);
  updated = Entry;
  if ( Entry < 0 )
    goto LABEL_4;
  if ( Entry == 1 )
  {
    updated = 0;
    v16 = 1;
    v15 = 0;
    goto LABEL_19;
  }
  if ( !GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
  {
    LastError = WxGetLastError(v19, v18);
    updated = LastError;
    if ( LastError > 0 )
      updated = (unsigned __int16)LastError | 0x80070000;
    if ( updated >= 0 )
      updated = -2147418113;
    goto LABEL_4;
  }
  v40 = v46 | ((unsigned __int64)HIDWORD(v45) << 32);
  v36 = *((_DWORD *)v38 + 4);
  v21 = this[19];
  v37 = *((_DWORD *)v38 + 4) & 1;
  v22 = CJetContextList::AcquireContext(*((CJetContextList **)v21 + 2), &v30, 0);
  v13 = (JET_SESID *)v30;
  updated = v22;
  if ( v22 < 0
    || (updated = CJetContext::SetCurrentIndex(v30, 0, L"EntryIdIndex", v23), updated < 0)
    || (v25 = JetBeginTransaction(v13[2]), updated = HRESULTFromJET_ERR(v25, 1), updated < 0) )
  {
    v15 = 0;
LABEL_18:
    v16 = 0;
    goto LABEL_19;
  }
  v26 = JetPrepareUpdate(v13[2], v13[4], 0);
  updated = HRESULTFromJET_ERR(v26, 1);
  if ( updated < 0 )
    goto LABEL_40;
  v29 = 1;
  v35 = WxComputePrefixHash(a3, 0xFFFFFFFFLL);
  updated = CJetContext::SetBasicColumn((CJetContext *)v13, 1u, this + 1, 8u);
  if ( updated < 0 )
    goto LABEL_40;
  updated = CJetContext::SetBasicColumn((CJetContext *)v13, 2u, &v35, 4u);
  if ( updated < 0 )
    goto LABEL_40;
  updated = CJetContext::SetStringColumn((CJetContext *)v13, 3u, a3);
  if ( updated < 0 )
    goto LABEL_40;
  updated = CJetContext::SetBinaryColumn((CJetContext *)v13, 0xAu, a8, a9);
  if ( updated < 0 )
    goto LABEL_40;
  updated = CJetContext::SetBasicColumn((CJetContext *)v13, 4u, &v36, 4u);
  if ( updated < 0 )
    goto LABEL_40;
  updated = CJetContext::SetBasicColumn((CJetContext *)v13, 5u, &v37, 4u);
  if ( updated < 0
    || (updated = CJetContext::SetBasicColumn((CJetContext *)v13, 0xBu, &v39, 4u), updated < 0)
    || (updated = CJetContext::SetBasicColumn((CJetContext *)v13, 0xCu, &v40, 8u), updated < 0)
    || (updated = CJetContext::SetStringColumn((CJetContext *)v13, 0xDu, v34), updated < 0)
    || (updated = CJetContext::SetBasicColumn((CJetContext *)v13, 6u, &v41, 8u), updated < 0)
    || (updated = CJetContext::SetBasicColumn((CJetContext *)v13, 7u, &v42, 8u), updated < 0)
    || (updated = CJetContext::SetBasicColumn((CJetContext *)v13, 8u, &v43, 8u), updated < 0)
    || (updated = CJetContext::SetBinaryColumn((CJetContext *)v13, 0xEu, 0, 0), updated < 0) )
  {
LABEL_40:
    v15 = 1;
  }
  else
  {
    v27 = JetUpdate(v13[2], v13[4], 0, 0, 0);
    updated = HRESULTFromJET_ERR(v27, 1);
    if ( updated >= 0 )
    {
      v29 = 0;
      CBloomFilter::AddMember(*((CBloomFilter **)this[19] + 5), a3);
      v28 = JetCommitTransaction(v13[2], 1u);
      updated = HRESULTFromJET_ERR(v28, 1);
      if ( updated >= 0 )
      {
        v15 = 0;
        updated = CFileListMap::RemoveEntry(this[5], v38);
        if ( updated >= 0 )
        {
          if ( a10 )
            this[14] = (CFileListMap *)((char *)this[14] + v40);
          if ( *((_DWORD *)this + 34) == 1 )
            updated = CAppCache::UpdateAppCache(this, 1);
        }
        goto LABEL_18;
      }
    }
    v15 = 1;
  }
  v16 = 0;
LABEL_19:
  AutoSrw::UnlockExclusive((AutoSrw *)&v31);
  if ( v29 )
    JetPrepareUpdate(v13[2], v13[4], 3u);
  if ( v15 )
    JetRollback(v13[2], 0);
  if ( v13 )
    CJetContextList::ReleaseContext(*((CJetContextList **)this[19] + 2), &v30);
  if ( v16 )
    WxDeleteFile(lpFileName);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 72, WPP_c3d0725a2afd3bb4de7e7a6d1e0eea73_Traceguids, (unsigned int)updated);
  if ( v38 )
  {
    CFileListEntry::Release(v38);
    v38 = 0;
  }
  if ( (_DWORD)v32 )
    AutoSrw::UnlockShared((AutoSrw *)&v31);
  if ( HIDWORD(v32) )
    AutoSrw::UnlockExclusive((AutoSrw *)&v31);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1801bead4  push    rbp
0x1801bead6  push    rbx
0x1801bead7  push    rsi
0x1801bead8  push    rdi
0x1801bead9  push    r12
0x1801beadb  push    r13
0x1801beadd  push    r14
0x1801beadf  push    r15
0x1801beae1  lea     rbp, [rsp-28h]
0x1801beae6  sub     rsp, 128h
0x1801beaed  mov     rax, cs:__security_cookie
0x1801beaf4  xor     rax, rsp
0x1801beaf7  mov     [rbp+60h+var_48], rax
0x1801beafb  mov     rax, qword ptr [rbp+60h+arg_20.dwLowDateTime]
0x1801beb02  xor     r10d, r10d
0x1801beb05  mov     r15, [rbp+60h+arg_38]
0x1801beb0c  mov     rsi, rcx
0x1801beb0f  mov     rcx, qword ptr [rbp+60h+arg_30.dwLowDateTime]
0x1801beb16  mov     rbx, r9
0x1801beb19  mov     [rbp+60h+var_98], edx
0x1801beb1c  mov     r9d, edx
0x1801beb1f  xorps   xmm0, xmm0
0x1801beb22  mov     [rbp+60h+var_88], rax
0x1801beb26  lea     rdx, [rsi+80h]
0x1801beb2d  mov     [rbp+60h+var_78], rcx
0x1801beb31  mov     r14, r8
0x1801beb34  mov     [rbp+60h+var_D0], rdx
0x1801beb38  mov     r8, qword ptr [rbp+60h+arg_28.dwLowDateTime]
0x1801beb3f  xor     edx, edx
0x1801beb41  mov     [rbp+60h+var_80], r8
0x1801beb45  mov     edi, r10d
0x1801beb48  mov     [rbp+60h+var_50], edx
0x1801beb4b  mov     [rbp+60h+lpFileName], rbx
0x1801beb4f  mov     [rsp+160h+var_E4], r10d
0x1801beb54  mov     [rbp+60h+var_C8], r10
0x1801beb58  mov     [rsp+160h+var_F0], r10d
0x1801beb5d  mov     [rbp+60h+var_E0], r10d
0x1801beb61  mov     [rbp+60h+var_D8], r10
0x1801beb65  mov     [rbp+60h+var_B0], r10d
0x1801beb69  mov     [rbp+60h+var_A0], r10
0x1801beb6d  mov     [rbp+60h+var_AC], r10d
0x1801beb71  mov     [rbp+60h+var_A8], r10d
0x1801beb75  movups  [rbp+60h+FileInformation], xmm0
0x1801beb79  mov     [rbp+60h+var_90], r10
0x1801beb7d  movups  [rbp+60h+var_60], xmm0
0x1801beb81  mov     [rbp+60h+var_B8], r10
0x1801beb85  mov     [rsp+160h+var_EC], r10d
0x1801beb8a  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801beb91  mov     r13d, [rbp+60h+arg_48]
0x1801beb98  mov     r12d, [rbp+60h+arg_40]
0x1801beb9f  jz      short loc_1801BEBD6
0x1801beba1  mov     [rsp+160h+var_100], r13d
0x1801beba6  mov     [rsp+160h+var_108], r12d
0x1801bebab  mov     [rsp+160h+var_110], r15
0x1801bebb0  mov     [rsp+160h+var_118], rcx
0x1801bebb5  mov     [rsp+160h+var_120], r8
0x1801bebba  mov     [rsp+160h+var_128], rax
0x1801bebbf  mov     [rsp+160h+var_130], rbx
0x1801bebc4  mov     [rsp+160h+var_138], r14
0x1801bebc9  mov     dword ptr [rsp+160h+pcbActual], r9d
0x1801bebce  mov     r9, rsi
0x1801bebd1  call    WPP_SF_qdSSiiiqdl
0x1801bebd6  lea     rcx, [rbp+60h+var_D0]; this
0x1801bebda  call    ?LockExclusive@AutoSrw@@QEAAXXZ; AutoSrw::LockExclusive(void)
0x1801bebdf  lea     r8, [rbp+60h+var_B8]; unsigned __int16 **
0x1801bebe3  mov     rdx, rbx; unsigned __int16 *
0x1801bebe6  mov     rcx, rsi; this
0x1801bebe9  call    ?VerifyDirectory@CAppCache@@AEAAJPEBGPEAPEBG@Z; CAppCache::VerifyDirectory(ushort const *,ushort const * *)
0x1801bebee  mov     ebx, eax
0x1801bebf0  test    eax, eax
0x1801bebf2  jns     short loc_1801BEC07
0x1801bebf4  mov     [rsp+160h+var_E4], 8FDh
0x1801bebfc  mov     r14d, edi
0x1801bebff  mov     r15d, edi
0x1801bec02  jmp     loc_1801BECE1
0x1801bec07  cmp     dword ptr [rsi+88h], 2
0x1801bec0e  jnz     short loc_1801BEC17
0x1801bec10  mov     ebx, 8000000Ch
0x1801bec15  jmp     short loc_1801BEBFC
0x1801bec17  mov     rcx, [rsi+28h]; this
0x1801bec1b  lea     r8, [rbp+60h+var_A0]; struct CFileListEntry **
0x1801bec1f  mov     rdx, r14; unsigned __int16 *
0x1801bec22  call    ?FindEntry@CFileListMap@@QEAAJPEBGPEAPEAVCFileListEntry@@@Z; CFileListMap::FindEntry(ushort const *,CFileListEntry * *)
0x1801bec27  mov     ebx, eax
0x1801bec29  test    eax, eax
0x1801bec2b  jns     short loc_1801BEC37
0x1801bec2d  mov     [rsp+160h+var_E4], 909h
0x1801bec35  jmp     short loc_1801BEBFC
0x1801bec37  cmp     eax, 1
0x1801bec3a  jnz     short loc_1801BEC49
0x1801bec3c  xor     ebx, ebx
0x1801bec3e  mov     r15d, eax
0x1801bec41  mov     r14d, ebx
0x1801bec44  jmp     loc_1801BECE1
0x1801bec49  mov     rcx, [rbp+60h+lpFileName]; lpFileName
0x1801bec4d  lea     r8, [rbp+60h+FileInformation]; lpFileInformation
0x1801bec51  xor     edx, edx; fInfoLevelId
0x1801bec53  call    cs:__imp_GetFileAttributesExW
0x1801bec59  test    eax, eax
0x1801bec5b  jnz     short loc_1801BEC88
0x1801bec5d  call    WxGetLastError
0x1801bec62  mov     ebx, eax
0x1801bec64  test    eax, eax
0x1801bec66  jle     short loc_1801BEC71
0x1801bec68  movzx   ebx, ax
0x1801bec6b  or      ebx, 80070000h
0x1801bec71  test    ebx, ebx
0x1801bec73  mov     [rsp+160h+var_E4], 91Dh
0x1801bec7b  mov     eax, 8000FFFFh
0x1801bec80  cmovns  ebx, eax
0x1801bec83  jmp     loc_1801BEBFC
0x1801bec88  mov     eax, [rbp+60h+var_50]
0x1801bec8b  lea     rdx, [rbp+60h+var_D8]; struct CJetContext **
0x1801bec8f  mov     ecx, dword ptr [rbp+60h+var_60+0Ch]
0x1801bec92  xor     r8d, r8d; int *
0x1801bec95  shl     rcx, 20h
0x1801bec99  or      rcx, rax
0x1801bec9c  mov     [rbp+60h+var_90], rcx
0x1801beca0  mov     rcx, [rbp+60h+var_A0]
0x1801beca4  mov     eax, [rcx+10h]
0x1801beca7  mov     [rbp+60h+var_AC], eax
0x1801becaa  mov     eax, [rcx+10h]
0x1801becad  mov     rcx, [rsi+98h]
0x1801becb4  and     eax, 1
0x1801becb7  mov     [rbp+60h+var_A8], eax
0x1801becba  mov     rcx, [rcx+10h]; this
0x1801becbe  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1801becc3  mov     rdi, [rbp+60h+var_D8]
0x1801becc7  mov     ebx, eax
0x1801becc9  test    eax, eax
0x1801beccb  jns     loc_1801BEDB3
0x1801becd1  mov     [rsp+160h+var_E4], 924h
0x1801becd9  mov     r14d, [rsp+160h+var_F0]
0x1801becde  mov     r15d, r14d
0x1801bece1  lea     rcx, [rbp+60h+var_D0]; this
0x1801bece5  call    ?UnlockExclusive@AutoSrw@@QEAAXXZ; AutoSrw::UnlockExclusive(void)
0x1801becea  cmp     [rbp+60h+var_E0], 0
0x1801becee  jz      short loc_1801BED04
0x1801becf0  mov     rdx, [rdi+20h]; tableid
0x1801becf4  mov     r8d, 3; prep
0x1801becfa  mov     rcx, [rdi+10h]; sesid
0x1801becfe  call    cs:__imp_JetPrepareUpdate
0x1801bed04  test    r14d, r14d
0x1801bed07  jz      short loc_1801BED15
0x1801bed09  mov     rcx, [rdi+10h]; sesid
0x1801bed0d  xor     edx, edx; grbit
0x1801bed0f  call    cs:__imp_JetRollback
0x1801bed15  xor     r14d, r14d
0x1801bed18  test    rdi, rdi
0x1801bed1b  jz      short loc_1801BED31
0x1801bed1d  mov     rcx, [rsi+98h]
0x1801bed24  lea     rdx, [rbp+60h+var_D8]; struct CJetContext **
0x1801bed28  mov     rcx, [rcx+10h]; this
0x1801bed2c  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1801bed31  test    r15d, r15d
0x1801bed34  jz      short loc_1801BED3F
0x1801bed36  mov     rcx, [rbp+60h+lpFileName]; lpPathName
0x1801bed3a  call    ?WxDeleteFile@@YAJPEBG@Z; WxDeleteFile(ushort const *)
0x1801bed3f  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801bed46  jz      short loc_1801BED61
0x1801bed48  mov     edx, 48h ; 'H'
0x1801bed4d  lea     r8, WPP_c3d0725a2afd3bb4de7e7a6d1e0eea73_Traceguids
0x1801bed54  mov     ecx, 40Ch
0x1801bed59  mov     r9d, ebx
0x1801bed5c  call    WPP_SF_d
0x1801bed61  mov     rcx, [rbp+60h+var_A0]; this
0x1801bed65  test    rcx, rcx
0x1801bed68  jz      short loc_1801BED73
0x1801bed6a  call    ?Release@CFileListEntry@@QEAAKXZ; CFileListEntry::Release(void)
0x1801bed6f  mov     [rbp+60h+var_A0], r14
0x1801bed73  cmp     dword ptr [rbp+60h+var_C8], r14d
0x1801bed77  jz      short loc_1801BED82
0x1801bed79  lea     rcx, [rbp+60h+var_D0]; this
0x1801bed7d  call    ?UnlockShared@AutoSrw@@QEAAXXZ; AutoSrw::UnlockShared(void)
0x1801bed82  cmp     dword ptr [rbp+60h+var_C8+4], r14d
0x1801bed86  jz      short loc_1801BED91
0x1801bed88  lea     rcx, [rbp+60h+var_D0]; this
0x1801bed8c  call    ?UnlockExclusive@AutoSrw@@QEAAXXZ; AutoSrw::UnlockExclusive(void)
0x1801bed91  mov     eax, ebx
0x1801bed93  mov     rcx, [rbp+60h+var_48]
0x1801bed97  xor     rcx, rsp; StackCookie
0x1801bed9a  call    __security_check_cookie
0x1801bed9f  add     rsp, 128h
0x1801beda6  pop     r15
0x1801beda8  pop     r14
0x1801bedaa  pop     r13
0x1801bedac  pop     r12
0x1801bedae  pop     rdi
0x1801bedaf  pop     rsi
0x1801bedb0  pop     rbx
0x1801bedb1  pop     rbp
0x1801bedb2  retn
0x1801bedb3  lea     r8, aEntryidindex; "EntryIdIndex"
0x1801bedba  xor     edx, edx; unsigned int
0x1801bedbc  mov     rcx, rdi; this
0x1801bedbf  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1801bedc4  mov     ebx, eax
0x1801bedc6  test    eax, eax
0x1801bedc8  jns     short loc_1801BEDD7
0x1801bedca  mov     [rsp+160h+var_E4], 927h
0x1801bedd2  jmp     loc_1801BECD9
0x1801bedd7  mov     rcx, [rdi+10h]; sesid
0x1801beddb  call    cs:__imp_JetBeginTransaction
0x1801bede1  mov     ecx, eax; int
0x1801bede3  mov     edx, 1; int
0x1801bede8  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801beded  mov     ebx, eax
0x1801bedef  test    eax, eax
0x1801bedf1  js      loc_1801BECD9
0x1801bedf7  mov     rdx, [rdi+20h]; tableid
0x1801bedfb  mov     ebx, 1
0x1801bee00  mov     rcx, [rdi+10h]; sesid
0x1801bee04  xor     r8d, r8d; prep
0x1801bee07  mov     [rsp+160h+var_F0], ebx
0x1801bee0b  call    cs:__imp_JetPrepareUpdate
0x1801bee11  mov     ecx, eax; int
0x1801bee13  mov     edx, ebx; int
0x1801bee15  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801bee1a  mov     ebx, eax
0x1801bee1c  test    eax, eax
0x1801bee1e  js      short loc_1801BEE56
0x1801bee20  mov     ebx, 1
0x1801bee25  or      edx, 0FFFFFFFFh
0x1801bee28  mov     rcx, r14
0x1801bee2b  mov     [rbp+60h+var_E0], ebx
0x1801bee2e  call    WxComputePrefixHash
0x1801bee33  lea     r8, [rsi+8]; void *
0x1801bee37  mov     [rbp+60h+var_B0], eax
0x1801bee3a  lea     r9d, [rbx+7]; unsigned int
0x1801bee3e  mov     rcx, rdi; this
0x1801bee41  mov     edx, ebx; unsigned int
0x1801bee43  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801bee48  mov     ebx, eax
0x1801bee4a  test    eax, eax
0x1801bee4c  jns     short loc_1801BEE65
0x1801bee4e  mov     [rsp+160h+var_E4], 93Ah
0x1801bee56  mov     r14d, [rsp+160h+var_F0]
0x1801bee5b  mov     r15d, [rsp+160h+var_EC]
0x1801bee60  jmp     loc_1801BECE1
0x1801bee65  mov     r9d, 4; unsigned int
0x1801bee6b  lea     r8, [rbp+60h+var_B0]; void *
0x1801bee6f  mov     rcx, rdi; this
0x1801bee72  lea     edx, [r9-2]; unsigned int
0x1801bee76  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801bee7b  mov     ebx, eax
0x1801bee7d  test    eax, eax
0x1801bee7f  jns     short loc_1801BEE8B
0x1801bee81  mov     [rsp+160h+var_E4], 93Eh
0x1801bee89  jmp     short loc_1801BEE56
0x1801bee8b  mov     r8, r14; unsigned __int16 *
0x1801bee8e  mov     edx, 3; unsigned int
0x1801bee93  mov     rcx, rdi; this
0x1801bee96  call    ?SetStringColumn@CJetContext@@QEAAJKPEBG@Z; CJetContext::SetStringColumn(ulong,ushort const *)
0x1801bee9b  mov     ebx, eax
0x1801bee9d  test    eax, eax
0x1801bee9f  jns     short loc_1801BEEAB
0x1801beea1  mov     [rsp+160h+var_E4], 941h
0x1801beea9  jmp     short loc_1801BEE56
0x1801beeab  mov     r9d, r12d; unsigned int
0x1801beeae  mov     r8, r15; unsigned __int8 *
0x1801beeb1  mov     edx, 0Ah; unsigned int
0x1801beeb6  mov     rcx, rdi; this
0x1801beeb9  call    ?SetBinaryColumn@CJetContext@@QEAAJKPEBEK@Z; CJetContext::SetBinaryColumn(ulong,uchar const *,ulong)
0x1801beebe  mov     ebx, eax
0x1801beec0  test    eax, eax
0x1801beec2  jns     short loc_1801BEECE
0x1801beec4  mov     [rsp+160h+var_E4], 945h
0x1801beecc  jmp     short loc_1801BEE56
0x1801beece  mov     r15d, 4
0x1801beed4  lea     r8, [rbp+60h+var_AC]; void *
0x1801beed8  mov     r9d, r15d; unsigned int
0x1801beedb  mov     edx, r15d; unsigned int
0x1801beede  mov     rcx, rdi; this
0x1801beee1  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801beee6  mov     ebx, eax
0x1801beee8  test    eax, eax
0x1801beeea  jns     short loc_1801BEEF9
0x1801beeec  mov     [rsp+160h+var_E4], 949h
0x1801beef4  jmp     loc_1801BEE56
0x1801beef9  mov     r9d, r15d; unsigned int
0x1801beefc  lea     r8, [rbp+60h+var_A8]; void *
0x1801bef00  mov     edx, 5; unsigned int
0x1801bef05  mov     rcx, rdi; this
0x1801bef08  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801bef0d  mov     ebx, eax
0x1801bef0f  test    eax, eax
0x1801bef11  jns     short loc_1801BEF20
0x1801bef13  mov     [rsp+160h+var_E4], 94Dh
0x1801bef1b  jmp     loc_1801BEE56
0x1801bef20  mov     r9d, r15d; unsigned int
0x1801bef23  lea     r8, [rbp+60h+var_98]; void *
0x1801bef27  mov     edx, 0Bh; unsigned int
0x1801bef2c  mov     rcx, rdi; this
0x1801bef2f  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801bef34  mov     ebx, eax
0x1801bef36  test    eax, eax
0x1801bef38  jns     short loc_1801BEF47
0x1801bef3a  mov     [rsp+160h+var_E4], 951h
0x1801bef42  jmp     loc_1801BEE56
0x1801bef47  mov     r15d, 8
  ... truncated ...
```
