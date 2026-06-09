# RQueryServiceStatusEx

- ea: `0x1400206c0`
- end: `0x14002085b`
- name: `RQueryServiceStatusEx`
- size: `411`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x140005584`
- `0x1400083f0`
- `0x1400206c0`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400207bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400207bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140020824`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140020824`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002079b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002079b`
- `ntdll!RtlAcquireResourceExclusive` at `0x140020767`
- `ntdll!RtlAcquireResourceExclusive` at `0x140020767`
- `ntdll!RtlReleaseResource` at `0x1400207a8`
- `ntdll!RtlReleaseResource` at `0x140020831`
- `ntdll!RtlReleaseResource` at `0x1400207a8`
- `ntdll!RtlReleaseResource` at `0x140020831`
- `ntdll!RtlAcquireResourceShared` at `0x1400207b3`
- `ntdll!RtlAcquireResourceShared` at `0x1400207b3`
- `ntdll!RtlAreAllAccessesGranted` at `0x140020709`
- `ntdll!RtlAreAllAccessesGranted` at `0x140020709`

## pseudocode

```c
__int64 __fastcall RQueryServiceStatusEx(__int64 a1, int a2, __int64 a3, unsigned int a4, _DWORD *a5)
{
  __int64 v10; // rdi
  unsigned int v11; // ebx

  ScSetTcpKeepalive();
  if ( ScShutdownInProgress )
    return 1115;
  if ( !a1 || *(_DWORD *)a1 != 1215456627 )
    return 6;
  if ( !RtlAreAllAccessesGranted(*(_DWORD *)(a1 + 8), 4u) )
    return 5;
  if ( a2 )
    return 124;
  v10 = *(_QWORD *)(a1 + 16);
  *a5 = 36;
  if ( a4 < 0x24 )
    return 122;
  *(_QWORD *)(a3 + 28) = 0;
  if ( (*(_BYTE *)(v10 + 80) & 0xB) != 0 )
  {
    RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
    CScmLock::LockExclusive((CScmLock *)(v10 + 312));
    v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 152LL))(v10, a3);
    if ( v10 != -312 )
    {
      *(_DWORD *)(v10 + 320) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(v10 + 312));
    }
    RtlReleaseResource(&ScServiceRecordLock);
  }
  else
  {
    RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
    AcquireSRWLockShared((PSRWLOCK)(v10 + 312));
    *(_OWORD *)a3 = *(_OWORD *)(v10 + 80);
    *(_OWORD *)(a3 + 12) = *(_OWORD *)(v10 + 92);
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 160LL))(v10) )
    {
      *(_DWORD *)(a3 + 28) = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 160LL))(v10) + 40);
      if ( (*(_BYTE *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 160LL))(v10) + 104) & 2) != 0 )
        *(_DWORD *)(a3 + 32) |= 1u;
    }
    if ( v10 != -312 )
      ReleaseSRWLockShared((PSRWLOCK)(v10 + 312));
    RtlReleaseResource(&ScServiceRecordLock);
    if ( (*(_DWORD *)(v10 + 52) & 0x40000) != 0 )
      *(_DWORD *)(a3 + 24) = 2000;
    return 0;
  }
  return v11;
}

```

## disassembly

```asm
0x1400206c0  push    rbx
0x1400206c2  push    rbp
0x1400206c3  push    rsi
0x1400206c4  push    rdi
0x1400206c5  sub     rsp, 28h
0x1400206c9  mov     ebp, r9d
0x1400206cc  mov     rbx, r8
0x1400206cf  mov     esi, edx
0x1400206d1  mov     rdi, rcx
0x1400206d4  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x1400206d9  cmp     cs:?ScShutdownInProgress@@3KA, 0; ulong ScShutdownInProgress
0x1400206e0  jz      short loc_1400206EC
0x1400206e2  mov     eax, 45Bh
0x1400206e7  jmp     loc_140020852
0x1400206ec  test    rdi, rdi
0x1400206ef  jz      loc_14002084D
0x1400206f5  cmp     dword ptr [rdi], 48726573h
0x1400206fb  jnz     loc_14002084D
0x140020701  mov     ecx, [rdi+8]; GrantedAccess
0x140020704  mov     edx, 4; DesiredAccess
0x140020709  call    cs:__imp_RtlAreAllAccessesGranted
0x14002070f  test    al, al
0x140020711  jnz     short loc_14002071D
0x140020713  mov     eax, 5
0x140020718  jmp     loc_140020852
0x14002071d  test    esi, esi
0x14002071f  jz      short loc_14002072B
0x140020721  mov     eax, 7Ch ; '|'
0x140020726  jmp     loc_140020852
0x14002072b  mov     rax, [rsp+48h+arg_20]
0x140020730  mov     rdi, [rdi+10h]
0x140020734  mov     dword ptr [rax], 24h ; '$'
0x14002073a  cmp     ebp, 24h ; '$'
0x14002073d  jnb     short loc_140020749
0x14002073f  mov     eax, 7Ah ; 'z'
0x140020744  jmp     loc_140020852
0x140020749  mov     qword ptr [rbx+1Ch], 0
0x140020751  lea     rsi, [rdi+138h]
0x140020758  test    byte ptr [rdi+50h], 0Bh
0x14002075c  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140020763  mov     dl, 1; Wait
0x140020765  jz      short loc_1400207B3
0x140020767  call    cs:__imp_RtlAcquireResourceExclusive
0x14002076d  mov     rcx, rsi; this
0x140020770  call    ?LockExclusive@CScmLock@@QEAAXXZ; CScmLock::LockExclusive(void)
0x140020775  mov     rax, [rdi]
0x140020778  mov     rdx, rbx
0x14002077b  mov     rcx, rdi
0x14002077e  mov     rax, [rax+98h]
0x140020785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002078a  mov     ebx, eax
0x14002078c  test    rsi, rsi
0x14002078f  jz      short loc_1400207A1
0x140020791  mov     rcx, rsi; SRWLock
0x140020794  mov     dword ptr [rsi+8], 0
0x14002079b  call    cs:__imp_ReleaseSRWLockExclusive
0x1400207a1  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x1400207a8  call    cs:__imp_RtlReleaseResource
0x1400207ae  jmp     loc_140020849
0x1400207b3  call    cs:__imp_RtlAcquireResourceShared
0x1400207b9  mov     rcx, rsi; SRWLock
0x1400207bc  call    cs:__imp_AcquireSRWLockShared
0x1400207c2  movups  xmm0, xmmword ptr [rdi+50h]
0x1400207c6  mov     rcx, rdi
0x1400207c9  movups  xmmword ptr [rbx], xmm0
0x1400207cc  movups  xmm1, xmmword ptr [rdi+5Ch]
0x1400207d0  movups  xmmword ptr [rbx+0Ch], xmm1
0x1400207d4  mov     rax, [rdi]
0x1400207d7  mov     rax, [rax+0A0h]
0x1400207de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400207e3  test    rax, rax
0x1400207e6  jz      short loc_14002081C
0x1400207e8  mov     rax, [rdi]
0x1400207eb  mov     rcx, rdi
0x1400207ee  mov     rax, [rax+0A0h]
0x1400207f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400207fa  mov     ecx, [rax+28h]
0x1400207fd  mov     [rbx+1Ch], ecx
0x140020800  mov     rcx, rdi
0x140020803  mov     rax, [rdi]
0x140020806  mov     rax, [rax+0A0h]
0x14002080d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020812  test    byte ptr [rax+68h], 2
0x140020816  jz      short loc_14002081C
0x140020818  or      dword ptr [rbx+20h], 1
0x14002081c  test    rsi, rsi
0x14002081f  jz      short loc_14002082A
0x140020821  mov     rcx, rsi; SRWLock
0x140020824  call    cs:__imp_ReleaseSRWLockShared
0x14002082a  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140020831  call    cs:__imp_RtlReleaseResource
0x140020837  mov     eax, [rdi+34h]
0x14002083a  bt      eax, 12h
0x14002083e  jnb     short loc_140020847
0x140020840  mov     dword ptr [rbx+18h], 7D0h
0x140020847  xor     ebx, ebx
0x140020849  mov     eax, ebx
0x14002084b  jmp     short loc_140020852
0x14002084d  mov     eax, 6
0x140020852  add     rsp, 28h
0x140020856  pop     rdi
0x140020857  pop     rsi
0x140020858  pop     rbp
0x140020859  pop     rbx
0x14002085a  retn
```
