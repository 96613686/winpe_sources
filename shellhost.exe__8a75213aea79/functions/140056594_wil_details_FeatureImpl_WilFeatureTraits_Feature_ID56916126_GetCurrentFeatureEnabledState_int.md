# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140056594`
- end: `0x140056719`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1400559f4`

## callees

- `0x14000afb0`
- `0x14005588c`
- `0x14005604c`
- `0x140056594`
- `0x14005c0d4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // r8d
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // edx
  unsigned int v12; // r8d
  __int64 v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+20h] BYREF
  __int64 v17; // [rsp+68h] [rbp+28h] BYREF

  v16 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x364789E, 3u, a3, a4);
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
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
                         v7,
                         &v17);
      v12 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_140084298,
      0x2F29A04u,
      (v12 >> 10) & 1,
      (v12 >> 11) & 1,
      (__int64)&v16,
      1u,
      0);
    v14 = *(_DWORD *)Feature_60011020__descriptor;
    if ( (*(_DWORD *)Feature_60011020__descriptor & 4) == 0 )
    {
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60011020>::GetCachedFeatureEnabledState(
                         v13,
                         &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_1400843B8,
      0x393B20Cu,
      (v14 >> 10) & 1,
      (v14 >> 11) & 1,
      (__int64)&v16,
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
0x140056594  mov     [rsp-18h+arg_10], rbx
0x140056599  mov     [rsp-18h+arg_0], rcx
0x14005659e  push    rbp
0x14005659f  push    rdi
0x1400565a0  push    r14
0x1400565a2  mov     rbp, rsp
0x1400565a5  sub     rsp, 40h
0x1400565a9  mov     rdi, rdx
0x1400565ac  mov     ecx, 364789Eh; this
0x1400565b1  mov     edx, 3; unsigned int
0x1400565b6  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1400565bb  mov     r8d, eax
0x1400565be  mov     qword ptr [rdi], 0
0x1400565c5  and     r8d, 0FFFFFF3Fh
0x1400565cc  mov     ecx, eax
0x1400565ce  and     eax, 80h
0x1400565d3  mov     edx, r8d
0x1400565d6  and     edx, 3
0x1400565d9  mov     r14d, 40h ; '@'
0x1400565df  shl     edx, 2
0x1400565e2  and     ecx, r14d
0x1400565e5  or      edx, ecx
0x1400565e7  shl     edx, 2
0x1400565ea  or      edx, eax
0x1400565ec  shl     edx, 3
0x1400565ef  test    r8d, r8d
0x1400565f2  jnz     short loc_1400565FC
0x1400565f4  mov     ecx, r14d
0x1400565f7  mov     r8d, r14d
0x1400565fa  jmp     short loc_140056609
0x1400565fc  xor     ecx, ecx
0x1400565fe  cmp     r8d, 2
0x140056602  cmovz   ecx, r14d
0x140056606  mov     r8d, ecx
0x140056609  mov     eax, edx
0x14005660b  mov     ebx, 1
0x140056610  or      eax, r8d
0x140056613  or      edx, ecx
0x140056615  mov     [rdi], eax
0x140056617  bt      edx, 0Ah
0x14005661b  jnb     short loc_140056625
0x14005661d  cmp     edx, 800h
0x140056623  jnb     short loc_140056630
0x140056625  xor     cl, cl
0x140056627  test    r14b, dl
0x14005662a  jz      loc_1400566F4
0x140056630  mov     rax, cs:Feature_Standalone_Future__descriptor
0x140056637  mov     r8d, [rax]
0x14005663a  test    r8b, 4
0x14005663e  jnz     short loc_140056653
0x140056640  lea     rdx, [rbp+arg_8]
0x140056644  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x140056649  mov     rcx, [rax]
0x14005664c  mov     [rbp+arg_8], rcx
0x140056650  mov     r8d, ecx
0x140056653  xor     eax, eax
0x140056655  mov     word ptr [rbp+arg_0+4], 3
0x14005665b  mov     r9d, r8d
0x14005665e  mov     [rsp+40h+var_10], eax
0x140056662  mov     dword ptr [rbp+arg_0], eax
0x140056665  lea     rcx, qword_140084298
0x14005666c  shr     r9d, 0Bh
0x140056670  lea     rax, [rbp+arg_0]
0x140056674  shr     r8d, 0Ah
0x140056678  and     r9d, ebx
0x14005667b  and     r8d, ebx
0x14005667e  mov     [rsp+40h+var_18], ebx
0x140056682  mov     edx, 2F29A04h
0x140056687  mov     [rsp+40h+var_20], rax
0x14005668c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140056691  mov     rax, cs:Feature_60011020__descriptor
0x140056698  mov     r8d, [rax]
0x14005669b  test    r8b, 4
0x14005669f  jnz     short loc_1400566B4
0x1400566a1  lea     rdx, [rbp+arg_8]
0x1400566a5  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_60011020@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60011020>::GetCachedFeatureEnabledState(void)
0x1400566aa  mov     rcx, [rax]
0x1400566ad  mov     [rbp+arg_8], rcx
0x1400566b1  mov     r8d, ecx
0x1400566b4  xor     eax, eax
0x1400566b6  mov     word ptr [rbp+arg_0+4], 3
0x1400566bc  mov     r9d, r8d
0x1400566bf  mov     [rsp+40h+var_10], eax
0x1400566c3  mov     dword ptr [rbp+arg_0], eax
0x1400566c6  lea     rcx, qword_1400843B8
0x1400566cd  shr     r9d, 0Bh
0x1400566d1  lea     rax, [rbp+arg_0]
0x1400566d5  shr     r8d, 0Ah
0x1400566d9  and     r9d, ebx
0x1400566dc  and     r8d, ebx
0x1400566df  mov     [rsp+40h+var_18], ebx
0x1400566e3  mov     edx, 393B20Ch
0x1400566e8  mov     [rsp+40h+var_20], rax
0x1400566ed  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1400566f2  mov     cl, bl
0x1400566f4  mov     eax, [rdi]
0x1400566f6  test    r14b, al
0x1400566f9  jz      short loc_1400566FF
0x1400566fb  test    cl, cl
0x1400566fd  jnz     short loc_140056701
0x1400566ff  xor     ebx, ebx
0x140056701  and     eax, 0FFFFFFFEh
0x140056704  or      eax, ebx
0x140056706  mov     rbx, [rsp+40h+arg_10]
0x14005670b  mov     [rdi], eax
0x14005670d  mov     rax, rdi
0x140056710  add     rsp, 40h
0x140056714  pop     r14
0x140056716  pop     rdi
0x140056717  pop     rbp
0x140056718  retn
```
