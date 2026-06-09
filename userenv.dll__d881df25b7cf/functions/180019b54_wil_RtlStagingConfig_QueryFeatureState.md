# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180019b54`
- end: `0x180019c7a`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180016e30`

## callees

- `0x18000e640`
- `0x180010c90`
- `0x180019b54`
- `0x18001d010`

## string_xrefs

- `0x180019ba0`: `RtlQueryFeatureConfiguration`

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
0x180019b54  mov     [rsp+arg_10], rbx
0x180019b59  push    rbp
0x180019b5a  push    rsi
0x180019b5b  push    rdi
0x180019b5c  sub     rsp, 50h
0x180019b60  mov     rax, cs:__security_cookie
0x180019b67  xor     rax, rsp
0x180019b6a  mov     [rsp+68h+var_20], rax
0x180019b6f  xor     esi, esi
0x180019b71  mov     [rsp+68h+var_38], 0
0x180019b7a  test    r8d, r8d
0x180019b7d  mov     rdi, r9
0x180019b80  mov     ebp, edx
0x180019b82  mov     rbx, rcx
0x180019b85  setz    sil
0x180019b89  xor     eax, eax
0x180019b8b  mov     [rsp+68h+var_30], rax
0x180019b90  mov     [rsp+68h+var_28], eax
0x180019b94  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180019b9b  test    rax, rax
0x180019b9e  jnz     short loc_180019BF5
0x180019ba0  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180019ba7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180019bac  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180019bb3  test    rax, rax
0x180019bb6  jnz     short loc_180019BF5
0x180019bb8  mov     r8d, 0C0000139h
0x180019bbe  xor     r9d, r9d
0x180019bc1  test    rdi, rdi
0x180019bc4  jz      short loc_180019BD4
0x180019bc6  xor     ecx, ecx
0x180019bc8  cmp     r8d, 80000022h
0x180019bcf  setnz   cl
0x180019bd2  mov     [rdi], ecx
0x180019bd4  mov     eax, r9d
0x180019bd7  mov     rcx, [rsp+68h+var_20]
0x180019bdc  xor     rcx, rsp; StackCookie
0x180019bdf  call    __security_check_cookie
0x180019be4  mov     rbx, [rsp+68h+arg_10]
0x180019bec  add     rsp, 50h
0x180019bf0  pop     rdi
0x180019bf1  pop     rsi
0x180019bf2  pop     rbp
0x180019bf3  retn
0x180019bf5  lea     r9, [rsp+68h+var_30]
0x180019bfa  mov     edx, esi
0x180019bfc  lea     r8, [rsp+68h+var_38]
0x180019c01  mov     ecx, ebp
0x180019c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c08  mov     r8d, eax
0x180019c0b  test    eax, eax
0x180019c0d  jnz     short loc_180019C57
0x180019c0f  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180019c13  lea     r9d, [r8+1]
0x180019c17  mov     eax, [rsp+68h+var_28]
0x180019c1b  mov     ecx, edx
0x180019c1d  mov     [rbx+0Ch], eax
0x180019c20  mov     eax, edx
0x180019c22  shr     eax, 0Eh
0x180019c25  shr     ecx, 4
0x180019c28  and     eax, 3
0x180019c2b  and     ecx, 3
0x180019c2e  mov     [rbx+8], eax
0x180019c31  mov     [rbx], ecx
0x180019c33  mov     eax, edx
0x180019c35  mov     ecx, edx
0x180019c37  shr     eax, 6
0x180019c3a  shr     ecx, 8
0x180019c3d  and     eax, r9d
0x180019c40  and     cl, 3Fh
0x180019c43  shr     edx, 7
0x180019c46  and     edx, r9d
0x180019c49  mov     [rbx+4], cl
0x180019c4c  mov     [rbx+10h], edx
0x180019c4f  mov     [rbx+14h], eax
0x180019c52  jmp     loc_180019BC1
0x180019c57  cmp     eax, 117h
0x180019c5c  jnz     loc_180019BBE
0x180019c62  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180019c66  mov     r9d, 1
0x180019c6c  shr     eax, 7
0x180019c6f  and     eax, r9d
0x180019c72  mov     [rbx+10h], eax
0x180019c75  jmp     loc_180019BC1
```
