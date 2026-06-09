# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18002c5a0`
- end: `0x18002c6c5`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18001d8f0`

## callees

- `0x18001ff00`
- `0x180022d58`
- `0x18002c5a0`
- `0x180032010`

## string_xrefs

- `0x18002c5ec`: `RtlQueryFeatureConfiguration`

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
0x18002c5a0  mov     [rsp+arg_10], rbx
0x18002c5a5  push    rbp
0x18002c5a6  push    rsi
0x18002c5a7  push    rdi
0x18002c5a8  sub     rsp, 50h
0x18002c5ac  mov     rax, cs:__security_cookie
0x18002c5b3  xor     rax, rsp
0x18002c5b6  mov     [rsp+68h+var_20], rax
0x18002c5bb  xor     esi, esi
0x18002c5bd  mov     [rsp+68h+var_38], 0
0x18002c5c6  test    r8d, r8d
0x18002c5c9  mov     rdi, r9
0x18002c5cc  mov     ebp, edx
0x18002c5ce  mov     rbx, rcx
0x18002c5d1  setz    sil
0x18002c5d5  xor     eax, eax
0x18002c5d7  mov     [rsp+68h+var_30], rax
0x18002c5dc  mov     [rsp+68h+var_28], eax
0x18002c5e0  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18002c5e7  test    rax, rax
0x18002c5ea  jnz     short loc_18002C640
0x18002c5ec  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002c5f3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002c5f8  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18002c5ff  test    rax, rax
0x18002c602  jnz     short loc_18002C640
0x18002c604  mov     r8d, 0C0000139h
0x18002c60a  xor     r9d, r9d
0x18002c60d  test    rdi, rdi
0x18002c610  jz      short loc_18002C620
0x18002c612  xor     ecx, ecx
0x18002c614  cmp     r8d, 80000022h
0x18002c61b  setnz   cl
0x18002c61e  mov     [rdi], ecx
0x18002c620  mov     eax, r9d
0x18002c623  mov     rcx, [rsp+68h+var_20]
0x18002c628  xor     rcx, rsp; StackCookie
0x18002c62b  call    __security_check_cookie
0x18002c630  mov     rbx, [rsp+68h+arg_10]
0x18002c638  add     rsp, 50h
0x18002c63c  pop     rdi
0x18002c63d  pop     rsi
0x18002c63e  pop     rbp
0x18002c63f  retn
0x18002c640  lea     r9, [rsp+68h+var_30]
0x18002c645  mov     edx, esi
0x18002c647  lea     r8, [rsp+68h+var_38]
0x18002c64c  mov     ecx, ebp
0x18002c64e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c653  mov     r8d, eax
0x18002c656  test    eax, eax
0x18002c658  jnz     short loc_18002C6A2
0x18002c65a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18002c65e  lea     r9d, [r8+1]
0x18002c662  mov     eax, [rsp+68h+var_28]
0x18002c666  mov     ecx, edx
0x18002c668  mov     [rbx+0Ch], eax
0x18002c66b  mov     eax, edx
0x18002c66d  shr     eax, 0Eh
0x18002c670  shr     ecx, 4
0x18002c673  and     eax, 3
0x18002c676  and     ecx, 3
0x18002c679  mov     [rbx+8], eax
0x18002c67c  mov     [rbx], ecx
0x18002c67e  mov     eax, edx
0x18002c680  mov     ecx, edx
0x18002c682  shr     eax, 6
0x18002c685  shr     ecx, 8
0x18002c688  and     eax, r9d
0x18002c68b  and     cl, 3Fh
0x18002c68e  shr     edx, 7
0x18002c691  and     edx, r9d
0x18002c694  mov     [rbx+4], cl
0x18002c697  mov     [rbx+10h], edx
0x18002c69a  mov     [rbx+14h], eax
0x18002c69d  jmp     loc_18002C60D
0x18002c6a2  cmp     eax, 117h
0x18002c6a7  jnz     loc_18002C60A
0x18002c6ad  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18002c6b1  mov     r9d, 1
0x18002c6b7  shr     eax, 7
0x18002c6ba  and     eax, r9d
0x18002c6bd  mov     [rbx+10h], eax
0x18002c6c0  jmp     loc_18002C60D
```
