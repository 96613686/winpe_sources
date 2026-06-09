# UbpmpMaintenanceTaskReevaluateAllTriggers(void)

- ea: `0x18000a8b0`
- end: `0x18000aaab`
- name: `?UbpmpMaintenanceTaskReevaluateAllTriggers@@YAKXZ`
- size: `507`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18002dbf0`

## callees

- `0x180001d70`
- `0x180001db8`
- `0x18000a8b0`
- `0x18000aba0`
- `0x18000ae00`
- `0x1800136f4`
- `0x180019d90`
- `0x18002cb88`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000aa92`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000aa92`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000aa53`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000aa53`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a97c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a992`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a97c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a992`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a9b7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a9f6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a9b7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a9f6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a953`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a95e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a9c8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a953`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a95e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a9c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a982`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a998`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a982`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a998`
- `RPCRT4!UuidIsNil` at `0x18000aa65`
- `RPCRT4!UuidIsNil` at `0x18000aa65`

## pseudocode

```c
__int64 UbpmpMaintenanceTaskReevaluateAllTriggers(void)
{
  unsigned int v0; // eax
  __int64 v1; // r12
  unsigned int v2; // r15d
  unsigned int v4; // r14d
  unsigned int i; // edi
  DWORD v6; // ebp
  __int64 v7; // rsi
  _QWORD *Value; // rbx
  __int64 v9; // rax
  __int64 *v10; // rax
  __int64 v11; // rdx
  unsigned int v13; // [rsp+60h] [rbp+8h] BYREF
  RPC_STATUS Status; // [rsp+68h] [rbp+10h] BYREF
  __int64 v15; // [rsp+70h] [rbp+18h] BYREF

  Status = 0;
  v13 = 0;
  v15 = 0;
  UbpmpAcquireListLockShared();
  v0 = UbpmConsumerSnapListCopy(&v15, &v13);
  v1 = v15;
  v2 = v0;
  if ( !v0 )
  {
    UbpmpReleaseListLockShared();
    v4 = v13;
    for ( i = 0; i < v4; ++i )
    {
      v6 = UbpmpLockTrackerId;
      v7 = *(_QWORD *)(v1 + 8LL * i);
      if ( UbpmpLockTrackerId != -1 )
      {
        Value = TlsGetValue(UbpmpLockTrackerId);
        if ( *(_QWORD *)TlsGetValue(v6) )
          __int2c();
        *Value |= 1uLL;
        ++Value[1];
      }
      RtlAcquireSRWLockExclusive(&g_ConsumerUpdateLock);
      dword_18004CEC8 = GetCurrentThreadId();
      RtlAcquireSRWLockExclusive(v7 + 48);
      *(_DWORD *)(v7 + 56) = GetCurrentThreadId();
      v9 = *(_QWORD *)(v7 + 24);
      if ( *(_QWORD *)(v9 + 48) && (*(_BYTE *)(v9 + 16) & 1) == 0 && !(unsigned __int8)UbpmConsumerIsUnregistered(v7) )
      {
        RtlAcquireSRWLockShared(v7 + 208);
        if ( UuidIsNil((UUID *)(v7 + 272), &Status) && *(_QWORD *)(v7 + 256) == v7 + 256 )
          v2 = UbpmpMaintenanceEvaluateTriggersForConsumer((struct _UBPM_TRIGGER_CONSUMER_BLOCK *)v7);
        else
          RtlReleaseSRWLockShared(v7 + 208);
      }
      *(_DWORD *)(v7 + 56) = 0;
      RtlReleaseSRWLockExclusive(v7 + 48);
      if ( UbpmpLockTrackerId != -1 )
      {
        v10 = (__int64 *)TlsGetValue(UbpmpLockTrackerId);
        v11 = *v10;
        if ( (*v10 & 1) == 0 )
          __int2c();
        if ( v10[1]-- == 1 )
          *v10 = v11 & 0xFFFFFFFFFFFFFFFEuLL;
      }
      dword_18004CEC8 = 0;
      RtlReleaseSRWLockExclusive(&g_ConsumerUpdateLock);
      UbpmpCloseTriggerConsumer(v7);
      if ( v2 )
        break;
    }
  }
  if ( v1 )
    UBPM_MIDL_user_free(v1);
  return v2;
}

```

## disassembly

```asm
0x18000a8b0  push    r12
0x18000a8b2  push    r15
0x18000a8b4  sub     rsp, 48h
0x18000a8b8  mov     [rsp+58h+var_30], r13
0x18000a8bd  xor     r13d, r13d
0x18000a8c0  mov     [rsp+58h+Status], r13d
0x18000a8c5  mov     [rsp+58h+arg_0], r13d
0x18000a8ca  mov     [rsp+58h+arg_10], r13
0x18000a8cf  call    UbpmpAcquireListLockShared
0x18000a8d4  lea     rdx, [rsp+58h+arg_0]
0x18000a8d9  lea     rcx, [rsp+58h+arg_10]
0x18000a8de  call    UbpmConsumerSnapListCopy
0x18000a8e3  mov     r12, [rsp+58h+arg_10]
0x18000a8e8  mov     r15d, eax
0x18000a8eb  test    eax, eax
0x18000a8ed  jz      short loc_18000A90F
0x18000a8ef  mov     r13, [rsp+58h+var_30]
0x18000a8f4  test    r12, r12
0x18000a8f7  jnz     short loc_18000A905
0x18000a8f9  mov     eax, r15d
0x18000a8fc  add     rsp, 48h
0x18000a900  pop     r15
0x18000a902  pop     r12
0x18000a904  retn
0x18000a905  mov     rcx, r12
0x18000a908  call    UBPM_MIDL_user_free
0x18000a90d  jmp     short loc_18000A8F9
0x18000a90f  mov     [rsp+58h+var_28], rdi
0x18000a914  mov     [rsp+58h+var_38], r14
0x18000a919  call    UbpmpReleaseListLockShared
0x18000a91e  mov     r14d, [rsp+58h+arg_0]
0x18000a923  mov     edi, r13d
0x18000a926  test    r14d, r14d
0x18000a929  jz      loc_18000AA23
0x18000a92f  mov     [rsp+58h+arg_18], rbx
0x18000a934  mov     [rsp+58h+var_18], rbp
0x18000a939  mov     [rsp+58h+var_20], rsi
0x18000a93e  xchg    ax, ax
0x18000a940  mov     ebp, cs:UbpmpLockTrackerId
0x18000a946  mov     eax, edi
0x18000a948  mov     rsi, [r12+rax*8]
0x18000a94c  cmp     ebp, 0FFFFFFFFh
0x18000a94f  jz      short loc_18000A975
0x18000a951  mov     ecx, ebp; dwTlsIndex
0x18000a953  call    cs:__imp_TlsGetValue
0x18000a959  mov     ecx, ebp; dwTlsIndex
0x18000a95b  mov     rbx, rax
0x18000a95e  call    cs:__imp_TlsGetValue
0x18000a964  cmp     [rax], r13
0x18000a967  jnz     loc_18000AAA4
0x18000a96d  or      qword ptr [rbx], 1
0x18000a971  inc     qword ptr [rbx+8]
0x18000a975  lea     rcx, ?g_ConsumerUpdateLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerUpdateLock
0x18000a97c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000a982  call    cs:__imp_GetCurrentThreadId
0x18000a988  lea     rcx, [rsi+30h]
0x18000a98c  mov     cs:dword_18004CEC8, eax
0x18000a992  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000a998  call    cs:__imp_GetCurrentThreadId
0x18000a99e  mov     [rsi+38h], eax
0x18000a9a1  mov     rax, [rsi+18h]
0x18000a9a5  cmp     [rax+30h], r13
0x18000a9a9  jnz     loc_18000AA32
0x18000a9af  lea     rcx, [rsi+30h]
0x18000a9b3  mov     [rsi+38h], r13d
0x18000a9b7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000a9bd  mov     ecx, cs:UbpmpLockTrackerId; dwTlsIndex
0x18000a9c3  cmp     ecx, 0FFFFFFFFh
0x18000a9c6  jz      short loc_18000A9E8
0x18000a9c8  call    cs:__imp_TlsGetValue
0x18000a9ce  mov     rdx, [rax]
0x18000a9d1  test    dl, 1
0x18000a9d4  jz      loc_18000AA9D
0x18000a9da  sub     qword ptr [rax+8], 1
0x18000a9df  jnz     short loc_18000A9E8
0x18000a9e1  and     rdx, 0FFFFFFFFFFFFFFFEh
0x18000a9e5  mov     [rax], rdx
0x18000a9e8  lea     rcx, ?g_ConsumerUpdateLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerUpdateLock
0x18000a9ef  mov     cs:dword_18004CEC8, r13d
0x18000a9f6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000a9fc  mov     rcx, rsi
0x18000a9ff  call    UbpmpCloseTriggerConsumer
0x18000aa04  test    r15d, r15d
0x18000aa07  jnz     short loc_18000AA14
0x18000aa09  inc     edi
0x18000aa0b  cmp     edi, r14d
0x18000aa0e  jb      loc_18000A940
0x18000aa14  mov     rbp, [rsp+58h+var_18]
0x18000aa19  mov     rsi, [rsp+58h+var_20]
0x18000aa1e  mov     rbx, [rsp+58h+arg_18]
0x18000aa23  mov     rdi, [rsp+58h+var_28]
0x18000aa28  mov     r14, [rsp+58h+var_38]
0x18000aa2d  jmp     loc_18000A8EF
0x18000aa32  test    byte ptr [rax+10h], 1
0x18000aa36  jnz     loc_18000A9AF
0x18000aa3c  mov     rcx, rsi
0x18000aa3f  call    UbpmConsumerIsUnregistered
0x18000aa44  test    al, al
0x18000aa46  jnz     loc_18000A9AF
0x18000aa4c  lea     rcx, [rsi+0D0h]
0x18000aa53  call    cs:__imp_RtlAcquireSRWLockShared
0x18000aa59  lea     rcx, [rsi+110h]; Uuid
0x18000aa60  lea     rdx, [rsp+58h+Status]; Status
0x18000aa65  call    cs:__imp_UuidIsNil
0x18000aa6b  test    eax, eax
0x18000aa6d  jz      short loc_18000AA8B
0x18000aa6f  lea     rax, [rsi+100h]
0x18000aa76  cmp     [rax], rax
0x18000aa79  jnz     short loc_18000AA8B
0x18000aa7b  mov     rcx, rsi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18000aa7e  call    ?UbpmpMaintenanceEvaluateTriggersForConsumer@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@@Z; UbpmpMaintenanceEvaluateTriggersForConsumer(_UBPM_TRIGGER_CONSUMER_BLOCK *)
0x18000aa83  mov     r15d, eax
0x18000aa86  jmp     loc_18000A9AF
0x18000aa8b  lea     rcx, [rsi+0D0h]
0x18000aa92  call    cs:__imp_RtlReleaseSRWLockShared
0x18000aa98  jmp     loc_18000A9AF
0x18000aa9d  int     2Ch; Windows NT - assertion failure
0x18000aa9f  jmp     loc_18000A9DA
0x18000aaa4  int     2Ch; Windows NT - assertion failure
0x18000aaa6  jmp     loc_18000A96D
```
