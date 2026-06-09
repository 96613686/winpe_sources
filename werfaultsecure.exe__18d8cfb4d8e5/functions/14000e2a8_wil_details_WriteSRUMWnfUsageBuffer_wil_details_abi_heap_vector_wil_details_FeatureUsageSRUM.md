# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000e2a8`
- end: `0x14000e4e0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140007de0`

## callees

- `0x1400023d0`
- `0x140002fcc`
- `0x14000e2a8`
- `0x14000e4e8`
- `0x1400112a0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e348`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e348`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e331`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e331`

## string_xrefs

- `0x14000e32a`: `ntdll.dll`

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
0x14000e2a8  push    rbp
0x14000e2aa  push    rbx
0x14000e2ab  push    rsi
0x14000e2ac  push    rdi
0x14000e2ad  push    r14
0x14000e2af  push    r15
0x14000e2b1  lea     rbp, [rsp-0F68h]
0x14000e2b9  mov     eax, 1068h
0x14000e2be  call    _alloca_probe
0x14000e2c3  sub     rsp, rax
0x14000e2c6  mov     rax, cs:__security_cookie
0x14000e2cd  xor     rax, rsp
0x14000e2d0  mov     [rbp+0F90h+var_40], rax
0x14000e2d7  mov     rax, [rcx+8]
0x14000e2db  xor     ebx, ebx
0x14000e2dd  sub     rax, [rcx]
0x14000e2e0  xor     esi, esi
0x14000e2e2  mov     r14, rcx
0x14000e2e5  cmp     rax, 0Ch
0x14000e2e9  jb      loc_14000E4AC
0x14000e2ef  xor     r15d, r15d
0x14000e2f2  xor     edx, edx; Val
0x14000e2f4  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000e2f9  mov     r8d, 1000h; Size
0x14000e2ff  call    memset_0
0x14000e304  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000e30c  mov     [rsp+1090h+var_1050], 1000h
0x14000e314  mov     [rsp+1090h+var_104C], 0
0x14000e31c  jnz     short loc_14000E366
0x14000e31e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e325  test    rax, rax
0x14000e328  jnz     short loc_14000E33E
0x14000e32a  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000e331  call    cs:__imp_GetModuleHandleW
0x14000e337  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e33e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000e345  mov     rcx, rax; hModule
0x14000e348  call    cs:__imp_GetProcAddress
0x14000e34e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000e355  test    rax, rax
0x14000e358  jnz     short loc_14000E366
0x14000e35a  mov     edi, 0C0000139h
0x14000e35f  mov     ebx, edi
0x14000e361  jmp     loc_14000E493
0x14000e366  lea     rax, [rsp+1090h+var_1050]
0x14000e36b  xor     r8d, r8d
0x14000e36e  mov     [rsp+1090h+var_1068], rax
0x14000e373  lea     r9, [rsp+1090h+var_104C]
0x14000e378  lea     rax, [rsp+1090h+var_1040]
0x14000e37d  xor     edx, edx
0x14000e37f  mov     [rsp+1090h+var_1070], rax
0x14000e384  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000e38b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000e392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e397  mov     ebx, eax
0x14000e399  mov     edi, eax
0x14000e39b  test    eax, eax
0x14000e39d  jnz     loc_14000E493
0x14000e3a3  mov     r9d, [rsp+1090h+var_1050]
0x14000e3a8  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000e3b2  mov     rax, r11
0x14000e3b5  mul     r9
0x14000e3b8  shr     rdx, 3
0x14000e3bc  lea     rcx, [rdx+rdx*2]
0x14000e3c0  shl     rcx, 2
0x14000e3c4  cmp     r9, rcx
0x14000e3c7  jz      short loc_14000E3D1
0x14000e3c9  xor     r9d, r9d
0x14000e3cc  mov     [rsp+1090h+var_1050], r9d
0x14000e3d1  mov     r8, [r14]
0x14000e3d4  mov     rax, r11
0x14000e3d7  mov     ecx, r9d
0x14000e3da  mul     rcx
0x14000e3dd  mov     rcx, [r14+8]
0x14000e3e1  mov     rax, r11
0x14000e3e4  mov     r10, rdx
0x14000e3e7  sub     rcx, r8
0x14000e3ea  mul     rcx
0x14000e3ed  shr     r10, 3
0x14000e3f1  shr     rdx, 3
0x14000e3f5  lea     rax, [rdx+rdx*2]
0x14000e3f9  lea     rsi, [r8+rax*4]
0x14000e3fd  jmp     short loc_14000E468
0x14000e3ff  mov     eax, r10d
0x14000e402  lea     rcx, [rax+rax*2]
0x14000e406  lea     rdx, [rdx+rcx*4]
0x14000e40a  lea     rax, [rsp+1090h+var_1040]
0x14000e40f  cmp     rax, rdx
0x14000e412  jz      short loc_14000E439
0x14000e414  mov     r11d, [r8]
0x14000e417  lea     rcx, [rsp+1090h+var_1040]
0x14000e41c  cmp     [rcx], r11d
0x14000e41f  jnz     short loc_14000E430
0x14000e421  movzx   eax, word ptr [r8+4]
0x14000e426  cmp     [rcx+4], ax
0x14000e42a  jz      loc_14000E4D2
0x14000e430  add     rcx, 0Ch
0x14000e434  cmp     rcx, rdx
0x14000e437  jnz     short loc_14000E41C
0x14000e439  mov     eax, r9d
0x14000e43c  add     rax, 0Ch
0x14000e440  cmp     rax, 1000h
0x14000e446  ja      short loc_14000E464
0x14000e448  movsd   xmm0, qword ptr [r8]
0x14000e44d  add     r9d, 0Ch
0x14000e451  movsd   qword ptr [rdx], xmm0
0x14000e455  inc     r10d
0x14000e458  mov     eax, [r8+8]
0x14000e45c  mov     [rdx+8], eax
0x14000e45f  mov     [rsp+1090h+var_1050], r9d
0x14000e464  add     r8, 0Ch
0x14000e468  lea     rdx, [rsp+1090h+var_1040]
0x14000e46d  cmp     r8, rsi
0x14000e470  jnz     short loc_14000E3FF
0x14000e472  mov     eax, [rsp+1090h+var_104C]
0x14000e476  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000e47d  mov     [rsp+1090h+var_1060], 1
0x14000e485  mov     r8d, r9d
0x14000e488  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000e48c  call    wil_details_NtUpdateWnfStateData
0x14000e491  mov     esi, eax
0x14000e493  cmp     esi, 0C0000001h
0x14000e499  jnz     short loc_14000E4AC
0x14000e49b  inc     r15d
0x14000e49e  cmp     r15d, 64h ; 'd'
0x14000e4a2  jge     short loc_14000E4AC
0x14000e4a4  test    edi, edi
0x14000e4a6  jz      loc_14000E2F2
0x14000e4ac  test    ebx, ebx
0x14000e4ae  cmovz   ebx, esi
0x14000e4b1  mov     eax, ebx
0x14000e4b3  mov     rcx, [rbp+0F90h+var_40]
0x14000e4ba  xor     rcx, rsp; StackCookie
0x14000e4bd  call    __security_check_cookie
0x14000e4c2  add     rsp, 1068h
0x14000e4c9  pop     r15
0x14000e4cb  pop     r14
0x14000e4cd  pop     rdi
0x14000e4ce  pop     rsi
0x14000e4cf  pop     rbx
0x14000e4d0  pop     rbp
0x14000e4d1  retn
0x14000e4d2  mov     eax, [r8+8]
0x14000e4d6  add     [rcx+8], eax
0x14000e4d9  mov     r9d, [rsp+1090h+var_1050]
0x14000e4de  jmp     short loc_14000E464
```
