# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180008558`
- end: `0x180008790`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002760`

## callees

- `0x180008558`
- `0x180008990`
- `0x18002170a`
- `0x180021740`
- `0x1800217d0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800085e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800085e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800085f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800085f8`

## string_xrefs

- `0x1800085da`: `ntdll.dll`

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
0x180008558  push    rbp
0x18000855a  push    rbx
0x18000855b  push    rsi
0x18000855c  push    rdi
0x18000855d  push    r14
0x18000855f  push    r15
0x180008561  lea     rbp, [rsp-0F68h]
0x180008569  mov     eax, 1068h
0x18000856e  call    _alloca_probe
0x180008573  sub     rsp, rax
0x180008576  mov     rax, cs:__security_cookie
0x18000857d  xor     rax, rsp
0x180008580  mov     [rbp+0F90h+var_40], rax
0x180008587  mov     rax, [rcx+8]
0x18000858b  xor     ebx, ebx
0x18000858d  sub     rax, [rcx]
0x180008590  xor     esi, esi
0x180008592  mov     r14, rcx
0x180008595  cmp     rax, 0Ch
0x180008599  jb      loc_18000875C
0x18000859f  xor     r15d, r15d
0x1800085a2  xor     edx, edx; Val
0x1800085a4  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800085a9  mov     r8d, 1000h; Size
0x1800085af  call    memset_0
0x1800085b4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1800085bc  mov     [rsp+1090h+var_1050], 1000h
0x1800085c4  mov     [rsp+1090h+var_104C], 0
0x1800085cc  jnz     short loc_180008616
0x1800085ce  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800085d5  test    rax, rax
0x1800085d8  jnz     short loc_1800085EE
0x1800085da  lea     rcx, ModuleName; "ntdll.dll"
0x1800085e1  call    cs:__imp_GetModuleHandleW
0x1800085e7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800085ee  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800085f5  mov     rcx, rax; hModule
0x1800085f8  call    cs:__imp_GetProcAddress
0x1800085fe  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008605  test    rax, rax
0x180008608  jnz     short loc_180008616
0x18000860a  mov     edi, 0C0000139h
0x18000860f  mov     ebx, edi
0x180008611  jmp     loc_180008743
0x180008616  lea     rax, [rsp+1090h+var_1050]
0x18000861b  xor     r8d, r8d
0x18000861e  mov     [rsp+1090h+var_1068], rax
0x180008623  lea     r9, [rsp+1090h+var_104C]
0x180008628  lea     rax, [rsp+1090h+var_1040]
0x18000862d  xor     edx, edx
0x18000862f  mov     [rsp+1090h+var_1070], rax
0x180008634  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000863b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008647  mov     ebx, eax
0x180008649  mov     edi, eax
0x18000864b  test    eax, eax
0x18000864d  jnz     loc_180008743
0x180008653  mov     r9d, [rsp+1090h+var_1050]
0x180008658  mov     r11, 0AAAAAAAAAAAAAAABh
0x180008662  mov     rax, r11
0x180008665  mul     r9
0x180008668  shr     rdx, 3
0x18000866c  lea     rcx, [rdx+rdx*2]
0x180008670  shl     rcx, 2
0x180008674  cmp     r9, rcx
0x180008677  jz      short loc_180008681
0x180008679  xor     r9d, r9d
0x18000867c  mov     [rsp+1090h+var_1050], r9d
0x180008681  mov     r8, [r14]
0x180008684  mov     rax, r11
0x180008687  mov     ecx, r9d
0x18000868a  mul     rcx
0x18000868d  mov     rcx, [r14+8]
0x180008691  mov     rax, r11
0x180008694  mov     r10, rdx
0x180008697  sub     rcx, r8
0x18000869a  mul     rcx
0x18000869d  shr     r10, 3
0x1800086a1  shr     rdx, 3
0x1800086a5  lea     rax, [rdx+rdx*2]
0x1800086a9  lea     rsi, [r8+rax*4]
0x1800086ad  jmp     short loc_180008718
0x1800086af  mov     eax, r10d
0x1800086b2  lea     rcx, [rax+rax*2]
0x1800086b6  lea     rdx, [rdx+rcx*4]
0x1800086ba  lea     rax, [rsp+1090h+var_1040]
0x1800086bf  cmp     rax, rdx
0x1800086c2  jz      short loc_1800086E9
0x1800086c4  mov     r11d, [r8]
0x1800086c7  lea     rcx, [rsp+1090h+var_1040]
0x1800086cc  cmp     [rcx], r11d
0x1800086cf  jnz     short loc_1800086E0
0x1800086d1  movzx   eax, word ptr [r8+4]
0x1800086d6  cmp     [rcx+4], ax
0x1800086da  jz      loc_180008782
0x1800086e0  add     rcx, 0Ch
0x1800086e4  cmp     rcx, rdx
0x1800086e7  jnz     short loc_1800086CC
0x1800086e9  mov     eax, r9d
0x1800086ec  add     rax, 0Ch
0x1800086f0  cmp     rax, 1000h
0x1800086f6  ja      short loc_180008714
0x1800086f8  movsd   xmm0, qword ptr [r8]
0x1800086fd  add     r9d, 0Ch
0x180008701  movsd   qword ptr [rdx], xmm0
0x180008705  inc     r10d
0x180008708  mov     eax, [r8+8]
0x18000870c  mov     [rdx+8], eax
0x18000870f  mov     [rsp+1090h+var_1050], r9d
0x180008714  add     r8, 0Ch
0x180008718  lea     rdx, [rsp+1090h+var_1040]
0x18000871d  cmp     r8, rsi
0x180008720  jnz     short loc_1800086AF
0x180008722  mov     eax, [rsp+1090h+var_104C]
0x180008726  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000872d  mov     [rsp+1090h+var_1060], 1
0x180008735  mov     r8d, r9d
0x180008738  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000873c  call    wil_details_NtUpdateWnfStateData
0x180008741  mov     esi, eax
0x180008743  cmp     esi, 0C0000001h
0x180008749  jnz     short loc_18000875C
0x18000874b  inc     r15d
0x18000874e  cmp     r15d, 64h ; 'd'
0x180008752  jge     short loc_18000875C
0x180008754  test    edi, edi
0x180008756  jz      loc_1800085A2
0x18000875c  test    ebx, ebx
0x18000875e  cmovz   ebx, esi
0x180008761  mov     eax, ebx
0x180008763  mov     rcx, [rbp+0F90h+var_40]
0x18000876a  xor     rcx, rsp; StackCookie
0x18000876d  call    __security_check_cookie
0x180008772  add     rsp, 1068h
0x180008779  pop     r15
0x18000877b  pop     r14
0x18000877d  pop     rdi
0x18000877e  pop     rsi
0x18000877f  pop     rbx
0x180008780  pop     rbp
0x180008781  retn
0x180008782  mov     eax, [r8+8]
0x180008786  add     [rcx+8], eax
0x180008789  mov     r9d, [rsp+1090h+var_1050]
0x18000878e  jmp     short loc_180008714
```
