# Session::ReadSync(SNI_Packet * *,int)

- ea: `0x10042e690`
- end: `0x10042eec5`
- name: `?ReadSync@Session@@UEAAKPEAPEAVSNI_Packet@@H@Z`
- size: `2101`
- prototype: `unsigned int __fastcall(Session *__hidden this, struct SNI_Packet **, DWORD dwMilliseconds)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x10041d520`
- `0x10041d950`
- `0x10041f180`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x10042c710`
- `0x10042c7f0`
- `0x10042e690`
- `0x100433440`
- `0x100433a70`
- `0x1004349f0`
- `0x100455430`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x10042e83a`
- `KERNEL32!WaitForSingleObject` at `0x10042e83a`
- `KERNEL32!GetTickCount` at `0x10042e75d`
- `KERNEL32!GetTickCount` at `0x10042e7fd`
- `KERNEL32!GetTickCount` at `0x10042eba6`
- `KERNEL32!GetTickCount` at `0x10042e75d`
- `KERNEL32!GetTickCount` at `0x10042e7fd`
- `KERNEL32!GetTickCount` at `0x10042eba6`
- `KERNEL32!GetLastError` at `0x10042e858`
- `KERNEL32!GetLastError` at `0x10042e858`

## string_xrefs

- `0x10042e79d`: `Worker access incremented; new value = %d\n`
- `0x10042e7b1`: `sql\common\dk\sni\include\smux.hpp`
- `0x10042e925`: `sql\common\dk\sni\include\smux.hpp`
- `0x10042ea61`: `sql\common\dk\sni\include\smux.hpp`
- `0x10042e7aa`: `Smux::IncrementWorkerAccessCounter`
- `0x10042e91e`: `Smux::DecrementWorkerAccessCounter`
- `0x10042ea5a`: `Smux::DecrementWorkerAccessCounter`
- `0x10042e911`: `Worker access decremented; new value = %d\n`
- `0x10042ea4d`: `Worker access decremented; new value = %d\n`
- `0x10042e6bf`: `sql\common\dk\sni\src\smux.cpp`
- `0x10042e70b`: `sql\common\dk\sni\src\smux.cpp`
- `0x10042e968`: `sql\common\dk\sni\src\smux.cpp`
- `0x10042ea05`: `sql\common\dk\sni\src\smux.cpp`
- `0x10042ec9f`: `sql\common\dk\sni\src\smux.cpp`
- `0x10042ecff`: `sql\common\dk\sni\src\smux.cpp`
- `0x10042ed66`: `sql\common\dk\sni\src\smux.cpp`
- `0x10042edd3`: `sql\common\dk\sni\src\smux.cpp`
- `0x10042ee76`: `sql\common\dk\sni\src\smux.cpp`
- `0x10042ee9b`: `sql\common\dk\sni\src\smux.cpp`
- `0x10042e6ca`: `Session::ReadSync`
- `0x10042e712`: `Session::ReadSync`
- `0x10042e961`: `Session::ReadSync`
- `0x10042e9fe`: `Session::ReadSync`
- `0x10042ec98`: `Session::ReadSync`
- `0x10042ecf8`: `Session::ReadSync`
- `0x10042ed5f`: `Session::ReadSync`
- `0x10042edcc`: `Session::ReadSync`
- `0x10042ee6f`: `Session::ReadSync`
- `0x10042ee94`: `Session::ReadSync`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Session::ReadSync(Session *this, struct SNI_Packet **a2, signed int dwMilliseconds)
{
  struct SNI_Packet **v4; // rdi
  signed int v6; // r15d
  DWORD v7; // r14d
  DWORD TickCount; // ebp
  char v9; // si
  _QWORD *v10; // r12
  __int64 v11; // rdi
  signed __int32 v12; // eax
  SOS_UnfairRecursiveMutexExtendedGuarantee **v13; // rsi
  __int64 v14; // rcx
  DWORD v15; // eax
  DWORD LastError; // edi
  unsigned int v17; // edx
  CCriticalSectionSOS *v18; // rsi
  SOS_UnfairRecursiveMutexExtendedGuarantee *v19; // rcx
  const wchar_t *v20; // r9
  signed __int32 v21; // edx
  char v22; // al
  signed __int32 v23; // edx
  struct SNI_Packet **v24; // r12
  Smux *v25; // rsi
  CCriticalSectionSOS *v26; // rbp
  unsigned int v27; // eax
  char v28; // bp
  char v29; // bp
  __int64 v31; // [rsp+20h] [rbp-B8h]
  void *v32; // [rsp+28h] [rbp-B0h]
  unsigned int *v33; // [rsp+30h] [rbp-A8h]
  DWORD v35; // [rsp+F0h] [rbp+18h]

  v4 = a2;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\smux.cpp",
      "Session::ReadSync",
      1471,
      L"API|SNI%u#, ppNewPacket: %p{SNI_Packet**}, timeout: %d\n",
      *((_DWORD *)this + 11),
      a2,
      dwMilliseconds);
  v6 = dwMilliseconds;
  v7 = 0;
  TickCount = 0;
  v35 = 0;
  *v4 = 0;
  v9 = *((_BYTE *)this + 161);
  if ( v9 || *((_BYTE *)this + 163) || *((_BYTE *)this + 164) )
  {
    LastError = -1;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v33) = -1;
      LODWORD(v32) = 19 - (v9 != 0);
      LODWORD(v31) = 2;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\smux.cpp",
        "Session::ReadSync",
        1501,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v31,
        v32,
        v33);
    }
    goto LABEL_82;
  }
  if ( dwMilliseconds != -1 )
  {
    TickCount = GetTickCount();
    v35 = TickCount;
  }
  v10 = (_QWORD *)((char *)this + 136);
  if ( *((_QWORD *)this + 17) )
  {
LABEL_26:
    v18 = (CCriticalSectionSOS *)*((_QWORD *)this + 7);
    CCriticalSectionSOS::Enter(v18);
    *v4 = (struct SNI_Packet *)DynamicQueue::DeQueue((Session *)((char *)this + 136));
    LastError = Session::PostReceiveFlowControl(this, v4);
    v19 = (SOS_UnfairRecursiveMutexExtendedGuarantee *)*((_QWORD *)v18 + 1);
    if ( LastError )
    {
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v19);
      goto LABEL_83;
    }
    goto LABEL_78;
  }
  while ( 1 )
  {
    v11 = *((_QWORD *)this + 6);
    v12 = _InterlockedIncrement((volatile signed __int32 *)(v11 + 124));
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v31) = v12;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\include\\smux.hpp",
        "Smux::IncrementWorkerAccessCounter",
        96,
        L"Worker access incremented; new value = %d\n",
        v31);
    }
    if ( !_InterlockedCompareExchange64((volatile signed __int64 *)(v11 + 136), (signed __int64)this, 0) )
    {
      v25 = (Smux *)*((_QWORD *)this + 6);
      if ( *v10 )
      {
        if ( v25 )
        {
          Smux::WakeUpNextWorker(v25, this, 0);
          v25 = 0;
        }
        v26 = (CCriticalSectionSOS *)*((_QWORD *)this + 7);
        CCriticalSectionSOS::Enter(v26);
        v24 = a2;
        *a2 = (struct SNI_Packet *)DynamicQueue::DeQueue((Session *)((char *)this + 136));
        v27 = Session::PostReceiveFlowControl(this, a2);
        LastError = v27;
LABEL_49:
        v19 = (SOS_UnfairRecursiveMutexExtendedGuarantee *)*((_QWORD *)v26 + 1);
        if ( !v27 )
          goto LABEL_78;
        SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v19);
      }
      else
      {
        v28 = *((_BYTE *)this + 161);
        if ( v28 || *((_BYTE *)this + 163) || *((_BYTE *)this + 164) )
        {
          LastError = -1;
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            LODWORD(v33) = -1;
            LODWORD(v32) = 19 - (v28 != 0);
            LODWORD(v31) = 2;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\smux.cpp",
              "Session::ReadSync",
              1558,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              v31,
              v32,
              v33);
          }
          SNISetLastError(2, 0xFFFFFFFFLL, 50119 - (unsigned int)(v28 != 0));
          if ( v25 )
            Smux::WakeUpNextWorker(v25, this, 0);
LABEL_83:
          v24 = a2;
          goto LABEL_84;
        }
        v24 = a2;
        while ( 1 )
        {
          if ( dwMilliseconds != -1 )
          {
            v6 = dwMilliseconds + v35 - GetTickCount();
            if ( v6 < 0 )
              break;
          }
          LastError = Smux::Worker(*((Smux **)this + 6), v6, a2, *((_WORD *)this + 32), 1, 0, 0);
          if ( LastError )
            goto LABEL_51;
          v29 = *((_BYTE *)this + 161);
          if ( v29 || *((_BYTE *)this + 163) || *((_BYTE *)this + 164) )
          {
            LastError = -1;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              LODWORD(v33) = -1;
              LODWORD(v32) = 19 - (v29 != 0);
              LODWORD(v31) = 2;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\smux.cpp",
                "Session::ReadSync",
                1596,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v31,
                v32,
                v33);
            }
            SNISetLastError(2, 0xFFFFFFFFLL, 50119 - (unsigned int)(v29 != 0));
            goto LABEL_51;
          }
          if ( *a2 )
          {
            if ( v25 )
            {
              Smux::WakeUpNextWorker(v25, this, 0);
              v25 = 0;
            }
            v26 = (CCriticalSectionSOS *)*((_QWORD *)this + 7);
            CCriticalSectionSOS::Enter(v26);
            v27 = Session::PostReceiveFlowControl(this, a2);
            LastError = v27;
            goto LABEL_49;
          }
        }
        LastError = 258;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v33) = 258;
          LODWORD(v32) = 11;
          LODWORD(v31) = 2;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\smux.cpp",
            "Session::ReadSync",
            1570,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v31,
            v32,
            v33);
        }
        SNISetLastError(2, 258, 50111);
      }
LABEL_51:
      if ( v25 )
        Smux::WakeUpNextWorker(v25, this, 0);
      goto LABEL_84;
    }
    v13 = (SOS_UnfairRecursiveMutexExtendedGuarantee **)*((_QWORD *)this + 7);
    CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v13);
    if ( *v10 )
      break;
    if ( dwMilliseconds != -1 )
    {
      v6 = dwMilliseconds + TickCount - GetTickCount();
      if ( v6 < 0 )
      {
        v21 = _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 6) + 124LL));
        v22 = g_XeSniPkg_enabledBitmap;
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v31) = v21;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\include\\smux.hpp",
            "Smux::DecrementWorkerAccessCounter",
            113,
            L"Worker access decremented; new value = %d\n",
            v31);
          v22 = g_XeSniPkg_enabledBitmap;
        }
        LastError = 258;
        if ( (v22 & 2) != 0 )
        {
          LODWORD(v33) = 258;
          LODWORD(v32) = 11;
          LODWORD(v31) = 2;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\smux.cpp",
            "Session::ReadSync",
            1662,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v31,
            v32,
            v33);
        }
        SNISetLastError(2, 258, 50111);
        SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v13[1]);
        goto LABEL_83;
      }
    }
    *((_BYTE *)this + 201) = 1;
    v14 = *((_QWORD *)this + 23);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
    v15 = WaitForSingleObject(*((HANDLE *)this + 24), v6);
    if ( v15 )
    {
      if ( v15 == 258 )
      {
        v17 = 258;
        LastError = 258;
        goto LABEL_35;
      }
      if ( v15 != -1 )
      {
        LastError = -2147418113;
        v17 = -2147418113;
LABEL_35:
        Session::HandleWaitError(this, v17);
        goto LABEL_83;
      }
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError )
        goto LABEL_35;
    }
    v9 = *((_BYTE *)this + 161);
    if ( v9 || *((_BYTE *)this + 163) || *((_BYTE *)this + 164) )
    {
      if ( !*v10 )
        Smux::WakeUpNextWorker(*((Smux **)this + 6), 0, 0);
      LastError = -1;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v33) = -1;
        LODWORD(v32) = 19 - (v9 != 0);
        LODWORD(v31) = 2;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\smux.cpp",
          "Session::ReadSync",
          1704,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v31,
          v32,
          v33);
      }
LABEL_82:
      SNISetLastError(2, 0xFFFFFFFFLL, 50119 - (unsigned int)(v9 != 0));
      goto LABEL_83;
    }
    if ( *v10 )
    {
      v4 = a2;
      goto LABEL_26;
    }
  }
  v23 = _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 6) + 124LL));
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v31) = v23;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\include\\smux.hpp",
      "Smux::DecrementWorkerAccessCounter",
      113,
      L"Worker access decremented; new value = %d\n",
      v31);
  }
  v24 = a2;
  *a2 = (struct SNI_Packet *)DynamicQueue::DeQueue((Session *)((char *)this + 136));
  LastError = Session::PostReceiveFlowControl(this, a2);
  v19 = v13[1];
  if ( LastError )
  {
    SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v19);
LABEL_84:
    if ( *v24 )
    {
      SNIPacketRelease(*v24);
      *v24 = 0;
    }
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v31) = LastError;
      SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\smux.cpp", "Session::ReadSync", 1722, L"RET|SNI%d{WINERR}\n", v31);
    }
    v7 = LastError;
    goto LABEL_89;
  }
LABEL_78:
  SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v19);
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v31) = 0;
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\smux.cpp", "Session::ReadSync", 1710, L"RET|SNI%d{WINERR}\n", v31);
  }
LABEL_89:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\smux.cpp", "Session::ReadSync", 1471, v20);
  return v7;
}

```

## disassembly

```asm
0x10042e690  mov     rax, rsp
0x10042e693  mov     [rax+10h], rdx
0x10042e697  push    rbp
0x10042e698  push    rsi
0x10042e699  push    rdi
0x10042e69a  push    r12
0x10042e69c  push    r13
0x10042e69e  push    r14
0x10042e6a0  push    r15
0x10042e6a2  sub     rsp, 0A0h
0x10042e6a9  mov     [rsp+0D8h+var_98], 0FFFFFFFFFFFFFFFEh
0x10042e6b2  mov     [rax+8], rbx
0x10042e6b6  mov     r13d, r8d
0x10042e6b9  mov     rdi, rdx
0x10042e6bc  mov     rbx, rcx
0x10042e6bf  lea     r10, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x10042e6c6  mov     [rax-58h], r10
0x10042e6ca  lea     rdx, aSessionReadsyn; "Session::ReadSync"
0x10042e6d1  mov     [rax-50h], rdx
0x10042e6d5  mov     dword ptr [rax-48h], 5BFh
0x10042e6dc  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042e6e3  jz      short loc_10042E719
0x10042e6e5  mov     dword ptr [rsp+0D8h+var_A8], r8d
0x10042e6ea  mov     [rsp+0D8h+var_B0], rdi
0x10042e6ef  mov     eax, [rcx+2Ch]
0x10042e6f2  mov     dword ptr [rsp+0D8h+var_B8], eax
0x10042e6f6  lea     r9, aApiSniUPpnewpa_1; "API|SNI%u#, ppNewPacket: %p{SNI_Packet*"...
0x10042e6fd  mov     r8d, 5BFh; int
0x10042e703  mov     rcx, r10; char *
0x10042e706  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10042e70b  lea     r10, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x10042e712  lea     rdx, aSessionReadsyn; "Session::ReadSync"
0x10042e719  mov     r15d, r13d
0x10042e71c  xor     r14d, r14d
0x10042e71f  mov     ebp, r14d
0x10042e722  mov     [rsp+0D8h+arg_10], r14d
0x10042e72a  mov     [rdi], r14
0x10042e72d  movzx   esi, byte ptr [rbx+0A1h]
0x10042e734  test    sil, sil
0x10042e737  jnz     loc_10042EDE4
0x10042e73d  cmp     [rbx+0A3h], bpl
0x10042e744  jnz     loc_10042EDE4
0x10042e74a  cmp     [rbx+0A4h], bpl
0x10042e751  jnz     loc_10042EDE4
0x10042e757  cmp     r13d, 0FFFFFFFFh
0x10042e75b  jz      short loc_10042E76C
0x10042e75d  call    cs:__imp_GetTickCount
0x10042e763  mov     ebp, eax
0x10042e765  mov     [rsp+0D8h+arg_10], eax
0x10042e76c  lea     r12, [rbx+88h]
0x10042e773  cmp     [r12], r14
0x10042e777  jnz     loc_10042E8A7
0x10042e77d  nop     dword ptr [rax]
0x10042e780  mov     rdi, [rbx+30h]
0x10042e784  mov     eax, 1
0x10042e789  lock xadd [rdi+7Ch], eax
0x10042e78e  inc     eax
0x10042e790  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042e797  jz      short loc_10042E7BD
0x10042e799  mov     dword ptr [rsp+0D8h+var_B8], eax
0x10042e79d  lea     r9, aWorkerAccessIn; "Worker access incremented; new value = "...
0x10042e7a4  mov     r8d, 60h ; '`'; int
0x10042e7aa  lea     rdx, aSmuxIncrementw; "Smux::IncrementWorkerAccessCounter"
0x10042e7b1  lea     rcx, aSqlCommonDkSni; "sql\\common\\dk\\sni\\include\\smux.hpp"
0x10042e7b8  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10042e7bd  xor     eax, eax
0x10042e7bf  lock cmpxchg [rdi+88h], rbx
0x10042e7c8  jz      loc_10042EAA4
0x10042e7ce  mov     rsi, [rbx+38h]
0x10042e7d2  mov     [rsp+0D8h+var_90], rsi
0x10042e7d7  mov     [rsp+0D8h+var_88], r14d
0x10042e7dc  mov     rcx, rsi; this
0x10042e7df  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x10042e7e4  mov     [rsp+0D8h+var_88], 1
0x10042e7ec  cmp     qword ptr [r12], 0
0x10042e7f1  jnz     loc_10042EA30
0x10042e7f7  cmp     r13d, 0FFFFFFFFh
0x10042e7fb  jz      short loc_10042E812
0x10042e7fd  call    cs:__imp_GetTickCount
0x10042e803  mov     r15d, ebp
0x10042e806  add     r15d, r13d
0x10042e809  sub     r15d, eax
0x10042e80c  js      loc_10042E8F3
0x10042e812  mov     byte ptr [rbx+0C9h], 1
0x10042e819  mov     [rsp+0D8h+var_88], r14d
0x10042e81e  mov     rcx, [rbx+0B8h]
0x10042e825  test    rcx, rcx
0x10042e828  jz      short loc_10042E830
0x10042e82a  mov     rax, [rcx]
0x10042e82d  call    qword ptr [rax+18h]
0x10042e830  mov     edx, r15d; dwMilliseconds
0x10042e833  mov     rcx, [rbx+0C0h]; hHandle
0x10042e83a  call    cs:__imp_WaitForSingleObject
0x10042e840  test    eax, eax
0x10042e842  jz      short loc_10042E86A
0x10042e844  cmp     eax, 102h
0x10042e849  jz      loc_10042E99E
0x10042e84f  cmp     eax, 0FFFFFFFFh
0x10042e852  jnz     loc_10042E995
0x10042e858  call    cs:__imp_GetLastError
0x10042e85e  mov     edi, eax
0x10042e860  mov     edx, eax
0x10042e862  test    eax, eax
0x10042e864  jnz     loc_10042E9A5
0x10042e86a  movzx   esi, byte ptr [rbx+0A1h]
0x10042e871  test    sil, sil
0x10042e874  jnz     loc_10042E9B3
0x10042e87a  cmp     [rbx+0A3h], sil
0x10042e881  jnz     loc_10042E9B3
0x10042e887  cmp     [rbx+0A4h], sil
0x10042e88e  jnz     loc_10042E9B3
0x10042e894  cmp     qword ptr [r12], 0
0x10042e899  jz      loc_10042E780
0x10042e89f  mov     rdi, [rsp+0D8h+arg_8]
0x10042e8a7  mov     rsi, [rbx+38h]
0x10042e8ab  mov     [rsp+0D8h+var_80], rsi
0x10042e8b0  mov     [rsp+0D8h+var_78], r14d
0x10042e8b5  mov     rcx, rsi; this
0x10042e8b8  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x10042e8bd  mov     [rsp+0D8h+var_78], 1
0x10042e8c5  mov     rcx, r12; this
0x10042e8c8  call    ?DeQueue@DynamicQueue@@QEAAPEAXXZ; DynamicQueue::DeQueue(void)
0x10042e8cd  mov     [rdi], rax
0x10042e8d0  mov     rdx, rdi; struct SNI_Packet **
0x10042e8d3  mov     rcx, rbx; this
0x10042e8d6  call    ?PostReceiveFlowControl@Session@@AEAAKPEAPEAVSNI_Packet@@@Z; Session::PostReceiveFlowControl(SNI_Packet * *)
0x10042e8db  mov     edi, eax
0x10042e8dd  mov     rcx, [rsi+8]; this
0x10042e8e1  test    eax, eax
0x10042e8e3  jz      loc_10042EDA8
0x10042e8e9  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x10042e8ee  jmp     loc_10042EE3B
0x10042e8f3  mov     rax, [rbx+30h]
0x10042e8f7  mov     edx, 0FFFFFFFFh
0x10042e8fc  lock xadd [rax+7Ch], edx
0x10042e901  dec     edx
0x10042e903  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042e909  test    al, 1
0x10042e90b  jz      short loc_10042E937
0x10042e90d  mov     dword ptr [rsp+0D8h+var_B8], edx
0x10042e911  lea     r9, aWorkerAccessDe; "Worker access decremented; new value = "...
0x10042e918  mov     r8d, 71h ; 'q'; int
0x10042e91e  lea     rdx, aSmuxDecrementw; "Smux::DecrementWorkerAccessCounter"
0x10042e925  lea     rcx, aSqlCommonDkSni; "sql\\common\\dk\\sni\\include\\smux.hpp"
0x10042e92c  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10042e931  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042e937  mov     edi, 102h
0x10042e93c  test    al, 2
0x10042e93e  jz      short loc_10042E974
0x10042e940  mov     dword ptr [rsp+0D8h+var_A8], edi
0x10042e944  mov     dword ptr [rsp+0D8h+var_B0], 0Bh
0x10042e94c  mov     dword ptr [rsp+0D8h+var_B8], 2
0x10042e954  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10042e95b  mov     r8d, 67Eh; int
0x10042e961  lea     rdx, aSessionReadsyn; "Session::ReadSync"
0x10042e968  lea     rcx, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x10042e96f  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10042e974  mov     edx, edi
0x10042e976  mov     ecx, 2
0x10042e97b  mov     r8d, 0C3BFh
0x10042e981  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042e986  nop
0x10042e987  mov     rcx, [rsi+8]; this
0x10042e98b  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x10042e990  jmp     loc_10042EE3B
0x10042e995  mov     edi, 8000FFFFh
0x10042e99a  mov     edx, edi
0x10042e99c  jmp     short loc_10042E9A5
0x10042e99e  mov     edx, 102h; unsigned int
0x10042e9a3  mov     edi, edx
0x10042e9a5  mov     rcx, rbx; this
0x10042e9a8  call    ?HandleWaitError@Session@@AEAAXK@Z; Session::HandleWaitError(ulong)
0x10042e9ad  nop
0x10042e9ae  jmp     loc_10042EE3B
0x10042e9b3  cmp     qword ptr [r12], 0
0x10042e9b8  jnz     short loc_10042E9C8
0x10042e9ba  xor     r8d, r8d; bool
0x10042e9bd  xor     edx, edx; struct Session *
0x10042e9bf  mov     rcx, [rbx+30h]; this
0x10042e9c3  call    ?WakeUpNextWorker@Smux@@QEAAXPEAVSession@@_N@Z; Smux::WakeUpNextWorker(Session *,bool)
0x10042e9c8  mov     edi, 0FFFFFFFFh
0x10042e9cd  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042e9d4  jz      short loc_10042EA11
0x10042e9d6  movzx   eax, sil
0x10042e9da  neg     al
0x10042e9dc  sbb     ecx, ecx
0x10042e9de  add     ecx, 13h
0x10042e9e1  mov     dword ptr [rsp+0D8h+var_A8], edi
0x10042e9e5  mov     dword ptr [rsp+0D8h+var_B0], ecx
0x10042e9e9  mov     dword ptr [rsp+0D8h+var_B8], 2
0x10042e9f1  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10042e9f8  mov     r8d, 6A8h; int
0x10042e9fe  lea     rdx, aSessionReadsyn; "Session::ReadSync"
0x10042ea05  lea     rcx, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x10042ea0c  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10042ea11  neg     sil
0x10042ea14  sbb     r8d, r8d
0x10042ea17  add     r8d, 0C3C7h
0x10042ea1e  mov     edx, edi
0x10042ea20  mov     ecx, 2
0x10042ea25  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042ea2a  nop
0x10042ea2b  jmp     loc_10042EE3B
0x10042ea30  mov     rax, [rbx+30h]
0x10042ea34  mov     edx, 0FFFFFFFFh
0x10042ea39  lock xadd [rax+7Ch], edx
0x10042ea3e  dec     edx
0x10042ea40  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042ea47  jz      short loc_10042EA6D
0x10042ea49  mov     dword ptr [rsp+0D8h+var_B8], edx
0x10042ea4d  lea     r9, aWorkerAccessDe; "Worker access decremented; new value = "...
0x10042ea54  mov     r8d, 71h ; 'q'; int
0x10042ea5a  lea     rdx, aSmuxDecrementw; "Smux::DecrementWorkerAccessCounter"
0x10042ea61  lea     rcx, aSqlCommonDkSni; "sql\\common\\dk\\sni\\include\\smux.hpp"
0x10042ea68  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10042ea6d  mov     rcx, r12; this
0x10042ea70  call    ?DeQueue@DynamicQueue@@QEAAPEAXXZ; DynamicQueue::DeQueue(void)
0x10042ea75  mov     r12, [rsp+0D8h+arg_8]
0x10042ea7d  mov     [r12], rax
0x10042ea81  mov     rdx, r12; struct SNI_Packet **
0x10042ea84  mov     rcx, rbx; this
0x10042ea87  call    ?PostReceiveFlowControl@Session@@AEAAKPEAPEAVSNI_Packet@@@Z; Session::PostReceiveFlowControl(SNI_Packet * *)
0x10042ea8c  mov     edi, eax
0x10042ea8e  mov     rcx, [rsi+8]; this
0x10042ea92  test    eax, eax
0x10042ea94  jz      loc_10042EDA8
0x10042ea9a  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x10042ea9f  jmp     loc_10042EE43
0x10042eaa4  mov     rsi, [rbx+30h]
0x10042eaa8  mov     [rsp+0D8h+var_70], rsi
0x10042eaad  mov     [rsp+0D8h+var_68], rbx
0x10042eab2  mov     [rsp+0D8h+var_60], 0
0x10042eab7  cmp     qword ptr [r12], 0
0x10042eabc  jz      loc_10042EB68
0x10042eac2  test    rsi, rsi
0x10042eac5  jz      short loc_10042EADD
0x10042eac7  xor     r8d, r8d; bool
0x10042eaca  mov     rdx, rbx; struct Session *
0x10042eacd  mov     rcx, rsi; this
0x10042ead0  call    ?WakeUpNextWorker@Smux@@QEAAXPEAVSession@@_N@Z; Smux::WakeUpNextWorker(Session *,bool)
0x10042ead5  mov     rsi, r14
0x10042ead8  mov     [rsp+0D8h+var_70], r14
0x10042eadd  mov     rbp, [rbx+38h]
0x10042eae1  mov     [rsp+0D8h+var_80], rbp
0x10042eae6  mov     [rsp+0D8h+var_78], r14d
0x10042eaeb  mov     rcx, rbp; this
0x10042eaee  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x10042eaf3  mov     [rsp+0D8h+var_78], 1
0x10042eafb  mov     rcx, r12; this
0x10042eafe  call    ?DeQueue@DynamicQueue@@QEAAPEAXXZ; DynamicQueue::DeQueue(void)
0x10042eb03  mov     r12, [rsp+0D8h+arg_8]
0x10042eb0b  mov     [r12], rax
0x10042eb0f  mov     rdx, r12; struct SNI_Packet **
0x10042eb12  mov     rcx, rbx; this
0x10042eb15  call    ?PostReceiveFlowControl@Session@@AEAAKPEAPEAVSNI_Packet@@@Z; Session::PostReceiveFlowControl(SNI_Packet * *)
0x10042eb1a  mov     edi, eax
0x10042eb1c  mov     rcx, [rbp+8]; this
0x10042eb20  test    eax, eax
0x10042eb22  jz      short loc_10042EB46
0x10042eb24  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x10042eb29  nop
0x10042eb2a  test    rsi, rsi
0x10042eb2d  jz      loc_10042EE43
0x10042eb33  xor     r8d, r8d; bool
0x10042eb36  mov     rdx, rbx; struct Session *
0x10042eb39  mov     rcx, rsi; this
0x10042eb3c  call    ?WakeUpNextWorker@Smux@@QEAAXPEAVSession@@_N@Z; Smux::WakeUpNextWorker(Session *,bool)
0x10042eb41  jmp     loc_10042EE43
0x10042eb46  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x10042eb4b  nop
0x10042eb4c  test    rsi, rsi
0x10042eb4f  jz      loc_10042EDAD
0x10042eb55  xor     r8d, r8d; bool
0x10042eb58  mov     rdx, rbx; struct Session *
0x10042eb5b  mov     rcx, rsi; this
0x10042eb5e  call    ?WakeUpNextWorker@Smux@@QEAAXPEAVSession@@_N@Z; Smux::WakeUpNextWorker(Session *,bool)
0x10042eb63  jmp     loc_10042EDAD
0x10042eb68  movzx   ebp, byte ptr [rbx+0A1h]
0x10042eb6f  test    bpl, bpl
0x10042eb72  jnz     loc_10042ED29
0x10042eb78  cmp     [rbx+0A3h], bpl
0x10042eb7f  jnz     loc_10042ED29
0x10042eb85  cmp     [rbx+0A4h], bpl
0x10042eb8c  jnz     loc_10042ED29
0x10042eb92  mov     r12, [rsp+0D8h+arg_8]
0x10042eb9a  nop     word ptr [rax+rax+00h]
0x10042eba0  cmp     r13d, 0FFFFFFFFh
0x10042eba4  jz      short loc_10042EBC0
0x10042eba6  call    cs:__imp_GetTickCount
0x10042ebac  mov     r15d, [rsp+0D8h+arg_10]
0x10042ebb4  add     r15d, r13d
0x10042ebb7  sub     r15d, eax
0x10042ebba  js      loc_10042EC69
0x10042ebc0  mov     [rsp+0D8h+var_A8], r14; unsigned int *
0x10042ebc5  mov     [rsp+0D8h+var_B0], r14; void *
0x10042ebca  mov     [rsp+0D8h+var_B8], 1; bool
0x10042ebcf  movzx   r9d, word ptr [rbx+40h]; unsigned __int16
0x10042ebd4  mov     r8, r12; struct SNI_Packet **
0x10042ebd7  mov     edx, r15d; int
0x10042ebda  mov     rcx, [rbx+30h]; this
  ... truncated ...
```
