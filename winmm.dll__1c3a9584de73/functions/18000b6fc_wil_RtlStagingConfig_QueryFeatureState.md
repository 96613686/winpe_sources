# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000b6fc`
- end: `0x18000b821`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800043e4`

## callees

- `0x18000ae00`
- `0x18000b6fc`
- `0x18000c990`
- `0x18001b010`

## string_xrefs

- `0x18000b748`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  BOOL v7; // esi
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v9; // r8d
  unsigned int v10; // r9d
  int v12; // eax
  unsigned int v13; // edx
  unsigned int v14; // ecx
  __int64 v15; // [rsp+30h] [rbp-38h] BYREF
  __int64 v16; // [rsp+38h] [rbp-30h] BYREF
  int v17; // [rsp+40h] [rbp-28h]

  v15 = 0;
  v7 = a3 == 0;
  v16 = 0;
  v17 = 0;
  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress;
    if ( !NtDllProcedureAddress )
    {
      v9 = -1073741511;
LABEL_4:
      v10 = 0;
      goto LABEL_5;
    }
  }
  v12 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v7, &v15, &v16);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 != 279 )
      goto LABEL_4;
    v10 = 1;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v16) >> 7) & 1;
  }
  else
  {
    v13 = HIDWORD(v16);
    v10 = 1;
    v14 = HIDWORD(v16);
    *(_DWORD *)(a1 + 12) = v17;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v14 >> 14;
    *(_DWORD *)a1 = (v14 >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v13) & 0x3F;
    *(_DWORD *)(a1 + 16) = (v13 >> 7) & 1;
    *(_DWORD *)(a1 + 20) = (v13 >> 6) & 1;
  }
LABEL_5:
  if ( a4 )
    *a4 = v9 != -2147483614;
  return v10;
}

```

## disassembly

```asm
0x18000b6fc  mov     [rsp+arg_10], rbx
0x18000b701  push    rbp
0x18000b702  push    rsi
0x18000b703  push    rdi
0x18000b704  sub     rsp, 50h
0x18000b708  mov     rax, cs:__security_cookie
0x18000b70f  xor     rax, rsp
0x18000b712  mov     [rsp+68h+var_20], rax
0x18000b717  xor     esi, esi
0x18000b719  mov     [rsp+68h+var_38], 0
0x18000b722  test    r8d, r8d
0x18000b725  mov     rdi, r9
0x18000b728  mov     ebp, edx
0x18000b72a  mov     rbx, rcx
0x18000b72d  setz    sil
0x18000b731  xor     eax, eax
0x18000b733  mov     [rsp+68h+var_30], rax
0x18000b738  mov     [rsp+68h+var_28], eax
0x18000b73c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000b743  test    rax, rax
0x18000b746  jnz     short loc_18000B79C
0x18000b748  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000b74f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b754  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000b75b  test    rax, rax
0x18000b75e  jnz     short loc_18000B79C
0x18000b760  mov     r8d, 0C0000139h
0x18000b766  xor     r9d, r9d
0x18000b769  test    rdi, rdi
0x18000b76c  jz      short loc_18000B77C
0x18000b76e  xor     ecx, ecx
0x18000b770  cmp     r8d, 80000022h
0x18000b777  setnz   cl
0x18000b77a  mov     [rdi], ecx
0x18000b77c  mov     eax, r9d
0x18000b77f  mov     rcx, [rsp+68h+var_20]
0x18000b784  xor     rcx, rsp; StackCookie
0x18000b787  call    __security_check_cookie
0x18000b78c  mov     rbx, [rsp+68h+arg_10]
0x18000b794  add     rsp, 50h
0x18000b798  pop     rdi
0x18000b799  pop     rsi
0x18000b79a  pop     rbp
0x18000b79b  retn
0x18000b79c  lea     r9, [rsp+68h+var_30]
0x18000b7a1  mov     edx, esi
0x18000b7a3  lea     r8, [rsp+68h+var_38]
0x18000b7a8  mov     ecx, ebp
0x18000b7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7af  mov     r8d, eax
0x18000b7b2  test    eax, eax
0x18000b7b4  jnz     short loc_18000B7FE
0x18000b7b6  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000b7ba  lea     r9d, [r8+1]
0x18000b7be  mov     eax, [rsp+68h+var_28]
0x18000b7c2  mov     ecx, edx
0x18000b7c4  mov     [rbx+0Ch], eax
0x18000b7c7  mov     eax, edx
0x18000b7c9  shr     eax, 0Eh
0x18000b7cc  shr     ecx, 4
0x18000b7cf  and     eax, 3
0x18000b7d2  and     ecx, 3
0x18000b7d5  mov     [rbx+8], eax
0x18000b7d8  mov     [rbx], ecx
0x18000b7da  mov     eax, edx
0x18000b7dc  mov     ecx, edx
0x18000b7de  shr     eax, 6
0x18000b7e1  shr     ecx, 8
0x18000b7e4  and     eax, r9d
0x18000b7e7  and     cl, 3Fh
0x18000b7ea  shr     edx, 7
0x18000b7ed  and     edx, r9d
0x18000b7f0  mov     [rbx+4], cl
0x18000b7f3  mov     [rbx+10h], edx
0x18000b7f6  mov     [rbx+14h], eax
0x18000b7f9  jmp     loc_18000B769
0x18000b7fe  cmp     eax, 117h
0x18000b803  jnz     loc_18000B766
0x18000b809  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000b80d  mov     r9d, 1
0x18000b813  shr     eax, 7
0x18000b816  and     eax, r9d
0x18000b819  mov     [rbx+10h], eax
0x18000b81c  jmp     loc_18000B769
```
