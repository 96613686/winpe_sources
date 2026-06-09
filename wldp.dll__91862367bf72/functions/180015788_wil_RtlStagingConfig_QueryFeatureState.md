# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180015788`
- end: `0x1800158ad`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180015630`

## callees

- `0x18000363c`
- `0x180015788`
- `0x180021ec0`
- `0x180042010`

## string_xrefs

- `0x1800157d4`: `RtlQueryFeatureConfiguration`

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
0x180015788  mov     [rsp+arg_10], rbx
0x18001578d  push    rbp
0x18001578e  push    rsi
0x18001578f  push    rdi
0x180015790  sub     rsp, 50h
0x180015794  mov     rax, cs:__security_cookie
0x18001579b  xor     rax, rsp
0x18001579e  mov     [rsp+68h+var_20], rax
0x1800157a3  xor     esi, esi
0x1800157a5  mov     [rsp+68h+var_38], 0
0x1800157ae  test    r8d, r8d
0x1800157b1  mov     rdi, r9
0x1800157b4  mov     ebp, edx
0x1800157b6  mov     rbx, rcx
0x1800157b9  setz    sil
0x1800157bd  xor     eax, eax
0x1800157bf  mov     [rsp+68h+var_30], rax
0x1800157c4  mov     [rsp+68h+var_28], eax
0x1800157c8  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800157cf  test    rax, rax
0x1800157d2  jnz     short loc_180015828
0x1800157d4  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1800157db  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800157e0  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800157e7  test    rax, rax
0x1800157ea  jnz     short loc_180015828
0x1800157ec  mov     r8d, 0C0000139h
0x1800157f2  xor     r9d, r9d
0x1800157f5  test    rdi, rdi
0x1800157f8  jz      short loc_180015808
0x1800157fa  xor     ecx, ecx
0x1800157fc  cmp     r8d, 80000022h
0x180015803  setnz   cl
0x180015806  mov     [rdi], ecx
0x180015808  mov     eax, r9d
0x18001580b  mov     rcx, [rsp+68h+var_20]
0x180015810  xor     rcx, rsp; StackCookie
0x180015813  call    __security_check_cookie
0x180015818  mov     rbx, [rsp+68h+arg_10]
0x180015820  add     rsp, 50h
0x180015824  pop     rdi
0x180015825  pop     rsi
0x180015826  pop     rbp
0x180015827  retn
0x180015828  lea     r9, [rsp+68h+var_30]
0x18001582d  mov     edx, esi
0x18001582f  lea     r8, [rsp+68h+var_38]
0x180015834  mov     ecx, ebp
0x180015836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001583b  mov     r8d, eax
0x18001583e  test    eax, eax
0x180015840  jnz     short loc_18001588A
0x180015842  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180015846  lea     r9d, [r8+1]
0x18001584a  mov     eax, [rsp+68h+var_28]
0x18001584e  mov     ecx, edx
0x180015850  mov     [rbx+0Ch], eax
0x180015853  mov     eax, edx
0x180015855  shr     eax, 0Eh
0x180015858  shr     ecx, 4
0x18001585b  and     eax, 3
0x18001585e  and     ecx, 3
0x180015861  mov     [rbx+8], eax
0x180015864  mov     [rbx], ecx
0x180015866  mov     eax, edx
0x180015868  mov     ecx, edx
0x18001586a  shr     eax, 6
0x18001586d  shr     ecx, 8
0x180015870  and     eax, r9d
0x180015873  and     cl, 3Fh
0x180015876  shr     edx, 7
0x180015879  and     edx, r9d
0x18001587c  mov     [rbx+4], cl
0x18001587f  mov     [rbx+10h], edx
0x180015882  mov     [rbx+14h], eax
0x180015885  jmp     loc_1800157F5
0x18001588a  cmp     eax, 117h
0x18001588f  jnz     loc_1800157F2
0x180015895  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180015899  mov     r9d, 1
0x18001589f  shr     eax, 7
0x1800158a2  and     eax, r9d
0x1800158a5  mov     [rbx+10h], eax
0x1800158a8  jmp     loc_1800157F5
```
