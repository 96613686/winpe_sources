# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800109d4`
- end: `0x180010a63`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `143`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180014f48`
- `0x1800150d8`
- `0x1800157ec`
- `0x180015ad4`
- `0x180015fe4`
- `0x1800162c8`
- `0x180016464`
- `0x180019924`
- `0x180019cf0`

## callees

- `0x180010418`
- `0x1800109d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800109fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800109fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010a4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010a4d`

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
      || a3 != dword_18004DDDC
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18004DE10, v7, v6)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x1800109d4  mov     [rsp+arg_8], rbx
0x1800109d9  mov     [rsp+arg_10], rsi
0x1800109de  push    rdi
0x1800109df  sub     rsp, 30h
0x1800109e3  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800109ea  mov     esi, r8d
0x1800109ed  mov     ebx, edx
0x1800109ef  mov     rdi, rcx
0x1800109f2  jz      short loc_180010A53
0x1800109f4  lea     rcx, SRWLock; SRWLock
0x1800109fb  call    cs:__imp_AcquireSRWLockExclusive
0x180010a01  mov     eax, cs:dword_18004DDDC
0x180010a07  test    esi, esi
0x180010a09  jz      short loc_180010A35
0x180010a0b  cmp     esi, eax
0x180010a0d  jnz     short loc_180010A35
0x180010a0f  lea     rdx, [rsp+38h+var_18]; void *
0x180010a14  mov     [rsp+38h+var_14], 0
0x180010a1c  lea     rcx, qword_18004DE10; this
0x180010a23  mov     [rsp+38h+var_18], ebx
0x180010a27  mov     [rsp+38h+var_10], rdi
0x180010a2c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180010a31  test    al, al
0x180010a33  jnz     short loc_180010A46
0x180010a35  neg     ebx
0x180010a37  sbb     eax, eax
0x180010a39  and     eax, 83Ah
0x180010a3e  add     eax, 0FFFFF7C1h
0x180010a43  lock and [rdi], eax
0x180010a46  lea     rcx, SRWLock; SRWLock
0x180010a4d  call    cs:__imp_ReleaseSRWLockExclusive
0x180010a53  mov     rbx, [rsp+38h+arg_8]
0x180010a58  mov     rsi, [rsp+38h+arg_10]
0x180010a5d  add     rsp, 30h
0x180010a61  pop     rdi
0x180010a62  retn
```
