# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000df18`
- end: `0x18000e150`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002d80`

## callees

- `0x1800020e0`
- `0x180002b38`
- `0x18000df18`
- `0x18000e6c0`
- `0x180014400`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dfa1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dfa1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dfb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dfb8`

## string_xrefs

- `0x18000df9a`: `ntdll.dll`

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
0x18000df18  push    rbp
0x18000df1a  push    rbx
0x18000df1b  push    rsi
0x18000df1c  push    rdi
0x18000df1d  push    r14
0x18000df1f  push    r15
0x18000df21  lea     rbp, [rsp-0F68h]
0x18000df29  mov     eax, 1068h
0x18000df2e  call    _alloca_probe
0x18000df33  sub     rsp, rax
0x18000df36  mov     rax, cs:__security_cookie
0x18000df3d  xor     rax, rsp
0x18000df40  mov     [rbp+0F90h+var_40], rax
0x18000df47  mov     rax, [rcx+8]
0x18000df4b  xor     ebx, ebx
0x18000df4d  sub     rax, [rcx]
0x18000df50  xor     esi, esi
0x18000df52  mov     r14, rcx
0x18000df55  cmp     rax, 0Ch
0x18000df59  jb      loc_18000E11C
0x18000df5f  xor     r15d, r15d
0x18000df62  xor     edx, edx; Val
0x18000df64  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000df69  mov     r8d, 1000h; Size
0x18000df6f  call    memset_0
0x18000df74  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000df7c  mov     [rsp+1090h+var_1050], 1000h
0x18000df84  mov     [rsp+1090h+var_104C], 0
0x18000df8c  jnz     short loc_18000DFD6
0x18000df8e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000df95  test    rax, rax
0x18000df98  jnz     short loc_18000DFAE
0x18000df9a  lea     rcx, ModuleName; "ntdll.dll"
0x18000dfa1  call    cs:__imp_GetModuleHandleW
0x18000dfa7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000dfae  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000dfb5  mov     rcx, rax; hModule
0x18000dfb8  call    cs:__imp_GetProcAddress
0x18000dfbe  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000dfc5  test    rax, rax
0x18000dfc8  jnz     short loc_18000DFD6
0x18000dfca  mov     edi, 0C0000139h
0x18000dfcf  mov     ebx, edi
0x18000dfd1  jmp     loc_18000E103
0x18000dfd6  lea     rax, [rsp+1090h+var_1050]
0x18000dfdb  xor     r8d, r8d
0x18000dfde  mov     [rsp+1090h+var_1068], rax
0x18000dfe3  lea     r9, [rsp+1090h+var_104C]
0x18000dfe8  lea     rax, [rsp+1090h+var_1040]
0x18000dfed  xor     edx, edx
0x18000dfef  mov     [rsp+1090h+var_1070], rax
0x18000dff4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000dffb  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000e002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e007  mov     ebx, eax
0x18000e009  mov     edi, eax
0x18000e00b  test    eax, eax
0x18000e00d  jnz     loc_18000E103
0x18000e013  mov     r9d, [rsp+1090h+var_1050]
0x18000e018  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000e022  mov     rax, r11
0x18000e025  mul     r9
0x18000e028  shr     rdx, 3
0x18000e02c  lea     rcx, [rdx+rdx*2]
0x18000e030  shl     rcx, 2
0x18000e034  cmp     r9, rcx
0x18000e037  jz      short loc_18000E041
0x18000e039  xor     r9d, r9d
0x18000e03c  mov     [rsp+1090h+var_1050], r9d
0x18000e041  mov     r8, [r14]
0x18000e044  mov     rax, r11
0x18000e047  mov     ecx, r9d
0x18000e04a  mul     rcx
0x18000e04d  mov     rcx, [r14+8]
0x18000e051  mov     rax, r11
0x18000e054  mov     r10, rdx
0x18000e057  sub     rcx, r8
0x18000e05a  mul     rcx
0x18000e05d  shr     r10, 3
0x18000e061  shr     rdx, 3
0x18000e065  lea     rax, [rdx+rdx*2]
0x18000e069  lea     rsi, [r8+rax*4]
0x18000e06d  jmp     short loc_18000E0D8
0x18000e06f  mov     eax, r10d
0x18000e072  lea     rcx, [rax+rax*2]
0x18000e076  lea     rdx, [rdx+rcx*4]
0x18000e07a  lea     rax, [rsp+1090h+var_1040]
0x18000e07f  cmp     rax, rdx
0x18000e082  jz      short loc_18000E0A9
0x18000e084  mov     r11d, [r8]
0x18000e087  lea     rcx, [rsp+1090h+var_1040]
0x18000e08c  cmp     [rcx], r11d
0x18000e08f  jnz     short loc_18000E0A0
0x18000e091  movzx   eax, word ptr [r8+4]
0x18000e096  cmp     [rcx+4], ax
0x18000e09a  jz      loc_18000E142
0x18000e0a0  add     rcx, 0Ch
0x18000e0a4  cmp     rcx, rdx
0x18000e0a7  jnz     short loc_18000E08C
0x18000e0a9  mov     eax, r9d
0x18000e0ac  add     rax, 0Ch
0x18000e0b0  cmp     rax, 1000h
0x18000e0b6  ja      short loc_18000E0D4
0x18000e0b8  movsd   xmm0, qword ptr [r8]
0x18000e0bd  add     r9d, 0Ch
0x18000e0c1  movsd   qword ptr [rdx], xmm0
0x18000e0c5  inc     r10d
0x18000e0c8  mov     eax, [r8+8]
0x18000e0cc  mov     [rdx+8], eax
0x18000e0cf  mov     [rsp+1090h+var_1050], r9d
0x18000e0d4  add     r8, 0Ch
0x18000e0d8  lea     rdx, [rsp+1090h+var_1040]
0x18000e0dd  cmp     r8, rsi
0x18000e0e0  jnz     short loc_18000E06F
0x18000e0e2  mov     eax, [rsp+1090h+var_104C]
0x18000e0e6  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000e0ed  mov     [rsp+1090h+var_1060], 1
0x18000e0f5  mov     r8d, r9d
0x18000e0f8  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000e0fc  call    wil_details_NtUpdateWnfStateData
0x18000e101  mov     esi, eax
0x18000e103  cmp     esi, 0C0000001h
0x18000e109  jnz     short loc_18000E11C
0x18000e10b  inc     r15d
0x18000e10e  cmp     r15d, 64h ; 'd'
0x18000e112  jge     short loc_18000E11C
0x18000e114  test    edi, edi
0x18000e116  jz      loc_18000DF62
0x18000e11c  test    ebx, ebx
0x18000e11e  cmovz   ebx, esi
0x18000e121  mov     eax, ebx
0x18000e123  mov     rcx, [rbp+0F90h+var_40]
0x18000e12a  xor     rcx, rsp; StackCookie
0x18000e12d  call    __security_check_cookie
0x18000e132  add     rsp, 1068h
0x18000e139  pop     r15
0x18000e13b  pop     r14
0x18000e13d  pop     rdi
0x18000e13e  pop     rsi
0x18000e13f  pop     rbx
0x18000e140  pop     rbp
0x18000e141  retn
0x18000e142  mov     eax, [r8+8]
0x18000e146  add     [rcx+8], eax
0x18000e149  mov     r9d, [rsp+1090h+var_1050]
0x18000e14e  jmp     short loc_18000E0D4
```
