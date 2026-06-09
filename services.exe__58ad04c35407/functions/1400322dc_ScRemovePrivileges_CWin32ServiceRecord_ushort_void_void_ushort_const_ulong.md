# ScRemovePrivileges(CWin32ServiceRecord *,ushort *,void *,void *,ushort const *,ulong *)

- ea: `0x1400322dc`
- end: `0x140032bda`
- name: `?ScRemovePrivileges@@YAKPEAVCWin32ServiceRecord@@PEAGPEAX2PEBGPEAK@Z`
- size: `2302`
- prototype: `unsigned int __usercall@<eax>(struct CWin32ServiceRecord *this@<rcx>, unsigned __int16 *@<rdx>, void *@<r8>, void *@<r9>, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400381d4`
- `0x14003ae4c`

## callees

- `0x140002890`
- `0x140003310`
- `0x140003e54`
- `0x140004c58`
- `0x140007130`
- `0x14000bebc`
- `0x1400173a0`
- `0x140020cbc`
- `0x14002178c`
- `0x14002575c`
- `0x140027320`
- `0x14002e930`
- `0x140030a5c`
- `0x1400322dc`
- `0x140038648`
- `0x1400575b0`
- `0x140062d1c`
- `0x140064a90`
- `0x140064b54`
- `0x140064c4c`
- `0x14006fee4`
- `0x140092060`
- `0x140092420`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140032379`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140032379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032a47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032a47`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14003288b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14003288b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140032b7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140032b7f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140032a3d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140032a3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140032540`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140032b17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140032540`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140032b17`
- `ntdll!RtlReleaseResource` at `0x140032bb2`
- `ntdll!RtlReleaseResource` at `0x140032bb2`
- `ntdll!RtlAcquireResourceShared` at `0x140032369`
- `ntdll!RtlAcquireResourceShared` at `0x140032369`
- `ntdll!RtlFreeHeap` at `0x1400324f3`
- `ntdll!RtlFreeHeap` at `0x140032b3f`
- `ntdll!RtlFreeHeap` at `0x140032b70`
- `ntdll!RtlFreeHeap` at `0x140032b9c`
- `ntdll!RtlFreeHeap` at `0x1400324f3`
- `ntdll!RtlFreeHeap` at `0x140032b3f`
- `ntdll!RtlFreeHeap` at `0x140032b70`
- `ntdll!RtlFreeHeap` at `0x140032b9c`
- `ntdll!RtlAllocateHeap` at `0x1400324ac`
- `ntdll!RtlAllocateHeap` at `0x1400324ac`

## pseudocode

```c
__int64 __fastcall ScRemovePrivileges(
        struct CWin32ServiceRecord *this,
        unsigned __int16 *a2,
        void *a3,
        void *a4,
        unsigned __int16 *String1,
        unsigned int *a6)
{
  HANDLE v6; // r13
  unsigned int Privileges; // esi
  PTOKEN_PRIVILEGES v10; // r15
  __int64 v11; // rcx
  __int64 v12; // r8
  bool v13; // di
  unsigned int v14; // ebx
  char v15; // al
  __int64 v16; // r13
  PRPC_ASYNC_STATE v17; // rcx
  CServiceRecord *v18; // rbx
  unsigned int IsCohostedService; // eax
  __int64 v20; // r8
  unsigned int v21; // edi
  PVOID Heap; // rax
  void *v23; // rsi
  unsigned __int16 **v24; // rdi
  unsigned __int16 **v25; // rdi
  unsigned int v26; // esi
  PRPC_ASYNC_STATE v27; // rcx
  int v28; // edx
  void *v29; // r13
  int v30; // r8d
  void *v31; // rcx
  unsigned int LastError; // eax
  PRPC_ASYNC_STATE v33; // rcx
  int v34; // edx
  unsigned int TokenInformation; // eax
  __int64 v36; // rbx
  __int64 v37; // rdi
  int v38; // edx
  int v39; // r8d
  __int64 v40; // rcx
  PRPC_ASYNC_STATE v41; // rcx
  __int64 v42; // rbx
  PVOID *v43; // r15
  bool v46; // [rsp+48h] [rbp-B8h]
  unsigned int v47; // [rsp+4Ch] [rbp-B4h]
  CServiceRecord *v48; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v49; // [rsp+58h] [rbp-A8h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  void *Src; // [rsp+68h] [rbp-98h]
  int v52; // [rsp+70h] [rbp-90h] BYREF
  PTOKEN_PRIVILEGES NewState; // [rsp+78h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-80h] BYREF
  HANDLE ProcessHandle; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v56; // [rsp+90h] [rbp-70h]
  unsigned int *v57; // [rsp+98h] [rbp-68h]
  char *v58; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v59[16]; // [rsp+B0h] [rbp-50h] BYREF

  v6 = a3;
  ProcessHandle = a3;
  v56 = String1;
  v57 = a6;
  TokenHandle = a4;
  Privileges = 0;
  memset(v59, 0, 0x78u);
  hKey = 0;
  Src = v59;
  v47 = 0;
  v10 = 0;
  NewState = 0;
  v52 = 0;
  RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
  AcquireSRWLockShared((PSRWLOCK)this + 39);
  v58 = (char *)this + 312;
  v13 = String1 && (unsigned int)ScIsVirtualServiceAccountName(String1);
  v46 = v13;
  if ( (*((_DWORD *)this + 13) & 0x80u) == 0 )
    goto LABEL_107;
  v14 = 0;
  v15 = *((_DWORD *)this + 20) & 0x30;
  v49 = 0;
  if ( v15 != 32 )
  {
    Privileges = CServiceRecord::OpenServiceConfigKey(this, 0x20019u, v12, &hKey);
    if ( Privileges )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          137,
          (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
          *((_QWORD *)this + 7),
          Privileges);
      goto LABEL_107;
    }
    Privileges = ScReadPrivileges(hKey, v59, 0);
    if ( !v59[0] )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          138,
          (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
          *((_QWORD *)this + 7),
          Privileges);
      if ( !Privileges )
        Privileges = 13;
      goto LABEL_107;
    }
    v30 = 1;
    v47 = 1;
LABEL_65:
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      WPP_SF_dSS(
        WPP_GLOBAL_Control->StubInfo,
        139,
        (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
        v30,
        (__int64)a2,
        *((_QWORD *)this + 7));
    v31 = TokenHandle;
    if ( !TokenHandle )
    {
      if ( !OpenProcessToken(v6, 0x28u, &TokenHandle) )
      {
        LastError = GetLastError();
        Privileges = LastError;
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_107;
        }
        v34 = 140;
LABEL_73:
        WPP_SF_SSD(
          v33->StubInfo,
          v34,
          (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
          *((_QWORD *)this + 7),
          (__int64)a2,
          LastError);
LABEL_107:
        v29 = a4;
        goto LABEL_108;
      }
      v31 = TokenHandle;
    }
    TokenInformation = ScGetTokenInformation(v31, TokenPrivileges, (void **)&NewState);
    Privileges = TokenInformation;
    if ( TokenInformation )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_SSD(
          WPP_GLOBAL_Control->StubInfo,
          141,
          (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
          *((_QWORD *)this + 7),
          (__int64)a2,
          TokenInformation);
      v10 = NewState;
      goto LABEL_107;
    }
    v10 = NewState;
    LastError = ScCheckPrivilegesInToken(0, NewState, *((unsigned __int16 **)Src + v14), 0, 0, 0);
    Privileges = LastError;
    if ( LastError )
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_107;
      v34 = 142;
      goto LABEL_73;
    }
    v36 = 0;
    v37 = 0;
    if ( v10->PrivilegeCount )
    {
      do
      {
        if ( (unsigned int)ScIsPrivilegeNeeded(v10->Privileges[v37].Luid, (unsigned __int16 **)Src, v47) )
        {
          v41 = WPP_GLOBAL_Control;
        }
        else
        {
          v40 = v36;
          v10->Privileges[v40].Attributes = 4;
          v10->Privileges[v40].Luid = v10->Privileges[v37].Luid;
          v41 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
          {
            WPP_SF_DSS(
              WPP_GLOBAL_Control->StubInfo,
              v38,
              v39,
              v10->Privileges[v37].Luid.LowPart,
              *((_QWORD *)this + 7),
              (__int64)a2);
            v41 = WPP_GLOBAL_Control;
          }
          v36 = (unsigned int)(v36 + 1);
        }
        v37 = (unsigned int)(v37 + 1);
      }
      while ( (unsigned int)v37 < v10->PrivilegeCount );
      if ( !(_DWORD)v36 )
        goto LABEL_99;
      v10->PrivilegeCount = v36;
      if ( !AdjustTokenPrivileges(TokenHandle, 0, v10, 0, 0, 0) )
      {
        Privileges = GetLastError();
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
        {
          WPP_SF_SSD(
            WPP_GLOBAL_Control->StubInfo,
            144,
            (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
            *((_QWORD *)this + 7),
            (__int64)a2,
            Privileges);
        }
        goto LABEL_107;
      }
      *v57 |= 4u;
    }
    v41 = WPP_GLOBAL_Control;
LABEL_99:
    Privileges = 0;
    if ( v41 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v41->UserInfo) & 4) != 0 )
      WPP_SF_dSS(
        v41->StubInfo,
        145,
        (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
        v36,
        *((_QWORD *)this + 7),
        (__int64)a2);
    goto LABEL_107;
  }
  LODWORD(v16) = 15;
  CServiceDatabase::GetFirst(v11, &v48);
  while ( 1 )
  {
    v18 = v48;
    if ( !v48 )
    {
      Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v48);
      v30 = v47;
      v14 = v49;
      v6 = ProcessHandle;
      goto LABEL_65;
    }
    if ( (*((_DWORD *)v48 + 20) & 0x30) != 0x20 )
      goto LABEL_30;
    IsCohostedService = CWin32ServiceRecord::IsCohostedService(this, a2, v48, &v52);
    if ( IsCohostedService )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
        WPP_SF_SSD(
          WPP_GLOBAL_Control->StubInfo,
          129,
          (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
          *((_QWORD *)this + 7),
          *((_QWORD *)v18 + 7),
          IsCohostedService);
      goto LABEL_30;
    }
    if ( !v52 )
      goto LABEL_30;
    if ( v13 && v18 != this )
    {
      Privileges = 1079;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_SSSD(
          WPP_GLOBAL_Control->StubInfo,
          130,
          (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
          *((_QWORD *)v18 + 7),
          *((_QWORD *)this + 7),
          (__int64)v56,
          55);
      goto LABEL_34;
    }
    if ( (*((_DWORD *)v18 + 13) & 0x80u) == 0 )
      break;
    v21 = v47;
    if ( (_DWORD)v16 == v47 )
    {
      if ( (unsigned int)v16 > 0x7FFFFFFF )
      {
        Privileges = 84;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_dSSD(
            WPP_GLOBAL_Control->StubInfo,
            133,
            (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
            v16,
            (__int64)a2,
            *((_QWORD *)this + 7),
            84);
        }
        goto LABEL_34;
      }
      v16 = (unsigned int)(2 * v16);
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 8 * v16);
      v23 = Heap;
      if ( !Heap )
      {
        Privileges = 8;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 134, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, 8);
        }
        goto LABEL_34;
      }
      v24 = (unsigned __int16 **)Src;
      memmove(Heap, Src, 8 * ((unsigned __int64)(unsigned int)v16 >> 1));
      if ( v24 != v59 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
      v21 = v47;
      Src = v23;
    }
    Privileges = CServiceRecord::OpenServiceConfigKey(v18, 0x20019u, v20, &hKey);
    if ( Privileges )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        v28 = 135;
LABEL_46:
        WPP_SF_Sd(
          v27->StubInfo,
          v28,
          (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
          *((_QWORD *)v18 + 7),
          Privileges);
      }
LABEL_34:
      Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v48);
      goto LABEL_107;
    }
    v25 = (unsigned __int16 **)((char *)Src + 8 * v21);
    Privileges = ScReadPrivileges(hKey, v25, 0);
    RegCloseKey(hKey);
    hKey = 0;
    if ( !*v25 )
    {
      if ( this != v18 )
        goto LABEL_30;
      if ( !Privileges )
        Privileges = 13;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        v28 = 136;
        goto LABEL_46;
      }
      goto LABEL_34;
    }
    v26 = v49;
    if ( this == v18 )
      v26 = v47;
    ++v47;
    v49 = v26;
LABEL_30:
    CServiceDatabase::GetNext((__int64)v17, &v48);
    v13 = v46;
  }
  v29 = a4;
  Privileges = ScCheckPrivilegesInToken(this, 0, 0, a4, ProcessHandle, 0);
  if ( Privileges )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_SSD(
        WPP_GLOBAL_Control->StubInfo,
        131,
        (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
        *((_QWORD *)this + 7),
        (__int64)a2,
        Privileges);
  }
  else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
         && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
  {
    WPP_SF_SSS(
      WPP_GLOBAL_Control->StubInfo,
      132,
      (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
      *((_QWORD *)v18 + 7),
      *((_QWORD *)this + 7),
      (__int64)a2);
  }
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v48);
LABEL_108:
  if ( hKey )
    RegCloseKey(hKey);
  v42 = 0;
  if ( v47 )
  {
    v43 = (PVOID *)Src;
    do
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v43[v42]);
      v42 = (unsigned int)(v42 + 1);
    }
    while ( (unsigned int)v42 < v47 );
    v10 = NewState;
  }
  if ( Src != v59 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Src);
  if ( TokenHandle != v29 )
    CloseHandle(TokenHandle);
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v58);
  RtlReleaseResource(&ScServiceRecordLock);
  return Privileges;
}

```

## disassembly

```asm
0x1400322dc  push    rbp
0x1400322de  push    rbx
0x1400322df  push    rsi
0x1400322e0  push    rdi
0x1400322e1  push    r12
0x1400322e3  push    r13
0x1400322e5  push    r14
0x1400322e7  push    r15
0x1400322e9  lea     rbp, [rsp-48h]
0x1400322ee  sub     rsp, 148h
0x1400322f5  mov     rax, cs:__security_cookie
0x1400322fc  xor     rax, rsp
0x1400322ff  mov     [rbp+80h+var_50], rax
0x140032303  mov     rax, [rbp+80h+arg_28]
0x14003230a  xor     ebx, ebx
0x14003230c  mov     rdi, [rbp+80h+String1]
0x140032313  mov     r13, r8
0x140032316  mov     [rbp+80h+ProcessHandle], r8
0x14003231a  mov     r12, rdx
0x14003231d  mov     r14, rcx
0x140032320  mov     [rsp+180h+var_140], r9
0x140032325  lea     r8d, [rbx+78h]; Size
0x140032329  mov     [rbp+80h+var_F0], rdi
0x14003232d  xor     edx, edx; Val
0x14003232f  mov     [rbp+80h+var_E8], rax
0x140032333  lea     rcx, [rbp+80h+var_D0]; void *
0x140032337  mov     [rbp+80h+TokenHandle], r9
0x14003233b  mov     esi, ebx
0x14003233d  call    memset
0x140032342  lea     rax, [rbp+80h+var_D0]
0x140032346  mov     [rsp+180h+hKey], rbx
0x14003234b  mov     dl, 1; Wait
0x14003234d  mov     [rsp+180h+Src], rax
0x140032352  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140032359  mov     [rsp+180h+var_134], ebx
0x14003235d  mov     r15d, ebx
0x140032360  mov     [rsp+180h+NewState], rbx
0x140032365  mov     [rsp+180h+var_110], ebx
0x140032369  call    cs:__imp_RtlAcquireResourceShared
0x14003236f  lea     rbx, [r14+138h]
0x140032376  mov     rcx, rbx; SRWLock
0x140032379  call    cs:__imp_AcquireSRWLockShared
0x14003237f  mov     [rbp+80h+var_E0], rbx
0x140032383  test    rdi, rdi
0x140032386  jz      short loc_140032399
0x140032388  mov     rcx, rdi; String1
0x14003238b  call    ?ScIsVirtualServiceAccountName@@YAHPEBG@Z; ScIsVirtualServiceAccountName(ushort const *)
0x140032390  test    eax, eax
0x140032392  jz      short loc_140032399
0x140032394  mov     dil, 1
0x140032397  jmp     short loc_14003239C
0x140032399  xor     dil, dil
0x14003239c  mov     eax, [r14+34h]
0x1400323a0  mov     [rsp+180h+var_138], dil
0x1400323a5  test    al, al
0x1400323a7  jns     loc_140032B08
0x1400323ad  mov     eax, [r14+50h]
0x1400323b1  lea     rsi, WPP_GLOBAL_Control
0x1400323b8  xor     ebx, ebx
0x1400323ba  and     al, 30h
0x1400323bc  mov     [rsp+180h+var_128], ebx
0x1400323c0  cmp     al, 20h ; ' '
0x1400323c2  jnz     loc_1400327B6
0x1400323c8  lea     rdx, [rsp+180h+var_130]
0x1400323cd  lea     r13d, [rbx+0Fh]
0x1400323d1  call    ?GetFirst@CServiceDatabase@@QEAA?AV?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@XZ; CServiceDatabase::GetFirst(void)
0x1400323d6  mov     rbx, [rsp+180h+var_130]
0x1400323db  test    rbx, rbx
0x1400323de  jz      loc_14003279A
0x1400323e4  mov     eax, [rbx+50h]
0x1400323e7  and     al, 30h
0x1400323e9  cmp     al, 20h ; ' '
0x1400323eb  jnz     loc_14003257A
0x1400323f1  lea     r9, [rsp+180h+var_110]; int *
0x1400323f6  mov     r8, rbx; struct CWin32ServiceRecord *
0x1400323f9  mov     rdx, r12; unsigned __int16 *
0x1400323fc  mov     rcx, r14; this
0x1400323ff  call    ?IsCohostedService@CWin32ServiceRecord@@QEAAKPEBGPEAV1@PEAH@Z; CWin32ServiceRecord::IsCohostedService(ushort const *,CWin32ServiceRecord *,int *)
0x140032404  test    eax, eax
0x140032406  jz      short loc_14003244D
0x140032408  mov     rcx, cs:WPP_GLOBAL_Control
0x14003240f  cmp     rcx, rsi
0x140032412  jz      loc_14003257A
0x140032418  test    byte ptr [rcx+1Ch], 2
0x14003241c  jz      loc_14003257A
0x140032422  mov     r9, [r14+38h]
0x140032426  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x14003242d  mov     rcx, [rcx+10h]
0x140032431  mov     edx, 81h
0x140032436  mov     dword ptr [rsp+180h+ReturnLength], eax
0x14003243a  mov     rax, [rbx+38h]
0x14003243e  mov     [rsp+180h+PreviousState], rax
0x140032443  call    WPP_SF_SSD
0x140032448  jmp     loc_14003257A
0x14003244d  cmp     [rsp+180h+var_110], r15d
0x140032452  jz      loc_14003257A
0x140032458  cmp     dil, 1
0x14003245c  jnz     short loc_140032467
0x14003245e  cmp     rbx, r14
0x140032461  jnz     loc_14003258E
0x140032467  mov     eax, [rbx+34h]
0x14003246a  test    al, al
0x14003246c  jns     loc_1400326E5
0x140032472  mov     edi, [rsp+180h+var_134]
0x140032476  cmp     r13d, edi
0x140032479  jnz     loc_140032502
0x14003247f  cmp     r13d, 7FFFFFFFh
0x140032486  ja      loc_140032625
0x14003248c  mov     rcx, gs:60h
0x140032495  add     r13d, r13d
0x140032498  mov     edx, 8; Flags
0x14003249d  mov     edi, r13d
0x1400324a0  mov     rcx, [rcx+30h]; HeapHandle
0x1400324a4  lea     r8, ds:0[r13*8]; Size
0x1400324ac  call    cs:__imp_RtlAllocateHeap
0x1400324b2  mov     rsi, rax
0x1400324b5  test    rax, rax
0x1400324b8  jz      loc_1400325EA
0x1400324be  shr     rdi, 1
0x1400324c1  mov     rcx, rax; void *
0x1400324c4  shl     rdi, 3
0x1400324c8  mov     r8, rdi; Size
0x1400324cb  mov     rdi, [rsp+180h+Src]
0x1400324d0  mov     rdx, rdi; Src
0x1400324d3  call    memmove
0x1400324d8  lea     rax, [rbp+80h+var_D0]
0x1400324dc  cmp     rdi, rax
0x1400324df  jz      short loc_1400324F9
0x1400324e1  mov     rcx, gs:60h
0x1400324ea  mov     r8, rdi; P
0x1400324ed  xor     edx, edx; Flags
0x1400324ef  mov     rcx, [rcx+30h]; HeapHandle
0x1400324f3  call    cs:__imp_RtlFreeHeap
0x1400324f9  mov     edi, [rsp+180h+var_134]
0x1400324fd  mov     [rsp+180h+Src], rsi
0x140032502  lea     r9, [rsp+180h+hKey]; HKEY *
0x140032507  mov     edx, 20019h; unsigned int
0x14003250c  mov     rcx, rbx; this
0x14003250f  call    ?OpenServiceConfigKey@CServiceRecord@@QEAAKKHPEAPEAUHKEY__@@@Z; CServiceRecord::OpenServiceConfigKey(ulong,int,HKEY__ * *)
0x140032514  mov     esi, eax
0x140032516  test    eax, eax
0x140032518  jnz     loc_1400326BD
0x14003251e  mov     rcx, [rsp+180h+Src]
0x140032523  xor     r8d, r8d; unsigned int *
0x140032526  mov     eax, edi
0x140032528  lea     rdi, [rcx+rax*8]
0x14003252c  mov     rcx, [rsp+180h+hKey]; HKEY
0x140032531  mov     rdx, rdi; unsigned __int16 **
0x140032534  call    ?ScReadPrivileges@@YAKPEAUHKEY__@@PEAPEAGPEAK@Z; ScReadPrivileges(HKEY__ *,ushort * *,ulong *)
0x140032539  mov     rcx, [rsp+180h+hKey]; hKey
0x14003253e  mov     esi, eax
0x140032540  call    cs:__imp_RegCloseKey
0x140032546  mov     [rsp+180h+hKey], r15
0x14003254b  cmp     [rdi], r15
0x14003254e  jz      short loc_14003256A
0x140032550  mov     eax, [rsp+180h+var_134]
0x140032554  cmp     r14, rbx
0x140032557  mov     esi, [rsp+180h+var_128]
0x14003255b  cmovz   esi, eax
0x14003255e  inc     eax
0x140032560  mov     [rsp+180h+var_134], eax
0x140032564  mov     [rsp+180h+var_128], esi
0x140032568  jmp     short loc_140032573
0x14003256a  cmp     r14, rbx
0x14003256d  jz      loc_140032670
0x140032573  lea     rsi, WPP_GLOBAL_Control
0x14003257a  lea     rdx, [rsp+180h+var_130]
0x14003257f  call    ?GetNext@CServiceDatabase@@QEAAXAEAV?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@Z; CServiceDatabase::GetNext(Microsoft::WRL::ComPtr<CServiceRecord> &)
0x140032584  mov     dil, [rsp+180h+var_138]
0x140032589  jmp     loc_1400323D6
0x14003258e  mov     esi, 437h
0x140032593  mov     rcx, cs:WPP_GLOBAL_Control
0x14003259a  lea     rax, WPP_GLOBAL_Control
0x1400325a1  cmp     rcx, rax
0x1400325a4  jz      short loc_1400325DB
0x1400325a6  test    byte ptr [rcx+1Ch], 1
0x1400325aa  jz      short loc_1400325DB
0x1400325ac  mov     rax, [rbp+80h+var_F0]
0x1400325b0  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x1400325b7  mov     r9, [rbx+38h]
0x1400325bb  mov     edx, 82h
0x1400325c0  mov     rcx, [rcx+10h]
0x1400325c4  mov     [rsp+180h+var_150], esi
0x1400325c8  mov     [rsp+180h+ReturnLength], rax
0x1400325cd  mov     rax, [r14+38h]
0x1400325d1  mov     [rsp+180h+PreviousState], rax
0x1400325d6  call    WPP_SF_SSSD
0x1400325db  lea     rcx, [rsp+180h+var_130]
0x1400325e0  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x1400325e5  jmp     loc_140032B08
0x1400325ea  mov     r8d, 8
0x1400325f0  mov     esi, r8d
0x1400325f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400325fa  lea     rax, WPP_GLOBAL_Control
0x140032601  cmp     rcx, rax
0x140032604  jz      short loc_1400325DB
0x140032606  test    byte ptr [rcx+1Ch], 1
0x14003260a  jz      short loc_1400325DB
0x14003260c  mov     rcx, [rcx+10h]
0x140032610  lea     edx, [r8+7Eh]
0x140032614  mov     r9d, r8d
0x140032617  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x14003261e  call    WPP_SF_d
0x140032623  jmp     short loc_1400325DB
0x140032625  mov     esi, 54h ; 'T'
0x14003262a  mov     rcx, cs:WPP_GLOBAL_Control
0x140032631  lea     rax, WPP_GLOBAL_Control
0x140032638  cmp     rcx, rax
0x14003263b  jz      short loc_1400325DB
0x14003263d  test    byte ptr [rcx+1Ch], 1
0x140032641  jz      short loc_1400325DB
0x140032643  mov     rax, [r14+38h]
0x140032647  lea     edx, [rsi+31h]
0x14003264a  mov     rcx, [rcx+10h]
0x14003264e  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140032655  mov     [rsp+180h+var_150], esi
0x140032659  mov     r9d, r13d
0x14003265c  mov     [rsp+180h+ReturnLength], rax
0x140032661  mov     [rsp+180h+PreviousState], r12
0x140032666  call    WPP_SF_dSSD
0x14003266b  jmp     loc_1400325DB
0x140032670  test    esi, esi
0x140032672  mov     eax, 0Dh
0x140032677  cmovz   esi, eax
0x14003267a  mov     rcx, cs:WPP_GLOBAL_Control
0x140032681  lea     rax, WPP_GLOBAL_Control
0x140032688  cmp     rcx, rax
0x14003268b  jz      loc_1400325DB
0x140032691  test    byte ptr [rcx+1Ch], 1
0x140032695  jz      loc_1400325DB
0x14003269b  mov     edx, 88h
0x1400326a0  mov     r9, [rbx+38h]
0x1400326a4  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x1400326ab  mov     rcx, [rcx+10h]
0x1400326af  mov     dword ptr [rsp+180h+PreviousState], esi
0x1400326b3  call    WPP_SF_Sd
0x1400326b8  jmp     loc_1400325DB
0x1400326bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400326c4  lea     rax, WPP_GLOBAL_Control
0x1400326cb  cmp     rcx, rax
0x1400326ce  jz      loc_1400325DB
0x1400326d4  test    byte ptr [rcx+1Ch], 1
0x1400326d8  jz      loc_1400325DB
0x1400326de  mov     edx, 87h
0x1400326e3  jmp     short loc_1400326A0
0x1400326e5  mov     rax, [rbp+80h+ProcessHandle]
0x1400326e9  xor     r8d, r8d; unsigned __int16 *
0x1400326ec  mov     r13, [rsp+180h+var_140]
0x1400326f1  xor     edx, edx; struct _TOKEN_PRIVILEGES *
0x1400326f3  mov     r9, r13; void *
0x1400326f6  mov     dword ptr [rsp+180h+ReturnLength], r15d; unsigned int
0x1400326fb  mov     rcx, r14; struct CServiceRecord *
0x1400326fe  mov     [rsp+180h+PreviousState], rax; void *
0x140032703  call    ?ScCheckPrivilegesInToken@@YAKPEAVCServiceRecord@@PEAU_TOKEN_PRIVILEGES@@PEAGPEAX3K@Z; ScCheckPrivilegesInToken(CServiceRecord *,_TOKEN_PRIVILEGES *,ushort *,void *,void *,ulong)
0x140032708  mov     esi, eax
0x14003270a  test    eax, eax
0x14003270c  jz      short loc_14003274B
0x14003270e  mov     rcx, cs:WPP_GLOBAL_Control
0x140032715  lea     rax, WPP_GLOBAL_Control
0x14003271c  cmp     rcx, rax
0x14003271f  jz      short loc_14003278B
0x140032721  test    byte ptr [rcx+1Ch], 1
0x140032725  jz      short loc_14003278B
0x140032727  mov     r9, [r14+38h]
0x14003272b  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140032732  mov     rcx, [rcx+10h]
0x140032736  mov     edx, 83h
0x14003273b  mov     dword ptr [rsp+180h+ReturnLength], esi
0x14003273f  mov     [rsp+180h+PreviousState], r12
0x140032744  call    WPP_SF_SSD
0x140032749  jmp     short loc_14003278B
0x14003274b  mov     rcx, cs:WPP_GLOBAL_Control
0x140032752  lea     rax, WPP_GLOBAL_Control
0x140032759  cmp     rcx, rax
0x14003275c  jz      short loc_14003278B
0x14003275e  test    byte ptr [rcx+1Ch], 4
0x140032762  jz      short loc_14003278B
0x140032764  mov     rax, [r14+38h]
0x140032768  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x14003276f  mov     r9, [rbx+38h]
0x140032773  mov     edx, 84h
0x140032778  mov     rcx, [rcx+10h]
0x14003277c  mov     [rsp+180h+ReturnLength], r12
0x140032781  mov     [rsp+180h+PreviousState], rax
0x140032786  call    WPP_SF_SSS
0x14003278b  lea     rcx, [rsp+180h+var_130]
0x140032790  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x140032795  jmp     loc_140032B0D
0x14003279a  lea     rcx, [rsp+180h+var_130]
0x14003279f  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x1400327a4  mov     r8d, [rsp+180h+var_134]
0x1400327a9  mov     ebx, [rsp+180h+var_128]
0x1400327ad  mov     r13, [rbp+80h+ProcessHandle]
0x1400327b1  jmp     loc_140032839
0x1400327b6  lea     r9, [rsp+180h+hKey]; HKEY *
0x1400327bb  mov     edx, 20019h; unsigned int
0x1400327c0  mov     rcx, r14; this
0x1400327c3  call    ?OpenServiceConfigKey@CServiceRecord@@QEAAKKHPEAPEAUHKEY__@@@Z; CServiceRecord::OpenServiceConfigKey(ulong,int,HKEY__ * *)
0x1400327c8  mov     esi, eax
0x1400327ca  test    eax, eax
  ... truncated ...
```
