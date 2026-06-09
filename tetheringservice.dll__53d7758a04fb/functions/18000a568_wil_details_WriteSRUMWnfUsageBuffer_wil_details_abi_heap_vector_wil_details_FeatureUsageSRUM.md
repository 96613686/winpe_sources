# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000a568`
- end: `0x18000a7a0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800038b0`

## callees

- `0x180002590`
- `0x180003088`
- `0x18000a568`
- `0x18000aa30`
- `0x180031580`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a5f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a5f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a608`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a608`

## string_xrefs

- `0x18000a5ea`: `ntdll.dll`

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
0x18000a568  push    rbp
0x18000a56a  push    rbx
0x18000a56b  push    rsi
0x18000a56c  push    rdi
0x18000a56d  push    r14
0x18000a56f  push    r15
0x18000a571  lea     rbp, [rsp-0F68h]
0x18000a579  mov     eax, 1068h
0x18000a57e  call    _alloca_probe
0x18000a583  sub     rsp, rax
0x18000a586  mov     rax, cs:__security_cookie
0x18000a58d  xor     rax, rsp
0x18000a590  mov     [rbp+0F90h+var_40], rax
0x18000a597  mov     rax, [rcx+8]
0x18000a59b  xor     ebx, ebx
0x18000a59d  sub     rax, [rcx]
0x18000a5a0  xor     esi, esi
0x18000a5a2  mov     r14, rcx
0x18000a5a5  cmp     rax, 0Ch
0x18000a5a9  jb      loc_18000A76C
0x18000a5af  xor     r15d, r15d
0x18000a5b2  xor     edx, edx; Val
0x18000a5b4  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000a5b9  mov     r8d, 1000h; Size
0x18000a5bf  call    memset_0
0x18000a5c4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000a5cc  mov     [rsp+1090h+var_1050], 1000h
0x18000a5d4  mov     [rsp+1090h+var_104C], 0
0x18000a5dc  jnz     short loc_18000A626
0x18000a5de  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a5e5  test    rax, rax
0x18000a5e8  jnz     short loc_18000A5FE
0x18000a5ea  lea     rcx, ModuleName; "ntdll.dll"
0x18000a5f1  call    cs:__imp_GetModuleHandleW
0x18000a5f7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a5fe  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000a605  mov     rcx, rax; hModule
0x18000a608  call    cs:__imp_GetProcAddress
0x18000a60e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000a615  test    rax, rax
0x18000a618  jnz     short loc_18000A626
0x18000a61a  mov     edi, 0C0000139h
0x18000a61f  mov     ebx, edi
0x18000a621  jmp     loc_18000A753
0x18000a626  lea     rax, [rsp+1090h+var_1050]
0x18000a62b  xor     r8d, r8d
0x18000a62e  mov     [rsp+1090h+var_1068], rax
0x18000a633  lea     r9, [rsp+1090h+var_104C]
0x18000a638  lea     rax, [rsp+1090h+var_1040]
0x18000a63d  xor     edx, edx
0x18000a63f  mov     [rsp+1090h+var_1070], rax
0x18000a644  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a64b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000a652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a657  mov     ebx, eax
0x18000a659  mov     edi, eax
0x18000a65b  test    eax, eax
0x18000a65d  jnz     loc_18000A753
0x18000a663  mov     r9d, [rsp+1090h+var_1050]
0x18000a668  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000a672  mov     rax, r11
0x18000a675  mul     r9
0x18000a678  shr     rdx, 3
0x18000a67c  lea     rcx, [rdx+rdx*2]
0x18000a680  shl     rcx, 2
0x18000a684  cmp     r9, rcx
0x18000a687  jz      short loc_18000A691
0x18000a689  xor     r9d, r9d
0x18000a68c  mov     [rsp+1090h+var_1050], r9d
0x18000a691  mov     r8, [r14]
0x18000a694  mov     rax, r11
0x18000a697  mov     ecx, r9d
0x18000a69a  mul     rcx
0x18000a69d  mov     rcx, [r14+8]
0x18000a6a1  mov     rax, r11
0x18000a6a4  mov     r10, rdx
0x18000a6a7  sub     rcx, r8
0x18000a6aa  mul     rcx
0x18000a6ad  shr     r10, 3
0x18000a6b1  shr     rdx, 3
0x18000a6b5  lea     rax, [rdx+rdx*2]
0x18000a6b9  lea     rsi, [r8+rax*4]
0x18000a6bd  jmp     short loc_18000A728
0x18000a6bf  mov     eax, r10d
0x18000a6c2  lea     rcx, [rax+rax*2]
0x18000a6c6  lea     rdx, [rdx+rcx*4]
0x18000a6ca  lea     rax, [rsp+1090h+var_1040]
0x18000a6cf  cmp     rax, rdx
0x18000a6d2  jz      short loc_18000A6F9
0x18000a6d4  mov     r11d, [r8]
0x18000a6d7  lea     rcx, [rsp+1090h+var_1040]
0x18000a6dc  cmp     [rcx], r11d
0x18000a6df  jnz     short loc_18000A6F0
0x18000a6e1  movzx   eax, word ptr [r8+4]
0x18000a6e6  cmp     [rcx+4], ax
0x18000a6ea  jz      loc_18000A792
0x18000a6f0  add     rcx, 0Ch
0x18000a6f4  cmp     rcx, rdx
0x18000a6f7  jnz     short loc_18000A6DC
0x18000a6f9  mov     eax, r9d
0x18000a6fc  add     rax, 0Ch
0x18000a700  cmp     rax, 1000h
0x18000a706  ja      short loc_18000A724
0x18000a708  movsd   xmm0, qword ptr [r8]
0x18000a70d  add     r9d, 0Ch
0x18000a711  movsd   qword ptr [rdx], xmm0
0x18000a715  inc     r10d
0x18000a718  mov     eax, [r8+8]
0x18000a71c  mov     [rdx+8], eax
0x18000a71f  mov     [rsp+1090h+var_1050], r9d
0x18000a724  add     r8, 0Ch
0x18000a728  lea     rdx, [rsp+1090h+var_1040]
0x18000a72d  cmp     r8, rsi
0x18000a730  jnz     short loc_18000A6BF
0x18000a732  mov     eax, [rsp+1090h+var_104C]
0x18000a736  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a73d  mov     [rsp+1090h+var_1060], 1
0x18000a745  mov     r8d, r9d
0x18000a748  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000a74c  call    wil_details_NtUpdateWnfStateData
0x18000a751  mov     esi, eax
0x18000a753  cmp     esi, 0C0000001h
0x18000a759  jnz     short loc_18000A76C
0x18000a75b  inc     r15d
0x18000a75e  cmp     r15d, 64h ; 'd'
0x18000a762  jge     short loc_18000A76C
0x18000a764  test    edi, edi
0x18000a766  jz      loc_18000A5B2
0x18000a76c  test    ebx, ebx
0x18000a76e  cmovz   ebx, esi
0x18000a771  mov     eax, ebx
0x18000a773  mov     rcx, [rbp+0F90h+var_40]
0x18000a77a  xor     rcx, rsp; StackCookie
0x18000a77d  call    __security_check_cookie
0x18000a782  add     rsp, 1068h
0x18000a789  pop     r15
0x18000a78b  pop     r14
0x18000a78d  pop     rdi
0x18000a78e  pop     rsi
0x18000a78f  pop     rbx
0x18000a790  pop     rbp
0x18000a791  retn
0x18000a792  mov     eax, [r8+8]
0x18000a796  add     [rcx+8], eax
0x18000a799  mov     r9d, [rsp+1090h+var_1050]
0x18000a79e  jmp     short loc_18000A724
```
