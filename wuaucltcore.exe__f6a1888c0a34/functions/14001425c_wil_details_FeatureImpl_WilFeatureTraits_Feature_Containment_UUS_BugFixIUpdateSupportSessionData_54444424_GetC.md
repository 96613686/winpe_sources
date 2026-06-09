# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14001425c`
- end: `0x140014371`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140014378`

## callees

- `0x140014220`
- `0x14001425c`
- `0x1400206e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetCurrentFeatureEnabledState(
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
  v4 = v2(54444424, 3);
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
  IsEnabled = wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestConfNum>::__private_IsEnabled(`wil::Feature<__WilExternalFeatureTraits_Feature_TestConfNum>::GetImpl'::`2'::impl);
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
0x14001425c  mov     [rsp+arg_0], rbx
0x140014261  mov     [rsp+arg_8], rbp
0x140014266  mov     [rsp+arg_10], rsi
0x14001426b  push    rdi
0x14001426c  sub     rsp, 20h
0x140014270  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140014277  mov     rbx, rdx
0x14001427a  test    rax, rax
0x14001427d  jnz     short loc_14001428B
0x14001427f  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140014286  test    rax, rax
0x140014289  jz      short loc_1400142DD
0x14001428b  mov     edx, 3
0x140014290  mov     ecx, 33EC188h
0x140014295  call    _guard_dispatch_icall
0x14001429a  mov     r8d, eax
0x14001429d  mov     qword ptr [rbx], 0
0x1400142a4  and     r8d, 0FFFFFF3Fh
0x1400142ab  mov     edx, eax
0x1400142ad  and     edx, 80h
0x1400142b3  mov     ecx, r8d
0x1400142b6  and     ecx, 3
0x1400142b9  mov     edi, 40h ; '@'
0x1400142be  shl     ecx, 2
0x1400142c1  and     eax, edi
0x1400142c3  or      ecx, eax
0x1400142c5  shl     ecx, 2
0x1400142c8  or      ecx, edx
0x1400142ca  shl     ecx, 3
0x1400142cd  test    r8d, r8d
0x1400142d0  jz      short loc_140014304
0x1400142d2  xor     eax, eax
0x1400142d4  cmp     r8d, 2
0x1400142d8  cmovz   eax, edi
0x1400142db  jmp     short loc_140014306
0x1400142dd  xor     ecx, ecx
0x1400142df  mov     qword ptr [rdx], 0
0x1400142e6  xor     eax, eax
0x1400142e8  and     ecx, 3
0x1400142eb  shl     ecx, 2
0x1400142ee  lea     edi, [rax+40h]
0x1400142f1  and     eax, edi
0x1400142f3  or      ecx, eax
0x1400142f5  xor     eax, eax
0x1400142f7  and     eax, 80h
0x1400142fc  shl     ecx, 2
0x1400142ff  or      ecx, eax
0x140014301  shl     ecx, 3
0x140014304  mov     eax, edi
0x140014306  or      ecx, eax
0x140014308  mov     esi, 1
0x14001430d  xor     al, al
0x14001430f  mov     [rbx], ecx
0x140014311  bt      ecx, 0Ah
0x140014315  jnb     short loc_140014324
0x140014317  cmp     ecx, 800h
0x14001431d  jb      short loc_140014324
0x14001431f  mov     bpl, sil
0x140014322  jmp     short loc_14001432C
0x140014324  xor     bpl, bpl
0x140014327  test    dil, cl
0x14001432a  jz      short loc_140014345
0x14001432c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilExternalFeatureTraits_Feature_TestConfNum@@@wil@@CAAEAV?$FeatureImpl@U__WilExternalFeatureTraits_Feature_TestConfNum@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestConfNum> `wil::Feature<__WilExternalFeatureTraits_Feature_TestConfNum>::GetImpl(void)'::`2'::impl
0x140014333  call    ?__private_IsEnabled@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_TestConfNum@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestConfNum>::__private_IsEnabled(wil::ReportingKind)
0x140014338  test    bpl, bpl
0x14001433b  jz      short loc_140014345
0x14001433d  test    al, al
0x14001433f  jnz     short loc_140014345
0x140014341  btr     dword ptr [rbx], 0Ah
0x140014345  mov     ecx, [rbx]
0x140014347  test    dil, cl
0x14001434a  jz      short loc_140014350
0x14001434c  test    al, al
0x14001434e  jnz     short loc_140014352
0x140014350  xor     esi, esi
0x140014352  mov     rbp, [rsp+28h+arg_8]
0x140014357  and     ecx, 0FFFFFFFEh
0x14001435a  or      ecx, esi
0x14001435c  mov     rax, rbx
0x14001435f  mov     rsi, [rsp+28h+arg_10]
0x140014364  mov     [rbx], ecx
0x140014366  mov     rbx, [rsp+28h+arg_0]
0x14001436b  add     rsp, 20h
0x14001436f  pop     rdi
0x140014370  retn
```
