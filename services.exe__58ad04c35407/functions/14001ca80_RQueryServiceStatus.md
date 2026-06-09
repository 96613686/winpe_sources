# RQueryServiceStatus

- ea: `0x14001ca80`
- end: `0x14001cbaa`
- name: `RQueryServiceStatus`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x140005584`
- `0x1400083f0`
- `0x14001ca80`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001cb4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001cb4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001cb6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001cb6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001cb2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001cb2c`
- `ntdll!RtlAcquireResourceExclusive` at `0x14001caf8`
- `ntdll!RtlAcquireResourceExclusive` at `0x14001caf8`
- `ntdll!RtlReleaseResource` at `0x14001cb39`
- `ntdll!RtlReleaseResource` at `0x14001cb79`
- `ntdll!RtlReleaseResource` at `0x14001cb39`
- `ntdll!RtlReleaseResource` at `0x14001cb79`
- `ntdll!RtlAcquireResourceShared` at `0x14001cb41`
- `ntdll!RtlAcquireResourceShared` at `0x14001cb41`
- `ntdll!RtlAreAllAccessesGranted` at `0x14001caca`
- `ntdll!RtlAreAllAccessesGranted` at `0x14001caca`

## pseudocode

```c
__int64 __fastcall RQueryServiceStatus(__int64 a1, __int64 a2)
{
  __int64 v5; // rdi
  __int64 v6; // rbx
  unsigned int v7; // edi

  ScSetTcpKeepalive();
  if ( ScShutdownInProgress )
    return 1115;
  if ( !a1 || *(_DWORD *)a1 != 1215456627 )
    return 6;
  if ( !RtlAreAllAccessesGranted(*(_DWORD *)(a1 + 8), 4u) )
    return 5;
  v5 = *(_QWORD *)(a1 + 16);
  v6 = v5 + 312;
  if ( (*(_BYTE *)(v5 + 80) & 0xB) != 0 )
  {
    RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
    CScmLock::LockExclusive((CScmLock *)(v5 + 312));
    v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 152LL))(v5, a2);
    if ( v6 )
    {
      *(_DWORD *)(v6 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v6);
    }
    RtlReleaseResource(&ScServiceRecordLock);
  }
  else
  {
    RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
    AcquireSRWLockShared((PSRWLOCK)(v5 + 312));
    if ( a2 )
    {
      *(_OWORD *)a2 = *(_OWORD *)(v5 + 80);
      *(_OWORD *)(a2 + 12) = *(_OWORD *)(v5 + 92);
    }
    if ( v5 != -312 )
      ReleaseSRWLockShared((PSRWLOCK)(v5 + 312));
    RtlReleaseResource(&ScServiceRecordLock);
    if ( (*(_DWORD *)(v5 + 52) & 0x40000) != 0 )
      *(_DWORD *)(a2 + 24) = 2000;
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x14001ca80  mov     [rsp+arg_0], rbx
0x14001ca85  mov     [rsp+arg_8], rsi
0x14001ca8a  push    rdi
0x14001ca8b  sub     rsp, 20h
0x14001ca8f  mov     rsi, rdx
0x14001ca92  mov     rdi, rcx
0x14001ca95  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x14001ca9a  cmp     cs:?ScShutdownInProgress@@3KA, 0; ulong ScShutdownInProgress
0x14001caa1  jz      short loc_14001CAAD
0x14001caa3  mov     eax, 45Bh
0x14001caa8  jmp     loc_14001CB9A
0x14001caad  test    rdi, rdi
0x14001cab0  jz      loc_14001CB95
0x14001cab6  cmp     dword ptr [rdi], 48726573h
0x14001cabc  jnz     loc_14001CB95
0x14001cac2  mov     ecx, [rdi+8]; GrantedAccess
0x14001cac5  mov     edx, 4; DesiredAccess
0x14001caca  call    cs:__imp_RtlAreAllAccessesGranted
0x14001cad0  test    al, al
0x14001cad2  jnz     short loc_14001CADE
0x14001cad4  mov     eax, 5
0x14001cad9  jmp     loc_14001CB9A
0x14001cade  mov     rdi, [rdi+10h]
0x14001cae2  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14001cae9  mov     dl, 1; Wait
0x14001caeb  test    byte ptr [rdi+50h], 0Bh
0x14001caef  lea     rbx, [rdi+138h]
0x14001caf6  jz      short loc_14001CB41
0x14001caf8  call    cs:__imp_RtlAcquireResourceExclusive
0x14001cafe  mov     rcx, rbx; this
0x14001cb01  call    ?LockExclusive@CScmLock@@QEAAXXZ; CScmLock::LockExclusive(void)
0x14001cb06  mov     rax, [rdi]
0x14001cb09  mov     rdx, rsi
0x14001cb0c  mov     rcx, rdi
0x14001cb0f  mov     rax, [rax+98h]
0x14001cb16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cb1b  mov     edi, eax
0x14001cb1d  test    rbx, rbx
0x14001cb20  jz      short loc_14001CB32
0x14001cb22  mov     rcx, rbx; SRWLock
0x14001cb25  mov     dword ptr [rbx+8], 0
0x14001cb2c  call    cs:__imp_ReleaseSRWLockExclusive
0x14001cb32  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14001cb39  call    cs:__imp_RtlReleaseResource
0x14001cb3f  jmp     short loc_14001CB91
0x14001cb41  call    cs:__imp_RtlAcquireResourceShared
0x14001cb47  mov     rcx, rbx; SRWLock
0x14001cb4a  call    cs:__imp_AcquireSRWLockShared
0x14001cb50  test    rsi, rsi
0x14001cb53  jz      short loc_14001CB64
0x14001cb55  movups  xmm0, xmmword ptr [rdi+50h]
0x14001cb59  movups  xmmword ptr [rsi], xmm0
0x14001cb5c  movups  xmm1, xmmword ptr [rdi+5Ch]
0x14001cb60  movups  xmmword ptr [rsi+0Ch], xmm1
0x14001cb64  test    rbx, rbx
0x14001cb67  jz      short loc_14001CB72
0x14001cb69  mov     rcx, rbx; SRWLock
0x14001cb6c  call    cs:__imp_ReleaseSRWLockShared
0x14001cb72  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14001cb79  call    cs:__imp_RtlReleaseResource
0x14001cb7f  mov     eax, [rdi+34h]
0x14001cb82  bt      eax, 12h
0x14001cb86  jnb     short loc_14001CB8F
0x14001cb88  mov     dword ptr [rsi+18h], 7D0h
0x14001cb8f  xor     edi, edi
0x14001cb91  mov     eax, edi
0x14001cb93  jmp     short loc_14001CB9A
0x14001cb95  mov     eax, 6
0x14001cb9a  mov     rbx, [rsp+28h+arg_0]
0x14001cb9f  mov     rsi, [rsp+28h+arg_8]
0x14001cba4  add     rsp, 20h
0x14001cba8  pop     rdi
0x14001cba9  retn
```
