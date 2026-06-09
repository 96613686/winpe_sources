# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18002f018`
- end: `0x18002f10b`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002f6c8`

## callees

- `0x18001fbd0`
- `0x18002f018`
- `0x18002f818`
- `0x180037010`

## string_xrefs

- `0x18002f063`: `RtlQueryFeatureConfiguration`

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
0x18002f018  mov     r11, rsp
0x18002f01b  mov     [r11+18h], rbx
0x18002f01f  mov     [r11+20h], rsi
0x18002f023  push    rdi
0x18002f024  sub     rsp, 50h
0x18002f028  mov     rax, cs:__security_cookie
0x18002f02f  xor     rax, rsp
0x18002f032  mov     [rsp+58h+var_10], rax
0x18002f037  xor     edi, edi
0x18002f039  mov     qword ptr [r11-28h], 0
0x18002f041  test    r8d, r8d
0x18002f044  mov     esi, edx
0x18002f046  mov     rbx, rcx
0x18002f049  setz    dil
0x18002f04d  xor     eax, eax
0x18002f04f  mov     [r11-20h], rax
0x18002f053  mov     [rsp+58h+var_18], eax
0x18002f057  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18002f05e  test    rax, rax
0x18002f061  jnz     short loc_18002F07F
0x18002f063  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002f06a  call    wil_details_GetNtDllProcedureAddress
0x18002f06f  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18002f076  test    rax, rax
0x18002f079  jnz     short loc_18002F07F
0x18002f07b  xor     edx, edx
0x18002f07d  jmp     short loc_18002F0EB
0x18002f07f  lea     r9, [rsp+58h+var_20]
0x18002f084  mov     edx, edi
0x18002f086  lea     r8, [rsp+58h+var_28]
0x18002f08b  mov     ecx, esi
0x18002f08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f092  test    eax, eax
0x18002f094  jnz     short loc_18002F0D1
0x18002f096  mov     ecx, [rsp+58h+var_1C]
0x18002f09a  mov     edx, 1
0x18002f09f  mov     eax, ecx
0x18002f0a1  shr     eax, 4
0x18002f0a4  and     eax, 3
0x18002f0a7  mov     [rbx], eax
0x18002f0a9  mov     eax, ecx
0x18002f0ab  shr     eax, 8
0x18002f0ae  and     al, 3Fh
0x18002f0b0  mov     [rbx+4], al
0x18002f0b3  mov     eax, [rsp+58h+var_18]
0x18002f0b7  mov     [rbx+0Ch], eax
0x18002f0ba  mov     eax, ecx
0x18002f0bc  shr     eax, 0Eh
0x18002f0bf  and     eax, 3
0x18002f0c2  mov     [rbx+8], eax
0x18002f0c5  mov     eax, ecx
0x18002f0c7  shr     eax, 6
0x18002f0ca  and     eax, edx
0x18002f0cc  mov     [rbx+14h], eax
0x18002f0cf  jmp     short loc_18002F0E3
0x18002f0d1  xor     edx, edx
0x18002f0d3  cmp     eax, 117h
0x18002f0d8  jnz     short loc_18002F0EB
0x18002f0da  mov     ecx, [rsp+58h+var_1C]
0x18002f0de  mov     edx, 1
0x18002f0e3  shr     ecx, 7
0x18002f0e6  and     ecx, edx
0x18002f0e8  mov     [rbx+10h], ecx
0x18002f0eb  mov     eax, edx
0x18002f0ed  mov     rcx, [rsp+58h+var_10]
0x18002f0f2  xor     rcx, rsp; StackCookie
0x18002f0f5  call    __security_check_cookie
0x18002f0fa  mov     rbx, [rsp+58h+arg_10]
0x18002f0ff  mov     rsi, [rsp+58h+arg_18]
0x18002f104  add     rsp, 50h
0x18002f108  pop     rdi
0x18002f109  retn
```
