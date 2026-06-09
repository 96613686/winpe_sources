# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14000a670`
- end: `0x14000a7c5`
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
- `0x14000a670`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a704`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a704`

## string_xrefs

- `0x14000a6ed`: `RtlQueryFeatureConfiguration`

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
0x14000a670  push    rbp
0x14000a672  push    rbx
0x14000a673  push    rdi
0x14000a674  push    r14
0x14000a676  mov     rbp, rsp
0x14000a679  sub     rsp, 68h
0x14000a67d  mov     rax, cs:__security_cookie
0x14000a684  xor     rax, rsp
0x14000a687  mov     [rbp+var_10], rax
0x14000a68b  lea     rbx, wil_details_featureDescriptors_a
0x14000a692  lea     r14, wil_details_featureDescriptors_z
0x14000a699  jmp     short loc_14000A6A9
0x14000a69b  cmp     qword ptr [rbx], 0
0x14000a69f  jnz     loc_14000A7A0
0x14000a6a5  add     rbx, 8
0x14000a6a9  cmp     rbx, r14
0x14000a6ac  jb      short loc_14000A69B
0x14000a6ae  jmp     loc_14000A7A9
0x14000a6b3  cmp     byte ptr [rbx+1Dh], 0
0x14000a6b7  jnz     loc_14000A789
0x14000a6bd  cmp     byte ptr [rbx+1Eh], 0
0x14000a6c1  jnz     loc_14000A789
0x14000a6c7  cmp     byte ptr [rbx+1Ch], 0
0x14000a6cb  jnz     loc_14000A789
0x14000a6d1  mov     edi, [rbx+18h]
0x14000a6d4  xor     eax, eax
0x14000a6d6  mov     [rbp+var_20], rax
0x14000a6da  mov     [rbp+var_18], eax
0x14000a6dd  mov     [rbp+var_28], rax
0x14000a6e1  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000a6e8  test    rax, rax
0x14000a6eb  jnz     short loc_14000A71C
0x14000a6ed  lea     rax, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000a6f4  mov     qword ptr [rbp+SystemRoutineName.Length], 3A0038h
0x14000a6fc  lea     rcx, [rbp+SystemRoutineName]; SystemRoutineName
0x14000a700  mov     [rbp+SystemRoutineName.Buffer], rax
0x14000a704  call    cs:__imp_MmGetSystemRoutineAddress
0x14000a70b  nop     dword ptr [rax+rax+00h]
0x14000a710  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000a717  test    rax, rax
0x14000a71a  jz      short loc_14000A771
0x14000a71c  lea     r9, [rbp+var_20]
0x14000a720  mov     edx, 1
0x14000a725  lea     r8, [rbp+var_28]
0x14000a729  mov     ecx, edi
0x14000a72b  call    _guard_dispatch_icall
0x14000a730  cmp     eax, 80000022h
0x14000a735  jz      short loc_14000A771
0x14000a737  cmp     eax, 0C0000225h
0x14000a73c  jz      short loc_14000A771
0x14000a73e  test    eax, eax
0x14000a740  jz      short loc_14000A754
0x14000a742  cmp     eax, 117h
0x14000a747  jnz     short loc_14000A771
0x14000a749  mov     edx, dword ptr [rbp+var_20+4]
0x14000a74c  and     edx, 80h
0x14000a752  jmp     short loc_14000A766
0x14000a754  mov     eax, dword ptr [rbp+var_20+4]
0x14000a757  mov     edx, eax
0x14000a759  and     edx, 0FFFFFFD0h
0x14000a75c  and     eax, 0B0h
0x14000a761  shl     edx, 2
0x14000a764  or      edx, eax
0x14000a766  shl     edx, 3
0x14000a769  or      edx, 206h
0x14000a76f  jmp     short loc_14000A776
0x14000a771  mov     edx, 206h
0x14000a776  mov     rax, [rbx]
0x14000a779  mov     ecx, [rax]
0x14000a77b  mov     rax, [rbx]
0x14000a77e  xor     ecx, edx
0x14000a780  and     ecx, 0F80h
0x14000a786  lock xor [rax], ecx
0x14000a789  add     rbx, 38h ; '8'
0x14000a78d  jmp     short loc_14000A799
0x14000a78f  cmp     qword ptr [rbx], 0
0x14000a793  jnz     short loc_14000A7A0
0x14000a795  add     rbx, 8
0x14000a799  cmp     rbx, r14
0x14000a79c  jb      short loc_14000A78F
0x14000a79e  jmp     short loc_14000A7A9
0x14000a7a0  test    rbx, rbx
0x14000a7a3  jnz     loc_14000A6B3
0x14000a7a9  call    wil_details_EvaluateFeatureDependencies
0x14000a7ae  mov     rcx, [rbp+var_10]
0x14000a7b2  xor     rcx, rsp; StackCookie
0x14000a7b5  call    __security_check_cookie
0x14000a7ba  add     rsp, 68h
0x14000a7be  pop     r14
0x14000a7c0  pop     rdi
0x14000a7c1  pop     rbx
0x14000a7c2  pop     rbp
0x14000a7c3  retn
```
