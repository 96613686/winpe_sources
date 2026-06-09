# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18002c734`
- end: `0x18002c826`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `242`
- prototype: `__int64 __fastcall(__int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002cf1c`

## callees

- `0x18001e420`
- `0x18002c734`
- `0x18002d030`
- `0x180034010`

## string_xrefs

- `0x18002c77f`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3)
{
  BOOL v5; // edi
  FARPROC NtDllProcedureAddress; // rax
  unsigned int v7; // edx
  int v8; // eax
  unsigned int v9; // ecx
  __int64 v11; // [rsp+30h] [rbp-28h] BYREF
  __int64 v12; // [rsp+38h] [rbp-20h] BYREF
  int v13; // [rsp+40h] [rbp-18h]

  v11 = 0;
  v5 = a3 == 0;
  v12 = 0;
  v13 = 0;
  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( g_wil_details_pfnRtlQueryFeatureConfiguration
    || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration"),
        (g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress) != 0) )
  {
    v8 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v5, &v11, &v12);
    if ( v8 )
    {
      v7 = 0;
      if ( v8 != 279 )
        return v7;
      v9 = HIDWORD(v12);
      v7 = 1;
    }
    else
    {
      v9 = HIDWORD(v12);
      v7 = 1;
      *(_DWORD *)a1 = (HIDWORD(v12) >> 4) & 3;
      *(_BYTE *)(a1 + 4) = BYTE1(v9) & 0x3F;
      *(_DWORD *)(a1 + 12) = v13;
      *(_DWORD *)(a1 + 8) = (unsigned __int16)v9 >> 14;
      *(_DWORD *)(a1 + 20) = (v9 >> 6) & 1;
    }
    *(_DWORD *)(a1 + 16) = (v9 >> 7) & 1;
    return v7;
  }
  return 0;
}

```

## disassembly

```asm
0x18002c734  mov     r11, rsp
0x18002c737  mov     [r11+18h], rbx
0x18002c73b  mov     [r11+20h], rsi
0x18002c73f  push    rdi
0x18002c740  sub     rsp, 50h
0x18002c744  mov     rax, cs:__security_cookie
0x18002c74b  xor     rax, rsp
0x18002c74e  mov     [rsp+58h+var_10], rax
0x18002c753  xor     edi, edi
0x18002c755  mov     qword ptr [r11-28h], 0
0x18002c75d  test    r8d, r8d
0x18002c760  mov     esi, edx
0x18002c762  mov     rbx, rcx
0x18002c765  setz    dil
0x18002c769  xor     eax, eax
0x18002c76b  mov     [r11-20h], rax
0x18002c76f  mov     [rsp+58h+var_18], eax
0x18002c773  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18002c77a  test    rax, rax
0x18002c77d  jnz     short loc_18002C79B
0x18002c77f  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002c786  call    wil_details_GetNtDllProcedureAddress
0x18002c78b  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18002c792  test    rax, rax
0x18002c795  jnz     short loc_18002C79B
0x18002c797  xor     edx, edx
0x18002c799  jmp     short loc_18002C807
0x18002c79b  lea     r9, [rsp+58h+var_20]
0x18002c7a0  mov     edx, edi
0x18002c7a2  lea     r8, [rsp+58h+var_28]
0x18002c7a7  mov     ecx, esi
0x18002c7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7ae  test    eax, eax
0x18002c7b0  jnz     short loc_18002C7ED
0x18002c7b2  mov     ecx, [rsp+58h+var_1C]
0x18002c7b6  mov     edx, 1
0x18002c7bb  mov     eax, ecx
0x18002c7bd  shr     eax, 4
0x18002c7c0  and     eax, 3
0x18002c7c3  mov     [rbx], eax
0x18002c7c5  mov     eax, ecx
0x18002c7c7  shr     eax, 8
0x18002c7ca  and     al, 3Fh
0x18002c7cc  mov     [rbx+4], al
0x18002c7cf  mov     eax, [rsp+58h+var_18]
0x18002c7d3  mov     [rbx+0Ch], eax
0x18002c7d6  mov     eax, ecx
0x18002c7d8  shr     eax, 0Eh
0x18002c7db  and     eax, 3
0x18002c7de  mov     [rbx+8], eax
0x18002c7e1  mov     eax, ecx
0x18002c7e3  shr     eax, 6
0x18002c7e6  and     eax, edx
0x18002c7e8  mov     [rbx+14h], eax
0x18002c7eb  jmp     short loc_18002C7FF
0x18002c7ed  xor     edx, edx
0x18002c7ef  cmp     eax, 117h
0x18002c7f4  jnz     short loc_18002C807
0x18002c7f6  mov     ecx, [rsp+58h+var_1C]
0x18002c7fa  mov     edx, 1
0x18002c7ff  shr     ecx, 7
0x18002c802  and     ecx, edx
0x18002c804  mov     [rbx+10h], ecx
0x18002c807  mov     eax, edx
0x18002c809  mov     rcx, [rsp+58h+var_10]
0x18002c80e  xor     rcx, rsp; StackCookie
0x18002c811  call    __security_check_cookie
0x18002c816  mov     rbx, [rsp+58h+arg_10]
0x18002c81b  mov     rsi, [rsp+58h+arg_18]
0x18002c820  add     rsp, 50h
0x18002c824  pop     rdi
0x18002c825  retn
```
