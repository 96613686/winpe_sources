# ScInitSecurityProcess(CServiceRecord *)

- ea: `0x14007a510`
- end: `0x14007a7bc`
- name: `?ScInitSecurityProcess@@YAKPEAVCServiceRecord@@@Z`
- size: `684`
- prototype: `unsigned int __fastcall(struct CServiceRecord *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14003c510`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x14000b014`
- `0x14001e710`
- `0x14006d760`
- `0x1400703f4`
- `0x14007a510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14007a650`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14007a650`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14007a578`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14007a578`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14007a549`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14007a549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007a55b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007a586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007a65a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007a55b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007a586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007a65a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007a7a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007a7a4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14007a796`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14007a796`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14007a780`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14007a780`

## string_xrefs

- `0x14007a534`: `SECURITY_SERVICES_STARTED`
- `0x14007a56a`: `SECURITY_SERVICES_STARTED`

## pseudocode

```c
__int64 __fastcall ScInitSecurityProcess(struct CServiceRecord *a1)
{
  HANDLE EventW; // rdi
  unsigned int LastError; // ebx
  PRPC_ASYNC_STATE v4; // rcx
  __int64 v5; // rdx
  PRPC_ASYNC_STATE v6; // rcx
  int v7; // edx
  PRPC_ASYNC_STATE v8; // rcx
  __int64 v9; // rdx
  const unsigned __int16 *v10; // r8
  unsigned int v12; // [rsp+58h] [rbp-18h]
  unsigned int v13; // [rsp+98h] [rbp+28h] BYREF
  struct _SC_SERVICE_CHANNEL_CONTEXT *v14; // [rsp+A0h] [rbp+30h] BYREF
  struct _IMAGE_RECORD *v15; // [rsp+A8h] [rbp+38h] BYREF

  v15 = 0;
  v13 = 0;
  v14 = 0;
  EventW = CreateEventW(0, 1, 0, L"SECURITY_SERVICES_STARTED");
  if ( EventW )
    goto LABEL_11;
  LastError = GetLastError();
  if ( LastError == 183 )
  {
    EventW = OpenEventW(0x40000000u, 0, L"SECURITY_SERVICES_STARTED");
    if ( !EventW )
    {
      LastError = GetLastError();
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        v5 = 22;
LABEL_7:
        WPP_SF_d(v4->StubInfo, v5, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, LastError);
        return LastError;
      }
      return LastError;
    }
LABEL_11:
    LastError = ScInitControlMessageContext(LocalSystemSid, 0, &v14);
    if ( LastError )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_30;
      v7 = 24;
      goto LABEL_15;
    }
    if ( SetEvent(EventW) )
    {
      LastError = ScWaitForFirstResponse(v14, 0, a1, &v13);
      if ( LastError )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_30;
        }
        v7 = 26;
LABEL_15:
        WPP_SF_Sd(
          v6->StubInfo,
          v7,
          (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
          *((_QWORD *)a1 + 7),
          LastError);
LABEL_30:
        if ( v14 )
        {
          RtlAcquireSRWLockExclusive(&g_ScServiceChannelLock);
          ScReleaseRefAndFreeServiceChannelContextUnlocked(&v14);
          RtlReleaseSRWLockExclusive(&g_ScServiceChannelLock);
        }
        CloseHandle(EventW);
        return LastError;
      }
      LastError = ScCreateImageRecord(&v15, ScGlobalSecurityExePath, v10, 0, v13, 0, 0, 0, 3u, v14, 0, v12, 0, 0);
      if ( !LastError )
      {
        LastError = 0;
        v14 = 0;
        goto LABEL_30;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_30;
      v9 = 27;
    }
    else
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_30;
      v9 = 25;
    }
    WPP_SF_d(v8->StubInfo, v9, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, LastError);
    goto LABEL_30;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    v5 = 23;
    goto LABEL_7;
  }
  return LastError;
}

```

## disassembly

```asm
0x14007a510  mov     [rsp-18h+arg_0], rbx
0x14007a515  push    rbp
0x14007a516  push    rsi
0x14007a517  push    rdi
0x14007a518  mov     rbp, rsp
0x14007a51b  sub     rsp, 70h
0x14007a51f  xor     r8d, r8d; bInitialState
0x14007a522  mov     [rbp+arg_18], 0
0x14007a52a  mov     rsi, rcx
0x14007a52d  mov     [rbp+arg_8], 0
0x14007a534  lea     r9, aSecurityServic; "SECURITY_SERVICES_STARTED"
0x14007a53b  mov     [rbp+arg_10], 0
0x14007a543  xor     ecx, ecx; lpEventAttributes
0x14007a545  lea     edx, [r8+1]; bManualReset
0x14007a549  call    cs:__imp_CreateEventW
0x14007a54f  mov     rdi, rax
0x14007a552  test    rax, rax
0x14007a555  jnz     loc_14007A5F2
0x14007a55b  call    cs:__imp_GetLastError
0x14007a561  mov     ebx, eax
0x14007a563  cmp     eax, 0B7h
0x14007a568  jnz     short loc_14007A5CA
0x14007a56a  lea     r8, aSecurityServic; "SECURITY_SERVICES_STARTED"
0x14007a571  xor     edx, edx; bInheritHandle
0x14007a573  mov     ecx, 40000000h; dwDesiredAccess
0x14007a578  call    cs:__imp_OpenEventW
0x14007a57e  mov     rdi, rax
0x14007a581  test    rax, rax
0x14007a584  jnz     short loc_14007A5F2
0x14007a586  call    cs:__imp_GetLastError
0x14007a58c  mov     ebx, eax
0x14007a58e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a595  lea     rax, WPP_GLOBAL_Control
0x14007a59c  cmp     rcx, rax
0x14007a59f  jz      loc_14007A7AA
0x14007a5a5  test    byte ptr [rcx+1Ch], 1
0x14007a5a9  jz      loc_14007A7AA
0x14007a5af  lea     edx, [rdi+16h]
0x14007a5b2  mov     rcx, [rcx+10h]
0x14007a5b6  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007a5bd  mov     r9d, ebx
0x14007a5c0  call    WPP_SF_d
0x14007a5c5  jmp     loc_14007A7AA
0x14007a5ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a5d1  lea     rax, WPP_GLOBAL_Control
0x14007a5d8  cmp     rcx, rax
0x14007a5db  jz      loc_14007A7AA
0x14007a5e1  test    byte ptr [rcx+1Ch], 1
0x14007a5e5  jz      loc_14007A7AA
0x14007a5eb  mov     edx, 17h
0x14007a5f0  jmp     short loc_14007A5B2
0x14007a5f2  mov     rcx, cs:LocalSystemSid; pSourceSid
0x14007a5f9  lea     r8, [rbp+arg_10]
0x14007a5fd  xor     edx, edx; Process
0x14007a5ff  call    ScInitControlMessageContext
0x14007a604  mov     ebx, eax
0x14007a606  test    eax, eax
0x14007a608  jz      short loc_14007A64D
0x14007a60a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a611  lea     rax, WPP_GLOBAL_Control
0x14007a618  cmp     rcx, rax
0x14007a61b  jz      loc_14007A772
0x14007a621  test    byte ptr [rcx+1Ch], 1
0x14007a625  jz      loc_14007A772
0x14007a62b  mov     edx, 18h
0x14007a630  mov     r9, [rsi+38h]
0x14007a634  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007a63b  mov     rcx, [rcx+10h]
0x14007a63f  mov     [rsp+70h+var_50], ebx
0x14007a643  call    WPP_SF_Sd
0x14007a648  jmp     loc_14007A772
0x14007a64d  mov     rcx, rdi; hEvent
0x14007a650  call    cs:__imp_SetEvent
0x14007a656  test    eax, eax
0x14007a658  jnz     short loc_14007A6A0
0x14007a65a  call    cs:__imp_GetLastError
0x14007a660  mov     ebx, eax
0x14007a662  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a669  lea     rax, WPP_GLOBAL_Control
0x14007a670  cmp     rcx, rax
0x14007a673  jz      loc_14007A772
0x14007a679  test    byte ptr [rcx+1Ch], 1
0x14007a67d  jz      loc_14007A772
0x14007a683  mov     edx, 19h
0x14007a688  mov     rcx, [rcx+10h]
0x14007a68c  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007a693  mov     r9d, ebx
0x14007a696  call    WPP_SF_d
0x14007a69b  jmp     loc_14007A772
0x14007a6a0  mov     rcx, [rbp+arg_10]; struct _SC_SERVICE_CHANNEL_CONTEXT *
0x14007a6a4  lea     r9, [rbp+arg_8]; unsigned int *
0x14007a6a8  mov     r8, rsi; struct CServiceRecord *
0x14007a6ab  xor     edx, edx; void *
0x14007a6ad  call    ?ScWaitForFirstResponse@@YAKPEAU_SC_SERVICE_CHANNEL_CONTEXT@@PEAXPEAVCServiceRecord@@PEAK@Z; ScWaitForFirstResponse(_SC_SERVICE_CHANNEL_CONTEXT *,void *,CServiceRecord *,ulong *)
0x14007a6b2  mov     ebx, eax
0x14007a6b4  test    eax, eax
0x14007a6b6  jz      short loc_14007A6E3
0x14007a6b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a6bf  lea     rax, WPP_GLOBAL_Control
0x14007a6c6  cmp     rcx, rax
0x14007a6c9  jz      loc_14007A772
0x14007a6cf  test    byte ptr [rcx+1Ch], 1
0x14007a6d3  jz      loc_14007A772
0x14007a6d9  mov     edx, 1Ah
0x14007a6de  jmp     loc_14007A630
0x14007a6e3  mov     rax, [rbp+arg_10]
0x14007a6e7  lea     rcx, [rbp+arg_18]; struct _IMAGE_RECORD **
0x14007a6eb  mov     rdx, cs:?ScGlobalSecurityExePath@@3PEAGEA; unsigned __int16 *
0x14007a6f2  xor     r9d, r9d; unsigned __int16 *
0x14007a6f5  mov     [rsp+70h+var_8], 0; void *
0x14007a6fe  mov     [rsp+70h+var_10], 0; unsigned __int64
0x14007a707  mov     [rsp+70h+var_20], 0; unsigned int
0x14007a70f  mov     [rsp+70h+var_28], rax; struct _SC_SERVICE_CHANNEL_CONTEXT *
0x14007a714  mov     eax, [rbp+arg_8]
0x14007a717  mov     [rsp+70h+var_30], 3; unsigned int
0x14007a71f  mov     [rsp+70h+var_38], 0; void *
0x14007a728  mov     [rsp+70h+var_40], 0; void *
0x14007a731  mov     [rsp+70h+var_48], 0; void *
0x14007a73a  mov     [rsp+70h+var_50], eax; unsigned int
0x14007a73e  call    ?ScCreateImageRecord@@YAKPEAPEAU_IMAGE_RECORD@@PEBG11KPEAX22KPEAU_SC_SERVICE_CHANNEL_CONTEXT@@KK_K2@Z; ScCreateImageRecord(_IMAGE_RECORD * *,ushort const *,ushort const *,ushort const *,ulong,void *,void *,void *,ulong,_SC_SERVICE_CHANNEL_CONTEXT *,ulong,ulong,unsigned __int64,void *)
0x14007a743  mov     ebx, eax
0x14007a745  test    eax, eax
0x14007a747  jz      short loc_14007A76C
0x14007a749  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a750  lea     rax, WPP_GLOBAL_Control
0x14007a757  cmp     rcx, rax
0x14007a75a  jz      short loc_14007A772
0x14007a75c  test    byte ptr [rcx+1Ch], 1
0x14007a760  jz      short loc_14007A772
0x14007a762  mov     edx, 1Bh
0x14007a767  jmp     loc_14007A688
0x14007a76c  xor     ebx, ebx
0x14007a76e  mov     [rbp+arg_10], rbx
0x14007a772  cmp     [rbp+arg_10], 0
0x14007a777  jz      short loc_14007A79C
0x14007a779  lea     rcx, g_ScServiceChannelLock
0x14007a780  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14007a786  lea     rcx, [rbp+arg_10]
0x14007a78a  call    ScReleaseRefAndFreeServiceChannelContextUnlocked
0x14007a78f  lea     rcx, g_ScServiceChannelLock
0x14007a796  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14007a79c  test    rdi, rdi
0x14007a79f  jz      short loc_14007A7AA
0x14007a7a1  mov     rcx, rdi; hObject
0x14007a7a4  call    cs:__imp_CloseHandle
0x14007a7aa  mov     eax, ebx
0x14007a7ac  mov     rbx, [rsp+70h+arg_0]
0x14007a7b4  add     rsp, 70h
0x14007a7b8  pop     rdi
0x14007a7b9  pop     rsi
0x14007a7ba  pop     rbp
0x14007a7bb  retn
```
