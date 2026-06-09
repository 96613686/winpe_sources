# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000c784`
- end: `0x18000c8a9`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180006870`

## callees

- `0x18000ba00`
- `0x18000c784`
- `0x18001b150`
- `0x18001d010`

## string_xrefs

- `0x18000c7d0`: `RtlQueryFeatureConfiguration`

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
0x18000c784  mov     [rsp+arg_10], rbx
0x18000c789  push    rbp
0x18000c78a  push    rsi
0x18000c78b  push    rdi
0x18000c78c  sub     rsp, 50h
0x18000c790  mov     rax, cs:__security_cookie
0x18000c797  xor     rax, rsp
0x18000c79a  mov     [rsp+68h+var_20], rax
0x18000c79f  xor     esi, esi
0x18000c7a1  mov     [rsp+68h+var_38], 0
0x18000c7aa  test    r8d, r8d
0x18000c7ad  mov     rdi, r9
0x18000c7b0  mov     ebp, edx
0x18000c7b2  mov     rbx, rcx
0x18000c7b5  setz    sil
0x18000c7b9  xor     eax, eax
0x18000c7bb  mov     [rsp+68h+var_30], rax
0x18000c7c0  mov     [rsp+68h+var_28], eax
0x18000c7c4  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000c7cb  test    rax, rax
0x18000c7ce  jnz     short loc_18000C824
0x18000c7d0  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000c7d7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000c7dc  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000c7e3  test    rax, rax
0x18000c7e6  jnz     short loc_18000C824
0x18000c7e8  mov     r8d, 0C0000139h
0x18000c7ee  xor     r9d, r9d
0x18000c7f1  test    rdi, rdi
0x18000c7f4  jz      short loc_18000C804
0x18000c7f6  xor     ecx, ecx
0x18000c7f8  cmp     r8d, 80000022h
0x18000c7ff  setnz   cl
0x18000c802  mov     [rdi], ecx
0x18000c804  mov     eax, r9d
0x18000c807  mov     rcx, [rsp+68h+var_20]
0x18000c80c  xor     rcx, rsp; StackCookie
0x18000c80f  call    __security_check_cookie
0x18000c814  mov     rbx, [rsp+68h+arg_10]
0x18000c81c  add     rsp, 50h
0x18000c820  pop     rdi
0x18000c821  pop     rsi
0x18000c822  pop     rbp
0x18000c823  retn
0x18000c824  lea     r9, [rsp+68h+var_30]
0x18000c829  mov     edx, esi
0x18000c82b  lea     r8, [rsp+68h+var_38]
0x18000c830  mov     ecx, ebp
0x18000c832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c837  mov     r8d, eax
0x18000c83a  test    eax, eax
0x18000c83c  jnz     short loc_18000C886
0x18000c83e  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000c842  lea     r9d, [r8+1]
0x18000c846  mov     eax, [rsp+68h+var_28]
0x18000c84a  mov     ecx, edx
0x18000c84c  mov     [rbx+0Ch], eax
0x18000c84f  mov     eax, edx
0x18000c851  shr     eax, 0Eh
0x18000c854  shr     ecx, 4
0x18000c857  and     eax, 3
0x18000c85a  and     ecx, 3
0x18000c85d  mov     [rbx+8], eax
0x18000c860  mov     [rbx], ecx
0x18000c862  mov     eax, edx
0x18000c864  mov     ecx, edx
0x18000c866  shr     eax, 6
0x18000c869  shr     ecx, 8
0x18000c86c  and     eax, r9d
0x18000c86f  and     cl, 3Fh
0x18000c872  shr     edx, 7
0x18000c875  and     edx, r9d
0x18000c878  mov     [rbx+4], cl
0x18000c87b  mov     [rbx+10h], edx
0x18000c87e  mov     [rbx+14h], eax
0x18000c881  jmp     loc_18000C7F1
0x18000c886  cmp     eax, 117h
0x18000c88b  jnz     loc_18000C7EE
0x18000c891  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000c895  mov     r9d, 1
0x18000c89b  shr     eax, 7
0x18000c89e  and     eax, r9d
0x18000c8a1  mov     [rbx+10h], eax
0x18000c8a4  jmp     loc_18000C7F1
```
