# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180032ea4`
- end: `0x18003304e`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `426`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033054`
- `0x18003317c`

## callees

- `0x180024d20`
- `0x18002b074`
- `0x18002dfd8`
- `0x18002e454`
- `0x180032ea4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032fba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032fba`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  unsigned int v6; // edx
  int *v7; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v9; // r8d
  int v10; // esi
  int v11; // eax
  int v12; // esi
  int v13; // eax
  bool v14; // zf
  signed __int32 v15; // edx
  signed __int32 v16; // ecx
  _QWORD v18[7]; // [rsp+20h] [rbp-38h] BYREF
  wil::details *v19; // [rsp+60h] [rbp+8h] BYREF
  RTL_SRWLOCK *v20; // [rsp+68h] [rbp+10h] BYREF

  v19 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_UxLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v19) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x3667C9A,
                            v6,
                            (enum FEATURE_CHANGE_TIME)&v19,
                            v7);
    v9 = FeatureEnabledState & 0xFFFFFF3F;
    v10 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v11 = 0;
      if ( v9 == 2 )
        v11 = 64;
    }
    else
    {
      v11 = 64;
    }
    v12 = v11 | v10;
    v13 = *(_DWORD *)a2;
    do
    {
      v14 = (_DWORD)v19 == 0;
      v15 = v13;
      *(_DWORD *)a2 = v13;
      if ( !v14 && (v13 & 2) == 0 )
      {
        v13 = (v13
             ^ ((unsigned __int16)v13
              ^ (unsigned __int16)v12)
             & 0x180
             ^ (v12
              ^ v13
              ^ ((unsigned __int16)v13
               ^ (unsigned __int16)v12)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v12
             ^ ((unsigned __int16)(v13 ^ (v13 ^ v12) & 0x180 ^ (v12 ^ v13 ^ (v13 ^ v12) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v13;
      }
      if ( (v15 & 4) != 0 )
      {
        v16 = v13;
      }
      else
      {
        v16 = v13 ^ ((unsigned __int16)v13 ^ (unsigned __int16)v12) & 0x400 | 4;
        *(_DWORD *)a2 = v16;
      }
      v13 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxLabTest__descriptor, v16, v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v20 = &SRWLock;
      if ( !v5
        || v5 != dword_1800443A4
        || (v18[0] = 3,
            v18[1] = Feature_UxLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800443D8, v18, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_UxLabTest__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v20);
    }
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v12
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v12
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v12
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v12
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v12
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v12
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v12
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x180032ea4  mov     [rsp+arg_10], rbx
0x180032ea9  mov     [rsp+arg_0], rcx
0x180032eae  push    rbp
0x180032eaf  push    rsi
0x180032eb0  push    rdi
0x180032eb1  push    r12
0x180032eb3  push    r14
0x180032eb5  sub     rsp, 30h
0x180032eb9  mov     rdi, cs:Feature_UxLabTest__descriptor
0x180032ec0  mov     rbx, rdx
0x180032ec3  mov     qword ptr [rdx], 0
0x180032eca  mov     eax, [rdi]
0x180032ecc  mov     [rdx], eax
0x180032ece  and     eax, 6
0x180032ed1  cmp     al, 6
0x180032ed3  jz      loc_180033039
0x180032ed9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180032ede  lea     r8, [rsp+58h+arg_0]; enum FEATURE_CHANGE_TIME
0x180032ee3  mov     dword ptr [rsp+58h+arg_0], 0
0x180032eeb  mov     ecx, 3667C9Ah; this
0x180032ef0  mov     ebp, eax
0x180032ef2  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180032ef7  mov     r8d, eax
0x180032efa  mov     ecx, eax
0x180032efc  and     r8d, 0FFFFFF3Fh
0x180032f03  and     eax, 80h
0x180032f08  mov     edx, r8d
0x180032f0b  mov     r12d, 40h ; '@'
0x180032f11  and     edx, 3
0x180032f14  and     ecx, r12d
0x180032f17  shl     edx, 2
0x180032f1a  or      edx, ecx
0x180032f1c  shl     edx, 2
0x180032f1f  or      edx, eax
0x180032f21  lea     esi, ds:0[rdx*8]
0x180032f28  test    r8d, r8d
0x180032f2b  jnz     short loc_180032F32
0x180032f2d  mov     eax, r12d
0x180032f30  jmp     short loc_180032F3C
0x180032f32  xor     eax, eax
0x180032f34  cmp     r8d, 2
0x180032f38  cmovz   eax, r12d
0x180032f3c  or      esi, eax
0x180032f3e  mov     eax, [rbx]
0x180032f40  cmp     dword ptr [rsp+58h+arg_0], 0
0x180032f45  mov     edx, eax
0x180032f47  mov     [rbx], eax
0x180032f49  jz      short loc_180032F79
0x180032f4b  test    dl, 2
0x180032f4e  jnz     short loc_180032F79
0x180032f50  mov     eax, esi
0x180032f52  xor     eax, edx
0x180032f54  and     eax, 180h
0x180032f59  xor     eax, edx
0x180032f5b  mov     ecx, eax
0x180032f5d  xor     ecx, esi
0x180032f5f  and     ecx, r12d
0x180032f62  xor     ecx, eax
0x180032f64  or      ecx, 1
0x180032f67  mov     eax, ecx
0x180032f69  xor     eax, esi
0x180032f6b  and     eax, 800h
0x180032f70  xor     eax, ecx
0x180032f72  or      eax, 2
0x180032f75  mov     [rbx], eax
0x180032f77  jmp     short loc_180032F7B
0x180032f79  mov     eax, edx
0x180032f7b  mov     r8d, edx
0x180032f7e  and     r8d, 4
0x180032f82  jnz     short loc_180032F97
0x180032f84  mov     ecx, esi
0x180032f86  xor     ecx, eax
0x180032f88  and     ecx, 400h
0x180032f8e  xor     ecx, eax
0x180032f90  or      ecx, 4
0x180032f93  mov     [rbx], ecx
0x180032f95  jmp     short loc_180032F99
0x180032f97  mov     ecx, eax
0x180032f99  mov     eax, edx
0x180032f9b  lock cmpxchg [rdi], ecx
0x180032f9f  jnz     short loc_180032F40
0x180032fa1  test    r8d, r8d
0x180032fa4  jnz     short loc_180033010
0x180032fa6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180032fac  test    eax, eax
0x180032fae  jz      short loc_180033010
0x180032fb0  lea     r14, SRWLock
0x180032fb7  mov     rcx, r14; SRWLock
0x180032fba  call    cs:__imp_AcquireSRWLockExclusive
0x180032fc1  nop     dword ptr [rax+rax+00h]
0x180032fc6  mov     eax, cs:dword_1800443A4
0x180032fcc  mov     [rsp+58h+arg_8], r14
0x180032fd1  test    ebp, ebp
0x180032fd3  jz      short loc_180033002
0x180032fd5  cmp     ebp, eax
0x180032fd7  jnz     short loc_180033002
0x180032fd9  mov     r8d, 10h; unsigned __int64
0x180032fdf  mov     [rsp+58h+var_38], 3
0x180032fe8  lea     rdx, [rsp+58h+var_38]; void *
0x180032fed  mov     [rsp+58h+var_30], rdi
0x180032ff2  lea     rcx, qword_1800443D8; this
0x180032ff9  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180032ffe  test    al, al
0x180033000  jnz     short loc_180033006
0x180033002  lock and dword ptr [rdi], 0FFFFFFFBh
0x180033006  lea     rcx, [rsp+58h+arg_8]
0x18003300b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180033010  test    byte ptr [rbx], 2
0x180033013  jnz     short loc_180033039
0x180033015  mov     eax, [rbx]
0x180033017  xor     eax, esi
0x180033019  and     eax, 180h
0x18003301e  xor     eax, [rbx]
0x180033020  mov     ecx, eax
0x180033022  xor     ecx, esi
0x180033024  and     ecx, r12d
0x180033027  xor     ecx, eax
0x180033029  or      ecx, 1
0x18003302c  mov     eax, ecx
0x18003302e  xor     eax, esi
0x180033030  and     eax, 800h
0x180033035  xor     eax, ecx
0x180033037  mov     [rbx], eax
0x180033039  mov     rax, rbx
0x18003303c  mov     rbx, [rsp+58h+arg_10]
0x180033041  add     rsp, 30h
0x180033045  pop     r14
0x180033047  pop     r12
0x180033049  pop     rdi
0x18003304a  pop     rsi
0x18003304b  pop     rbp
0x18003304c  retn
```
