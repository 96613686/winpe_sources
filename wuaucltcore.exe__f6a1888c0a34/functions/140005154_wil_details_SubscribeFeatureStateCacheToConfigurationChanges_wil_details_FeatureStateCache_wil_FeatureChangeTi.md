# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x140005154`
- end: `0x1400051e3`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `143`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009c30`
- `0x14000a14c`
- `0x140013764`
- `0x140014094`
- `0x140014378`
- `0x140014674`
- `0x14001a220`

## callees

- `0x140004b40`
- `0x140005154`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400051cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400051cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000517b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000517b`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  unsigned __int64 v6; // r8
  _DWORD v7[2]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v8; // [rsp+28h] [rbp-10h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_14002E5AC
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002E5E0, v7, v6)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x140005154  mov     [rsp+arg_10], rbx
0x140005159  mov     [rsp+arg_18], rsi
0x14000515e  push    rdi
0x14000515f  sub     rsp, 30h
0x140005163  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000516a  mov     esi, r8d
0x14000516d  mov     edi, edx
0x14000516f  mov     rbx, rcx
0x140005172  jz      short loc_1400051D3
0x140005174  lea     rcx, SRWLock; SRWLock
0x14000517b  call    cs:__imp_AcquireSRWLockExclusive
0x140005181  mov     eax, cs:dword_14002E5AC
0x140005187  test    esi, esi
0x140005189  jz      short loc_1400051B5
0x14000518b  cmp     esi, eax
0x14000518d  jnz     short loc_1400051B5
0x14000518f  lea     rdx, [rsp+38h+var_18]; void *
0x140005194  mov     [rsp+38h+var_14], 0
0x14000519c  lea     rcx, qword_14002E5E0; this
0x1400051a3  mov     [rsp+38h+var_18], edi
0x1400051a7  mov     [rsp+38h+var_10], rbx
0x1400051ac  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1400051b1  test    al, al
0x1400051b3  jnz     short loc_1400051C6
0x1400051b5  neg     edi
0x1400051b7  sbb     eax, eax
0x1400051b9  and     eax, 83Ah
0x1400051be  add     eax, 0FFFFF7C1h
0x1400051c3  lock and [rbx], eax
0x1400051c6  lea     rcx, SRWLock; SRWLock
0x1400051cd  call    cs:__imp_ReleaseSRWLockExclusive
0x1400051d3  mov     rbx, [rsp+38h+arg_10]
0x1400051d8  mov     rsi, [rsp+38h+arg_18]
0x1400051dd  add     rsp, 30h
0x1400051e1  pop     rdi
0x1400051e2  retn
```
