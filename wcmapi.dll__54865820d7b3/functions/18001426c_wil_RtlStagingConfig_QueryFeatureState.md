# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18001426c`
- end: `0x180014392`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000dbec`

## callees

- `0x180008a90`
- `0x18000aac8`
- `0x18001426c`
- `0x18001e010`

## string_xrefs

- `0x1800142b8`: `RtlQueryFeatureConfiguration`

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
  int v16; // [rsp+38h] [rbp-30h]
  __int64 v17; // [rsp+40h] [rbp-28h] BYREF

  v17 = 0;
  v7 = a3 == 0;
  v15 = 0;
  v16 = 0;
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
  v12 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v7, &v17, &v15);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 != 279 )
      goto LABEL_4;
    v10 = 1;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v15) >> 7) & 1;
  }
  else
  {
    v13 = HIDWORD(v15);
    v10 = 1;
    v14 = HIDWORD(v15);
    *(_DWORD *)(a1 + 12) = v16;
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
0x18001426c  mov     [rsp+arg_10], rbx
0x180014271  push    rbp
0x180014272  push    rsi
0x180014273  push    rdi
0x180014274  sub     rsp, 50h
0x180014278  mov     rax, cs:__security_cookie
0x18001427f  xor     rax, rsp
0x180014282  mov     [rsp+68h+var_20], rax
0x180014287  xor     esi, esi
0x180014289  mov     [rsp+68h+var_28], 0
0x180014292  test    r8d, r8d
0x180014295  mov     rdi, r9
0x180014298  mov     ebp, edx
0x18001429a  mov     rbx, rcx
0x18001429d  setz    sil
0x1800142a1  xor     eax, eax
0x1800142a3  mov     [rsp+68h+var_38], rax
0x1800142a8  mov     [rsp+68h+var_30], eax
0x1800142ac  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800142b3  test    rax, rax
0x1800142b6  jnz     short loc_18001430D
0x1800142b8  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1800142bf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800142c4  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800142cb  test    rax, rax
0x1800142ce  jnz     short loc_18001430D
0x1800142d0  mov     r8d, 0C0000139h
0x1800142d6  xor     r9d, r9d
0x1800142d9  test    rdi, rdi
0x1800142dc  jz      short loc_1800142EC
0x1800142de  xor     ecx, ecx
0x1800142e0  cmp     r8d, 80000022h
0x1800142e7  setnz   cl
0x1800142ea  mov     [rdi], ecx
0x1800142ec  mov     eax, r9d
0x1800142ef  mov     rcx, [rsp+68h+var_20]
0x1800142f4  xor     rcx, rsp; StackCookie
0x1800142f7  call    __security_check_cookie
0x1800142fc  mov     rbx, [rsp+68h+arg_10]
0x180014304  add     rsp, 50h
0x180014308  pop     rdi
0x180014309  pop     rsi
0x18001430a  pop     rbp
0x18001430b  retn
0x18001430d  lea     r9, [rsp+68h+var_38]
0x180014312  mov     edx, esi
0x180014314  lea     r8, [rsp+68h+var_28]
0x180014319  mov     ecx, ebp
0x18001431b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014320  mov     r8d, eax
0x180014323  test    eax, eax
0x180014325  jnz     short loc_18001436F
0x180014327  mov     edx, dword ptr [rsp+68h+var_38+4]
0x18001432b  lea     r9d, [r8+1]
0x18001432f  mov     eax, [rsp+68h+var_30]
0x180014333  mov     ecx, edx
0x180014335  mov     [rbx+0Ch], eax
0x180014338  mov     eax, edx
0x18001433a  shr     eax, 0Eh
0x18001433d  shr     ecx, 4
0x180014340  and     eax, 3
0x180014343  and     ecx, 3
0x180014346  mov     [rbx+8], eax
0x180014349  mov     [rbx], ecx
0x18001434b  mov     eax, edx
0x18001434d  mov     ecx, edx
0x18001434f  shr     eax, 6
0x180014352  shr     ecx, 8
0x180014355  and     eax, r9d
0x180014358  and     cl, 3Fh
0x18001435b  shr     edx, 7
0x18001435e  and     edx, r9d
0x180014361  mov     [rbx+4], cl
0x180014364  mov     [rbx+10h], edx
0x180014367  mov     [rbx+14h], eax
0x18001436a  jmp     loc_1800142D9
0x18001436f  cmp     eax, 117h
0x180014374  jnz     loc_1800142D6
0x18001437a  mov     eax, dword ptr [rsp+68h+var_38+4]
0x18001437e  mov     r9d, 1
0x180014384  shr     eax, 7
0x180014387  and     eax, r9d
0x18001438a  mov     [rbx+10h], eax
0x18001438d  jmp     loc_1800142D9
```
