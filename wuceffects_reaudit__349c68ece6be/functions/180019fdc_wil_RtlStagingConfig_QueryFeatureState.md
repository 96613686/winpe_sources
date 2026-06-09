# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180019fdc`
- end: `0x18001a101`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180019eb0`

## callees

- `0x180018154`
- `0x180019fdc`
- `0x180021060`
- `0x18002e010`

## string_xrefs

- `0x18001a028`: `RtlQueryFeatureConfiguration`

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
0x180019fdc  mov     [rsp+arg_10], rbx
0x180019fe1  push    rbp
0x180019fe2  push    rsi
0x180019fe3  push    rdi
0x180019fe4  sub     rsp, 50h
0x180019fe8  mov     rax, cs:__security_cookie
0x180019fef  xor     rax, rsp
0x180019ff2  mov     [rsp+68h+var_20], rax
0x180019ff7  xor     esi, esi
0x180019ff9  mov     [rsp+68h+var_38], 0
0x18001a002  test    r8d, r8d
0x18001a005  mov     rdi, r9
0x18001a008  mov     ebp, edx
0x18001a00a  mov     rbx, rcx
0x18001a00d  setz    sil
0x18001a011  xor     eax, eax
0x18001a013  mov     [rsp+68h+var_30], rax
0x18001a018  mov     [rsp+68h+var_28], eax
0x18001a01c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001a023  test    rax, rax
0x18001a026  jnz     short loc_18001A07C
0x18001a028  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001a02f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001a034  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001a03b  test    rax, rax
0x18001a03e  jnz     short loc_18001A07C
0x18001a040  mov     r8d, 0C0000139h
0x18001a046  xor     r9d, r9d
0x18001a049  test    rdi, rdi
0x18001a04c  jz      short loc_18001A05C
0x18001a04e  xor     ecx, ecx
0x18001a050  cmp     r8d, 80000022h
0x18001a057  setnz   cl
0x18001a05a  mov     [rdi], ecx
0x18001a05c  mov     eax, r9d
0x18001a05f  mov     rcx, [rsp+68h+var_20]
0x18001a064  xor     rcx, rsp; StackCookie
0x18001a067  call    __security_check_cookie
0x18001a06c  mov     rbx, [rsp+68h+arg_10]
0x18001a074  add     rsp, 50h
0x18001a078  pop     rdi
0x18001a079  pop     rsi
0x18001a07a  pop     rbp
0x18001a07b  retn
0x18001a07c  lea     r9, [rsp+68h+var_30]
0x18001a081  mov     edx, esi
0x18001a083  lea     r8, [rsp+68h+var_38]
0x18001a088  mov     ecx, ebp
0x18001a08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a08f  mov     r8d, eax
0x18001a092  test    eax, eax
0x18001a094  jnz     short loc_18001A0DE
0x18001a096  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18001a09a  lea     r9d, [r8+1]
0x18001a09e  mov     eax, [rsp+68h+var_28]
0x18001a0a2  mov     ecx, edx
0x18001a0a4  mov     [rbx+0Ch], eax
0x18001a0a7  mov     eax, edx
0x18001a0a9  shr     eax, 0Eh
0x18001a0ac  shr     ecx, 4
0x18001a0af  and     eax, 3
0x18001a0b2  and     ecx, 3
0x18001a0b5  mov     [rbx+8], eax
0x18001a0b8  mov     [rbx], ecx
0x18001a0ba  mov     eax, edx
0x18001a0bc  mov     ecx, edx
0x18001a0be  shr     eax, 6
0x18001a0c1  shr     ecx, 8
0x18001a0c4  and     eax, r9d
0x18001a0c7  and     cl, 3Fh
0x18001a0ca  shr     edx, 7
0x18001a0cd  and     edx, r9d
0x18001a0d0  mov     [rbx+4], cl
0x18001a0d3  mov     [rbx+10h], edx
0x18001a0d6  mov     [rbx+14h], eax
0x18001a0d9  jmp     loc_18001A049
0x18001a0de  cmp     eax, 117h
0x18001a0e3  jnz     loc_18001A046
0x18001a0e9  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18001a0ed  mov     r9d, 1
0x18001a0f3  shr     eax, 7
0x18001a0f6  and     eax, r9d
0x18001a0f9  mov     [rbx+10h], eax
0x18001a0fc  jmp     loc_18001A049
```
