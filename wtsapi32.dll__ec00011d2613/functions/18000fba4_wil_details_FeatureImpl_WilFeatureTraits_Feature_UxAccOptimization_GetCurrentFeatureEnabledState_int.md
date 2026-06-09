# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000fba4`
- end: `0x18000fcc4`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000f9fc`

## callees

- `0x18000f8a0`
- `0x18000fba4`
- `0x18001104c`
- `0x180011e70`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  __int64 v7; // rcx
  int v8; // edx
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v14 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2E30A37, (unsigned int)a2, a3, a4);
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (LOBYTE(v7) = 0, (v11 & 0x40) != 0) )
  {
    v12 = *(_DWORD *)Feature_Standalone_Future__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_Future__descriptor & 4) == 0 )
    {
      v15 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
               (wil::details *)v7,
               &v15);
      v12 = v15;
    }
    WORD2(v14) = 3;
    LODWORD(v14) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18001FAE0,
      0x2F29A04u,
      (v12 >> 10) & 1,
      (v12 >> 11) & 1,
      (__int64)&v14,
      1u,
      0);
    LOBYTE(v7) = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18000fba4  mov     [rsp+arg_10], rbx
0x18000fba9  mov     [rsp+arg_18], rsi
0x18000fbae  mov     [rsp+arg_0], rcx
0x18000fbb3  push    rdi
0x18000fbb4  sub     rsp, 40h
0x18000fbb8  mov     ecx, 2E30A37h; this
0x18000fbbd  mov     rdi, rdx
0x18000fbc0  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000fbc5  mov     edx, eax
0x18000fbc7  mov     qword ptr [rdi], 0
0x18000fbce  and     edx, 0FFFFFF3Fh
0x18000fbd4  mov     ecx, eax
0x18000fbd6  and     eax, 80h
0x18000fbdb  mov     r8d, edx
0x18000fbde  and     r8d, 3
0x18000fbe2  mov     esi, 40h ; '@'
0x18000fbe7  shl     r8d, 2
0x18000fbeb  and     ecx, esi
0x18000fbed  or      r8d, ecx
0x18000fbf0  shl     r8d, 2
0x18000fbf4  or      r8d, eax
0x18000fbf7  shl     r8d, 3
0x18000fbfb  test    edx, edx
0x18000fbfd  jnz     short loc_18000FC05
0x18000fbff  mov     ecx, esi
0x18000fc01  mov     edx, esi
0x18000fc03  jmp     short loc_18000FC0F
0x18000fc05  xor     ecx, ecx
0x18000fc07  cmp     edx, 2
0x18000fc0a  cmovz   ecx, esi
0x18000fc0d  mov     edx, ecx
0x18000fc0f  mov     eax, r8d
0x18000fc12  mov     ebx, 1
0x18000fc17  or      eax, edx
0x18000fc19  or      r8d, ecx
0x18000fc1c  mov     [rdi], eax
0x18000fc1e  bt      r8d, 0Ah
0x18000fc23  jnb     short loc_18000FC2E
0x18000fc25  cmp     r8d, 800h
0x18000fc2c  jnb     short loc_18000FC35
0x18000fc2e  xor     cl, cl
0x18000fc30  test    sil, r8b
0x18000fc33  jz      short loc_18000FC9D
0x18000fc35  mov     rax, cs:Feature_Standalone_Future__descriptor
0x18000fc3c  mov     r8d, [rax]
0x18000fc3f  test    r8b, 4
0x18000fc43  jnz     short loc_18000FC5A
0x18000fc45  lea     rdx, [rsp+48h+arg_8]
0x18000fc4a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x18000fc4f  mov     rcx, [rax]
0x18000fc52  mov     [rsp+48h+arg_8], rcx
0x18000fc57  mov     r8d, ecx
0x18000fc5a  xor     eax, eax
0x18000fc5c  mov     word ptr [rsp+48h+arg_0+4], 3
0x18000fc63  mov     r9d, r8d
0x18000fc66  mov     [rsp+48h+var_18], eax
0x18000fc6a  mov     dword ptr [rsp+48h+arg_0], eax
0x18000fc6e  lea     rcx, qword_18001FAE0
0x18000fc75  shr     r9d, 0Bh
0x18000fc79  lea     rax, [rsp+48h+arg_0]
0x18000fc7e  shr     r8d, 0Ah
0x18000fc82  and     r9d, ebx
0x18000fc85  and     r8d, ebx
0x18000fc88  mov     [rsp+48h+var_20], ebx
0x18000fc8c  mov     edx, 2F29A04h
0x18000fc91  mov     [rsp+48h+var_28], rax
0x18000fc96  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000fc9b  mov     cl, bl
0x18000fc9d  mov     eax, [rdi]
0x18000fc9f  test    sil, al
0x18000fca2  jz      short loc_18000FCA8
0x18000fca4  test    cl, cl
0x18000fca6  jnz     short loc_18000FCAA
0x18000fca8  xor     ebx, ebx
0x18000fcaa  mov     rsi, [rsp+48h+arg_18]
0x18000fcaf  and     eax, 0FFFFFFFEh
0x18000fcb2  or      eax, ebx
0x18000fcb4  mov     rbx, [rsp+48h+arg_10]
0x18000fcb9  mov     [rdi], eax
0x18000fcbb  mov     rax, rdi
0x18000fcbe  add     rsp, 40h
0x18000fcc2  pop     rdi
0x18000fcc3  retn
```
