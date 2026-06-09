# wil_QueryFeatureState

- ea: `0x180004a48`
- end: `0x180004b8a`
- name: `wil_QueryFeatureState`
- size: `322`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800027a0`
- `0x180027074`

## callees

- `0x180004a48`
- `0x180004b90`
- `0x180008320`
- `0x180029010`

## string_xrefs

- `0x180004aba`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_QueryFeatureState(__int64 a1, unsigned int a2, int a3, __int64 a4, _DWORD *a5, _DWORD *a6)
{
  unsigned int v8; // ebx
  BOOL v9; // ebp
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v11; // r8d
  int v13; // eax
  unsigned int v14; // edx
  unsigned int v15; // ecx
  __int64 v16; // [rsp+30h] [rbp-38h] BYREF
  __int64 v17; // [rsp+38h] [rbp-30h] BYREF
  int v18; // [rsp+40h] [rbp-28h]

  if ( a5 )
    *a5 = 0;
  v16 = 0;
  v8 = 1;
  *a6 = 1;
  v9 = a3 == 0;
  v17 = 0;
  v18 = 0;
  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress;
    if ( !NtDllProcedureAddress )
    {
      v11 = -1073741511;
LABEL_6:
      v8 = 0;
      goto LABEL_7;
    }
  }
  v13 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v9, &v16, &v17);
  v11 = v13;
  if ( v13 )
  {
    if ( v13 != 279 )
      goto LABEL_6;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v17) >> 7) & 1;
  }
  else
  {
    v14 = HIDWORD(v17);
    v15 = HIDWORD(v17);
    *(_DWORD *)(a1 + 12) = v18;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v15 >> 14;
    *(_DWORD *)a1 = (v15 >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v14) & 0x3F;
    *(_DWORD *)(a1 + 16) = (v14 >> 7) & 1;
    *(_DWORD *)(a1 + 20) = (v14 >> 6) & 1;
  }
LABEL_7:
  if ( a5 )
    *a5 = v11 != -2147483614;
  return v8;
}

```

## disassembly

```asm
0x180004a48  mov     [rsp+arg_10], rbx
0x180004a4d  mov     [rsp+arg_18], rbp
0x180004a52  push    rsi
0x180004a53  push    rdi
0x180004a54  push    r14
0x180004a56  sub     rsp, 50h
0x180004a5a  mov     rax, cs:__security_cookie
0x180004a61  xor     rax, rsp
0x180004a64  mov     [rsp+68h+var_20], rax
0x180004a69  mov     rdi, [rsp+68h+arg_20]
0x180004a71  mov     r14d, edx
0x180004a74  mov     rax, [rsp+68h+arg_28]
0x180004a7c  mov     rsi, rcx
0x180004a7f  test    rdi, rdi
0x180004a82  jz      short loc_180004A8A
0x180004a84  mov     dword ptr [rdi], 0
0x180004a8a  xor     ebp, ebp
0x180004a8c  mov     [rsp+68h+var_38], 0
0x180004a95  test    r8d, r8d
0x180004a98  mov     ebx, 1
0x180004a9d  mov     [rax], ebx
0x180004a9f  setz    bpl
0x180004aa3  xor     eax, eax
0x180004aa5  mov     [rsp+68h+var_30], rax
0x180004aaa  mov     [rsp+68h+var_28], eax
0x180004aae  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180004ab5  test    rax, rax
0x180004ab8  jnz     short loc_180004B11
0x180004aba  lea     rcx, ProcName; "RtlQueryFeatureConfiguration"
0x180004ac1  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180004ac6  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180004acd  test    rax, rax
0x180004ad0  jnz     short loc_180004B11
0x180004ad2  mov     r8d, 0C0000139h
0x180004ad8  xor     ebx, ebx
0x180004ada  test    rdi, rdi
0x180004add  jz      short loc_180004AED
0x180004adf  xor     ecx, ecx
0x180004ae1  cmp     r8d, 80000022h
0x180004ae8  setnz   cl
0x180004aeb  mov     [rdi], ecx
0x180004aed  mov     eax, ebx
0x180004aef  mov     rcx, [rsp+68h+var_20]
0x180004af4  xor     rcx, rsp; StackCookie
0x180004af7  call    __security_check_cookie
0x180004afc  lea     r11, [rsp+68h+var_18]
0x180004b01  mov     rbx, [r11+30h]
0x180004b05  mov     rbp, [r11+38h]
0x180004b09  mov     rsp, r11
0x180004b0c  pop     r14
0x180004b0e  pop     rdi
0x180004b0f  pop     rsi
0x180004b10  retn
0x180004b11  lea     r9, [rsp+68h+var_30]
0x180004b16  mov     edx, ebp
0x180004b18  lea     r8, [rsp+68h+var_38]
0x180004b1d  mov     ecx, r14d
0x180004b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b25  mov     r8d, eax
0x180004b28  test    eax, eax
0x180004b2a  jnz     short loc_180004B6E
0x180004b2c  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180004b30  mov     ecx, edx
0x180004b32  mov     eax, [rsp+68h+var_28]
0x180004b36  mov     [rsi+0Ch], eax
0x180004b39  mov     eax, edx
0x180004b3b  shr     eax, 0Eh
0x180004b3e  shr     ecx, 4
0x180004b41  and     eax, 3
0x180004b44  and     ecx, 3
0x180004b47  mov     [rsi+8], eax
0x180004b4a  mov     [rsi], ecx
0x180004b4c  mov     eax, edx
0x180004b4e  mov     ecx, edx
0x180004b50  shr     eax, 6
0x180004b53  shr     ecx, 8
0x180004b56  and     eax, ebx
0x180004b58  and     cl, 3Fh
0x180004b5b  shr     edx, 7
0x180004b5e  and     edx, ebx
0x180004b60  mov     [rsi+4], cl
0x180004b63  mov     [rsi+10h], edx
0x180004b66  mov     [rsi+14h], eax
0x180004b69  jmp     loc_180004ADA
0x180004b6e  cmp     eax, 117h
0x180004b73  jnz     loc_180004AD8
0x180004b79  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180004b7d  shr     eax, 7
0x180004b80  and     eax, ebx
0x180004b82  mov     [rsi+10h], eax
0x180004b85  jmp     loc_180004ADA
```
