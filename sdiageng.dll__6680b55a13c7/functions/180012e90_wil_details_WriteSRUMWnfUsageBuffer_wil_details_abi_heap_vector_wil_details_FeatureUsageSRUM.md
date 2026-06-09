# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180012e90`
- end: `0x1800130c8`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180008390`

## callees

- `0x180012e90`
- `0x180013264`
- `0x180029882`
- `0x1800298c0`
- `0x180029980`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180012f19`
- `KERNEL32!GetModuleHandleW` at `0x180012f19`
- `KERNEL32!GetProcAddress` at `0x180012f30`
- `KERNEL32!GetProcAddress` at `0x180012f30`

## string_xrefs

- `0x180012f12`: `ntdll.dll`

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
0x180012e90  push    rbp
0x180012e92  push    rbx
0x180012e93  push    rsi
0x180012e94  push    rdi
0x180012e95  push    r14
0x180012e97  push    r15
0x180012e99  lea     rbp, [rsp-0F68h]
0x180012ea1  mov     eax, 1068h
0x180012ea6  call    _alloca_probe
0x180012eab  sub     rsp, rax
0x180012eae  mov     rax, cs:__security_cookie
0x180012eb5  xor     rax, rsp
0x180012eb8  mov     [rbp+0F90h+var_40], rax
0x180012ebf  mov     rax, [rcx+8]
0x180012ec3  xor     ebx, ebx
0x180012ec5  sub     rax, [rcx]
0x180012ec8  xor     esi, esi
0x180012eca  mov     r14, rcx
0x180012ecd  cmp     rax, 0Ch
0x180012ed1  jb      loc_180013094
0x180012ed7  xor     r15d, r15d
0x180012eda  xor     edx, edx; Val
0x180012edc  lea     rcx, [rsp+1090h+var_1040]; void *
0x180012ee1  mov     r8d, 1000h; Size
0x180012ee7  call    memset_0
0x180012eec  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180012ef4  mov     [rsp+1090h+var_1050], 1000h
0x180012efc  mov     [rsp+1090h+var_104C], 0
0x180012f04  jnz     short loc_180012F4E
0x180012f06  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012f0d  test    rax, rax
0x180012f10  jnz     short loc_180012F26
0x180012f12  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180012f19  call    cs:__imp_GetModuleHandleW
0x180012f1f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012f26  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180012f2d  mov     rcx, rax; hModule
0x180012f30  call    cs:__imp_GetProcAddress
0x180012f36  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180012f3d  test    rax, rax
0x180012f40  jnz     short loc_180012F4E
0x180012f42  mov     edi, 0C0000139h
0x180012f47  mov     ebx, edi
0x180012f49  jmp     loc_18001307B
0x180012f4e  lea     rax, [rsp+1090h+var_1050]
0x180012f53  xor     r8d, r8d
0x180012f56  mov     [rsp+1090h+var_1068], rax
0x180012f5b  lea     r9, [rsp+1090h+var_104C]
0x180012f60  lea     rax, [rsp+1090h+var_1040]
0x180012f65  xor     edx, edx
0x180012f67  mov     [rsp+1090h+var_1070], rax
0x180012f6c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180012f73  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180012f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f7f  mov     ebx, eax
0x180012f81  mov     edi, eax
0x180012f83  test    eax, eax
0x180012f85  jnz     loc_18001307B
0x180012f8b  mov     r9d, [rsp+1090h+var_1050]
0x180012f90  mov     r11, 0AAAAAAAAAAAAAAABh
0x180012f9a  mov     rax, r11
0x180012f9d  mul     r9
0x180012fa0  shr     rdx, 3
0x180012fa4  lea     rcx, [rdx+rdx*2]
0x180012fa8  shl     rcx, 2
0x180012fac  cmp     r9, rcx
0x180012faf  jz      short loc_180012FB9
0x180012fb1  xor     r9d, r9d
0x180012fb4  mov     [rsp+1090h+var_1050], r9d
0x180012fb9  mov     r8, [r14]
0x180012fbc  mov     rax, r11
0x180012fbf  mov     ecx, r9d
0x180012fc2  mul     rcx
0x180012fc5  mov     rcx, [r14+8]
0x180012fc9  mov     rax, r11
0x180012fcc  mov     r10, rdx
0x180012fcf  sub     rcx, r8
0x180012fd2  mul     rcx
0x180012fd5  shr     r10, 3
0x180012fd9  shr     rdx, 3
0x180012fdd  lea     rax, [rdx+rdx*2]
0x180012fe1  lea     rsi, [r8+rax*4]
0x180012fe5  jmp     short loc_180013050
0x180012fe7  mov     eax, r10d
0x180012fea  lea     rcx, [rax+rax*2]
0x180012fee  lea     rdx, [rdx+rcx*4]
0x180012ff2  lea     rax, [rsp+1090h+var_1040]
0x180012ff7  cmp     rax, rdx
0x180012ffa  jz      short loc_180013021
0x180012ffc  mov     r11d, [r8]
0x180012fff  lea     rcx, [rsp+1090h+var_1040]
0x180013004  cmp     [rcx], r11d
0x180013007  jnz     short loc_180013018
0x180013009  movzx   eax, word ptr [r8+4]
0x18001300e  cmp     [rcx+4], ax
0x180013012  jz      loc_1800130BA
0x180013018  add     rcx, 0Ch
0x18001301c  cmp     rcx, rdx
0x18001301f  jnz     short loc_180013004
0x180013021  mov     eax, r9d
0x180013024  add     rax, 0Ch
0x180013028  cmp     rax, 1000h
0x18001302e  ja      short loc_18001304C
0x180013030  movsd   xmm0, qword ptr [r8]
0x180013035  add     r9d, 0Ch
0x180013039  movsd   qword ptr [rdx], xmm0
0x18001303d  inc     r10d
0x180013040  mov     eax, [r8+8]
0x180013044  mov     [rdx+8], eax
0x180013047  mov     [rsp+1090h+var_1050], r9d
0x18001304c  add     r8, 0Ch
0x180013050  lea     rdx, [rsp+1090h+var_1040]
0x180013055  cmp     r8, rsi
0x180013058  jnz     short loc_180012FE7
0x18001305a  mov     eax, [rsp+1090h+var_104C]
0x18001305e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180013065  mov     [rsp+1090h+var_1060], 1
0x18001306d  mov     r8d, r9d
0x180013070  mov     dword ptr [rsp+1090h+var_1068], eax
0x180013074  call    wil_details_NtUpdateWnfStateData
0x180013079  mov     esi, eax
0x18001307b  cmp     esi, 0C0000001h
0x180013081  jnz     short loc_180013094
0x180013083  inc     r15d
0x180013086  cmp     r15d, 64h ; 'd'
0x18001308a  jge     short loc_180013094
0x18001308c  test    edi, edi
0x18001308e  jz      loc_180012EDA
0x180013094  test    ebx, ebx
0x180013096  cmovz   ebx, esi
0x180013099  mov     eax, ebx
0x18001309b  mov     rcx, [rbp+0F90h+var_40]
0x1800130a2  xor     rcx, rsp; StackCookie
0x1800130a5  call    __security_check_cookie
0x1800130aa  add     rsp, 1068h
0x1800130b1  pop     r15
0x1800130b3  pop     r14
0x1800130b5  pop     rdi
0x1800130b6  pop     rsi
0x1800130b7  pop     rbx
0x1800130b8  pop     rbp
0x1800130b9  retn
0x1800130ba  mov     eax, [r8+8]
0x1800130be  add     [rcx+8], eax
0x1800130c1  mov     r9d, [rsp+1090h+var_1050]
0x1800130c6  jmp     short loc_18001304C
```
