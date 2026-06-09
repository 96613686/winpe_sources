# wil::details::FeatureImpl<__WilFeatureTraits_Feature_58212721>::GetCachedVariantState(void)

- ea: `0x180012f70`
- end: `0x1800130f5`
- name: `?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_58212721@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `389`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014f00`
- `0x180015148`

## callees

- `0x180005dd8`
- `0x18000b3d8`
- `0x180012f70`
- `0x1800155c4`
- `0x18001b010`

## pseudocode

```c
__int64 *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_58212721>::GetCachedVariantState(
        wil::details *a1,
        signed __int64 *a2)
{
  __int64 v3; // rax
  int v4; // r15d
  __int64 (__fastcall *v5)(__int64, __int64, int *, wil::details **, int *); // rax
  int v6; // esi
  int v7; // ebx
  int v8; // r9d
  __int64 v9; // r8
  signed __int64 v10; // rax
  signed __int64 v11; // r10
  int v12; // eax
  int v13; // eax
  bool v14; // zf
  wil::details *v16; // [rsp+60h] [rbp+30h] BYREF
  int v17; // [rsp+68h] [rbp+38h] BYREF
  int v18; // [rsp+70h] [rbp+40h] BYREF

  v16 = a1;
  v3 = *Feature_58212721__descriptor;
  *a2 = *Feature_58212721__descriptor;
  if ( (v3 & 0xC) == 0xC )
    return a2;
  v18 = 0;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v16) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, int *, wil::details **, int *))g_wil_details_internalGetFeatureVariant;
  v17 = 0;
  if ( g_wil_details_internalGetFeatureVariant
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, int *, wil::details **, int *))g_wil_details_apiGetFeatureVariant) != 0 )
  {
    v6 = v5(58212721, 3, &v17, &v16, &v18);
  }
  else
  {
    v6 = 0;
  }
  v7 = ((_DWORD)v16 != 0 ? 0x400 : 0) | (16 * (v6 & 0x80));
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl'::`2'::impl) )
    goto LABEL_11;
  if ( (v6 & 0xFFFFFE7F) == 0 )
  {
    v8 = 0;
    v7 |= 0x3000u;
    goto LABEL_12;
  }
  v7 ^= (v6 & 0x3F) << 12;
  if ( (v6 & 0x100) != 0 )
    v8 = v17;
  else
LABEL_11:
    v8 = 0;
LABEL_12:
  v9 = *a2;
  v10 = *a2;
  v11 = *a2;
  while ( 1 )
  {
    *(_DWORD *)a2 = v9;
    *((_DWORD *)a2 + 1) = HIDWORD(v10);
    if ( (v9 & 8) != 0 )
    {
      v13 = v9;
    }
    else
    {
      v12 = v18;
      *((_DWORD *)a2 + 1) = v8;
      v13 = ((v12 != 0 ? 8 : 0) | (v9 ^ (v7 ^ v9) & 0x3F000) & 0xFFFFFFF7)
          ^ ((unsigned __int16)v7
           ^ ((v12 != 0 ? 8 : 0)
            | ((unsigned __int16)v9 ^ ((unsigned __int16)v7 ^ (unsigned __int16)v9) & 0xF000) & 0xFFF7))
          & 0x800;
      *(_DWORD *)a2 = v13;
    }
    if ( (v9 & 4) == 0 )
      *(_DWORD *)a2 = v13 ^ ((unsigned __int16)v13 ^ (unsigned __int16)v7) & 0x400 | 4;
    v10 = _InterlockedCompareExchange64(Feature_58212721__descriptor, *a2, v11);
    v14 = v11 == v10;
    v11 = v10;
    if ( v14 )
      break;
    LODWORD(v9) = v10;
  }
  if ( (v9 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_58212721__descriptor,
      3u,
      v4);
  return a2;
}

```

## disassembly

```asm
0x180012f70  mov     [rsp-28h+arg_18], rbx
0x180012f75  mov     [rsp-28h+arg_0], rcx
0x180012f7a  push    rbp
0x180012f7b  push    rsi
0x180012f7c  push    rdi
0x180012f7d  push    r14
0x180012f7f  push    r15
0x180012f81  mov     rbp, rsp
0x180012f84  sub     rsp, 30h
0x180012f88  mov     r14, cs:Feature_58212721__descriptor
0x180012f8f  mov     rdi, rdx
0x180012f92  mov     rax, [r14]
0x180012f95  mov     [rdx], rax
0x180012f98  and     eax, 0Ch
0x180012f9b  cmp     al, 0Ch
0x180012f9d  jz      loc_1800130E1
0x180012fa3  mov     [rbp+arg_10], 0
0x180012faa  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012faf  mov     r15d, eax
0x180012fb2  mov     dword ptr [rbp+arg_0], 0
0x180012fb9  mov     rax, cs:g_wil_details_internalGetFeatureVariant
0x180012fc0  mov     [rbp+arg_8], 0
0x180012fc7  test    rax, rax
0x180012fca  jz      short loc_180012FF0
0x180012fcc  lea     rcx, [rbp+arg_10]
0x180012fd0  mov     edx, 3
0x180012fd5  mov     [rsp+30h+var_10], rcx
0x180012fda  lea     r9, [rbp+arg_0]
0x180012fde  mov     ecx, 3784171h
0x180012fe3  lea     r8, [rbp+arg_8]
0x180012fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fec  mov     esi, eax
0x180012fee  jmp     short loc_180012FFE
0x180012ff0  mov     rax, cs:g_wil_details_apiGetFeatureVariant
0x180012ff7  test    rax, rax
0x180012ffa  jnz     short loc_180012FCC
0x180012ffc  xor     esi, esi
0x180012ffe  mov     eax, dword ptr [rbp+arg_0]
0x180013001  mov     ebx, esi
0x180013003  neg     eax
0x180013005  sbb     ecx, ecx
0x180013007  and     ebx, 80h
0x18001300d  and     ecx, 400h
0x180013013  shl     ebx, 4
0x180013016  or      ebx, ecx
0x180013018  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57519991@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991> `wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl(void)'::`2'::impl
0x18001301f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(wil::ReportingKind)
0x180013024  test    al, al
0x180013026  jz      short loc_180013050
0x180013028  mov     eax, esi
0x18001302a  and     eax, 0FFFFFE7Fh
0x18001302f  jnz     short loc_18001303C
0x180013031  xor     r9d, r9d
0x180013034  or      ebx, 3000h
0x18001303a  jmp     short loc_180013053
0x18001303c  and     eax, 3Fh
0x18001303f  shl     eax, 0Ch
0x180013042  xor     ebx, eax
0x180013044  bt      esi, 8
0x180013048  jnb     short loc_180013050
0x18001304a  mov     r9d, [rbp+arg_8]
0x18001304e  jmp     short loc_180013053
0x180013050  xor     r9d, r9d
0x180013053  mov     r8, [rdi]
0x180013056  mov     rax, r8
0x180013059  mov     r10, r8
0x18001305c  shr     rax, 20h
0x180013060  mov     [rdi], r8d
0x180013063  mov     [rdi+4], eax
0x180013066  test    r8b, 8
0x18001306a  jnz     short loc_18001309C
0x18001306c  mov     eax, [rbp+arg_10]
0x18001306f  mov     edx, r8d
0x180013072  xor     edx, ebx
0x180013074  mov     [rdi+4], r9d
0x180013078  and     edx, 3F000h
0x18001307e  xor     edx, r8d
0x180013081  neg     eax
0x180013083  sbb     ecx, ecx
0x180013085  and     edx, 0FFFFFFF7h
0x180013088  and     ecx, 8
0x18001308b  or      edx, ecx
0x18001308d  mov     eax, edx
0x18001308f  xor     eax, ebx
0x180013091  and     eax, 800h
0x180013096  xor     eax, edx
0x180013098  mov     [rdi], eax
0x18001309a  jmp     short loc_18001309F
0x18001309c  mov     eax, r8d
0x18001309f  test    r8b, 4
0x1800130a3  jnz     short loc_1800130B6
0x1800130a5  mov     ecx, ebx
0x1800130a7  xor     ecx, eax
0x1800130a9  and     ecx, 400h
0x1800130af  xor     ecx, eax
0x1800130b1  or      ecx, 4
0x1800130b4  mov     [rdi], ecx
0x1800130b6  mov     rcx, [rdi]
0x1800130b9  mov     rax, r10
0x1800130bc  lock cmpxchg [r14], rcx
0x1800130c1  mov     r10, rax
0x1800130c4  jz      short loc_1800130CB
0x1800130c6  mov     r8d, eax
0x1800130c9  jmp     short loc_18001305C
0x1800130cb  test    r8b, 4
0x1800130cf  jnz     short loc_1800130E1
0x1800130d1  mov     r8d, r15d
0x1800130d4  mov     edx, 3
0x1800130d9  mov     rcx, r14
0x1800130dc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800130e1  mov     rbx, [rsp+30h+arg_18]
0x1800130e6  mov     rax, rdi
0x1800130e9  add     rsp, 30h
0x1800130ed  pop     r15
0x1800130ef  pop     r14
0x1800130f1  pop     rdi
0x1800130f2  pop     rsi
0x1800130f3  pop     rbp
0x1800130f4  retn
```
