# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18002f0c4`
- end: `0x18002f1ea`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002bbf8`

## callees

- `0x1800287d0`
- `0x18002e5fc`
- `0x18002f0c4`
- `0x180039010`

## string_xrefs

- `0x18002f110`: `RtlQueryFeatureConfiguration`

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
0x18002f0c4  mov     [rsp+arg_10], rbx
0x18002f0c9  push    rbp
0x18002f0ca  push    rsi
0x18002f0cb  push    rdi
0x18002f0cc  sub     rsp, 50h
0x18002f0d0  mov     rax, cs:__security_cookie
0x18002f0d7  xor     rax, rsp
0x18002f0da  mov     [rsp+68h+var_20], rax
0x18002f0df  xor     esi, esi
0x18002f0e1  mov     [rsp+68h+var_38], 0
0x18002f0ea  test    r8d, r8d
0x18002f0ed  mov     rdi, r9
0x18002f0f0  mov     ebp, edx
0x18002f0f2  mov     rbx, rcx
0x18002f0f5  setz    sil
0x18002f0f9  xor     eax, eax
0x18002f0fb  mov     [rsp+68h+var_30], rax
0x18002f100  mov     [rsp+68h+var_28], eax
0x18002f104  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18002f10b  test    rax, rax
0x18002f10e  jnz     short loc_18002F165
0x18002f110  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002f117  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002f11c  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18002f123  test    rax, rax
0x18002f126  jnz     short loc_18002F165
0x18002f128  mov     r8d, 0C0000139h
0x18002f12e  xor     r9d, r9d
0x18002f131  test    rdi, rdi
0x18002f134  jz      short loc_18002F144
0x18002f136  xor     ecx, ecx
0x18002f138  cmp     r8d, 80000022h
0x18002f13f  setnz   cl
0x18002f142  mov     [rdi], ecx
0x18002f144  mov     eax, r9d
0x18002f147  mov     rcx, [rsp+68h+var_20]
0x18002f14c  xor     rcx, rsp; StackCookie
0x18002f14f  call    __security_check_cookie
0x18002f154  mov     rbx, [rsp+68h+arg_10]
0x18002f15c  add     rsp, 50h
0x18002f160  pop     rdi
0x18002f161  pop     rsi
0x18002f162  pop     rbp
0x18002f163  retn
0x18002f165  lea     r9, [rsp+68h+var_30]
0x18002f16a  mov     edx, esi
0x18002f16c  lea     r8, [rsp+68h+var_38]
0x18002f171  mov     ecx, ebp
0x18002f173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f178  mov     r8d, eax
0x18002f17b  test    eax, eax
0x18002f17d  jnz     short loc_18002F1C7
0x18002f17f  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18002f183  lea     r9d, [r8+1]
0x18002f187  mov     eax, [rsp+68h+var_28]
0x18002f18b  mov     ecx, edx
0x18002f18d  mov     [rbx+0Ch], eax
0x18002f190  mov     eax, edx
0x18002f192  shr     eax, 0Eh
0x18002f195  shr     ecx, 4
0x18002f198  and     eax, 3
0x18002f19b  and     ecx, 3
0x18002f19e  mov     [rbx+8], eax
0x18002f1a1  mov     [rbx], ecx
0x18002f1a3  mov     eax, edx
0x18002f1a5  mov     ecx, edx
0x18002f1a7  shr     eax, 6
0x18002f1aa  shr     ecx, 8
0x18002f1ad  and     eax, r9d
0x18002f1b0  and     cl, 3Fh
0x18002f1b3  shr     edx, 7
0x18002f1b6  and     edx, r9d
0x18002f1b9  mov     [rbx+4], cl
0x18002f1bc  mov     [rbx+10h], edx
0x18002f1bf  mov     [rbx+14h], eax
0x18002f1c2  jmp     loc_18002F131
0x18002f1c7  cmp     eax, 117h
0x18002f1cc  jnz     loc_18002F12E
0x18002f1d2  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18002f1d6  mov     r9d, 1
0x18002f1dc  shr     eax, 7
0x18002f1df  and     eax, r9d
0x18002f1e2  mov     [rbx+10h], eax
0x18002f1e5  jmp     loc_18002F131
```
