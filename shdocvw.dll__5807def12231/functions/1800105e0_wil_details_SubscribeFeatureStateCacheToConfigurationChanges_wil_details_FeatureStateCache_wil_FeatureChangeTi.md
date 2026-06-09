# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800105e0`
- end: `0x180010676`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `150`
- prototype: ``
- caller_count: `24`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800027a0`
- `0x18000d3f0`
- `0x18000d4d0`
- `0x18000d630`
- `0x18000d790`
- `0x18000d930`
- `0x18000da10`
- `0x18000db70`
- `0x18000dcd0`
- `0x18000de30`
- `0x18000df90`
- `0x18000e070`
- `0x18000e150`
- `0x18000e230`
- `0x18000e310`
- `0x18000e3f0`
- `0x18000e4d0`
- `0x180015fc4`
- `0x180016164`
- `0x180016244`
- `0x1800163a0`
- `0x180016480`
- `0x180016560`
- `0x180022bf8`

## callees

- `0x180003b30`
- `0x1800105e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010608`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010608`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010660`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010660`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD v6[2]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-10h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_18003855C
      || (v6[1] = 0,
          v6[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180038580, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x1800105e0  mov     [rsp+arg_0], rbx
0x1800105e5  mov     [rsp+arg_8], rsi
0x1800105ea  push    rdi
0x1800105eb  sub     rsp, 30h
0x1800105ef  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800105f5  mov     esi, r8d
0x1800105f8  mov     ebx, edx
0x1800105fa  mov     rdi, rcx
0x1800105fd  test    eax, eax
0x1800105ff  jz      short loc_180010666
0x180010601  lea     rcx, SRWLock; SRWLock
0x180010608  call    cs:__imp_AcquireSRWLockExclusive
0x18001060e  mov     eax, cs:dword_18003855C
0x180010614  test    esi, esi
0x180010616  jz      short loc_180010648
0x180010618  cmp     esi, eax
0x18001061a  jnz     short loc_180010648
0x18001061c  mov     r8d, 10h; unsigned __int64
0x180010622  mov     [rsp+38h+var_14], 0
0x18001062a  lea     rdx, [rsp+38h+var_18]; void *
0x18001062f  mov     [rsp+38h+var_18], ebx
0x180010633  lea     rcx, qword_180038580; this
0x18001063a  mov     [rsp+38h+var_10], rdi
0x18001063f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180010644  test    al, al
0x180010646  jnz     short loc_180010659
0x180010648  neg     ebx
0x18001064a  sbb     eax, eax
0x18001064c  and     eax, 83Ah
0x180010651  add     eax, 0FFFFF7C1h
0x180010656  lock and [rdi], eax
0x180010659  lea     rcx, SRWLock; SRWLock
0x180010660  call    cs:__imp_ReleaseSRWLockExclusive
0x180010666  mov     rbx, [rsp+38h+arg_0]
0x18001066b  mov     rsi, [rsp+38h+arg_8]
0x180010670  add     rsp, 30h
0x180010674  pop     rdi
0x180010675  retn
```
