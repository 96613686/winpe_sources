# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180036704`
- end: `0x180036871`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039e28`

## callees

- `0x1800015d0`
- `0x180036170`
- `0x180036704`
- `0x18003b548`
- `0x18003bc40`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  unsigned int v5; // edx
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  enum FEATURE_CHANGE_TIME v17; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v17 = FEATURE_CHANGE_TIME_READ;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2AF34FD,
                            v5,
                            (enum FEATURE_CHANGE_TIME)&v17,
                            v6);
    v8 = FeatureEnabledState & 0xFFFFFF3F;
    v9 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
    }
    else
    {
      v10 = 64;
    }
    v11 = v10 | v9;
    v12 = *(_DWORD *)a2;
    do
    {
      v13 = v17 == FEATURE_CHANGE_TIME_READ;
      v14 = v12;
      *(_DWORD *)a2 = v12;
      if ( !v13 && (v12 & 2) == 0 )
      {
        v12 = (v12
             ^ ((unsigned __int16)v12
              ^ (unsigned __int16)v11)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v12
               ^ (unsigned __int16)v11)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v12 ^ v11) & 0x180 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v14 & 4) != 0 )
      {
        v15 = v12;
      }
      else
      {
        v15 = v12 ^ ((unsigned __int16)v12 ^ (unsigned __int16)v11) & 0x400 | 4;
        *(_DWORD *)a2 = v15;
      }
      v12 = _InterlockedCompareExchange(
              (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor,
        3,
        v4);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v11
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v11
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v11
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v11
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
0x180036704  mov     [rsp+arg_0], rbx
0x180036709  mov     [rsp+arg_10], rbp
0x18003670e  push    rsi
0x18003670f  push    rdi
0x180036710  push    r15
0x180036712  sub     rsp, 30h
0x180036716  mov     rax, cs:__security_cookie
0x18003671d  xor     rax, rsp
0x180036720  mov     [rsp+48h+var_20], rax
0x180036725  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18003672c  mov     rbx, rdx
0x18003672f  mov     qword ptr [rdx], 0
0x180036736  mov     eax, [rsi]
0x180036738  mov     [rdx], eax
0x18003673a  and     eax, 6
0x18003673d  cmp     al, 6
0x18003673f  jz      loc_18003684E
0x180036745  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18003674a  lea     r8, [rsp+48h+var_28]; enum FEATURE_CHANGE_TIME
0x18003674f  mov     [rsp+48h+var_28], 0
0x180036757  mov     ecx, 2AF34FDh; this
0x18003675c  mov     ebp, eax
0x18003675e  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180036763  mov     r8d, eax
0x180036766  mov     edx, eax
0x180036768  and     r8d, 0FFFFFF3Fh
0x18003676f  and     edx, 80h
0x180036775  mov     ecx, r8d
0x180036778  mov     r15d, 40h ; '@'
0x18003677e  and     ecx, 3
0x180036781  and     eax, r15d
0x180036784  shl     ecx, 2
0x180036787  or      ecx, eax
0x180036789  shl     ecx, 2
0x18003678c  or      ecx, edx
0x18003678e  lea     edi, ds:0[rcx*8]
0x180036795  test    r8d, r8d
0x180036798  jnz     short loc_18003679F
0x18003679a  mov     eax, r15d
0x18003679d  jmp     short loc_1800367A9
0x18003679f  xor     eax, eax
0x1800367a1  cmp     r8d, 2
0x1800367a5  cmovz   eax, r15d
0x1800367a9  or      edi, eax
0x1800367ab  mov     eax, [rbx]
0x1800367ad  cmp     [rsp+48h+var_28], 0
0x1800367b2  mov     edx, eax
0x1800367b4  mov     [rbx], eax
0x1800367b6  jz      short loc_1800367E6
0x1800367b8  test    dl, 2
0x1800367bb  jnz     short loc_1800367E6
0x1800367bd  mov     eax, edi
0x1800367bf  xor     eax, edx
0x1800367c1  and     eax, 180h
0x1800367c6  xor     eax, edx
0x1800367c8  mov     ecx, eax
0x1800367ca  xor     ecx, edi
0x1800367cc  and     ecx, r15d
0x1800367cf  xor     ecx, eax
0x1800367d1  or      ecx, 1
0x1800367d4  mov     eax, ecx
0x1800367d6  xor     eax, edi
0x1800367d8  and     eax, 800h
0x1800367dd  xor     eax, ecx
0x1800367df  or      eax, 2
0x1800367e2  mov     [rbx], eax
0x1800367e4  jmp     short loc_1800367E8
0x1800367e6  mov     eax, edx
0x1800367e8  mov     r8d, edx
0x1800367eb  and     r8d, 4
0x1800367ef  jnz     short loc_180036804
0x1800367f1  mov     ecx, edi
0x1800367f3  xor     ecx, eax
0x1800367f5  and     ecx, 400h
0x1800367fb  xor     ecx, eax
0x1800367fd  or      ecx, 4
0x180036800  mov     [rbx], ecx
0x180036802  jmp     short loc_180036806
0x180036804  mov     ecx, eax
0x180036806  mov     eax, edx
0x180036808  lock cmpxchg [rsi], ecx
0x18003680c  jnz     short loc_1800367AD
0x18003680e  test    r8d, r8d
0x180036811  jnz     short loc_180036823
0x180036813  mov     r8d, ebp
0x180036816  mov     edx, 3
0x18003681b  mov     rcx, rsi
0x18003681e  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180036823  test    byte ptr [rbx], 2
0x180036826  jnz     short loc_18003684E
0x180036828  mov     ecx, [rbx]
0x18003682a  xor     ecx, edi
0x18003682c  and     ecx, 180h
0x180036832  xor     ecx, [rbx]
0x180036834  mov     edx, ecx
0x180036836  xor     edx, edi
0x180036838  and     edx, r15d
0x18003683b  xor     edx, ecx
0x18003683d  or      edx, 1
0x180036840  mov     ecx, edx
0x180036842  xor     ecx, edi
0x180036844  and     ecx, 800h
0x18003684a  xor     ecx, edx
0x18003684c  mov     [rbx], ecx
0x18003684e  mov     rax, rbx
0x180036851  mov     rcx, [rsp+48h+var_20]
0x180036856  xor     rcx, rsp; StackCookie
0x180036859  call    __security_check_cookie
0x18003685e  mov     rbx, [rsp+48h+arg_0]
0x180036863  mov     rbp, [rsp+48h+arg_10]
0x180036868  add     rsp, 30h
0x18003686c  pop     r15
0x18003686e  pop     rdi
0x18003686f  pop     rsi
0x180036870  retn
```
