# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140014b48`
- end: `0x140014d80`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14000f7d0`

## callees

- `0x140002fbc`
- `0x140003200`
- `0x140014b48`
- `0x140015010`
- `0x14001c930`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014be8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014be8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140014bd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140014bd1`

## string_xrefs

- `0x140014bca`: `ntdll.dll`

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
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x140014b48  push    rbp
0x140014b4a  push    rbx
0x140014b4b  push    rsi
0x140014b4c  push    rdi
0x140014b4d  push    r14
0x140014b4f  push    r15
0x140014b51  lea     rbp, [rsp-0F68h]
0x140014b59  mov     eax, 1068h
0x140014b5e  call    _alloca_probe
0x140014b63  sub     rsp, rax
0x140014b66  mov     rax, cs:__security_cookie
0x140014b6d  xor     rax, rsp
0x140014b70  mov     [rbp+0F90h+var_40], rax
0x140014b77  mov     rax, [rcx+8]
0x140014b7b  xor     ebx, ebx
0x140014b7d  sub     rax, [rcx]
0x140014b80  xor     esi, esi
0x140014b82  mov     r14, rcx
0x140014b85  cmp     rax, 0Ch
0x140014b89  jb      loc_140014D4C
0x140014b8f  xor     r15d, r15d
0x140014b92  xor     edx, edx; Val
0x140014b94  lea     rcx, [rsp+1090h+var_1040]; void *
0x140014b99  mov     r8d, 1000h; Size
0x140014b9f  call    memset_0
0x140014ba4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x140014bac  mov     [rsp+1090h+var_1050], 1000h
0x140014bb4  mov     [rsp+1090h+var_104C], 0
0x140014bbc  jnz     short loc_140014C06
0x140014bbe  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140014bc5  test    rax, rax
0x140014bc8  jnz     short loc_140014BDE
0x140014bca  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140014bd1  call    cs:__imp_GetModuleHandleW
0x140014bd7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140014bde  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140014be5  mov     rcx, rax; hModule
0x140014be8  call    cs:__imp_GetProcAddress
0x140014bee  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140014bf5  test    rax, rax
0x140014bf8  jnz     short loc_140014C06
0x140014bfa  mov     edi, 0C0000139h
0x140014bff  mov     ebx, edi
0x140014c01  jmp     loc_140014D33
0x140014c06  lea     rax, [rsp+1090h+var_1050]
0x140014c0b  xor     r8d, r8d
0x140014c0e  mov     [rsp+1090h+var_1068], rax
0x140014c13  lea     r9, [rsp+1090h+var_104C]
0x140014c18  lea     rax, [rsp+1090h+var_1040]
0x140014c1d  xor     edx, edx
0x140014c1f  mov     [rsp+1090h+var_1070], rax
0x140014c24  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140014c2b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140014c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014c37  mov     ebx, eax
0x140014c39  mov     edi, eax
0x140014c3b  test    eax, eax
0x140014c3d  jnz     loc_140014D33
0x140014c43  mov     r9d, [rsp+1090h+var_1050]
0x140014c48  mov     r11, 0AAAAAAAAAAAAAAABh
0x140014c52  mov     rax, r11
0x140014c55  mul     r9
0x140014c58  shr     rdx, 3
0x140014c5c  lea     rcx, [rdx+rdx*2]
0x140014c60  shl     rcx, 2
0x140014c64  cmp     r9, rcx
0x140014c67  jz      short loc_140014C71
0x140014c69  xor     r9d, r9d
0x140014c6c  mov     [rsp+1090h+var_1050], r9d
0x140014c71  mov     r8, [r14]
0x140014c74  mov     rax, r11
0x140014c77  mov     ecx, r9d
0x140014c7a  mul     rcx
0x140014c7d  mov     rcx, [r14+8]
0x140014c81  mov     rax, r11
0x140014c84  mov     r10, rdx
0x140014c87  sub     rcx, r8
0x140014c8a  mul     rcx
0x140014c8d  shr     r10, 3
0x140014c91  shr     rdx, 3
0x140014c95  lea     rax, [rdx+rdx*2]
0x140014c99  lea     rsi, [r8+rax*4]
0x140014c9d  jmp     short loc_140014D08
0x140014c9f  mov     eax, r10d
0x140014ca2  lea     rcx, [rax+rax*2]
0x140014ca6  lea     rdx, [rdx+rcx*4]
0x140014caa  lea     rax, [rsp+1090h+var_1040]
0x140014caf  cmp     rax, rdx
0x140014cb2  jz      short loc_140014CD9
0x140014cb4  mov     r11d, [r8]
0x140014cb7  lea     rcx, [rsp+1090h+var_1040]
0x140014cbc  cmp     [rcx], r11d
0x140014cbf  jnz     short loc_140014CD0
0x140014cc1  movzx   eax, word ptr [r8+4]
0x140014cc6  cmp     [rcx+4], ax
0x140014cca  jz      loc_140014D72
0x140014cd0  add     rcx, 0Ch
0x140014cd4  cmp     rcx, rdx
0x140014cd7  jnz     short loc_140014CBC
0x140014cd9  mov     eax, r9d
0x140014cdc  add     rax, 0Ch
0x140014ce0  cmp     rax, 1000h
0x140014ce6  ja      short loc_140014D04
0x140014ce8  movsd   xmm0, qword ptr [r8]
0x140014ced  add     r9d, 0Ch
0x140014cf1  movsd   qword ptr [rdx], xmm0
0x140014cf5  inc     r10d
0x140014cf8  mov     eax, [r8+8]
0x140014cfc  mov     [rdx+8], eax
0x140014cff  mov     [rsp+1090h+var_1050], r9d
0x140014d04  add     r8, 0Ch
0x140014d08  lea     rdx, [rsp+1090h+var_1040]
0x140014d0d  cmp     r8, rsi
0x140014d10  jnz     short loc_140014C9F
0x140014d12  mov     eax, [rsp+1090h+var_104C]
0x140014d16  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140014d1d  mov     [rsp+1090h+var_1060], 1
0x140014d25  mov     r8d, r9d
0x140014d28  mov     dword ptr [rsp+1090h+var_1068], eax
0x140014d2c  call    wil_details_NtUpdateWnfStateData
0x140014d31  mov     esi, eax
0x140014d33  cmp     esi, 0C0000001h
0x140014d39  jnz     short loc_140014D4C
0x140014d3b  inc     r15d
0x140014d3e  cmp     r15d, 64h ; 'd'
0x140014d42  jge     short loc_140014D4C
0x140014d44  test    edi, edi
0x140014d46  jz      loc_140014B92
0x140014d4c  test    ebx, ebx
0x140014d4e  cmovz   ebx, esi
0x140014d51  mov     eax, ebx
0x140014d53  mov     rcx, [rbp+0F90h+var_40]
0x140014d5a  xor     rcx, rsp; StackCookie
0x140014d5d  call    __security_check_cookie
0x140014d62  add     rsp, 1068h
0x140014d69  pop     r15
0x140014d6b  pop     r14
0x140014d6d  pop     rdi
0x140014d6e  pop     rsi
0x140014d6f  pop     rbx
0x140014d70  pop     rbp
0x140014d71  retn
0x140014d72  mov     eax, [r8+8]
0x140014d76  add     [rcx+8], eax
0x140014d79  mov     r9d, [rsp+1090h+var_1050]
0x140014d7e  jmp     short loc_140014D04
```
