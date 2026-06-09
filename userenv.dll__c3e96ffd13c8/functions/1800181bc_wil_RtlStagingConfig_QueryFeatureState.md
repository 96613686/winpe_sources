# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1800181bc`
- end: `0x1800182e1`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800156e4`

## callees

- `0x18000d9b0`
- `0x18000fe50`
- `0x1800181bc`
- `0x18001c010`

## string_xrefs

- `0x180018208`: `RtlQueryFeatureConfiguration`

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
0x1800181bc  mov     [rsp+arg_10], rbx
0x1800181c1  push    rbp
0x1800181c2  push    rsi
0x1800181c3  push    rdi
0x1800181c4  sub     rsp, 50h
0x1800181c8  mov     rax, cs:__security_cookie
0x1800181cf  xor     rax, rsp
0x1800181d2  mov     [rsp+68h+var_20], rax
0x1800181d7  xor     esi, esi
0x1800181d9  mov     [rsp+68h+var_38], 0
0x1800181e2  test    r8d, r8d
0x1800181e5  mov     rdi, r9
0x1800181e8  mov     ebp, edx
0x1800181ea  mov     rbx, rcx
0x1800181ed  setz    sil
0x1800181f1  xor     eax, eax
0x1800181f3  mov     [rsp+68h+var_30], rax
0x1800181f8  mov     [rsp+68h+var_28], eax
0x1800181fc  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180018203  test    rax, rax
0x180018206  jnz     short loc_18001825C
0x180018208  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001820f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180018214  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001821b  test    rax, rax
0x18001821e  jnz     short loc_18001825C
0x180018220  mov     r8d, 0C0000139h
0x180018226  xor     r9d, r9d
0x180018229  test    rdi, rdi
0x18001822c  jz      short loc_18001823C
0x18001822e  xor     ecx, ecx
0x180018230  cmp     r8d, 80000022h
0x180018237  setnz   cl
0x18001823a  mov     [rdi], ecx
0x18001823c  mov     eax, r9d
0x18001823f  mov     rcx, [rsp+68h+var_20]
0x180018244  xor     rcx, rsp; StackCookie
0x180018247  call    __security_check_cookie
0x18001824c  mov     rbx, [rsp+68h+arg_10]
0x180018254  add     rsp, 50h
0x180018258  pop     rdi
0x180018259  pop     rsi
0x18001825a  pop     rbp
0x18001825b  retn
0x18001825c  lea     r9, [rsp+68h+var_30]
0x180018261  mov     edx, esi
0x180018263  lea     r8, [rsp+68h+var_38]
0x180018268  mov     ecx, ebp
0x18001826a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001826f  mov     r8d, eax
0x180018272  test    eax, eax
0x180018274  jnz     short loc_1800182BE
0x180018276  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18001827a  lea     r9d, [r8+1]
0x18001827e  mov     eax, [rsp+68h+var_28]
0x180018282  mov     ecx, edx
0x180018284  mov     [rbx+0Ch], eax
0x180018287  mov     eax, edx
0x180018289  shr     eax, 0Eh
0x18001828c  shr     ecx, 4
0x18001828f  and     eax, 3
0x180018292  and     ecx, 3
0x180018295  mov     [rbx+8], eax
0x180018298  mov     [rbx], ecx
0x18001829a  mov     eax, edx
0x18001829c  mov     ecx, edx
0x18001829e  shr     eax, 6
0x1800182a1  shr     ecx, 8
0x1800182a4  and     eax, r9d
0x1800182a7  and     cl, 3Fh
0x1800182aa  shr     edx, 7
0x1800182ad  and     edx, r9d
0x1800182b0  mov     [rbx+4], cl
0x1800182b3  mov     [rbx+10h], edx
0x1800182b6  mov     [rbx+14h], eax
0x1800182b9  jmp     loc_180018229
0x1800182be  cmp     eax, 117h
0x1800182c3  jnz     loc_180018226
0x1800182c9  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800182cd  mov     r9d, 1
0x1800182d3  shr     eax, 7
0x1800182d6  and     eax, r9d
0x1800182d9  mov     [rbx+10h], eax
0x1800182dc  jmp     loc_180018229
```
