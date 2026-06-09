# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800369ec`
- end: `0x180036b59`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039f60`

## callees

- `0x1800015d0`
- `0x180036170`
- `0x1800369ec`
- `0x18003b548`
- `0x18003bc40`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v17 = FEATURE_CHANGE_TIME_READ;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x37E287E,
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
              (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor,
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
0x1800369ec  mov     [rsp+arg_0], rbx
0x1800369f1  mov     [rsp+arg_10], rbp
0x1800369f6  push    rsi
0x1800369f7  push    rdi
0x1800369f8  push    r15
0x1800369fa  sub     rsp, 30h
0x1800369fe  mov     rax, cs:__security_cookie
0x180036a05  xor     rax, rsp
0x180036a08  mov     [rsp+48h+var_20], rax
0x180036a0d  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180036a14  mov     rbx, rdx
0x180036a17  mov     qword ptr [rdx], 0
0x180036a1e  mov     eax, [rsi]
0x180036a20  mov     [rdx], eax
0x180036a22  and     eax, 6
0x180036a25  cmp     al, 6
0x180036a27  jz      loc_180036B36
0x180036a2d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180036a32  lea     r8, [rsp+48h+var_28]; enum FEATURE_CHANGE_TIME
0x180036a37  mov     [rsp+48h+var_28], 0
0x180036a3f  mov     ecx, 37E287Eh; this
0x180036a44  mov     ebp, eax
0x180036a46  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180036a4b  mov     r8d, eax
0x180036a4e  mov     edx, eax
0x180036a50  and     r8d, 0FFFFFF3Fh
0x180036a57  and     edx, 80h
0x180036a5d  mov     ecx, r8d
0x180036a60  mov     r15d, 40h ; '@'
0x180036a66  and     ecx, 3
0x180036a69  and     eax, r15d
0x180036a6c  shl     ecx, 2
0x180036a6f  or      ecx, eax
0x180036a71  shl     ecx, 2
0x180036a74  or      ecx, edx
0x180036a76  lea     edi, ds:0[rcx*8]
0x180036a7d  test    r8d, r8d
0x180036a80  jnz     short loc_180036A87
0x180036a82  mov     eax, r15d
0x180036a85  jmp     short loc_180036A91
0x180036a87  xor     eax, eax
0x180036a89  cmp     r8d, 2
0x180036a8d  cmovz   eax, r15d
0x180036a91  or      edi, eax
0x180036a93  mov     eax, [rbx]
0x180036a95  cmp     [rsp+48h+var_28], 0
0x180036a9a  mov     edx, eax
0x180036a9c  mov     [rbx], eax
0x180036a9e  jz      short loc_180036ACE
0x180036aa0  test    dl, 2
0x180036aa3  jnz     short loc_180036ACE
0x180036aa5  mov     eax, edi
0x180036aa7  xor     eax, edx
0x180036aa9  and     eax, 180h
0x180036aae  xor     eax, edx
0x180036ab0  mov     ecx, eax
0x180036ab2  xor     ecx, edi
0x180036ab4  and     ecx, r15d
0x180036ab7  xor     ecx, eax
0x180036ab9  or      ecx, 1
0x180036abc  mov     eax, ecx
0x180036abe  xor     eax, edi
0x180036ac0  and     eax, 800h
0x180036ac5  xor     eax, ecx
0x180036ac7  or      eax, 2
0x180036aca  mov     [rbx], eax
0x180036acc  jmp     short loc_180036AD0
0x180036ace  mov     eax, edx
0x180036ad0  mov     r8d, edx
0x180036ad3  and     r8d, 4
0x180036ad7  jnz     short loc_180036AEC
0x180036ad9  mov     ecx, edi
0x180036adb  xor     ecx, eax
0x180036add  and     ecx, 400h
0x180036ae3  xor     ecx, eax
0x180036ae5  or      ecx, 4
0x180036ae8  mov     [rbx], ecx
0x180036aea  jmp     short loc_180036AEE
0x180036aec  mov     ecx, eax
0x180036aee  mov     eax, edx
0x180036af0  lock cmpxchg [rsi], ecx
0x180036af4  jnz     short loc_180036A95
0x180036af6  test    r8d, r8d
0x180036af9  jnz     short loc_180036B0B
0x180036afb  mov     r8d, ebp
0x180036afe  mov     edx, 3
0x180036b03  mov     rcx, rsi
0x180036b06  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180036b0b  test    byte ptr [rbx], 2
0x180036b0e  jnz     short loc_180036B36
0x180036b10  mov     ecx, [rbx]
0x180036b12  xor     ecx, edi
0x180036b14  and     ecx, 180h
0x180036b1a  xor     ecx, [rbx]
0x180036b1c  mov     edx, ecx
0x180036b1e  xor     edx, edi
0x180036b20  and     edx, r15d
0x180036b23  xor     edx, ecx
0x180036b25  or      edx, 1
0x180036b28  mov     ecx, edx
0x180036b2a  xor     ecx, edi
0x180036b2c  and     ecx, 800h
0x180036b32  xor     ecx, edx
0x180036b34  mov     [rbx], ecx
0x180036b36  mov     rax, rbx
0x180036b39  mov     rcx, [rsp+48h+var_20]
0x180036b3e  xor     rcx, rsp; StackCookie
0x180036b41  call    __security_check_cookie
0x180036b46  mov     rbx, [rsp+48h+arg_0]
0x180036b4b  mov     rbp, [rsp+48h+arg_10]
0x180036b50  add     rsp, 30h
0x180036b54  pop     r15
0x180036b56  pop     rdi
0x180036b57  pop     rsi
0x180036b58  retn
```
