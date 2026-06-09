# ScRegisterPreshutdownRestart(ushort *)

- ea: `0x140011670`
- end: `0x140011a72`
- name: `?ScRegisterPreshutdownRestart@@YAKPEAG@Z`
- size: `1026`
- prototype: `unsigned int __fastcall(wchar_t *String2)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14006d5a0`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x140004c98`
- `0x140005584`
- `0x140007130`
- `0x140011670`
- `0x140011ba0`
- `0x140013b0c`
- `0x1400188fc`
- `0x14001c87c`
- `0x14004401c`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400119fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400119fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400116d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400118df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400116d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400118df`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400116c8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400116c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400116b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400116b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011a56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011a56`
- `RPCRT4!RpcImpersonateClient` at `0x14001169a`
- `RPCRT4!RpcImpersonateClient` at `0x14001169a`
- `RPCRT4!RpcRevertToSelf` at `0x1400116da`
- `RPCRT4!RpcRevertToSelf` at `0x1400116da`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140011787`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400118d5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140011787`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400118d5`
- `ntdll!RtlAcquireResourceExclusive` at `0x1400117e0`
- `ntdll!RtlAcquireResourceExclusive` at `0x1400117e0`
- `ntdll!RtlReleaseResource` at `0x1400119a5`
- `ntdll!RtlReleaseResource` at `0x140011a47`
- `ntdll!RtlReleaseResource` at `0x1400119a5`
- `ntdll!RtlReleaseResource` at `0x140011a47`

## pseudocode

```c
__int64 __fastcall ScRegisterPreshutdownRestart(wchar_t *String2)
{
  RPC_STATUS v2; // eax
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  unsigned int v5; // esi
  PRPC_ASYNC_STATE v6; // rcx
  int v7; // edx
  CServiceRecord *v8; // rbx
  char *v9; // rsi
  bool v10; // zf
  __int64 v11; // rax
  PRPC_ASYNC_STATE v12; // rcx
  int v13; // edx
  CServiceRecord *v15[2]; // [rsp+30h] [rbp-10h] BYREF
  WINBOOL IsMember; // [rsp+78h] [rbp+38h] BYREF
  char *v17; // [rsp+80h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp+48h] BYREF

  TokenHandle = 0;
  IsMember = 0;
  v15[0] = 0;
  v2 = RpcImpersonateClient(0);
  LastError = v2;
  if ( v2 )
  {
    ScLogImpersonateFailureEvent(v2);
    goto LABEL_55;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    LastError = GetLastError();
  v5 = RpcRevertToSelf();
  if ( LastError )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v7 = 156;
LABEL_9:
      WPP_SF_Sd(
        v6->StubInfo,
        v7,
        (unsigned int)WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
        (_DWORD)String2,
        LastError);
      goto LABEL_55;
    }
    goto LABEL_55;
  }
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 157, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, v5);
    ScLogEvent(5u, L"RpcRevertToSelf", v5);
    LastError = v5;
    goto LABEL_55;
  }
  if ( CheckTokenMembership(TokenHandle, LocalSystemSid, &IsMember) )
  {
    if ( IsMember != 1 )
    {
      LastError = 5;
      goto LABEL_55;
    }
    RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
    Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(v15);
    LastError = ScGetNamedServiceRecord(String2, v15);
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          159,
          (unsigned int)WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
          (_DWORD)String2,
          LastError);
      goto LABEL_54;
    }
    v8 = v15[0];
    v9 = (char *)v15[0] + 312;
    CScmLock::LockExclusive((CServiceRecord *)((char *)v15[0] + 312));
    v10 = (*((_DWORD *)v8 + 22) & 0x100) == 0;
    v17 = v9;
    if ( v10 || (*((_BYTE *)v8 + 80) & 0x30) == 0 )
    {
      LastError = 87;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_53;
      v13 = 160;
    }
    else
    {
      if ( !(*(__int64 (__fastcall **)(CServiceRecord *))(*(_QWORD *)v8 + 160LL))(v8)
        || !*(_QWORD *)((*(__int64 (__fastcall **)(CServiceRecord *))(*(_QWORD *)v8 + 160LL))(v8) + 96)
        || *((_DWORD *)v8 + 21) != 4 )
      {
        LastError = 1062;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            161,
            (unsigned int)WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
            (_DWORD)String2,
            38);
        }
        if ( v9 )
        {
          *((_DWORD *)v9 + 2) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)v9);
        }
        goto LABEL_54;
      }
      v11 = (*(__int64 (__fastcall **)(CServiceRecord *))(*(_QWORD *)v8 + 160LL))(v8);
      if ( CheckTokenMembership(TokenHandle, *(PSID *)(*(_QWORD *)(v11 + 96) + 88LL), &IsMember) )
      {
        if ( IsMember != 1 )
        {
          LastError = 5;
LABEL_53:
          CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v17);
LABEL_54:
          RtlReleaseResource(&ScServiceRecordLock);
          goto LABEL_55;
        }
        if ( g_fPreshutdownStarted != 1 )
        {
          CServiceRecord::SetStatusFlag(v8, 0x20000u);
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
          {
            WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 164, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, String2);
          }
          CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v17);
          RtlReleaseResource(&ScServiceRecordLock);
          LastError = 0;
          goto LABEL_55;
        }
        LastError = 1115;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_53;
        }
        v13 = 163;
      }
      else
      {
        LastError = GetLastError();
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_53;
        }
        v13 = 162;
      }
    }
    WPP_SF_Sd(
      v12->StubInfo,
      v13,
      (unsigned int)WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
      (_DWORD)String2,
      LastError);
    goto LABEL_53;
  }
  LastError = GetLastError();
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    v7 = 158;
    goto LABEL_9;
  }
LABEL_55:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(v15);
  return LastError;
}

```

## disassembly

```asm
0x140011670  push    rbp
0x140011672  push    rbx
0x140011673  push    rsi
0x140011674  push    rdi
0x140011675  push    r12
0x140011677  mov     rbp, rsp
0x14001167a  sub     rsp, 40h
0x14001167e  mov     rdi, rcx
0x140011681  mov     [rbp+TokenHandle], 0
0x140011689  xor     ecx, ecx; BindingHandle
0x14001168b  mov     [rbp+IsMember], 0
0x140011692  mov     [rbp+var_10], 0
0x14001169a  call    cs:__imp_RpcImpersonateClient
0x1400116a0  mov     ebx, eax
0x1400116a2  test    eax, eax
0x1400116a4  jz      short loc_1400116B2
0x1400116a6  mov     ecx, eax; int
0x1400116a8  call    ?ScLogImpersonateFailureEvent@@YAXJ@Z; ScLogImpersonateFailureEvent(long)
0x1400116ad  jmp     loc_140011A4D
0x1400116b2  call    cs:__imp_GetCurrentThread
0x1400116b8  mov     edx, 8; DesiredAccess
0x1400116bd  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1400116c1  mov     rcx, rax; ThreadHandle
0x1400116c4  lea     r8d, [rdx-7]; OpenAsSelf
0x1400116c8  call    cs:__imp_OpenThreadToken
0x1400116ce  test    eax, eax
0x1400116d0  jnz     short loc_1400116DA
0x1400116d2  call    cs:__imp_GetLastError
0x1400116d8  mov     ebx, eax
0x1400116da  call    cs:__imp_RpcRevertToSelf
0x1400116e0  mov     esi, eax
0x1400116e2  test    ebx, ebx
0x1400116e4  jz      short loc_140011728
0x1400116e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400116ed  lea     rax, WPP_GLOBAL_Control
0x1400116f4  cmp     rcx, rax
0x1400116f7  jz      loc_140011A4D
0x1400116fd  test    byte ptr [rcx+1Ch], 1
0x140011701  jz      loc_140011A4D
0x140011707  mov     edx, 9Ch
0x14001170c  mov     rcx, [rcx+10h]
0x140011710  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x140011717  mov     r9, rdi
0x14001171a  mov     [rsp+40h+var_20], ebx
0x14001171e  call    WPP_SF_Sd
0x140011723  jmp     loc_140011A4D
0x140011728  test    esi, esi
0x14001172a  jz      short loc_140011778
0x14001172c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011733  lea     rax, WPP_GLOBAL_Control
0x14001173a  cmp     rcx, rax
0x14001173d  jz      short loc_14001175D
0x14001173f  test    byte ptr [rcx+1Ch], 1
0x140011743  jz      short loc_14001175D
0x140011745  mov     rcx, [rcx+10h]
0x140011749  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x140011750  mov     edx, 9Dh
0x140011755  mov     r9d, esi
0x140011758  call    WPP_SF_d
0x14001175d  mov     r8d, esi
0x140011760  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x140011767  mov     ecx, 5; unsigned int
0x14001176c  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x140011771  mov     ebx, esi
0x140011773  jmp     loc_140011A4D
0x140011778  mov     rdx, cs:LocalSystemSid; SidToCheck
0x14001177f  lea     r8, [rbp+IsMember]; IsMember
0x140011783  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140011787  call    cs:__imp_CheckTokenMembership
0x14001178d  test    eax, eax
0x14001178f  jnz     short loc_1400117C4
0x140011791  call    cs:__imp_GetLastError
0x140011797  mov     ebx, eax
0x140011799  mov     rcx, cs:WPP_GLOBAL_Control
0x1400117a0  lea     rax, WPP_GLOBAL_Control
0x1400117a7  cmp     rcx, rax
0x1400117aa  jz      loc_140011A4D
0x1400117b0  test    byte ptr [rcx+1Ch], 1
0x1400117b4  jz      loc_140011A4D
0x1400117ba  mov     edx, 9Eh
0x1400117bf  jmp     loc_14001170C
0x1400117c4  cmp     [rbp+IsMember], 1
0x1400117c8  jz      short loc_1400117D4
0x1400117ca  mov     ebx, 5
0x1400117cf  jmp     loc_140011A4D
0x1400117d4  lea     r12, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; CServiceRecordLock ScServiceRecordLock
0x1400117db  mov     dl, 1; Wait
0x1400117dd  mov     rcx, r12; Resource
0x1400117e0  call    cs:__imp_RtlAcquireResourceExclusive
0x1400117e6  lea     rcx, [rbp+var_10]
0x1400117ea  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x1400117ef  lea     rdx, [rbp+var_10]; struct CServiceRecord **
0x1400117f3  mov     rcx, rdi; String2
0x1400117f6  call    ?ScGetNamedServiceRecord@@YAKPEBGPEAPEAVCServiceRecord@@@Z; ScGetNamedServiceRecord(ushort const *,CServiceRecord * *)
0x1400117fb  mov     ebx, eax
0x1400117fd  test    eax, eax
0x1400117ff  jz      short loc_140011843
0x140011801  mov     rcx, cs:WPP_GLOBAL_Control
0x140011808  lea     rax, WPP_GLOBAL_Control
0x14001180f  cmp     rcx, rax
0x140011812  jz      loc_140011A44
0x140011818  test    byte ptr [rcx+1Ch], 1
0x14001181c  jz      loc_140011A44
0x140011822  mov     rcx, [rcx+10h]
0x140011826  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14001182d  mov     edx, 9Fh
0x140011832  mov     [rsp+40h+var_20], ebx
0x140011836  mov     r9, rdi
0x140011839  call    WPP_SF_Sd
0x14001183e  jmp     loc_140011A44
0x140011843  mov     rbx, [rbp+var_10]
0x140011847  lea     rsi, [rbx+138h]
0x14001184e  mov     rcx, rsi; this
0x140011851  call    ?LockExclusive@CScmLock@@QEAAXXZ; CScmLock::LockExclusive(void)
0x140011856  test    dword ptr [rbx+58h], 100h
0x14001185d  mov     [rbp+arg_10], rsi
0x140011861  jz      loc_140011A03
0x140011867  test    byte ptr [rbx+50h], 30h
0x14001186b  jz      loc_140011A03
0x140011871  mov     rax, [rbx]
0x140011874  mov     rcx, rbx
0x140011877  mov     rax, [rax+0A0h]
0x14001187e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011883  test    rax, rax
0x140011886  jz      loc_1400119B2
0x14001188c  mov     rax, [rbx]
0x14001188f  mov     rcx, rbx
0x140011892  mov     rax, [rax+0A0h]
0x140011899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001189e  cmp     qword ptr [rax+60h], 0
0x1400118a3  jz      loc_1400119B2
0x1400118a9  cmp     dword ptr [rbx+54h], 4
0x1400118ad  jnz     loc_1400119B2
0x1400118b3  mov     rax, [rbx]
0x1400118b6  mov     rcx, rbx
0x1400118b9  mov     rax, [rax+0A0h]
0x1400118c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400118c5  lea     r8, [rbp+IsMember]; IsMember
0x1400118c9  mov     rcx, [rax+60h]
0x1400118cd  mov     rdx, [rcx+58h]; SidToCheck
0x1400118d1  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400118d5  call    cs:__imp_CheckTokenMembership
0x1400118db  test    eax, eax
0x1400118dd  jnz     short loc_140011912
0x1400118df  call    cs:__imp_GetLastError
0x1400118e5  mov     ebx, eax
0x1400118e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400118ee  lea     rax, WPP_GLOBAL_Control
0x1400118f5  cmp     rcx, rax
0x1400118f8  jz      loc_140011A3B
0x1400118fe  test    byte ptr [rcx+1Ch], 1
0x140011902  jz      loc_140011A3B
0x140011908  mov     edx, 0A2h
0x14001190d  jmp     loc_140011A24
0x140011912  cmp     [rbp+IsMember], 1
0x140011916  jz      short loc_140011922
0x140011918  mov     ebx, 5
0x14001191d  jmp     loc_140011A3B
0x140011922  cmp     cs:g_fPreshutdownStarted, 1
0x140011929  jnz     short loc_14001195B
0x14001192b  mov     ebx, 45Bh
0x140011930  mov     rcx, cs:WPP_GLOBAL_Control
0x140011937  lea     rax, WPP_GLOBAL_Control
0x14001193e  cmp     rcx, rax
0x140011941  jz      loc_140011A3B
0x140011947  test    byte ptr [rcx+1Ch], 1
0x14001194b  jz      loc_140011A3B
0x140011951  mov     edx, 0A3h
0x140011956  jmp     loc_140011A24
0x14001195b  mov     edx, 20000h; unsigned int
0x140011960  mov     rcx, rbx; this
0x140011963  call    ?SetStatusFlag@CServiceRecord@@QEAAXK@Z; CServiceRecord::SetStatusFlag(ulong)
0x140011968  mov     rcx, cs:WPP_GLOBAL_Control
0x14001196f  lea     rax, WPP_GLOBAL_Control
0x140011976  cmp     rcx, rax
0x140011979  jz      short loc_140011999
0x14001197b  test    byte ptr [rcx+1Ch], 4
0x14001197f  jz      short loc_140011999
0x140011981  mov     rcx, [rcx+10h]
0x140011985  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14001198c  mov     edx, 0A4h
0x140011991  mov     r9, rdi
0x140011994  call    WPP_SF_S
0x140011999  lea     rcx, [rbp+arg_10]; this
0x14001199d  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x1400119a2  mov     rcx, r12; Resource
0x1400119a5  call    cs:__imp_RtlReleaseResource
0x1400119ab  xor     ebx, ebx
0x1400119ad  jmp     loc_140011A4D
0x1400119b2  mov     ebx, 426h
0x1400119b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400119be  lea     rax, WPP_GLOBAL_Control
0x1400119c5  cmp     rcx, rax
0x1400119c8  jz      short loc_1400119EC
0x1400119ca  test    byte ptr [rcx+1Ch], 1
0x1400119ce  jz      short loc_1400119EC
0x1400119d0  mov     rcx, [rcx+10h]
0x1400119d4  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x1400119db  mov     edx, 0A1h
0x1400119e0  mov     [rsp+40h+var_20], ebx
0x1400119e4  mov     r9, rdi
0x1400119e7  call    WPP_SF_Sd
0x1400119ec  test    rsi, rsi
0x1400119ef  jz      short loc_140011A44
0x1400119f1  mov     rcx, rsi; SRWLock
0x1400119f4  mov     dword ptr [rsi+8], 0
0x1400119fb  call    cs:__imp_ReleaseSRWLockExclusive
0x140011a01  jmp     short loc_140011A44
0x140011a03  mov     ebx, 57h ; 'W'
0x140011a08  mov     rcx, cs:WPP_GLOBAL_Control
0x140011a0f  lea     rax, WPP_GLOBAL_Control
0x140011a16  cmp     rcx, rax
0x140011a19  jz      short loc_140011A3B
0x140011a1b  test    byte ptr [rcx+1Ch], 1
0x140011a1f  jz      short loc_140011A3B
0x140011a21  lea     edx, [rbx+49h]
0x140011a24  mov     rcx, [rcx+10h]
0x140011a28  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x140011a2f  mov     r9, rdi
0x140011a32  mov     [rsp+40h+var_20], ebx
0x140011a36  call    WPP_SF_Sd
0x140011a3b  lea     rcx, [rbp+arg_10]; this
0x140011a3f  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x140011a44  mov     rcx, r12; Resource
0x140011a47  call    cs:__imp_RtlReleaseResource
0x140011a4d  mov     rcx, [rbp+TokenHandle]; hObject
0x140011a51  test    rcx, rcx
0x140011a54  jz      short loc_140011A5C
0x140011a56  call    cs:__imp_CloseHandle
0x140011a5c  lea     rcx, [rbp+var_10]
0x140011a60  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x140011a65  mov     eax, ebx
0x140011a67  add     rsp, 40h
0x140011a6b  pop     r12
0x140011a6d  pop     rdi
0x140011a6e  pop     rsi
0x140011a6f  pop     rbx
0x140011a70  pop     rbp
0x140011a71  retn
```
