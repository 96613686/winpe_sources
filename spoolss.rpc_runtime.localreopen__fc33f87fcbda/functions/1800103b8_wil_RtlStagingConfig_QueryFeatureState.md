# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1800103b8`
- end: `0x1800104de`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180010390`

## callees

- `0x180005680`
- `0x18000ca40`
- `0x1800103b8`
- `0x180017010`

## string_xrefs

- `0x180010404`: `RtlQueryFeatureConfiguration`

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
0x1800103b8  mov     [rsp+arg_10], rbx
0x1800103bd  push    rbp
0x1800103be  push    rsi
0x1800103bf  push    rdi
0x1800103c0  sub     rsp, 50h
0x1800103c4  mov     rax, cs:__security_cookie
0x1800103cb  xor     rax, rsp
0x1800103ce  mov     [rsp+68h+var_20], rax
0x1800103d3  xor     esi, esi
0x1800103d5  mov     [rsp+68h+var_38], 0
0x1800103de  test    r8d, r8d
0x1800103e1  mov     rdi, r9
0x1800103e4  mov     ebp, edx
0x1800103e6  mov     rbx, rcx
0x1800103e9  setz    sil
0x1800103ed  xor     eax, eax
0x1800103ef  mov     [rsp+68h+var_30], rax
0x1800103f4  mov     [rsp+68h+var_28], eax
0x1800103f8  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800103ff  test    rax, rax
0x180010402  jnz     short loc_180010459
0x180010404  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001040b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180010410  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180010417  test    rax, rax
0x18001041a  jnz     short loc_180010459
0x18001041c  mov     r8d, 0C0000139h
0x180010422  xor     r9d, r9d
0x180010425  test    rdi, rdi
0x180010428  jz      short loc_180010438
0x18001042a  xor     ecx, ecx
0x18001042c  cmp     r8d, 80000022h
0x180010433  setnz   cl
0x180010436  mov     [rdi], ecx
0x180010438  mov     eax, r9d
0x18001043b  mov     rcx, [rsp+68h+var_20]
0x180010440  xor     rcx, rsp; StackCookie
0x180010443  call    __security_check_cookie
0x180010448  mov     rbx, [rsp+68h+arg_10]
0x180010450  add     rsp, 50h
0x180010454  pop     rdi
0x180010455  pop     rsi
0x180010456  pop     rbp
0x180010457  retn
0x180010459  lea     r9, [rsp+68h+var_30]
0x18001045e  mov     edx, esi
0x180010460  lea     r8, [rsp+68h+var_38]
0x180010465  mov     ecx, ebp
0x180010467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001046c  mov     r8d, eax
0x18001046f  test    eax, eax
0x180010471  jnz     short loc_1800104BB
0x180010473  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180010477  lea     r9d, [r8+1]
0x18001047b  mov     eax, [rsp+68h+var_28]
0x18001047f  mov     ecx, edx
0x180010481  mov     [rbx+0Ch], eax
0x180010484  mov     eax, edx
0x180010486  shr     eax, 0Eh
0x180010489  shr     ecx, 4
0x18001048c  and     eax, 3
0x18001048f  and     ecx, 3
0x180010492  mov     [rbx+8], eax
0x180010495  mov     [rbx], ecx
0x180010497  mov     eax, edx
0x180010499  mov     ecx, edx
0x18001049b  shr     eax, 6
0x18001049e  shr     ecx, 8
0x1800104a1  and     eax, r9d
0x1800104a4  and     cl, 3Fh
0x1800104a7  shr     edx, 7
0x1800104aa  and     edx, r9d
0x1800104ad  mov     [rbx+4], cl
0x1800104b0  mov     [rbx+10h], edx
0x1800104b3  mov     [rbx+14h], eax
0x1800104b6  jmp     loc_180010425
0x1800104bb  cmp     eax, 117h
0x1800104c0  jnz     loc_180010422
0x1800104c6  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800104ca  mov     r9d, 1
0x1800104d0  shr     eax, 7
0x1800104d3  and     eax, r9d
0x1800104d6  mov     [rbx+10h], eax
0x1800104d9  jmp     loc_180010425
```
