# CacheStorageTraceLogging::CS_CacheStorage_match::Stop(__MIDL_RPCCacheStorage_0003 const *)

- ea: `0x180025bd0`
- end: `0x180026277`
- name: `?Stop@CS_CacheStorage_match@CacheStorageTraceLogging@@QEAAXPEBU__MIDL_RPCCacheStorage_0003@@@Z`
- size: `1703`
- prototype: `void __fastcall(CacheStorageTraceLogging::CS_CacheStorage_match *__hidden this, const struct __MIDL_RPCCacheStorage_0003 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800256a0`

## callees

- `0x180025bd0`
- `0x180037e10`
- `0x180052c74`
- `0x18005df6c`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026173`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026173`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025c58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800260e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025c58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800260e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025c70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025c8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025ca5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026100`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026117`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026131`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025c70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025c8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025ca5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026100`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026117`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026131`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800260bf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180026243`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800260bf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180026243`

## pseudocode

```c
void __fastcall CacheStorageTraceLogging::CS_CacheStorage_match::Stop(
        CacheStorageTraceLogging::CS_CacheStorage_match *this,
        const struct __MIDL_RPCCacheStorage_0003 *a2)
{
  char *v2; // rsi
  int v4; // eax
  __int64 v5; // rdi
  RTL_SRWLOCK *v6; // rbx
  RTL_SRWLOCK *v7; // rbx
  RTL_SRWLOCK *v8; // rdx
  __int64 v9; // rcx
  const unsigned __int16 *v10; // rdx
  const WCHAR *v11; // r8
  const unsigned __int16 *v12; // r9
  const WCHAR *v13; // r10
  const unsigned __int16 *v14; // r11
  const unsigned __int16 *v15; // rbx
  const WCHAR *v16; // r15
  const unsigned __int16 *v17; // r12
  const unsigned __int16 *v18; // r13
  int v19; // eax
  __int64 v20; // rdi
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  bool v24; // zf
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rax
  int v37; // eax
  int v38; // ecx
  PSRWLOCK v39; // rcx
  RTL_SRWLOCK *v40; // rbx
  __int64 v41; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v43; // r8
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v45; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK v46; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK v47; // [rsp+48h] [rbp-B8h] BYREF
  int v48; // [rsp+50h] [rbp-B0h] BYREF
  int v49; // [rsp+54h] [rbp-ACh] BYREF
  int v50; // [rsp+58h] [rbp-A8h] BYREF
  int v51; // [rsp+5Ch] [rbp-A4h] BYREF
  int v52; // [rsp+60h] [rbp-A0h] BYREF
  int v53; // [rsp+64h] [rbp-9Ch] BYREF
  PSRWLOCK v54; // [rsp+68h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v56; // [rsp+80h] [rbp-80h] BYREF
  __int16 *v57; // [rsp+90h] [rbp-70h]
  int v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+9Ch] [rbp-64h]
  PSRWLOCK *v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  PSRWLOCK *v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  PSRWLOCK *p_SRWLock; // [rsp+C0h] [rbp-40h]
  __int64 v65; // [rsp+C8h] [rbp-38h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+D0h] [rbp-30h] BYREF
  __int16 *v67; // [rsp+E0h] [rbp-20h]
  int v68; // [rsp+E8h] [rbp-18h]
  int v69; // [rsp+ECh] [rbp-14h]
  PSRWLOCK *v70; // [rsp+F0h] [rbp-10h]
  __int64 v71; // [rsp+F8h] [rbp-8h]
  PSRWLOCK *v72; // [rsp+100h] [rbp+0h]
  __int64 v73; // [rsp+108h] [rbp+8h]
  PSRWLOCK *v74; // [rsp+110h] [rbp+10h]
  __int64 v75; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v76; // [rsp+120h] [rbp+20h]
  int v77; // [rsp+128h] [rbp+28h]
  int v78; // [rsp+12Ch] [rbp+2Ch]
  unsigned int *v79; // [rsp+130h] [rbp+30h]
  __int64 v80; // [rsp+138h] [rbp+38h]
  const unsigned __int16 *v81; // [rsp+140h] [rbp+40h]
  int v82; // [rsp+148h] [rbp+48h]
  int v83; // [rsp+14Ch] [rbp+4Ch]
  int *v84; // [rsp+150h] [rbp+50h]
  __int64 v85; // [rsp+158h] [rbp+58h]
  const WCHAR *v86; // [rsp+160h] [rbp+60h]
  int v87; // [rsp+168h] [rbp+68h]
  int v88; // [rsp+16Ch] [rbp+6Ch]
  int *v89; // [rsp+170h] [rbp+70h]
  __int64 v90; // [rsp+178h] [rbp+78h]
  const unsigned __int16 *v91; // [rsp+180h] [rbp+80h]
  int v92; // [rsp+188h] [rbp+88h]
  int v93; // [rsp+18Ch] [rbp+8Ch]
  int *v94; // [rsp+190h] [rbp+90h]
  __int64 v95; // [rsp+198h] [rbp+98h]
  const unsigned __int16 *v96; // [rsp+1A0h] [rbp+A0h]
  int v97; // [rsp+1A8h] [rbp+A8h]
  int v98; // [rsp+1ACh] [rbp+ACh]
  const WCHAR *v99; // [rsp+1B0h] [rbp+B0h]
  int v100; // [rsp+1B8h] [rbp+B8h]
  int v101; // [rsp+1BCh] [rbp+BCh]
  int *v102; // [rsp+1C0h] [rbp+C0h]
  __int64 v103; // [rsp+1C8h] [rbp+C8h]
  const unsigned __int16 *v104; // [rsp+1D0h] [rbp+D0h]
  int v105; // [rsp+1D8h] [rbp+D8h]
  int v106; // [rsp+1DCh] [rbp+DCh]
  const WCHAR *v107; // [rsp+1E0h] [rbp+E0h]
  int v108; // [rsp+1E8h] [rbp+E8h]
  int v109; // [rsp+1ECh] [rbp+ECh]
  int *v110; // [rsp+1F0h] [rbp+F0h]
  __int64 v111; // [rsp+1F8h] [rbp+F8h]
  int *v112; // [rsp+200h] [rbp+100h]
  __int64 v113; // [rsp+208h] [rbp+108h]
  const unsigned __int16 *v114; // [rsp+210h] [rbp+110h]
  int v115; // [rsp+218h] [rbp+118h]
  int v116; // [rsp+21Ch] [rbp+11Ch]

  v2 = (char *)this + 272;
  if ( a2 )
    CacheStorageTraceLogging::LogResponseInfo((const struct _GUID *)(*(_QWORD *)v2 + 8LL), a2);
  v4 = *(_DWORD *)(*(_QWORD *)v2 + 72LL);
  if ( v4 < 0 && (v5 = *(_QWORD *)v2 + 80LL, v4 == *(_DWORD *)(*(_QWORD *)v2 + 88LL)) )
  {
    v6 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
    if ( *(_QWORD *)v2 != -80 )
    {
      if ( v6 )
      {
        v7 = v6 + 33;
        AcquireSRWLockExclusive(v7);
        SRWLock = 0;
        **((_DWORD **)this + 34) = 2;
        if ( v7 )
          ReleaseSRWLockExclusive(v7);
      }
      else
      {
        v46 = 0;
        **((_DWORD **)this + 34) = 2;
      }
      v8 = (RTL_SRWLOCK *)*((_QWORD *)StorageServerProvider::Instance() + 1);
      SRWLock = v8;
      if ( LODWORD(v8->Ptr) > 4 && ((__int64)v8[2].Ptr & 2) != 0 && (PVOID)((__int64)v8[3].Ptr & 2) == v8[3].Ptr )
      {
        v9 = -1;
        v10 = *(const unsigned __int16 **)(v5 + 48);
        v11 = *(const WCHAR **)(v5 + 120);
        v12 = *(const unsigned __int16 **)(v5 + 112);
        v13 = *(const WCHAR **)(v5 + 96);
        v14 = *(const unsigned __int16 **)(v5 + 88);
        v15 = *(const unsigned __int16 **)(v5 + 72);
        v16 = *(const WCHAR **)(v5 + 24);
        v17 = *(const unsigned __int16 **)(v5 + 128);
        v18 = *(const unsigned __int16 **)(v5 + 56);
        v48 = *(_DWORD *)(v5 + 68);
        v49 = *(_DWORD *)(v5 + 16);
        v50 = *(_DWORD *)(v5 + 104);
        v51 = *(_DWORD *)(v5 + 80);
        v52 = *(_DWORD *)(v5 + 32);
        v53 = *(_DWORD *)v5;
        v45 = *(_DWORD *)(v5 + 64);
        v19 = *(_DWORD *)(v5 + 8);
        v20 = *(_QWORD *)v2;
        LODWORD(v46) = v19;
        v54 = (PSRWLOCK)0x1000000;
        v47 = 0;
        if ( v10 )
        {
          v21 = -1;
          do
            ++v21;
          while ( *((_BYTE *)v10 + v21) );
          v22 = v21 + 1;
        }
        else
        {
          v10 = &word_1800D8FA6;
          v22 = 1;
        }
        v115 = v22;
        v114 = v10;
        v112 = &v48;
        v110 = &v49;
        v116 = 0;
        v113 = 4;
        v111 = 4;
        if ( v11 )
        {
          v23 = -1;
          do
            v24 = v11[++v23] == 0;
          while ( !v24 );
          v25 = 2 * v23 + 2;
        }
        else
        {
          v11 = &word_1800D6108;
          v25 = 2;
        }
        v107 = v11;
        v108 = v25;
        v109 = 0;
        if ( v12 )
        {
          v26 = -1;
          do
            ++v26;
          while ( *((_BYTE *)v12 + v26) );
          v27 = v26 + 1;
        }
        else
        {
          v12 = &word_1800D8FA6;
          v27 = 1;
        }
        v105 = v27;
        v102 = &v50;
        v104 = v12;
        v106 = 0;
        v103 = 4;
        if ( v13 )
        {
          v28 = -1;
          do
            v24 = v13[++v28] == 0;
          while ( !v24 );
          v29 = 2 * v28 + 2;
        }
        else
        {
          v13 = &word_1800D6108;
          v29 = 2;
        }
        v99 = v13;
        v100 = v29;
        v101 = 0;
        if ( v14 )
        {
          v30 = -1;
          do
            ++v30;
          while ( *((_BYTE *)v14 + v30) );
          v31 = v30 + 1;
        }
        else
        {
          v14 = &word_1800D8FA6;
          v31 = 1;
        }
        v97 = v31;
        v94 = &v51;
        v96 = v14;
        v98 = 0;
        v95 = 4;
        if ( v15 )
        {
          v32 = -1;
          do
            ++v32;
          while ( *((_BYTE *)v15 + v32) );
          v33 = v32 + 1;
        }
        else
        {
          v15 = &word_1800D8FA6;
          v33 = 1;
        }
        v92 = v33;
        v89 = &v52;
        v91 = v15;
        v93 = 0;
        v90 = 4;
        if ( v16 )
        {
          v34 = -1;
          do
            v24 = v16[++v34] == 0;
          while ( !v24 );
          v35 = 2 * v34 + 2;
        }
        else
        {
          v16 = &word_1800D6108;
          v35 = 2;
        }
        v87 = v35;
        v84 = &v53;
        v86 = v16;
        v88 = 0;
        v85 = 4;
        if ( v17 )
        {
          v36 = -1;
          do
            ++v36;
          while ( *((_BYTE *)v17 + v36) );
          v37 = v36 + 1;
        }
        else
        {
          v17 = &word_1800D8FA6;
          v37 = 1;
        }
        v82 = v37;
        v81 = v17;
        v79 = &v45;
        v83 = 0;
        v80 = 4;
        if ( v18 )
        {
          do
            ++v9;
          while ( *((_BYTE *)v18 + v9) );
          v38 = v9 + 1;
        }
        else
        {
          v18 = &word_1800D8FA6;
          v38 = 1;
        }
        v77 = v38;
        v39 = SRWLock;
        v74 = &v46;
        v78 = 0;
        v72 = &v54;
        v76 = v18;
        v70 = &v47;
        *(_DWORD *)&EventDescriptor.Level = 516;
        UserData.Ptr = (ULONGLONG)SRWLock[1].Ptr;
        v75 = 4;
        v73 = 8;
        v71 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 2;
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        v67 = &word_1800E6E5E;
        UserData.Reserved = 2;
        v68 = 324;
        v69 = 1;
        LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer((REGHANDLE)v39[4].Ptr, &EventDescriptor, (LPCGUID)(v20 + 8), 0, 0x15u, &UserData);
      }
      goto LABEL_67;
    }
  }
  else
  {
    v6 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  }
  if ( v6 )
  {
    v40 = v6 + 33;
    AcquireSRWLockExclusive(v40);
    v47 = 0;
    **(_DWORD **)v2 = 2;
    if ( v40 )
      ReleaseSRWLockExclusive(v40);
  }
  else
  {
    v54 = 0;
    **(_DWORD **)v2 = 2;
  }
  v41 = *((_QWORD *)StorageServerProvider::Instance() + 1);
  if ( *(_DWORD *)v41 > 4u && (*(_QWORD *)(v41 + 16) & 2) != 0 && (*(_QWORD *)(v41 + 24) & 2LL) == *(_QWORD *)(v41 + 24) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v43 = *(_QWORD *)v2;
    LODWORD(SRWLock) = CurrentThreadId;
    v65 = 4;
    v63 = 4;
    LODWORD(v46) = *(_DWORD *)(v43 + 72);
    p_SRWLock = &SRWLock;
    v62 = &v46;
    v60 = &v47;
    *(_DWORD *)&EventDescriptor.Level = 516;
    v56.Ptr = *(_QWORD *)(v41 + 8);
    v47 = 0;
    v61 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    v56.Size = *(unsigned __int16 *)v56.Ptr;
    v57 = &word_1800E6FAE;
    v56.Reserved = 2;
    v58 = 74;
    v59 = 1;
    v45 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v41 + 32), &EventDescriptor, (LPCGUID)(v43 + 8), 0, 5u, &v56);
  }
LABEL_67:
  wil::ActivityBase<StorageServerProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180025bd0  push    rbp
0x180025bd2  push    rsi
0x180025bd3  push    rdi
0x180025bd4  push    r14
0x180025bd6  push    r15
0x180025bd8  lea     rbp, [rsp-140h]
0x180025be0  sub     rsp, 240h
0x180025be7  mov     rax, cs:__security_cookie
0x180025bee  xor     rax, rsp
0x180025bf1  mov     [rbp+160h+var_40], rax
0x180025bf8  xor     r15d, r15d
0x180025bfb  lea     rsi, [rcx+110h]
0x180025c02  mov     r14, rcx
0x180025c05  test    rdx, rdx
0x180025c08  jz      short loc_180025C16
0x180025c0a  mov     rcx, [rsi]
0x180025c0d  add     rcx, 8; struct _GUID *
0x180025c11  call    ?LogResponseInfo@CacheStorageTraceLogging@@SAXPEBU_GUID@@AEBU__MIDL_RPCCacheStorage_0003@@@Z; CacheStorageTraceLogging::LogResponseInfo(_GUID const *,__MIDL_RPCCacheStorage_0003 const &)
0x180025c16  mov     rdi, [rsi]
0x180025c19  mov     [rsp+260h+arg_10], rbx
0x180025c21  mov     eax, [rdi+48h]
0x180025c24  test    eax, eax
0x180025c26  jns     loc_1800260D2
0x180025c2c  add     rdi, 50h ; 'P'
0x180025c30  cmp     eax, [rdi+8]
0x180025c33  jnz     loc_1800260D2
0x180025c39  mov     rbx, [r14+118h]
0x180025c40  test    rdi, rdi
0x180025c43  jz      loc_1800260D9
0x180025c49  test    rbx, rbx
0x180025c4c  jz      short loc_180025C93
0x180025c4e  add     rbx, 108h
0x180025c55  mov     rcx, rbx; SRWLock
0x180025c58  call    cs:__imp_AcquireSRWLockExclusive
0x180025c5e  lea     rax, [rsp+260h+SRWLock]
0x180025c63  mov     [rax], r15
0x180025c66  mov     rcx, [rsp+260h+SRWLock]; SRWLock
0x180025c6b  test    rcx, rcx
0x180025c6e  jz      short loc_180025C76
0x180025c70  call    cs:__imp_ReleaseSRWLockExclusive
0x180025c76  mov     rax, [r14+110h]
0x180025c7d  mov     dword ptr [rax], 2
0x180025c83  test    rbx, rbx
0x180025c86  jz      short loc_180025CB8
0x180025c88  mov     rcx, rbx; SRWLock
0x180025c8b  call    cs:__imp_ReleaseSRWLockExclusive
0x180025c91  jmp     short loc_180025CB8
0x180025c93  lea     rax, [rsp+260h+var_220]
0x180025c98  mov     [rax], r15
0x180025c9b  mov     rcx, [rsp+260h+var_220]; SRWLock
0x180025ca0  test    rcx, rcx
0x180025ca3  jz      short loc_180025CAB
0x180025ca5  call    cs:__imp_ReleaseSRWLockExclusive
0x180025cab  mov     rax, [r14+110h]
0x180025cb2  mov     dword ptr [rax], 2
0x180025cb8  call    ?Instance@StorageServerProvider@@KAPEAV1@XZ; StorageServerProvider::Instance(void)
0x180025cbd  mov     rdx, [rax+8]
0x180025cc1  mov     [rsp+260h+SRWLock], rdx
0x180025cc6  mov     eax, [rdx]
0x180025cc8  cmp     eax, 4
0x180025ccb  jbe     loc_180026249
0x180025cd1  mov     rcx, [rdx+18h]
0x180025cd5  mov     rax, [rdx+10h]
0x180025cd9  test    al, 2
0x180025cdb  jz      loc_180026249
0x180025ce1  mov     rax, rcx
0x180025ce4  and     eax, 2
0x180025ce7  cmp     rax, rcx
0x180025cea  jnz     loc_180026249
0x180025cf0  mov     [rsp+260h+var_28], r12
0x180025cf8  mov     [rsp+260h+var_30], r13
0x180025d00  mov     eax, [rdi+44h]
0x180025d03  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180025d0a  mov     rdx, [rdi+30h]
0x180025d0e  mov     r8, [rdi+78h]
0x180025d12  mov     r9, [rdi+70h]
0x180025d16  mov     r10, [rdi+60h]
0x180025d1a  mov     r11, [rdi+58h]
0x180025d1e  mov     rbx, [rdi+48h]
0x180025d22  mov     r15, [rdi+18h]
0x180025d26  mov     r12, [rdi+80h]
0x180025d2d  mov     r13, [rdi+38h]
0x180025d31  mov     [rsp+260h+var_210], eax
0x180025d35  mov     eax, [rdi+10h]
0x180025d38  mov     [rsp+260h+var_20C], eax
0x180025d3c  mov     eax, [rdi+68h]
0x180025d3f  mov     [rsp+260h+var_208], eax
0x180025d43  mov     eax, [rdi+50h]
0x180025d46  mov     [rsp+260h+var_204], eax
0x180025d4a  mov     eax, [rdi+20h]
0x180025d4d  mov     [rsp+260h+var_200], eax
0x180025d51  mov     eax, [rdi]
0x180025d53  mov     [rsp+260h+var_1FC], eax
0x180025d57  mov     eax, [rdi+40h]
0x180025d5a  mov     [rsp+260h+var_228], eax
0x180025d5e  mov     eax, [rdi+8]
0x180025d61  mov     rdi, [rsi]
0x180025d64  mov     dword ptr [rsp+260h+var_220], eax
0x180025d68  mov     [rsp+260h+var_1F8], 1000000h
0x180025d71  mov     [rsp+260h+var_218], 0
0x180025d7a  test    rdx, rdx
0x180025d7d  jz      short loc_180025D8F
0x180025d7f  mov     rax, rcx
0x180025d82  inc     rax
0x180025d85  cmp     byte ptr [rdx+rax], 0
0x180025d89  jnz     short loc_180025D82
0x180025d8b  inc     eax
0x180025d8d  jmp     short loc_180025D9B
0x180025d8f  lea     rdx, word_1800D8FA6
0x180025d96  mov     eax, 1
0x180025d9b  mov     [rbp+160h+var_48], eax
0x180025da1  lea     rax, [rsp+260h+var_210]
0x180025da6  mov     [rbp+160h+var_50], rdx
0x180025dad  xor     edx, edx
0x180025daf  mov     [rbp+160h+var_60], rax
0x180025db6  lea     rax, [rsp+260h+var_20C]
0x180025dbb  mov     [rbp+160h+var_70], rax
0x180025dc2  mov     [rbp+160h+var_44], edx
0x180025dc8  mov     [rbp+160h+var_58], 4
0x180025dd3  mov     [rbp+160h+var_68], 4
0x180025dde  test    r8, r8
0x180025de1  jz      short loc_180025E05
0x180025de3  mov     rax, rcx
0x180025de6  nop     word ptr [rax+rax+00000000h]
0x180025df0  cmp     [r8+rax*2+2], dx
0x180025df6  lea     rax, [rax+1]
0x180025dfa  jnz     short loc_180025DF0
0x180025dfc  lea     eax, ds:2[rax*2]
0x180025e03  jmp     short loc_180025E11
0x180025e05  lea     r8, word_1800D6108
0x180025e0c  mov     eax, 2
0x180025e11  mov     [rbp+160h+var_80], r8
0x180025e18  mov     [rbp+160h+var_78], eax
0x180025e1e  mov     [rbp+160h+var_74], edx
0x180025e24  test    r9, r9
0x180025e27  jz      short loc_180025E3D
0x180025e29  mov     rax, rcx
0x180025e2c  nop     dword ptr [rax+00h]
0x180025e30  inc     rax
0x180025e33  cmp     [r9+rax], dl
0x180025e37  jnz     short loc_180025E30
0x180025e39  inc     eax
0x180025e3b  jmp     short loc_180025E49
0x180025e3d  lea     r9, word_1800D8FA6
0x180025e44  mov     eax, 1
0x180025e49  mov     [rbp+160h+var_88], eax
0x180025e4f  lea     rax, [rsp+260h+var_208]
0x180025e54  mov     [rbp+160h+var_A0], rax
0x180025e5b  mov     [rbp+160h+var_90], r9
0x180025e62  mov     [rbp+160h+var_84], edx
0x180025e68  mov     [rbp+160h+var_98], 4
0x180025e73  test    r10, r10
0x180025e76  jz      short loc_180025E95
0x180025e78  mov     rax, rcx
0x180025e7b  nop     dword ptr [rax+rax+00h]
0x180025e80  cmp     [r10+rax*2+2], dx
0x180025e86  lea     rax, [rax+1]
0x180025e8a  jnz     short loc_180025E80
0x180025e8c  lea     eax, ds:2[rax*2]
0x180025e93  jmp     short loc_180025EA1
0x180025e95  lea     r10, word_1800D6108
0x180025e9c  mov     eax, 2
0x180025ea1  mov     [rbp+160h+var_B0], r10
0x180025ea8  mov     [rbp+160h+var_A8], eax
0x180025eae  mov     [rbp+160h+var_A4], edx
0x180025eb4  test    r11, r11
0x180025eb7  jz      short loc_180025ECD
0x180025eb9  mov     rax, rcx
0x180025ebc  nop     dword ptr [rax+00h]
0x180025ec0  inc     rax
0x180025ec3  cmp     [r11+rax], dl
0x180025ec7  jnz     short loc_180025EC0
0x180025ec9  inc     eax
0x180025ecb  jmp     short loc_180025ED9
0x180025ecd  lea     r11, word_1800D8FA6
0x180025ed4  mov     eax, 1
0x180025ed9  mov     [rbp+160h+var_B8], eax
0x180025edf  lea     rax, [rsp+260h+var_204]
0x180025ee4  mov     [rbp+160h+var_D0], rax
0x180025eeb  mov     [rbp+160h+var_C0], r11
0x180025ef2  mov     [rbp+160h+var_B4], edx
0x180025ef8  mov     [rbp+160h+var_C8], 4
0x180025f03  test    rbx, rbx
0x180025f06  jz      short loc_180025F1C
0x180025f08  mov     rax, rcx
0x180025f0b  nop     dword ptr [rax+rax+00h]
0x180025f10  inc     rax
0x180025f13  cmp     [rbx+rax], dl
0x180025f16  jnz     short loc_180025F10
0x180025f18  inc     eax
0x180025f1a  jmp     short loc_180025F28
0x180025f1c  lea     rbx, word_1800D8FA6
0x180025f23  mov     eax, 1
0x180025f28  mov     [rbp+160h+var_D8], eax
0x180025f2e  lea     rax, [rsp+260h+var_200]
0x180025f33  mov     [rbp+160h+var_F0], rax
0x180025f37  mov     [rbp+160h+var_E0], rbx
0x180025f3e  mov     [rbp+160h+var_D4], edx
0x180025f44  mov     [rbp+160h+var_E8], 4
0x180025f4c  test    r15, r15
0x180025f4f  jz      short loc_180025F69
0x180025f51  mov     rax, rcx
0x180025f54  cmp     [r15+rax*2+2], dx
0x180025f5a  lea     rax, [rax+1]
0x180025f5e  jnz     short loc_180025F54
0x180025f60  lea     eax, ds:2[rax*2]
0x180025f67  jmp     short loc_180025F75
0x180025f69  lea     r15, word_1800D6108
0x180025f70  mov     eax, 2
0x180025f75  mov     [rbp+160h+var_F8], eax
0x180025f78  lea     rax, [rsp+260h+var_1FC]
0x180025f7d  mov     [rbp+160h+var_110], rax
0x180025f81  mov     [rbp+160h+var_100], r15
0x180025f85  mov     [rbp+160h+var_F4], edx
0x180025f88  mov     [rbp+160h+var_108], 4
0x180025f90  test    r12, r12
0x180025f93  jz      short loc_180025FAD
0x180025f95  mov     rax, rcx
0x180025f98  nop     dword ptr [rax+rax+00000000h]
0x180025fa0  inc     rax
0x180025fa3  cmp     [r12+rax], dl
0x180025fa7  jnz     short loc_180025FA0
0x180025fa9  inc     eax
0x180025fab  jmp     short loc_180025FB9
0x180025fad  lea     r12, word_1800D8FA6
0x180025fb4  mov     eax, 1
0x180025fb9  mov     [rbp+160h+var_118], eax
0x180025fbc  lea     rax, [rsp+260h+var_228]
0x180025fc1  mov     [rbp+160h+var_120], r12
0x180025fc5  mov     r12, [rsp+260h+var_28]
0x180025fcd  mov     [rbp+160h+var_130], rax
0x180025fd1  mov     [rbp+160h+var_114], edx
0x180025fd4  mov     [rbp+160h+var_128], 4
0x180025fdc  test    r13, r13
0x180025fdf  jz      short loc_180025FEE
0x180025fe1  inc     rcx
0x180025fe4  cmp     [rcx+r13], dl
0x180025fe8  jnz     short loc_180025FE1
0x180025fea  inc     ecx
0x180025fec  jmp     short loc_180025FFA
0x180025fee  lea     r13, word_1800D8FA6
0x180025ff5  mov     ecx, 1
0x180025ffa  mov     [rbp+160h+var_138], ecx
0x180025ffd  lea     rax, [rsp+260h+var_220]
0x180026002  mov     rcx, [rsp+260h+SRWLock]
0x180026007  lea     r8, [rdi+8]; ActivityId
0x18002600b  mov     [rbp+160h+var_150], rax
0x18002600f  xor     r9d, r9d; RelatedActivityId
0x180026012  mov     [rbp+160h+var_134], edx
0x180026015  lea     rax, [rsp+260h+var_1F8]
0x18002601a  mov     [rbp+160h+var_160], rax
0x18002601e  lea     rdx, _TraceLoggingMetadata
0x180026025  lea     rax, [rsp+260h+var_218]
0x18002602a  mov     [rbp+160h+var_140], r13
0x18002602e  mov     [rbp+160h+var_170], rax
0x180026032  movzx   eax, cs:word_1800E6E54
0x180026039  mov     dword ptr [rsp+260h+EventDescriptor.Level], eax
0x18002603d  mov     rax, [rcx+8]
0x180026041  mov     [rbp+160h+var_190.Ptr], rax
0x180026045  mov     [rbp+160h+var_148], 4
0x18002604d  mov     [rbp+160h+var_158], 8
0x180026055  mov     [rbp+160h+var_168], 8
0x18002605d  mov     dword ptr [rsp+260h+EventDescriptor.Id], 0B000000h
0x180026065  mov     [rsp+260h+EventDescriptor.Keyword], 2
0x18002606e  movzx   eax, word ptr [rax]
0x180026071  mov     [rbp+160h+var_190.Size], eax
0x180026074  lea     rax, word_1800E6E5E
0x18002607b  mov     [rbp+160h+var_180], rax
0x18002607f  lea     rax, _TraceLoggingMetadataEnd
0x180026086  sub     eax, edx
0x180026088  mov     dword ptr [rbp+160h+var_190.0Ch], 2
0x18002608f  mov     [rbp+160h+var_178], 144h
0x180026096  lea     rdx, [rsp+260h+EventDescriptor]; EventDescriptor
0x18002609b  mov     [rbp+160h+var_174], 1
0x1800260a2  mov     dword ptr [rsp+260h+SRWLock], eax
0x1800260a6  mov     eax, dword ptr [rsp+260h+SRWLock]
0x1800260aa  mov     rcx, [rcx+20h]; RegHandle
0x1800260ae  lea     rax, [rbp+160h+var_190]
0x1800260b2  mov     [rsp+260h+UserData], rax; UserData
0x1800260b7  mov     [rsp+260h+UserDataCount], 15h; UserDataCount
0x1800260bf  call    cs:__imp_EventWriteTransfer
0x1800260c5  mov     r13, [rsp+260h+var_30]
0x1800260cd  jmp     loc_180026249
0x1800260d2  mov     rbx, [r14+118h]
0x1800260d9  test    rbx, rbx
0x1800260dc  jz      short loc_18002611F
0x1800260de  add     rbx, 108h
0x1800260e5  mov     rcx, rbx; SRWLock
0x1800260e8  call    cs:__imp_AcquireSRWLockExclusive
0x1800260ee  lea     rax, [rsp+260h+var_218]
0x1800260f3  mov     [rax], r15
0x1800260f6  mov     rcx, [rsp+260h+var_218]; SRWLock
0x1800260fb  test    rcx, rcx
0x1800260fe  jz      short loc_180026106
0x180026100  call    cs:__imp_ReleaseSRWLockExclusive
0x180026106  mov     rax, [rsi]
0x180026109  mov     dword ptr [rax], 2
0x18002610f  test    rbx, rbx
0x180026112  jz      short loc_180026140
0x180026114  mov     rcx, rbx; SRWLock
  ... truncated ...
```
