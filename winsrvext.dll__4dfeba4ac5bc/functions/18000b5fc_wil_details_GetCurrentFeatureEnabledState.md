# wil_details_GetCurrentFeatureEnabledState

- ea: `0x18000b5fc`
- end: `0x18000b82a`
- name: `wil_details_GetCurrentFeatureEnabledState`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b48c`

## callees

- `0x18000b48c`
- `0x18000b5fc`
- `0x1800138f0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b674`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b674`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b691`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b691`

## string_xrefs

- `0x18000b66d`: `ntdll.dll`
- `0x18000b687`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_details_GetCurrentFeatureEnabledState(__int64 a1, _DWORD *a2)
{
  unsigned int v2; // esi
  unsigned __int8 v3; // al
  BOOL v5; // ebx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v8; // r9d
  int v9; // eax
  int v10; // r8d
  int v11; // edx
  int v12; // eax
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // r9d
  int v16; // ebx
  __int64 *v17; // rdi
  __int64 v18; // rcx
  _DWORD *v19; // r9
  unsigned __int8 v20; // al
  BOOL v21; // ecx
  unsigned int v22; // eax
  unsigned int v23; // ebx
  __int64 v25; // [rsp+30h] [rbp-40h] BYREF
  __int128 v26; // [rsp+38h] [rbp-38h]
  __int64 v27; // [rsp+48h] [rbp-28h]
  __int64 v28; // [rsp+50h] [rbp-20h] BYREF
  int v29; // [rsp+58h] [rbp-18h]

  v2 = *(_DWORD *)(a1 + 24);
  v3 = *(_BYTE *)(a1 + 28) - 2;
  v26 = 0;
  *a2 = 1;
  v5 = v3 > 1u;
  v27 = 0;
  v25 = 0;
  v28 = 0;
  v29 = 0;
  ProcAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      v8 = 0;
      goto LABEL_6;
    }
  }
  v14 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(v2, v5, &v25, &v28);
  if ( v14 )
  {
    v8 = 0;
    if ( v14 == 279 )
    {
      v8 = 1;
      v9 = v27;
      if ( (v28 & 0x8000000000LL) != 0 )
        v9 = 1;
      goto LABEL_7;
    }
LABEL_6:
    v9 = v27;
LABEL_7:
    v10 = v26;
    goto LABEL_8;
  }
  v8 = 1;
  HIDWORD(v27) = (BYTE4(v28) >> 6) & 1;
  v10 = (HIDWORD(v28) >> 4) & 3;
  v9 = BYTE4(v28) >> 7;
LABEL_8:
  v28 = 0;
  v11 = (v9 != 0 ? 0x400 : 0) | (HIDWORD(v27) != 0 ? 0x800 : 0);
  v12 = (unsigned __int8)v10 & (unsigned __int8)-(v8 != 0) & 3;
  if ( v12 )
  {
    v13 = 0;
    if ( v10 == 2 )
      v13 = 64;
  }
  else
  {
    v13 = *(_BYTE *)(a1 + 31) != 0 ? 0x40 : 0;
  }
  v15 = v13 | v11 | (v12 << 7);
  v16 = v15 | (v15 >> 6) & 1;
  LODWORD(v28) = v16;
  if ( ((v15 >> 6) & 1) != 0 )
  {
    v17 = *(__int64 **)(a1 + 32);
    if ( v17 )
    {
      for ( ; (v16 & 1) != 0; LODWORD(v28) = v16 )
      {
        v18 = *v17;
        if ( !*v17 )
          break;
        if ( *(_BYTE *)(v18 + 30) || *(_BYTE *)(v18 + 29) )
        {
          v22 = (v16 & 1) != 0 && *(_BYTE *)(v18 + 31);
          v23 = v16 & 0xFFFFFFFE;
        }
        else
        {
          v19 = *(_DWORD **)v18;
          v25 = 0;
          LODWORD(v25) = *v19;
          v20 = (v25 & 2) != 0 ? v25 : wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(v19, v25, v18);
          v21 = ((unsigned __int8)v16 & v20 & 1) != 0;
          v22 = v16 & 0xFFFFFFFE;
          v23 = v21;
        }
        v16 = v22 | v23;
        ++v17;
      }
    }
  }
  return v28;
}

```

## disassembly

```asm
0x18000b5fc  mov     [rsp-18h+arg_10], rbx
0x18000b601  mov     [rsp-18h+arg_18], rsi
0x18000b606  push    rbp
0x18000b607  push    rdi
0x18000b608  push    r15
0x18000b60a  mov     rbp, rsp
0x18000b60d  sub     rsp, 70h
0x18000b611  mov     rax, cs:__security_cookie
0x18000b618  xor     rax, rsp
0x18000b61b  mov     [rbp+var_10], rax
0x18000b61f  mov     al, [rcx+1Ch]
0x18000b622  xor     ebx, ebx
0x18000b624  mov     esi, [rcx+18h]
0x18000b627  sub     al, 2
0x18000b629  xorps   xmm0, xmm0
0x18000b62c  mov     rdi, rcx
0x18000b62f  movups  [rbp+var_38], xmm0
0x18000b633  lea     r15d, [rbx+1]
0x18000b637  cmp     al, r15b
0x18000b63a  mov     [rdx], r15d
0x18000b63d  setnbe  bl
0x18000b640  xor     eax, eax
0x18000b642  mov     [rbp+var_28], rax
0x18000b646  mov     [rbp+var_40], rax
0x18000b64a  mov     [rbp+var_20], rax
0x18000b64e  mov     [rbp+var_18], eax
0x18000b651  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000b658  test    rax, rax
0x18000b65b  jnz     loc_18000B6F9
0x18000b661  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000b668  test    rax, rax
0x18000b66b  jnz     short loc_18000B687
0x18000b66d  lea     rcx, ModuleName; "ntdll.dll"
0x18000b674  call    cs:__imp_GetModuleHandleW
0x18000b67b  nop     dword ptr [rax+rax+00h]
0x18000b680  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000b687  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000b68e  mov     rcx, rax; hModule
0x18000b691  call    cs:__imp_GetProcAddress
0x18000b698  nop     dword ptr [rax+rax+00h]
0x18000b69d  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000b6a4  test    rax, rax
0x18000b6a7  jnz     short loc_18000B6F9
0x18000b6a9  xor     r9d, r9d
0x18000b6ac  mov     eax, dword ptr [rbp+var_28]
0x18000b6af  mov     r8d, dword ptr [rbp+var_38]
0x18000b6b3  neg     eax
0x18000b6b5  mov     [rbp+var_20], 0
0x18000b6bd  mov     eax, dword ptr [rbp+var_28+4]
0x18000b6c0  sbb     ecx, ecx
0x18000b6c2  and     ecx, 400h
0x18000b6c8  neg     eax
0x18000b6ca  sbb     edx, edx
0x18000b6cc  and     edx, 800h
0x18000b6d2  or      edx, ecx
0x18000b6d4  neg     r9d
0x18000b6d7  sbb     eax, eax
0x18000b6d9  and     eax, r8d
0x18000b6dc  and     eax, 3
0x18000b6df  mov     r9d, eax
0x18000b6e2  shl     r9d, 7
0x18000b6e6  or      r9d, edx
0x18000b6e9  test    eax, eax
0x18000b6eb  jnz     short loc_18000B754
0x18000b6ed  mov     al, [rdi+1Fh]
0x18000b6f0  neg     al
0x18000b6f2  sbb     ecx, ecx
0x18000b6f4  and     ecx, 40h
0x18000b6f7  jmp     short loc_18000B760
0x18000b6f9  lea     r9, [rbp+var_20]
0x18000b6fd  mov     edx, ebx
0x18000b6ff  lea     r8, [rbp+var_40]
0x18000b703  mov     ecx, esi
0x18000b705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b70a  test    eax, eax
0x18000b70c  jnz     short loc_18000B733
0x18000b70e  mov     ecx, dword ptr [rbp+var_20+4]
0x18000b711  mov     r9d, r15d
0x18000b714  movzx   eax, cl
0x18000b717  mov     r8d, ecx
0x18000b71a  shr     eax, 6
0x18000b71d  and     eax, r15d
0x18000b720  shr     r8d, 4
0x18000b724  mov     dword ptr [rbp+var_28+4], eax
0x18000b727  and     r8d, 3
0x18000b72b  movzx   eax, cl
0x18000b72e  shr     eax, 7
0x18000b731  jmp     short loc_18000B6B3
0x18000b733  xor     r9d, r9d
0x18000b736  cmp     eax, 117h
0x18000b73b  jnz     loc_18000B6AC
0x18000b741  test    byte ptr [rbp+var_20+4], 80h
0x18000b745  mov     r9d, r15d
0x18000b748  mov     eax, dword ptr [rbp+var_28]
0x18000b74b  cmovnz  eax, r15d
0x18000b74f  jmp     loc_18000B6AF
0x18000b754  xor     ecx, ecx
0x18000b756  cmp     r8d, 2
0x18000b75a  lea     eax, [rcx+40h]
0x18000b75d  cmovz   ecx, eax
0x18000b760  or      r9d, ecx
0x18000b763  mov     eax, r9d
0x18000b766  shr     eax, 6
0x18000b769  and     eax, r15d
0x18000b76c  mov     ebx, eax
0x18000b76e  or      ebx, r9d
0x18000b771  mov     dword ptr [rbp+var_20], ebx
0x18000b774  test    eax, eax
0x18000b776  jz      loc_18000B804
0x18000b77c  mov     rdi, [rdi+20h]
0x18000b780  test    rdi, rdi
0x18000b783  jz      short loc_18000B804
0x18000b785  test    r15b, bl
0x18000b788  jz      short loc_18000B804
0x18000b78a  mov     esi, 0FFFFFFFEh
0x18000b78f  mov     rcx, [rdi]
0x18000b792  test    rcx, rcx
0x18000b795  jz      short loc_18000B804
0x18000b797  cmp     byte ptr [rcx+1Eh], 0
0x18000b79b  jnz     short loc_18000B7E2
0x18000b79d  cmp     byte ptr [rcx+1Dh], 0
0x18000b7a1  jnz     short loc_18000B7E2
0x18000b7a3  mov     r9, [rcx]
0x18000b7a6  mov     [rbp+var_40], 0
0x18000b7ae  mov     eax, [r9]
0x18000b7b1  mov     dword ptr [rbp+var_40], eax
0x18000b7b4  test    al, 2
0x18000b7b6  jz      short loc_18000B7BE
0x18000b7b8  mov     rax, [rbp+var_40]
0x18000b7bc  jmp     short loc_18000B7CD
0x18000b7be  mov     rdx, [rbp+var_40]
0x18000b7c2  mov     r8, rcx
0x18000b7c5  mov     rcx, r9
0x18000b7c8  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x18000b7cd  and     eax, ebx
0x18000b7cf  mov     ecx, 0
0x18000b7d4  test    r15b, al
0x18000b7d7  mov     eax, ebx
0x18000b7d9  setnz   cl
0x18000b7dc  and     eax, esi
0x18000b7de  mov     ebx, ecx
0x18000b7e0  jmp     short loc_18000B7F6
0x18000b7e2  test    r15b, bl
0x18000b7e5  jz      short loc_18000B7F2
0x18000b7e7  cmp     byte ptr [rcx+1Fh], 0
0x18000b7eb  jz      short loc_18000B7F2
0x18000b7ed  mov     eax, r15d
0x18000b7f0  jmp     short loc_18000B7F4
0x18000b7f2  xor     eax, eax
0x18000b7f4  and     ebx, esi
0x18000b7f6  or      ebx, eax
0x18000b7f8  add     rdi, 8
0x18000b7fc  mov     dword ptr [rbp+var_20], ebx
0x18000b7ff  test    r15b, bl
0x18000b802  jnz     short loc_18000B78F
0x18000b804  mov     rax, [rbp+var_20]
0x18000b808  mov     rcx, [rbp+var_10]
0x18000b80c  xor     rcx, rsp; StackCookie
0x18000b80f  call    __security_check_cookie
0x18000b814  lea     r11, [rsp+70h+var_s0]
0x18000b819  mov     rbx, [r11+30h]
0x18000b81d  mov     rsi, [r11+38h]
0x18000b821  mov     rsp, r11
0x18000b824  pop     r15
0x18000b826  pop     rdi
0x18000b827  pop     rbp
0x18000b828  retn
```
