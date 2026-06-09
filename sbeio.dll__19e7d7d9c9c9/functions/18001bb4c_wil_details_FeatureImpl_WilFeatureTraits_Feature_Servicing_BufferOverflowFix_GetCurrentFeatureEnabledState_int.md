# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BufferOverflowFix>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bb4c`
- end: `0x18001bc0b`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_BufferOverflowFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001b090`

## callees

- `0x18001bb4c`
- `0x180026d60`
- `0x180026fe4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BufferOverflowFix>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  unsigned int v9; // r8d
  int v10; // edi
  char v11; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x37EA6FE, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v8 = 0;
    if ( v6 == 2 )
      v8 = 64;
  }
  else
  {
    v8 = 64;
  }
  v9 = v8 | v7;
  v10 = 1;
  *(_DWORD *)a2 = v9;
  if ( (v9 & 0x400) != 0 && v9 >= 0x800 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    IsEnabled = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_12;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl);
  if ( v11 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_12:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v10 = 0;
  result = a2;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x18001bb4c  push    rbx
0x18001bb4e  push    rbp
0x18001bb4f  push    rsi
0x18001bb50  push    rdi
0x18001bb51  sub     rsp, 28h
0x18001bb55  mov     ecx, 37EA6FEh; this
0x18001bb5a  mov     rbx, rdx
0x18001bb5d  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001bb62  mov     edx, eax
0x18001bb64  mov     qword ptr [rbx], 0
0x18001bb6b  and     edx, 0FFFFFF3Fh
0x18001bb71  mov     ecx, eax
0x18001bb73  and     eax, 80h
0x18001bb78  mov     r8d, edx
0x18001bb7b  and     r8d, 3
0x18001bb7f  mov     ebp, 40h ; '@'
0x18001bb84  shl     r8d, 2
0x18001bb88  and     ecx, ebp
0x18001bb8a  or      r8d, ecx
0x18001bb8d  shl     r8d, 2
0x18001bb91  or      r8d, eax
0x18001bb94  shl     r8d, 3
0x18001bb98  test    edx, edx
0x18001bb9a  jnz     short loc_18001BBA0
0x18001bb9c  mov     eax, ebp
0x18001bb9e  jmp     short loc_18001BBA8
0x18001bba0  xor     eax, eax
0x18001bba2  cmp     edx, 2
0x18001bba5  cmovz   eax, ebp
0x18001bba8  or      r8d, eax
0x18001bbab  mov     edi, 1
0x18001bbb0  mov     [rbx], r8d
0x18001bbb3  bt      r8d, 0Ah
0x18001bbb8  jnb     short loc_18001BBC8
0x18001bbba  cmp     r8d, 800h
0x18001bbc1  jb      short loc_18001BBC8
0x18001bbc3  mov     sil, dil
0x18001bbc6  jmp     short loc_18001BBD2
0x18001bbc8  xor     sil, sil
0x18001bbcb  xor     al, al
0x18001bbcd  test    bpl, r8b
0x18001bbd0  jz      short loc_18001BBEB
0x18001bbd2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x18001bbd9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x18001bbde  test    sil, sil
0x18001bbe1  jz      short loc_18001BBEB
0x18001bbe3  test    al, al
0x18001bbe5  jnz     short loc_18001BBEB
0x18001bbe7  btr     dword ptr [rbx], 0Ah
0x18001bbeb  mov     ecx, [rbx]
0x18001bbed  test    bpl, cl
0x18001bbf0  jz      short loc_18001BBF6
0x18001bbf2  test    al, al
0x18001bbf4  jnz     short loc_18001BBF8
0x18001bbf6  xor     edi, edi
0x18001bbf8  and     ecx, 0FFFFFFFEh
0x18001bbfb  mov     rax, rbx
0x18001bbfe  or      ecx, edi
0x18001bc00  mov     [rbx], ecx
0x18001bc02  add     rsp, 28h
0x18001bc06  pop     rdi
0x18001bc07  pop     rsi
0x18001bc08  pop     rbp
0x18001bc09  pop     rbx
0x18001bc0a  retn
```
