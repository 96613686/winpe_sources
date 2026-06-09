# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000e09c`
- end: `0x18000e2d4`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000aa90`

## callees

- `0x1800026d0`
- `0x180003198`
- `0x18000e09c`
- `0x18000e2dc`
- `0x18000e400`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e125`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e125`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e13c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e13c`

## string_xrefs

- `0x18000e11e`: `ntdll.dll`

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
0x18000e09c  push    rbp
0x18000e09e  push    rbx
0x18000e09f  push    rsi
0x18000e0a0  push    rdi
0x18000e0a1  push    r14
0x18000e0a3  push    r15
0x18000e0a5  lea     rbp, [rsp-0F68h]
0x18000e0ad  mov     eax, 1068h
0x18000e0b2  call    _alloca_probe
0x18000e0b7  sub     rsp, rax
0x18000e0ba  mov     rax, cs:__security_cookie
0x18000e0c1  xor     rax, rsp
0x18000e0c4  mov     [rbp+0F90h+var_40], rax
0x18000e0cb  mov     rax, [rcx+8]
0x18000e0cf  xor     ebx, ebx
0x18000e0d1  sub     rax, [rcx]
0x18000e0d4  xor     esi, esi
0x18000e0d6  mov     r14, rcx
0x18000e0d9  cmp     rax, 0Ch
0x18000e0dd  jb      loc_18000E2A0
0x18000e0e3  xor     r15d, r15d
0x18000e0e6  xor     edx, edx; Val
0x18000e0e8  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000e0ed  mov     r8d, 1000h; Size
0x18000e0f3  call    memset_0
0x18000e0f8  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000e100  mov     [rsp+1090h+var_1050], 1000h
0x18000e108  mov     [rsp+1090h+var_104C], 0
0x18000e110  jnz     short loc_18000E15A
0x18000e112  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e119  test    rax, rax
0x18000e11c  jnz     short loc_18000E132
0x18000e11e  lea     rcx, ModuleName; "ntdll.dll"
0x18000e125  call    cs:__imp_GetModuleHandleW
0x18000e12b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e132  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000e139  mov     rcx, rax; hModule
0x18000e13c  call    cs:__imp_GetProcAddress
0x18000e142  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000e149  test    rax, rax
0x18000e14c  jnz     short loc_18000E15A
0x18000e14e  mov     edi, 0C0000139h
0x18000e153  mov     ebx, edi
0x18000e155  jmp     loc_18000E287
0x18000e15a  lea     rax, [rsp+1090h+var_1050]
0x18000e15f  xor     r8d, r8d
0x18000e162  mov     [rsp+1090h+var_1068], rax
0x18000e167  lea     r9, [rsp+1090h+var_104C]
0x18000e16c  lea     rax, [rsp+1090h+var_1040]
0x18000e171  xor     edx, edx
0x18000e173  mov     [rsp+1090h+var_1070], rax
0x18000e178  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000e17f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000e186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e18b  mov     ebx, eax
0x18000e18d  mov     edi, eax
0x18000e18f  test    eax, eax
0x18000e191  jnz     loc_18000E287
0x18000e197  mov     r9d, [rsp+1090h+var_1050]
0x18000e19c  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000e1a6  mov     rax, r11
0x18000e1a9  mul     r9
0x18000e1ac  shr     rdx, 3
0x18000e1b0  lea     rcx, [rdx+rdx*2]
0x18000e1b4  shl     rcx, 2
0x18000e1b8  cmp     r9, rcx
0x18000e1bb  jz      short loc_18000E1C5
0x18000e1bd  xor     r9d, r9d
0x18000e1c0  mov     [rsp+1090h+var_1050], r9d
0x18000e1c5  mov     r8, [r14]
0x18000e1c8  mov     rax, r11
0x18000e1cb  mov     ecx, r9d
0x18000e1ce  mul     rcx
0x18000e1d1  mov     rcx, [r14+8]
0x18000e1d5  mov     rax, r11
0x18000e1d8  mov     r10, rdx
0x18000e1db  sub     rcx, r8
0x18000e1de  mul     rcx
0x18000e1e1  shr     r10, 3
0x18000e1e5  shr     rdx, 3
0x18000e1e9  lea     rax, [rdx+rdx*2]
0x18000e1ed  lea     rsi, [r8+rax*4]
0x18000e1f1  jmp     short loc_18000E25C
0x18000e1f3  mov     eax, r10d
0x18000e1f6  lea     rcx, [rax+rax*2]
0x18000e1fa  lea     rdx, [rdx+rcx*4]
0x18000e1fe  lea     rax, [rsp+1090h+var_1040]
0x18000e203  cmp     rax, rdx
0x18000e206  jz      short loc_18000E22D
0x18000e208  mov     r11d, [r8]
0x18000e20b  lea     rcx, [rsp+1090h+var_1040]
0x18000e210  cmp     [rcx], r11d
0x18000e213  jnz     short loc_18000E224
0x18000e215  movzx   eax, word ptr [r8+4]
0x18000e21a  cmp     [rcx+4], ax
0x18000e21e  jz      loc_18000E2C6
0x18000e224  add     rcx, 0Ch
0x18000e228  cmp     rcx, rdx
0x18000e22b  jnz     short loc_18000E210
0x18000e22d  mov     eax, r9d
0x18000e230  add     rax, 0Ch
0x18000e234  cmp     rax, 1000h
0x18000e23a  ja      short loc_18000E258
0x18000e23c  movsd   xmm0, qword ptr [r8]
0x18000e241  add     r9d, 0Ch
0x18000e245  movsd   qword ptr [rdx], xmm0
0x18000e249  inc     r10d
0x18000e24c  mov     eax, [r8+8]
0x18000e250  mov     [rdx+8], eax
0x18000e253  mov     [rsp+1090h+var_1050], r9d
0x18000e258  add     r8, 0Ch
0x18000e25c  lea     rdx, [rsp+1090h+var_1040]
0x18000e261  cmp     r8, rsi
0x18000e264  jnz     short loc_18000E1F3
0x18000e266  mov     eax, [rsp+1090h+var_104C]
0x18000e26a  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000e271  mov     [rsp+1090h+var_1060], 1
0x18000e279  mov     r8d, r9d
0x18000e27c  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000e280  call    wil_details_NtUpdateWnfStateData
0x18000e285  mov     esi, eax
0x18000e287  cmp     esi, 0C0000001h
0x18000e28d  jnz     short loc_18000E2A0
0x18000e28f  inc     r15d
0x18000e292  cmp     r15d, 64h ; 'd'
0x18000e296  jge     short loc_18000E2A0
0x18000e298  test    edi, edi
0x18000e29a  jz      loc_18000E0E6
0x18000e2a0  test    ebx, ebx
0x18000e2a2  cmovz   ebx, esi
0x18000e2a5  mov     eax, ebx
0x18000e2a7  mov     rcx, [rbp+0F90h+var_40]
0x18000e2ae  xor     rcx, rsp; StackCookie
0x18000e2b1  call    __security_check_cookie
0x18000e2b6  add     rsp, 1068h
0x18000e2bd  pop     r15
0x18000e2bf  pop     r14
0x18000e2c1  pop     rdi
0x18000e2c2  pop     rsi
0x18000e2c3  pop     rbx
0x18000e2c4  pop     rbp
0x18000e2c5  retn
0x18000e2c6  mov     eax, [r8+8]
0x18000e2ca  add     [rcx+8], eax
0x18000e2cd  mov     r9d, [rsp+1090h+var_1050]
0x18000e2d2  jmp     short loc_18000E258
```
