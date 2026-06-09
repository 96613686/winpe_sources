# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1800154ac`
- end: `0x18001559e`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `242`
- prototype: `__int64 __fastcall(__int64, unsigned int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180015c90`
- `0x180017f0c`

## callees

- `0x180010070`
- `0x1800154ac`
- `0x180015da4`
- `0x180019010`

## string_xrefs

- `0x1800154f7`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3)
{
  BOOL v5; // edi
  FARPROC NtDllProcedureAddress; // rax
  unsigned int v7; // edx
  int v8; // eax
  unsigned int v9; // ecx
  __int64 v11; // [rsp+30h] [rbp-28h] BYREF
  __int64 v12; // [rsp+38h] [rbp-20h] BYREF
  int v13; // [rsp+40h] [rbp-18h]

  v11 = 0;
  v5 = a3 == 0;
  v12 = 0;
  v13 = 0;
  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( g_wil_details_pfnRtlQueryFeatureConfiguration
    || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration"),
        (g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress) != 0) )
  {
    v8 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v5, &v11, &v12);
    if ( v8 )
    {
      v7 = 0;
      if ( v8 != 279 )
        return v7;
      v9 = HIDWORD(v12);
      v7 = 1;
    }
    else
    {
      v9 = HIDWORD(v12);
      v7 = 1;
      *(_DWORD *)a1 = (HIDWORD(v12) >> 4) & 3;
      *(_BYTE *)(a1 + 4) = BYTE1(v9) & 0x3F;
      *(_DWORD *)(a1 + 12) = v13;
      *(_DWORD *)(a1 + 8) = (unsigned __int16)v9 >> 14;
      *(_DWORD *)(a1 + 20) = (v9 >> 6) & 1;
    }
    *(_DWORD *)(a1 + 16) = (v9 >> 7) & 1;
    return v7;
  }
  return 0;
}

```

## disassembly

```asm
0x1800154ac  mov     r11, rsp
0x1800154af  mov     [r11+18h], rbx
0x1800154b3  mov     [r11+20h], rsi
0x1800154b7  push    rdi
0x1800154b8  sub     rsp, 50h
0x1800154bc  mov     rax, cs:__security_cookie
0x1800154c3  xor     rax, rsp
0x1800154c6  mov     [rsp+58h+var_10], rax
0x1800154cb  xor     edi, edi
0x1800154cd  mov     qword ptr [r11-28h], 0
0x1800154d5  test    r8d, r8d
0x1800154d8  mov     esi, edx
0x1800154da  mov     rbx, rcx
0x1800154dd  setz    dil
0x1800154e1  xor     eax, eax
0x1800154e3  mov     [r11-20h], rax
0x1800154e7  mov     [rsp+58h+var_18], eax
0x1800154eb  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800154f2  test    rax, rax
0x1800154f5  jnz     short loc_180015513
0x1800154f7  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1800154fe  call    wil_details_GetNtDllProcedureAddress
0x180015503  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001550a  test    rax, rax
0x18001550d  jnz     short loc_180015513
0x18001550f  xor     edx, edx
0x180015511  jmp     short loc_18001557F
0x180015513  lea     r9, [rsp+58h+var_20]
0x180015518  mov     edx, edi
0x18001551a  lea     r8, [rsp+58h+var_28]
0x18001551f  mov     ecx, esi
0x180015521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015526  test    eax, eax
0x180015528  jnz     short loc_180015565
0x18001552a  mov     ecx, [rsp+58h+var_1C]
0x18001552e  mov     edx, 1
0x180015533  mov     eax, ecx
0x180015535  shr     eax, 4
0x180015538  and     eax, 3
0x18001553b  mov     [rbx], eax
0x18001553d  mov     eax, ecx
0x18001553f  shr     eax, 8
0x180015542  and     al, 3Fh
0x180015544  mov     [rbx+4], al
0x180015547  mov     eax, [rsp+58h+var_18]
0x18001554b  mov     [rbx+0Ch], eax
0x18001554e  mov     eax, ecx
0x180015550  shr     eax, 0Eh
0x180015553  and     eax, 3
0x180015556  mov     [rbx+8], eax
0x180015559  mov     eax, ecx
0x18001555b  shr     eax, 6
0x18001555e  and     eax, edx
0x180015560  mov     [rbx+14h], eax
0x180015563  jmp     short loc_180015577
0x180015565  xor     edx, edx
0x180015567  cmp     eax, 117h
0x18001556c  jnz     short loc_18001557F
0x18001556e  mov     ecx, [rsp+58h+var_1C]
0x180015572  mov     edx, 1
0x180015577  shr     ecx, 7
0x18001557a  and     ecx, edx
0x18001557c  mov     [rbx+10h], ecx
0x18001557f  mov     eax, edx
0x180015581  mov     rcx, [rsp+58h+var_10]
0x180015586  xor     rcx, rsp; StackCookie
0x180015589  call    __security_check_cookie
0x18001558e  mov     rbx, [rsp+58h+arg_10]
0x180015593  mov     rsi, [rsp+58h+arg_18]
0x180015598  add     rsp, 50h
0x18001559c  pop     rdi
0x18001559d  retn
```
