# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000cb98`
- end: `0x18000cdd0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002c10`

## callees

- `0x180001e40`
- `0x1800028b4`
- `0x18000cb98`
- `0x18000d718`
- `0x180019850`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cc21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cc21`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cc38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cc38`

## string_xrefs

- `0x18000cc1a`: `ntdll.dll`

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
0x18000cb98  push    rbp
0x18000cb9a  push    rbx
0x18000cb9b  push    rsi
0x18000cb9c  push    rdi
0x18000cb9d  push    r14
0x18000cb9f  push    r15
0x18000cba1  lea     rbp, [rsp-0F68h]
0x18000cba9  mov     eax, 1068h
0x18000cbae  call    _alloca_probe
0x18000cbb3  sub     rsp, rax
0x18000cbb6  mov     rax, cs:__security_cookie
0x18000cbbd  xor     rax, rsp
0x18000cbc0  mov     [rbp+0F90h+var_40], rax
0x18000cbc7  mov     rax, [rcx+8]
0x18000cbcb  xor     ebx, ebx
0x18000cbcd  sub     rax, [rcx]
0x18000cbd0  xor     esi, esi
0x18000cbd2  mov     r14, rcx
0x18000cbd5  cmp     rax, 0Ch
0x18000cbd9  jb      loc_18000CD9C
0x18000cbdf  xor     r15d, r15d
0x18000cbe2  xor     edx, edx; Val
0x18000cbe4  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000cbe9  mov     r8d, 1000h; Size
0x18000cbef  call    memset_0
0x18000cbf4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000cbfc  mov     [rsp+1090h+var_1050], 1000h
0x18000cc04  mov     [rsp+1090h+var_104C], 0
0x18000cc0c  jnz     short loc_18000CC56
0x18000cc0e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cc15  test    rax, rax
0x18000cc18  jnz     short loc_18000CC2E
0x18000cc1a  lea     rcx, ModuleName; "ntdll.dll"
0x18000cc21  call    cs:__imp_GetModuleHandleW
0x18000cc27  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cc2e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000cc35  mov     rcx, rax; hModule
0x18000cc38  call    cs:__imp_GetProcAddress
0x18000cc3e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000cc45  test    rax, rax
0x18000cc48  jnz     short loc_18000CC56
0x18000cc4a  mov     edi, 0C0000139h
0x18000cc4f  mov     ebx, edi
0x18000cc51  jmp     loc_18000CD83
0x18000cc56  lea     rax, [rsp+1090h+var_1050]
0x18000cc5b  xor     r8d, r8d
0x18000cc5e  mov     [rsp+1090h+var_1068], rax
0x18000cc63  lea     r9, [rsp+1090h+var_104C]
0x18000cc68  lea     rax, [rsp+1090h+var_1040]
0x18000cc6d  xor     edx, edx
0x18000cc6f  mov     [rsp+1090h+var_1070], rax
0x18000cc74  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000cc7b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000cc82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc87  mov     ebx, eax
0x18000cc89  mov     edi, eax
0x18000cc8b  test    eax, eax
0x18000cc8d  jnz     loc_18000CD83
0x18000cc93  mov     r9d, [rsp+1090h+var_1050]
0x18000cc98  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000cca2  mov     rax, r11
0x18000cca5  mul     r9
0x18000cca8  shr     rdx, 3
0x18000ccac  lea     rcx, [rdx+rdx*2]
0x18000ccb0  shl     rcx, 2
0x18000ccb4  cmp     r9, rcx
0x18000ccb7  jz      short loc_18000CCC1
0x18000ccb9  xor     r9d, r9d
0x18000ccbc  mov     [rsp+1090h+var_1050], r9d
0x18000ccc1  mov     r8, [r14]
0x18000ccc4  mov     rax, r11
0x18000ccc7  mov     ecx, r9d
0x18000ccca  mul     rcx
0x18000cccd  mov     rcx, [r14+8]
0x18000ccd1  mov     rax, r11
0x18000ccd4  mov     r10, rdx
0x18000ccd7  sub     rcx, r8
0x18000ccda  mul     rcx
0x18000ccdd  shr     r10, 3
0x18000cce1  shr     rdx, 3
0x18000cce5  lea     rax, [rdx+rdx*2]
0x18000cce9  lea     rsi, [r8+rax*4]
0x18000cced  jmp     short loc_18000CD58
0x18000ccef  mov     eax, r10d
0x18000ccf2  lea     rcx, [rax+rax*2]
0x18000ccf6  lea     rdx, [rdx+rcx*4]
0x18000ccfa  lea     rax, [rsp+1090h+var_1040]
0x18000ccff  cmp     rax, rdx
0x18000cd02  jz      short loc_18000CD29
0x18000cd04  mov     r11d, [r8]
0x18000cd07  lea     rcx, [rsp+1090h+var_1040]
0x18000cd0c  cmp     [rcx], r11d
0x18000cd0f  jnz     short loc_18000CD20
0x18000cd11  movzx   eax, word ptr [r8+4]
0x18000cd16  cmp     [rcx+4], ax
0x18000cd1a  jz      loc_18000CDC2
0x18000cd20  add     rcx, 0Ch
0x18000cd24  cmp     rcx, rdx
0x18000cd27  jnz     short loc_18000CD0C
0x18000cd29  mov     eax, r9d
0x18000cd2c  add     rax, 0Ch
0x18000cd30  cmp     rax, 1000h
0x18000cd36  ja      short loc_18000CD54
0x18000cd38  movsd   xmm0, qword ptr [r8]
0x18000cd3d  add     r9d, 0Ch
0x18000cd41  movsd   qword ptr [rdx], xmm0
0x18000cd45  inc     r10d
0x18000cd48  mov     eax, [r8+8]
0x18000cd4c  mov     [rdx+8], eax
0x18000cd4f  mov     [rsp+1090h+var_1050], r9d
0x18000cd54  add     r8, 0Ch
0x18000cd58  lea     rdx, [rsp+1090h+var_1040]
0x18000cd5d  cmp     r8, rsi
0x18000cd60  jnz     short loc_18000CCEF
0x18000cd62  mov     eax, [rsp+1090h+var_104C]
0x18000cd66  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000cd6d  mov     [rsp+1090h+var_1060], 1
0x18000cd75  mov     r8d, r9d
0x18000cd78  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000cd7c  call    wil_details_NtUpdateWnfStateData
0x18000cd81  mov     esi, eax
0x18000cd83  cmp     esi, 0C0000001h
0x18000cd89  jnz     short loc_18000CD9C
0x18000cd8b  inc     r15d
0x18000cd8e  cmp     r15d, 64h ; 'd'
0x18000cd92  jge     short loc_18000CD9C
0x18000cd94  test    edi, edi
0x18000cd96  jz      loc_18000CBE2
0x18000cd9c  test    ebx, ebx
0x18000cd9e  cmovz   ebx, esi
0x18000cda1  mov     eax, ebx
0x18000cda3  mov     rcx, [rbp+0F90h+var_40]
0x18000cdaa  xor     rcx, rsp; StackCookie
0x18000cdad  call    __security_check_cookie
0x18000cdb2  add     rsp, 1068h
0x18000cdb9  pop     r15
0x18000cdbb  pop     r14
0x18000cdbd  pop     rdi
0x18000cdbe  pop     rsi
0x18000cdbf  pop     rbx
0x18000cdc0  pop     rbp
0x18000cdc1  retn
0x18000cdc2  mov     eax, [r8+8]
0x18000cdc6  add     [rcx+8], eax
0x18000cdc9  mov     r9d, [rsp+1090h+var_1050]
0x18000cdce  jmp     short loc_18000CD54
```
