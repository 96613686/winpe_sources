# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140013938`
- end: `0x140013a6e`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140013764`

## callees

- `0x140013938`
- `0x140014514`
- `0x140014800`
- `0x1400206e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // eax
  unsigned int v5; // r8d
  unsigned int v6; // ecx
  int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // ecx
  int v10; // edi
  char v11; // bp

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
  v4 = v2(55615378, 3);
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
  v9 = v7 | v6;
  LOBYTE(v8) = 0;
  v10 = 1;
  if ( (v9 & 0x400) != 0 && v9 >= 0x800 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_20;
  }
  LOBYTE(v8) = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(
                                  `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl'::`2'::impl,
                                  v8)
            && (unsigned __int8)wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
  if ( v11 && !(_BYTE)v8 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_20:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v8 )
    v10 = 0;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x140013938  mov     [rsp+arg_0], rbx
0x14001393d  mov     [rsp+arg_8], rbp
0x140013942  mov     [rsp+arg_10], rsi
0x140013947  push    rdi
0x140013948  sub     rsp, 20h
0x14001394c  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140013953  mov     rbx, rdx
0x140013956  test    rax, rax
0x140013959  jnz     short loc_140013967
0x14001395b  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140013962  test    rax, rax
0x140013965  jz      short loc_1400139BD
0x140013967  mov     edx, 3
0x14001396c  mov     ecx, 3509F92h
0x140013971  call    _guard_dispatch_icall
0x140013976  mov     r8d, eax
0x140013979  mov     qword ptr [rbx], 0
0x140013980  and     r8d, 0FFFFFF3Fh
0x140013987  mov     edx, eax
0x140013989  and     edx, 80h
0x14001398f  mov     ecx, r8d
0x140013992  and     ecx, 3
0x140013995  mov     esi, 40h ; '@'
0x14001399a  shl     ecx, 2
0x14001399d  and     eax, esi
0x14001399f  or      ecx, eax
0x1400139a1  shl     ecx, 2
0x1400139a4  or      ecx, edx
0x1400139a6  shl     ecx, 3
0x1400139a9  test    r8d, r8d
0x1400139ac  jz      short loc_1400139E4
0x1400139ae  xor     eax, eax
0x1400139b0  cmp     r8d, 2
0x1400139b4  cmovz   eax, esi
0x1400139b7  mov     edx, eax
0x1400139b9  or      edx, ecx
0x1400139bb  jmp     short loc_1400139E8
0x1400139bd  xor     ecx, ecx
0x1400139bf  mov     qword ptr [rdx], 0
0x1400139c6  xor     eax, eax
0x1400139c8  and     ecx, 3
0x1400139cb  shl     ecx, 2
0x1400139ce  lea     esi, [rax+40h]
0x1400139d1  and     eax, esi
0x1400139d3  or      ecx, eax
0x1400139d5  xor     eax, eax
0x1400139d7  and     eax, 80h
0x1400139dc  shl     ecx, 2
0x1400139df  or      ecx, eax
0x1400139e1  shl     ecx, 3
0x1400139e4  xor     eax, eax
0x1400139e6  mov     edx, ecx
0x1400139e8  mov     [rbx], edx
0x1400139ea  or      ecx, eax
0x1400139ec  xor     dl, dl
0x1400139ee  mov     edi, 1
0x1400139f3  bt      ecx, 0Ah
0x1400139f7  jnb     short loc_140013A06
0x1400139f9  cmp     ecx, 800h
0x1400139ff  jb      short loc_140013A06
0x140013a01  mov     bpl, dil
0x140013a04  jmp     short loc_140013A0E
0x140013a06  xor     bpl, bpl
0x140013a09  test    sil, cl
0x140013a0c  jz      short loc_140013A42
0x140013a0e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl(void)'::`2'::impl
0x140013a15  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(wil::ReportingKind)
0x140013a1a  test    al, al
0x140013a1c  jz      short loc_140013A33
0x140013a1e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x140013a25  call    ?__private_IsEnabled@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x140013a2a  test    al, al
0x140013a2c  jz      short loc_140013A33
0x140013a2e  mov     dl, dil
0x140013a31  jmp     short loc_140013A35
0x140013a33  xor     dl, dl
0x140013a35  test    bpl, bpl
0x140013a38  jz      short loc_140013A42
0x140013a3a  test    dl, dl
0x140013a3c  jnz     short loc_140013A42
0x140013a3e  btr     dword ptr [rbx], 0Ah
0x140013a42  mov     eax, [rbx]
0x140013a44  test    sil, al
0x140013a47  jz      short loc_140013A4D
0x140013a49  test    dl, dl
0x140013a4b  jnz     short loc_140013A4F
0x140013a4d  xor     edi, edi
0x140013a4f  mov     rbp, [rsp+28h+arg_8]
0x140013a54  and     eax, 0FFFFFFFEh
0x140013a57  mov     rsi, [rsp+28h+arg_10]
0x140013a5c  or      eax, edi
0x140013a5e  mov     [rbx], eax
0x140013a60  mov     rax, rbx
0x140013a63  mov     rbx, [rsp+28h+arg_0]
0x140013a68  add     rsp, 20h
0x140013a6c  pop     rdi
0x140013a6d  retn
```
