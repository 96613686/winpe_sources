# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000b824`
- end: `0x18000ba5c`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180003db0`

## callees

- `0x180001770`
- `0x1800021f4`
- `0x18000b824`
- `0x18000bf30`
- `0x18000d740`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b8c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b8c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b8ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b8ad`

## string_xrefs

- `0x18000b8a6`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int v1; // ebx
  unsigned int updated; // esi
  int v4; // r15d
  HMODULE ModuleHandleW; // rax
  int v6; // edi
  __int64 v7; // r9
  __int64 v8; // r8
  int v9; // r10d
  unsigned __int64 v10; // rsi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  unsigned int v14; // [rsp+40h] [rbp-C0h]
  int v15[3]; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v16[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v1 = 0;
  updated = 0;
  if ( (unsigned __int64)(a1[1] - *a1) >= 0xC )
  {
    v4 = 0;
    do
    {
      memset_0(v16, 0, sizeof(v16));
      v15[0] = 0;
      if ( g_wil_details_pfnNtQueryWnfStateData )
        goto LABEL_8;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      g_wil_details_pfnNtQueryWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
      if ( g_wil_details_pfnNtQueryWnfStateData )
      {
LABEL_8:
        v1 = ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, int *))g_wil_details_pfnNtQueryWnfStateData)(
               &__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
               0,
               0,
               v15);
        v6 = v1;
        if ( !v1 )
        {
          v7 = 0;
          v14 = 0;
          v8 = *a1;
          v9 = 0;
          v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
          while ( v8 != v10 )
          {
            v11 = &v16[3 * v9];
            if ( v16 == v11 )
            {
LABEL_15:
              if ( (unsigned __int64)(unsigned int)v7 + 12 <= 0x1000 )
              {
                v7 = (unsigned int)(v7 + 12);
                *(_QWORD *)v11 = *(_QWORD *)v8;
                ++v9;
                v11[2] = *(_DWORD *)(v8 + 8);
                v14 = v7;
              }
            }
            else
            {
              v12 = v16;
              while ( *v12 != *(_DWORD *)v8 || *((_WORD *)v12 + 2) != *(_WORD *)(v8 + 4) )
              {
                v12 += 3;
                if ( v12 == v11 )
                  goto LABEL_15;
              }
              v12[2] += *(_DWORD *)(v8 + 8);
              v7 = v14;
            }
            v8 += 12;
          }
          updated = wil_details_NtUpdateWnfStateData(
                      (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                      (__int64)v16,
                      v7,
                      v7,
                      (int)v16,
                      v15[0],
                      1);
        }
      }
      else
      {
        v6 = -1073741511;
        v1 = -1073741511;
      }
      if ( updated != -1073741823 )
        break;
      if ( ++v4 >= 100 )
        break;
    }
    while ( !v6 );
  }
  if ( !v1 )
    return updated;
  return v1;
}

```

## disassembly

```asm
0x18000b824  push    rbp
0x18000b826  push    rbx
0x18000b827  push    rsi
0x18000b828  push    rdi
0x18000b829  push    r14
0x18000b82b  push    r15
0x18000b82d  lea     rbp, [rsp-0F68h]
0x18000b835  mov     eax, 1068h
0x18000b83a  call    _alloca_probe
0x18000b83f  sub     rsp, rax
0x18000b842  mov     rax, cs:__security_cookie
0x18000b849  xor     rax, rsp
0x18000b84c  mov     [rbp+0F90h+var_40], rax
0x18000b853  mov     rax, [rcx+8]
0x18000b857  xor     ebx, ebx
0x18000b859  sub     rax, [rcx]
0x18000b85c  xor     esi, esi
0x18000b85e  mov     r14, rcx
0x18000b861  cmp     rax, 0Ch
0x18000b865  jb      loc_18000BA28
0x18000b86b  xor     r15d, r15d
0x18000b86e  xor     edx, edx; Val
0x18000b870  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000b875  mov     r8d, 1000h; Size
0x18000b87b  call    memset_0
0x18000b880  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000b888  mov     [rsp+1090h+var_1050], 1000h
0x18000b890  mov     [rsp+1090h+var_104C], 0
0x18000b898  jnz     short loc_18000B8E2
0x18000b89a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b8a1  test    rax, rax
0x18000b8a4  jnz     short loc_18000B8BA
0x18000b8a6  lea     rcx, ModuleName; "ntdll.dll"
0x18000b8ad  call    cs:__imp_GetModuleHandleW
0x18000b8b3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b8ba  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000b8c1  mov     rcx, rax; hModule
0x18000b8c4  call    cs:__imp_GetProcAddress
0x18000b8ca  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000b8d1  test    rax, rax
0x18000b8d4  jnz     short loc_18000B8E2
0x18000b8d6  mov     edi, 0C0000139h
0x18000b8db  mov     ebx, edi
0x18000b8dd  jmp     loc_18000BA0F
0x18000b8e2  lea     rax, [rsp+1090h+var_1050]
0x18000b8e7  xor     r8d, r8d
0x18000b8ea  mov     [rsp+1090h+var_1068], rax
0x18000b8ef  lea     r9, [rsp+1090h+var_104C]
0x18000b8f4  lea     rax, [rsp+1090h+var_1040]
0x18000b8f9  xor     edx, edx
0x18000b8fb  mov     [rsp+1090h+var_1070], rax
0x18000b900  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b907  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000b90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b913  mov     ebx, eax
0x18000b915  mov     edi, eax
0x18000b917  test    eax, eax
0x18000b919  jnz     loc_18000BA0F
0x18000b91f  mov     r9d, [rsp+1090h+var_1050]
0x18000b924  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000b92e  mov     rax, r11
0x18000b931  mul     r9
0x18000b934  shr     rdx, 3
0x18000b938  lea     rcx, [rdx+rdx*2]
0x18000b93c  shl     rcx, 2
0x18000b940  cmp     r9, rcx
0x18000b943  jz      short loc_18000B94D
0x18000b945  xor     r9d, r9d
0x18000b948  mov     [rsp+1090h+var_1050], r9d
0x18000b94d  mov     r8, [r14]
0x18000b950  mov     rax, r11
0x18000b953  mov     ecx, r9d
0x18000b956  mul     rcx
0x18000b959  mov     rcx, [r14+8]
0x18000b95d  mov     rax, r11
0x18000b960  mov     r10, rdx
0x18000b963  sub     rcx, r8
0x18000b966  mul     rcx
0x18000b969  shr     r10, 3
0x18000b96d  shr     rdx, 3
0x18000b971  lea     rax, [rdx+rdx*2]
0x18000b975  lea     rsi, [r8+rax*4]
0x18000b979  jmp     short loc_18000B9E4
0x18000b97b  mov     eax, r10d
0x18000b97e  lea     rcx, [rax+rax*2]
0x18000b982  lea     rdx, [rdx+rcx*4]
0x18000b986  lea     rax, [rsp+1090h+var_1040]
0x18000b98b  cmp     rax, rdx
0x18000b98e  jz      short loc_18000B9B5
0x18000b990  mov     r11d, [r8]
0x18000b993  lea     rcx, [rsp+1090h+var_1040]
0x18000b998  cmp     [rcx], r11d
0x18000b99b  jnz     short loc_18000B9AC
0x18000b99d  movzx   eax, word ptr [r8+4]
0x18000b9a2  cmp     [rcx+4], ax
0x18000b9a6  jz      loc_18000BA4E
0x18000b9ac  add     rcx, 0Ch
0x18000b9b0  cmp     rcx, rdx
0x18000b9b3  jnz     short loc_18000B998
0x18000b9b5  mov     eax, r9d
0x18000b9b8  add     rax, 0Ch
0x18000b9bc  cmp     rax, 1000h
0x18000b9c2  ja      short loc_18000B9E0
0x18000b9c4  movsd   xmm0, qword ptr [r8]
0x18000b9c9  add     r9d, 0Ch
0x18000b9cd  movsd   qword ptr [rdx], xmm0
0x18000b9d1  inc     r10d
0x18000b9d4  mov     eax, [r8+8]
0x18000b9d8  mov     [rdx+8], eax
0x18000b9db  mov     [rsp+1090h+var_1050], r9d
0x18000b9e0  add     r8, 0Ch
0x18000b9e4  lea     rdx, [rsp+1090h+var_1040]
0x18000b9e9  cmp     r8, rsi
0x18000b9ec  jnz     short loc_18000B97B
0x18000b9ee  mov     eax, [rsp+1090h+var_104C]
0x18000b9f2  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b9f9  mov     [rsp+1090h+var_1060], 1
0x18000ba01  mov     r8d, r9d
0x18000ba04  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000ba08  call    wil_details_NtUpdateWnfStateData
0x18000ba0d  mov     esi, eax
0x18000ba0f  cmp     esi, 0C0000001h
0x18000ba15  jnz     short loc_18000BA28
0x18000ba17  inc     r15d
0x18000ba1a  cmp     r15d, 64h ; 'd'
0x18000ba1e  jge     short loc_18000BA28
0x18000ba20  test    edi, edi
0x18000ba22  jz      loc_18000B86E
0x18000ba28  test    ebx, ebx
0x18000ba2a  cmovz   ebx, esi
0x18000ba2d  mov     eax, ebx
0x18000ba2f  mov     rcx, [rbp+0F90h+var_40]
0x18000ba36  xor     rcx, rsp; StackCookie
0x18000ba39  call    __security_check_cookie
0x18000ba3e  add     rsp, 1068h
0x18000ba45  pop     r15
0x18000ba47  pop     r14
0x18000ba49  pop     rdi
0x18000ba4a  pop     rsi
0x18000ba4b  pop     rbx
0x18000ba4c  pop     rbp
0x18000ba4d  retn
0x18000ba4e  mov     eax, [r8+8]
0x18000ba52  add     [rcx+8], eax
0x18000ba55  mov     r9d, [rsp+1090h+var_1050]
0x18000ba5a  jmp     short loc_18000B9E0
```
