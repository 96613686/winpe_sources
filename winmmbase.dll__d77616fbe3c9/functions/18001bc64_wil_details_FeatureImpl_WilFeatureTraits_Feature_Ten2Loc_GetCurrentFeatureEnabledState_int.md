# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bc64`
- end: `0x18001bd42`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b3bc`

## callees

- `0x1800162fc`
- `0x18001bc64`
- `0x18001c4a4`
- `0x18001c924`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
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
  char v13; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419CA, (unsigned int)a2, a3, a4);
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
      goto LABEL_16;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetImpl'::`2'::impl);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_16:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18001bc64  push    rbx
0x18001bc66  push    rbp
0x18001bc67  push    rsi
0x18001bc68  push    rdi
0x18001bc69  sub     rsp, 28h
0x18001bc6d  mov     ecx, 38419CAh; this
0x18001bc72  mov     rbx, rdx
0x18001bc75  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001bc7a  mov     edx, eax
0x18001bc7c  mov     qword ptr [rbx], 0
0x18001bc83  and     edx, 0FFFFFF3Fh
0x18001bc89  mov     ecx, eax
0x18001bc8b  and     eax, 80h
0x18001bc90  mov     r8d, edx
0x18001bc93  and     r8d, 3
0x18001bc97  mov     ebp, 40h ; '@'
0x18001bc9c  shl     r8d, 2
0x18001bca0  and     ecx, ebp
0x18001bca2  or      r8d, ecx
0x18001bca5  shl     r8d, 2
0x18001bca9  or      r8d, eax
0x18001bcac  shl     r8d, 3
0x18001bcb0  test    edx, edx
0x18001bcb2  jnz     short loc_18001BCBA
0x18001bcb4  mov     ecx, ebp
0x18001bcb6  mov     edx, ebp
0x18001bcb8  jmp     short loc_18001BCC4
0x18001bcba  xor     ecx, ecx
0x18001bcbc  cmp     edx, 2
0x18001bcbf  cmovz   ecx, ebp
0x18001bcc2  mov     edx, ecx
0x18001bcc4  mov     eax, r8d
0x18001bcc7  mov     edi, 1
0x18001bccc  or      eax, edx
0x18001bcce  or      r8d, ecx
0x18001bcd1  mov     [rbx], eax
0x18001bcd3  bt      r8d, 0Ah
0x18001bcd8  jnb     short loc_18001BCE8
0x18001bcda  cmp     r8d, 800h
0x18001bce1  jb      short loc_18001BCE8
0x18001bce3  mov     sil, dil
0x18001bce6  jmp     short loc_18001BCF2
0x18001bce8  xor     sil, sil
0x18001bceb  xor     cl, cl
0x18001bced  test    bpl, r8b
0x18001bcf0  jz      short loc_18001BD22
0x18001bcf2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x18001bcf9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x18001bcfe  test    al, al
0x18001bd00  jz      short loc_18001BD13
0x18001bd02  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetImpl(void)'::`2'::impl
0x18001bd09  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001bd0e  mov     cl, dil
0x18001bd11  jmp     short loc_18001BD15
0x18001bd13  xor     cl, cl
0x18001bd15  test    sil, sil
0x18001bd18  jz      short loc_18001BD22
0x18001bd1a  test    cl, cl
0x18001bd1c  jnz     short loc_18001BD22
0x18001bd1e  btr     dword ptr [rbx], 0Ah
0x18001bd22  mov     eax, [rbx]
0x18001bd24  test    bpl, al
0x18001bd27  jz      short loc_18001BD2D
0x18001bd29  test    cl, cl
0x18001bd2b  jnz     short loc_18001BD2F
0x18001bd2d  xor     edi, edi
0x18001bd2f  and     eax, 0FFFFFFFEh
0x18001bd32  or      eax, edi
0x18001bd34  mov     [rbx], eax
0x18001bd36  mov     rax, rbx
0x18001bd39  add     rsp, 28h
0x18001bd3d  pop     rdi
0x18001bd3e  pop     rsi
0x18001bd3f  pop     rbp
0x18001bd40  pop     rbx
0x18001bd41  retn
```
