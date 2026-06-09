# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14000a710`
- end: `0x14000a865`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `341`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x140002bb0`
- `0x140002c90`
- `0x14000a41c`
- `0x14000a710`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a7a4`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a7a4`

## string_xrefs

- `0x14000a78d`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 wil_details_ReevaluateOnFeatureConfigurationChange()
{
  int **i; // rbx
  unsigned int v1; // edi
  __int64 (__fastcall *SystemRoutineAddress)(_QWORD, __int64, __int64 *, __int64 *); // rax
  int v3; // eax
  __int16 v4; // dx
  __int16 v5; // dx
  struct _UNICODE_STRING SystemRoutineName; // [rsp+30h] [rbp-38h] BYREF
  __int64 v8; // [rsp+40h] [rbp-28h] BYREF
  __int64 v9; // [rsp+48h] [rbp-20h] BYREF
  int v10; // [rsp+50h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; i < (int **)wil_details_featureDescriptors_z; ++i )
  {
    if ( *i )
    {
LABEL_25:
      if ( !i )
        return wil_details_EvaluateFeatureDependencies();
      if ( !*((_BYTE *)i + 29) && !*((_BYTE *)i + 30) && !*((_BYTE *)i + 28) )
      {
        v1 = *((_DWORD *)i + 6);
        v9 = 0;
        v10 = 0;
        v8 = 0;
        SystemRoutineAddress = (__int64 (__fastcall *)(_QWORD, __int64, __int64 *, __int64 *))g_wil_details_pfnRtlQueryFeatureConfiguration;
        if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
        {
          *(_QWORD *)&SystemRoutineName.Length = 3801144;
          SystemRoutineName.Buffer = L"RtlQueryFeatureConfiguration";
          SystemRoutineAddress = (__int64 (__fastcall *)(_QWORD, __int64, __int64 *, __int64 *))MmGetSystemRoutineAddress(&SystemRoutineName);
          g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)SystemRoutineAddress;
          if ( !SystemRoutineAddress )
            goto LABEL_18;
        }
        v3 = SystemRoutineAddress(v1, 1, &v8, &v9);
        if ( v3 == -2147483614 || v3 == -1073741275 )
          goto LABEL_18;
        if ( v3 )
        {
          if ( v3 == 279 )
          {
            v4 = BYTE4(v9) & 0x80;
            goto LABEL_17;
          }
LABEL_18:
          v5 = 518;
        }
        else
        {
          v4 = BYTE4(v9) & 0xB0 | (4 * (WORD2(v9) & 0xFFD0));
LABEL_17:
          v5 = (8 * v4) | 0x206;
        }
        _InterlockedXor(*i, ((unsigned __int16)v5 ^ (unsigned __int16)**i) & 0xF80);
      }
      for ( i += 7; i < (int **)wil_details_featureDescriptors_z; ++i )
      {
        if ( *i )
          goto LABEL_25;
      }
      return wil_details_EvaluateFeatureDependencies();
    }
  }
  return wil_details_EvaluateFeatureDependencies();
}

```

## disassembly

```asm
0x14000a710  push    rbp
0x14000a712  push    rbx
0x14000a713  push    rdi
0x14000a714  push    r14
0x14000a716  mov     rbp, rsp
0x14000a719  sub     rsp, 68h
0x14000a71d  mov     rax, cs:__security_cookie
0x14000a724  xor     rax, rsp
0x14000a727  mov     [rbp+var_10], rax
0x14000a72b  lea     rbx, wil_details_featureDescriptors_a
0x14000a732  lea     r14, wil_details_featureDescriptors_z
0x14000a739  jmp     short loc_14000A749
0x14000a73b  cmp     qword ptr [rbx], 0
0x14000a73f  jnz     loc_14000A840
0x14000a745  add     rbx, 8
0x14000a749  cmp     rbx, r14
0x14000a74c  jb      short loc_14000A73B
0x14000a74e  jmp     loc_14000A849
0x14000a753  cmp     byte ptr [rbx+1Dh], 0
0x14000a757  jnz     loc_14000A829
0x14000a75d  cmp     byte ptr [rbx+1Eh], 0
0x14000a761  jnz     loc_14000A829
0x14000a767  cmp     byte ptr [rbx+1Ch], 0
0x14000a76b  jnz     loc_14000A829
0x14000a771  mov     edi, [rbx+18h]
0x14000a774  xor     eax, eax
0x14000a776  mov     [rbp+var_20], rax
0x14000a77a  mov     [rbp+var_18], eax
0x14000a77d  mov     [rbp+var_28], rax
0x14000a781  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000a788  test    rax, rax
0x14000a78b  jnz     short loc_14000A7BC
0x14000a78d  lea     rax, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000a794  mov     qword ptr [rbp+SystemRoutineName.Length], 3A0038h
0x14000a79c  lea     rcx, [rbp+SystemRoutineName]; SystemRoutineName
0x14000a7a0  mov     [rbp+SystemRoutineName.Buffer], rax
0x14000a7a4  call    cs:__imp_MmGetSystemRoutineAddress
0x14000a7ab  nop     dword ptr [rax+rax+00h]
0x14000a7b0  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000a7b7  test    rax, rax
0x14000a7ba  jz      short loc_14000A811
0x14000a7bc  lea     r9, [rbp+var_20]
0x14000a7c0  mov     edx, 1
0x14000a7c5  lea     r8, [rbp+var_28]
0x14000a7c9  mov     ecx, edi
0x14000a7cb  call    _guard_dispatch_icall
0x14000a7d0  cmp     eax, 80000022h
0x14000a7d5  jz      short loc_14000A811
0x14000a7d7  cmp     eax, 0C0000225h
0x14000a7dc  jz      short loc_14000A811
0x14000a7de  test    eax, eax
0x14000a7e0  jz      short loc_14000A7F4
0x14000a7e2  cmp     eax, 117h
0x14000a7e7  jnz     short loc_14000A811
0x14000a7e9  mov     edx, dword ptr [rbp+var_20+4]
0x14000a7ec  and     edx, 80h
0x14000a7f2  jmp     short loc_14000A806
0x14000a7f4  mov     eax, dword ptr [rbp+var_20+4]
0x14000a7f7  mov     edx, eax
0x14000a7f9  and     edx, 0FFFFFFD0h
0x14000a7fc  and     eax, 0B0h
0x14000a801  shl     edx, 2
0x14000a804  or      edx, eax
0x14000a806  shl     edx, 3
0x14000a809  or      edx, 206h
0x14000a80f  jmp     short loc_14000A816
0x14000a811  mov     edx, 206h
0x14000a816  mov     rax, [rbx]
0x14000a819  mov     ecx, [rax]
0x14000a81b  mov     rax, [rbx]
0x14000a81e  xor     ecx, edx
0x14000a820  and     ecx, 0F80h
0x14000a826  lock xor [rax], ecx
0x14000a829  add     rbx, 38h ; '8'
0x14000a82d  jmp     short loc_14000A839
0x14000a82f  cmp     qword ptr [rbx], 0
0x14000a833  jnz     short loc_14000A840
0x14000a835  add     rbx, 8
0x14000a839  cmp     rbx, r14
0x14000a83c  jb      short loc_14000A82F
0x14000a83e  jmp     short loc_14000A849
0x14000a840  test    rbx, rbx
0x14000a843  jnz     loc_14000A753
0x14000a849  call    wil_details_EvaluateFeatureDependencies
0x14000a84e  mov     rcx, [rbp+var_10]
0x14000a852  xor     rcx, rsp; StackCookie
0x14000a855  call    __security_check_cookie
0x14000a85a  add     rsp, 68h
0x14000a85e  pop     r14
0x14000a860  pop     rdi
0x14000a861  pop     rbx
0x14000a862  pop     rbp
0x14000a863  retn
```
