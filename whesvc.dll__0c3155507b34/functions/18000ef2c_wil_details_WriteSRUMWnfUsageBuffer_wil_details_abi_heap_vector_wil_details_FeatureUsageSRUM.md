# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000ef2c`
- end: `0x18000f164`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000bc60`

## callees

- `0x1800032e0`
- `0x180003da4`
- `0x18000ef2c`
- `0x18000f360`
- `0x1800265e0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000efb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000efb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000efcc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000efcc`

## string_xrefs

- `0x18000efae`: `ntdll.dll`

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
0x18000ef2c  push    rbp
0x18000ef2e  push    rbx
0x18000ef2f  push    rsi
0x18000ef30  push    rdi
0x18000ef31  push    r14
0x18000ef33  push    r15
0x18000ef35  lea     rbp, [rsp-0F68h]
0x18000ef3d  mov     eax, 1068h
0x18000ef42  call    _alloca_probe
0x18000ef47  sub     rsp, rax
0x18000ef4a  mov     rax, cs:__security_cookie
0x18000ef51  xor     rax, rsp
0x18000ef54  mov     [rbp+0F90h+var_40], rax
0x18000ef5b  mov     rax, [rcx+8]
0x18000ef5f  xor     ebx, ebx
0x18000ef61  sub     rax, [rcx]
0x18000ef64  xor     esi, esi
0x18000ef66  mov     r14, rcx
0x18000ef69  cmp     rax, 0Ch
0x18000ef6d  jb      loc_18000F130
0x18000ef73  xor     r15d, r15d
0x18000ef76  xor     edx, edx; Val
0x18000ef78  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000ef7d  mov     r8d, 1000h; Size
0x18000ef83  call    memset_0
0x18000ef88  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000ef90  mov     [rsp+1090h+var_1050], 1000h
0x18000ef98  mov     [rsp+1090h+var_104C], 0
0x18000efa0  jnz     short loc_18000EFEA
0x18000efa2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000efa9  test    rax, rax
0x18000efac  jnz     short loc_18000EFC2
0x18000efae  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000efb5  call    cs:__imp_GetModuleHandleW
0x18000efbb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000efc2  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000efc9  mov     rcx, rax; hModule
0x18000efcc  call    cs:__imp_GetProcAddress
0x18000efd2  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000efd9  test    rax, rax
0x18000efdc  jnz     short loc_18000EFEA
0x18000efde  mov     edi, 0C0000139h
0x18000efe3  mov     ebx, edi
0x18000efe5  jmp     loc_18000F117
0x18000efea  lea     rax, [rsp+1090h+var_1050]
0x18000efef  xor     r8d, r8d
0x18000eff2  mov     [rsp+1090h+var_1068], rax
0x18000eff7  lea     r9, [rsp+1090h+var_104C]
0x18000effc  lea     rax, [rsp+1090h+var_1040]
0x18000f001  xor     edx, edx
0x18000f003  mov     [rsp+1090h+var_1070], rax
0x18000f008  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000f00f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000f016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f01b  mov     ebx, eax
0x18000f01d  mov     edi, eax
0x18000f01f  test    eax, eax
0x18000f021  jnz     loc_18000F117
0x18000f027  mov     r9d, [rsp+1090h+var_1050]
0x18000f02c  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000f036  mov     rax, r11
0x18000f039  mul     r9
0x18000f03c  shr     rdx, 3
0x18000f040  lea     rcx, [rdx+rdx*2]
0x18000f044  shl     rcx, 2
0x18000f048  cmp     r9, rcx
0x18000f04b  jz      short loc_18000F055
0x18000f04d  xor     r9d, r9d
0x18000f050  mov     [rsp+1090h+var_1050], r9d
0x18000f055  mov     r8, [r14]
0x18000f058  mov     rax, r11
0x18000f05b  mov     ecx, r9d
0x18000f05e  mul     rcx
0x18000f061  mov     rcx, [r14+8]
0x18000f065  mov     rax, r11
0x18000f068  mov     r10, rdx
0x18000f06b  sub     rcx, r8
0x18000f06e  mul     rcx
0x18000f071  shr     r10, 3
0x18000f075  shr     rdx, 3
0x18000f079  lea     rax, [rdx+rdx*2]
0x18000f07d  lea     rsi, [r8+rax*4]
0x18000f081  jmp     short loc_18000F0EC
0x18000f083  mov     eax, r10d
0x18000f086  lea     rcx, [rax+rax*2]
0x18000f08a  lea     rdx, [rdx+rcx*4]
0x18000f08e  lea     rax, [rsp+1090h+var_1040]
0x18000f093  cmp     rax, rdx
0x18000f096  jz      short loc_18000F0BD
0x18000f098  mov     r11d, [r8]
0x18000f09b  lea     rcx, [rsp+1090h+var_1040]
0x18000f0a0  cmp     [rcx], r11d
0x18000f0a3  jnz     short loc_18000F0B4
0x18000f0a5  movzx   eax, word ptr [r8+4]
0x18000f0aa  cmp     [rcx+4], ax
0x18000f0ae  jz      loc_18000F156
0x18000f0b4  add     rcx, 0Ch
0x18000f0b8  cmp     rcx, rdx
0x18000f0bb  jnz     short loc_18000F0A0
0x18000f0bd  mov     eax, r9d
0x18000f0c0  add     rax, 0Ch
0x18000f0c4  cmp     rax, 1000h
0x18000f0ca  ja      short loc_18000F0E8
0x18000f0cc  movsd   xmm0, qword ptr [r8]
0x18000f0d1  add     r9d, 0Ch
0x18000f0d5  movsd   qword ptr [rdx], xmm0
0x18000f0d9  inc     r10d
0x18000f0dc  mov     eax, [r8+8]
0x18000f0e0  mov     [rdx+8], eax
0x18000f0e3  mov     [rsp+1090h+var_1050], r9d
0x18000f0e8  add     r8, 0Ch
0x18000f0ec  lea     rdx, [rsp+1090h+var_1040]
0x18000f0f1  cmp     r8, rsi
0x18000f0f4  jnz     short loc_18000F083
0x18000f0f6  mov     eax, [rsp+1090h+var_104C]
0x18000f0fa  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000f101  mov     [rsp+1090h+var_1060], 1
0x18000f109  mov     r8d, r9d
0x18000f10c  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000f110  call    wil_details_NtUpdateWnfStateData
0x18000f115  mov     esi, eax
0x18000f117  cmp     esi, 0C0000001h
0x18000f11d  jnz     short loc_18000F130
0x18000f11f  inc     r15d
0x18000f122  cmp     r15d, 64h ; 'd'
0x18000f126  jge     short loc_18000F130
0x18000f128  test    edi, edi
0x18000f12a  jz      loc_18000EF76
0x18000f130  test    ebx, ebx
0x18000f132  cmovz   ebx, esi
0x18000f135  mov     eax, ebx
0x18000f137  mov     rcx, [rbp+0F90h+var_40]
0x18000f13e  xor     rcx, rsp; StackCookie
0x18000f141  call    __security_check_cookie
0x18000f146  add     rsp, 1068h
0x18000f14d  pop     r15
0x18000f14f  pop     r14
0x18000f151  pop     rdi
0x18000f152  pop     rsi
0x18000f153  pop     rbx
0x18000f154  pop     rbp
0x18000f155  retn
0x18000f156  mov     eax, [r8+8]
0x18000f15a  add     [rcx+8], eax
0x18000f15d  mov     r9d, [rsp+1090h+var_1050]
0x18000f162  jmp     short loc_18000F0E8
```
