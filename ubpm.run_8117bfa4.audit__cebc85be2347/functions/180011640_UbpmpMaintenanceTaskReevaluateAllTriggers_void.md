# UbpmpMaintenanceTaskReevaluateAllTriggers(void)

- ea: `0x180011640`
- end: `0x180011883`
- name: `?UbpmpMaintenanceTaskReevaluateAllTriggers@@YAKXZ`
- size: `579`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18002fd10`

## callees

- `0x180002c70`
- `0x180002cc4`
- `0x18000fbf0`
- `0x18000fdc8`
- `0x180010400`
- `0x180011640`
- `0x180012950`
- `0x18002ec30`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180011864`
- `ntdll!RtlReleaseSRWLockShared` at `0x180011864`
- `ntdll!RtlAcquireSRWLockShared` at `0x180011819`
- `ntdll!RtlAcquireSRWLockShared` at `0x180011819`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011718`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001173a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011718`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001173a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001176b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800117b6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001176b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800117b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800116e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800116f4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011782`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800116e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800116f4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011782`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011724`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011746`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011724`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011746`
- `RPCRT4!UuidIsNil` at `0x180011831`
- `RPCRT4!UuidIsNil` at `0x180011831`

## pseudocode

```c
__int64 UbpmpMaintenanceTaskReevaluateAllTriggers(void)
{
  unsigned int v0; // eax
  __int64 v1; // rdx
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // r12
  unsigned int v5; // r15d
  unsigned int v7; // r14d
  unsigned int i; // edi
  DWORD v9; // ebp
  __int64 v10; // rsi
  _QWORD *Value; // rbx
  __int64 v12; // rax
  __int64 *v13; // rax
  __int64 v14; // rdx
  unsigned int v16; // [rsp+60h] [rbp+8h] BYREF
  RPC_STATUS Status; // [rsp+68h] [rbp+10h] BYREF
  __int64 v18; // [rsp+70h] [rbp+18h] BYREF

  Status = 0;
  v16 = 0;
  v18 = 0;
  UbpmpAcquireListLockShared();
  v0 = UbpmConsumerSnapListCopy(&v18, &v16);
  v4 = v18;
  v5 = v0;
  if ( !v0 )
  {
    UbpmpReleaseListLockShared();
    v7 = v16;
    for ( i = 0; i < v7; ++i )
    {
      v9 = UbpmpLockTrackerId;
      v10 = *(_QWORD *)(v4 + 8LL * i);
      if ( UbpmpLockTrackerId != -1 )
      {
        Value = TlsGetValue(UbpmpLockTrackerId);
        if ( *(_QWORD *)TlsGetValue(v9) )
          __int2c();
        *Value |= 1uLL;
        ++Value[1];
      }
      RtlAcquireSRWLockExclusive(&g_ConsumerUpdateLock);
      dword_18004FFC8 = GetCurrentThreadId();
      RtlAcquireSRWLockExclusive(v10 + 48);
      *(_DWORD *)(v10 + 56) = GetCurrentThreadId();
      v12 = *(_QWORD *)(v10 + 24);
      if ( *(_QWORD *)(v12 + 48) && (*(_BYTE *)(v12 + 16) & 1) == 0 && !(unsigned __int8)UbpmConsumerIsUnregistered(v10) )
      {
        RtlAcquireSRWLockShared(v10 + 208);
        if ( UuidIsNil((UUID *)(v10 + 272), &Status) && *(_QWORD *)(v10 + 256) == v10 + 256 )
          v5 = UbpmpMaintenanceEvaluateTriggersForConsumer((struct _UBPM_TRIGGER_CONSUMER_BLOCK *)v10);
        else
          RtlReleaseSRWLockShared(v10 + 208);
      }
      *(_DWORD *)(v10 + 56) = 0;
      RtlReleaseSRWLockExclusive(v10 + 48);
      if ( UbpmpLockTrackerId != -1 )
      {
        v13 = (__int64 *)TlsGetValue(UbpmpLockTrackerId);
        v14 = *v13;
        if ( (*v13 & 1) == 0 )
          __int2c();
        if ( v13[1]-- == 1 )
          *v13 = v14 & 0xFFFFFFFFFFFFFFFEuLL;
      }
      dword_18004FFC8 = 0;
      RtlReleaseSRWLockExclusive(&g_ConsumerUpdateLock);
      UbpmpCloseTriggerConsumer(v10);
      if ( v5 )
        break;
    }
  }
  if ( v4 )
    UBPM_MIDL_user_free(v4, v1, v2, v3);
  return v5;
}

```

## disassembly

```asm
0x180011640  push    r12
0x180011642  push    r15
0x180011644  sub     rsp, 48h
0x180011648  mov     [rsp+58h+var_30], r13
0x18001164d  xor     r13d, r13d
0x180011650  mov     [rsp+58h+Status], r13d
0x180011655  mov     [rsp+58h+arg_0], r13d
0x18001165a  mov     [rsp+58h+arg_10], r13
0x18001165f  call    UbpmpAcquireListLockShared
0x180011664  lea     rdx, [rsp+58h+arg_0]
0x180011669  lea     rcx, [rsp+58h+arg_10]
0x18001166e  call    UbpmConsumerSnapListCopy
0x180011673  mov     r12, [rsp+58h+arg_10]
0x180011678  mov     r15d, eax
0x18001167b  test    eax, eax
0x18001167d  jz      short loc_1800116A0
0x18001167f  mov     r13, [rsp+58h+var_30]
0x180011684  test    r12, r12
0x180011687  jnz     short loc_180011696
0x180011689  mov     eax, r15d
0x18001168c  add     rsp, 48h
0x180011690  pop     r15
0x180011692  pop     r12
0x180011694  retn
0x180011696  mov     rcx, r12
0x180011699  call    UBPM_MIDL_user_free
0x18001169e  jmp     short loc_180011689
0x1800116a0  mov     [rsp+58h+var_28], rdi
0x1800116a5  mov     [rsp+58h+var_38], r14
0x1800116aa  call    UbpmpReleaseListLockShared
0x1800116af  mov     r14d, [rsp+58h+arg_0]
0x1800116b4  mov     edi, r13d
0x1800116b7  test    r14d, r14d
0x1800116ba  jz      loc_1800117E9
0x1800116c0  mov     [rsp+58h+arg_18], rbx
0x1800116c5  mov     [rsp+58h+var_18], rbp
0x1800116ca  mov     [rsp+58h+var_20], rsi
0x1800116cf  nop
0x1800116d0  mov     ebp, cs:UbpmpLockTrackerId
0x1800116d6  mov     eax, edi
0x1800116d8  mov     rsi, [r12+rax*8]
0x1800116dc  cmp     ebp, 0FFFFFFFFh
0x1800116df  jz      short loc_180011711
0x1800116e1  mov     ecx, ebp; dwTlsIndex
0x1800116e3  call    cs:__imp_TlsGetValue
0x1800116ea  nop     dword ptr [rax+rax+00h]
0x1800116ef  mov     ecx, ebp; dwTlsIndex
0x1800116f1  mov     rbx, rax
0x1800116f4  call    cs:__imp_TlsGetValue
0x1800116fb  nop     dword ptr [rax+rax+00h]
0x180011700  cmp     [rax], r13
0x180011703  jnz     loc_18001187C
0x180011709  or      qword ptr [rbx], 1
0x18001170d  inc     qword ptr [rbx+8]
0x180011711  lea     rcx, ?g_ConsumerUpdateLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerUpdateLock
0x180011718  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001171f  nop     dword ptr [rax+rax+00h]
0x180011724  call    cs:__imp_GetCurrentThreadId
0x18001172b  nop     dword ptr [rax+rax+00h]
0x180011730  lea     rcx, [rsi+30h]
0x180011734  mov     cs:dword_18004FFC8, eax
0x18001173a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180011741  nop     dword ptr [rax+rax+00h]
0x180011746  call    cs:__imp_GetCurrentThreadId
0x18001174d  nop     dword ptr [rax+rax+00h]
0x180011752  mov     [rsi+38h], eax
0x180011755  mov     rax, [rsi+18h]
0x180011759  cmp     [rax+30h], r13
0x18001175d  jnz     loc_1800117F8
0x180011763  lea     rcx, [rsi+30h]
0x180011767  mov     [rsi+38h], r13d
0x18001176b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180011772  nop     dword ptr [rax+rax+00h]
0x180011777  mov     ecx, cs:UbpmpLockTrackerId; dwTlsIndex
0x18001177d  cmp     ecx, 0FFFFFFFFh
0x180011780  jz      short loc_1800117A8
0x180011782  call    cs:__imp_TlsGetValue
0x180011789  nop     dword ptr [rax+rax+00h]
0x18001178e  mov     rdx, [rax]
0x180011791  test    dl, 1
0x180011794  jz      loc_180011875
0x18001179a  sub     qword ptr [rax+8], 1
0x18001179f  jnz     short loc_1800117A8
0x1800117a1  and     rdx, 0FFFFFFFFFFFFFFFEh
0x1800117a5  mov     [rax], rdx
0x1800117a8  lea     rcx, ?g_ConsumerUpdateLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerUpdateLock
0x1800117af  mov     cs:dword_18004FFC8, r13d
0x1800117b6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800117bd  nop     dword ptr [rax+rax+00h]
0x1800117c2  mov     rcx, rsi
0x1800117c5  call    UbpmpCloseTriggerConsumer
0x1800117ca  test    r15d, r15d
0x1800117cd  jnz     short loc_1800117DA
0x1800117cf  inc     edi
0x1800117d1  cmp     edi, r14d
0x1800117d4  jb      loc_1800116D0
0x1800117da  mov     rbp, [rsp+58h+var_18]
0x1800117df  mov     rsi, [rsp+58h+var_20]
0x1800117e4  mov     rbx, [rsp+58h+arg_18]
0x1800117e9  mov     rdi, [rsp+58h+var_28]
0x1800117ee  mov     r14, [rsp+58h+var_38]
0x1800117f3  jmp     loc_18001167F
0x1800117f8  test    byte ptr [rax+10h], 1
0x1800117fc  jnz     loc_180011763
0x180011802  mov     rcx, rsi
0x180011805  call    UbpmConsumerIsUnregistered
0x18001180a  test    al, al
0x18001180c  jnz     loc_180011763
0x180011812  lea     rcx, [rsi+0D0h]
0x180011819  call    cs:__imp_RtlAcquireSRWLockShared
0x180011820  nop     dword ptr [rax+rax+00h]
0x180011825  lea     rcx, [rsi+110h]; Uuid
0x18001182c  lea     rdx, [rsp+58h+Status]; Status
0x180011831  call    cs:__imp_UuidIsNil
0x180011838  nop     dword ptr [rax+rax+00h]
0x18001183d  test    eax, eax
0x18001183f  jz      short loc_18001185D
0x180011841  lea     rax, [rsi+100h]
0x180011848  cmp     [rax], rax
0x18001184b  jnz     short loc_18001185D
0x18001184d  mov     rcx, rsi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x180011850  call    ?UbpmpMaintenanceEvaluateTriggersForConsumer@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@@Z; UbpmpMaintenanceEvaluateTriggersForConsumer(_UBPM_TRIGGER_CONSUMER_BLOCK *)
0x180011855  mov     r15d, eax
0x180011858  jmp     loc_180011763
0x18001185d  lea     rcx, [rsi+0D0h]
0x180011864  call    cs:__imp_RtlReleaseSRWLockShared
0x18001186b  nop     dword ptr [rax+rax+00h]
0x180011870  jmp     loc_180011763
0x180011875  int     2Ch; Windows NT - assertion failure
0x180011877  jmp     loc_18001179A
0x18001187c  int     2Ch; Windows NT - assertion failure
0x18001187e  jmp     loc_180011709
```
