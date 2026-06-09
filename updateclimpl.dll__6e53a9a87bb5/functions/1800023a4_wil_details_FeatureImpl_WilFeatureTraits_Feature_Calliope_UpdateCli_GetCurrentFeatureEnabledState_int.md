# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800023a4`
- end: `0x1800024b9`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_UpdateCli@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `277`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180002214`

## callees

- `0x1800023a4`
- `0x180002b68`
- `0x1800148e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // eax
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // eax
  unsigned int v8; // ecx
  int v9; // esi
  char IsEnabled; // al
  char v11; // bp
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
  v4 = v2(59428333, 3);
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) == 0 )
  {
LABEL_8:
    v7 = 64;
    goto LABEL_9;
  }
  v7 = 0;
  if ( v5 == 2 )
    v7 = 64;
LABEL_9:
  v8 = v7 | v6;
  v9 = 1;
  IsEnabled = 0;
  *(_DWORD *)a2 = v8;
  if ( (v8 & 0x400) != 0 && v8 >= 0x800 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    if ( (v8 & 0x40) == 0 )
      goto LABEL_16;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope>::GetImpl'::`2'::impl);
  if ( v11 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_16:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v9 = 0;
  result = a2;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x1800023a4  mov     [rsp+arg_0], rbx
0x1800023a9  mov     [rsp+arg_8], rbp
0x1800023ae  mov     [rsp+arg_10], rsi
0x1800023b3  push    rdi
0x1800023b4  sub     rsp, 20h
0x1800023b8  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800023bf  mov     rbx, rdx
0x1800023c2  test    rax, rax
0x1800023c5  jnz     short loc_1800023D3
0x1800023c7  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800023ce  test    rax, rax
0x1800023d1  jz      short loc_180002425
0x1800023d3  mov     edx, 3
0x1800023d8  mov     ecx, 38ACDEDh
0x1800023dd  call    _guard_dispatch_icall
0x1800023e2  mov     r8d, eax
0x1800023e5  mov     qword ptr [rbx], 0
0x1800023ec  and     r8d, 0FFFFFF3Fh
0x1800023f3  mov     edx, eax
0x1800023f5  and     edx, 80h
0x1800023fb  mov     ecx, r8d
0x1800023fe  and     ecx, 3
0x180002401  mov     edi, 40h ; '@'
0x180002406  shl     ecx, 2
0x180002409  and     eax, edi
0x18000240b  or      ecx, eax
0x18000240d  shl     ecx, 2
0x180002410  or      ecx, edx
0x180002412  shl     ecx, 3
0x180002415  test    r8d, r8d
0x180002418  jz      short loc_18000244C
0x18000241a  xor     eax, eax
0x18000241c  cmp     r8d, 2
0x180002420  cmovz   eax, edi
0x180002423  jmp     short loc_18000244E
0x180002425  xor     ecx, ecx
0x180002427  mov     qword ptr [rdx], 0
0x18000242e  xor     eax, eax
0x180002430  and     ecx, 3
0x180002433  shl     ecx, 2
0x180002436  lea     edi, [rax+40h]
0x180002439  and     eax, edi
0x18000243b  or      ecx, eax
0x18000243d  xor     eax, eax
0x18000243f  and     eax, 80h
0x180002444  shl     ecx, 2
0x180002447  or      ecx, eax
0x180002449  shl     ecx, 3
0x18000244c  mov     eax, edi
0x18000244e  or      ecx, eax
0x180002450  mov     esi, 1
0x180002455  xor     al, al
0x180002457  mov     [rbx], ecx
0x180002459  bt      ecx, 0Ah
0x18000245d  jnb     short loc_18000246C
0x18000245f  cmp     ecx, 800h
0x180002465  jb      short loc_18000246C
0x180002467  mov     bpl, sil
0x18000246a  jmp     short loc_180002474
0x18000246c  xor     bpl, bpl
0x18000246f  test    dil, cl
0x180002472  jz      short loc_18000248D
0x180002474  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calliope@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope> `wil::Feature<__WilFeatureTraits_Feature_Calliope>::GetImpl(void)'::`2'::impl
0x18000247b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope>::__private_IsEnabled(wil::ReportingKind)
0x180002480  test    bpl, bpl
0x180002483  jz      short loc_18000248D
0x180002485  test    al, al
0x180002487  jnz     short loc_18000248D
0x180002489  btr     dword ptr [rbx], 0Ah
0x18000248d  mov     ecx, [rbx]
0x18000248f  test    dil, cl
0x180002492  jz      short loc_180002498
0x180002494  test    al, al
0x180002496  jnz     short loc_18000249A
0x180002498  xor     esi, esi
0x18000249a  mov     rbp, [rsp+28h+arg_8]
0x18000249f  and     ecx, 0FFFFFFFEh
0x1800024a2  or      ecx, esi
0x1800024a4  mov     rax, rbx
0x1800024a7  mov     rsi, [rsp+28h+arg_10]
0x1800024ac  mov     [rbx], ecx
0x1800024ae  mov     rbx, [rsp+28h+arg_0]
0x1800024b3  add     rsp, 20h
0x1800024b7  pop     rdi
0x1800024b8  retn
```
