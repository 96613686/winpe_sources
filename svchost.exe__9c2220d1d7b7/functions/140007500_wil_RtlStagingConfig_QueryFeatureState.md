# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x140007500`
- end: `0x1400075f3`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140007bb0`

## callees

- `0x140004f90`
- `0x140007500`
- `0x140007d00`
- `0x140009010`

## string_xrefs

- `0x14000754b`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3)
{
  BOOL v5; // edi
  __int64 (__fastcall *NtDllProcedureAddress)(_QWORD, BOOL, __int64 *, __int64 *); // rax
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
  NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( g_wil_details_pfnRtlQueryFeatureConfiguration
    || (NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))wil_details_GetNtDllProcedureAddress(
                                                                                              "RtlQueryFeatureConfiguration"),
        (g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress) != 0) )
  {
    v8 = NtDllProcedureAddress(a2, v5, &v11, &v12);
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
0x140007500  mov     r11, rsp
0x140007503  mov     [r11+18h], rbx
0x140007507  mov     [r11+20h], rsi
0x14000750b  push    rdi
0x14000750c  sub     rsp, 50h
0x140007510  mov     rax, cs:__security_cookie
0x140007517  xor     rax, rsp
0x14000751a  mov     [rsp+58h+var_10], rax
0x14000751f  xor     edi, edi
0x140007521  mov     qword ptr [r11-28h], 0
0x140007529  test    r8d, r8d
0x14000752c  mov     esi, edx
0x14000752e  mov     rbx, rcx
0x140007531  setz    dil
0x140007535  xor     eax, eax
0x140007537  mov     [r11-20h], rax
0x14000753b  mov     [rsp+58h+var_18], eax
0x14000753f  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x140007546  test    rax, rax
0x140007549  jnz     short loc_140007567
0x14000754b  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x140007552  call    wil_details_GetNtDllProcedureAddress
0x140007557  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000755e  test    rax, rax
0x140007561  jnz     short loc_140007567
0x140007563  xor     edx, edx
0x140007565  jmp     short loc_1400075D3
0x140007567  lea     r9, [rsp+58h+var_20]
0x14000756c  mov     edx, edi
0x14000756e  lea     r8, [rsp+58h+var_28]
0x140007573  mov     ecx, esi
0x140007575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000757a  test    eax, eax
0x14000757c  jnz     short loc_1400075B9
0x14000757e  mov     ecx, [rsp+58h+var_1C]
0x140007582  mov     edx, 1
0x140007587  mov     eax, ecx
0x140007589  shr     eax, 4
0x14000758c  and     eax, 3
0x14000758f  mov     [rbx], eax
0x140007591  mov     eax, ecx
0x140007593  shr     eax, 8
0x140007596  and     al, 3Fh
0x140007598  mov     [rbx+4], al
0x14000759b  mov     eax, [rsp+58h+var_18]
0x14000759f  mov     [rbx+0Ch], eax
0x1400075a2  mov     eax, ecx
0x1400075a4  shr     eax, 0Eh
0x1400075a7  and     eax, 3
0x1400075aa  mov     [rbx+8], eax
0x1400075ad  mov     eax, ecx
0x1400075af  shr     eax, 6
0x1400075b2  and     eax, edx
0x1400075b4  mov     [rbx+14h], eax
0x1400075b7  jmp     short loc_1400075CB
0x1400075b9  xor     edx, edx
0x1400075bb  cmp     eax, 117h
0x1400075c0  jnz     short loc_1400075D3
0x1400075c2  mov     ecx, [rsp+58h+var_1C]
0x1400075c6  mov     edx, 1
0x1400075cb  shr     ecx, 7
0x1400075ce  and     ecx, edx
0x1400075d0  mov     [rbx+10h], ecx
0x1400075d3  mov     eax, edx
0x1400075d5  mov     rcx, [rsp+58h+var_10]
0x1400075da  xor     rcx, rsp; StackCookie
0x1400075dd  call    __security_check_cookie
0x1400075e2  mov     rbx, [rsp+58h+arg_10]
0x1400075e7  mov     rsi, [rsp+58h+arg_18]
0x1400075ec  add     rsp, 50h
0x1400075f0  pop     rdi
0x1400075f1  retn
```
