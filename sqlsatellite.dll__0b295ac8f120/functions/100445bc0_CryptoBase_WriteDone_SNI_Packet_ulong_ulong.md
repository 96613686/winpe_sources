# CryptoBase::WriteDone(SNI_Packet * *,ulong,ulong)

- ea: `0x100445bc0`
- end: `0x1004464f8`
- name: `?WriteDone@CryptoBase@@UEAAKPEAPEAVSNI_Packet@@KK@Z`
- size: `2360`
- prototype: `unsigned int __fastcall(CryptoBase *__hidden this, struct SNI_Packet **, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

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
- `0x100445bc0`
- `0x100446b10`
- `0x100447930`
- `0x100448060`
- `0x100448700`
- `0x1004494a0`
- `0x1004499b0`
- `0x100449a10`
- `0x1004557f0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100445df3`
- `KERNEL32!QueryPerformanceCounter` at `0x1004460f8`
- `KERNEL32!QueryPerformanceCounter` at `0x100445df3`
- `KERNEL32!QueryPerformanceCounter` at `0x1004460f8`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x100445dd7`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x1004460dc`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100445de3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004460e8`

## string_xrefs

- `0x100445bf7`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100445f7e`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x1004460b8`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100446203`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x1004462d2`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100446323`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x1004463b5`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100446490`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x10044630f`: `ERR|SNITask enqueue failed: %d{WINERR}\n`
- `0x100445c02`: `CryptoBase::WriteDone`
- `0x100445d10`: `CryptoBase::WriteDone`
- `0x100445d95`: `CryptoBase::WriteDone`
- `0x100445e74`: `CryptoBase::WriteDone`
- `0x100445ee7`: `CryptoBase::WriteDone`
- `0x1004461f9`: `CryptoBase::WriteDone`
- `0x1004462cb`: `CryptoBase::WriteDone`
- `0x10044631c`: `CryptoBase::WriteDone`
- `0x1004463ab`: `CryptoBase::WriteDone`
- `0x1004463fb`: `CryptoBase::WriteDone`
- `0x100446436`: `CryptoBase::WriteDone`
- `0x10044647c`: `CryptoBase::WriteDone`
- `0x100446497`: `CryptoBase::WriteDone`
- `0x100445f89`: `CryptoBase::HandshakeWriteDone`
- `0x100446062`: `CryptoBase::HandshakeWriteDone`
- `0x100446081`: `CryptoBase::HandshakeWriteDone`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CryptoBase::WriteDone(CryptoBase *this, struct SNI_Packet **a2, unsigned int a3, unsigned int a4)
{
  unsigned int Token; // edi
  unsigned int v8; // eax
  const wchar_t *v9; // r9
  SOS_UnfairRecursiveMutexExtendedGuarantee **v10; // r13
  LARGE_INTEGER *v11; // rsi
  LARGE_INTEGER v12; // rax
  struct SNI_Packet *v13; // rcx
  __int64 v14; // rbx
  const wchar_t *v15; // r9
  struct SNI_Packet *v16; // r14
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rsi
  LARGE_INTEGER *v20; // rsi
  LARGE_INTEGER v21; // rax
  unsigned int SecurityToken; // eax
  void *v23; // rsi
  CryptoBase *v24; // rcx
  unsigned int v25; // eax
  unsigned int v26; // r14d
  char v27; // al
  const wchar_t *v28; // rax
  __int64 v30; // [rsp+28h] [rbp-39h]
  __int64 v31; // [rsp+30h] [rbp-31h]
  __int64 v32; // [rsp+38h] [rbp-29h]
  LARGE_INTEGER PerformanceCount; // [rsp+C8h] [rbp+67h] BYREF

  Token = a4;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
      "CryptoBase::WriteDone",
      2090,
      L"API|SNI%u#, ppPacket: %p{SNI_Packet**}, dwBytes: %d, dwError: %d{WINERR}\n",
      *((_DWORD *)this + 11),
      a2,
      a3,
      a4,
      -2);
  if ( *((_DWORD *)this + 12) == 5 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, struct SNI_Packet **, _QWORD, _QWORD))(**((_QWORD **)this + 1) + 64LL))(
           *((_QWORD *)this + 1),
           a2,
           a3,
           Token);
    Token = v8;
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v30) = v8;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
        "CryptoBase::WriteDone",
        2101,
        L"RET|SNI%d{WINERR}\n",
        v30);
    }
    goto LABEL_106;
  }
  v10 = (SOS_UnfairRecursiveMutexExtendedGuarantee **)*((_QWORD *)this + 12);
  CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v10);
  if ( *((unsigned __int8 *)*a2 + 233) == *((_DWORD *)this + 6) )
  {
    *((_BYTE *)*a2 + 233) = 10;
    if ( !a3 )
    {
      Token = -1;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v32) = -1;
        LODWORD(v31) = 31;
        LODWORD(v30) = *((_DWORD *)this + 6);
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
          "CryptoBase::WriteDone",
          2124,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v30,
          v31,
          v32);
      }
      SNISetLastError(*((unsigned int *)this + 6), 0xFFFFFFFFLL, 50131);
    }
  }
  else
  {
    Token = (*(__int64 (__fastcall **)(_QWORD, struct SNI_Packet **, _QWORD, _QWORD))(**((_QWORD **)this + 1) + 64LL))(
              *((_QWORD *)this + 1),
              a2,
              a3,
              Token);
  }
  switch ( *((_DWORD *)this + 12) )
  {
    case 1:
    case 2:
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
          LODWORD(v32) = Token;
          LODWORD(v31) = 20;
          LODWORD(v30) = *((_DWORD *)this + 6);
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
            "CryptoBase::WriteDone",
            2209,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v30,
            v31,
            v32);
        }
        SNISetLastError(*((unsigned int *)this + 6), Token, 50120);
        *((_DWORD *)this + 48) = 3;
        *((_DWORD *)this + 49) = 7;
      }
      CryptoBase::SetLoginEvent(this, 1);
      if ( Token )
      {
        *((_DWORD *)this + 12) = 4;
        SNIPacketRelease(*a2);
        *a2 = 0;
        if ( !*((_BYTE *)this + 288) )
        {
          *((_DWORD *)this + 48) = 3;
          *((_DWORD *)this + 49) = 8;
        }
      }
      v16 = *a2;
      *a2 = 0;
      v17 = *((_QWORD *)this + 4);
      if ( (*(_BYTE *)(v17 + 12804) & 2) != 0 && (*((_BYTE *)this + 64) & 8) != 0 )
      {
        if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
        {
          LODWORD(v32) = Token;
          LODWORD(v30) = *((_DWORD *)this + 11);
          SNIXE_SNI_ENTER_ON(
            "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
            "CryptoBase::HandshakeWriteDone",
            3364,
            L"API|SNI%u#, pPacket: %p{SNI_Packet*}, dwError: %d{WINERR}\n",
            v30,
            v16,
            v32);
        }
        if ( Token )
        {
LABEL_52:
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
          while ( 1 )
          {
            v18 = *((_DWORD *)this + 12);
            if ( v18 == 3 )
              break;
            if ( v18 != 7 )
              Token = CryptoBase::HandshakeWriteToken(this, v16);
            v16 = 0;
            if ( !Token )
            {
              if ( *((_DWORD *)this + 12) == 3 )
                break;
              Token = CryptoBase::HandshakeReadToken(this, 0);
              if ( !Token )
              {
                Token = (*(__int64 (__fastcall **)(CryptoBase *))(*(_QWORD *)this + 336LL))(this);
                if ( !Token )
                  continue;
              }
            }
            goto LABEL_52;
          }
          CryptoBase::ProcessPendingIO(this);
        }
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v30) = Token;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
            "CryptoBase::HandshakeWriteDone",
            3415,
            L"RET|SNI%d{WINERR}\n",
            v30);
        }
        if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
          SNIXE_SNI_LEAVE_ON(
            "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
            "CryptoBase::HandshakeWriteDone",
            3364,
            v15);
        goto LABEL_60;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v17 + 12744));
      v20 = (LARGE_INTEGER *)*((_QWORD *)this + 4);
      if ( CommonGlobalState::m_CollectingStatistics )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v21 = PerformanceCount;
        }
        else
        {
          v21.QuadPart = MEMORY[0x7FFE0008];
        }
        v20[1599] = v21;
      }
      if ( Token )
      {
        if ( Token != 997 )
        {
          *((_DWORD *)this + 12) = 4;
          v19 = *((_QWORD *)this + 4);
          goto LABEL_72;
        }
      }
      else
      {
        Token = CryptoBase::HandshakeWriteToken(this, v16);
      }
LABEL_60:
      v19 = *((_QWORD *)this + 4);
      if ( Token == 997 )
      {
        Token = 0;
        LOBYTE(PerformanceCount.LowPart) = 0;
        SNI_Conn::ReleaseUnderForceCloseLock(v19, 6, &PerformanceCount);
        goto LABEL_104;
      }
LABEL_72:
      if ( (*(_BYTE *)(v19 + 12804) & 2) != 0 && (*((_BYTE *)this + 64) & 8) != 0 )
      {
        SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v10[1]);
        goto LABEL_82;
      }
      if ( g_osviSNI.dwMajorVersion < 6 )
      {
        *((_DWORD *)this + 28) = Token;
        SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v10[1]);
        SNIAutoEvent::Signal((CryptoBase *)((char *)this + 232));
LABEL_81:
        *a2 = 0;
LABEL_82:
        LOBYTE(PerformanceCount.LowPart) = 0;
        SNI_Conn::ReleaseUnderForceCloseLock(v19, 6, &PerformanceCount);
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v30) = Token;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
            "CryptoBase::WriteDone",
            2396,
            L"RET|SNI%d{WINERR}\n",
            v30);
        }
        goto LABEL_106;
      }
      if ( !Token && *((_DWORD *)this + 12) != 3 )
      {
        *((_DWORD *)this + 54) = 2;
        SecurityToken = CryptoBase::ReadSecurityToken(this);
        Token = SecurityToken;
        if ( SecurityToken == 997 )
        {
          v19 = *((_QWORD *)this + 4);
          SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v10[1]);
          goto LABEL_81;
        }
        if ( SecurityToken )
        {
          *((_DWORD *)this + 48) = 2;
          *((_DWORD *)this + 49) = 9;
        }
      }
      CryptoBase::SetLoginEvent(this, 3);
      *((_DWORD *)this + 28) = Token;
      v23 = (void *)*((_QWORD *)this + 4);
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v10[1]);
      if ( *(_QWORD *)(*((_QWORD *)this + 25) + 56LL) )
        v25 = CryptoBase::AuthEnqueueTaskWrapper(this, (void *(*)(void *))SNIProcessAddProviderOnWorker, v23);
      else
        v25 = CryptoBase::EnqueueAuthTask(v24, (void *(*)(void *))SNIProcessAddProviderOnWorker, v23);
      if ( v25 )
      {
        v26 = Token;
        CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v10);
        Token = 14;
        *((_DWORD *)this + 28) = 14;
        *((_DWORD *)this + 12) = 4;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v32) = 14;
          LODWORD(v31) = 23;
          LODWORD(v30) = *((_DWORD *)this + 6);
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
            "CryptoBase::WriteDone",
            2348,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v30,
            v31,
            v32);
        }
        SNISetLastError(*((unsigned int *)this + 6), 14, 50123);
        *((_DWORD *)this + 48) = 1;
        *((_DWORD *)this + 49) = 10;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v30) = 14;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
            "CryptoBase::WriteDone",
            2351,
            L"ERR|SNITask enqueue failed: %d{WINERR}\n",
            v30);
        }
        CryptoBase::SetLoginEvent(this, 3);
        SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v10[1]);
        SNIProcessAddProviderOnIOCP(v23, 14, v26, 10);
        LOBYTE(PerformanceCount.LowPart) = 0;
        SNI_Conn::ReleaseUnderForceCloseLock(v23, 1, &PerformanceCount);
      }
      *a2 = 0;
      LOBYTE(PerformanceCount.LowPart) = 0;
      SNI_Conn::ReleaseUnderForceCloseLock(v23, 6, &PerformanceCount);
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v30) = Token;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
          "CryptoBase::WriteDone",
          2371,
          L"RET|SNI%d{WINERR}\n",
          v30);
      }
LABEL_106:
      if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
        SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp", "CryptoBase::WriteDone", 2090, v9);
      return Token;
    case 3:
    case 4:
      CryptoBase::RestoreHeaderTrailerOnWriteCompletion(this, *a2);
      goto LABEL_104;
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
        LODWORD(v32) = Token;
        LODWORD(v31) = 20;
        LODWORD(v30) = *((_DWORD *)this + 6);
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
          "CryptoBase::WriteDone",
          2153,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v30,
          v31,
          v32);
      }
      SNISetLastError(*((unsigned int *)this + 6), Token, 50120);
      *((_DWORD *)this + 48) = 2;
      *((_DWORD *)this + 49) = 11;
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 4) + 12744LL));
      v11 = (LARGE_INTEGER *)*((_QWORD *)this + 4);
      if ( CommonGlobalState::m_CollectingStatistics )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v12 = PerformanceCount;
        }
        else
        {
          v12.QuadPart = MEMORY[0x7FFE0008];
        }
        v11[1599] = v12;
      }
      if ( *a2 )
      {
        SNIPacketRelease(*a2);
        *a2 = 0;
      }
      v13 = (struct SNI_Packet *)*((_QWORD *)this + 7);
      if ( v13 )
      {
        SNIPacketRelease(v13);
        *((_QWORD *)this + 7) = 0;
      }
      v14 = *((_QWORD *)this + 4);
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v10[1]);
      LOBYTE(PerformanceCount.LowPart) = 0;
      SNI_Conn::ReleaseUnderForceCloseLock(v14, 6, &PerformanceCount);
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v30) = Token;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
          "CryptoBase::WriteDone",
          2181,
          L"RET|SNI%d{WINERR}\n",
          v30);
      }
      goto LABEL_106;
    default:
      v27 = g_XeSniPkg_enabledBitmap;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        v28 = L"SSPI";
        if ( *((_DWORD *)this + 6) == 6 )
          v28 = L"SSL";
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
          "CryptoBase::WriteDone",
          2406,
          L"ERR|SNI%s provider is in an unknown state \n",
          v28);
        v27 = g_XeSniPkg_enabledBitmap;
      }
      Token = 5023;
      if ( (v27 & 2) != 0 )
      {
        LODWORD(v32) = 5023;
        LODWORD(v31) = 0;
        LODWORD(v30) = *((_DWORD *)this + 6);
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
          "CryptoBase::WriteDone",
          2410,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v30,
          v31,
          v32);
      }
      SNISetLastError(*((unsigned int *)this + 6), 5023, 50100);
LABEL_104:
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v10[1]);
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v30) = Token;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
          "CryptoBase::WriteDone",
          2415,
          L"RET|SNI%d{WINERR}\n",
          v30);
      }
      goto LABEL_106;
  }
}

```

## disassembly

```asm
0x100445bc0  mov     rax, rsp
0x100445bc3  push    rbp
0x100445bc4  push    r12
0x100445bc6  push    r13
0x100445bc8  push    r14
0x100445bca  push    r15
0x100445bcc  lea     rbp, [rax-5Fh]
0x100445bd0  sub     rsp, 90h
0x100445bd7  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x100445bdf  mov     [rax+10h], rbx
0x100445be3  mov     [rax+18h], rsi
0x100445be7  mov     [rax+20h], rdi
0x100445beb  mov     edi, r9d
0x100445bee  mov     esi, r8d
0x100445bf1  mov     r15, rdx
0x100445bf4  mov     rbx, rcx
0x100445bf7  lea     r14, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
0x100445bfe  mov     [rbp+57h+var_58], r14
0x100445c02  lea     r12, aCryptobaseWrit_1; "CryptoBase::WriteDone"
0x100445c09  mov     [rbp+57h+var_50], r12
0x100445c0d  mov     [rbp+57h+var_48], 82Ah
0x100445c14  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100445c1b  jz      short loc_100445C4A
0x100445c1d  mov     [rax-80h], r9d
0x100445c21  mov     [rsp+0B0h+var_80], r8d
0x100445c26  mov     [rsp+0B0h+var_88], rdx
0x100445c2b  mov     eax, [rcx+2Ch]
0x100445c2e  mov     dword ptr [rsp+0B0h+var_90], eax
0x100445c32  lea     r9, aApiSniUPppacke_2; "API|SNI%u#, ppPacket: %p{SNI_Packet**},"...
0x100445c39  mov     r8d, 82Ah; int
0x100445c3f  mov     rdx, r12; char *
0x100445c42  mov     rcx, r14; char *
0x100445c45  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100445c4a  cmp     dword ptr [rbx+30h], 5
0x100445c4e  jnz     short loc_100445C93
0x100445c50  mov     rcx, [rbx+8]
0x100445c54  mov     rax, [rcx]
0x100445c57  mov     r9d, edi
0x100445c5a  mov     r8d, esi
0x100445c5d  mov     rdx, r15
0x100445c60  call    qword ptr [rax+40h]
0x100445c63  mov     edi, eax
0x100445c65  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100445c6c  jz      loc_10044649E
0x100445c72  mov     dword ptr [rsp+0B0h+var_90], eax
0x100445c76  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100445c7d  mov     r8d, 835h; int
0x100445c83  mov     rdx, r12; char *
0x100445c86  mov     rcx, r14; char *
0x100445c89  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100445c8e  jmp     loc_10044649E
0x100445c93  mov     r13, [rbx+60h]
0x100445c97  mov     [rbp+57h+var_68], r13
0x100445c9b  xor     r12d, r12d
0x100445c9e  mov     [rbp+57h+var_60], r12d
0x100445ca2  mov     rcx, r13; this
0x100445ca5  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100445caa  mov     [rbp+57h+var_60], 1
0x100445cb1  mov     rcx, [r15]
0x100445cb4  movzx   eax, byte ptr [rcx+0E9h]
0x100445cbb  cmp     eax, [rbx+18h]
0x100445cbe  jz      short loc_100445CD7
0x100445cc0  mov     rcx, [rbx+8]
0x100445cc4  mov     rax, [rcx]
0x100445cc7  mov     r9d, edi
0x100445cca  mov     r8d, esi
0x100445ccd  mov     rdx, r15
0x100445cd0  call    qword ptr [rax+40h]
0x100445cd3  mov     edi, eax
0x100445cd5  jmp     short loc_100445D2F
0x100445cd7  mov     byte ptr [rcx+0E9h], 0Ah
0x100445cde  test    esi, esi
0x100445ce0  jnz     short loc_100445D2F
0x100445ce2  mov     edi, 0FFFFFFFFh
0x100445ce7  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100445cee  jz      short loc_100445D1F
0x100445cf0  mov     [rsp+0B0h+var_80], edi
0x100445cf4  mov     dword ptr [rsp+0B0h+var_88], 1Fh
0x100445cfc  mov     eax, [rbx+18h]
0x100445cff  mov     dword ptr [rsp+0B0h+var_90], eax
0x100445d03  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100445d0a  mov     r8d, 84Ch; int
0x100445d10  lea     rdx, aCryptobaseWrit_1; "CryptoBase::WriteDone"
0x100445d17  mov     rcx, r14; char *
0x100445d1a  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100445d1f  mov     edx, edi
0x100445d21  mov     r8d, 0C3D3h
0x100445d27  mov     ecx, [rbx+18h]
0x100445d2a  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100445d2f  mov     eax, [rbx+30h]
0x100445d32  dec     eax; switch 7 cases
0x100445d34  cmp     eax, 6
0x100445d37  ja      def_100445D50; jumptable 0000000100445D50 default case, case 5
0x100445d3d  cdqe
0x100445d3f  lea     rdx, cs:100400000h
0x100445d46  mov     ecx, ds:(jpt_100445D50 - 100400000h)[rdx+rax*4]
0x100445d4d  add     rcx, rdx
0x100445d50  jmp     rcx; switch jump
0x100445d52  mov     edi, 0FFFFFFFFh; jumptable 0000000100445D50 case 6
0x100445d57  mov     eax, [rbx+68h]
0x100445d5a  test    eax, eax
0x100445d5c  jz      short loc_100445D62
0x100445d5e  mov     edi, eax
0x100445d60  jmp     short loc_100445D6C
0x100445d62  mov     [rbx+68h], edi
0x100445d65  mov     dword ptr [rbx+6Ch], 0C3C8h
0x100445d6c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100445d73  jz      short loc_100445DA4
0x100445d75  mov     [rsp+0B0h+var_80], edi
0x100445d79  mov     dword ptr [rsp+0B0h+var_88], 14h
0x100445d81  mov     eax, [rbx+18h]
0x100445d84  mov     dword ptr [rsp+0B0h+var_90], eax
0x100445d88  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100445d8f  mov     r8d, 869h; int
0x100445d95  lea     rdx, aCryptobaseWrit_1; "CryptoBase::WriteDone"
0x100445d9c  mov     rcx, r14; char *
0x100445d9f  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100445da4  mov     r8d, 0C3C8h
0x100445daa  mov     edx, edi
0x100445dac  mov     ecx, [rbx+18h]
0x100445daf  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100445db4  mov     dword ptr [rbx+0C0h], 2
0x100445dbe  mov     dword ptr [rbx+0C4h], 0Bh
0x100445dc8  mov     rax, [rbx+20h]
0x100445dcc  lock inc dword ptr [rax+31C8h]
0x100445dd3  mov     rsi, [rbx+20h]
0x100445dd7  mov     rax, cs:__imp_?m_CollectingStatistics@CommonGlobalState@@2_NA; bool CommonGlobalState::m_CollectingStatistics
0x100445dde  cmp     byte ptr [rax], 0
0x100445de1  jz      short loc_100445E0E
0x100445de3  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100445dea  cmp     dword ptr [rax], 0
0x100445ded  jz      short loc_100445DFF
0x100445def  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x100445df3  call    cs:__imp_QueryPerformanceCounter
0x100445df9  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x100445dfd  jmp     short loc_100445E07
0x100445dff  mov     rax, ds:7FFE0008h
0x100445e07  mov     [rsi+31F8h], rax
0x100445e0e  mov     rcx, [r15]; struct SNI_Packet *
0x100445e11  test    rcx, rcx
0x100445e14  jz      short loc_100445E1E
0x100445e16  call    SNIPacketRelease
0x100445e1b  mov     [r15], r12
0x100445e1e  mov     rcx, [rbx+38h]; struct SNI_Packet *
0x100445e22  test    rcx, rcx
0x100445e25  jz      short loc_100445E30
0x100445e27  call    SNIPacketRelease
0x100445e2c  mov     [rbx+38h], r12
0x100445e30  mov     rbx, [rbx+20h]
0x100445e34  mov     rcx, [r13+8]; this
0x100445e38  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100445e3d  mov     [rbp+57h+var_60], r12d
0x100445e41  mov     byte ptr [rbp+57h+PerformanceCount], 0
0x100445e45  lea     r8, [rbp+57h+PerformanceCount]
0x100445e49  mov     edx, 6
0x100445e4e  mov     rcx, rbx
0x100445e51  call    ?ReleaseUnderForceCloseLock@SNI_Conn@@QEAAJW4SNI_REF@@AEA_N@Z; SNI_Conn::ReleaseUnderForceCloseLock(SNI_REF,bool &)
0x100445e56  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100445e5d  jz      loc_100446497
0x100445e63  mov     dword ptr [rsp+0B0h+var_90], edi
0x100445e67  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100445e6e  mov     r8d, 885h; int
0x100445e74  lea     r12, aCryptobaseWrit_1; "CryptoBase::WriteDone"
0x100445e7b  mov     rdx, r12; char *
0x100445e7e  mov     rcx, r14; char *
0x100445e81  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100445e86  jmp     loc_10044649E
0x100445e8b  mov     rdx, [r15]; jumptable 0000000100445D50 cases 3,4
0x100445e8e  mov     rcx, rbx; this
0x100445e91  call    ?RestoreHeaderTrailerOnWriteCompletion@CryptoBase@@IEAAXPEAVSNI_Packet@@@Z; CryptoBase::RestoreHeaderTrailerOnWriteCompletion(SNI_Packet *)
0x100445e96  jmp     loc_100446455
0x100445e9b  cmp     byte ptr [rbx+120h], 0; jumptable 0000000100445D50 cases 1,2,7
0x100445ea2  jz      short loc_100445F1A
0x100445ea4  mov     edi, 0FFFFFFFFh
0x100445ea9  mov     eax, [rbx+68h]
0x100445eac  test    eax, eax
0x100445eae  jz      short loc_100445EB4
0x100445eb0  mov     edi, eax
0x100445eb2  jmp     short loc_100445EBE
0x100445eb4  mov     [rbx+68h], edi
0x100445eb7  mov     dword ptr [rbx+6Ch], 0C3C8h
0x100445ebe  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100445ec5  jz      short loc_100445EF6
0x100445ec7  mov     [rsp+0B0h+var_80], edi
0x100445ecb  mov     dword ptr [rsp+0B0h+var_88], 14h
0x100445ed3  mov     eax, [rbx+18h]
0x100445ed6  mov     dword ptr [rsp+0B0h+var_90], eax
0x100445eda  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100445ee1  mov     r8d, 8A1h; int
0x100445ee7  lea     rdx, aCryptobaseWrit_1; "CryptoBase::WriteDone"
0x100445eee  mov     rcx, r14; char *
0x100445ef1  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100445ef6  mov     r8d, 0C3C8h
0x100445efc  mov     edx, edi
0x100445efe  mov     ecx, [rbx+18h]
0x100445f01  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100445f06  mov     dword ptr [rbx+0C0h], 3
0x100445f10  mov     dword ptr [rbx+0C4h], 7
0x100445f1a  mov     edx, 1
0x100445f1f  mov     r8d, edx
0x100445f22  mov     rcx, rbx
0x100445f25  call    ?SetLoginEvent@CryptoBase@@QEAAXW4SNIAuthTimerEvent@@W4SNIAuthTimerEventType@@@Z; CryptoBase::SetLoginEvent(SNIAuthTimerEvent,SNIAuthTimerEventType)
0x100445f2a  test    edi, edi
0x100445f2c  jz      short loc_100445F5D
0x100445f2e  mov     dword ptr [rbx+30h], 4
0x100445f35  mov     rcx, [r15]; struct SNI_Packet *
0x100445f38  call    SNIPacketRelease
0x100445f3d  mov     [r15], r12
0x100445f40  cmp     byte ptr [rbx+120h], 0
0x100445f47  jnz     short loc_100445F5D
0x100445f49  mov     dword ptr [rbx+0C0h], 3
0x100445f53  mov     dword ptr [rbx+0C4h], 8
0x100445f5d  mov     r14, [r15]
0x100445f60  mov     [r15], r12
0x100445f63  mov     rax, [rbx+20h]
0x100445f67  test    byte ptr [rax+3204h], 2
0x100445f6e  jz      loc_1004460D1
0x100445f74  test    byte ptr [rbx+40h], 8
0x100445f78  jz      loc_1004460D1
0x100445f7e  lea     rsi, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
0x100445f85  mov     [rbp+57h+var_40], rsi
0x100445f89  lea     rcx, aCryptobaseHand_2; "CryptoBase::HandshakeWriteDone"
0x100445f90  mov     [rbp+57h+var_38], rcx
0x100445f94  mov     [rbp+57h+var_30], 0D24h
0x100445f9b  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100445fa2  jz      short loc_100445FCC
0x100445fa4  mov     [rsp+0B0h+var_80], edi
0x100445fa8  mov     [rsp+0B0h+var_88], r14
0x100445fad  mov     eax, [rbx+2Ch]
0x100445fb0  mov     dword ptr [rsp+0B0h+var_90], eax
0x100445fb4  lea     r9, aApiSniUPpacket_1; "API|SNI%u#, pPacket: %p{SNI_Packet*}, d"...
0x100445fbb  mov     r8d, 0D24h; int
0x100445fc1  mov     rdx, rcx; char *
0x100445fc4  mov     rcx, rsi; char *
0x100445fc7  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100445fcc  test    edi, edi
0x100445fce  jnz     short loc_100446021
0x100445fd0  mov     eax, [rbx+30h]
0x100445fd3  cmp     eax, 3
0x100445fd6  jz      loc_1004460C4
0x100445fdc  cmp     eax, 7
0x100445fdf  jz      short loc_100445FEE
0x100445fe1  mov     rdx, r14; struct SNI_Packet *
0x100445fe4  mov     rcx, rbx; this
0x100445fe7  call    ?HandshakeWriteToken@CryptoBase@@IEAAKPEAVSNI_Packet@@@Z; CryptoBase::HandshakeWriteToken(SNI_Packet *)
0x100445fec  mov     edi, eax
0x100445fee  mov     r14, r12
0x100445ff1  test    edi, edi
0x100445ff3  jnz     short loc_100446021
0x100445ff5  cmp     dword ptr [rbx+30h], 3
0x100445ff9  jz      loc_1004460C4
0x100445fff  xor     edx, edx; struct SNI_Packet *
0x100446001  mov     rcx, rbx; this
0x100446004  call    ?HandshakeReadToken@CryptoBase@@IEAAKPEAVSNI_Packet@@@Z; CryptoBase::HandshakeReadToken(SNI_Packet *)
0x100446009  mov     edi, eax
0x10044600b  test    eax, eax
0x10044600d  jnz     short loc_100446021
0x10044600f  mov     rax, [rbx]
0x100446012  mov     rcx, rbx
0x100446015  call    qword ptr [rax+150h]
0x10044601b  mov     edi, eax
0x10044601d  test    eax, eax
0x10044601f  jz      short loc_100445FD0
0x100446021  cmp     edi, 3E5h
0x100446027  jz      short loc_100446048
0x100446029  mov     dword ptr [rbx+30h], 4
0x100446030  cmp     dword ptr [rbx+68h], 0
0x100446034  jnz     short loc_100446040
0x100446036  mov     [rbx+68h], edi
0x100446039  mov     dword ptr [rbx+6Ch], 0C3D3h
0x100446040  mov     rcx, rbx; this
0x100446043  call    ?CallbackError@CryptoBase@@IEAAXXZ; CryptoBase::CallbackError(void)
0x100446048  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044604f  jz      short loc_100446072
0x100446051  mov     dword ptr [rsp+0B0h+var_90], edi
0x100446055  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10044605c  mov     r8d, 0D57h; int
0x100446062  lea     rdx, aCryptobaseHand_2; "CryptoBase::HandshakeWriteDone"
0x100446069  mov     rcx, rsi; char *
0x10044606c  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100446071  nop
0x100446072  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100446079  jz      short loc_100446090
0x10044607b  mov     r8d, 0D24h; int
0x100446081  lea     rdx, aCryptobaseHand_2; "CryptoBase::HandshakeWriteDone"
0x100446088  mov     rcx, rsi; char *
0x10044608b  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100446090  mov     rsi, [rbx+20h]
0x100446094  cmp     edi, 3E5h
0x10044609a  jnz     loc_100446140
0x1004460a0  mov     edi, r12d
0x1004460a3  mov     byte ptr [rbp+57h+PerformanceCount], dil
0x1004460a7  lea     r8, [rbp+57h+PerformanceCount]
0x1004460ab  mov     edx, 6
0x1004460b0  mov     rcx, rsi
0x1004460b3  call    ?ReleaseUnderForceCloseLock@SNI_Conn@@QEAAJW4SNI_REF@@AEA_N@Z; SNI_Conn::ReleaseUnderForceCloseLock(SNI_REF,bool &)
0x1004460b8  lea     r14, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
0x1004460bf  jmp     loc_100446455
0x1004460c4  mov     rcx, rbx; this
0x1004460c7  call    ?ProcessPendingIO@CryptoBase@@IEAAXXZ; CryptoBase::ProcessPendingIO(void)
  ... truncated ...
```
