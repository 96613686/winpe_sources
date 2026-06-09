# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18002d094`
- end: `0x18002d1b9`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180029cd0`

## callees

- `0x180026a30`
- `0x18002c630`
- `0x18002d094`
- `0x180036010`

## string_xrefs

- `0x18002d0e0`: `RtlQueryFeatureConfiguration`

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
0x18002d094  mov     [rsp+arg_10], rbx
0x18002d099  push    rbp
0x18002d09a  push    rsi
0x18002d09b  push    rdi
0x18002d09c  sub     rsp, 50h
0x18002d0a0  mov     rax, cs:__security_cookie
0x18002d0a7  xor     rax, rsp
0x18002d0aa  mov     [rsp+68h+var_20], rax
0x18002d0af  xor     esi, esi
0x18002d0b1  mov     [rsp+68h+var_38], 0
0x18002d0ba  test    r8d, r8d
0x18002d0bd  mov     rdi, r9
0x18002d0c0  mov     ebp, edx
0x18002d0c2  mov     rbx, rcx
0x18002d0c5  setz    sil
0x18002d0c9  xor     eax, eax
0x18002d0cb  mov     [rsp+68h+var_30], rax
0x18002d0d0  mov     [rsp+68h+var_28], eax
0x18002d0d4  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18002d0db  test    rax, rax
0x18002d0de  jnz     short loc_18002D134
0x18002d0e0  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002d0e7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002d0ec  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18002d0f3  test    rax, rax
0x18002d0f6  jnz     short loc_18002D134
0x18002d0f8  mov     r8d, 0C0000139h
0x18002d0fe  xor     r9d, r9d
0x18002d101  test    rdi, rdi
0x18002d104  jz      short loc_18002D114
0x18002d106  xor     ecx, ecx
0x18002d108  cmp     r8d, 80000022h
0x18002d10f  setnz   cl
0x18002d112  mov     [rdi], ecx
0x18002d114  mov     eax, r9d
0x18002d117  mov     rcx, [rsp+68h+var_20]
0x18002d11c  xor     rcx, rsp; StackCookie
0x18002d11f  call    __security_check_cookie
0x18002d124  mov     rbx, [rsp+68h+arg_10]
0x18002d12c  add     rsp, 50h
0x18002d130  pop     rdi
0x18002d131  pop     rsi
0x18002d132  pop     rbp
0x18002d133  retn
0x18002d134  lea     r9, [rsp+68h+var_30]
0x18002d139  mov     edx, esi
0x18002d13b  lea     r8, [rsp+68h+var_38]
0x18002d140  mov     ecx, ebp
0x18002d142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d147  mov     r8d, eax
0x18002d14a  test    eax, eax
0x18002d14c  jnz     short loc_18002D196
0x18002d14e  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18002d152  lea     r9d, [r8+1]
0x18002d156  mov     eax, [rsp+68h+var_28]
0x18002d15a  mov     ecx, edx
0x18002d15c  mov     [rbx+0Ch], eax
0x18002d15f  mov     eax, edx
0x18002d161  shr     eax, 0Eh
0x18002d164  shr     ecx, 4
0x18002d167  and     eax, 3
0x18002d16a  and     ecx, 3
0x18002d16d  mov     [rbx+8], eax
0x18002d170  mov     [rbx], ecx
0x18002d172  mov     eax, edx
0x18002d174  mov     ecx, edx
0x18002d176  shr     eax, 6
0x18002d179  shr     ecx, 8
0x18002d17c  and     eax, r9d
0x18002d17f  and     cl, 3Fh
0x18002d182  shr     edx, 7
0x18002d185  and     edx, r9d
0x18002d188  mov     [rbx+4], cl
0x18002d18b  mov     [rbx+10h], edx
0x18002d18e  mov     [rbx+14h], eax
0x18002d191  jmp     loc_18002D101
0x18002d196  cmp     eax, 117h
0x18002d19b  jnz     loc_18002D0FE
0x18002d1a1  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18002d1a5  mov     r9d, 1
0x18002d1ab  shr     eax, 7
0x18002d1ae  and     eax, r9d
0x18002d1b1  mov     [rbx+10h], eax
0x18002d1b4  jmp     loc_18002D101
```
