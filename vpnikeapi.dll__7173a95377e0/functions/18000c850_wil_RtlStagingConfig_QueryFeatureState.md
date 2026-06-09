# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000c850`
- end: `0x18000c975`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180009434`

## callees

- `0x18000c12c`
- `0x18000c850`
- `0x18000cff0`
- `0x18000e010`

## string_xrefs

- `0x18000c89c`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  BOOL v7; // esi
  FARPROC NtDllProcedureAddress; // rax
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
  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
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
0x18000c850  mov     [rsp+arg_10], rbx
0x18000c855  push    rbp
0x18000c856  push    rsi
0x18000c857  push    rdi
0x18000c858  sub     rsp, 50h
0x18000c85c  mov     rax, cs:__security_cookie
0x18000c863  xor     rax, rsp
0x18000c866  mov     [rsp+68h+var_20], rax
0x18000c86b  xor     esi, esi
0x18000c86d  mov     [rsp+68h+var_38], 0
0x18000c876  test    r8d, r8d
0x18000c879  mov     rdi, r9
0x18000c87c  mov     ebp, edx
0x18000c87e  mov     rbx, rcx
0x18000c881  setz    sil
0x18000c885  xor     eax, eax
0x18000c887  mov     [rsp+68h+var_30], rax
0x18000c88c  mov     [rsp+68h+var_28], eax
0x18000c890  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000c897  test    rax, rax
0x18000c89a  jnz     short loc_18000C8F0
0x18000c89c  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000c8a3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000c8a8  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000c8af  test    rax, rax
0x18000c8b2  jnz     short loc_18000C8F0
0x18000c8b4  mov     r8d, 0C0000139h
0x18000c8ba  xor     r9d, r9d
0x18000c8bd  test    rdi, rdi
0x18000c8c0  jz      short loc_18000C8D0
0x18000c8c2  xor     ecx, ecx
0x18000c8c4  cmp     r8d, 80000022h
0x18000c8cb  setnz   cl
0x18000c8ce  mov     [rdi], ecx
0x18000c8d0  mov     eax, r9d
0x18000c8d3  mov     rcx, [rsp+68h+var_20]
0x18000c8d8  xor     rcx, rsp; StackCookie
0x18000c8db  call    __security_check_cookie
0x18000c8e0  mov     rbx, [rsp+68h+arg_10]
0x18000c8e8  add     rsp, 50h
0x18000c8ec  pop     rdi
0x18000c8ed  pop     rsi
0x18000c8ee  pop     rbp
0x18000c8ef  retn
0x18000c8f0  lea     r9, [rsp+68h+var_30]
0x18000c8f5  mov     edx, esi
0x18000c8f7  lea     r8, [rsp+68h+var_38]
0x18000c8fc  mov     ecx, ebp
0x18000c8fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c903  mov     r8d, eax
0x18000c906  test    eax, eax
0x18000c908  jnz     short loc_18000C952
0x18000c90a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000c90e  lea     r9d, [r8+1]
0x18000c912  mov     eax, [rsp+68h+var_28]
0x18000c916  mov     ecx, edx
0x18000c918  mov     [rbx+0Ch], eax
0x18000c91b  mov     eax, edx
0x18000c91d  shr     eax, 0Eh
0x18000c920  shr     ecx, 4
0x18000c923  and     eax, 3
0x18000c926  and     ecx, 3
0x18000c929  mov     [rbx+8], eax
0x18000c92c  mov     [rbx], ecx
0x18000c92e  mov     eax, edx
0x18000c930  mov     ecx, edx
0x18000c932  shr     eax, 6
0x18000c935  shr     ecx, 8
0x18000c938  and     eax, r9d
0x18000c93b  and     cl, 3Fh
0x18000c93e  shr     edx, 7
0x18000c941  and     edx, r9d
0x18000c944  mov     [rbx+4], cl
0x18000c947  mov     [rbx+10h], edx
0x18000c94a  mov     [rbx+14h], eax
0x18000c94d  jmp     loc_18000C8BD
0x18000c952  cmp     eax, 117h
0x18000c957  jnz     loc_18000C8BA
0x18000c95d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000c961  mov     r9d, 1
0x18000c967  shr     eax, 7
0x18000c96a  and     eax, r9d
0x18000c96d  mov     [rbx+10h], eax
0x18000c970  jmp     loc_18000C8BD
```
