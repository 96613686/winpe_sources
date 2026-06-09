# wil_details_GetCurrentFeatureEnabledState

- ea: `0x140012914`
- end: `0x140012b57`
- name: `wil_details_GetCurrentFeatureEnabledState`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1400127a8`

## callees

- `0x140001686`
- `0x14000169e`
- `0x1400127a8`
- `0x140012914`
- `0x14002e420`
- `0x14002f010`

## string_xrefs

- `0x140012988`: `ntdll.dll`
- `0x14001299b`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_details_GetCurrentFeatureEnabledState(__int64 a1, _DWORD *a2)
{
  unsigned int v2; // r14d
  unsigned __int8 v3; // al
  int v5; // edi
  BOOL v6; // ebx
  FARPROC RtlQueryFeatureConfiguration; // rax
  HMODULE ModuleHandleW_0; // rax
  int v9; // r9d
  int v10; // eax
  int v11; // r8d
  int v12; // r9d
  int v13; // edx
  int v14; // eax
  unsigned int v15; // ecx
  int v16; // r12d
  __int64 *v17; // rsi
  int v18; // r15d
  BOOL v19; // ebx
  __int64 v20; // rcx
  _DWORD *v21; // r9
  char v22; // al
  __int64 v24; // [rsp+30h] [rbp-40h] BYREF
  __int128 v25; // [rsp+38h] [rbp-38h]
  __int64 v26; // [rsp+48h] [rbp-28h]
  __int64 v27; // [rsp+50h] [rbp-20h] BYREF
  int v28; // [rsp+58h] [rbp-18h]

  v2 = *(_DWORD *)(a1 + 24);
  v3 = *(_BYTE *)(a1 + 28) - 2;
  v25 = 0;
  v5 = 1;
  *a2 = 1;
  v6 = v3 > 1u;
  v26 = 0;
  v24 = 0;
  v27 = 0;
  v28 = 0;
  RtlQueryFeatureConfiguration = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    ModuleHandleW_0 = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW_0 = GetModuleHandleW_0(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW_0;
    }
    RtlQueryFeatureConfiguration = GetProcAddress_0(ModuleHandleW_0, "RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)RtlQueryFeatureConfiguration;
    if ( !RtlQueryFeatureConfiguration )
    {
      v9 = 0;
      goto LABEL_6;
    }
  }
  v14 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))RtlQueryFeatureConfiguration)(v2, v6, &v24, &v27);
  if ( v14 )
  {
    v9 = 0;
    if ( v14 == 279 )
    {
      v9 = 1;
      v10 = v26;
      if ( (v27 & 0x8000000000LL) != 0 )
        v10 = 1;
      goto LABEL_7;
    }
LABEL_6:
    v10 = v26;
LABEL_7:
    v11 = v25;
    goto LABEL_8;
  }
  v9 = 1;
  HIDWORD(v26) = (BYTE4(v27) >> 6) & 1;
  v11 = (HIDWORD(v27) >> 4) & 3;
  v10 = BYTE4(v27) >> 7;
LABEL_8:
  v24 = 0;
  v12 = -v9;
  if ( ((unsigned __int8)v11 & (unsigned __int8)-(v12 != 0) & 3) != 0 )
  {
    v13 = 0;
    if ( v11 == 2 )
      v13 = 64;
  }
  else
  {
    v13 = *(_BYTE *)(a1 + 31) != 0 ? 0x40 : 0;
  }
  v15 = v13
      | (v10 != 0 ? 0x400 : 0)
      | (HIDWORD(v26) != 0 ? 0x800 : 0)
      | (((unsigned __int8)v11 & (unsigned __int8)-(v12 != 0) & 3) << 7);
  if ( (v13 & 0xC00
      | (v10 != 0 ? 0x400 : 0)
      | (HIDWORD(v26) != 0 ? 0x800 : 0)
      | (((unsigned __int8)v11 & (unsigned __int8)-(v12 != 0) & 3) << 7) & 0xC00) == 0xC00 )
  {
    v16 = 1;
  }
  else
  {
    v16 = 0;
    if ( (v13 & 0x40) == 0 )
    {
LABEL_38:
      v5 = 0;
      goto LABEL_39;
    }
  }
  v17 = *(__int64 **)(a1 + 32);
  v18 = v13
      | (v10 != 0 ? 0x400 : 0)
      | (HIDWORD(v26) != 0 ? 0x800 : 0)
      | (((unsigned __int8)v11 & (unsigned __int8)-(v12 != 0) & 3) << 7);
  v19 = 1;
  if ( v17 )
  {
    while ( 1 )
    {
      v20 = *v17;
      if ( !*v17 )
        break;
      if ( *(_BYTE *)(v20 + 30) || *(_BYTE *)(v20 + 29) )
      {
        if ( !*(_BYTE *)(v20 + 31) )
        {
          v19 = 0;
          break;
        }
        v19 = 1;
        ++v17;
      }
      else
      {
        v21 = *(_DWORD **)v20;
        v27 = 0;
        LODWORD(v27) = *v21;
        if ( (v27 & 2) != 0 )
          v22 = v27;
        else
          v22 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(v21, v27, v20);
        v19 = (v22 & 1) != 0;
        ++v17;
        if ( (v22 & 1) == 0 )
          break;
      }
    }
  }
  v15 = v18;
  if ( v16 && !v19 )
    v15 = v18 & 0xFFFFFBFF;
  if ( (v15 & 0x40) == 0 || !v19 )
    goto LABEL_38;
LABEL_39:
  LODWORD(v24) = v5 | v15 & 0xFFFFFFFE;
  return v24;
}

```

## disassembly

```asm
0x140012914  mov     [rsp-28h+arg_10], rbx
0x140012919  mov     [rsp-28h+arg_18], rsi
0x14001291e  push    rbp
0x14001291f  push    rdi
0x140012920  push    r12
0x140012922  push    r14
0x140012924  push    r15
0x140012926  mov     rbp, rsp
0x140012929  sub     rsp, 70h
0x14001292d  mov     rax, cs:__security_cookie
0x140012934  xor     rax, rsp
0x140012937  mov     [rbp+var_10], rax
0x14001293b  mov     al, [rcx+1Ch]
0x14001293e  xor     ebx, ebx
0x140012940  mov     r14d, [rcx+18h]
0x140012944  sub     al, 2
0x140012946  xorps   xmm0, xmm0
0x140012949  mov     rsi, rcx
0x14001294c  movups  [rbp+var_38], xmm0
0x140012950  lea     edi, [rbx+1]
0x140012953  cmp     al, dil
0x140012956  mov     [rdx], edi
0x140012958  setnbe  bl
0x14001295b  xor     eax, eax
0x14001295d  mov     [rbp+var_28], rax
0x140012961  mov     [rbp+var_40], rax
0x140012965  mov     [rbp+var_20], rax
0x140012969  mov     [rbp+var_18], eax
0x14001296c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x140012973  test    rax, rax
0x140012976  jnz     loc_140012A09
0x14001297c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x140012983  test    rax, rax
0x140012986  jnz     short loc_14001299B
0x140012988  lea     rcx, LibFileName; "ntdll.dll"
0x14001298f  call    GetModuleHandleW_0
0x140012994  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x14001299b  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1400129a2  mov     rcx, rax; hModule
0x1400129a5  call    GetProcAddress_0
0x1400129aa  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1400129b1  test    rax, rax
0x1400129b4  jnz     short loc_140012A09
0x1400129b6  xor     r9d, r9d
0x1400129b9  mov     eax, dword ptr [rbp+var_28]
0x1400129bc  mov     r8d, dword ptr [rbp+var_38]
0x1400129c0  neg     eax
0x1400129c2  mov     [rbp+var_40], 0
0x1400129ca  mov     eax, dword ptr [rbp+var_28+4]
0x1400129cd  mov     r14d, 40h ; '@'
0x1400129d3  sbb     ecx, ecx
0x1400129d5  and     ecx, 400h
0x1400129db  neg     eax
0x1400129dd  sbb     edx, edx
0x1400129df  and     edx, 800h
0x1400129e5  or      edx, ecx
0x1400129e7  neg     r9d
0x1400129ea  sbb     eax, eax
0x1400129ec  and     eax, r8d
0x1400129ef  and     eax, 3
0x1400129f2  mov     ecx, eax
0x1400129f4  shl     ecx, 7
0x1400129f7  or      ecx, edx
0x1400129f9  test    eax, eax
0x1400129fb  jnz     short loc_140012A66
0x1400129fd  mov     al, [rsi+1Fh]
0x140012a00  neg     al
0x140012a02  sbb     edx, edx
0x140012a04  and     edx, r14d
0x140012a07  jmp     short loc_140012A70
0x140012a09  lea     r9, [rbp+var_20]
0x140012a0d  mov     edx, ebx
0x140012a0f  lea     r8, [rbp+var_40]
0x140012a13  mov     ecx, r14d
0x140012a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012a1b  test    eax, eax
0x140012a1d  jnz     short loc_140012A46
0x140012a1f  mov     ecx, dword ptr [rbp+var_20+4]
0x140012a22  mov     r9d, edi
0x140012a25  movzx   eax, cl
0x140012a28  mov     r8d, ecx
0x140012a2b  shr     eax, 6
0x140012a2e  and     eax, edi
0x140012a30  shr     r8d, 4
0x140012a34  mov     dword ptr [rbp+var_28+4], eax
0x140012a37  and     r8d, 3
0x140012a3b  movzx   eax, cl
0x140012a3e  shr     eax, 7
0x140012a41  jmp     loc_1400129C0
0x140012a46  xor     r9d, r9d
0x140012a49  cmp     eax, 117h
0x140012a4e  jnz     loc_1400129B9
0x140012a54  test    byte ptr [rbp+var_20+4], 80h
0x140012a58  mov     r9d, edi
0x140012a5b  mov     eax, dword ptr [rbp+var_28]
0x140012a5e  cmovnz  eax, edi
0x140012a61  jmp     loc_1400129BC
0x140012a66  xor     edx, edx
0x140012a68  cmp     r8d, 2
0x140012a6c  cmovz   edx, r14d
0x140012a70  or      ecx, edx
0x140012a72  mov     edx, 0C00h
0x140012a77  mov     eax, ecx
0x140012a79  and     eax, edx
0x140012a7b  cmp     eax, edx
0x140012a7d  jnz     short loc_140012A84
0x140012a7f  mov     r12d, edi
0x140012a82  jmp     short loc_140012A92
0x140012a84  xor     r12d, r12d
0x140012a87  xor     ebx, ebx
0x140012a89  test    r14b, cl
0x140012a8c  jz      loc_140012B24
0x140012a92  mov     rsi, [rsi+20h]
0x140012a96  mov     r15d, ecx
0x140012a99  mov     ebx, edi
0x140012a9b  test    rsi, rsi
0x140012a9e  jz      short loc_140012B0B
0x140012aa0  mov     rcx, [rsi]
0x140012aa3  test    rcx, rcx
0x140012aa6  jz      short loc_140012B0B
0x140012aa8  cmp     byte ptr [rcx+1Eh], 0
0x140012aac  jnz     short loc_140012AF7
0x140012aae  cmp     byte ptr [rcx+1Dh], 0
0x140012ab2  jnz     short loc_140012AF7
0x140012ab4  mov     r9, [rcx]
0x140012ab7  mov     [rbp+var_20], 0
0x140012abf  mov     eax, [r9]
0x140012ac2  mov     dword ptr [rbp+var_20], eax
0x140012ac5  test    al, 2
0x140012ac7  jz      short loc_140012ACF
0x140012ac9  mov     rax, [rbp+var_20]
0x140012acd  jmp     short loc_140012ADE
0x140012acf  mov     rdx, [rbp+var_20]
0x140012ad3  mov     r8, rcx
0x140012ad6  mov     rcx, r9
0x140012ad9  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x140012ade  test    ebx, ebx
0x140012ae0  jz      short loc_140012AEB
0x140012ae2  test    dil, al
0x140012ae5  jz      short loc_140012AEB
0x140012ae7  mov     ebx, edi
0x140012ae9  jmp     short loc_140012AED
0x140012aeb  xor     ebx, ebx
0x140012aed  add     rsi, 8
0x140012af1  test    ebx, ebx
0x140012af3  jnz     short loc_140012AA0
0x140012af5  jmp     short loc_140012B0B
0x140012af7  test    ebx, ebx
0x140012af9  jz      short loc_140012B09
0x140012afb  cmp     byte ptr [rcx+1Fh], 0
0x140012aff  jz      short loc_140012B09
0x140012b01  mov     ebx, edi
0x140012b03  add     rsi, 8
0x140012b07  jmp     short loc_140012AA0
0x140012b09  xor     ebx, ebx
0x140012b0b  mov     ecx, r15d
0x140012b0e  test    r12d, r12d
0x140012b11  jz      short loc_140012B1B
0x140012b13  test    ebx, ebx
0x140012b15  jnz     short loc_140012B1B
0x140012b17  btr     ecx, 0Ah
0x140012b1b  test    r14b, cl
0x140012b1e  jz      short loc_140012B24
0x140012b20  test    ebx, ebx
0x140012b22  jnz     short loc_140012B26
0x140012b24  xor     edi, edi
0x140012b26  and     ecx, 0FFFFFFFEh
0x140012b29  or      ecx, edi
0x140012b2b  mov     dword ptr [rbp+var_40], ecx
0x140012b2e  mov     rax, [rbp+var_40]
0x140012b32  mov     rcx, [rbp+var_10]
0x140012b36  xor     rcx, rsp; StackCookie
0x140012b39  call    __security_check_cookie
0x140012b3e  lea     r11, [rsp+70h+var_s0]
0x140012b43  mov     rbx, [r11+40h]
0x140012b47  mov     rsi, [r11+48h]
0x140012b4b  mov     rsp, r11
0x140012b4e  pop     r15
0x140012b50  pop     r14
0x140012b52  pop     r12
0x140012b54  pop     rdi
0x140012b55  pop     rbp
0x140012b56  retn
```
