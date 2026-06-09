# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001b8e4`
- end: `0x18001b9c6`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ae7c`

## callees

- `0x1800162fc`
- `0x18001b8e4`
- `0x18001c7f8`
- `0x18001c8ac`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // si
  bool v13; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38AB9A9, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (FeatureEnabledState & 0xFFFFFF3F) == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_17;
  }
  v13 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MediaQI2511>::GetImpl'::`2'::impl)
     && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl);
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_17:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18001b8e4  push    rbx
0x18001b8e6  push    rbp
0x18001b8e7  push    rsi
0x18001b8e8  push    rdi
0x18001b8e9  sub     rsp, 28h
0x18001b8ed  mov     ecx, 38AB9A9h; this
0x18001b8f2  mov     rbx, rdx
0x18001b8f5  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001b8fa  mov     edx, eax
0x18001b8fc  mov     qword ptr [rbx], 0
0x18001b903  and     edx, 0FFFFFF3Fh
0x18001b909  mov     ecx, eax
0x18001b90b  and     eax, 80h
0x18001b910  mov     r8d, edx
0x18001b913  and     r8d, 3
0x18001b917  mov     ebp, 40h ; '@'
0x18001b91c  shl     r8d, 2
0x18001b920  and     ecx, ebp
0x18001b922  or      r8d, ecx
0x18001b925  shl     r8d, 2
0x18001b929  or      r8d, eax
0x18001b92c  shl     r8d, 3
0x18001b930  test    edx, edx
0x18001b932  jnz     short loc_18001B93A
0x18001b934  mov     ecx, ebp
0x18001b936  mov     edx, ebp
0x18001b938  jmp     short loc_18001B944
0x18001b93a  xor     ecx, ecx
0x18001b93c  cmp     edx, 2
0x18001b93f  cmovz   ecx, ebp
0x18001b942  mov     edx, ecx
0x18001b944  mov     eax, r8d
0x18001b947  mov     edi, 1
0x18001b94c  or      eax, edx
0x18001b94e  or      r8d, ecx
0x18001b951  mov     [rbx], eax
0x18001b953  bt      r8d, 0Ah
0x18001b958  jnb     short loc_18001B968
0x18001b95a  cmp     r8d, 800h
0x18001b961  jb      short loc_18001B968
0x18001b963  mov     sil, dil
0x18001b966  jmp     short loc_18001B972
0x18001b968  xor     sil, sil
0x18001b96b  xor     cl, cl
0x18001b96d  test    bpl, r8b
0x18001b970  jz      short loc_18001B9A6
0x18001b972  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MediaQI2511@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2511@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511> `wil::Feature<__WilFeatureTraits_Feature_MediaQI2511>::GetImpl(void)'::`2'::impl
0x18001b979  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2511@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::__private_IsEnabled(wil::ReportingKind)
0x18001b97e  test    al, al
0x18001b980  jz      short loc_18001B997
0x18001b982  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x18001b989  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x18001b98e  test    al, al
0x18001b990  jz      short loc_18001B997
0x18001b992  mov     cl, dil
0x18001b995  jmp     short loc_18001B999
0x18001b997  xor     cl, cl
0x18001b999  test    sil, sil
0x18001b99c  jz      short loc_18001B9A6
0x18001b99e  test    cl, cl
0x18001b9a0  jnz     short loc_18001B9A6
0x18001b9a2  btr     dword ptr [rbx], 0Ah
0x18001b9a6  mov     eax, [rbx]
0x18001b9a8  test    bpl, al
0x18001b9ab  jz      short loc_18001B9B1
0x18001b9ad  test    cl, cl
0x18001b9af  jnz     short loc_18001B9B3
0x18001b9b1  xor     edi, edi
0x18001b9b3  and     eax, 0FFFFFFFEh
0x18001b9b6  or      eax, edi
0x18001b9b8  mov     [rbx], eax
0x18001b9ba  mov     rax, rbx
0x18001b9bd  add     rsp, 28h
0x18001b9c1  pop     rdi
0x18001b9c2  pop     rsi
0x18001b9c3  pop     rbp
0x18001b9c4  pop     rbx
0x18001b9c5  retn
```
