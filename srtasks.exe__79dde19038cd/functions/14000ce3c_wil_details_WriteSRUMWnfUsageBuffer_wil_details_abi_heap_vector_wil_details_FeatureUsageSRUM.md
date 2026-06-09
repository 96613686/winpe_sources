# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000ce3c`
- end: `0x14000d074`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140007b60`

## callees

- `0x14000ce3c`
- `0x14000d07c`
- `0x14001094e`
- `0x140010980`
- `0x140010a10`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000cec5`
- `KERNEL32!GetModuleHandleW` at `0x14000cec5`
- `KERNEL32!GetProcAddress` at `0x14000cedc`
- `KERNEL32!GetProcAddress` at `0x14000cedc`

## string_xrefs

- `0x14000cebe`: `ntdll.dll`

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
0x14000ce3c  push    rbp
0x14000ce3e  push    rbx
0x14000ce3f  push    rsi
0x14000ce40  push    rdi
0x14000ce41  push    r14
0x14000ce43  push    r15
0x14000ce45  lea     rbp, [rsp-0F68h]
0x14000ce4d  mov     eax, 1068h
0x14000ce52  call    _alloca_probe
0x14000ce57  sub     rsp, rax
0x14000ce5a  mov     rax, cs:__security_cookie
0x14000ce61  xor     rax, rsp
0x14000ce64  mov     [rbp+0F90h+var_40], rax
0x14000ce6b  mov     rax, [rcx+8]
0x14000ce6f  xor     ebx, ebx
0x14000ce71  sub     rax, [rcx]
0x14000ce74  xor     esi, esi
0x14000ce76  mov     r14, rcx
0x14000ce79  cmp     rax, 0Ch
0x14000ce7d  jb      loc_14000D040
0x14000ce83  xor     r15d, r15d
0x14000ce86  xor     edx, edx; Val
0x14000ce88  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000ce8d  mov     r8d, 1000h; Size
0x14000ce93  call    memset_0
0x14000ce98  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000cea0  mov     [rsp+1090h+var_1050], 1000h
0x14000cea8  mov     [rsp+1090h+var_104C], 0
0x14000ceb0  jnz     short loc_14000CEFA
0x14000ceb2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ceb9  test    rax, rax
0x14000cebc  jnz     short loc_14000CED2
0x14000cebe  lea     rcx, ModuleName; "ntdll.dll"
0x14000cec5  call    cs:__imp_GetModuleHandleW
0x14000cecb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ced2  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000ced9  mov     rcx, rax; hModule
0x14000cedc  call    cs:__imp_GetProcAddress
0x14000cee2  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000cee9  test    rax, rax
0x14000ceec  jnz     short loc_14000CEFA
0x14000ceee  mov     edi, 0C0000139h
0x14000cef3  mov     ebx, edi
0x14000cef5  jmp     loc_14000D027
0x14000cefa  lea     rax, [rsp+1090h+var_1050]
0x14000ceff  xor     r8d, r8d
0x14000cf02  mov     [rsp+1090h+var_1068], rax
0x14000cf07  lea     r9, [rsp+1090h+var_104C]
0x14000cf0c  lea     rax, [rsp+1090h+var_1040]
0x14000cf11  xor     edx, edx
0x14000cf13  mov     [rsp+1090h+var_1070], rax
0x14000cf18  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000cf1f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000cf26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cf2b  mov     ebx, eax
0x14000cf2d  mov     edi, eax
0x14000cf2f  test    eax, eax
0x14000cf31  jnz     loc_14000D027
0x14000cf37  mov     r9d, [rsp+1090h+var_1050]
0x14000cf3c  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000cf46  mov     rax, r11
0x14000cf49  mul     r9
0x14000cf4c  shr     rdx, 3
0x14000cf50  lea     rcx, [rdx+rdx*2]
0x14000cf54  shl     rcx, 2
0x14000cf58  cmp     r9, rcx
0x14000cf5b  jz      short loc_14000CF65
0x14000cf5d  xor     r9d, r9d
0x14000cf60  mov     [rsp+1090h+var_1050], r9d
0x14000cf65  mov     r8, [r14]
0x14000cf68  mov     rax, r11
0x14000cf6b  mov     ecx, r9d
0x14000cf6e  mul     rcx
0x14000cf71  mov     rcx, [r14+8]
0x14000cf75  mov     rax, r11
0x14000cf78  mov     r10, rdx
0x14000cf7b  sub     rcx, r8
0x14000cf7e  mul     rcx
0x14000cf81  shr     r10, 3
0x14000cf85  shr     rdx, 3
0x14000cf89  lea     rax, [rdx+rdx*2]
0x14000cf8d  lea     rsi, [r8+rax*4]
0x14000cf91  jmp     short loc_14000CFFC
0x14000cf93  mov     eax, r10d
0x14000cf96  lea     rcx, [rax+rax*2]
0x14000cf9a  lea     rdx, [rdx+rcx*4]
0x14000cf9e  lea     rax, [rsp+1090h+var_1040]
0x14000cfa3  cmp     rax, rdx
0x14000cfa6  jz      short loc_14000CFCD
0x14000cfa8  mov     r11d, [r8]
0x14000cfab  lea     rcx, [rsp+1090h+var_1040]
0x14000cfb0  cmp     [rcx], r11d
0x14000cfb3  jnz     short loc_14000CFC4
0x14000cfb5  movzx   eax, word ptr [r8+4]
0x14000cfba  cmp     [rcx+4], ax
0x14000cfbe  jz      loc_14000D066
0x14000cfc4  add     rcx, 0Ch
0x14000cfc8  cmp     rcx, rdx
0x14000cfcb  jnz     short loc_14000CFB0
0x14000cfcd  mov     eax, r9d
0x14000cfd0  add     rax, 0Ch
0x14000cfd4  cmp     rax, 1000h
0x14000cfda  ja      short loc_14000CFF8
0x14000cfdc  movsd   xmm0, qword ptr [r8]
0x14000cfe1  add     r9d, 0Ch
0x14000cfe5  movsd   qword ptr [rdx], xmm0
0x14000cfe9  inc     r10d
0x14000cfec  mov     eax, [r8+8]
0x14000cff0  mov     [rdx+8], eax
0x14000cff3  mov     [rsp+1090h+var_1050], r9d
0x14000cff8  add     r8, 0Ch
0x14000cffc  lea     rdx, [rsp+1090h+var_1040]
0x14000d001  cmp     r8, rsi
0x14000d004  jnz     short loc_14000CF93
0x14000d006  mov     eax, [rsp+1090h+var_104C]
0x14000d00a  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000d011  mov     [rsp+1090h+var_1060], 1
0x14000d019  mov     r8d, r9d
0x14000d01c  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000d020  call    wil_details_NtUpdateWnfStateData
0x14000d025  mov     esi, eax
0x14000d027  cmp     esi, 0C0000001h
0x14000d02d  jnz     short loc_14000D040
0x14000d02f  inc     r15d
0x14000d032  cmp     r15d, 64h ; 'd'
0x14000d036  jge     short loc_14000D040
0x14000d038  test    edi, edi
0x14000d03a  jz      loc_14000CE86
0x14000d040  test    ebx, ebx
0x14000d042  cmovz   ebx, esi
0x14000d045  mov     eax, ebx
0x14000d047  mov     rcx, [rbp+0F90h+var_40]
0x14000d04e  xor     rcx, rsp; StackCookie
0x14000d051  call    __security_check_cookie
0x14000d056  add     rsp, 1068h
0x14000d05d  pop     r15
0x14000d05f  pop     r14
0x14000d061  pop     rdi
0x14000d062  pop     rsi
0x14000d063  pop     rbx
0x14000d064  pop     rbp
0x14000d065  retn
0x14000d066  mov     eax, [r8+8]
0x14000d06a  add     [rcx+8], eax
0x14000d06d  mov     r9d, [rsp+1090h+var_1050]
0x14000d072  jmp     short loc_14000CFF8
```
