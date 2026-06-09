# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000d850`
- end: `0x18000d975`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d700`

## callees

- `0x18000d850`
- `0x180011354`
- `0x180012880`
- `0x180038010`

## string_xrefs

- `0x18000d89c`: `RtlQueryFeatureConfiguration`

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
0x18000d850  mov     [rsp+arg_10], rbx
0x18000d855  push    rbp
0x18000d856  push    rsi
0x18000d857  push    rdi
0x18000d858  sub     rsp, 50h
0x18000d85c  mov     rax, cs:__security_cookie
0x18000d863  xor     rax, rsp
0x18000d866  mov     [rsp+68h+var_20], rax
0x18000d86b  xor     esi, esi
0x18000d86d  mov     [rsp+68h+var_38], 0
0x18000d876  test    r8d, r8d
0x18000d879  mov     rdi, r9
0x18000d87c  mov     ebp, edx
0x18000d87e  mov     rbx, rcx
0x18000d881  setz    sil
0x18000d885  xor     eax, eax
0x18000d887  mov     [rsp+68h+var_30], rax
0x18000d88c  mov     [rsp+68h+var_28], eax
0x18000d890  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000d897  test    rax, rax
0x18000d89a  jnz     short loc_18000D8F0
0x18000d89c  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000d8a3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d8a8  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000d8af  test    rax, rax
0x18000d8b2  jnz     short loc_18000D8F0
0x18000d8b4  mov     r8d, 0C0000139h
0x18000d8ba  xor     r9d, r9d
0x18000d8bd  test    rdi, rdi
0x18000d8c0  jz      short loc_18000D8D0
0x18000d8c2  xor     ecx, ecx
0x18000d8c4  cmp     r8d, 80000022h
0x18000d8cb  setnz   cl
0x18000d8ce  mov     [rdi], ecx
0x18000d8d0  mov     eax, r9d
0x18000d8d3  mov     rcx, [rsp+68h+var_20]
0x18000d8d8  xor     rcx, rsp; StackCookie
0x18000d8db  call    __security_check_cookie
0x18000d8e0  mov     rbx, [rsp+68h+arg_10]
0x18000d8e8  add     rsp, 50h
0x18000d8ec  pop     rdi
0x18000d8ed  pop     rsi
0x18000d8ee  pop     rbp
0x18000d8ef  retn
0x18000d8f0  lea     r9, [rsp+68h+var_30]
0x18000d8f5  mov     edx, esi
0x18000d8f7  lea     r8, [rsp+68h+var_38]
0x18000d8fc  mov     ecx, ebp
0x18000d8fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d903  mov     r8d, eax
0x18000d906  test    eax, eax
0x18000d908  jnz     short loc_18000D952
0x18000d90a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000d90e  lea     r9d, [r8+1]
0x18000d912  mov     eax, [rsp+68h+var_28]
0x18000d916  mov     ecx, edx
0x18000d918  mov     [rbx+0Ch], eax
0x18000d91b  mov     eax, edx
0x18000d91d  shr     eax, 0Eh
0x18000d920  shr     ecx, 4
0x18000d923  and     eax, 3
0x18000d926  and     ecx, 3
0x18000d929  mov     [rbx+8], eax
0x18000d92c  mov     [rbx], ecx
0x18000d92e  mov     eax, edx
0x18000d930  mov     ecx, edx
0x18000d932  shr     eax, 6
0x18000d935  shr     ecx, 8
0x18000d938  and     eax, r9d
0x18000d93b  and     cl, 3Fh
0x18000d93e  shr     edx, 7
0x18000d941  and     edx, r9d
0x18000d944  mov     [rbx+4], cl
0x18000d947  mov     [rbx+10h], edx
0x18000d94a  mov     [rbx+14h], eax
0x18000d94d  jmp     loc_18000D8BD
0x18000d952  cmp     eax, 117h
0x18000d957  jnz     loc_18000D8BA
0x18000d95d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000d961  mov     r9d, 1
0x18000d967  shr     eax, 7
0x18000d96a  and     eax, r9d
0x18000d96d  mov     [rbx+10h], eax
0x18000d970  jmp     loc_18000D8BD
```
