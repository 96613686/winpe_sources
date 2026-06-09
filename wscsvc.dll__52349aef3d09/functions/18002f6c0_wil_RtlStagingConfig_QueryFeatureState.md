# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18002f6c0`
- end: `0x18002f7e5`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002f698`

## callees

- `0x18002f4a0`
- `0x18002f6c0`
- `0x18003fc30`
- `0x180042010`

## string_xrefs

- `0x18002f70c`: `RtlQueryFeatureConfiguration`

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
0x18002f6c0  mov     [rsp+arg_10], rbx
0x18002f6c5  push    rbp
0x18002f6c6  push    rsi
0x18002f6c7  push    rdi
0x18002f6c8  sub     rsp, 50h
0x18002f6cc  mov     rax, cs:__security_cookie
0x18002f6d3  xor     rax, rsp
0x18002f6d6  mov     [rsp+68h+var_20], rax
0x18002f6db  xor     esi, esi
0x18002f6dd  mov     [rsp+68h+var_38], 0
0x18002f6e6  test    r8d, r8d
0x18002f6e9  mov     rdi, r9
0x18002f6ec  mov     ebp, edx
0x18002f6ee  mov     rbx, rcx
0x18002f6f1  setz    sil
0x18002f6f5  xor     eax, eax
0x18002f6f7  mov     [rsp+68h+var_30], rax
0x18002f6fc  mov     [rsp+68h+var_28], eax
0x18002f700  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18002f707  test    rax, rax
0x18002f70a  jnz     short loc_18002F760
0x18002f70c  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002f713  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002f718  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18002f71f  test    rax, rax
0x18002f722  jnz     short loc_18002F760
0x18002f724  mov     r8d, 0C0000139h
0x18002f72a  xor     r9d, r9d
0x18002f72d  test    rdi, rdi
0x18002f730  jz      short loc_18002F740
0x18002f732  xor     ecx, ecx
0x18002f734  cmp     r8d, 80000022h
0x18002f73b  setnz   cl
0x18002f73e  mov     [rdi], ecx
0x18002f740  mov     eax, r9d
0x18002f743  mov     rcx, [rsp+68h+var_20]
0x18002f748  xor     rcx, rsp; StackCookie
0x18002f74b  call    __security_check_cookie
0x18002f750  mov     rbx, [rsp+68h+arg_10]
0x18002f758  add     rsp, 50h
0x18002f75c  pop     rdi
0x18002f75d  pop     rsi
0x18002f75e  pop     rbp
0x18002f75f  retn
0x18002f760  lea     r9, [rsp+68h+var_30]
0x18002f765  mov     edx, esi
0x18002f767  lea     r8, [rsp+68h+var_38]
0x18002f76c  mov     ecx, ebp
0x18002f76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f773  mov     r8d, eax
0x18002f776  test    eax, eax
0x18002f778  jnz     short loc_18002F7C2
0x18002f77a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18002f77e  lea     r9d, [r8+1]
0x18002f782  mov     eax, [rsp+68h+var_28]
0x18002f786  mov     ecx, edx
0x18002f788  mov     [rbx+0Ch], eax
0x18002f78b  mov     eax, edx
0x18002f78d  shr     eax, 0Eh
0x18002f790  shr     ecx, 4
0x18002f793  and     eax, 3
0x18002f796  and     ecx, 3
0x18002f799  mov     [rbx+8], eax
0x18002f79c  mov     [rbx], ecx
0x18002f79e  mov     eax, edx
0x18002f7a0  mov     ecx, edx
0x18002f7a2  shr     eax, 6
0x18002f7a5  shr     ecx, 8
0x18002f7a8  and     eax, r9d
0x18002f7ab  and     cl, 3Fh
0x18002f7ae  shr     edx, 7
0x18002f7b1  and     edx, r9d
0x18002f7b4  mov     [rbx+4], cl
0x18002f7b7  mov     [rbx+10h], edx
0x18002f7ba  mov     [rbx+14h], eax
0x18002f7bd  jmp     loc_18002F72D
0x18002f7c2  cmp     eax, 117h
0x18002f7c7  jnz     loc_18002F72A
0x18002f7cd  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18002f7d1  mov     r9d, 1
0x18002f7d7  shr     eax, 7
0x18002f7da  and     eax, r9d
0x18002f7dd  mov     [rbx+10h], eax
0x18002f7e0  jmp     loc_18002F72D
```
