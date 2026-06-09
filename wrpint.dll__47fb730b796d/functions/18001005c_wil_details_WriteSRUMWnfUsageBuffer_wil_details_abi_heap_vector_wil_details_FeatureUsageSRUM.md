# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001005c`
- end: `0x180010294`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a310`

## callees

- `0x18001005c`
- `0x1800117f4`
- `0x18001b77a`
- `0x18001b7b0`
- `0x18001b840`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800100fc`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800100fc`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800100e5`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800100e5`

## string_xrefs

- `0x1800100de`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int v1; // ebx
  unsigned int updated; // esi
  int v4; // r15d
  HMODULE ModuleHandleW; // rax
  int v6; // edi
  unsigned int v7; // r9d
  __int64 v8; // r8
  int v9; // r10d
  unsigned __int64 v10; // rsi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  unsigned int v14; // [rsp+40h] [rbp-C0h]
  _DWORD v15[3]; // [rsp+44h] [rbp-BCh] BYREF
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
        v1 = ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, _DWORD *))g_wil_details_pfnNtQueryWnfStateData)(
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
              if ( (unsigned __int64)v7 + 12 <= 0x1000 )
              {
                v7 += 12;
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
                      (unsigned int)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                      (unsigned int)v16,
                      v7,
                      v7,
                      (unsigned int)v16,
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
0x18001005c  push    rbp
0x18001005e  push    rbx
0x18001005f  push    rsi
0x180010060  push    rdi
0x180010061  push    r14
0x180010063  push    r15
0x180010065  lea     rbp, [rsp-0F68h]
0x18001006d  mov     eax, 1068h
0x180010072  call    _alloca_probe
0x180010077  sub     rsp, rax
0x18001007a  mov     rax, cs:__security_cookie
0x180010081  xor     rax, rsp
0x180010084  mov     [rbp+0F90h+var_40], rax
0x18001008b  mov     rax, [rcx+8]
0x18001008f  xor     ebx, ebx
0x180010091  sub     rax, [rcx]
0x180010094  xor     esi, esi
0x180010096  mov     r14, rcx
0x180010099  cmp     rax, 0Ch
0x18001009d  jb      loc_180010260
0x1800100a3  xor     r15d, r15d
0x1800100a6  xor     edx, edx; Val
0x1800100a8  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800100ad  mov     r8d, 1000h; Size
0x1800100b3  call    memset_0
0x1800100b8  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1800100c0  mov     [rsp+1090h+var_1050], 1000h
0x1800100c8  mov     [rsp+1090h+var_104C], 0
0x1800100d0  jnz     short loc_18001011A
0x1800100d2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800100d9  test    rax, rax
0x1800100dc  jnz     short loc_1800100F2
0x1800100de  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800100e5  call    cs:__imp_GetModuleHandleW
0x1800100eb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800100f2  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800100f9  mov     rcx, rax; hModule
0x1800100fc  call    cs:__imp_GetProcAddress
0x180010102  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180010109  test    rax, rax
0x18001010c  jnz     short loc_18001011A
0x18001010e  mov     edi, 0C0000139h
0x180010113  mov     ebx, edi
0x180010115  jmp     loc_180010247
0x18001011a  lea     rax, [rsp+1090h+var_1050]
0x18001011f  xor     r8d, r8d
0x180010122  mov     [rsp+1090h+var_1068], rax
0x180010127  lea     r9, [rsp+1090h+var_104C]
0x18001012c  lea     rax, [rsp+1090h+var_1040]
0x180010131  xor     edx, edx
0x180010133  mov     [rsp+1090h+var_1070], rax
0x180010138  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001013f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180010146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001014b  mov     ebx, eax
0x18001014d  mov     edi, eax
0x18001014f  test    eax, eax
0x180010151  jnz     loc_180010247
0x180010157  mov     r9d, [rsp+1090h+var_1050]
0x18001015c  mov     r11, 0AAAAAAAAAAAAAAABh
0x180010166  mov     rax, r11
0x180010169  mul     r9
0x18001016c  shr     rdx, 3
0x180010170  lea     rcx, [rdx+rdx*2]
0x180010174  shl     rcx, 2
0x180010178  cmp     r9, rcx
0x18001017b  jz      short loc_180010185
0x18001017d  xor     r9d, r9d
0x180010180  mov     [rsp+1090h+var_1050], r9d
0x180010185  mov     r8, [r14]
0x180010188  mov     rax, r11
0x18001018b  mov     ecx, r9d
0x18001018e  mul     rcx
0x180010191  mov     rcx, [r14+8]
0x180010195  mov     rax, r11
0x180010198  mov     r10, rdx
0x18001019b  sub     rcx, r8
0x18001019e  mul     rcx
0x1800101a1  shr     r10, 3
0x1800101a5  shr     rdx, 3
0x1800101a9  lea     rax, [rdx+rdx*2]
0x1800101ad  lea     rsi, [r8+rax*4]
0x1800101b1  jmp     short loc_18001021C
0x1800101b3  mov     eax, r10d
0x1800101b6  lea     rcx, [rax+rax*2]
0x1800101ba  lea     rdx, [rdx+rcx*4]
0x1800101be  lea     rax, [rsp+1090h+var_1040]
0x1800101c3  cmp     rax, rdx
0x1800101c6  jz      short loc_1800101ED
0x1800101c8  mov     r11d, [r8]
0x1800101cb  lea     rcx, [rsp+1090h+var_1040]
0x1800101d0  cmp     [rcx], r11d
0x1800101d3  jnz     short loc_1800101E4
0x1800101d5  movzx   eax, word ptr [r8+4]
0x1800101da  cmp     [rcx+4], ax
0x1800101de  jz      loc_180010286
0x1800101e4  add     rcx, 0Ch
0x1800101e8  cmp     rcx, rdx
0x1800101eb  jnz     short loc_1800101D0
0x1800101ed  mov     eax, r9d
0x1800101f0  add     rax, 0Ch
0x1800101f4  cmp     rax, 1000h
0x1800101fa  ja      short loc_180010218
0x1800101fc  movsd   xmm0, qword ptr [r8]
0x180010201  add     r9d, 0Ch
0x180010205  movsd   qword ptr [rdx], xmm0
0x180010209  inc     r10d
0x18001020c  mov     eax, [r8+8]
0x180010210  mov     [rdx+8], eax
0x180010213  mov     [rsp+1090h+var_1050], r9d
0x180010218  add     r8, 0Ch
0x18001021c  lea     rdx, [rsp+1090h+var_1040]
0x180010221  cmp     r8, rsi
0x180010224  jnz     short loc_1800101B3
0x180010226  mov     eax, [rsp+1090h+var_104C]
0x18001022a  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180010231  mov     [rsp+1090h+var_1060], 1
0x180010239  mov     r8d, r9d
0x18001023c  mov     dword ptr [rsp+1090h+var_1068], eax
0x180010240  call    wil_details_NtUpdateWnfStateData
0x180010245  mov     esi, eax
0x180010247  cmp     esi, 0C0000001h
0x18001024d  jnz     short loc_180010260
0x18001024f  inc     r15d
0x180010252  cmp     r15d, 64h ; 'd'
0x180010256  jge     short loc_180010260
0x180010258  test    edi, edi
0x18001025a  jz      loc_1800100A6
0x180010260  test    ebx, ebx
0x180010262  cmovz   ebx, esi
0x180010265  mov     eax, ebx
0x180010267  mov     rcx, [rbp+0F90h+var_40]
0x18001026e  xor     rcx, rsp; StackCookie
0x180010271  call    __security_check_cookie
0x180010276  add     rsp, 1068h
0x18001027d  pop     r15
0x18001027f  pop     r14
0x180010281  pop     rdi
0x180010282  pop     rsi
0x180010283  pop     rbx
0x180010284  pop     rbp
0x180010285  retn
0x180010286  mov     eax, [r8+8]
0x18001028a  add     [rcx+8], eax
0x18001028d  mov     r9d, [rsp+1090h+var_1050]
0x180010292  jmp     short loc_180010218
```
