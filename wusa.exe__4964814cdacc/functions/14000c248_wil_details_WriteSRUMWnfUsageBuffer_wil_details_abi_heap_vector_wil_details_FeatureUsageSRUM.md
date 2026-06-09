# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000c248`
- end: `0x14000c480`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140004a30`

## callees

- `0x140001a63`
- `0x14000c248`
- `0x14000cec0`
- `0x140014910`
- `0x1400149a0`
- `0x140015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000c2e8`
- `KERNEL32!GetProcAddress` at `0x14000c2e8`
- `KERNEL32!GetModuleHandleW` at `0x14000c2d1`
- `KERNEL32!GetModuleHandleW` at `0x14000c2d1`

## string_xrefs

- `0x14000c2ca`: `ntdll.dll`

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
0x14000c248  push    rbp
0x14000c24a  push    rbx
0x14000c24b  push    rsi
0x14000c24c  push    rdi
0x14000c24d  push    r14
0x14000c24f  push    r15
0x14000c251  lea     rbp, [rsp-0F68h]
0x14000c259  mov     eax, 1068h
0x14000c25e  call    _alloca_probe
0x14000c263  sub     rsp, rax
0x14000c266  mov     rax, cs:__security_cookie
0x14000c26d  xor     rax, rsp
0x14000c270  mov     [rbp+0F90h+var_40], rax
0x14000c277  mov     rax, [rcx+8]
0x14000c27b  xor     ebx, ebx
0x14000c27d  sub     rax, [rcx]
0x14000c280  xor     esi, esi
0x14000c282  mov     r14, rcx
0x14000c285  cmp     rax, 0Ch
0x14000c289  jb      loc_14000C44C
0x14000c28f  xor     r15d, r15d
0x14000c292  xor     edx, edx; Val
0x14000c294  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000c299  mov     r8d, 1000h; Size
0x14000c29f  call    memset_0
0x14000c2a4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000c2ac  mov     [rsp+1090h+var_1050], 1000h
0x14000c2b4  mov     [rsp+1090h+var_104C], 0
0x14000c2bc  jnz     short loc_14000C306
0x14000c2be  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c2c5  test    rax, rax
0x14000c2c8  jnz     short loc_14000C2DE
0x14000c2ca  lea     rcx, ModuleName; "ntdll.dll"
0x14000c2d1  call    cs:__imp_GetModuleHandleW
0x14000c2d7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c2de  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000c2e5  mov     rcx, rax; hModule
0x14000c2e8  call    cs:__imp_GetProcAddress
0x14000c2ee  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000c2f5  test    rax, rax
0x14000c2f8  jnz     short loc_14000C306
0x14000c2fa  mov     edi, 0C0000139h
0x14000c2ff  mov     ebx, edi
0x14000c301  jmp     loc_14000C433
0x14000c306  lea     rax, [rsp+1090h+var_1050]
0x14000c30b  xor     r8d, r8d
0x14000c30e  mov     [rsp+1090h+var_1068], rax
0x14000c313  lea     r9, [rsp+1090h+var_104C]
0x14000c318  lea     rax, [rsp+1090h+var_1040]
0x14000c31d  xor     edx, edx
0x14000c31f  mov     [rsp+1090h+var_1070], rax
0x14000c324  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000c32b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000c332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c337  mov     ebx, eax
0x14000c339  mov     edi, eax
0x14000c33b  test    eax, eax
0x14000c33d  jnz     loc_14000C433
0x14000c343  mov     r9d, [rsp+1090h+var_1050]
0x14000c348  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000c352  mov     rax, r11
0x14000c355  mul     r9
0x14000c358  shr     rdx, 3
0x14000c35c  lea     rcx, [rdx+rdx*2]
0x14000c360  shl     rcx, 2
0x14000c364  cmp     r9, rcx
0x14000c367  jz      short loc_14000C371
0x14000c369  xor     r9d, r9d
0x14000c36c  mov     [rsp+1090h+var_1050], r9d
0x14000c371  mov     r8, [r14]
0x14000c374  mov     rax, r11
0x14000c377  mov     ecx, r9d
0x14000c37a  mul     rcx
0x14000c37d  mov     rcx, [r14+8]
0x14000c381  mov     rax, r11
0x14000c384  mov     r10, rdx
0x14000c387  sub     rcx, r8
0x14000c38a  mul     rcx
0x14000c38d  shr     r10, 3
0x14000c391  shr     rdx, 3
0x14000c395  lea     rax, [rdx+rdx*2]
0x14000c399  lea     rsi, [r8+rax*4]
0x14000c39d  jmp     short loc_14000C408
0x14000c39f  mov     eax, r10d
0x14000c3a2  lea     rcx, [rax+rax*2]
0x14000c3a6  lea     rdx, [rdx+rcx*4]
0x14000c3aa  lea     rax, [rsp+1090h+var_1040]
0x14000c3af  cmp     rax, rdx
0x14000c3b2  jz      short loc_14000C3D9
0x14000c3b4  mov     r11d, [r8]
0x14000c3b7  lea     rcx, [rsp+1090h+var_1040]
0x14000c3bc  cmp     [rcx], r11d
0x14000c3bf  jnz     short loc_14000C3D0
0x14000c3c1  movzx   eax, word ptr [r8+4]
0x14000c3c6  cmp     [rcx+4], ax
0x14000c3ca  jz      loc_14000C472
0x14000c3d0  add     rcx, 0Ch
0x14000c3d4  cmp     rcx, rdx
0x14000c3d7  jnz     short loc_14000C3BC
0x14000c3d9  mov     eax, r9d
0x14000c3dc  add     rax, 0Ch
0x14000c3e0  cmp     rax, 1000h
0x14000c3e6  ja      short loc_14000C404
0x14000c3e8  movsd   xmm0, qword ptr [r8]
0x14000c3ed  add     r9d, 0Ch
0x14000c3f1  movsd   qword ptr [rdx], xmm0
0x14000c3f5  inc     r10d
0x14000c3f8  mov     eax, [r8+8]
0x14000c3fc  mov     [rdx+8], eax
0x14000c3ff  mov     [rsp+1090h+var_1050], r9d
0x14000c404  add     r8, 0Ch
0x14000c408  lea     rdx, [rsp+1090h+var_1040]
0x14000c40d  cmp     r8, rsi
0x14000c410  jnz     short loc_14000C39F
0x14000c412  mov     eax, [rsp+1090h+var_104C]
0x14000c416  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000c41d  mov     [rsp+1090h+var_1060], 1
0x14000c425  mov     r8d, r9d
0x14000c428  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000c42c  call    wil_details_NtUpdateWnfStateData
0x14000c431  mov     esi, eax
0x14000c433  cmp     esi, 0C0000001h
0x14000c439  jnz     short loc_14000C44C
0x14000c43b  inc     r15d
0x14000c43e  cmp     r15d, 64h ; 'd'
0x14000c442  jge     short loc_14000C44C
0x14000c444  test    edi, edi
0x14000c446  jz      loc_14000C292
0x14000c44c  test    ebx, ebx
0x14000c44e  cmovz   ebx, esi
0x14000c451  mov     eax, ebx
0x14000c453  mov     rcx, [rbp+0F90h+var_40]
0x14000c45a  xor     rcx, rsp; StackCookie
0x14000c45d  call    __security_check_cookie
0x14000c462  add     rsp, 1068h
0x14000c469  pop     r15
0x14000c46b  pop     r14
0x14000c46d  pop     rdi
0x14000c46e  pop     rsi
0x14000c46f  pop     rbx
0x14000c470  pop     rbp
0x14000c471  retn
0x14000c472  mov     eax, [r8+8]
0x14000c476  add     [rcx+8], eax
0x14000c479  mov     r9d, [rsp+1090h+var_1050]
0x14000c47e  jmp     short loc_14000C404
```
