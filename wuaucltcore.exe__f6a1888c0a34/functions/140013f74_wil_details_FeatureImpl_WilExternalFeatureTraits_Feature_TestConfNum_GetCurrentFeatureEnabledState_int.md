# wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestConfNum>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140013f74`
- end: `0x14001408b`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_TestConfNum@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140014094`

## callees

- `0x140009f10`
- `0x140013f74`
- `0x1400206e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestConfNum>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // eax
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // eax
  int v8; // edx
  unsigned int v9; // eax
  bool v10; // dl
  int v11; // esi
  char v12; // bp
  bool v13; // al
  _QWORD *result; // rax

  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( !g_wil_details_internalGetFeatureEnabledState )
  {
    v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState;
    if ( !g_wil_details_apiGetFeatureEnabledState )
    {
      *a2 = 0;
      v6 = 0;
      goto LABEL_8;
    }
  }
  v4 = v2(54237951, 64);
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) == 0 )
  {
LABEL_8:
    v7 = 0;
    v8 = v6;
    goto LABEL_9;
  }
  v7 = 0;
  if ( v5 == 2 )
    v7 = 64;
  v8 = v6 | v7;
LABEL_9:
  *(_DWORD *)a2 = v8;
  v9 = v6 | v7;
  v10 = 0;
  v11 = 1;
  if ( (v9 & 0x400) != 0 && v9 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_16;
  }
  v13 = wil::Wil_Staging_AreExternalFeatureDependenciesEnabled((wil *)0x33B9AFF);
  v10 = v13;
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_16:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v10 )
    v11 = 0;
  result = a2;
  *(_DWORD *)a2 = v11 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x140013f74  mov     [rsp+arg_0], rbx
0x140013f79  mov     [rsp+arg_8], rbp
0x140013f7e  mov     [rsp+arg_10], rsi
0x140013f83  push    rdi
0x140013f84  sub     rsp, 20h
0x140013f88  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140013f8f  mov     rbx, rdx
0x140013f92  test    rax, rax
0x140013f95  jnz     short loc_140013FA3
0x140013f97  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140013f9e  test    rax, rax
0x140013fa1  jz      short loc_140013FF6
0x140013fa3  mov     edi, 40h ; '@'
0x140013fa8  mov     ecx, 33B9AFFh
0x140013fad  mov     edx, edi
0x140013faf  call    _guard_dispatch_icall
0x140013fb4  mov     r8d, eax
0x140013fb7  mov     qword ptr [rbx], 0
0x140013fbe  and     r8d, 0FFFFFF3Fh
0x140013fc5  mov     edx, eax
0x140013fc7  and     eax, edi
0x140013fc9  and     edx, 80h
0x140013fcf  mov     ecx, r8d
0x140013fd2  and     ecx, 3
0x140013fd5  shl     ecx, 2
0x140013fd8  or      ecx, eax
0x140013fda  shl     ecx, 2
0x140013fdd  or      ecx, edx
0x140013fdf  shl     ecx, 3
0x140013fe2  test    r8d, r8d
0x140013fe5  jz      short loc_14001401D
0x140013fe7  xor     eax, eax
0x140013fe9  cmp     r8d, 2
0x140013fed  cmovz   eax, edi
0x140013ff0  mov     edx, eax
0x140013ff2  or      edx, ecx
0x140013ff4  jmp     short loc_140014021
0x140013ff6  xor     ecx, ecx
0x140013ff8  mov     qword ptr [rdx], 0
0x140013fff  xor     eax, eax
0x140014001  and     ecx, 3
0x140014004  shl     ecx, 2
0x140014007  lea     edi, [rax+40h]
0x14001400a  and     eax, edi
0x14001400c  or      ecx, eax
0x14001400e  xor     eax, eax
0x140014010  and     eax, 80h
0x140014015  shl     ecx, 2
0x140014018  or      ecx, eax
0x14001401a  shl     ecx, 3
0x14001401d  xor     eax, eax
0x14001401f  mov     edx, ecx
0x140014021  mov     [rbx], edx
0x140014023  or      eax, ecx
0x140014025  xor     dl, dl; unsigned int
0x140014027  mov     esi, 1
0x14001402c  bt      eax, 0Ah
0x140014030  jnb     short loc_14001403E
0x140014032  cmp     eax, 800h
0x140014037  jb      short loc_14001403E
0x140014039  mov     bpl, sil
0x14001403c  jmp     short loc_140014046
0x14001403e  xor     bpl, bpl
0x140014041  test    dil, al
0x140014044  jz      short loc_14001405F
0x140014046  mov     ecx, 33B9AFFh; this
0x14001404b  call    ?Wil_Staging_AreExternalFeatureDependenciesEnabled@wil@@YA_NI@Z; wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(uint)
0x140014050  mov     dl, al
0x140014052  test    bpl, bpl
0x140014055  jz      short loc_14001405F
0x140014057  test    al, al
0x140014059  jnz     short loc_14001405F
0x14001405b  btr     dword ptr [rbx], 0Ah
0x14001405f  mov     ecx, [rbx]
0x140014061  test    dil, cl
0x140014064  jz      short loc_14001406A
0x140014066  test    dl, dl
0x140014068  jnz     short loc_14001406C
0x14001406a  xor     esi, esi
0x14001406c  mov     rbp, [rsp+28h+arg_8]
0x140014071  and     ecx, 0FFFFFFFEh
0x140014074  or      ecx, esi
0x140014076  mov     rax, rbx
0x140014079  mov     rsi, [rsp+28h+arg_10]
0x14001407e  mov     [rbx], ecx
0x140014080  mov     rbx, [rsp+28h+arg_0]
0x140014085  add     rsp, 20h
0x140014089  pop     rdi
0x14001408a  retn
```
