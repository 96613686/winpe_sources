# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18002d968`
- end: `0x18002da8d`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002b004`

## callees

- `0x180024a50`
- `0x18002d770`
- `0x18002d968`
- `0x18003c010`

## string_xrefs

- `0x18002d9b4`: `RtlQueryFeatureConfiguration`

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
0x18002d968  mov     [rsp+arg_10], rbx
0x18002d96d  push    rbp
0x18002d96e  push    rsi
0x18002d96f  push    rdi
0x18002d970  sub     rsp, 50h
0x18002d974  mov     rax, cs:__security_cookie
0x18002d97b  xor     rax, rsp
0x18002d97e  mov     [rsp+68h+var_20], rax
0x18002d983  xor     esi, esi
0x18002d985  mov     [rsp+68h+var_38], 0
0x18002d98e  test    r8d, r8d
0x18002d991  mov     rdi, r9
0x18002d994  mov     ebp, edx
0x18002d996  mov     rbx, rcx
0x18002d999  setz    sil
0x18002d99d  xor     eax, eax
0x18002d99f  mov     [rsp+68h+var_30], rax
0x18002d9a4  mov     [rsp+68h+var_28], eax
0x18002d9a8  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18002d9af  test    rax, rax
0x18002d9b2  jnz     short loc_18002DA08
0x18002d9b4  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002d9bb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002d9c0  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18002d9c7  test    rax, rax
0x18002d9ca  jnz     short loc_18002DA08
0x18002d9cc  mov     r8d, 0C0000139h
0x18002d9d2  xor     r9d, r9d
0x18002d9d5  test    rdi, rdi
0x18002d9d8  jz      short loc_18002D9E8
0x18002d9da  xor     ecx, ecx
0x18002d9dc  cmp     r8d, 80000022h
0x18002d9e3  setnz   cl
0x18002d9e6  mov     [rdi], ecx
0x18002d9e8  mov     eax, r9d
0x18002d9eb  mov     rcx, [rsp+68h+var_20]
0x18002d9f0  xor     rcx, rsp; StackCookie
0x18002d9f3  call    __security_check_cookie
0x18002d9f8  mov     rbx, [rsp+68h+arg_10]
0x18002da00  add     rsp, 50h
0x18002da04  pop     rdi
0x18002da05  pop     rsi
0x18002da06  pop     rbp
0x18002da07  retn
0x18002da08  lea     r9, [rsp+68h+var_30]
0x18002da0d  mov     edx, esi
0x18002da0f  lea     r8, [rsp+68h+var_38]
0x18002da14  mov     ecx, ebp
0x18002da16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da1b  mov     r8d, eax
0x18002da1e  test    eax, eax
0x18002da20  jnz     short loc_18002DA6A
0x18002da22  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18002da26  lea     r9d, [r8+1]
0x18002da2a  mov     eax, [rsp+68h+var_28]
0x18002da2e  mov     ecx, edx
0x18002da30  mov     [rbx+0Ch], eax
0x18002da33  mov     eax, edx
0x18002da35  shr     eax, 0Eh
0x18002da38  shr     ecx, 4
0x18002da3b  and     eax, 3
0x18002da3e  and     ecx, 3
0x18002da41  mov     [rbx+8], eax
0x18002da44  mov     [rbx], ecx
0x18002da46  mov     eax, edx
0x18002da48  mov     ecx, edx
0x18002da4a  shr     eax, 6
0x18002da4d  shr     ecx, 8
0x18002da50  and     eax, r9d
0x18002da53  and     cl, 3Fh
0x18002da56  shr     edx, 7
0x18002da59  and     edx, r9d
0x18002da5c  mov     [rbx+4], cl
0x18002da5f  mov     [rbx+10h], edx
0x18002da62  mov     [rbx+14h], eax
0x18002da65  jmp     loc_18002D9D5
0x18002da6a  cmp     eax, 117h
0x18002da6f  jnz     loc_18002D9D2
0x18002da75  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18002da79  mov     r9d, 1
0x18002da7f  shr     eax, 7
0x18002da82  and     eax, r9d
0x18002da85  mov     [rbx+10h], eax
0x18002da88  jmp     loc_18002D9D5
```
