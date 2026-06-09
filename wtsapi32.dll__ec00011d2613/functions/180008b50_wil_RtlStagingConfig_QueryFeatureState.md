# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180008b50`
- end: `0x180008c42`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180009298`

## callees

- `0x180008b50`
- `0x1800093ac`
- `0x1800155c0`
- `0x180016010`

## string_xrefs

- `0x180008b9b`: `RtlQueryFeatureConfiguration`

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
0x180008b50  mov     r11, rsp
0x180008b53  mov     [r11+18h], rbx
0x180008b57  mov     [r11+20h], rsi
0x180008b5b  push    rdi
0x180008b5c  sub     rsp, 50h
0x180008b60  mov     rax, cs:__security_cookie
0x180008b67  xor     rax, rsp
0x180008b6a  mov     [rsp+58h+var_10], rax
0x180008b6f  xor     edi, edi
0x180008b71  mov     qword ptr [r11-28h], 0
0x180008b79  test    r8d, r8d
0x180008b7c  mov     esi, edx
0x180008b7e  mov     rbx, rcx
0x180008b81  setz    dil
0x180008b85  xor     eax, eax
0x180008b87  mov     [r11-20h], rax
0x180008b8b  mov     [rsp+58h+var_18], eax
0x180008b8f  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180008b96  test    rax, rax
0x180008b99  jnz     short loc_180008BB7
0x180008b9b  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180008ba2  call    wil_details_GetNtDllProcedureAddress
0x180008ba7  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180008bae  test    rax, rax
0x180008bb1  jnz     short loc_180008BB7
0x180008bb3  xor     edx, edx
0x180008bb5  jmp     short loc_180008C23
0x180008bb7  lea     r9, [rsp+58h+var_20]
0x180008bbc  mov     edx, edi
0x180008bbe  lea     r8, [rsp+58h+var_28]
0x180008bc3  mov     ecx, esi
0x180008bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bca  test    eax, eax
0x180008bcc  jnz     short loc_180008C09
0x180008bce  mov     ecx, [rsp+58h+var_1C]
0x180008bd2  mov     edx, 1
0x180008bd7  mov     eax, ecx
0x180008bd9  shr     eax, 4
0x180008bdc  and     eax, 3
0x180008bdf  mov     [rbx], eax
0x180008be1  mov     eax, ecx
0x180008be3  shr     eax, 8
0x180008be6  and     al, 3Fh
0x180008be8  mov     [rbx+4], al
0x180008beb  mov     eax, [rsp+58h+var_18]
0x180008bef  mov     [rbx+0Ch], eax
0x180008bf2  mov     eax, ecx
0x180008bf4  shr     eax, 0Eh
0x180008bf7  and     eax, 3
0x180008bfa  mov     [rbx+8], eax
0x180008bfd  mov     eax, ecx
0x180008bff  shr     eax, 6
0x180008c02  and     eax, edx
0x180008c04  mov     [rbx+14h], eax
0x180008c07  jmp     short loc_180008C1B
0x180008c09  xor     edx, edx
0x180008c0b  cmp     eax, 117h
0x180008c10  jnz     short loc_180008C23
0x180008c12  mov     ecx, [rsp+58h+var_1C]
0x180008c16  mov     edx, 1
0x180008c1b  shr     ecx, 7
0x180008c1e  and     ecx, edx
0x180008c20  mov     [rbx+10h], ecx
0x180008c23  mov     eax, edx
0x180008c25  mov     rcx, [rsp+58h+var_10]
0x180008c2a  xor     rcx, rsp; StackCookie
0x180008c2d  call    __security_check_cookie
0x180008c32  mov     rbx, [rsp+58h+arg_10]
0x180008c37  mov     rsi, [rsp+58h+arg_18]
0x180008c3c  add     rsp, 50h
0x180008c40  pop     rdi
0x180008c41  retn
```
