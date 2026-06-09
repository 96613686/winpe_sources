# wil::details::FeatureImpl<__WilFeatureTraits_Feature_SSDP_Defense_Potential_Race>::GetCachedFeatureEnabledState(void)

- ea: `0x18002ffd0`
- end: `0x1800301b4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SSDP_Defense_Potential_Race@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `484`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030f4c`
- `0x180030fdc`

## callees

- `0x180024d20`
- `0x18002b074`
- `0x18002dfd8`
- `0x18002e454`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003011a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003011a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_SSDP_Defense_Potential_Race>::GetCachedFeatureEnabledState(
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
  int v10; // edx
  int v11; // eax
  int v12; // edi
  char v13; // al
  int v14; // eax
  int v15; // edi
  signed __int32 v16; // eax
  bool v17; // zf
  signed __int32 v18; // edx
  int v19; // eax
  int v20; // r8d
  signed __int32 v21; // ecx
  _QWORD v23[7]; // [rsp+20h] [rbp-38h] BYREF
  wil::details *v24; // [rsp+60h] [rbp+8h] BYREF
  RTL_SRWLOCK *v25; // [rsp+68h] [rbp+10h] BYREF

  v24 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_SSDP_Defense_Potential_Race__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_SSDP_Defense_Potential_Race__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v24) = 0;
  v5 = v4;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                          (wil::details *)0x39B153B,
                          v6,
                          (enum FEATURE_CHANGE_TIME)&v24,
                          v7);
  v9 = FeatureEnabledState & 0xFFFFFF3F;
  v10 = FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3))));
  v11 = 0;
  if ( v9 == 2 )
    v11 = 64;
  v12 = v11 | (8 * v10);
  if ( (v12 & 0xC00) == 0xC00 )
  {
    v13 = 1;
  }
  else
  {
    if ( (v12 & 0x40) != 0 )
      goto LABEL_11;
    v13 = 0;
  }
  if ( (v12 & 0x40) == 0 || !v13 )
  {
    v14 = 0;
    goto LABEL_12;
  }
LABEL_11:
  v14 = 1;
LABEL_12:
  v15 = v14 | v12;
  v16 = *(_DWORD *)a2;
  do
  {
    v17 = (_DWORD)v24 == 0;
    v18 = v16;
    *(_DWORD *)a2 = v16;
    if ( v17 || (v16 & 2) != 0 )
    {
      v20 = v16;
    }
    else
    {
      v19 = v16
          ^ ((unsigned __int16)v15
           ^ (unsigned __int16)v16)
          & 0x180
          ^ (v15
           ^ v16
           ^ ((unsigned __int16)v15
            ^ (unsigned __int16)v16)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v15
           ^ (unsigned __int8)(v16 ^ (v15 ^ v16) & 0x80 ^ (v15 ^ v16 ^ (v15 ^ v16) & 0x80) & 0x40))
          & 1;
      v20 = v19 ^ ((unsigned __int16)v15 ^ (unsigned __int16)v19) & 0x800 | 2;
      *(_DWORD *)a2 = v20;
    }
    v21 = v20;
    if ( (v18 & 4) == 0 )
    {
      v21 = v20 ^ ((unsigned __int16)v15 ^ (unsigned __int16)v20) & 0x400 | 4;
      *(_DWORD *)a2 = v21;
    }
    v16 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_SSDP_Defense_Potential_Race__descriptor,
            v21,
            v18);
  }
  while ( v18 != v16 );
  if ( (v18 & 4) == 0 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v25 = &SRWLock;
    if ( !v5
      || v5 != dword_1800443A4
      || (v23[0] = 3,
          v23[1] = Feature_SSDP_Defense_Potential_Race__descriptor,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800443D8, v23, 0x10u)) )
    {
      _InterlockedAnd((volatile signed __int32 *)Feature_SSDP_Defense_Potential_Race__descriptor, 0xFFFFFFFB);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v25);
  }
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v15
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v15
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v15
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v15
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v15
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v15
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v15
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v15
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v15
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v15
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v15
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v15
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v15
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v15
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v15
                       ^ (unsigned __int8)*(_DWORD *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x18002ffd0  mov     [rsp+arg_10], rbx
0x18002ffd5  mov     [rsp+arg_0], rcx
0x18002ffda  push    rbp
0x18002ffdb  push    rsi
0x18002ffdc  push    rdi
0x18002ffdd  push    r12
0x18002ffdf  push    r14
0x18002ffe1  sub     rsp, 30h
0x18002ffe5  mov     rsi, cs:Feature_SSDP_Defense_Potential_Race__descriptor
0x18002ffec  mov     rbx, rdx
0x18002ffef  mov     qword ptr [rdx], 0
0x18002fff6  mov     eax, [rsi]
0x18002fff8  mov     [rdx], eax
0x18002fffa  and     eax, 6
0x18002fffd  cmp     al, 6
0x18002ffff  jz      loc_18003019F
0x180030005  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18003000a  lea     r8, [rsp+58h+arg_0]; enum FEATURE_CHANGE_TIME
0x18003000f  mov     dword ptr [rsp+58h+arg_0], 0
0x180030017  mov     ecx, 39B153Bh; this
0x18003001c  mov     ebp, eax
0x18003001e  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180030023  mov     r8d, eax
0x180030026  mov     ecx, eax
0x180030028  and     eax, 80h
0x18003002d  and     r8d, 0FFFFFF3Fh
0x180030034  mov     edx, r8d
0x180030037  mov     r12d, 40h ; '@'
0x18003003d  and     edx, 3
0x180030040  and     ecx, r12d
0x180030043  shl     edx, 2
0x180030046  or      edx, ecx
0x180030048  shl     edx, 2
0x18003004b  or      edx, eax
0x18003004d  xor     eax, eax
0x18003004f  lea     edi, ds:0[rdx*8]
0x180030056  test    r8d, r8d
0x180030059  jz      short loc_180030063
0x18003005b  cmp     r8d, 2
0x18003005f  cmovz   eax, r12d
0x180030063  or      edi, eax
0x180030065  mov     edx, 0C00h
0x18003006a  mov     ecx, edi
0x18003006c  mov     eax, edi
0x18003006e  and     ecx, r12d
0x180030071  and     eax, edx
0x180030073  cmp     eax, edx
0x180030075  jnz     short loc_18003007B
0x180030077  mov     al, 1
0x180030079  jmp     short loc_180030081
0x18003007b  test    ecx, ecx
0x18003007d  jnz     short loc_18003008D
0x18003007f  xor     al, al
0x180030081  test    ecx, ecx
0x180030083  jz      short loc_180030089
0x180030085  test    al, al
0x180030087  jnz     short loc_18003008D
0x180030089  xor     eax, eax
0x18003008b  jmp     short loc_180030092
0x18003008d  mov     eax, 1
0x180030092  or      edi, eax
0x180030094  mov     eax, [rbx]
0x180030096  cmp     dword ptr [rsp+58h+arg_0], 0
0x18003009b  mov     edx, eax
0x18003009d  mov     [rbx], eax
0x18003009f  jz      short loc_1800300DA
0x1800300a1  test    dl, 2
0x1800300a4  jnz     short loc_1800300DA
0x1800300a6  xor     eax, edi
0x1800300a8  and     eax, 180h
0x1800300ad  xor     eax, edx
0x1800300af  mov     ecx, eax
0x1800300b1  xor     ecx, edi
0x1800300b3  and     ecx, r12d
0x1800300b6  xor     ecx, eax
0x1800300b8  mov     eax, ecx
0x1800300ba  xor     eax, edi
0x1800300bc  and     eax, 1
0x1800300bf  xor     eax, ecx
0x1800300c1  mov     r8d, eax
0x1800300c4  xor     r8d, edi
0x1800300c7  and     r8d, 800h
0x1800300ce  xor     r8d, eax
0x1800300d1  or      r8d, 2
0x1800300d5  mov     [rbx], r8d
0x1800300d8  jmp     short loc_1800300DD
0x1800300da  mov     r8d, edx
0x1800300dd  mov     r9d, edx
0x1800300e0  mov     ecx, r8d
0x1800300e3  and     r9d, 4
0x1800300e7  jnz     short loc_1800300F9
0x1800300e9  xor     ecx, edi
0x1800300eb  and     ecx, 400h
0x1800300f1  xor     ecx, r8d
0x1800300f4  or      ecx, 4
0x1800300f7  mov     [rbx], ecx
0x1800300f9  mov     eax, edx
0x1800300fb  lock cmpxchg [rsi], ecx
0x1800300ff  jnz     short loc_180030096
0x180030101  test    r9d, r9d
0x180030104  jnz     short loc_180030170
0x180030106  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18003010c  test    eax, eax
0x18003010e  jz      short loc_180030170
0x180030110  lea     r14, SRWLock
0x180030117  mov     rcx, r14; SRWLock
0x18003011a  call    cs:__imp_AcquireSRWLockExclusive
0x180030121  nop     dword ptr [rax+rax+00h]
0x180030126  mov     eax, cs:dword_1800443A4
0x18003012c  mov     [rsp+58h+arg_8], r14
0x180030131  test    ebp, ebp
0x180030133  jz      short loc_180030162
0x180030135  cmp     ebp, eax
0x180030137  jnz     short loc_180030162
0x180030139  mov     r8d, 10h; unsigned __int64
0x18003013f  mov     [rsp+58h+var_38], 3
0x180030148  lea     rdx, [rsp+58h+var_38]; void *
0x18003014d  mov     [rsp+58h+var_30], rsi
0x180030152  lea     rcx, qword_1800443D8; this
0x180030159  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003015e  test    al, al
0x180030160  jnz     short loc_180030166
0x180030162  lock and dword ptr [rsi], 0FFFFFFFBh
0x180030166  lea     rcx, [rsp+58h+arg_8]
0x18003016b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180030170  test    byte ptr [rbx], 2
0x180030173  jnz     short loc_18003019F
0x180030175  mov     eax, [rbx]
0x180030177  xor     eax, edi
0x180030179  and     eax, 180h
0x18003017e  xor     eax, [rbx]
0x180030180  mov     ecx, eax
0x180030182  xor     ecx, edi
0x180030184  and     ecx, r12d
0x180030187  xor     ecx, eax
0x180030189  mov     edx, ecx
0x18003018b  xor     edx, edi
0x18003018d  and     edx, 1
0x180030190  xor     edx, ecx
0x180030192  mov     eax, edx
0x180030194  xor     eax, edi
0x180030196  and     eax, 800h
0x18003019b  xor     eax, edx
0x18003019d  mov     [rbx], eax
0x18003019f  mov     rax, rbx
0x1800301a2  mov     rbx, [rsp+58h+arg_10]
0x1800301a7  add     rsp, 30h
0x1800301ab  pop     r14
0x1800301ad  pop     r12
0x1800301af  pop     rdi
0x1800301b0  pop     rsi
0x1800301b1  pop     rbp
0x1800301b2  retn
```
