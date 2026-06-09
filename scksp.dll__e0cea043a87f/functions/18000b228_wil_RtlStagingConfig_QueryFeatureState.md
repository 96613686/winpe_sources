# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000b228`
- end: `0x18000b34d`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b9cc`
- `0x18000ec7c`

## callees

- `0x18000b228`
- `0x18000bae4`
- `0x18003c240`
- `0x18003d010`

## string_xrefs

- `0x18000b274`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  BOOL v7; // esi
  __int64 (__fastcall *NtDllProcedureAddress)(_QWORD, BOOL, __int64 *, __int64 *); // rax
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
  NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress;
    if ( !NtDllProcedureAddress )
    {
      v9 = -1073741511;
LABEL_4:
      v10 = 0;
      goto LABEL_5;
    }
  }
  v12 = NtDllProcedureAddress(a2, v7, &v15, &v16);
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
0x18000b228  mov     [rsp+arg_10], rbx
0x18000b22d  push    rbp
0x18000b22e  push    rsi
0x18000b22f  push    rdi
0x18000b230  sub     rsp, 50h
0x18000b234  mov     rax, cs:__security_cookie
0x18000b23b  xor     rax, rsp
0x18000b23e  mov     [rsp+68h+var_20], rax
0x18000b243  xor     esi, esi
0x18000b245  mov     [rsp+68h+var_38], 0
0x18000b24e  test    r8d, r8d
0x18000b251  mov     rdi, r9
0x18000b254  mov     ebp, edx
0x18000b256  mov     rbx, rcx
0x18000b259  setz    sil
0x18000b25d  xor     eax, eax
0x18000b25f  mov     [rsp+68h+var_30], rax
0x18000b264  mov     [rsp+68h+var_28], eax
0x18000b268  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000b26f  test    rax, rax
0x18000b272  jnz     short loc_18000B2C8
0x18000b274  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000b27b  call    wil_details_GetNtDllProcedureAddress
0x18000b280  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000b287  test    rax, rax
0x18000b28a  jnz     short loc_18000B2C8
0x18000b28c  mov     r8d, 0C0000139h
0x18000b292  xor     r9d, r9d
0x18000b295  test    rdi, rdi
0x18000b298  jz      short loc_18000B2A8
0x18000b29a  xor     ecx, ecx
0x18000b29c  cmp     r8d, 80000022h
0x18000b2a3  setnz   cl
0x18000b2a6  mov     [rdi], ecx
0x18000b2a8  mov     eax, r9d
0x18000b2ab  mov     rcx, [rsp+68h+var_20]
0x18000b2b0  xor     rcx, rsp; StackCookie
0x18000b2b3  call    __security_check_cookie
0x18000b2b8  mov     rbx, [rsp+68h+arg_10]
0x18000b2c0  add     rsp, 50h
0x18000b2c4  pop     rdi
0x18000b2c5  pop     rsi
0x18000b2c6  pop     rbp
0x18000b2c7  retn
0x18000b2c8  lea     r9, [rsp+68h+var_30]
0x18000b2cd  mov     edx, esi
0x18000b2cf  lea     r8, [rsp+68h+var_38]
0x18000b2d4  mov     ecx, ebp
0x18000b2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2db  mov     r8d, eax
0x18000b2de  test    eax, eax
0x18000b2e0  jnz     short loc_18000B32A
0x18000b2e2  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000b2e6  lea     r9d, [r8+1]
0x18000b2ea  mov     eax, [rsp+68h+var_28]
0x18000b2ee  mov     ecx, edx
0x18000b2f0  mov     [rbx+0Ch], eax
0x18000b2f3  mov     eax, edx
0x18000b2f5  shr     eax, 0Eh
0x18000b2f8  shr     ecx, 4
0x18000b2fb  and     eax, 3
0x18000b2fe  and     ecx, 3
0x18000b301  mov     [rbx+8], eax
0x18000b304  mov     [rbx], ecx
0x18000b306  mov     eax, edx
0x18000b308  mov     ecx, edx
0x18000b30a  shr     eax, 6
0x18000b30d  shr     ecx, 8
0x18000b310  and     eax, r9d
0x18000b313  and     cl, 3Fh
0x18000b316  shr     edx, 7
0x18000b319  and     edx, r9d
0x18000b31c  mov     [rbx+4], cl
0x18000b31f  mov     [rbx+10h], edx
0x18000b322  mov     [rbx+14h], eax
0x18000b325  jmp     loc_18000B295
0x18000b32a  cmp     eax, 117h
0x18000b32f  jnz     loc_18000B292
0x18000b335  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000b339  mov     r9d, 1
0x18000b33f  shr     eax, 7
0x18000b342  and     eax, r9d
0x18000b345  mov     [rbx+10h], eax
0x18000b348  jmp     loc_18000B295
```
