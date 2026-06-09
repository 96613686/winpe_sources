# CSatelliteSpeesExecutor::AfterSetupInfoIsReady(CSQLSatelliteConnection * &)

- ea: `0x10040af40`
- end: `0x10040b6fa`
- name: `?AfterSetupInfoIsReady@CSatelliteSpeesExecutor@@AEAAJAEAPEAVCSQLSatelliteConnection@@@Z`
- size: `1978`
- prototype: `__int64 __fastcall(CSatelliteSpeesExecutor *__hidden this, struct CSQLSatelliteConnection **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1004089b0`

## callees

- `0x100403270`
- `0x10040af40`
- `0x10040bbb0`
- `0x10040be80`
- `0x10040c0e0`
- `0x10040c7a0`
- `0x10040c9e0`
- `0x10040cc90`
- `0x10040ce80`
- `0x10040d0c0`
- `0x10040d370`
- `0x10040d490`
- `0x1004729f0`
- `0x100479bb0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10040b126`
- `KERNEL32!QueryPerformanceCounter` at `0x10040b17c`
- `KERNEL32!QueryPerformanceCounter` at `0x10040b407`
- `KERNEL32!QueryPerformanceCounter` at `0x10040b45b`
- `KERNEL32!QueryPerformanceCounter` at `0x10040b126`
- `KERNEL32!QueryPerformanceCounter` at `0x10040b17c`
- `KERNEL32!QueryPerformanceCounter` at `0x10040b407`
- `KERNEL32!QueryPerformanceCounter` at `0x10040b45b`
- `KERNEL32!VirtualProtect` at `0x10040b4e6`
- `KERNEL32!VirtualProtect` at `0x10040b4e6`
- `KERNEL32!VirtualFree` at `0x10040b642`
- `KERNEL32!VirtualFree` at `0x10040b642`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040b1d0`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040b596`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040b5da`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x10040b628`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040b113`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040b16b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040b3f7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040b44a`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10040b13e`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10040b41c`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x10040b003`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x10040b003`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x10040b2f6`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x10040b2f6`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10040b2c5`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10040b374`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10040b6bb`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10040b2c5`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10040b374`
- `sqldk!?Destroy@SOSHost@@AEAAXXZ` at `0x10040b6bb`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10040b6c9`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10040b6c9`
- `sqldk!SystemThread_TlsIndex` at `0x10040b0e5`
- `sqldk!SystemThread_TlsIndex` at `0x10040b218`
- `sqldk!SystemThread_TlsIndex` at `0x10040b3c9`
- `sqldk!SystemThread_TlsOffset` at `0x10040b0ee`
- `sqldk!SystemThread_TlsOffset` at `0x10040b221`
- `sqldk!SystemThread_TlsOffset` at `0x10040b3d2`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040b0c8`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040b28a`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040b33d`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040b3ac`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040b684`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040b1dc`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040b5a2`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040b5e6`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040b1dc`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040b5a2`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040b5e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CSatelliteSpeesExecutor::AfterSetupInfoIsReady(
        CSatelliteSpeesExecutor *this,
        struct CSQLSatelliteConnection **a2)
{
  __int64 v4; // rbp
  __int64 result; // rax
  unsigned int v6; // r13d
  __int64 **v7; // rsi
  unsigned int v8; // eax
  _QWORD *v9; // rbx
  __int64 *v10; // rsi
  LARGE_INTEGER v11; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v13; // r8
  LARGE_INTEGER v14; // rax
  LONGLONG v15; // rcx
  _QWORD *v16; // rcx
  __int64 v17; // rax
  volatile signed __int64 *v18; // rbx
  int v19; // r8d
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 v22; // rbx
  SOS_Node *v23; // rcx
  __int64 v24; // rbp
  __int64 *v25; // rsi
  __int64 v26; // rbx
  __int64 v27; // rdi
  __int64 v28; // rbp
  LARGE_INTEGER v29; // rbx
  signed __int64 v30; // r15
  __int64 v31; // r8
  __int64 v32; // rcx
  LARGE_INTEGER v33; // rax
  LONGLONG v34; // rcx
  __int64 *v35; // rcx
  unsigned __int64 v36; // rax
  SOS_ObjectStore *v37; // rcx
  unsigned int PoolIdForObject; // eax
  char v39; // r11
  __int64 v40; // r9
  __int64 v41; // r10
  _QWORD *v42; // r8
  __int64 v43; // rcx
  int v44; // r8d
  int v45; // r8d
  __int64 *v46; // rsi
  __int64 v47; // rbx
  LARGE_INTEGER v48; // [rsp+30h] [rbp-78h] BYREF
  LARGE_INTEGER v49; // [rsp+38h] [rbp-70h] BYREF
  LARGE_INTEGER v50; // [rsp+40h] [rbp-68h] BYREF
  _QWORD *v51; // [rsp+48h] [rbp-60h]
  __int64 v52; // [rsp+50h] [rbp-58h]
  __int64 *v53; // [rsp+58h] [rbp-50h]
  volatile signed __int64 *v54; // [rsp+60h] [rbp-48h]
  int v55; // [rsp+68h] [rbp-40h]
  DWORD flOldProtect; // [rsp+C0h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+C8h] [rbp+20h] BYREF

  v52 = -2;
  v4 = 0;
  result = CSQLSatelliteCommunication::Init(
             *((_QWORD *)this + 259) + 8LL,
             *(_QWORD *)(*((_QWORD *)this + 259) + 3264LL),
             *(unsigned __int16 *)(*((_QWORD *)this + 260) + 42LL),
             *(_QWORD *)(*((_QWORD *)this + 260) + 152LL),
             0,
             (char *)this + 3136);
  v6 = result;
  _mm_lfence();
  if ( (int)result >= 0 )
  {
    if ( !CSatelliteSessionContext::ConvertColumnSchema(*((CSatelliteSessionContext **)this + 260)) )
      return (unsigned int)-2147024882;
    _InterlockedIncrement((volatile signed __int32 *)*a2 + 8);
    v7 = (__int64 **)((char *)this + 2096);
    v51 = (_QWORD *)((char *)this + 2096);
    v8 = SOS_Node::EnqueueTask(DataCargoReadTask, this, 672, (char *)this + 2096, 0);
    if ( !v8 )
    {
      *a2 = 0;
      return v6;
    }
    v6 = HRESULT_FROM_SOS_RESULT_Uncommon(v8);
    v9 = *a2;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*a2 + 8, 0xFFFFFFFF) == 1 )
    {
      if ( v9[2] )
        TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(v9[3], v9);
      (*(void (__fastcall **)(_QWORD *))(*v9 + 24LL))(v9);
    }
    v10 = *v7;
    if ( !v10 )
      return v6;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 10, 0xFFFFFFFF) == 1 )
    {
      if ( v10[3] )
      {
        TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v10 + 2);
        *v51 = 0;
        return v6;
      }
      if ( *((_DWORD *)v10 + 46) == 2 )
      {
        v54 = (volatile signed __int64 *)(v10[20] + 4952);
        v55 = 0;
        v11.QuadPart = 0;
        UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)v54 || _InterlockedCompareExchange64(v54, UniqueThread_low, 0) )
        {
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            if ( v13 && *(_QWORD *)(v13 + 272) == v13 )
              v4 = *(_QWORD *)(v13 + 256);
            if ( v4 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&PerformanceCount);
                v11 = PerformanceCount;
              }
              else
              {
                v11.QuadPart = MEMORY[0x7FFE0008];
              }
            }
          }
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v54, UniqueThread_low);
          else
            Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v54, v4, UniqueThread_low);
          if ( v4 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v48);
              v14 = v48;
            }
            else
            {
              v14.QuadPart = MEMORY[0x7FFE0008];
            }
            v15 = v14.QuadPart - v11.QuadPart;
            if ( v14.QuadPart < (unsigned __int64)v11.QuadPart )
              v15 = 0;
            *(_QWORD *)(v4 + 3192) += v15;
          }
        }
        v55 = 1;
        v16 = (_QWORD *)v10[1];
        v17 = *v10;
        *(_QWORD *)(v17 + 8) = v16;
        *v16 = v17;
        v10[1] = 0;
        *v10 = 0;
        v18 = v54;
        if ( v54 )
        {
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v19 = rand();
            if ( v19 == 5 * (v19 / 5) )
              Spinlock<11,2,268435714>::UpdateStatSnapshot();
          }
          *v18 = 0;
          v54 = 0;
          v55 = 0;
        }
      }
      v20 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v20
        && *(_QWORD *)(v20 + 272) == v20
        && (v21 = *(_QWORD *)(v20 + 256)) != 0
        && *(__int64 **)(v21 + 528) == v10 )
      {
        *(v10 - 1) = (__int64)&ISOSHost_TaskImpl::`vftable';
        v53 = v10;
        v22 = v10[22];
        if ( v22 )
        {
          if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
          {
            _InterlockedDecrement((volatile signed __int32 *)(v22 + 112));
            v22 = v10[22];
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v22 + 24), 0xFFFFFFFF) == 1 )
          {
            if ( *(_QWORD *)(v22 + 8) )
              TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v22 + 16), v22);
            SOSHost::Destroy((SOSHost *)v22);
            *v51 = 0;
            return v6;
          }
        }
      }
      else
      {
        v23 = (SOS_Node *)v10[21];
        if ( v23 && *((_QWORD *)v23 + 30) && !SOS_Node::IsTaskStoreDisabled(v23) )
        {
          v24 = *(_QWORD *)(v10[21] + 240);
          v25 = v10 - 1;
          *v25 = (__int64)&ISOSHost_TaskImpl::`vftable';
          v53 = v25 + 1;
          v26 = v25[23];
          if ( v26 )
          {
            if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
            {
              _InterlockedDecrement((volatile signed __int32 *)(v26 + 112));
              v26 = v25[23];
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26 + 24), 0xFFFFFFFF) == 1 )
            {
              if ( *(_QWORD *)(v26 + 8) )
                TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v26 + 16), v26);
              SOSHost::Destroy((SOSHost *)v26);
            }
          }
          v27 = *(_QWORD *)(v24 + 2016);
          v28 = 0;
          v29.QuadPart = 0;
          v30 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *(_DWORD *)(v27 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v27 + 40), v30, 0) )
          {
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v31 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              if ( v31 && *(_QWORD *)(v31 + 272) == v31 )
                v28 = *(_QWORD *)(v31 + 256);
              if ( v28 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v49);
                  v29 = v49;
                }
                else
                {
                  v29.QuadPart = MEMORY[0x7FFE0008];
                }
              }
            }
            v32 = v27 + 40;
            if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
              Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v32, v30);
            else
              Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v32, v28, v30);
            if ( v28 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v50);
                v33 = v50;
              }
              else
              {
                v33.QuadPart = MEMORY[0x7FFE0008];
              }
              v34 = v33.QuadPart - v29.QuadPart;
              if ( v33.QuadPart < (unsigned __int64)v29.QuadPart )
                v34 = 0;
              *(_QWORD *)(v28 + 3192) += v34;
            }
          }
          if ( *(_QWORD *)(v27 + 8) >= *(_QWORD *)v27 )
          {
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v45 = rand();
              if ( v45 == 5 * (v45 / 5) )
                Spinlock<34,1,268435714>::UpdateStatSnapshot();
            }
            *(_QWORD *)(v27 + 40) = 0;
            (*(void (__fastcall **)(__int64 *))(v27 + 48))(v25);
            *v51 = 0;
          }
          else
          {
            if ( *(_BYTE *)(*(_QWORD *)(v27 + 32) + 5820LL) )
            {
              v35 = (__int64 *)(v27 + 16 * ((*(_DWORD *)(v27 + 1176) & 0x3F) + 9LL));
              *v25 = *v35;
              if ( !*v35 )
                v35[1] = (__int64)v25;
              *v35 = (__int64)v25;
              ++*(_QWORD *)(v27 + 1176);
              VirtualProtect(v25, 0x1000u, 1u, &flOldProtect);
            }
            else
            {
              *v25 = *(_QWORD *)(v27 + 128);
              if ( !*(_QWORD *)(v27 + 128) )
                *(_QWORD *)(v27 + 136) = v25;
              *(_QWORD *)(v27 + 128) = v25;
            }
            v36 = *(_QWORD *)(v27 + 1168) + 1LL;
            ++*(_QWORD *)(v27 + 8);
            v37 = *(SOS_ObjectStore **)(v27 + 32);
            if ( !*((_BYTE *)v37 + 5820) && v36 >= 0x20 )
            {
              PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v37, (struct SList *)v25);
              v39 = PoolIdForObject;
              v40 = v27 + 8LL * PoolIdForObject;
              v41 = *(_QWORD *)(v27 + 128);
              v42 = *(_QWORD **)(v27 + 136);
              if ( v42 != (_QWORD *)(v27 + 128) && v42 )
              {
                *v42 = *(_QWORD *)(v40 + 1184);
                *(_QWORD *)(v40 + 1184) = v41;
              }
              *(_QWORD *)(v27 + 128) = 0;
              *(_QWORD *)(v27 + 136) = v27 + 128;
              v36 = 0;
              v43 = *(_QWORD *)(v27 + 1696);
              if ( (v43 & (1LL << v39)) == 0 )
                *(_QWORD *)(v27 + 1696) = (1LL << v39) | v43;
            }
            *(_QWORD *)(v27 + 1168) = v36;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v44 = rand();
              if ( v44 == 5 * (v44 / 5) )
                Spinlock<34,1,268435714>::UpdateStatSnapshot();
            }
            *(_QWORD *)(v27 + 40) = 0;
            *v51 = 0;
          }
          return v6;
        }
        v46 = v10 - 1;
        if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
        {
          VirtualFree(v46, 0, 0x8000u);
          *v51 = 0;
          return v6;
        }
        if ( v46 )
        {
          *v46 = (__int64)&ISOSHost_TaskImpl::`vftable';
          v47 = v46[23];
          if ( v47 )
          {
            if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
            {
              _InterlockedDecrement((volatile signed __int32 *)(v47 + 112));
              v47 = v46[23];
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v47 + 24), 0xFFFFFFFF) == 1 )
            {
              if ( *(_QWORD *)(v47 + 8) )
                TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v47 + 16), v47);
              SOSHost::Destroy((SOSHost *)v47);
            }
          }
          operator delete(v46, 0x3E0u);
        }
      }
    }
    *v51 = 0;
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x10040af40  push    rbp
0x10040af42  push    rsi
0x10040af43  push    rdi
0x10040af44  push    r12
0x10040af46  push    r13
0x10040af48  push    r14
0x10040af4a  push    r15
0x10040af4c  sub     rsp, 70h
0x10040af50  mov     [rsp+0A8h+var_58], 0FFFFFFFFFFFFFFFEh
0x10040af59  mov     [rsp+0A8h+arg_8], rbx
0x10040af61  mov     rdi, rdx
0x10040af64  mov     rbx, rcx
0x10040af67  mov     rax, [rcx+820h]
0x10040af6e  mov     r9, [rax+98h]
0x10040af75  movzx   r8d, word ptr [rax+2Ah]
0x10040af7a  mov     rdx, [rcx+818h]
0x10040af81  lea     rax, [rcx+0C40h]
0x10040af88  lea     rcx, [rdx+8]
0x10040af8c  mov     [rsp+0A8h+var_80], rax
0x10040af91  xor     ebp, ebp
0x10040af93  mov     dword ptr [rsp+0A8h+var_88], ebp
0x10040af97  mov     rdx, [rdx+0CC0h]
0x10040af9e  call    ?Init@CSQLSatelliteCommunication@@QEAAJPEAVIMemObj@@GPEAU_SQLSatellite_ColumnSchema@@W4ESQLSatelliteDataOrientation@@AEBU_GUID@@@Z; CSQLSatelliteCommunication::Init(IMemObj *,ushort,_SQLSatellite_ColumnSchema *,ESQLSatelliteDataOrientation,_GUID const &)
0x10040afa3  mov     r13d, eax
0x10040afa6  lfence
0x10040afa9  test    eax, eax
0x10040afab  js      loc_10040B6E2
0x10040afb1  mov     rcx, [rbx+820h]; this
0x10040afb8  call    ?ConvertColumnSchema@CSatelliteSessionContext@@QEAA_NXZ; CSatelliteSessionContext::ConvertColumnSchema(void)
0x10040afbd  test    al, al
0x10040afbf  jz      loc_10040B6D9
0x10040afc5  mov     rax, [rdi]
0x10040afc8  lock inc dword ptr [rax+20h]
0x10040afcc  lea     rsi, [rbx+830h]
0x10040afd3  mov     [rsp+0A8h+var_60], rsi
0x10040afd8  mov     [rsp+0A8h+var_88], rbp
0x10040afdd  mov     r9, rsi
0x10040afe0  mov     r8d, 2A0h
0x10040afe6  mov     rdx, rbx
0x10040afe9  lea     rcx, ?DataCargoReadTask@@YAPEAXPEAX@Z; DataCargoReadTask(void *)
0x10040aff0  call    ?EnqueueTask@SOS_Node@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@PEAPEAX@Z; SOS_Node::EnqueueTask(void * (*)(void *),void *,ulong,SOS_Task * *,void * *)
0x10040aff5  test    eax, eax
0x10040aff7  jnz     short loc_10040B001
0x10040aff9  mov     [rdi], rbp
0x10040affc  jmp     loc_10040B6DF
0x10040b001  mov     ecx, eax
0x10040b003  call    cs:__imp_?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z; HRESULT_FROM_SOS_RESULT_Uncommon(SOS_RESULT)
0x10040b009  mov     r13d, eax
0x10040b00c  mov     rbx, [rdi]
0x10040b00f  mov     edi, 0FFFFFFFFh
0x10040b014  mov     eax, edi
0x10040b016  lock xadd [rbx+20h], eax
0x10040b01b  cmp     eax, 1
0x10040b01e  jnz     short loc_10040B03B
0x10040b020  cmp     [rbx+10h], rbp
0x10040b024  jz      short loc_10040B032
0x10040b026  mov     rdx, rbx
0x10040b029  mov     rcx, [rbx+18h]
0x10040b02d  call    ?RemoveElem@?$TList@VSqlSatelliteConnectionList@@VCSQLSatelliteConnection@@$07UTListSLock@@@@QEAAXPEAVCSQLSatelliteConnection@@@Z; TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(CSQLSatelliteConnection *)
0x10040b032  mov     rax, [rbx]
0x10040b035  mov     rcx, rbx
0x10040b038  call    qword ptr [rax+18h]
0x10040b03b  mov     rsi, [rsi]
0x10040b03e  test    rsi, rsi
0x10040b041  jz      loc_10040B6DF
0x10040b047  lea     rcx, [rsi+10h]
0x10040b04b  mov     eax, edi
0x10040b04d  lock xadd [rcx+18h], eax
0x10040b052  cmp     eax, 1
0x10040b055  jnz     loc_10040B6CF
0x10040b05b  cmp     [rcx+8], rbp
0x10040b05f  jz      short loc_10040B073
0x10040b061  call    ?RemoveAndDestroy@?$TListElem@V?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@@@IEAAXXZ; TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(void)
0x10040b066  mov     rax, [rsp+0A8h+var_60]
0x10040b06b  mov     [rax], rbp
0x10040b06e  jmp     loc_10040B6DF
0x10040b073  mov     eax, [rsi+0B8h]
0x10040b079  mov     r12d, 1
0x10040b07f  cmp     eax, 2
0x10040b082  jnz     loc_10040B20F
0x10040b088  mov     r14, [rsi+0A0h]
0x10040b08f  add     r14, 1358h
0x10040b096  mov     [rsp+0A8h+var_48], r14
0x10040b09b  mov     [rsp+0A8h+var_40], ebp
0x10040b09f  mov     rbx, rbp
0x10040b0a2  mov     eax, gs:48h
0x10040b0aa  mov     r15d, eax
0x10040b0ad  mov     eax, [r14]
0x10040b0b0  test    eax, eax
0x10040b0b2  jnz     short loc_10040B0C8
0x10040b0b4  xor     eax, eax
0x10040b0b6  lock cmpxchg [r14], r15
0x10040b0bb  mov     eax, ebp
0x10040b0bd  setz    al
0x10040b0c0  test    eax, eax
0x10040b0c2  jnz     loc_10040B1AC
0x10040b0c8  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040b0cf  mov     ecx, [rax]
0x10040b0d1  and     ecx, 84h
0x10040b0d7  cmp     cl, 84h
0x10040b0da  jnz     short loc_10040B13E
0x10040b0dc  mov     rdx, gs:58h
0x10040b0e5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040b0ec  mov     ecx, [rax]
0x10040b0ee  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040b0f5  mov     r8d, [rax]
0x10040b0f8  add     r8, [rdx+rcx*8]
0x10040b0fc  jz      short loc_10040B10E
0x10040b0fe  cmp     [r8+110h], r8
0x10040b105  jnz     short loc_10040B10E
0x10040b107  mov     rbp, [r8+100h]
0x10040b10e  test    rbp, rbp
0x10040b111  jz      short loc_10040B13E
0x10040b113  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040b11a  cmp     [rax], ebx
0x10040b11c  jz      short loc_10040B136
0x10040b11e  lea     rcx, [rsp+0A8h+PerformanceCount]; lpPerformanceCount
0x10040b126  call    cs:__imp_QueryPerformanceCounter
0x10040b12c  mov     rbx, qword ptr [rsp+0A8h+PerformanceCount]
0x10040b134  jmp     short loc_10040B13E
0x10040b136  mov     rbx, ds:7FFE0008h
0x10040b13e  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10040b145  mov     rcx, r14
0x10040b148  cmp     byte ptr [rax+0C7h], 0
0x10040b14f  jge     short loc_10040B15E
0x10040b151  mov     r8, r15
0x10040b154  mov     rdx, rbp
0x10040b157  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10040b15c  jmp     short loc_10040B166
0x10040b15e  mov     rdx, r15
0x10040b161  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10040b166  test    rbp, rbp
0x10040b169  jz      short loc_10040B1AA
0x10040b16b  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040b172  cmp     dword ptr [rax], 0
0x10040b175  jz      short loc_10040B189
0x10040b177  lea     rcx, [rsp+0A8h+var_78]; lpPerformanceCount
0x10040b17c  call    cs:__imp_QueryPerformanceCounter
0x10040b182  mov     rax, qword ptr [rsp+0A8h+var_78]
0x10040b187  jmp     short loc_10040B191
0x10040b189  mov     rax, ds:7FFE0008h
0x10040b191  mov     rcx, rax
0x10040b194  sub     rcx, rbx
0x10040b197  cmp     rax, rbx
0x10040b19a  mov     eax, 0
0x10040b19f  cmovb   rcx, rax
0x10040b1a3  add     [rbp+0C78h], rcx
0x10040b1aa  xor     ebp, ebp
0x10040b1ac  mov     [rsp+0A8h+var_40], r12d
0x10040b1b1  mov     rcx, [rsi+8]
0x10040b1b5  mov     rax, [rsi]
0x10040b1b8  mov     [rax+8], rcx
0x10040b1bc  mov     [rcx], rax
0x10040b1bf  mov     [rsi+8], rbp
0x10040b1c3  mov     [rsi], rbp
0x10040b1c6  mov     rbx, [rsp+0A8h+var_48]
0x10040b1cb  test    rbx, rbx
0x10040b1ce  jz      short loc_10040B20F
0x10040b1d0  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10040b1d7  cmp     byte ptr [rax], 0
0x10040b1da  jz      short loc_10040B203
0x10040b1dc  call    cs:__imp_rand
0x10040b1e2  mov     r8d, eax
0x10040b1e5  mov     eax, 66666667h
0x10040b1ea  imul    r8d
0x10040b1ed  sar     edx, 1
0x10040b1ef  mov     ecx, edx
0x10040b1f1  shr     ecx, 1Fh
0x10040b1f4  add     edx, ecx
0x10040b1f6  lea     ecx, [rdx+rdx*4]
0x10040b1f9  cmp     r8d, ecx
0x10040b1fc  jnz     short loc_10040B203
0x10040b1fe  call    ?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ; Spinlock<11,2,268435714>::UpdateStatSnapshot(void)
0x10040b203  mov     [rbx], rbp
0x10040b206  mov     [rsp+0A8h+var_48], rbp
0x10040b20b  mov     [rsp+0A8h+var_40], ebp
0x10040b20f  mov     rdx, gs:58h
0x10040b218  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040b21f  mov     ecx, [rax]
0x10040b221  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040b228  mov     r8d, [rax]
0x10040b22b  add     r8, [rdx+rcx*8]
0x10040b22f  jz      loc_10040B2D8
0x10040b235  cmp     [r8+110h], r8
0x10040b23c  jnz     loc_10040B2D8
0x10040b242  mov     rax, [r8+100h]
0x10040b249  test    rax, rax
0x10040b24c  jz      loc_10040B2D8
0x10040b252  cmp     [rax+210h], rsi
0x10040b259  jnz     short loc_10040B2D8
0x10040b25b  lea     rax, [rsi-8]
0x10040b25f  mov     [rsp+0A8h+arg_0], rax
0x10040b267  lea     rcx, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x10040b26e  mov     [rax], rcx
0x10040b271  lea     rcx, [rax+8]
0x10040b275  mov     [rsp+0A8h+var_50], rcx
0x10040b27a  mov     rbx, [rcx+0B0h]
0x10040b281  test    rbx, rbx
0x10040b284  jz      loc_10040B6CF
0x10040b28a  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040b291  test    byte ptr [rax], 8
0x10040b294  jz      short loc_10040B2A1
0x10040b296  lock dec dword ptr [rbx+70h]
0x10040b29a  mov     rbx, [rcx+0B0h]
0x10040b2a1  lock xadd [rbx+18h], edi
0x10040b2a6  cmp     edi, 1
0x10040b2a9  jnz     loc_10040B6CF
0x10040b2af  cmp     qword ptr [rbx+8], 0
0x10040b2b4  jz      short loc_10040B2C2
0x10040b2b6  mov     rdx, rbx
0x10040b2b9  mov     rcx, [rbx+10h]
0x10040b2bd  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x10040b2c2  mov     rcx, rbx
0x10040b2c5  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x10040b2cb  mov     rax, [rsp+0A8h+var_60]
0x10040b2d0  mov     [rax], rbp
0x10040b2d3  jmp     loc_10040B6DF
0x10040b2d8  mov     rcx, [rsi+0A8h]
0x10040b2df  test    rcx, rcx
0x10040b2e2  jz      loc_10040B624
0x10040b2e8  cmp     qword ptr [rcx+0F0h], 0
0x10040b2f0  jz      loc_10040B624
0x10040b2f6  call    cs:__imp_?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ; SOS_Node::IsTaskStoreDisabled(void)
0x10040b2fc  test    al, al
0x10040b2fe  jnz     loc_10040B624
0x10040b304  mov     rax, [rsi+0A8h]
0x10040b30b  mov     rbp, [rax+0F0h]
0x10040b312  add     rsi, 0FFFFFFFFFFFFFFF8h
0x10040b316  mov     [rsp+0A8h+arg_0], rsi
0x10040b31e  lea     rcx, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x10040b325  mov     [rsi], rcx
0x10040b328  lea     rcx, [rsi+8]
0x10040b32c  mov     [rsp+0A8h+var_50], rcx
0x10040b331  mov     rbx, [rcx+0B0h]
0x10040b338  test    rbx, rbx
0x10040b33b  jz      short loc_10040B37A
0x10040b33d  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040b344  test    byte ptr [rax], 8
0x10040b347  jz      short loc_10040B354
0x10040b349  lock dec dword ptr [rbx+70h]
0x10040b34d  mov     rbx, [rcx+0B0h]
0x10040b354  lock xadd [rbx+18h], edi
0x10040b359  cmp     edi, 1
0x10040b35c  jnz     short loc_10040B37A
0x10040b35e  cmp     qword ptr [rbx+8], 0
0x10040b363  jz      short loc_10040B371
0x10040b365  mov     rdx, rbx
0x10040b368  mov     rcx, [rbx+10h]
0x10040b36c  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x10040b371  mov     rcx, rbx
0x10040b374  call    cs:__imp_?Destroy@SOSHost@@AEAAXXZ; SOSHost::Destroy(void)
0x10040b37a  mov     rdi, [rbp+7E0h]
0x10040b381  xor     ebp, ebp
0x10040b383  mov     ebx, ebp
0x10040b385  mov     eax, gs:48h
0x10040b38d  mov     r15d, eax
0x10040b390  mov     eax, [rdi+28h]
0x10040b393  test    eax, eax
0x10040b395  jnz     short loc_10040B3AC
0x10040b397  xor     eax, eax
0x10040b399  lock cmpxchg [rdi+28h], r15
0x10040b39f  mov     eax, ebp
0x10040b3a1  setz    al
0x10040b3a4  test    eax, eax
0x10040b3a6  jnz     loc_10040B48B
0x10040b3ac  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040b3b3  mov     ecx, [rax]
0x10040b3b5  and     ecx, 84h
0x10040b3bb  cmp     cl, 84h
0x10040b3be  jnz     short loc_10040B41C
0x10040b3c0  mov     rdx, gs:58h
0x10040b3c9  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040b3d0  mov     ecx, [rax]
0x10040b3d2  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040b3d9  mov     r8d, [rax]
0x10040b3dc  add     r8, [rdx+rcx*8]
0x10040b3e0  jz      short loc_10040B3F2
0x10040b3e2  cmp     [r8+110h], r8
0x10040b3e9  jnz     short loc_10040B3F2
0x10040b3eb  mov     rbp, [r8+100h]
0x10040b3f2  test    rbp, rbp
0x10040b3f5  jz      short loc_10040B41C
0x10040b3f7  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040b3fe  cmp     [rax], ebx
0x10040b400  jz      short loc_10040B414
0x10040b402  lea     rcx, [rsp+0A8h+var_70]; lpPerformanceCount
0x10040b407  call    cs:__imp_QueryPerformanceCounter
0x10040b40d  mov     rbx, qword ptr [rsp+0A8h+var_70]
0x10040b412  jmp     short loc_10040B41C
0x10040b414  mov     rbx, ds:7FFE0008h
0x10040b41c  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10040b423  lea     rcx, [rdi+28h]
0x10040b427  cmp     byte ptr [rax+0C7h], 0
0x10040b42e  jge     short loc_10040B43D
0x10040b430  mov     r8, r15
0x10040b433  mov     rdx, rbp
0x10040b436  call    ?SpinToAcquireOptimistic@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<34,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10040b43b  jmp     short loc_10040B445
0x10040b43d  mov     rdx, r15
0x10040b440  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
  ... truncated ...
```
