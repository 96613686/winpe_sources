# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000abe4`
- end: `0x14000ae1c`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1400082b0`

## callees

- `0x1400015a0`
- `0x140002254`
- `0x14000abe4`
- `0x14000afe4`
- `0x14000b180`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ac6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ac6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ac84`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ac84`

## string_xrefs

- `0x14000ac66`: `ntdll.dll`

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
0x14000abe4  push    rbp
0x14000abe6  push    rbx
0x14000abe7  push    rsi
0x14000abe8  push    rdi
0x14000abe9  push    r14
0x14000abeb  push    r15
0x14000abed  lea     rbp, [rsp-0F68h]
0x14000abf5  mov     eax, 1068h
0x14000abfa  call    _alloca_probe
0x14000abff  sub     rsp, rax
0x14000ac02  mov     rax, cs:__security_cookie
0x14000ac09  xor     rax, rsp
0x14000ac0c  mov     [rbp+0F90h+var_40], rax
0x14000ac13  mov     rax, [rcx+8]
0x14000ac17  xor     ebx, ebx
0x14000ac19  sub     rax, [rcx]
0x14000ac1c  xor     esi, esi
0x14000ac1e  mov     r14, rcx
0x14000ac21  cmp     rax, 0Ch
0x14000ac25  jb      loc_14000ADE8
0x14000ac2b  xor     r15d, r15d
0x14000ac2e  xor     edx, edx; Val
0x14000ac30  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000ac35  mov     r8d, 1000h; Size
0x14000ac3b  call    memset_0
0x14000ac40  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000ac48  mov     [rsp+1090h+var_1050], 1000h
0x14000ac50  mov     [rsp+1090h+var_104C], 0
0x14000ac58  jnz     short loc_14000ACA2
0x14000ac5a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ac61  test    rax, rax
0x14000ac64  jnz     short loc_14000AC7A
0x14000ac66  lea     rcx, ModuleName; "ntdll.dll"
0x14000ac6d  call    cs:__imp_GetModuleHandleW
0x14000ac73  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ac7a  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000ac81  mov     rcx, rax; hModule
0x14000ac84  call    cs:__imp_GetProcAddress
0x14000ac8a  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000ac91  test    rax, rax
0x14000ac94  jnz     short loc_14000ACA2
0x14000ac96  mov     edi, 0C0000139h
0x14000ac9b  mov     ebx, edi
0x14000ac9d  jmp     loc_14000ADCF
0x14000aca2  lea     rax, [rsp+1090h+var_1050]
0x14000aca7  xor     r8d, r8d
0x14000acaa  mov     [rsp+1090h+var_1068], rax
0x14000acaf  lea     r9, [rsp+1090h+var_104C]
0x14000acb4  lea     rax, [rsp+1090h+var_1040]
0x14000acb9  xor     edx, edx
0x14000acbb  mov     [rsp+1090h+var_1070], rax
0x14000acc0  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000acc7  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000acce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000acd3  mov     ebx, eax
0x14000acd5  mov     edi, eax
0x14000acd7  test    eax, eax
0x14000acd9  jnz     loc_14000ADCF
0x14000acdf  mov     r9d, [rsp+1090h+var_1050]
0x14000ace4  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000acee  mov     rax, r11
0x14000acf1  mul     r9
0x14000acf4  shr     rdx, 3
0x14000acf8  lea     rcx, [rdx+rdx*2]
0x14000acfc  shl     rcx, 2
0x14000ad00  cmp     r9, rcx
0x14000ad03  jz      short loc_14000AD0D
0x14000ad05  xor     r9d, r9d
0x14000ad08  mov     [rsp+1090h+var_1050], r9d
0x14000ad0d  mov     r8, [r14]
0x14000ad10  mov     rax, r11
0x14000ad13  mov     ecx, r9d
0x14000ad16  mul     rcx
0x14000ad19  mov     rcx, [r14+8]
0x14000ad1d  mov     rax, r11
0x14000ad20  mov     r10, rdx
0x14000ad23  sub     rcx, r8
0x14000ad26  mul     rcx
0x14000ad29  shr     r10, 3
0x14000ad2d  shr     rdx, 3
0x14000ad31  lea     rax, [rdx+rdx*2]
0x14000ad35  lea     rsi, [r8+rax*4]
0x14000ad39  jmp     short loc_14000ADA4
0x14000ad3b  mov     eax, r10d
0x14000ad3e  lea     rcx, [rax+rax*2]
0x14000ad42  lea     rdx, [rdx+rcx*4]
0x14000ad46  lea     rax, [rsp+1090h+var_1040]
0x14000ad4b  cmp     rax, rdx
0x14000ad4e  jz      short loc_14000AD75
0x14000ad50  mov     r11d, [r8]
0x14000ad53  lea     rcx, [rsp+1090h+var_1040]
0x14000ad58  cmp     [rcx], r11d
0x14000ad5b  jnz     short loc_14000AD6C
0x14000ad5d  movzx   eax, word ptr [r8+4]
0x14000ad62  cmp     [rcx+4], ax
0x14000ad66  jz      loc_14000AE0E
0x14000ad6c  add     rcx, 0Ch
0x14000ad70  cmp     rcx, rdx
0x14000ad73  jnz     short loc_14000AD58
0x14000ad75  mov     eax, r9d
0x14000ad78  add     rax, 0Ch
0x14000ad7c  cmp     rax, 1000h
0x14000ad82  ja      short loc_14000ADA0
0x14000ad84  movsd   xmm0, qword ptr [r8]
0x14000ad89  add     r9d, 0Ch
0x14000ad8d  movsd   qword ptr [rdx], xmm0
0x14000ad91  inc     r10d
0x14000ad94  mov     eax, [r8+8]
0x14000ad98  mov     [rdx+8], eax
0x14000ad9b  mov     [rsp+1090h+var_1050], r9d
0x14000ada0  add     r8, 0Ch
0x14000ada4  lea     rdx, [rsp+1090h+var_1040]
0x14000ada9  cmp     r8, rsi
0x14000adac  jnz     short loc_14000AD3B
0x14000adae  mov     eax, [rsp+1090h+var_104C]
0x14000adb2  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000adb9  mov     [rsp+1090h+var_1060], 1
0x14000adc1  mov     r8d, r9d
0x14000adc4  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000adc8  call    wil_details_NtUpdateWnfStateData
0x14000adcd  mov     esi, eax
0x14000adcf  cmp     esi, 0C0000001h
0x14000add5  jnz     short loc_14000ADE8
0x14000add7  inc     r15d
0x14000adda  cmp     r15d, 64h ; 'd'
0x14000adde  jge     short loc_14000ADE8
0x14000ade0  test    edi, edi
0x14000ade2  jz      loc_14000AC2E
0x14000ade8  test    ebx, ebx
0x14000adea  cmovz   ebx, esi
0x14000aded  mov     eax, ebx
0x14000adef  mov     rcx, [rbp+0F90h+var_40]
0x14000adf6  xor     rcx, rsp; StackCookie
0x14000adf9  call    __security_check_cookie
0x14000adfe  add     rsp, 1068h
0x14000ae05  pop     r15
0x14000ae07  pop     r14
0x14000ae09  pop     rdi
0x14000ae0a  pop     rsi
0x14000ae0b  pop     rbx
0x14000ae0c  pop     rbp
0x14000ae0d  retn
0x14000ae0e  mov     eax, [r8+8]
0x14000ae12  add     [rcx+8], eax
0x14000ae15  mov     r9d, [rsp+1090h+var_1050]
0x14000ae1a  jmp     short loc_14000ADA0
```
