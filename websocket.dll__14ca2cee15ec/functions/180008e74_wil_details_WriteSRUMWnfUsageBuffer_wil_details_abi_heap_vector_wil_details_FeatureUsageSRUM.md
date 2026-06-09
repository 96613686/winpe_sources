# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180008e74`
- end: `0x1800090ac`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002ac0`

## callees

- `0x180001670`
- `0x180001fa4`
- `0x180008e74`
- `0x1800092a0`
- `0x18000dba0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008efd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008efd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008f14`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008f14`

## string_xrefs

- `0x180008ef6`: `ntdll.dll`

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
0x180008e74  push    rbp
0x180008e76  push    rbx
0x180008e77  push    rsi
0x180008e78  push    rdi
0x180008e79  push    r14
0x180008e7b  push    r15
0x180008e7d  lea     rbp, [rsp-0F68h]
0x180008e85  mov     eax, 1068h
0x180008e8a  call    _alloca_probe
0x180008e8f  sub     rsp, rax
0x180008e92  mov     rax, cs:__security_cookie
0x180008e99  xor     rax, rsp
0x180008e9c  mov     [rbp+0F90h+var_40], rax
0x180008ea3  mov     rax, [rcx+8]
0x180008ea7  xor     ebx, ebx
0x180008ea9  sub     rax, [rcx]
0x180008eac  xor     esi, esi
0x180008eae  mov     r14, rcx
0x180008eb1  cmp     rax, 0Ch
0x180008eb5  jb      loc_180009078
0x180008ebb  xor     r15d, r15d
0x180008ebe  xor     edx, edx; Val
0x180008ec0  lea     rcx, [rsp+1090h+var_1040]; void *
0x180008ec5  mov     r8d, 1000h; Size
0x180008ecb  call    memset_0
0x180008ed0  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180008ed8  mov     [rsp+1090h+var_1050], 1000h
0x180008ee0  mov     [rsp+1090h+var_104C], 0
0x180008ee8  jnz     short loc_180008F32
0x180008eea  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008ef1  test    rax, rax
0x180008ef4  jnz     short loc_180008F0A
0x180008ef6  lea     rcx, ModuleName; "ntdll.dll"
0x180008efd  call    cs:__imp_GetModuleHandleW
0x180008f03  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008f0a  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008f11  mov     rcx, rax; hModule
0x180008f14  call    cs:__imp_GetProcAddress
0x180008f1a  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008f21  test    rax, rax
0x180008f24  jnz     short loc_180008F32
0x180008f26  mov     edi, 0C0000139h
0x180008f2b  mov     ebx, edi
0x180008f2d  jmp     loc_18000905F
0x180008f32  lea     rax, [rsp+1090h+var_1050]
0x180008f37  xor     r8d, r8d
0x180008f3a  mov     [rsp+1090h+var_1068], rax
0x180008f3f  lea     r9, [rsp+1090h+var_104C]
0x180008f44  lea     rax, [rsp+1090h+var_1040]
0x180008f49  xor     edx, edx
0x180008f4b  mov     [rsp+1090h+var_1070], rax
0x180008f50  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008f57  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f63  mov     ebx, eax
0x180008f65  mov     edi, eax
0x180008f67  test    eax, eax
0x180008f69  jnz     loc_18000905F
0x180008f6f  mov     r9d, [rsp+1090h+var_1050]
0x180008f74  mov     r11, 0AAAAAAAAAAAAAAABh
0x180008f7e  mov     rax, r11
0x180008f81  mul     r9
0x180008f84  shr     rdx, 3
0x180008f88  lea     rcx, [rdx+rdx*2]
0x180008f8c  shl     rcx, 2
0x180008f90  cmp     r9, rcx
0x180008f93  jz      short loc_180008F9D
0x180008f95  xor     r9d, r9d
0x180008f98  mov     [rsp+1090h+var_1050], r9d
0x180008f9d  mov     r8, [r14]
0x180008fa0  mov     rax, r11
0x180008fa3  mov     ecx, r9d
0x180008fa6  mul     rcx
0x180008fa9  mov     rcx, [r14+8]
0x180008fad  mov     rax, r11
0x180008fb0  mov     r10, rdx
0x180008fb3  sub     rcx, r8
0x180008fb6  mul     rcx
0x180008fb9  shr     r10, 3
0x180008fbd  shr     rdx, 3
0x180008fc1  lea     rax, [rdx+rdx*2]
0x180008fc5  lea     rsi, [r8+rax*4]
0x180008fc9  jmp     short loc_180009034
0x180008fcb  mov     eax, r10d
0x180008fce  lea     rcx, [rax+rax*2]
0x180008fd2  lea     rdx, [rdx+rcx*4]
0x180008fd6  lea     rax, [rsp+1090h+var_1040]
0x180008fdb  cmp     rax, rdx
0x180008fde  jz      short loc_180009005
0x180008fe0  mov     r11d, [r8]
0x180008fe3  lea     rcx, [rsp+1090h+var_1040]
0x180008fe8  cmp     [rcx], r11d
0x180008feb  jnz     short loc_180008FFC
0x180008fed  movzx   eax, word ptr [r8+4]
0x180008ff2  cmp     [rcx+4], ax
0x180008ff6  jz      loc_18000909E
0x180008ffc  add     rcx, 0Ch
0x180009000  cmp     rcx, rdx
0x180009003  jnz     short loc_180008FE8
0x180009005  mov     eax, r9d
0x180009008  add     rax, 0Ch
0x18000900c  cmp     rax, 1000h
0x180009012  ja      short loc_180009030
0x180009014  movsd   xmm0, qword ptr [r8]
0x180009019  add     r9d, 0Ch
0x18000901d  movsd   qword ptr [rdx], xmm0
0x180009021  inc     r10d
0x180009024  mov     eax, [r8+8]
0x180009028  mov     [rdx+8], eax
0x18000902b  mov     [rsp+1090h+var_1050], r9d
0x180009030  add     r8, 0Ch
0x180009034  lea     rdx, [rsp+1090h+var_1040]
0x180009039  cmp     r8, rsi
0x18000903c  jnz     short loc_180008FCB
0x18000903e  mov     eax, [rsp+1090h+var_104C]
0x180009042  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180009049  mov     [rsp+1090h+var_1060], 1
0x180009051  mov     r8d, r9d
0x180009054  mov     dword ptr [rsp+1090h+var_1068], eax
0x180009058  call    wil_details_NtUpdateWnfStateData
0x18000905d  mov     esi, eax
0x18000905f  cmp     esi, 0C0000001h
0x180009065  jnz     short loc_180009078
0x180009067  inc     r15d
0x18000906a  cmp     r15d, 64h ; 'd'
0x18000906e  jge     short loc_180009078
0x180009070  test    edi, edi
0x180009072  jz      loc_180008EBE
0x180009078  test    ebx, ebx
0x18000907a  cmovz   ebx, esi
0x18000907d  mov     eax, ebx
0x18000907f  mov     rcx, [rbp+0F90h+var_40]
0x180009086  xor     rcx, rsp; StackCookie
0x180009089  call    __security_check_cookie
0x18000908e  add     rsp, 1068h
0x180009095  pop     r15
0x180009097  pop     r14
0x180009099  pop     rdi
0x18000909a  pop     rsi
0x18000909b  pop     rbx
0x18000909c  pop     rbp
0x18000909d  retn
0x18000909e  mov     eax, [r8+8]
0x1800090a2  add     [rcx+8], eax
0x1800090a5  mov     r9d, [rsp+1090h+var_1050]
0x1800090aa  jmp     short loc_180009030
```
