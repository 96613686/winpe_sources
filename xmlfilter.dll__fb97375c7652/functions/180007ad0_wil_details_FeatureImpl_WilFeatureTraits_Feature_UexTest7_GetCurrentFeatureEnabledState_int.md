# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180007ad0`
- end: `0x180007c39`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000708c`

## callees

- `0x180006c78`
- `0x180007ad0`
- `0x18000b2e0`
- `0x18000d394`
- `0x180017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  wil::details *v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58989021, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( v5 == 2 )
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
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_1800218A8, 58599553, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180007ad0  mov     [rsp+arg_10], rbx
0x180007ad5  mov     [rsp+arg_0], rcx
0x180007ada  push    rbp
0x180007adb  push    rsi
0x180007adc  push    rdi
0x180007add  sub     rsp, 40h
0x180007ae1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180007ae8  mov     rbx, rdx
0x180007aeb  test    rax, rax
0x180007aee  jz      short loc_180007B03
0x180007af0  mov     edx, 3
0x180007af5  mov     ecx, 38419DDh
0x180007afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aff  mov     edx, eax
0x180007b01  jmp     short loc_180007B11
0x180007b03  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180007b0a  test    rax, rax
0x180007b0d  jnz     short loc_180007AF0
0x180007b0f  xor     edx, edx
0x180007b11  mov     r8d, edx
0x180007b14  mov     qword ptr [rbx], 0
0x180007b1b  and     r8d, 0FFFFFF3Fh
0x180007b22  mov     eax, edx
0x180007b24  and     edx, 80h
0x180007b2a  mov     ecx, r8d
0x180007b2d  and     ecx, 3
0x180007b30  mov     ebp, 40h ; '@'
0x180007b35  shl     ecx, 2
0x180007b38  and     eax, ebp
0x180007b3a  or      ecx, eax
0x180007b3c  shl     ecx, 2
0x180007b3f  or      ecx, edx
0x180007b41  shl     ecx, 3
0x180007b44  test    r8d, r8d
0x180007b47  jnz     short loc_180007B50
0x180007b49  mov     edx, ebp
0x180007b4b  mov     r8d, ebp
0x180007b4e  jmp     short loc_180007B5C
0x180007b50  xor     edx, edx
0x180007b52  cmp     r8d, 2
0x180007b56  cmovz   edx, ebp
0x180007b59  mov     r8d, edx
0x180007b5c  mov     eax, ecx
0x180007b5e  mov     edi, 1
0x180007b63  or      eax, r8d
0x180007b66  or      ecx, edx
0x180007b68  mov     [rbx], eax
0x180007b6a  bt      ecx, 0Ah
0x180007b6e  jnb     short loc_180007B7D
0x180007b70  cmp     ecx, 800h
0x180007b76  jb      short loc_180007B7D
0x180007b78  mov     sil, dil
0x180007b7b  jmp     short loc_180007B8B
0x180007b7d  xor     sil, sil
0x180007b80  xor     dl, dl
0x180007b82  test    bpl, cl
0x180007b85  jz      loc_180007C15
0x180007b8b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x180007b92  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x180007b97  test    al, al
0x180007b99  jz      short loc_180007C06
0x180007b9b  mov     rax, cs:Feature_Standalone_26_03_NonSec__descriptor
0x180007ba2  mov     r8d, [rax]
0x180007ba5  test    r8b, 4
0x180007ba9  jnz     short loc_180007BC0
0x180007bab  lea     rdx, [rsp+58h+arg_8]
0x180007bb0  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)
0x180007bb5  mov     rcx, [rax]
0x180007bb8  mov     [rsp+58h+arg_8], rcx
0x180007bbd  mov     r8d, ecx
0x180007bc0  xor     eax, eax
0x180007bc2  mov     word ptr [rsp+58h+arg_0+4], 3
0x180007bc9  mov     r9d, r8d
0x180007bcc  mov     [rsp+58h+var_28], eax
0x180007bd0  mov     dword ptr [rsp+58h+arg_0], eax
0x180007bd4  lea     rcx, qword_1800218A8
0x180007bdb  shr     r9d, 0Bh
0x180007bdf  lea     rax, [rsp+58h+arg_0]
0x180007be4  shr     r8d, 0Ah
0x180007be8  and     r9d, edi
0x180007beb  and     r8d, edi
0x180007bee  mov     [rsp+58h+var_30], edi
0x180007bf2  mov     edx, 37E2881h
0x180007bf7  mov     [rsp+58h+var_38], rax
0x180007bfc  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180007c01  mov     dl, dil
0x180007c04  jmp     short loc_180007C08
0x180007c06  xor     dl, dl
0x180007c08  test    sil, sil
0x180007c0b  jz      short loc_180007C15
0x180007c0d  test    dl, dl
0x180007c0f  jnz     short loc_180007C15
0x180007c11  btr     dword ptr [rbx], 0Ah
0x180007c15  mov     eax, [rbx]
0x180007c17  test    bpl, al
0x180007c1a  jz      short loc_180007C20
0x180007c1c  test    dl, dl
0x180007c1e  jnz     short loc_180007C22
0x180007c20  xor     edi, edi
0x180007c22  and     eax, 0FFFFFFFEh
0x180007c25  or      eax, edi
0x180007c27  mov     [rbx], eax
0x180007c29  mov     rax, rbx
0x180007c2c  mov     rbx, [rsp+58h+arg_10]
0x180007c31  add     rsp, 40h
0x180007c35  pop     rdi
0x180007c36  pop     rsi
0x180007c37  pop     rbp
0x180007c38  retn
```
