# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000c42c`
- end: `0x14000c664`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1400088d0`

## callees

- `0x140001ee0`
- `0x1400028b8`
- `0x14000c42c`
- `0x14000cbf0`
- `0x1400154e0`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000c4cc`
- `KERNEL32!GetProcAddress` at `0x14000c4cc`
- `KERNEL32!GetModuleHandleW` at `0x14000c4b5`
- `KERNEL32!GetModuleHandleW` at `0x14000c4b5`

## string_xrefs

- `0x14000c4ae`: `ntdll.dll`

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
0x14000c42c  push    rbp
0x14000c42e  push    rbx
0x14000c42f  push    rsi
0x14000c430  push    rdi
0x14000c431  push    r14
0x14000c433  push    r15
0x14000c435  lea     rbp, [rsp-0F68h]
0x14000c43d  mov     eax, 1068h
0x14000c442  call    _alloca_probe
0x14000c447  sub     rsp, rax
0x14000c44a  mov     rax, cs:__security_cookie
0x14000c451  xor     rax, rsp
0x14000c454  mov     [rbp+0F90h+var_40], rax
0x14000c45b  mov     rax, [rcx+8]
0x14000c45f  xor     ebx, ebx
0x14000c461  sub     rax, [rcx]
0x14000c464  xor     esi, esi
0x14000c466  mov     r14, rcx
0x14000c469  cmp     rax, 0Ch
0x14000c46d  jb      loc_14000C630
0x14000c473  xor     r15d, r15d
0x14000c476  xor     edx, edx; Val
0x14000c478  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000c47d  mov     r8d, 1000h; Size
0x14000c483  call    memset_0
0x14000c488  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000c490  mov     [rsp+1090h+var_1050], 1000h
0x14000c498  mov     [rsp+1090h+var_104C], 0
0x14000c4a0  jnz     short loc_14000C4EA
0x14000c4a2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c4a9  test    rax, rax
0x14000c4ac  jnz     short loc_14000C4C2
0x14000c4ae  lea     rcx, ModuleName; "ntdll.dll"
0x14000c4b5  call    cs:__imp_GetModuleHandleW
0x14000c4bb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA, rax; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c4c2  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000c4c9  mov     rcx, rax; hModule
0x14000c4cc  call    cs:__imp_GetProcAddress
0x14000c4d2  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000c4d9  test    rax, rax
0x14000c4dc  jnz     short loc_14000C4EA
0x14000c4de  mov     edi, 0C0000139h
0x14000c4e3  mov     ebx, edi
0x14000c4e5  jmp     loc_14000C617
0x14000c4ea  lea     rax, [rsp+1090h+var_1050]
0x14000c4ef  xor     r8d, r8d
0x14000c4f2  mov     [rsp+1090h+var_1068], rax
0x14000c4f7  lea     r9, [rsp+1090h+var_104C]
0x14000c4fc  lea     rax, [rsp+1090h+var_1040]
0x14000c501  xor     edx, edx
0x14000c503  mov     [rsp+1090h+var_1070], rax
0x14000c508  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000c50f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000c516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c51b  mov     ebx, eax
0x14000c51d  mov     edi, eax
0x14000c51f  test    eax, eax
0x14000c521  jnz     loc_14000C617
0x14000c527  mov     r9d, [rsp+1090h+var_1050]
0x14000c52c  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000c536  mov     rax, r11
0x14000c539  mul     r9
0x14000c53c  shr     rdx, 3
0x14000c540  lea     rcx, [rdx+rdx*2]
0x14000c544  shl     rcx, 2
0x14000c548  cmp     r9, rcx
0x14000c54b  jz      short loc_14000C555
0x14000c54d  xor     r9d, r9d
0x14000c550  mov     [rsp+1090h+var_1050], r9d
0x14000c555  mov     r8, [r14]
0x14000c558  mov     rax, r11
0x14000c55b  mov     ecx, r9d
0x14000c55e  mul     rcx
0x14000c561  mov     rcx, [r14+8]
0x14000c565  mov     rax, r11
0x14000c568  mov     r10, rdx
0x14000c56b  sub     rcx, r8
0x14000c56e  mul     rcx
0x14000c571  shr     r10, 3
0x14000c575  shr     rdx, 3
0x14000c579  lea     rax, [rdx+rdx*2]
0x14000c57d  lea     rsi, [r8+rax*4]
0x14000c581  jmp     short loc_14000C5EC
0x14000c583  mov     eax, r10d
0x14000c586  lea     rcx, [rax+rax*2]
0x14000c58a  lea     rdx, [rdx+rcx*4]
0x14000c58e  lea     rax, [rsp+1090h+var_1040]
0x14000c593  cmp     rax, rdx
0x14000c596  jz      short loc_14000C5BD
0x14000c598  mov     r11d, [r8]
0x14000c59b  lea     rcx, [rsp+1090h+var_1040]
0x14000c5a0  cmp     [rcx], r11d
0x14000c5a3  jnz     short loc_14000C5B4
0x14000c5a5  movzx   eax, word ptr [r8+4]
0x14000c5aa  cmp     [rcx+4], ax
0x14000c5ae  jz      loc_14000C656
0x14000c5b4  add     rcx, 0Ch
0x14000c5b8  cmp     rcx, rdx
0x14000c5bb  jnz     short loc_14000C5A0
0x14000c5bd  mov     eax, r9d
0x14000c5c0  add     rax, 0Ch
0x14000c5c4  cmp     rax, 1000h
0x14000c5ca  ja      short loc_14000C5E8
0x14000c5cc  movsd   xmm0, qword ptr [r8]
0x14000c5d1  add     r9d, 0Ch
0x14000c5d5  movsd   qword ptr [rdx], xmm0
0x14000c5d9  inc     r10d
0x14000c5dc  mov     eax, [r8+8]
0x14000c5e0  mov     [rdx+8], eax
0x14000c5e3  mov     [rsp+1090h+var_1050], r9d
0x14000c5e8  add     r8, 0Ch
0x14000c5ec  lea     rdx, [rsp+1090h+var_1040]
0x14000c5f1  cmp     r8, rsi
0x14000c5f4  jnz     short loc_14000C583
0x14000c5f6  mov     eax, [rsp+1090h+var_104C]
0x14000c5fa  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000c601  mov     [rsp+1090h+var_1060], 1
0x14000c609  mov     r8d, r9d
0x14000c60c  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000c610  call    wil_details_NtUpdateWnfStateData
0x14000c615  mov     esi, eax
0x14000c617  cmp     esi, 0C0000001h
0x14000c61d  jnz     short loc_14000C630
0x14000c61f  inc     r15d
0x14000c622  cmp     r15d, 64h ; 'd'
0x14000c626  jge     short loc_14000C630
0x14000c628  test    edi, edi
0x14000c62a  jz      loc_14000C476
0x14000c630  test    ebx, ebx
0x14000c632  cmovz   ebx, esi
0x14000c635  mov     eax, ebx
0x14000c637  mov     rcx, [rbp+0F90h+var_40]
0x14000c63e  xor     rcx, rsp; StackCookie
0x14000c641  call    __security_check_cookie
0x14000c646  add     rsp, 1068h
0x14000c64d  pop     r15
0x14000c64f  pop     r14
0x14000c651  pop     rdi
0x14000c652  pop     rsi
0x14000c653  pop     rbx
0x14000c654  pop     rbp
0x14000c655  retn
0x14000c656  mov     eax, [r8+8]
0x14000c65a  add     [rcx+8], eax
0x14000c65d  mov     r9d, [rsp+1090h+var_1050]
0x14000c662  jmp     short loc_14000C5E8
```
