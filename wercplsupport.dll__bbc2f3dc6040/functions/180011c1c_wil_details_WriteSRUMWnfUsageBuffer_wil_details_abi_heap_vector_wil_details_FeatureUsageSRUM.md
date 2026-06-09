# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180011c1c`
- end: `0x180011e54`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180008100`

## callees

- `0x180011c1c`
- `0x180011e5c`
- `0x18001218a`
- `0x1800121b0`
- `0x180012240`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011cbc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011cbc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011ca5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011ca5`

## string_xrefs

- `0x180011c9e`: `ntdll.dll`

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
0x180011c1c  push    rbp
0x180011c1e  push    rbx
0x180011c1f  push    rsi
0x180011c20  push    rdi
0x180011c21  push    r14
0x180011c23  push    r15
0x180011c25  lea     rbp, [rsp-0F68h]
0x180011c2d  mov     eax, 1068h
0x180011c32  call    _alloca_probe
0x180011c37  sub     rsp, rax
0x180011c3a  mov     rax, cs:__security_cookie
0x180011c41  xor     rax, rsp
0x180011c44  mov     [rbp+0F90h+var_40], rax
0x180011c4b  mov     rax, [rcx+8]
0x180011c4f  xor     ebx, ebx
0x180011c51  sub     rax, [rcx]
0x180011c54  xor     esi, esi
0x180011c56  mov     r14, rcx
0x180011c59  cmp     rax, 0Ch
0x180011c5d  jb      loc_180011E20
0x180011c63  xor     r15d, r15d
0x180011c66  xor     edx, edx; Val
0x180011c68  lea     rcx, [rsp+1090h+var_1040]; void *
0x180011c6d  mov     r8d, 1000h; Size
0x180011c73  call    memset_0
0x180011c78  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180011c80  mov     [rsp+1090h+var_1050], 1000h
0x180011c88  mov     [rsp+1090h+var_104C], 0
0x180011c90  jnz     short loc_180011CDA
0x180011c92  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011c99  test    rax, rax
0x180011c9c  jnz     short loc_180011CB2
0x180011c9e  lea     rcx, ModuleName; "ntdll.dll"
0x180011ca5  call    cs:__imp_GetModuleHandleW
0x180011cab  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011cb2  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180011cb9  mov     rcx, rax; hModule
0x180011cbc  call    cs:__imp_GetProcAddress
0x180011cc2  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180011cc9  test    rax, rax
0x180011ccc  jnz     short loc_180011CDA
0x180011cce  mov     edi, 0C0000139h
0x180011cd3  mov     ebx, edi
0x180011cd5  jmp     loc_180011E07
0x180011cda  lea     rax, [rsp+1090h+var_1050]
0x180011cdf  xor     r8d, r8d
0x180011ce2  mov     [rsp+1090h+var_1068], rax
0x180011ce7  lea     r9, [rsp+1090h+var_104C]
0x180011cec  lea     rax, [rsp+1090h+var_1040]
0x180011cf1  xor     edx, edx
0x180011cf3  mov     [rsp+1090h+var_1070], rax
0x180011cf8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180011cff  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180011d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d0b  mov     ebx, eax
0x180011d0d  mov     edi, eax
0x180011d0f  test    eax, eax
0x180011d11  jnz     loc_180011E07
0x180011d17  mov     r9d, [rsp+1090h+var_1050]
0x180011d1c  mov     r11, 0AAAAAAAAAAAAAAABh
0x180011d26  mov     rax, r11
0x180011d29  mul     r9
0x180011d2c  shr     rdx, 3
0x180011d30  lea     rcx, [rdx+rdx*2]
0x180011d34  shl     rcx, 2
0x180011d38  cmp     r9, rcx
0x180011d3b  jz      short loc_180011D45
0x180011d3d  xor     r9d, r9d
0x180011d40  mov     [rsp+1090h+var_1050], r9d
0x180011d45  mov     r8, [r14]
0x180011d48  mov     rax, r11
0x180011d4b  mov     ecx, r9d
0x180011d4e  mul     rcx
0x180011d51  mov     rcx, [r14+8]
0x180011d55  mov     rax, r11
0x180011d58  mov     r10, rdx
0x180011d5b  sub     rcx, r8
0x180011d5e  mul     rcx
0x180011d61  shr     r10, 3
0x180011d65  shr     rdx, 3
0x180011d69  lea     rax, [rdx+rdx*2]
0x180011d6d  lea     rsi, [r8+rax*4]
0x180011d71  jmp     short loc_180011DDC
0x180011d73  mov     eax, r10d
0x180011d76  lea     rcx, [rax+rax*2]
0x180011d7a  lea     rdx, [rdx+rcx*4]
0x180011d7e  lea     rax, [rsp+1090h+var_1040]
0x180011d83  cmp     rax, rdx
0x180011d86  jz      short loc_180011DAD
0x180011d88  mov     r11d, [r8]
0x180011d8b  lea     rcx, [rsp+1090h+var_1040]
0x180011d90  cmp     [rcx], r11d
0x180011d93  jnz     short loc_180011DA4
0x180011d95  movzx   eax, word ptr [r8+4]
0x180011d9a  cmp     [rcx+4], ax
0x180011d9e  jz      loc_180011E46
0x180011da4  add     rcx, 0Ch
0x180011da8  cmp     rcx, rdx
0x180011dab  jnz     short loc_180011D90
0x180011dad  mov     eax, r9d
0x180011db0  add     rax, 0Ch
0x180011db4  cmp     rax, 1000h
0x180011dba  ja      short loc_180011DD8
0x180011dbc  movsd   xmm0, qword ptr [r8]
0x180011dc1  add     r9d, 0Ch
0x180011dc5  movsd   qword ptr [rdx], xmm0
0x180011dc9  inc     r10d
0x180011dcc  mov     eax, [r8+8]
0x180011dd0  mov     [rdx+8], eax
0x180011dd3  mov     [rsp+1090h+var_1050], r9d
0x180011dd8  add     r8, 0Ch
0x180011ddc  lea     rdx, [rsp+1090h+var_1040]
0x180011de1  cmp     r8, rsi
0x180011de4  jnz     short loc_180011D73
0x180011de6  mov     eax, [rsp+1090h+var_104C]
0x180011dea  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180011df1  mov     [rsp+1090h+var_1060], 1
0x180011df9  mov     r8d, r9d
0x180011dfc  mov     dword ptr [rsp+1090h+var_1068], eax
0x180011e00  call    wil_details_NtUpdateWnfStateData
0x180011e05  mov     esi, eax
0x180011e07  cmp     esi, 0C0000001h
0x180011e0d  jnz     short loc_180011E20
0x180011e0f  inc     r15d
0x180011e12  cmp     r15d, 64h ; 'd'
0x180011e16  jge     short loc_180011E20
0x180011e18  test    edi, edi
0x180011e1a  jz      loc_180011C66
0x180011e20  test    ebx, ebx
0x180011e22  cmovz   ebx, esi
0x180011e25  mov     eax, ebx
0x180011e27  mov     rcx, [rbp+0F90h+var_40]
0x180011e2e  xor     rcx, rsp; StackCookie
0x180011e31  call    __security_check_cookie
0x180011e36  add     rsp, 1068h
0x180011e3d  pop     r15
0x180011e3f  pop     r14
0x180011e41  pop     rdi
0x180011e42  pop     rsi
0x180011e43  pop     rbx
0x180011e44  pop     rbp
0x180011e45  retn
0x180011e46  mov     eax, [r8+8]
0x180011e4a  add     [rcx+8], eax
0x180011e4d  mov     r9d, [rsp+1090h+var_1050]
0x180011e52  jmp     short loc_180011DD8
```
