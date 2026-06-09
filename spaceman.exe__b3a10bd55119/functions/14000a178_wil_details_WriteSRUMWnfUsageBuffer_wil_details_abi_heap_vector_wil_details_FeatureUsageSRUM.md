# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000a178`
- end: `0x14000a3b0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140004330`

## callees

- `0x14000a178`
- `0x14000a4b0`
- `0x14000d1be`
- `0x14000d1f0`
- `0x14000d280`
- `0x14000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a218`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a218`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a201`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a201`

## string_xrefs

- `0x14000a1fa`: `ntdll.dll`

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
0x14000a178  push    rbp
0x14000a17a  push    rbx
0x14000a17b  push    rsi
0x14000a17c  push    rdi
0x14000a17d  push    r14
0x14000a17f  push    r15
0x14000a181  lea     rbp, [rsp-0F68h]
0x14000a189  mov     eax, 1068h
0x14000a18e  call    _alloca_probe
0x14000a193  sub     rsp, rax
0x14000a196  mov     rax, cs:__security_cookie
0x14000a19d  xor     rax, rsp
0x14000a1a0  mov     [rbp+0F90h+var_40], rax
0x14000a1a7  mov     rax, [rcx+8]
0x14000a1ab  xor     ebx, ebx
0x14000a1ad  sub     rax, [rcx]
0x14000a1b0  xor     esi, esi
0x14000a1b2  mov     r14, rcx
0x14000a1b5  cmp     rax, 0Ch
0x14000a1b9  jb      loc_14000A37C
0x14000a1bf  xor     r15d, r15d
0x14000a1c2  xor     edx, edx; Val
0x14000a1c4  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000a1c9  mov     r8d, 1000h; Size
0x14000a1cf  call    memset_0
0x14000a1d4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000a1dc  mov     [rsp+1090h+var_1050], 1000h
0x14000a1e4  mov     [rsp+1090h+var_104C], 0
0x14000a1ec  jnz     short loc_14000A236
0x14000a1ee  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a1f5  test    rax, rax
0x14000a1f8  jnz     short loc_14000A20E
0x14000a1fa  lea     rcx, ModuleName; "ntdll.dll"
0x14000a201  call    cs:__imp_GetModuleHandleW
0x14000a207  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a20e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000a215  mov     rcx, rax; hModule
0x14000a218  call    cs:__imp_GetProcAddress
0x14000a21e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000a225  test    rax, rax
0x14000a228  jnz     short loc_14000A236
0x14000a22a  mov     edi, 0C0000139h
0x14000a22f  mov     ebx, edi
0x14000a231  jmp     loc_14000A363
0x14000a236  lea     rax, [rsp+1090h+var_1050]
0x14000a23b  xor     r8d, r8d
0x14000a23e  mov     [rsp+1090h+var_1068], rax
0x14000a243  lea     r9, [rsp+1090h+var_104C]
0x14000a248  lea     rax, [rsp+1090h+var_1040]
0x14000a24d  xor     edx, edx
0x14000a24f  mov     [rsp+1090h+var_1070], rax
0x14000a254  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000a25b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000a262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a267  mov     ebx, eax
0x14000a269  mov     edi, eax
0x14000a26b  test    eax, eax
0x14000a26d  jnz     loc_14000A363
0x14000a273  mov     r9d, [rsp+1090h+var_1050]
0x14000a278  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000a282  mov     rax, r11
0x14000a285  mul     r9
0x14000a288  shr     rdx, 3
0x14000a28c  lea     rcx, [rdx+rdx*2]
0x14000a290  shl     rcx, 2
0x14000a294  cmp     r9, rcx
0x14000a297  jz      short loc_14000A2A1
0x14000a299  xor     r9d, r9d
0x14000a29c  mov     [rsp+1090h+var_1050], r9d
0x14000a2a1  mov     r8, [r14]
0x14000a2a4  mov     rax, r11
0x14000a2a7  mov     ecx, r9d
0x14000a2aa  mul     rcx
0x14000a2ad  mov     rcx, [r14+8]
0x14000a2b1  mov     rax, r11
0x14000a2b4  mov     r10, rdx
0x14000a2b7  sub     rcx, r8
0x14000a2ba  mul     rcx
0x14000a2bd  shr     r10, 3
0x14000a2c1  shr     rdx, 3
0x14000a2c5  lea     rax, [rdx+rdx*2]
0x14000a2c9  lea     rsi, [r8+rax*4]
0x14000a2cd  jmp     short loc_14000A338
0x14000a2cf  mov     eax, r10d
0x14000a2d2  lea     rcx, [rax+rax*2]
0x14000a2d6  lea     rdx, [rdx+rcx*4]
0x14000a2da  lea     rax, [rsp+1090h+var_1040]
0x14000a2df  cmp     rax, rdx
0x14000a2e2  jz      short loc_14000A309
0x14000a2e4  mov     r11d, [r8]
0x14000a2e7  lea     rcx, [rsp+1090h+var_1040]
0x14000a2ec  cmp     [rcx], r11d
0x14000a2ef  jnz     short loc_14000A300
0x14000a2f1  movzx   eax, word ptr [r8+4]
0x14000a2f6  cmp     [rcx+4], ax
0x14000a2fa  jz      loc_14000A3A2
0x14000a300  add     rcx, 0Ch
0x14000a304  cmp     rcx, rdx
0x14000a307  jnz     short loc_14000A2EC
0x14000a309  mov     eax, r9d
0x14000a30c  add     rax, 0Ch
0x14000a310  cmp     rax, 1000h
0x14000a316  ja      short loc_14000A334
0x14000a318  movsd   xmm0, qword ptr [r8]
0x14000a31d  add     r9d, 0Ch
0x14000a321  movsd   qword ptr [rdx], xmm0
0x14000a325  inc     r10d
0x14000a328  mov     eax, [r8+8]
0x14000a32c  mov     [rdx+8], eax
0x14000a32f  mov     [rsp+1090h+var_1050], r9d
0x14000a334  add     r8, 0Ch
0x14000a338  lea     rdx, [rsp+1090h+var_1040]
0x14000a33d  cmp     r8, rsi
0x14000a340  jnz     short loc_14000A2CF
0x14000a342  mov     eax, [rsp+1090h+var_104C]
0x14000a346  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000a34d  mov     [rsp+1090h+var_1060], 1
0x14000a355  mov     r8d, r9d
0x14000a358  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000a35c  call    wil_details_NtUpdateWnfStateData
0x14000a361  mov     esi, eax
0x14000a363  cmp     esi, 0C0000001h
0x14000a369  jnz     short loc_14000A37C
0x14000a36b  inc     r15d
0x14000a36e  cmp     r15d, 64h ; 'd'
0x14000a372  jge     short loc_14000A37C
0x14000a374  test    edi, edi
0x14000a376  jz      loc_14000A1C2
0x14000a37c  test    ebx, ebx
0x14000a37e  cmovz   ebx, esi
0x14000a381  mov     eax, ebx
0x14000a383  mov     rcx, [rbp+0F90h+var_40]
0x14000a38a  xor     rcx, rsp; StackCookie
0x14000a38d  call    __security_check_cookie
0x14000a392  add     rsp, 1068h
0x14000a399  pop     r15
0x14000a39b  pop     r14
0x14000a39d  pop     rdi
0x14000a39e  pop     rsi
0x14000a39f  pop     rbx
0x14000a3a0  pop     rbp
0x14000a3a1  retn
0x14000a3a2  mov     eax, [r8+8]
0x14000a3a6  add     [rcx+8], eax
0x14000a3a9  mov     r9d, [rsp+1090h+var_1050]
0x14000a3ae  jmp     short loc_14000A334
```
