# RQueryServiceConfigEx

- ea: `0x140028140`
- end: `0x14002829b`
- name: `RQueryServiceConfigEx`
- size: `347`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140002890`
- `0x1400083f0`
- `0x14000ac50`
- `0x14000bebc`
- `0x140028140`
- `0x1400282a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400281b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400281b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140028245`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140028245`
- `ntdll!RtlReleaseResource` at `0x140028252`
- `ntdll!RtlReleaseResource` at `0x140028291`
- `ntdll!RtlReleaseResource` at `0x140028252`
- `ntdll!RtlReleaseResource` at `0x140028291`
- `ntdll!RtlAcquireResourceShared` at `0x14002819f`
- `ntdll!RtlAcquireResourceShared` at `0x14002819f`
- `ntdll!RtlAreAllAccessesGranted` at `0x14002817c`
- `ntdll!RtlAreAllAccessesGranted` at `0x14002817c`
- `ntdll!NtClose` at `0x14002822f`
- `ntdll!NtClose` at `0x14002822f`
- `ntdll!RtlNtStatusToDosError` at `0x140028237`
- `ntdll!RtlNtStatusToDosError` at `0x140028237`

## pseudocode

```c
__int64 __fastcall RQueryServiceConfigEx(ACCESS_MASK *a1, int a2, __int64 a3)
{
  __int64 v6; // rdi
  RTL_SRWLOCK *v7; // rbx
  __int64 v8; // r8
  unsigned int v9; // esi
  unsigned int TriggerInfo; // edi
  NTSTATUS v11; // eax
  _QWORD v13[7]; // [rsp+40h] [rbp-38h] BYREF
  HANDLE Handle; // [rsp+98h] [rbp+20h] BYREF

  ScSetTcpKeepalive();
  if ( ScShutdownInProgress )
    return 1115;
  if ( !(unsigned int)ScIsValidServiceHandle(a1) )
    return 6;
  if ( !RtlAreAllAccessesGranted(a1[2], 1u) )
    return 5;
  if ( a2 != 8 )
    return 124;
  *(_DWORD *)a3 = 8;
  RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
  v6 = *((_QWORD *)a1 + 2);
  v7 = (RTL_SRWLOCK *)(v6 + 312);
  AcquireSRWLockShared((PSRWLOCK)(v6 + 312));
  v13[0] = v6 + 312;
  Handle = 0;
  v9 = CServiceRecord::OpenServiceConfigKey((CServiceRecord *)v6, 0x20019u, v8, (HKEY *)&Handle);
  if ( v9 )
  {
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v13);
    RtlReleaseResource(&ScServiceRecordLock);
    return v9;
  }
  else
  {
    TriggerInfo = ScGetTriggerInfo(
                    *(struct _SERVICE_CONFIG_ROOT **)(v6 + 216),
                    *(const unsigned __int16 **)(v6 + 56),
                    (HKEY)Handle,
                    *(_DWORD *)(v6 + 80),
                    1,
                    (*(_DWORD *)(v6 + 168) >> 1) & 1,
                    (struct _SERVICE_TRIGGER_INFO **)(a3 + 8));
    v11 = NtClose(Handle);
    RtlNtStatusToDosError(v11);
    if ( v7 )
      ReleaseSRWLockShared(v7);
    RtlReleaseResource(&ScServiceRecordLock);
    return TriggerInfo;
  }
}

```

## disassembly

```asm
0x140028140  push    rbx
0x140028142  push    rsi
0x140028143  push    rdi
0x140028144  push    r14
0x140028146  sub     rsp, 58h
0x14002814a  mov     r14, r8
0x14002814d  mov     edi, edx
0x14002814f  mov     rbx, rcx
0x140028152  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x140028157  cmp     cs:?ScShutdownInProgress@@3KA, 0; ulong ScShutdownInProgress
0x14002815e  jnz     loc_140028264
0x140028164  mov     rcx, rbx; void *
0x140028167  call    ?ScIsValidServiceHandle@@YAHPEAX@Z; ScIsValidServiceHandle(void *)
0x14002816c  test    eax, eax
0x14002816e  jz      loc_14002826B
0x140028174  mov     ecx, [rbx+8]; GrantedAccess
0x140028177  mov     edx, 1; DesiredAccess
0x14002817c  call    cs:__imp_RtlAreAllAccessesGranted
0x140028182  test    al, al
0x140028184  jz      loc_140028272
0x14002818a  cmp     edi, 8
0x14002818d  jnz     loc_140028279
0x140028193  mov     dl, 1; Wait
0x140028195  mov     [r14], edi
0x140028198  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14002819f  call    cs:__imp_RtlAcquireResourceShared
0x1400281a5  mov     rdi, [rbx+10h]
0x1400281a9  lea     rbx, [rdi+138h]
0x1400281b0  mov     rcx, rbx; SRWLock
0x1400281b3  call    cs:__imp_AcquireSRWLockShared
0x1400281b9  lea     r9, [rsp+78h+Handle]; HKEY *
0x1400281c1  mov     [rsp+78h+var_38], rbx
0x1400281c6  mov     edx, 20019h; unsigned int
0x1400281cb  mov     [rsp+78h+Handle], 0
0x1400281d7  mov     rcx, rdi; this
0x1400281da  call    ?OpenServiceConfigKey@CServiceRecord@@QEAAKKHPEAPEAUHKEY__@@@Z; CServiceRecord::OpenServiceConfigKey(ulong,int,HKEY__ * *)
0x1400281df  mov     esi, eax
0x1400281e1  test    eax, eax
0x1400281e3  jnz     loc_140028280
0x1400281e9  mov     edx, [rdi+0A8h]
0x1400281ef  lea     rax, [r14+8]
0x1400281f3  mov     r9d, [rdi+50h]; unsigned int
0x1400281f7  mov     r8, [rsp+78h+Handle]; HKEY
0x1400281ff  mov     rcx, [rdi+0D8h]; struct _SERVICE_CONFIG_ROOT *
0x140028206  shr     edx, 1
0x140028208  and     edx, 1
0x14002820b  mov     [rsp+78h+var_48], rax; struct _SERVICE_TRIGGER_INFO **
0x140028210  mov     [rsp+78h+var_50], edx; int
0x140028214  mov     rdx, [rdi+38h]; unsigned __int16 *
0x140028218  mov     [rsp+78h+var_58], 1; int
0x140028220  call    ?ScGetTriggerInfo@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEBGPEAUHKEY__@@KHHPEAPEAU_SERVICE_TRIGGER_INFO@@@Z; ScGetTriggerInfo(_SERVICE_CONFIG_ROOT *,ushort const *,HKEY__ *,ulong,int,int,_SERVICE_TRIGGER_INFO * *)
0x140028225  mov     rcx, [rsp+78h+Handle]; Handle
0x14002822d  mov     edi, eax
0x14002822f  call    cs:__imp_NtClose
0x140028235  mov     ecx, eax; Status
0x140028237  call    cs:__imp_RtlNtStatusToDosError
0x14002823d  test    rbx, rbx
0x140028240  jz      short loc_14002824B
0x140028242  mov     rcx, rbx; SRWLock
0x140028245  call    cs:__imp_ReleaseSRWLockShared
0x14002824b  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140028252  call    cs:__imp_RtlReleaseResource
0x140028258  mov     eax, edi
0x14002825a  add     rsp, 58h
0x14002825e  pop     r14
0x140028260  pop     rdi
0x140028261  pop     rsi
0x140028262  pop     rbx
0x140028263  retn
0x140028264  mov     eax, 45Bh
0x140028269  jmp     short loc_14002825A
0x14002826b  mov     eax, 6
0x140028270  jmp     short loc_14002825A
0x140028272  mov     eax, 5
0x140028277  jmp     short loc_14002825A
0x140028279  mov     eax, 7Ch ; '|'
0x14002827e  jmp     short loc_14002825A
0x140028280  lea     rcx, [rsp+78h+var_38]; this
0x140028285  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x14002828a  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140028291  call    cs:__imp_RtlReleaseResource
0x140028297  mov     eax, esi
0x140028299  jmp     short loc_14002825A
```
