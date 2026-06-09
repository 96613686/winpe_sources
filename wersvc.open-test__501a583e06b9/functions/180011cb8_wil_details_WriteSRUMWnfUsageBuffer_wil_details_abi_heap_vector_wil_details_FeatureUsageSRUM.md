# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180011cb8`
- end: `0x180011ef0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180006d60`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180011cb8`
- `0x180012550`
- `0x1800344f0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011d41`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011d41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011d58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011d58`

## string_xrefs

- `0x180011d3a`: `ntdll.dll`

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
0x180011cb8  push    rbp
0x180011cba  push    rbx
0x180011cbb  push    rsi
0x180011cbc  push    rdi
0x180011cbd  push    r14
0x180011cbf  push    r15
0x180011cc1  lea     rbp, [rsp-0F68h]
0x180011cc9  mov     eax, 1068h
0x180011cce  call    _alloca_probe
0x180011cd3  sub     rsp, rax
0x180011cd6  mov     rax, cs:__security_cookie
0x180011cdd  xor     rax, rsp
0x180011ce0  mov     [rbp+0F90h+var_40], rax
0x180011ce7  mov     rax, [rcx+8]
0x180011ceb  xor     ebx, ebx
0x180011ced  sub     rax, [rcx]
0x180011cf0  xor     esi, esi
0x180011cf2  mov     r14, rcx
0x180011cf5  cmp     rax, 0Ch
0x180011cf9  jb      loc_180011EBC
0x180011cff  xor     r15d, r15d
0x180011d02  xor     edx, edx; Val
0x180011d04  lea     rcx, [rsp+1090h+var_1040]; void *
0x180011d09  mov     r8d, 1000h; Size
0x180011d0f  call    memset_0
0x180011d14  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180011d1c  mov     [rsp+1090h+var_1050], 1000h
0x180011d24  mov     [rsp+1090h+var_104C], 0
0x180011d2c  jnz     short loc_180011D76
0x180011d2e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011d35  test    rax, rax
0x180011d38  jnz     short loc_180011D4E
0x180011d3a  lea     rcx, Src; "ntdll.dll"
0x180011d41  call    cs:__imp_GetModuleHandleW
0x180011d47  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011d4e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180011d55  mov     rcx, rax; hModule
0x180011d58  call    cs:__imp_GetProcAddress
0x180011d5e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180011d65  test    rax, rax
0x180011d68  jnz     short loc_180011D76
0x180011d6a  mov     edi, 0C0000139h
0x180011d6f  mov     ebx, edi
0x180011d71  jmp     loc_180011EA3
0x180011d76  lea     rax, [rsp+1090h+var_1050]
0x180011d7b  xor     r8d, r8d
0x180011d7e  mov     [rsp+1090h+var_1068], rax
0x180011d83  lea     r9, [rsp+1090h+var_104C]
0x180011d88  lea     rax, [rsp+1090h+var_1040]
0x180011d8d  xor     edx, edx
0x180011d8f  mov     [rsp+1090h+var_1070], rax
0x180011d94  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180011d9b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180011da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011da7  mov     ebx, eax
0x180011da9  mov     edi, eax
0x180011dab  test    eax, eax
0x180011dad  jnz     loc_180011EA3
0x180011db3  mov     r9d, [rsp+1090h+var_1050]
0x180011db8  mov     r11, 0AAAAAAAAAAAAAAABh
0x180011dc2  mov     rax, r11
0x180011dc5  mul     r9
0x180011dc8  shr     rdx, 3
0x180011dcc  lea     rcx, [rdx+rdx*2]
0x180011dd0  shl     rcx, 2
0x180011dd4  cmp     r9, rcx
0x180011dd7  jz      short loc_180011DE1
0x180011dd9  xor     r9d, r9d
0x180011ddc  mov     [rsp+1090h+var_1050], r9d
0x180011de1  mov     r8, [r14]
0x180011de4  mov     rax, r11
0x180011de7  mov     ecx, r9d
0x180011dea  mul     rcx
0x180011ded  mov     rcx, [r14+8]
0x180011df1  mov     rax, r11
0x180011df4  mov     r10, rdx
0x180011df7  sub     rcx, r8
0x180011dfa  mul     rcx
0x180011dfd  shr     r10, 3
0x180011e01  shr     rdx, 3
0x180011e05  lea     rax, [rdx+rdx*2]
0x180011e09  lea     rsi, [r8+rax*4]
0x180011e0d  jmp     short loc_180011E78
0x180011e0f  mov     eax, r10d
0x180011e12  lea     rcx, [rax+rax*2]
0x180011e16  lea     rdx, [rdx+rcx*4]
0x180011e1a  lea     rax, [rsp+1090h+var_1040]
0x180011e1f  cmp     rax, rdx
0x180011e22  jz      short loc_180011E49
0x180011e24  mov     r11d, [r8]
0x180011e27  lea     rcx, [rsp+1090h+var_1040]
0x180011e2c  cmp     [rcx], r11d
0x180011e2f  jnz     short loc_180011E40
0x180011e31  movzx   eax, word ptr [r8+4]
0x180011e36  cmp     [rcx+4], ax
0x180011e3a  jz      loc_180011EE2
0x180011e40  add     rcx, 0Ch
0x180011e44  cmp     rcx, rdx
0x180011e47  jnz     short loc_180011E2C
0x180011e49  mov     eax, r9d
0x180011e4c  add     rax, 0Ch
0x180011e50  cmp     rax, 1000h
0x180011e56  ja      short loc_180011E74
0x180011e58  movsd   xmm0, qword ptr [r8]
0x180011e5d  add     r9d, 0Ch
0x180011e61  movsd   qword ptr [rdx], xmm0
0x180011e65  inc     r10d
0x180011e68  mov     eax, [r8+8]
0x180011e6c  mov     [rdx+8], eax
0x180011e6f  mov     [rsp+1090h+var_1050], r9d
0x180011e74  add     r8, 0Ch
0x180011e78  lea     rdx, [rsp+1090h+var_1040]
0x180011e7d  cmp     r8, rsi
0x180011e80  jnz     short loc_180011E0F
0x180011e82  mov     eax, [rsp+1090h+var_104C]
0x180011e86  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180011e8d  mov     [rsp+1090h+var_1060], 1
0x180011e95  mov     r8d, r9d
0x180011e98  mov     dword ptr [rsp+1090h+var_1068], eax
0x180011e9c  call    wil_details_NtUpdateWnfStateData
0x180011ea1  mov     esi, eax
0x180011ea3  cmp     esi, 0C0000001h
0x180011ea9  jnz     short loc_180011EBC
0x180011eab  inc     r15d
0x180011eae  cmp     r15d, 64h ; 'd'
0x180011eb2  jge     short loc_180011EBC
0x180011eb4  test    edi, edi
0x180011eb6  jz      loc_180011D02
0x180011ebc  test    ebx, ebx
0x180011ebe  cmovz   ebx, esi
0x180011ec1  mov     eax, ebx
0x180011ec3  mov     rcx, [rbp+0F90h+var_40]
0x180011eca  xor     rcx, rsp; StackCookie
0x180011ecd  call    __security_check_cookie
0x180011ed2  add     rsp, 1068h
0x180011ed9  pop     r15
0x180011edb  pop     r14
0x180011edd  pop     rdi
0x180011ede  pop     rsi
0x180011edf  pop     rbx
0x180011ee0  pop     rbp
0x180011ee1  retn
0x180011ee2  mov     eax, [r8+8]
0x180011ee6  add     [rcx+8], eax
0x180011ee9  mov     r9d, [rsp+1090h+var_1050]
0x180011eee  jmp     short loc_180011E74
```
