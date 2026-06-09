# SmpReadySubSys

- ea: `0x1400011b0`
- end: `0x14000124b`
- name: `SmpReadySubSys`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001f60`

## callees

- `0x1400011b0`
- `0x140017ff0`

## import_xrefs

- `ntdll!NtSetEvent` at `0x14000123c`
- `ntdll!NtSetEvent` at `0x14000123c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400011de`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400011de`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400011f5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400011f5`
- `ntdll!RtlWakeAllConditionVariable` at `0x140001218`

## pseudocode

```c
__int64 __fastcall SmpReadySubSys(__int64 a1, _OWORD *a2)
{
  __int64 v4; // rdi
  HANDLE *v6; // rcx

  v4 = SmpKnownSubSysTable + 24LL * (*(_DWORD *)(a1 + 64) & 0x1F);
  RtlAcquireSRWLockExclusive(v4 + 16);
  if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
    *(_OWORD *)(a1 + 48) = *a2;
  else
    *(_DWORD *)(a1 + 24) = *(_DWORD *)a2;
  RtlReleaseSRWLockExclusive(v4 + 16);
  if ( *(_QWORD *)(a1 + 16) )
  {
    v6 = (HANDLE *)_InterlockedExchange64((volatile __int64 *)(a1 + 16), 0);
    if ( v6 )
    {
      if ( *(_DWORD *)v6 )
        NtSetEvent(v6[1], 0);
      else
        SmpDisposeSubSysSynch(v6);
    }
  }
  return RtlWakeAllConditionVariable(&SmpSubSysReadyCondition);
}

```

## disassembly

```asm
0x1400011b0  mov     [rsp+arg_0], rbx
0x1400011b5  mov     [rsp+arg_8], rsi
0x1400011ba  push    rdi
0x1400011bb  sub     rsp, 20h
0x1400011bf  mov     eax, [rcx+40h]
0x1400011c2  mov     rbx, rcx
0x1400011c5  and     eax, 1Fh
0x1400011c8  mov     rsi, rdx
0x1400011cb  lea     rcx, [rax+rax*2]
0x1400011cf  mov     rax, cs:SmpKnownSubSysTable
0x1400011d6  lea     rdi, [rax+rcx*8]
0x1400011da  lea     rcx, [rdi+10h]
0x1400011de  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1400011e4  test    byte ptr [rbx+8], 1
0x1400011e8  jz      short loc_14000121F
0x1400011ea  movups  xmm0, xmmword ptr [rsi]
0x1400011ed  movups  xmmword ptr [rbx+30h], xmm0
0x1400011f1  lea     rcx, [rdi+10h]
0x1400011f5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1400011fb  cmp     qword ptr [rbx+10h], 0
0x140001200  jnz     short loc_140001226
0x140001202  lea     rcx, SmpSubSysReadyCondition
0x140001209  mov     rbx, [rsp+28h+arg_0]
0x14000120e  mov     rsi, [rsp+28h+arg_8]
0x140001213  add     rsp, 20h
0x140001217  pop     rdi
0x140001218  jmp     cs:__imp_RtlWakeAllConditionVariable
0x14000121f  mov     eax, [rsi]
0x140001221  mov     [rbx+18h], eax
0x140001224  jmp     short loc_1400011F1
0x140001226  xor     ecx, ecx
0x140001228  xchg    rcx, [rbx+10h]; BaseAddress
0x14000122c  test    rcx, rcx
0x14000122f  jz      short loc_140001202
0x140001231  cmp     dword ptr [rcx], 0
0x140001234  jbe     short loc_140001244
0x140001236  mov     rcx, [rcx+8]; EventHandle
0x14000123a  xor     edx, edx; PreviousState
0x14000123c  call    cs:__imp_NtSetEvent
0x140001242  jmp     short loc_140001202
0x140001244  call    SmpDisposeSubSysSynch
0x140001249  jmp     short loc_140001202
```
