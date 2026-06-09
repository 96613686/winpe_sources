# RQueryServiceConfig2W

- ea: `0x14000a050`
- end: `0x14000ab40`
- name: `RQueryServiceConfig2W`
- size: `2800`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140009240`

## callees

- `0x140002890`
- `0x140003e54`
- `0x140004c58`
- `0x14000a050`
- `0x14000ae84`
- `0x14000c120`
- `0x14000c220`
- `0x14000c8f0`
- `0x14000cee0`
- `0x140013b0c`
- `0x140014dec`
- `0x14001a230`
- `0x14001f99c`
- `0x14002178c`
- `0x140030238`
- `0x140042c90`
- `0x14004401c`
- `0x1400575b0`
- `0x14007b7dc`
- `0x140092420`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000a1eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000a1eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000aad3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000aad3`
- `RPCRT4!RpcBindingFree` at `0x14000a11d`
- `RPCRT4!RpcBindingFree` at `0x14000a11d`
- `RPCRT4!RpcServerInqCallAttributesA` at `0x14000a0e8`
- `RPCRT4!RpcServerInqCallAttributesA` at `0x14000a0e8`
- `RPCRT4!RpcStringFreeW` at `0x14000a10a`
- `RPCRT4!RpcStringFreeW` at `0x14000a10a`
- `RPCRT4!RpcImpersonateClient` at `0x14000a91f`
- `RPCRT4!RpcImpersonateClient` at `0x14000a91f`
- `RPCRT4!RpcRevertToSelf` at `0x14000a967`
- `RPCRT4!RpcRevertToSelf` at `0x14000a967`
- `ntdll!RtlReleaseResource` at `0x14000a467`
- `ntdll!RtlReleaseResource` at `0x14000a467`
- `ntdll!RtlAcquireResourceShared` at `0x14000a1d7`
- `ntdll!RtlAcquireResourceShared` at `0x14000a1d7`
- `ntdll!RtlAreAllAccessesGranted` at `0x14000a1b9`
- `ntdll!RtlAreAllAccessesGranted` at `0x14000a1b9`
- `ntdll!NtClose` at `0x14000aab9`
- `ntdll!NtClose` at `0x14000aab9`
- `ntdll!RtlNtStatusToDosError` at `0x14000a411`
- `ntdll!RtlNtStatusToDosError` at `0x14000aac1`
- `ntdll!RtlNtStatusToDosError` at `0x14000a411`
- `ntdll!RtlNtStatusToDosError` at `0x14000aac1`
- `ntdll!RtlInitUnicodeString` at `0x14000a30d`
- `ntdll!RtlInitUnicodeString` at `0x14000a30d`
- `ntdll!RtlFreeHeap` at `0x14000a390`
- `ntdll!RtlFreeHeap` at `0x14000a407`
- `ntdll!RtlFreeHeap` at `0x14000a549`
- `ntdll!RtlFreeHeap` at `0x14000a9d0`
- `ntdll!RtlFreeHeap` at `0x14000aa34`
- `ntdll!RtlFreeHeap` at `0x14000aaae`
- `ntdll!RtlFreeHeap` at `0x14000a390`
- `ntdll!RtlFreeHeap` at `0x14000a407`
- `ntdll!RtlFreeHeap` at `0x14000a549`
- `ntdll!RtlFreeHeap` at `0x14000a9d0`
- `ntdll!RtlFreeHeap` at `0x14000aa34`
- `ntdll!RtlFreeHeap` at `0x14000aaae`
- `ntdll!NtOpenKey` at `0x14000a34b`
- `ntdll!NtOpenKey` at `0x14000a3aa`
- `ntdll!NtOpenKey` at `0x14000a34b`
- `ntdll!NtOpenKey` at `0x14000a3aa`
- `ntdll!RtlAllocateHeap` at `0x14000a26d`
- `ntdll!RtlAllocateHeap` at `0x14000a26d`

## string_xrefs

- `0x14000a561`: `FailureCommand`
- `0x14000a2c5`: `\REGISTRY\MACHINE\`

## pseudocode

```c
__int64 __fastcall RQueryServiceConfig2W(__int64 a1, int a2, __int64 a3, unsigned int a4, unsigned int *a5)
{
  int v8; // edi
  unsigned __int16 v9; // ax
  unsigned __int16 v10; // cx
  __int64 *v12; // r13
  RTL_SRWLOCK *v13; // rdi
  __int64 v14; // rax
  __int64 v15; // r15
  void *v16; // rcx
  __int64 v17; // rax
  bool v18; // zf
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v20; // r14
  PRPC_ASYNC_STATE v21; // rcx
  ULONG FailureActions; // r14d
  NTSTATUS v23; // eax
  _DWORD *v24; // rbx
  RTL_SRWLOCK v25; // rax
  unsigned __int16 v26; // ax
  int v27; // esi
  unsigned int v28; // esi
  unsigned int v29; // esi
  RPC_WSTR v30; // rdx
  __int64 v31; // rbx
  int v32; // ebx
  _WORD *v33; // rdx
  HKEY v34; // rcx
  struct _PEB *v35; // rcx
  RPC_WSTR v36; // r8
  int v37; // eax
  __int16 v38; // ax
  RTL_SRWLOCK v39; // rax
  __int16 v40; // ax
  HKEY v41; // r13
  unsigned int v42; // eax
  RPC_STATUS v43; // eax
  unsigned int v44; // r13d
  _DWORD *v45; // r13
  __int64 v46; // rcx
  __int64 v47; // rax
  NTSTATUS v48; // eax
  RPC_WSTR String; // [rsp+30h] [rbp-D0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-C8h] BYREF
  int v51; // [rsp+40h] [rbp-C0h]
  PVOID P; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v54; // [rsp+58h] [rbp-A8h]
  void *Src; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v56; // [rsp+68h] [rbp-98h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v60; // [rsp+B8h] [rbp-48h]
  __int128 v61; // [rsp+C8h] [rbp-38h]
  __int128 v62; // [rsp+D8h] [rbp-28h]
  __int128 v63; // [rsp+E8h] [rbp-18h]
  __int128 v64; // [rsp+F8h] [rbp-8h]
  __int128 v65; // [rsp+108h] [rbp+8h]
  __int128 v66; // [rsp+118h] [rbp+18h]

  v54 = a4;
  LODWORD(P) = a2;
  if ( s_pfnI_RpcServerTurnOnOffKeepalives )
  {
    String = 0;
    Binding = 0;
    RpcCallAttributes[0] = 3;
    v60 = 0;
    v8 = 0;
    RpcCallAttributes[1] = 64;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    if ( !RpcServerInqCallAttributesA(0, RpcCallAttributes) )
    {
      LOBYTE(v8) = (_DWORD)v63 == 1;
      if ( v8 == 1 )
      {
        v9 = *((_WORD *)&g_dwRpcOverTcpKeepAliveTimes + 1);
        v10 = *(_WORD *)&g_dwRpcOverTcpKeepAliveTimes;
        if ( *(_WORD *)&g_dwRpcOverTcpKeepAliveTimes < 5u )
          v10 = 5;
        if ( *((_WORD *)&g_dwRpcOverTcpKeepAliveTimes + 1) < 5u )
          v9 = 5;
        ((void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))s_pfnI_RpcServerTurnOnOffKeepalives)(
          0,
          1,
          60000 * (unsigned int)v10,
          1000 * (unsigned int)v9);
      }
    }
  }
  if ( ScShutdownInProgress )
    return 1115;
  if ( !a1 || *(_DWORD *)a1 != 1215456627 )
    return 6;
  if ( a3 && a5 )
  {
    if ( !RtlAreAllAccessesGranted(*(_DWORD *)(a1 + 8), 1u) )
      return 5;
    *a5 = 0;
    RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
    v12 = *(__int64 **)(a1 + 16);
    v13 = (RTL_SRWLOCK *)(v12 + 39);
    AcquireSRWLockShared((PSRWLOCK)v12 + 39);
    KeyHandle = 0;
    v14 = v12[27];
    v15 = -1;
    v16 = (void *)v12[7];
    v56 = v12 + 39;
    Src = v16;
    Binding = *(RPC_BINDING_HANDLE *)(v14 + 32);
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    DestinationString = 0;
    if ( Binding == (RPC_BINDING_HANDLE)-2147483646LL )
    {
      v17 = -1;
      do
        v18 = *((_WORD *)v16 + ++v17) == 0;
      while ( !v18 );
      Binding = (RPC_BINDING_HANDLE)(unsigned int)(2 * v17 + 40);
      Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Binding);
      String = Heap;
      v20 = Heap;
      if ( !Heap )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->StubInfo, 111, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
          v21 = WPP_GLOBAL_Control;
        }
        FailureActions = 8;
        goto LABEL_40;
      }
      v51 = 1;
      StringCbCopyW(Heap, (unsigned __int64)Binding, L"\\REGISTRY\\MACHINE\\");
      StringCbCatW(v20, (unsigned __int64)Binding, (const unsigned __int16 *)Src);
      Binding = 0;
    }
    else
    {
      v51 = 0;
      v20 = (unsigned __int16 *)v16;
      String = (RPC_WSTR)v16;
    }
    RtlInitUnicodeString(&DestinationString, v20);
    ObjectAttributes.RootDirectory = Binding;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    LODWORD(Binding) = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( (_DWORD)Binding == -1073741790 )
    {
      FailureActions = ScTakeOwnership(&ObjectAttributes);
      if ( FailureActions )
      {
        if ( v51 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, String);
LABEL_39:
        v21 = WPP_GLOBAL_Control;
LABEL_40:
        if ( v21 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v21->UserInfo) & 1) != 0 )
          WPP_SF_Sd(
            v21->StubInfo,
            39,
            (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
            (_DWORD)Src,
            FailureActions);
        Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v56);
LABEL_44:
        RtlReleaseResource(&ScServiceRecordLock);
        return FailureActions;
      }
      v23 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
      LODWORD(Binding) = v23;
      if ( v23 < 0
        && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 112, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, (unsigned int)v23);
      }
      v20 = String;
    }
    if ( v51 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
    FailureActions = RtlNtStatusToDosError((NTSTATUS)Binding);
    if ( FailureActions )
      goto LABEL_39;
    if ( (_DWORD)P != 1 )
    {
      if ( (_DWORD)P == 3 )
      {
        *a5 = 4;
        if ( a4 >= 4 )
        {
          *(_DWORD *)a3 = (*((_DWORD *)v12 + 13) >> 3) & 1;
          FailureActions = 0;
        }
        else
        {
          FailureActions = 122;
        }
      }
      else
      {
        switch ( (int)P )
        {
          case 2:
            P = 0;
            FailureActions = ScReadFailureActions((HKEY)KeyHandle, (struct _SERVICE_FAILURE_ACTIONS_WOW64 **)&P, a5);
            if ( FailureActions )
            {
              CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>::~CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>(&P);
              goto LABEL_135;
            }
            v24 = P;
            if ( !P )
              *a5 = 20;
            v25.Ptr = (PVOID)*v12;
            String = 0;
            v26 = (*((__int64 (__fastcall **)(__int64 *))v25.Ptr + 6))(v12);
            FailureActions = ScReadAndTranslateString((HKEY)KeyHandle, L"RebootMessage", 1, v26, &String, a5);
            if ( FailureActions )
            {
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, String);
              goto LABEL_133;
            }
            Binding = 0;
            FailureActions = ScReadOptionalString((HKEY)KeyHandle, L"FailureCommand", (unsigned __int16 **)&Binding, a5);
            if ( FailureActions )
              goto LABEL_55;
            if ( v54 < *a5 )
            {
              FailureActions = 122;
              goto LABEL_55;
            }
            if ( v24 )
            {
              *(_DWORD *)a3 = *v24;
              v27 = v24[3];
              *(_DWORD *)(a3 + 12) = v27;
              if ( v27 )
              {
                v28 = 8 * v27;
                *(_DWORD *)(a3 + 16) = 20;
                memmove((void *)(a3 + 20), v24 + 5, v28);
                v29 = v28 + 20;
                goto LABEL_63;
              }
            }
            else
            {
              *(_DWORD *)a3 = 0;
              *(_DWORD *)(a3 + 12) = 0;
            }
            v29 = 20;
            *(_DWORD *)(a3 + 16) = 0;
LABEL_63:
            v30 = String;
            if ( String )
            {
              *(_DWORD *)(a3 + 4) = v29;
              v31 = -1;
              do
                ++v31;
              while ( v30[v31] );
              v32 = 2 * v31;
              memmove((void *)(a3 + v29), v30, (unsigned int)(v32 + 2));
              v29 += v32 + 2;
            }
            else
            {
              *(_DWORD *)(a3 + 4) = 0;
            }
            v33 = Binding;
            if ( Binding )
            {
              *(_DWORD *)(a3 + 8) = v29;
              do
                v18 = v33[++v15] == 0;
              while ( !v18 );
              memmove((void *)(a3 + v29), v33, (unsigned int)(2 * v15 + 2));
            }
            else
            {
              *(_DWORD *)(a3 + 8) = 0;
            }
LABEL_55:
            CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>::~CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>(&Binding);
            CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>::~CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>((PVOID *)&String);
            CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>::~CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>(&P);
            break;
          case 4:
            *a5 = 4;
            if ( a4 >= 4 )
            {
              *(_DWORD *)a3 = (*((_DWORD *)v12 + 13) >> 5) & 1;
              FailureActions = 0;
            }
            else
            {
              FailureActions = 122;
            }
            goto LABEL_135;
          case 5:
            *a5 = 4;
            if ( a4 >= 4 )
            {
              *(_DWORD *)a3 = (*((_DWORD *)v12 + 13) >> 6) & 1;
              v37 = 3;
              if ( (*((_DWORD *)v12 + 13) & 0x100) == 0 )
                v37 = *(_DWORD *)a3;
              *(_DWORD *)a3 = v37;
              FailureActions = 0;
            }
            else
            {
              FailureActions = 122;
            }
            goto LABEL_135;
          case 6:
            v34 = (HKEY)KeyHandle;
            *a5 = 4;
            String = 0;
            FailureActions = ScReadPrivileges(v34, &String, a5);
            if ( FailureActions )
            {
              v35 = NtCurrentPeb();
              v36 = String;
              goto LABEL_134;
            }
            if ( a4 < *a5 )
            {
              v35 = NtCurrentPeb();
              FailureActions = 122;
              v36 = String;
              goto LABEL_134;
            }
            v24 = String;
            if ( String )
            {
              *(_DWORD *)a3 = 4;
              memmove((void *)(a3 + 4), v24, *a5 - 4);
            }
            else
            {
              *(_DWORD *)a3 = 0;
            }
            goto LABEL_133;
          case 7:
            *a5 = 4;
            if ( a4 >= 4 )
              FailureActions = ScReadPreshutdownTimeout(
                                 (struct _SERVICE_CONFIG_ROOT *)v12[27],
                                 (unsigned __int16 *)v12[7],
                                 (unsigned int *)a3);
            else
              FailureActions = 122;
            goto LABEL_135;
          case 9:
            if ( (v12[10] & 0x20) != 0 || !(*(unsigned __int16 (__fastcall **)(__int64 *))(*v12 + 128))(v12) )
            {
              FailureActions = 87;
            }
            else
            {
              *a5 = 4;
              if ( a4 >= 4 )
              {
                v38 = (*(__int64 (__fastcall **)(__int64 *))(*v12 + 128))(v12);
                *(_BYTE *)(a3 + 2) = 0;
                *(_WORD *)a3 = v38 - 1;
                FailureActions = 0;
              }
              else
              {
                FailureActions = 122;
              }
            }
            goto LABEL_135;
          case 11:
            *a5 = 1;
            if ( a4 )
            {
              FailureActions = 0;
              *(_BYTE *)a3 = (*(unsigned int (__fastcall **)(__int64 *))(*v12 + 216))(v12) == 1;
            }
            else
            {
              FailureActions = 122;
            }
            goto LABEL_135;
          case 12:
            *a5 = 4;
            if ( a4 >= 4 )
            {
              *(_DWORD *)a3 = (*(__int64 (__fastcall **)(__int64 *))(*v12 + 224))(v12);
              FailureActions = 0;
            }
            else
            {
              FailureActions = 122;
            }
            goto LABEL_135;
          default:
            FailureActions = 124;
            goto LABEL_135;
        }
      }
      goto LABEL_135;
    }
    *a5 = 4;
    v39.Ptr = (PVOID)*v12;
    String = 0;
    v40 = (*((__int64 (__fastcall **)(__int64 *))v39.Ptr + 6))(v12);
    v41 = (HKEY)KeyHandle;
    LOWORD(v51) = v40;
    Src = 0;
    v42 = ScReadOptionalString((HKEY)KeyHandle, L"Description", &String, a5);
    v24 = String;
    FailureActions = v42;
    if ( v42 || !(unsigned int)ScIsIndirectString(String, 0) )
      goto LABEL_126;
    v43 = RpcImpersonateClient(0);
    FailureActions = v43;
    if ( v43 )
    {
      ScLogImpersonateFailureEvent(v43);
      CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>::~CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>((PVOID *)&String);
      goto LABEL_135;
    }
    FailureActions = ScReadStringIndirect(v41, L"Description", (unsigned __int16 *)v24, v51, (unsigned __int16 **)&Src);
    v44 = RpcRevertToSelf();
    if ( v44 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 194, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, v44);
      ScLogEvent(5u, L"RpcRevertToSelf", v44);
    }
    if ( FailureActions )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
      String = 0;
      CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>::~CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>((PVOID *)&String);
      goto LABEL_135;
    }
    v45 = Src;
    if ( Src )
    {
      v46 = -1;
      do
        ++v46;
      while ( *((_WORD *)v24 + v46) );
      v47 = -1;
      do
        ++v47;
      while ( *((_WORD *)Src + v47) );
      *a5 += 2 * (v47 - v46);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
      v24 = v45;
    }
    else
    {
LABEL_126:
      if ( FailureActions )
      {
        CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>::~CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>((PVOID *)&String);
LABEL_135:
        v48 = NtClose(KeyHandle);
        RtlNtStatusToDosError(v48);
        if ( v13 )
          ReleaseSRWLockShared(v13);
        goto LABEL_44;
      }
    }
    if ( v54 >= *a5 )
    {
      if ( v24 )
      {
        *(_DWORD *)a3 = 4;
        do
          v18 = *((_WORD *)v24 + ++v15) == 0;
        while ( !v18 );
        memmove((void *)(a3 + 4), v24, (unsigned int)(2 * v15 + 2));
      }
      else
      {
        *(_DWORD *)a3 = 0;
      }
    }
    else
    {
      FailureActions = 122;
    }
LABEL_133:
    v35 = NtCurrentPeb();
    v36 = (RPC_WSTR)v24;
LABEL_134:
    RtlFreeHeap(v35->ProcessHeap, 0, v36);
    goto LABEL_135;
  }
  return 87;
}

```

## disassembly

```asm
0x14000a050  mov     [rsp-8+arg_8], rbx
0x14000a055  push    rbp
0x14000a056  push    rsi
0x14000a057  push    rdi
0x14000a058  push    r12
0x14000a05a  push    r13
0x14000a05c  push    r14
0x14000a05e  push    r15
0x14000a060  lea     rbp, [rsp-40h]
0x14000a065  sub     rsp, 140h
0x14000a06c  mov     rax, cs:__security_cookie
0x14000a073  xor     rax, rsp
0x14000a076  mov     [rbp+70h+var_40], rax
0x14000a07a  mov     rsi, [rbp+70h+arg_20]
0x14000a081  xor     r14d, r14d
0x14000a084  cmp     cs:?s_pfnI_RpcServerTurnOnOffKeepalives@@3P6AJPEAXHKK@ZEA, r14; long (*s_pfnI_RpcServerTurnOnOffKeepalives)(void *,int,ulong,ulong)
0x14000a08b  mov     ebx, r9d
0x14000a08e  mov     [rsp+170h+var_118], ebx
0x14000a092  mov     r12, r8
0x14000a095  mov     dword ptr [rsp+170h+P], edx
0x14000a099  mov     r13, rcx
0x14000a09c  mov     r15d, 5
0x14000a0a2  jz      loc_14000A174
0x14000a0a8  xorps   xmm0, xmm0
0x14000a0ab  mov     [rsp+170h+String], r14
0x14000a0b0  lea     rdx, [rbp+70h+RpcCallAttributes]; RpcCallAttributes
0x14000a0b4  mov     [rsp+170h+Binding], r14
0x14000a0b9  xor     ecx, ecx; ClientBinding
0x14000a0bb  mov     [rbp+70h+RpcCallAttributes], 3
0x14000a0c2  movups  [rbp+70h+var_B8], xmm0
0x14000a0c6  mov     edi, r14d
0x14000a0c9  mov     [rbp+70h+var_BC], 40h ; '@'
0x14000a0d0  movups  [rbp+70h+var_A8], xmm0
0x14000a0d4  movups  [rbp+70h+var_98], xmm0
0x14000a0d8  movups  [rbp+70h+var_88], xmm0
0x14000a0dc  movups  [rbp+70h+var_78], xmm0
0x14000a0e0  movups  [rbp+70h+var_68], xmm0
0x14000a0e4  movups  [rbp+70h+var_58], xmm0
0x14000a0e8  call    cs:__imp_RpcServerInqCallAttributesA
0x14000a0ee  mov     r14d, eax
0x14000a0f1  test    eax, eax
0x14000a0f3  jnz     short loc_14000A0FD
0x14000a0f5  cmp     dword ptr [rbp+70h+var_88], 1
0x14000a0f9  setz    dil
0x14000a0fd  cmp     [rsp+170h+String], 0
0x14000a103  jz      short loc_14000A110
0x14000a105  lea     rcx, [rsp+170h+String]; String
0x14000a10a  call    cs:__imp_RpcStringFreeW
0x14000a110  cmp     [rsp+170h+Binding], 0
0x14000a116  jz      short loc_14000A123
0x14000a118  lea     rcx, [rsp+170h+Binding]; Binding
0x14000a11d  call    cs:__imp_RpcBindingFree
0x14000a123  test    r14d, r14d
0x14000a126  jnz     short loc_14000A171
0x14000a128  cmp     edi, 1
0x14000a12b  jnz     short loc_14000A171
0x14000a12d  movzx   eax, word ptr cs:?g_dwRpcOverTcpKeepAliveTimes@@3KA+2; ulong g_dwRpcOverTcpKeepAliveTimes
0x14000a134  mov     edx, edi
0x14000a136  movzx   ecx, word ptr cs:?g_dwRpcOverTcpKeepAliveTimes@@3KA; ulong g_dwRpcOverTcpKeepAliveTimes
0x14000a13d  cmp     cx, r15w
0x14000a141  cmovb   cx, r15w
0x14000a146  cmp     ax, r15w
0x14000a14a  cmovb   ax, r15w
0x14000a14f  movzx   eax, ax
0x14000a152  imul    r9d, eax, 3E8h
0x14000a159  movzx   eax, cx
0x14000a15c  xor     ecx, ecx
0x14000a15e  imul    r8d, eax, 0EA60h
0x14000a165  mov     rax, cs:?s_pfnI_RpcServerTurnOnOffKeepalives@@3P6AJPEAXHKK@ZEA; long (*s_pfnI_RpcServerTurnOnOffKeepalives)(void *,int,ulong,ulong)
0x14000a16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a171  xor     r14d, r14d
0x14000a174  cmp     cs:?ScShutdownInProgress@@3KA, 0; ulong ScShutdownInProgress
0x14000a17b  jz      short loc_14000A187
0x14000a17d  mov     eax, 45Bh
0x14000a182  jmp     loc_14000AAEA
0x14000a187  test    r13, r13
0x14000a18a  jz      loc_14000AAE5
0x14000a190  cmp     dword ptr [r13+0], 48726573h
0x14000a198  jnz     loc_14000AAE5
0x14000a19e  test    r12, r12
0x14000a1a1  jz      loc_14000AADE
0x14000a1a7  test    rsi, rsi
0x14000a1aa  jz      loc_14000AADE
0x14000a1b0  mov     ecx, [r13+8]; GrantedAccess
0x14000a1b4  mov     edx, 1; DesiredAccess
0x14000a1b9  call    cs:__imp_RtlAreAllAccessesGranted
0x14000a1bf  test    al, al
0x14000a1c1  jnz     short loc_14000A1CB
0x14000a1c3  mov     eax, r15d
0x14000a1c6  jmp     loc_14000AAEA
0x14000a1cb  mov     dl, 1; Wait
0x14000a1cd  mov     [rsi], r14d
0x14000a1d0  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14000a1d7  call    cs:__imp_RtlAcquireResourceShared
0x14000a1dd  mov     r13, [r13+10h]
0x14000a1e1  lea     rdi, [r13+138h]
0x14000a1e8  mov     rcx, rdi; SRWLock
0x14000a1eb  call    cs:__imp_AcquireSRWLockShared
0x14000a1f1  xorps   xmm0, xmm0
0x14000a1f4  mov     [rsp+170h+KeyHandle], r14
0x14000a1f9  mov     rax, [r13+0D8h]
0x14000a200  mov     r15, 0FFFFFFFFFFFFFFFFh
0x14000a207  mov     rcx, [r13+38h]
0x14000a20b  mov     [rsp+170h+var_108], rdi
0x14000a210  mov     [rsp+170h+Src], rcx
0x14000a215  mov     rax, [rax+20h]
0x14000a219  mov     [rsp+170h+Binding], rax
0x14000a21e  movups  xmmword ptr [rsp+170h+ObjectAttributes.Length], xmm0
0x14000a223  movups  xmmword ptr [rbp+70h+ObjectAttributes.ObjectName], xmm0
0x14000a227  movups  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000a22b  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x14000a22f  cmp     rax, 0FFFFFFFF80000002h
0x14000a235  jnz     loc_14000A2F9
0x14000a23b  mov     rax, r15
0x14000a23e  xchg    ax, ax
0x14000a240  cmp     word ptr [rcx+rax*2+2], 0
0x14000a246  lea     rax, [rax+1]
0x14000a24a  jnz     short loc_14000A240
0x14000a24c  mov     rcx, gs:60h
0x14000a255  lea     rax, ds:28h[rax*2]
0x14000a25d  mov     eax, eax
0x14000a25f  xor     edx, edx; Flags
0x14000a261  mov     r8d, eax; Size
0x14000a264  mov     [rsp+170h+Binding], rax
0x14000a269  mov     rcx, [rcx+30h]; HeapHandle
0x14000a26d  call    cs:__imp_RtlAllocateHeap
0x14000a273  mov     [rsp+170h+String], rax
0x14000a278  mov     r14, rax
0x14000a27b  test    rax, rax
0x14000a27e  jnz     short loc_14000A2C0
0x14000a280  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a287  lea     rdx, WPP_GLOBAL_Control
0x14000a28e  cmp     rcx, rdx
0x14000a291  jz      short loc_14000A2B5
0x14000a293  test    byte ptr [rcx+1Ch], 1
0x14000a297  jz      short loc_14000A2B5
0x14000a299  mov     rcx, [rcx+10h]
0x14000a29d  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14000a2a4  mov     edx, 6Fh ; 'o'
0x14000a2a9  call    WPP_SF_
0x14000a2ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a2b5  mov     r14d, 8
0x14000a2bb  jmp     loc_14000A425
0x14000a2c0  mov     rdx, [rsp+170h+Binding]; unsigned __int64
0x14000a2c5  lea     r8, aRegistryMachin_1; "\\REGISTRY\\MACHINE\\"
0x14000a2cc  mov     rcx, r14; unsigned __int16 *
0x14000a2cf  mov     [rsp+170h+var_130], 1
0x14000a2d7  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14000a2dc  mov     r8, [rsp+170h+Src]; unsigned __int16 *
0x14000a2e1  mov     rcx, r14; unsigned __int16 *
0x14000a2e4  mov     rdx, [rsp+170h+Binding]; unsigned __int64
0x14000a2e9  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x14000a2ee  mov     [rsp+170h+Binding], 0
0x14000a2f7  jmp     short loc_14000A306
0x14000a2f9  mov     [rsp+170h+var_130], r14d
0x14000a2fe  mov     r14, rcx
0x14000a301  mov     [rsp+170h+String], rcx
0x14000a306  mov     rdx, r14; SourceString
0x14000a309  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x14000a30d  call    cs:__imp_RtlInitUnicodeString
0x14000a313  mov     rax, [rsp+170h+Binding]
0x14000a318  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x14000a31d  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x14000a322  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x14000a327  lea     rax, [rbp+70h+DestinationString]
0x14000a32b  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x14000a333  xorps   xmm0, xmm0
0x14000a336  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x14000a33a  mov     edx, 20019h; DesiredAccess
0x14000a33f  mov     [rbp+70h+ObjectAttributes.Attributes], 40h ; '@'
0x14000a346  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000a34b  call    cs:__imp_NtOpenKey
0x14000a351  mov     dword ptr [rsp+170h+Binding], eax
0x14000a355  cmp     eax, 0C0000022h
0x14000a35a  jnz     loc_14000A3EE
0x14000a360  lea     rcx, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x14000a365  call    ?ScTakeOwnership@@YAKPEAU_OBJECT_ATTRIBUTES@@@Z; ScTakeOwnership(_OBJECT_ATTRIBUTES *)
0x14000a36a  mov     r14d, eax
0x14000a36d  test    eax, eax
0x14000a36f  jz      short loc_14000A39B
0x14000a371  cmp     [rsp+170h+var_130], 0
0x14000a376  jz      loc_14000A41E
0x14000a37c  mov     rcx, gs:60h
0x14000a385  xor     edx, edx; Flags
0x14000a387  mov     r8, [rsp+170h+String]; P
0x14000a38c  mov     rcx, [rcx+30h]; HeapHandle
0x14000a390  call    cs:__imp_RtlFreeHeap
0x14000a396  jmp     loc_14000A41E
0x14000a39b  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x14000a3a0  mov     edx, 20019h; DesiredAccess
0x14000a3a5  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x14000a3aa  call    cs:__imp_NtOpenKey
0x14000a3b0  mov     dword ptr [rsp+170h+Binding], eax
0x14000a3b4  test    eax, eax
0x14000a3b6  jns     short loc_14000A3E9
0x14000a3b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a3bf  lea     rdx, WPP_GLOBAL_Control
0x14000a3c6  cmp     rcx, rdx
0x14000a3c9  jz      short loc_14000A3E9
0x14000a3cb  test    byte ptr [rcx+1Ch], 1
0x14000a3cf  jz      short loc_14000A3E9
0x14000a3d1  mov     rcx, [rcx+10h]
0x14000a3d5  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14000a3dc  mov     edx, 70h ; 'p'
0x14000a3e1  mov     r9d, eax
0x14000a3e4  call    WPP_SF_d
0x14000a3e9  mov     r14, [rsp+170h+String]
0x14000a3ee  cmp     [rsp+170h+var_130], 0
0x14000a3f3  jz      short loc_14000A40D
0x14000a3f5  mov     rcx, gs:60h
0x14000a3fe  mov     r8, r14; P
0x14000a401  xor     edx, edx; Flags
0x14000a403  mov     rcx, [rcx+30h]; HeapHandle
0x14000a407  call    cs:__imp_RtlFreeHeap
0x14000a40d  mov     ecx, dword ptr [rsp+170h+Binding]; Status
0x14000a411  call    cs:__imp_RtlNtStatusToDosError
0x14000a417  mov     r14d, eax
0x14000a41a  test    eax, eax
0x14000a41c  jz      short loc_14000A475
0x14000a41e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a425  lea     rax, WPP_GLOBAL_Control
0x14000a42c  cmp     rcx, rax
0x14000a42f  jz      short loc_14000A456
0x14000a431  test    byte ptr [rcx+1Ch], 1
0x14000a435  jz      short loc_14000A456
0x14000a437  mov     r9, [rsp+170h+Src]
0x14000a43c  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14000a443  mov     rcx, [rcx+10h]
0x14000a447  mov     edx, 27h ; '''
0x14000a44c  mov     dword ptr [rsp+170h+var_150], r14d
0x14000a451  call    WPP_SF_Sd
0x14000a456  lea     rcx, [rsp+170h+var_108]; this
0x14000a45b  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x14000a460  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14000a467  call    cs:__imp_RtlReleaseResource
0x14000a46d  mov     eax, r14d
0x14000a470  jmp     loc_14000AAEA
0x14000a475  mov     eax, dword ptr [rsp+170h+P]
0x14000a479  cmp     eax, 1
0x14000a47c  jz      loc_14000A8B8
0x14000a482  cmp     eax, 3
0x14000a485  jz      loc_14000A88C
0x14000a48b  add     eax, 0FFFFFFFEh; switch 11 cases
0x14000a48e  cmp     eax, 0Ah
0x14000a491  ja      def_14000A4A8; jumptable 000000014000A4A8 default case, cases 3,8,10
0x14000a497  lea     rcx, __ImageBase
0x14000a49e  mov     eax, ds:(jpt_14000A4A8 - 140000000h)[rcx+rax*4]
0x14000a4a5  add     rax, rcx
0x14000a4a8  jmp     rax; switch jump
0x14000a4aa  mov     rcx, [rsp+170h+KeyHandle]; jumptable 000000014000A4A8 case 2
0x14000a4af  lea     rdx, [rsp+170h+P]; struct _SERVICE_FAILURE_ACTIONS_WOW64 **
0x14000a4b4  mov     r8, rsi; unsigned int *
0x14000a4b7  mov     [rsp+170h+P], 0
0x14000a4c0  call    ?ScReadFailureActions@@YAKPEAUHKEY__@@PEAPEAU_SERVICE_FAILURE_ACTIONS_WOW64@@PEAK@Z; ScReadFailureActions(HKEY__ *,_SERVICE_FAILURE_ACTIONS_WOW64 * *,ulong *)
0x14000a4c5  mov     r14d, eax
0x14000a4c8  test    eax, eax
0x14000a4ca  jz      short loc_14000A4DB
0x14000a4cc  lea     rcx, [rsp+170h+P]
0x14000a4d1  call    ??1?$CHeapPtr@PEAU_SERVICE_FAILURE_ACTIONS_WOW64@@@@QEAA@XZ; CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>::~CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>(void)
0x14000a4d6  jmp     loc_14000AAB4
0x14000a4db  mov     rbx, [rsp+170h+P]
0x14000a4e0  test    rbx, rbx
0x14000a4e3  jnz     short loc_14000A4EB
0x14000a4e5  mov     dword ptr [rsi], 14h
0x14000a4eb  mov     rax, [r13+0]
0x14000a4ef  mov     rcx, r13
0x14000a4f2  mov     [rsp+170h+String], 0
0x14000a4fb  mov     rax, [rax+30h]
0x14000a4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a504  lea     rcx, [rsp+170h+String]
0x14000a509  mov     [rsp+170h+var_148], rsi; unsigned int *
0x14000a50e  mov     [rsp+170h+var_150], rcx; unsigned __int16 **
0x14000a513  lea     rdx, aRebootmessage; "RebootMessage"
0x14000a51a  mov     rcx, [rsp+170h+KeyHandle]; hKey
0x14000a51f  movzx   r9d, ax; unsigned __int16
0x14000a523  mov     r8d, 1; int
0x14000a529  call    ?ScReadAndTranslateString@@YAKPEAUHKEY__@@PEAGHGPEAPEAGPEAK@Z; ScReadAndTranslateString(HKEY__ *,ushort *,int,ushort,ushort * *,ulong *)
0x14000a52e  mov     r14d, eax
0x14000a531  test    eax, eax
0x14000a533  jz      short loc_14000A554
0x14000a535  mov     rcx, gs:60h
0x14000a53e  xor     edx, edx; Flags
0x14000a540  mov     r8, [rsp+170h+String]; P
0x14000a545  mov     rcx, [rcx+30h]; HeapHandle
0x14000a549  call    cs:__imp_RtlFreeHeap
0x14000a54f  jmp     loc_14000AA9C
0x14000a554  mov     rcx, [rsp+170h+KeyHandle]; HKEY
0x14000a559  lea     r8, [rsp+170h+Binding]; unsigned __int16 **
0x14000a55e  xor     r13d, r13d
0x14000a561  lea     rdx, aFailurecommand; "FailureCommand"
0x14000a568  mov     r9, rsi; unsigned int *
0x14000a56b  mov     [rsp+170h+Binding], r13
0x14000a570  call    ?ScReadOptionalString@@YAKPEAUHKEY__@@PEBGPEAPEAGPEAK@Z; ScReadOptionalString(HKEY__ *,ushort const *,ushort * *,ulong *)
0x14000a575  mov     r14d, eax
0x14000a578  test    eax, eax
0x14000a57a  jz      short loc_14000A59F
0x14000a57c  lea     rcx, [rsp+170h+Binding]
0x14000a581  call    ??1?$CHeapPtr@PEAU_SERVICE_FAILURE_ACTIONS_WOW64@@@@QEAA@XZ; CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>::~CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>(void)
0x14000a586  lea     rcx, [rsp+170h+String]
0x14000a58b  call    ??1?$CHeapPtr@PEAU_SERVICE_FAILURE_ACTIONS_WOW64@@@@QEAA@XZ; CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>::~CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>(void)
  ... truncated ...
```
