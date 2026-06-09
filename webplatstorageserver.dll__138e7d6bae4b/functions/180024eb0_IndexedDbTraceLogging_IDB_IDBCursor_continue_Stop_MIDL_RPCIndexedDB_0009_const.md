# IndexedDbTraceLogging::IDB_IDBCursor_continue::Stop(__MIDL_RPCIndexedDB_0009 const *)

- ea: `0x180024eb0`
- end: `0x180025557`
- name: `?Stop@IDB_IDBCursor_continue@IndexedDbTraceLogging@@QEAAXPEBU__MIDL_RPCIndexedDB_0009@@@Z`
- size: `1703`
- prototype: `void __fastcall(IndexedDbTraceLogging::IDB_IDBCursor_continue *__hidden this, const struct __MIDL_RPCIndexedDB_0009 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800263f0`

## callees

- `0x180024eb0`
- `0x180037e10`
- `0x180052c74`
- `0x18005fa1c`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025453`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025453`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024f38`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800253c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024f38`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800253c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024f50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024f6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024f85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800253e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800253f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025411`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024f50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024f6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024f85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800253e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800253f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025411`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002539f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180025523`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002539f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180025523`

## pseudocode

```c
void __fastcall IndexedDbTraceLogging::IDB_IDBCursor_continue::Stop(
        IndexedDbTraceLogging::IDB_IDBCursor_continue *this,
        const struct __MIDL_RPCIndexedDB_0009 *a2)
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
  char *v67; // [rsp+E0h] [rbp-20h]
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
    IndexedDbTraceLogging::LogCursorPositionValues((LPCGUID)(*(_QWORD *)v2 + 8LL), a2);
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
      if ( LODWORD(v8->Ptr) > 4 && ((__int64)v8[2].Ptr & 8) != 0 && (PVOID)((__int64)v8[3].Ptr & 8) == v8[3].Ptr )
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
        EventDescriptor.Keyword = 8;
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        v67 = byte_1800F35C9;
        UserData.Reserved = 2;
        v68 = 325;
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
  if ( *(_DWORD *)v41 > 4u && (*(_QWORD *)(v41 + 16) & 8) != 0 && (*(_QWORD *)(v41 + 24) & 8LL) == *(_QWORD *)(v41 + 24) )
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
    EventDescriptor.Keyword = 8;
    v56.Size = *(unsigned __int16 *)v56.Ptr;
    v57 = word_1800F3572;
    v56.Reserved = 2;
    v58 = 75;
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
0x180024eb0  push    rbp
0x180024eb2  push    rsi
0x180024eb3  push    rdi
0x180024eb4  push    r14
0x180024eb6  push    r15
0x180024eb8  lea     rbp, [rsp-140h]
0x180024ec0  sub     rsp, 240h
0x180024ec7  mov     rax, cs:__security_cookie
0x180024ece  xor     rax, rsp
0x180024ed1  mov     [rbp+160h+var_40], rax
0x180024ed8  xor     r15d, r15d
0x180024edb  lea     rsi, [rcx+110h]
0x180024ee2  mov     r14, rcx
0x180024ee5  test    rdx, rdx
0x180024ee8  jz      short loc_180024EF6
0x180024eea  mov     rcx, [rsi]
0x180024eed  add     rcx, 8; ActivityId
0x180024ef1  call    ?LogCursorPositionValues@IndexedDbTraceLogging@@SAXPEBU_GUID@@AEBU__MIDL_RPCIndexedDB_0009@@@Z; IndexedDbTraceLogging::LogCursorPositionValues(_GUID const *,__MIDL_RPCIndexedDB_0009 const &)
0x180024ef6  mov     rdi, [rsi]
0x180024ef9  mov     [rsp+260h+arg_10], rbx
0x180024f01  mov     eax, [rdi+48h]
0x180024f04  test    eax, eax
0x180024f06  jns     loc_1800253B2
0x180024f0c  add     rdi, 50h ; 'P'
0x180024f10  cmp     eax, [rdi+8]
0x180024f13  jnz     loc_1800253B2
0x180024f19  mov     rbx, [r14+118h]
0x180024f20  test    rdi, rdi
0x180024f23  jz      loc_1800253B9
0x180024f29  test    rbx, rbx
0x180024f2c  jz      short loc_180024F73
0x180024f2e  add     rbx, 108h
0x180024f35  mov     rcx, rbx; SRWLock
0x180024f38  call    cs:__imp_AcquireSRWLockExclusive
0x180024f3e  lea     rax, [rsp+260h+SRWLock]
0x180024f43  mov     [rax], r15
0x180024f46  mov     rcx, [rsp+260h+SRWLock]; SRWLock
0x180024f4b  test    rcx, rcx
0x180024f4e  jz      short loc_180024F56
0x180024f50  call    cs:__imp_ReleaseSRWLockExclusive
0x180024f56  mov     rax, [r14+110h]
0x180024f5d  mov     dword ptr [rax], 2
0x180024f63  test    rbx, rbx
0x180024f66  jz      short loc_180024F98
0x180024f68  mov     rcx, rbx; SRWLock
0x180024f6b  call    cs:__imp_ReleaseSRWLockExclusive
0x180024f71  jmp     short loc_180024F98
0x180024f73  lea     rax, [rsp+260h+var_220]
0x180024f78  mov     [rax], r15
0x180024f7b  mov     rcx, [rsp+260h+var_220]; SRWLock
0x180024f80  test    rcx, rcx
0x180024f83  jz      short loc_180024F8B
0x180024f85  call    cs:__imp_ReleaseSRWLockExclusive
0x180024f8b  mov     rax, [r14+110h]
0x180024f92  mov     dword ptr [rax], 2
0x180024f98  call    ?Instance@StorageServerProvider@@KAPEAV1@XZ; StorageServerProvider::Instance(void)
0x180024f9d  mov     rdx, [rax+8]
0x180024fa1  mov     [rsp+260h+SRWLock], rdx
0x180024fa6  mov     eax, [rdx]
0x180024fa8  cmp     eax, 4
0x180024fab  jbe     loc_180025529
0x180024fb1  mov     rcx, [rdx+18h]
0x180024fb5  mov     rax, [rdx+10h]
0x180024fb9  test    al, 8
0x180024fbb  jz      loc_180025529
0x180024fc1  mov     rax, rcx
0x180024fc4  and     eax, 8
0x180024fc7  cmp     rax, rcx
0x180024fca  jnz     loc_180025529
0x180024fd0  mov     [rsp+260h+var_28], r12
0x180024fd8  mov     [rsp+260h+var_30], r13
0x180024fe0  mov     eax, [rdi+44h]
0x180024fe3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180024fea  mov     rdx, [rdi+30h]
0x180024fee  mov     r8, [rdi+78h]
0x180024ff2  mov     r9, [rdi+70h]
0x180024ff6  mov     r10, [rdi+60h]
0x180024ffa  mov     r11, [rdi+58h]
0x180024ffe  mov     rbx, [rdi+48h]
0x180025002  mov     r15, [rdi+18h]
0x180025006  mov     r12, [rdi+80h]
0x18002500d  mov     r13, [rdi+38h]
0x180025011  mov     [rsp+260h+var_210], eax
0x180025015  mov     eax, [rdi+10h]
0x180025018  mov     [rsp+260h+var_20C], eax
0x18002501c  mov     eax, [rdi+68h]
0x18002501f  mov     [rsp+260h+var_208], eax
0x180025023  mov     eax, [rdi+50h]
0x180025026  mov     [rsp+260h+var_204], eax
0x18002502a  mov     eax, [rdi+20h]
0x18002502d  mov     [rsp+260h+var_200], eax
0x180025031  mov     eax, [rdi]
0x180025033  mov     [rsp+260h+var_1FC], eax
0x180025037  mov     eax, [rdi+40h]
0x18002503a  mov     [rsp+260h+var_228], eax
0x18002503e  mov     eax, [rdi+8]
0x180025041  mov     rdi, [rsi]
0x180025044  mov     dword ptr [rsp+260h+var_220], eax
0x180025048  mov     [rsp+260h+var_1F8], 1000000h
0x180025051  mov     [rsp+260h+var_218], 0
0x18002505a  test    rdx, rdx
0x18002505d  jz      short loc_18002506F
0x18002505f  mov     rax, rcx
0x180025062  inc     rax
0x180025065  cmp     byte ptr [rdx+rax], 0
0x180025069  jnz     short loc_180025062
0x18002506b  inc     eax
0x18002506d  jmp     short loc_18002507B
0x18002506f  lea     rdx, word_1800D8FA6
0x180025076  mov     eax, 1
0x18002507b  mov     [rbp+160h+var_48], eax
0x180025081  lea     rax, [rsp+260h+var_210]
0x180025086  mov     [rbp+160h+var_50], rdx
0x18002508d  xor     edx, edx
0x18002508f  mov     [rbp+160h+var_60], rax
0x180025096  lea     rax, [rsp+260h+var_20C]
0x18002509b  mov     [rbp+160h+var_70], rax
0x1800250a2  mov     [rbp+160h+var_44], edx
0x1800250a8  mov     [rbp+160h+var_58], 4
0x1800250b3  mov     [rbp+160h+var_68], 4
0x1800250be  test    r8, r8
0x1800250c1  jz      short loc_1800250E5
0x1800250c3  mov     rax, rcx
0x1800250c6  nop     word ptr [rax+rax+00000000h]
0x1800250d0  cmp     [r8+rax*2+2], dx
0x1800250d6  lea     rax, [rax+1]
0x1800250da  jnz     short loc_1800250D0
0x1800250dc  lea     eax, ds:2[rax*2]
0x1800250e3  jmp     short loc_1800250F1
0x1800250e5  lea     r8, word_1800D6108
0x1800250ec  mov     eax, 2
0x1800250f1  mov     [rbp+160h+var_80], r8
0x1800250f8  mov     [rbp+160h+var_78], eax
0x1800250fe  mov     [rbp+160h+var_74], edx
0x180025104  test    r9, r9
0x180025107  jz      short loc_18002511D
0x180025109  mov     rax, rcx
0x18002510c  nop     dword ptr [rax+00h]
0x180025110  inc     rax
0x180025113  cmp     [r9+rax], dl
0x180025117  jnz     short loc_180025110
0x180025119  inc     eax
0x18002511b  jmp     short loc_180025129
0x18002511d  lea     r9, word_1800D8FA6
0x180025124  mov     eax, 1
0x180025129  mov     [rbp+160h+var_88], eax
0x18002512f  lea     rax, [rsp+260h+var_208]
0x180025134  mov     [rbp+160h+var_A0], rax
0x18002513b  mov     [rbp+160h+var_90], r9
0x180025142  mov     [rbp+160h+var_84], edx
0x180025148  mov     [rbp+160h+var_98], 4
0x180025153  test    r10, r10
0x180025156  jz      short loc_180025175
0x180025158  mov     rax, rcx
0x18002515b  nop     dword ptr [rax+rax+00h]
0x180025160  cmp     [r10+rax*2+2], dx
0x180025166  lea     rax, [rax+1]
0x18002516a  jnz     short loc_180025160
0x18002516c  lea     eax, ds:2[rax*2]
0x180025173  jmp     short loc_180025181
0x180025175  lea     r10, word_1800D6108
0x18002517c  mov     eax, 2
0x180025181  mov     [rbp+160h+var_B0], r10
0x180025188  mov     [rbp+160h+var_A8], eax
0x18002518e  mov     [rbp+160h+var_A4], edx
0x180025194  test    r11, r11
0x180025197  jz      short loc_1800251AD
0x180025199  mov     rax, rcx
0x18002519c  nop     dword ptr [rax+00h]
0x1800251a0  inc     rax
0x1800251a3  cmp     [r11+rax], dl
0x1800251a7  jnz     short loc_1800251A0
0x1800251a9  inc     eax
0x1800251ab  jmp     short loc_1800251B9
0x1800251ad  lea     r11, word_1800D8FA6
0x1800251b4  mov     eax, 1
0x1800251b9  mov     [rbp+160h+var_B8], eax
0x1800251bf  lea     rax, [rsp+260h+var_204]
0x1800251c4  mov     [rbp+160h+var_D0], rax
0x1800251cb  mov     [rbp+160h+var_C0], r11
0x1800251d2  mov     [rbp+160h+var_B4], edx
0x1800251d8  mov     [rbp+160h+var_C8], 4
0x1800251e3  test    rbx, rbx
0x1800251e6  jz      short loc_1800251FC
0x1800251e8  mov     rax, rcx
0x1800251eb  nop     dword ptr [rax+rax+00h]
0x1800251f0  inc     rax
0x1800251f3  cmp     [rbx+rax], dl
0x1800251f6  jnz     short loc_1800251F0
0x1800251f8  inc     eax
0x1800251fa  jmp     short loc_180025208
0x1800251fc  lea     rbx, word_1800D8FA6
0x180025203  mov     eax, 1
0x180025208  mov     [rbp+160h+var_D8], eax
0x18002520e  lea     rax, [rsp+260h+var_200]
0x180025213  mov     [rbp+160h+var_F0], rax
0x180025217  mov     [rbp+160h+var_E0], rbx
0x18002521e  mov     [rbp+160h+var_D4], edx
0x180025224  mov     [rbp+160h+var_E8], 4
0x18002522c  test    r15, r15
0x18002522f  jz      short loc_180025249
0x180025231  mov     rax, rcx
0x180025234  cmp     [r15+rax*2+2], dx
0x18002523a  lea     rax, [rax+1]
0x18002523e  jnz     short loc_180025234
0x180025240  lea     eax, ds:2[rax*2]
0x180025247  jmp     short loc_180025255
0x180025249  lea     r15, word_1800D6108
0x180025250  mov     eax, 2
0x180025255  mov     [rbp+160h+var_F8], eax
0x180025258  lea     rax, [rsp+260h+var_1FC]
0x18002525d  mov     [rbp+160h+var_110], rax
0x180025261  mov     [rbp+160h+var_100], r15
0x180025265  mov     [rbp+160h+var_F4], edx
0x180025268  mov     [rbp+160h+var_108], 4
0x180025270  test    r12, r12
0x180025273  jz      short loc_18002528D
0x180025275  mov     rax, rcx
0x180025278  nop     dword ptr [rax+rax+00000000h]
0x180025280  inc     rax
0x180025283  cmp     [r12+rax], dl
0x180025287  jnz     short loc_180025280
0x180025289  inc     eax
0x18002528b  jmp     short loc_180025299
0x18002528d  lea     r12, word_1800D8FA6
0x180025294  mov     eax, 1
0x180025299  mov     [rbp+160h+var_118], eax
0x18002529c  lea     rax, [rsp+260h+var_228]
0x1800252a1  mov     [rbp+160h+var_120], r12
0x1800252a5  mov     r12, [rsp+260h+var_28]
0x1800252ad  mov     [rbp+160h+var_130], rax
0x1800252b1  mov     [rbp+160h+var_114], edx
0x1800252b4  mov     [rbp+160h+var_128], 4
0x1800252bc  test    r13, r13
0x1800252bf  jz      short loc_1800252CE
0x1800252c1  inc     rcx
0x1800252c4  cmp     [rcx+r13], dl
0x1800252c8  jnz     short loc_1800252C1
0x1800252ca  inc     ecx
0x1800252cc  jmp     short loc_1800252DA
0x1800252ce  lea     r13, word_1800D8FA6
0x1800252d5  mov     ecx, 1
0x1800252da  mov     [rbp+160h+var_138], ecx
0x1800252dd  lea     rax, [rsp+260h+var_220]
0x1800252e2  mov     rcx, [rsp+260h+SRWLock]
0x1800252e7  lea     r8, [rdi+8]; ActivityId
0x1800252eb  mov     [rbp+160h+var_150], rax
0x1800252ef  xor     r9d, r9d; RelatedActivityId
0x1800252f2  mov     [rbp+160h+var_134], edx
0x1800252f5  lea     rax, [rsp+260h+var_1F8]
0x1800252fa  mov     [rbp+160h+var_160], rax
0x1800252fe  lea     rdx, _TraceLoggingMetadata
0x180025305  lea     rax, [rsp+260h+var_218]
0x18002530a  mov     [rbp+160h+var_140], r13
0x18002530e  mov     [rbp+160h+var_170], rax
0x180025312  movzx   eax, cs:word_1800F35BF
0x180025319  mov     dword ptr [rsp+260h+EventDescriptor.Level], eax
0x18002531d  mov     rax, [rcx+8]
0x180025321  mov     [rbp+160h+var_190.Ptr], rax
0x180025325  mov     [rbp+160h+var_148], 4
0x18002532d  mov     [rbp+160h+var_158], 8
0x180025335  mov     [rbp+160h+var_168], 8
0x18002533d  mov     dword ptr [rsp+260h+EventDescriptor.Id], 0B000000h
0x180025345  mov     [rsp+260h+EventDescriptor.Keyword], 8
0x18002534e  movzx   eax, word ptr [rax]
0x180025351  mov     [rbp+160h+var_190.Size], eax
0x180025354  lea     rax, byte_1800F35C9
0x18002535b  mov     [rbp+160h+var_180], rax
0x18002535f  lea     rax, _TraceLoggingMetadataEnd
0x180025366  sub     eax, edx
0x180025368  mov     dword ptr [rbp+160h+var_190.0Ch], 2
0x18002536f  mov     [rbp+160h+var_178], 145h
0x180025376  lea     rdx, [rsp+260h+EventDescriptor]; EventDescriptor
0x18002537b  mov     [rbp+160h+var_174], 1
0x180025382  mov     dword ptr [rsp+260h+SRWLock], eax
0x180025386  mov     eax, dword ptr [rsp+260h+SRWLock]
0x18002538a  mov     rcx, [rcx+20h]; RegHandle
0x18002538e  lea     rax, [rbp+160h+var_190]
0x180025392  mov     [rsp+260h+UserData], rax; UserData
0x180025397  mov     [rsp+260h+UserDataCount], 15h; UserDataCount
0x18002539f  call    cs:__imp_EventWriteTransfer
0x1800253a5  mov     r13, [rsp+260h+var_30]
0x1800253ad  jmp     loc_180025529
0x1800253b2  mov     rbx, [r14+118h]
0x1800253b9  test    rbx, rbx
0x1800253bc  jz      short loc_1800253FF
0x1800253be  add     rbx, 108h
0x1800253c5  mov     rcx, rbx; SRWLock
0x1800253c8  call    cs:__imp_AcquireSRWLockExclusive
0x1800253ce  lea     rax, [rsp+260h+var_218]
0x1800253d3  mov     [rax], r15
0x1800253d6  mov     rcx, [rsp+260h+var_218]; SRWLock
0x1800253db  test    rcx, rcx
0x1800253de  jz      short loc_1800253E6
0x1800253e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800253e6  mov     rax, [rsi]
0x1800253e9  mov     dword ptr [rax], 2
0x1800253ef  test    rbx, rbx
0x1800253f2  jz      short loc_180025420
0x1800253f4  mov     rcx, rbx; SRWLock
  ... truncated ...
```
