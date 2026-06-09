# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x14000a448`
- end: `0x14000a56e`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14000a420`

## callees

- `0x140002480`
- `0x14000a118`
- `0x14000a448`
- `0x140029010`

## string_xrefs

- `0x14000a494`: `RtlQueryFeatureConfiguration`

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
0x14000a448  mov     [rsp+arg_10], rbx
0x14000a44d  push    rbp
0x14000a44e  push    rsi
0x14000a44f  push    rdi
0x14000a450  sub     rsp, 50h
0x14000a454  mov     rax, cs:__security_cookie
0x14000a45b  xor     rax, rsp
0x14000a45e  mov     [rsp+68h+var_20], rax
0x14000a463  xor     esi, esi
0x14000a465  mov     [rsp+68h+var_38], 0
0x14000a46e  test    r8d, r8d
0x14000a471  mov     rdi, r9
0x14000a474  mov     ebp, edx
0x14000a476  mov     rbx, rcx
0x14000a479  setz    sil
0x14000a47d  xor     eax, eax
0x14000a47f  mov     [rsp+68h+var_30], rax
0x14000a484  mov     [rsp+68h+var_28], eax
0x14000a488  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000a48f  test    rax, rax
0x14000a492  jnz     short loc_14000A4E9
0x14000a494  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000a49b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000a4a0  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000a4a7  test    rax, rax
0x14000a4aa  jnz     short loc_14000A4E9
0x14000a4ac  mov     r8d, 0C0000139h
0x14000a4b2  xor     r9d, r9d
0x14000a4b5  test    rdi, rdi
0x14000a4b8  jz      short loc_14000A4C8
0x14000a4ba  xor     ecx, ecx
0x14000a4bc  cmp     r8d, 80000022h
0x14000a4c3  setnz   cl
0x14000a4c6  mov     [rdi], ecx
0x14000a4c8  mov     eax, r9d
0x14000a4cb  mov     rcx, [rsp+68h+var_20]
0x14000a4d0  xor     rcx, rsp; StackCookie
0x14000a4d3  call    __security_check_cookie
0x14000a4d8  mov     rbx, [rsp+68h+arg_10]
0x14000a4e0  add     rsp, 50h
0x14000a4e4  pop     rdi
0x14000a4e5  pop     rsi
0x14000a4e6  pop     rbp
0x14000a4e7  retn
0x14000a4e9  lea     r9, [rsp+68h+var_30]
0x14000a4ee  mov     edx, esi
0x14000a4f0  lea     r8, [rsp+68h+var_38]
0x14000a4f5  mov     ecx, ebp
0x14000a4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a4fc  mov     r8d, eax
0x14000a4ff  test    eax, eax
0x14000a501  jnz     short loc_14000A54B
0x14000a503  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14000a507  lea     r9d, [r8+1]
0x14000a50b  mov     eax, [rsp+68h+var_28]
0x14000a50f  mov     ecx, edx
0x14000a511  mov     [rbx+0Ch], eax
0x14000a514  mov     eax, edx
0x14000a516  shr     eax, 0Eh
0x14000a519  shr     ecx, 4
0x14000a51c  and     eax, 3
0x14000a51f  and     ecx, 3
0x14000a522  mov     [rbx+8], eax
0x14000a525  mov     [rbx], ecx
0x14000a527  mov     eax, edx
0x14000a529  mov     ecx, edx
0x14000a52b  shr     eax, 6
0x14000a52e  shr     ecx, 8
0x14000a531  and     eax, r9d
0x14000a534  and     cl, 3Fh
0x14000a537  shr     edx, 7
0x14000a53a  and     edx, r9d
0x14000a53d  mov     [rbx+4], cl
0x14000a540  mov     [rbx+10h], edx
0x14000a543  mov     [rbx+14h], eax
0x14000a546  jmp     loc_14000A4B5
0x14000a54b  cmp     eax, 117h
0x14000a550  jnz     loc_14000A4B2
0x14000a556  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14000a55a  mov     r9d, 1
0x14000a560  shr     eax, 7
0x14000a563  and     eax, r9d
0x14000a566  mov     [rbx+10h], eax
0x14000a569  jmp     loc_14000A4B5
```
