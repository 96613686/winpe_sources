# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18002bbf8`
- end: `0x18002bd37`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002de00`

## callees

- `0x180024d20`
- `0x18002b074`
- `0x18002bbf8`
- `0x18002e454`
- `0x18002f0c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bca7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bca7`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(
        wil::details *a1,
        unsigned int a2,
        unsigned __int8 a3,
        int a4,
        _DWORD *a5)
{
  int v5; // esi
  __int64 *v7; // rbx
  unsigned int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  int v13; // edx
  bool v14; // si
  char v15; // al
  RTL_SRWLOCK *v16; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v17[6]; // [rsp+28h] [rbp-30h] BYREF
  int v18; // [rsp+78h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v18 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, v5, &v18);
    v13 = v18;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v18 != 0) + 6);
    if ( !v13 && (v15 & 4) == 0 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v11
        || v11 != dword_1800443A4
        || (v17[0] = 0,
            v17[1] = v7,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800443D8, v17, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)v7, 0xFFFFF7C1);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
    return v14;
  }
}

```

## disassembly

```asm
0x18002bbf8  mov     [rsp+arg_0], rbx
0x18002bbfd  mov     [rsp+arg_8], rbp
0x18002bc02  push    rsi
0x18002bc03  push    rdi
0x18002bc04  push    r14
0x18002bc06  sub     rsp, 40h
0x18002bc0a  test    r9d, r9d
0x18002bc0d  movzx   esi, r8b
0x18002bc11  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18002bc18  mov     ebp, edx
0x18002bc1a  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18002bc21  mov     r14, rcx
0x18002bc24  cmovnz  rbx, rax
0x18002bc28  mov     r9d, [rbx]
0x18002bc2b  mov     eax, r9d
0x18002bc2e  and     al, 3
0x18002bc30  cmp     al, 2
0x18002bc32  jnz     short loc_18002BC3B
0x18002bc34  xor     al, al
0x18002bc36  jmp     loc_18002BD23
0x18002bc3b  test    r9b, 2
0x18002bc3f  jnz     loc_18002BD05
0x18002bc45  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002bc4a  mov     rcx, [rsp+58h+arg_20]
0x18002bc52  lea     r9, [rsp+58h+arg_18]
0x18002bc57  mov     r8d, esi
0x18002bc5a  mov     [rsp+58h+arg_18], 0
0x18002bc62  mov     edx, ebp
0x18002bc64  mov     edi, eax
0x18002bc66  mov     dword ptr [rcx], 1
0x18002bc6c  mov     rcx, r14
0x18002bc6f  call    wil_RtlStagingConfig_QueryFeatureState
0x18002bc74  mov     edx, [rsp+58h+arg_18]
0x18002bc78  test    eax, eax
0x18002bc7a  mov     ecx, edx
0x18002bc7c  setnz   sil
0x18002bc80  neg     ecx
0x18002bc82  sbb     eax, eax
0x18002bc84  neg     eax
0x18002bc86  add     eax, 6
0x18002bc89  xchg    eax, [rbx]
0x18002bc8b  test    edx, edx
0x18002bc8d  jnz     short loc_18002BD00
0x18002bc8f  test    al, 4
0x18002bc91  jnz     short loc_18002BD00
0x18002bc93  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002bc99  test    eax, eax
0x18002bc9b  jz      short loc_18002BD00
0x18002bc9d  lea     rbp, SRWLock
0x18002bca4  mov     rcx, rbp; SRWLock
0x18002bca7  call    cs:__imp_AcquireSRWLockExclusive
0x18002bcae  nop     dword ptr [rax+rax+00h]
0x18002bcb3  mov     eax, cs:dword_1800443A4
0x18002bcb9  mov     [rsp+58h+var_38], rbp
0x18002bcbe  test    edi, edi
0x18002bcc0  jz      short loc_18002BCEF
0x18002bcc2  cmp     edi, eax
0x18002bcc4  jnz     short loc_18002BCEF
0x18002bcc6  mov     r8d, 10h; unsigned __int64
0x18002bccc  mov     [rsp+58h+var_30], 0
0x18002bcd5  lea     rdx, [rsp+58h+var_30]; void *
0x18002bcda  mov     [rsp+58h+var_28], rbx
0x18002bcdf  lea     rcx, qword_1800443D8; this
0x18002bce6  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002bceb  test    al, al
0x18002bced  jnz     short loc_18002BCF6
0x18002bcef  lock and dword ptr [rbx], 0FFFFF7C1h
0x18002bcf6  lea     rcx, [rsp+58h+var_38]
0x18002bcfb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002bd00  mov     al, sil
0x18002bd03  jmp     short loc_18002BD23
0x18002bd05  mov     rax, [rsp+58h+arg_20]
0x18002bd0d  mov     r8d, esi
0x18002bd10  xor     r9d, r9d
0x18002bd13  mov     dword ptr [rax], 1
0x18002bd19  call    wil_RtlStagingConfig_QueryFeatureState
0x18002bd1e  test    eax, eax
0x18002bd20  setnz   al
0x18002bd23  mov     rbx, [rsp+58h+arg_0]
0x18002bd28  mov     rbp, [rsp+58h+arg_8]
0x18002bd2d  add     rsp, 40h
0x18002bd31  pop     r14
0x18002bd33  pop     rdi
0x18002bd34  pop     rsi
0x18002bd35  retn
```
