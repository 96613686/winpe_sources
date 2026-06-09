# CryptoBase::ReadDone(SNI_Packet * *,SNI_Packet * *,ulong,ulong)

- ea: `0x100444980`
- end: `0x1004454a0`
- name: `?ReadDone@CryptoBase@@UEAAKPEAPEAVSNI_Packet@@0KK@Z`
- size: `2848`
- prototype: `unsigned int __usercall@<eax>(CryptoBase *__hidden this@<rcx>, struct SNI_Packet **@<rdx>, struct SNI_Packet **@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x10041d520`
- `0x10041d950`
- `0x10041f180`
- `0x100423130`
- `0x100429470`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100443550`
- `0x100443c30`
- `0x1004445c0`
- `0x100444980`
- `0x100446b10`
- `0x100447930`
- `0x100448060`
- `0x100448700`
- `0x1004499b0`
- `0x100455430`
- `0x1004557f0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100444b7f`
- `KERNEL32!QueryPerformanceCounter` at `0x10044511a`
- `KERNEL32!QueryPerformanceCounter` at `0x100444b7f`
- `KERNEL32!QueryPerformanceCounter` at `0x10044511a`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x100444b63`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x1004450fe`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100444b6f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10044510a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100444dc7`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100444dc7`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100444e0e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100444e0e`
- `sqldk!SystemThread_TlsIndex` at `0x100444d1d`
- `sqldk!SystemThread_TlsIndex` at `0x100444d69`
- `sqldk!SystemThread_TlsOffset` at `0x100444d26`
- `sqldk!SystemThread_TlsOffset` at `0x100444d72`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100444d42`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100444d8d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100444d42`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100444d8d`

## string_xrefs

- `0x1004449b7`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100444b24`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100444c1a`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100444caa`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100444db2`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100444e27`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100444e4b`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100444ecc`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100444f57`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x1004451a9`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100445260`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x1004452b1`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100445343`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100445390`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x1004453a7`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100445424`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x10044543c`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x1004449c2`: `CryptoBase::ReadDone`
- `0x100444b1d`: `CryptoBase::ReadDone`
- `0x100444c10`: `CryptoBase::ReadDone`
- `0x100444ca3`: `CryptoBase::ReadDone`
- `0x100444ec5`: `CryptoBase::ReadDone`
- `0x10044519f`: `CryptoBase::ReadDone`
- `0x100445259`: `CryptoBase::ReadDone`
- `0x1004452aa`: `CryptoBase::ReadDone`
- `0x100445339`: `CryptoBase::ReadDone`
- `0x100445389`: `CryptoBase::ReadDone`
- `0x1004453d7`: `CryptoBase::ReadDone`
- `0x10044541a`: `CryptoBase::ReadDone`
- `0x100445435`: `CryptoBase::ReadDone`
- `0x10044529d`: `ERR|SNITask enqueue failed: %d{WINERR}\n`
- `0x100444f62`: `CryptoBase::HandshakeReadDone`
- `0x100445042`: `CryptoBase::HandshakeReadDone`
- `0x100445061`: `CryptoBase::HandshakeReadDone`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CryptoBase::ReadDone(
        CryptoBase *this,
        struct SNI_Packet **a2,
        struct SNI_Packet **a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned int Token; // edi
  unsigned int v10; // eax
  const wchar_t *v11; // r9
  SOS_UnfairRecursiveMutexExtendedGuarantee **v12; // r13
  LARGE_INTEGER *v13; // r14
  LARGE_INTEGER v14; // rax
  struct SNI_Packet *v15; // rcx
  __int64 v16; // rbx
  unsigned int v17; // ecx
  int v18; // ecx
  int v19; // edx
  int v20; // eax
  __int64 v21; // r8
  struct SNI_Packet *v22; // rax
  __int64 v23; // r14
  __int64 v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rax
  _QWORD *v27; // rax
  void *v28; // r14
  CryptoBase *v29; // rcx
  int v30; // r8d
  const wchar_t *v31; // r9
  struct SNI_Packet *v32; // rsi
  int v33; // eax
  __int64 v34; // rsi
  unsigned int v35; // eax
  LARGE_INTEGER *v36; // rsi
  LARGE_INTEGER v37; // rax
  void *v38; // rsi
  CryptoBase *v39; // rcx
  unsigned int v40; // eax
  unsigned int v41; // r14d
  char v42; // al
  const wchar_t *v43; // rax
  int v45[2]; // [rsp+28h] [rbp-51h]
  int v46[2]; // [rsp+28h] [rbp-51h]
  __int64 v47; // [rsp+30h] [rbp-49h]
  __int64 v48; // [rsp+38h] [rbp-41h]
  LARGE_INTEGER PerformanceCount; // [rsp+D8h] [rbp+5Fh] BYREF

  Token = a5;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
      "CryptoBase::ReadDone",
      1382,
      L"API|SNI%u#, ppPacket: %p{SNI_Packet**}, ppLeftOver: %p{SNI_Packet**}, dwBytes: %d, dwError: %d{WINERR}\n",
      *((_DWORD *)this + 11),
      a2,
      a3,
      a4,
      a5);
  if ( *((_DWORD *)this + 12) == 5 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, struct SNI_Packet **, struct SNI_Packet **, _QWORD, unsigned int))(**((_QWORD **)this + 1) + 56LL))(
            *((_QWORD *)this + 1),
            a2,
            a3,
            a4,
            Token);
    Token = v10;
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      v46[0] = v10;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
        "CryptoBase::ReadDone",
        1393,
        L"RET|SNI%d{WINERR}\n",
        *(_QWORD *)v46);
    }
    goto LABEL_133;
  }
  v12 = (SOS_UnfairRecursiveMutexExtendedGuarantee **)*((_QWORD *)this + 12);
  CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v12);
  if ( *((unsigned __int8 *)*a2 + 233) == *((_DWORD *)this + 6) )
    *((_BYTE *)*a2 + 233) = 10;
  else
    Token = (*(__int64 (__fastcall **)(_QWORD, struct SNI_Packet **, struct SNI_Packet **, _QWORD, unsigned int))(**((_QWORD **)this + 1) + 56LL))(
              *((_QWORD *)this + 1),
              a2,
              a3,
              a4,
              Token);
  if ( *a2 )
  {
    switch ( *((_DWORD *)this + 12) )
    {
      case 0:
      case 1:
      case 7:
        if ( *((_BYTE *)this + 288) )
        {
          Token = -1;
          if ( *((_DWORD *)this + 26) )
          {
            Token = *((_DWORD *)this + 26);
          }
          else
          {
            *((_DWORD *)this + 26) = -1;
            *((_DWORD *)this + 27) = 50120;
          }
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            LODWORD(v48) = Token;
            LODWORD(v47) = 20;
            v45[0] = *((_DWORD *)this + 6);
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
              "CryptoBase::ReadDone",
              1579,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              *(_QWORD *)v45,
              v47,
              v48);
          }
          SNISetLastError(*((unsigned int *)this + 6), Token, 50120);
          *((_DWORD *)this + 48) = 2;
          *((_DWORD *)this + 49) = 4;
        }
        CryptoBase::SetLoginEvent(this, 0);
        if ( Token )
        {
          SNIPacketRelease(*a2);
          *a2 = 0;
          if ( !*((_BYTE *)this + 288) )
          {
            *((_DWORD *)this + 48) = 2;
            *((_DWORD *)this + 49) = 5;
          }
        }
        v32 = *a2;
        *a2 = 0;
        if ( (*(_BYTE *)(*((_QWORD *)this + 4) + 12804LL) & 2) != 0 && (*((_BYTE *)this + 64) & 8) != 0 )
        {
          if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
          {
            LODWORD(v48) = Token;
            v45[0] = *((_DWORD *)this + 11);
            SNIXE_SNI_ENTER_ON(
              "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
              "CryptoBase::HandshakeReadDone",
              3010,
              L"API|SNI%u#, pPacket: %p{SNI_Packet*}, dwError: %d{WINERR}\n",
              *(_QWORD *)v45,
              v32,
              v48);
          }
          if ( Token )
          {
LABEL_83:
            if ( Token != 997 )
            {
              *((_DWORD *)this + 12) = 4;
              if ( !*((_DWORD *)this + 26) )
              {
                *((_DWORD *)this + 26) = Token;
                *((_DWORD *)this + 27) = 50131;
              }
              CryptoBase::CallbackError(this);
            }
          }
          else
          {
            while ( *((_DWORD *)this + 12) != 3 )
            {
              Token = CryptoBase::HandshakeReadToken(this, v32);
              v32 = 0;
              if ( !Token )
              {
                Token = (*(__int64 (__fastcall **)(CryptoBase *))(*(_QWORD *)this + 336LL))(this);
                if ( !Token )
                {
                  v33 = *((_DWORD *)this + 12);
                  if ( v33 == 7 )
                    continue;
                  if ( v33 == 3 )
                    break;
                  Token = CryptoBase::HandshakeWriteToken(this, 0);
                  if ( !Token )
                    continue;
                }
              }
              goto LABEL_83;
            }
            CryptoBase::ProcessPendingIO(this);
          }
          if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
          {
            v45[0] = Token;
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
              "CryptoBase::HandshakeReadDone",
              3062,
              L"RET|SNI%d{WINERR}\n",
              *(_QWORD *)v45);
          }
          if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
            SNIXE_SNI_LEAVE_ON(
              "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
              "CryptoBase::HandshakeReadDone",
              3010,
              v31);
          goto LABEL_91;
        }
        if ( !Token )
        {
          v35 = CryptoBase::HandshakeReadToken(this, v32);
          Token = v35;
          if ( v35 )
          {
            if ( v35 != 997 )
            {
              *((_DWORD *)this + 12) = 4;
              v34 = *((_QWORD *)this + 4);
              goto LABEL_98;
            }
          }
        }
LABEL_91:
        v34 = *((_QWORD *)this + 4);
        if ( Token == 997 )
        {
          Token = 0;
          LOBYTE(PerformanceCount.LowPart) = 0;
          SNI_Conn::ReleaseUnderForceCloseLock(v34, 4, &PerformanceCount);
          break;
        }
LABEL_98:
        if ( (*(_BYTE *)(v34 + 12804) & 2) != 0 && (*((_BYTE *)this + 64) & 8) != 0 )
        {
          SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v12[1]);
          goto LABEL_110;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v34 + 12748));
        v36 = (LARGE_INTEGER *)*((_QWORD *)this + 4);
        if ( CommonGlobalState::m_CollectingStatistics )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v37 = PerformanceCount;
          }
          else
          {
            v37.QuadPart = MEMORY[0x7FFE0008];
          }
          v36[1598] = v37;
        }
        if ( Token )
          *((_DWORD *)this + 12) = 4;
        if ( g_osviSNI.dwMajorVersion < 6 )
        {
          *((_DWORD *)this + 28) = Token;
          v34 = *((_QWORD *)this + 4);
          SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v12[1]);
          SNIAutoEvent::Signal((CryptoBase *)((char *)this + 232));
          *a2 = 0;
LABEL_110:
          LOBYTE(PerformanceCount.LowPart) = 0;
          SNI_Conn::ReleaseUnderForceCloseLock(v34, 4, &PerformanceCount);
          if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
          {
            v45[0] = Token;
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
              "CryptoBase::ReadDone",
              1755,
              L"RET|SNI%d{WINERR}\n",
              *(_QWORD *)v45);
          }
          goto LABEL_133;
        }
        CryptoBase::SetLoginEvent(this, 3);
        *((_DWORD *)this + 28) = Token;
        v38 = (void *)*((_QWORD *)this + 4);
        SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v12[1]);
        if ( *(_QWORD *)(*((_QWORD *)this + 25) + 56LL) )
          v40 = CryptoBase::AuthEnqueueTaskWrapper(this, (void *(*)(void *))SNIProcessAddProviderOnWorker, v38);
        else
          v40 = CryptoBase::EnqueueAuthTask(v39, (void *(*)(void *))SNIProcessAddProviderOnWorker, v38);
        if ( v40 )
        {
          v41 = Token;
          CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v12);
          Token = 14;
          *((_DWORD *)this + 28) = 14;
          *((_DWORD *)this + 12) = 4;
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            LODWORD(v48) = 14;
            LODWORD(v47) = 23;
            v45[0] = *((_DWORD *)this + 6);
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
              "CryptoBase::ReadDone",
              1711,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              *(_QWORD *)v45,
              v47,
              v48);
          }
          SNISetLastError(*((unsigned int *)this + 6), 14, 50123);
          *((_DWORD *)this + 48) = 1;
          *((_DWORD *)this + 49) = 3;
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            v45[0] = 14;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
              "CryptoBase::ReadDone",
              1714,
              L"ERR|SNITask enqueue failed: %d{WINERR}\n",
              *(_QWORD *)v45);
          }
          CryptoBase::SetLoginEvent(this, 3);
          SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v12[1]);
          SNIProcessAddProviderOnIOCP(v38, 14, v41, 3);
          LOBYTE(PerformanceCount.LowPart) = 0;
          SNI_Conn::ReleaseUnderForceCloseLock(v38, 1, &PerformanceCount);
        }
        *a2 = 0;
        LOBYTE(PerformanceCount.LowPart) = 0;
        SNI_Conn::ReleaseUnderForceCloseLock(v38, 4, &PerformanceCount);
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          v45[0] = Token;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
            "CryptoBase::ReadDone",
            1734,
            L"RET|SNI%d{WINERR}\n",
            *(_QWORD *)v45);
        }
        goto LABEL_133;
      case 3:
        if ( Token || (*((_DWORD *)this + 16) & 0x800) == 0 )
          goto LABEL_61;
        v23 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v24 = *(_QWORD *)(v23 + 256);
        if ( !v24 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v24 = *(_QWORD *)(v23 + 256);
        }
        if ( (*(_BYTE *)(*(_QWORD *)(v24 + 600) + 64LL) & 2) == 0 )
        {
LABEL_61:
          Token = CryptoBase::ReadDoneDecryptInternal(this, a2, a3, Token, 1);
          break;
        }
        v25 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v26 = *(_QWORD *)(v25 + 256);
        if ( !v26 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v26 = *(_QWORD *)(v25 + 256);
        }
        v27 = operator new(
                0x18u,
                *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v26 + 992) + 56LL) + 8LL),
                1,
                "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
                1529,
                6u);
        v28 = v27;
        if ( !v27 )
        {
          Token = 14;
          if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
            goto LABEL_130;
          v30 = 1553;
          goto LABEL_129;
        }
        *v27 = this;
        v27[1] = *a2;
        v29 = *a3;
        v27[2] = *a3;
        Token = CryptoBase::EnqueueAuthTask(v29, (void *(*)(void *))CryptoBase::ReadDoneDecryptInternalCallback, v27);
        if ( !Token )
        {
          *a2 = 0;
          *a3 = 0;
          break;
        }
        operator delete(v28, 0x18u);
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          v30 = 1547;
LABEL_129:
          LODWORD(v48) = Token;
          LODWORD(v47) = 0;
          v45[0] = *((_DWORD *)this + 6);
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
            "CryptoBase::ReadDone",
            v30,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            *(_QWORD *)v45,
            v47,
            v48);
        }
LABEL_130:
        SNISetLastError(*((unsigned int *)this + 6), Token, 50100);
        break;
      case 4:
        if ( !Token )
        {
          Token = *((_DWORD *)this + 26);
          if ( !Token )
            Token = -1;
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            v17 = *((_DWORD *)this + 27);
            if ( v17 == 50100 )
            {
              v18 = 19;
              v19 = 0;
            }
            else if ( v17 < 0xC3B4 )
            {
              v18 = -1;
              v19 = -2147024362;
            }
            else
            {
              v18 = v17 - 50100;
              v19 = 0;
            }
            v20 = 0;
            if ( v19 >= 0 )
              v20 = v18;
            LODWORD(v48) = Token;
            LODWORD(v47) = v20;
            v45[0] = *((_DWORD *)this + 6);
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
              "CryptoBase::ReadDone",
              1498,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              *(_QWORD *)v45,
              v47,
              v48);
          }
          v21 = *((unsigned int *)this + 27);
          if ( (_DWORD)v21 == 50100 )
            v21 = 50119;
          SNISetLastError(*((unsigned int *)this + 6), Token, v21);
        }
        if ( *((_QWORD *)this + 37) )
        {
          v22 = (struct SNI_Packet *)DynamicQueue::DeQueue((CryptoBase *)((char *)this + 296));
          *a3 = v22;
          *((_BYTE *)v22 + 233) = *((_BYTE *)this + 24);
        }
        else
        {
          *((_BYTE *)this + 289) = 0;
        }
        break;
      case 6:
        Token = -1;
        if ( *((_DWORD *)this + 26) )
        {
          Token = *((_DWORD *)this + 26);
        }
        else
        {
          *((_DWORD *)this + 26) = -1;
          *((_DWORD *)this + 27) = 50120;
        }
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v48) = Token;
          LODWORD(v47) = 20;
          v45[0] = *((_DWORD *)this + 6);
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
            "CryptoBase::ReadDone",
            1451,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            *(_QWORD *)v45,
            v47,
            v48);
        }
        SNISetLastError(*((unsigned int *)this + 6), Token, 50120);
        *((_DWORD *)this + 48) = 2;
        *((_DWORD *)this + 49) = 6;
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 4) + 12748LL));
        v13 = (LARGE_INTEGER *)*((_QWORD *)this + 4);
        if ( CommonGlobalState::m_CollectingStatistics )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v14 = PerformanceCount;
          }
          else
          {
            v14.QuadPart = MEMORY[0x7FFE0008];
          }
          v13[1598] = v14;
        }
        if ( *a2 )
        {
          SNIPacketRelease(*a2);
          *a2 = 0;
        }
        if ( *a3 )
        {
          SNIPacketRelease(*a3);
          *a3 = 0;
        }
        v15 = (struct SNI_Packet *)*((_QWORD *)this + 7);
        if ( v15 )
        {
          SNIPacketRelease(v15);
          *((_QWORD *)this + 7) = 0;
        }
        v16 = *((_QWORD *)this + 4);
        SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v12[1]);
        LOBYTE(PerformanceCount.LowPart) = 0;
        SNI_Conn::ReleaseUnderForceCloseLock(v16, 4, &PerformanceCount);
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          v45[0] = Token;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
            "CryptoBase::ReadDone",
            1489,
            L"RET|SNI%d{WINERR}\n",
            *(_QWORD *)v45);
        }
        goto LABEL_133;
      default:
        v42 = g_XeSniPkg_enabledBitmap;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          v43 = L"SSPI";
          if ( *((_DWORD *)this + 6) == 6 )
            v43 = L"SSL";
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
            "CryptoBase::ReadDone",
            1765,
            L"ERR|SNI%s provider is in an unknown state \n",
            v43);
          v42 = g_XeSniPkg_enabledBitmap;
        }
        Token = 5023;
        if ( (v42 & 2) == 0 )
          goto LABEL_130;
        v30 = 1768;
        goto LABEL_129;
    }
  }
  SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v12[1]);
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    v45[0] = Token;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
      "CryptoBase::ReadDone",
      1775,
      L"RET|SNI%d{WINERR}\n",
      *(_QWORD *)v45);
  }
LABEL_133:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp", "CryptoBase::ReadDone", 1382, v11);
  return Token;
}

```

## disassembly

```asm
0x100444980  mov     rax, rsp
0x100444983  push    rbp
0x100444984  push    r12
0x100444986  push    r13
0x100444988  push    r14
0x10044498a  push    r15
0x10044498c  lea     rbp, [rax-57h]
0x100444990  sub     rsp, 0A0h
0x100444997  mov     [rbp+4Fh+var_70], 0FFFFFFFFFFFFFFFEh
0x10044499f  mov     [rax+10h], rbx
0x1004449a3  mov     [rax+18h], rsi
0x1004449a7  mov     [rax+20h], rdi
0x1004449ab  mov     r14d, r9d
0x1004449ae  mov     rsi, r8
0x1004449b1  mov     r15, rdx
0x1004449b4  mov     rbx, rcx
0x1004449b7  lea     r12, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
0x1004449be  mov     [rbp+4Fh+var_58], r12
0x1004449c2  lea     r13, aCryptobaseRead_1; "CryptoBase::ReadDone"
0x1004449c9  mov     [rbp+4Fh+var_50], r13
0x1004449cd  mov     [rbp+4Fh+var_48], 566h
0x1004449d4  mov     edi, [rbp+4Fh+arg_20]
0x1004449d7  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004449de  jz      short loc_100444A12
0x1004449e0  mov     [rsp+0C0h+var_80], edi
0x1004449e4  mov     [rsp+0C0h+var_88], r9d
0x1004449e9  mov     [rsp+0C0h+var_90], r8
0x1004449ee  mov     [rsp+0C0h+var_98], rdx
0x1004449f3  mov     eax, [rcx+2Ch]
0x1004449f6  mov     [rsp+0C0h+var_A0], eax
0x1004449fa  lea     r9, aApiSniUPppacke_0; "API|SNI%u#, ppPacket: %p{SNI_Packet**},"...
0x100444a01  mov     r8d, 566h; int
0x100444a07  mov     rdx, r13; char *
0x100444a0a  mov     rcx, r12; char *
0x100444a0d  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100444a12  cmp     dword ptr [rbx+30h], 5
0x100444a16  jnz     short loc_100444A5F
0x100444a18  mov     rcx, [rbx+8]
0x100444a1c  mov     rax, [rcx]
0x100444a1f  mov     [rsp+0C0h+var_A0], edi
0x100444a23  mov     r9d, r14d
0x100444a26  mov     r8, rsi
0x100444a29  mov     rdx, r15
0x100444a2c  call    qword ptr [rax+38h]
0x100444a2f  mov     edi, eax
0x100444a31  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100444a38  jz      loc_100445443
0x100444a3e  mov     [rsp+0C0h+var_A0], eax
0x100444a42  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100444a49  mov     r8d, 571h; int
0x100444a4f  mov     rdx, r13; char *
0x100444a52  mov     rcx, r12; char *
0x100444a55  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100444a5a  jmp     loc_100445443
0x100444a5f  mov     r13, [rbx+60h]
0x100444a63  mov     [rbp+4Fh+var_68], r13
0x100444a67  xor     r12d, r12d
0x100444a6a  mov     [rbp+4Fh+var_60], r12d
0x100444a6e  mov     rcx, r13; this
0x100444a71  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100444a76  mov     [rbp+4Fh+var_60], 1
0x100444a7d  mov     rcx, [r15]
0x100444a80  movzx   eax, byte ptr [rcx+0E9h]
0x100444a87  cmp     eax, [rbx+18h]
0x100444a8a  jz      short loc_100444AA7
0x100444a8c  mov     rcx, [rbx+8]
0x100444a90  mov     rax, [rcx]
0x100444a93  mov     [rsp+0C0h+var_A0], edi
0x100444a97  mov     r9d, r14d
0x100444a9a  mov     r8, rsi
0x100444a9d  mov     rdx, r15
0x100444aa0  call    qword ptr [rax+38h]
0x100444aa3  mov     edi, eax
0x100444aa5  jmp     short loc_100444AAE
0x100444aa7  mov     byte ptr [rcx+0E9h], 0Ah
0x100444aae  cmp     qword ptr [r15], 0
0x100444ab2  jz      loc_1004453F3
0x100444ab8  movsxd  rax, dword ptr [rbx+30h]
0x100444abc  cmp     eax, 7; switch 8 cases
0x100444abf  ja      def_100444AD6; jumptable 0000000100444AD6 default case, cases 2,5
0x100444ac5  lea     rdx, cs:100400000h
0x100444acc  mov     ecx, ds:(jpt_100444AD6 - 100400000h)[rdx+rax*4]
0x100444ad3  add     rcx, rdx
0x100444ad6  jmp     rcx; switch jump
0x100444ad8  mov     eax, 0FFFFFFFFh; jumptable 0000000100444AD6 case 6
0x100444add  mov     edi, eax
0x100444adf  mov     ecx, [rbx+68h]
0x100444ae2  test    ecx, ecx
0x100444ae4  jz      short loc_100444AEA
0x100444ae6  mov     edi, ecx
0x100444ae8  jmp     short loc_100444AF4
0x100444aea  mov     [rbx+68h], eax
0x100444aed  mov     dword ptr [rbx+6Ch], 0C3C8h
0x100444af4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100444afb  jz      short loc_100444B30
0x100444afd  mov     dword ptr [rsp+0C0h+var_90], edi
0x100444b01  mov     dword ptr [rsp+0C0h+var_98], 14h
0x100444b09  mov     eax, [rbx+18h]
0x100444b0c  mov     [rsp+0C0h+var_A0], eax
0x100444b10  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100444b17  mov     r8d, 5ABh; int
0x100444b1d  lea     rdx, aCryptobaseRead_1; "CryptoBase::ReadDone"
0x100444b24  lea     rcx, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
0x100444b2b  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100444b30  mov     r8d, 0C3C8h
0x100444b36  mov     edx, edi
0x100444b38  mov     ecx, [rbx+18h]
0x100444b3b  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100444b40  mov     dword ptr [rbx+0C0h], 2
0x100444b4a  mov     dword ptr [rbx+0C4h], 6
0x100444b54  mov     rax, [rbx+20h]
0x100444b58  lock inc dword ptr [rax+31CCh]
0x100444b5f  mov     r14, [rbx+20h]
0x100444b63  mov     rax, cs:__imp_?m_CollectingStatistics@CommonGlobalState@@2_NA; bool CommonGlobalState::m_CollectingStatistics
0x100444b6a  cmp     byte ptr [rax], 0
0x100444b6d  jz      short loc_100444B9A
0x100444b6f  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100444b76  cmp     dword ptr [rax], 0
0x100444b79  jz      short loc_100444B8B
0x100444b7b  lea     rcx, [rbp+4Fh+PerformanceCount]; lpPerformanceCount
0x100444b7f  call    cs:__imp_QueryPerformanceCounter
0x100444b85  mov     rax, qword ptr [rbp+4Fh+PerformanceCount]
0x100444b89  jmp     short loc_100444B93
0x100444b8b  mov     rax, ds:7FFE0008h
0x100444b93  mov     [r14+31F0h], rax
0x100444b9a  mov     rcx, [r15]; struct SNI_Packet *
0x100444b9d  test    rcx, rcx
0x100444ba0  jz      short loc_100444BAA
0x100444ba2  call    SNIPacketRelease
0x100444ba7  mov     [r15], r12
0x100444baa  mov     rcx, [rsi]; struct SNI_Packet *
0x100444bad  test    rcx, rcx
0x100444bb0  jz      short loc_100444BBA
0x100444bb2  call    SNIPacketRelease
0x100444bb7  mov     [rsi], r12
0x100444bba  mov     rcx, [rbx+38h]; struct SNI_Packet *
0x100444bbe  test    rcx, rcx
0x100444bc1  jz      short loc_100444BCC
0x100444bc3  call    SNIPacketRelease
0x100444bc8  mov     [rbx+38h], r12
0x100444bcc  mov     rbx, [rbx+20h]
0x100444bd0  mov     rcx, [r13+8]; this
0x100444bd4  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100444bd9  mov     [rbp+4Fh+var_60], r12d
0x100444bdd  mov     byte ptr [rbp+4Fh+PerformanceCount], 0
0x100444be1  lea     r8, [rbp+4Fh+PerformanceCount]
0x100444be5  mov     edx, 4
0x100444bea  mov     rcx, rbx
0x100444bed  call    ?ReleaseUnderForceCloseLock@SNI_Conn@@QEAAJW4SNI_REF@@AEA_N@Z; SNI_Conn::ReleaseUnderForceCloseLock(SNI_REF,bool &)
0x100444bf2  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100444bf9  jz      loc_100445435
0x100444bff  mov     [rsp+0C0h+var_A0], edi
0x100444c03  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100444c0a  mov     r8d, 5D1h; int
0x100444c10  lea     r13, aCryptobaseRead_1; "CryptoBase::ReadDone"
0x100444c17  mov     rdx, r13; char *
0x100444c1a  lea     r12, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
0x100444c21  mov     rcx, r12; char *
0x100444c24  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100444c29  jmp     loc_100445443
0x100444c2e  test    edi, edi; jumptable 0000000100444AD6 case 4
0x100444c30  jnz     loc_100444CCF
0x100444c36  mov     edi, [rbx+68h]
0x100444c39  mov     eax, 0FFFFFFFFh
0x100444c3e  test    edi, edi
0x100444c40  cmovz   edi, eax
0x100444c43  mov     r14d, 0C3C7h
0x100444c49  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100444c50  jz      short loc_100444CB6
0x100444c52  mov     ecx, [rbx+6Ch]
0x100444c55  cmp     ecx, 0C3B4h
0x100444c5b  jnz     short loc_100444C6B
0x100444c5d  mov     ecx, r14d
0x100444c60  add     ecx, 0FFFF3C4Ch
0x100444c66  mov     edx, r12d
0x100444c69  jmp     short loc_100444C7F
0x100444c6b  jb      short loc_100444C78
0x100444c6d  add     ecx, 0FFFF3C4Ch
0x100444c73  mov     edx, r12d
0x100444c76  jmp     short loc_100444C7F
0x100444c78  mov     ecx, eax
0x100444c7a  mov     edx, 80070216h
0x100444c7f  mov     eax, r12d
0x100444c82  test    edx, edx
0x100444c84  cmovns  eax, ecx
0x100444c87  mov     dword ptr [rsp+0C0h+var_90], edi
0x100444c8b  mov     dword ptr [rsp+0C0h+var_98], eax
0x100444c8f  mov     eax, [rbx+18h]
0x100444c92  mov     [rsp+0C0h+var_A0], eax
0x100444c96  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100444c9d  mov     r8d, 5DAh; int
0x100444ca3  lea     rdx, aCryptobaseRead_1; "CryptoBase::ReadDone"
0x100444caa  lea     rcx, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
0x100444cb1  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100444cb6  mov     r8d, [rbx+6Ch]
0x100444cba  cmp     r8d, 0C3B4h
0x100444cc1  cmovz   r8d, r14d
0x100444cc5  mov     edx, edi
0x100444cc7  mov     ecx, [rbx+18h]
0x100444cca  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100444ccf  lea     rcx, [rbx+128h]; this
0x100444cd6  cmp     qword ptr [rcx], 0
0x100444cda  jz      short loc_100444CF3
0x100444cdc  call    ?DeQueue@DynamicQueue@@QEAAPEAXXZ; DynamicQueue::DeQueue(void)
0x100444ce1  mov     [rsi], rax
0x100444ce4  movzx   ecx, byte ptr [rbx+18h]
0x100444ce8  mov     [rax+0E9h], cl
0x100444cee  jmp     loc_1004453F3
0x100444cf3  mov     byte ptr [rbx+121h], 0
0x100444cfa  jmp     loc_1004453F3
0x100444cff  test    edi, edi; jumptable 0000000100444AD6 case 3
0x100444d01  jnz     loc_100444E57
0x100444d07  test    dword ptr [rbx+40h], 800h
0x100444d0e  jz      loc_100444E57
0x100444d14  mov     rdx, gs:58h
0x100444d1d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100444d24  mov     ecx, [rax]
0x100444d26  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100444d2d  mov     r14d, [rax]
0x100444d30  add     r14, [rdx+rcx*8]
0x100444d34  mov     rax, [r14+100h]
0x100444d3b  test    rax, rax
0x100444d3e  jnz     short loc_100444D4F
0x100444d40  xor     ecx, ecx
0x100444d42  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100444d48  mov     rax, [r14+100h]
0x100444d4f  mov     rax, [rax+258h]
0x100444d56  test    byte ptr [rax+40h], 2
0x100444d5a  jz      loc_100444E57
0x100444d60  mov     rdx, gs:58h
0x100444d69  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100444d70  mov     ecx, [rax]
0x100444d72  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100444d79  mov     edi, [rax]
0x100444d7b  add     rdi, [rdx+rcx*8]
0x100444d7f  mov     rax, [rdi+100h]
0x100444d86  test    rax, rax
0x100444d89  jnz     short loc_100444D9A
0x100444d8b  xor     ecx, ecx
0x100444d8d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100444d93  mov     rax, [rdi+100h]
0x100444d9a  mov     rax, [rax+3E0h]
0x100444da1  mov     rcx, [rax+38h]
0x100444da5  mov     byte ptr [rsp+0C0h+var_98], 6
0x100444daa  mov     [rsp+0C0h+var_A0], 5F9h
0x100444db2  lea     r9, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
0x100444db9  mov     r8d, 1
0x100444dbf  mov     rdx, [rcx+8]
0x100444dc3  lea     ecx, [r8+17h]
0x100444dc7  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100444dcd  mov     r14, rax
0x100444dd0  test    rax, rax
0x100444dd3  jz      short loc_100444E33
0x100444dd5  mov     [rax], rbx
0x100444dd8  mov     rcx, [r15]
0x100444ddb  mov     [rax+8], rcx
0x100444ddf  mov     rcx, [rsi]; this
0x100444de2  mov     [rax+10h], rcx
0x100444de6  mov     r8, rax; void *
0x100444de9  lea     rdx, ?ReadDoneDecryptInternalCallback@CryptoBase@@CAPEAXPEAX@Z; void *(*)(void *)
0x100444df0  call    ?EnqueueAuthTask@CryptoBase@@IEAAKP6APEAXPEAX@Z0@Z; CryptoBase::EnqueueAuthTask(void * (*)(void *),void *)
0x100444df5  mov     edi, eax
0x100444df7  test    eax, eax
0x100444df9  jnz     short loc_100444E06
0x100444dfb  mov     [r15], r12
0x100444dfe  mov     [rsi], r12
0x100444e01  jmp     loc_1004453F3
0x100444e06  mov     edx, 18h
0x100444e0b  mov     rcx, r14
0x100444e0e  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100444e14  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100444e1b  jz      loc_1004453E3
0x100444e21  mov     r8d, 60Bh
0x100444e27  lea     rcx, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
0x100444e2e  jmp     loc_1004453C0
0x100444e33  mov     edi, 0Eh
0x100444e38  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100444e3f  jz      loc_1004453E3
0x100444e45  mov     r8d, 611h
0x100444e4b  lea     rcx, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
0x100444e52  jmp     loc_1004453C0
0x100444e57  mov     [rsp+0C0h+var_A0], 1; int
0x100444e5f  mov     r9d, edi; unsigned int
0x100444e62  mov     r8, rsi; struct SNI_Packet **
0x100444e65  mov     rdx, r15; struct SNI_Packet **
0x100444e68  mov     rcx, rbx; this
0x100444e6b  call    ?ReadDoneDecryptInternal@CryptoBase@@AEAAKPEAPEAVSNI_Packet@@0KH@Z; CryptoBase::ReadDoneDecryptInternal(SNI_Packet * *,SNI_Packet * *,ulong,int)
0x100444e70  mov     edi, eax
0x100444e72  jmp     loc_1004453F3
0x100444e77  cmp     byte ptr [rbx+120h], 0; jumptable 0000000100444AD6 cases 0,1,7
0x100444e7e  jz      short loc_100444EFC
0x100444e80  mov     eax, 0FFFFFFFFh
0x100444e85  mov     edi, eax
0x100444e87  mov     ecx, [rbx+68h]
0x100444e8a  test    ecx, ecx
0x100444e8c  jz      short loc_100444E92
0x100444e8e  mov     edi, ecx
0x100444e90  jmp     short loc_100444E9C
0x100444e92  mov     [rbx+68h], eax
0x100444e95  mov     dword ptr [rbx+6Ch], 0C3C8h
  ... truncated ...
```
