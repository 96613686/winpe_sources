# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140009df4`
- end: `0x140009f09`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009c30`

## callees

- `0x140009df4`
- `0x14000a2d8`
- `0x1400206e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetCurrentFeatureEnabledState(
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
  v4 = v2(55045381, 3);
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
  IsEnabled = wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(`wil::Feature<__WilExternalFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl);
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
0x140009df4  mov     [rsp+arg_0], rbx
0x140009df9  mov     [rsp+arg_8], rbp
0x140009dfe  mov     [rsp+arg_10], rsi
0x140009e03  push    rdi
0x140009e04  sub     rsp, 20h
0x140009e08  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140009e0f  mov     rbx, rdx
0x140009e12  test    rax, rax
0x140009e15  jnz     short loc_140009E23
0x140009e17  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140009e1e  test    rax, rax
0x140009e21  jz      short loc_140009E75
0x140009e23  mov     edx, 3
0x140009e28  mov     ecx, 347ED05h
0x140009e2d  call    _guard_dispatch_icall
0x140009e32  mov     r8d, eax
0x140009e35  mov     qword ptr [rbx], 0
0x140009e3c  and     r8d, 0FFFFFF3Fh
0x140009e43  mov     edx, eax
0x140009e45  and     edx, 80h
0x140009e4b  mov     ecx, r8d
0x140009e4e  and     ecx, 3
0x140009e51  mov     edi, 40h ; '@'
0x140009e56  shl     ecx, 2
0x140009e59  and     eax, edi
0x140009e5b  or      ecx, eax
0x140009e5d  shl     ecx, 2
0x140009e60  or      ecx, edx
0x140009e62  shl     ecx, 3
0x140009e65  test    r8d, r8d
0x140009e68  jz      short loc_140009E9C
0x140009e6a  xor     eax, eax
0x140009e6c  cmp     r8d, 2
0x140009e70  cmovz   eax, edi
0x140009e73  jmp     short loc_140009E9E
0x140009e75  xor     ecx, ecx
0x140009e77  mov     qword ptr [rdx], 0
0x140009e7e  xor     eax, eax
0x140009e80  and     ecx, 3
0x140009e83  shl     ecx, 2
0x140009e86  lea     edi, [rax+40h]
0x140009e89  and     eax, edi
0x140009e8b  or      ecx, eax
0x140009e8d  xor     eax, eax
0x140009e8f  and     eax, 80h
0x140009e94  shl     ecx, 2
0x140009e97  or      ecx, eax
0x140009e99  shl     ecx, 3
0x140009e9c  mov     eax, edi
0x140009e9e  or      ecx, eax
0x140009ea0  mov     esi, 1
0x140009ea5  xor     al, al
0x140009ea7  mov     [rbx], ecx
0x140009ea9  bt      ecx, 0Ah
0x140009ead  jnb     short loc_140009EBC
0x140009eaf  cmp     ecx, 800h
0x140009eb5  jb      short loc_140009EBC
0x140009eb7  mov     bpl, sil
0x140009eba  jmp     short loc_140009EC4
0x140009ebc  xor     bpl, bpl
0x140009ebf  test    dil, cl
0x140009ec2  jz      short loc_140009EDD
0x140009ec4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilExternalFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilExternalFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilExternalFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x140009ecb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x140009ed0  test    bpl, bpl
0x140009ed3  jz      short loc_140009EDD
0x140009ed5  test    al, al
0x140009ed7  jnz     short loc_140009EDD
0x140009ed9  btr     dword ptr [rbx], 0Ah
0x140009edd  mov     ecx, [rbx]
0x140009edf  test    dil, cl
0x140009ee2  jz      short loc_140009EE8
0x140009ee4  test    al, al
0x140009ee6  jnz     short loc_140009EEA
0x140009ee8  xor     esi, esi
0x140009eea  mov     rbp, [rsp+28h+arg_8]
0x140009eef  and     ecx, 0FFFFFFFEh
0x140009ef2  or      ecx, esi
0x140009ef4  mov     rax, rbx
0x140009ef7  mov     rsi, [rsp+28h+arg_10]
0x140009efc  mov     [rbx], ecx
0x140009efe  mov     rbx, [rsp+28h+arg_0]
0x140009f03  add     rsp, 20h
0x140009f07  pop     rdi
0x140009f08  retn
```
