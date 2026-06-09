# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180014ae0`
- end: `0x180014d18`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f690`

## callees

- `0x180014ae0`
- `0x180014d20`
- `0x1800157be`
- `0x1800157f0`
- `0x180015880`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180014b80`
- `KERNEL32!GetProcAddress` at `0x180014b80`
- `KERNEL32!GetModuleHandleW` at `0x180014b69`
- `KERNEL32!GetModuleHandleW` at `0x180014b69`

## string_xrefs

- `0x180014b62`: `ntdll.dll`

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
0x180014ae0  push    rbp
0x180014ae2  push    rbx
0x180014ae3  push    rsi
0x180014ae4  push    rdi
0x180014ae5  push    r14
0x180014ae7  push    r15
0x180014ae9  lea     rbp, [rsp-0F68h]
0x180014af1  mov     eax, 1068h
0x180014af6  call    _alloca_probe
0x180014afb  sub     rsp, rax
0x180014afe  mov     rax, cs:__security_cookie
0x180014b05  xor     rax, rsp
0x180014b08  mov     [rbp+0F90h+var_40], rax
0x180014b0f  mov     rax, [rcx+8]
0x180014b13  xor     ebx, ebx
0x180014b15  sub     rax, [rcx]
0x180014b18  xor     esi, esi
0x180014b1a  mov     r14, rcx
0x180014b1d  cmp     rax, 0Ch
0x180014b21  jb      loc_180014CE4
0x180014b27  xor     r15d, r15d
0x180014b2a  xor     edx, edx; Val
0x180014b2c  lea     rcx, [rsp+1090h+var_1040]; void *
0x180014b31  mov     r8d, 1000h; Size
0x180014b37  call    memset_0
0x180014b3c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180014b44  mov     [rsp+1090h+var_1050], 1000h
0x180014b4c  mov     [rsp+1090h+var_104C], 0
0x180014b54  jnz     short loc_180014B9E
0x180014b56  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014b5d  test    rax, rax
0x180014b60  jnz     short loc_180014B76
0x180014b62  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180014b69  call    cs:__imp_GetModuleHandleW
0x180014b6f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014b76  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180014b7d  mov     rcx, rax; hModule
0x180014b80  call    cs:__imp_GetProcAddress
0x180014b86  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180014b8d  test    rax, rax
0x180014b90  jnz     short loc_180014B9E
0x180014b92  mov     edi, 0C0000139h
0x180014b97  mov     ebx, edi
0x180014b99  jmp     loc_180014CCB
0x180014b9e  lea     rax, [rsp+1090h+var_1050]
0x180014ba3  xor     r8d, r8d
0x180014ba6  mov     [rsp+1090h+var_1068], rax
0x180014bab  lea     r9, [rsp+1090h+var_104C]
0x180014bb0  lea     rax, [rsp+1090h+var_1040]
0x180014bb5  xor     edx, edx
0x180014bb7  mov     [rsp+1090h+var_1070], rax
0x180014bbc  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180014bc3  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180014bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bcf  mov     ebx, eax
0x180014bd1  mov     edi, eax
0x180014bd3  test    eax, eax
0x180014bd5  jnz     loc_180014CCB
0x180014bdb  mov     r9d, [rsp+1090h+var_1050]
0x180014be0  mov     r11, 0AAAAAAAAAAAAAAABh
0x180014bea  mov     rax, r11
0x180014bed  mul     r9
0x180014bf0  shr     rdx, 3
0x180014bf4  lea     rcx, [rdx+rdx*2]
0x180014bf8  shl     rcx, 2
0x180014bfc  cmp     r9, rcx
0x180014bff  jz      short loc_180014C09
0x180014c01  xor     r9d, r9d
0x180014c04  mov     [rsp+1090h+var_1050], r9d
0x180014c09  mov     r8, [r14]
0x180014c0c  mov     rax, r11
0x180014c0f  mov     ecx, r9d
0x180014c12  mul     rcx
0x180014c15  mov     rcx, [r14+8]
0x180014c19  mov     rax, r11
0x180014c1c  mov     r10, rdx
0x180014c1f  sub     rcx, r8
0x180014c22  mul     rcx
0x180014c25  shr     r10, 3
0x180014c29  shr     rdx, 3
0x180014c2d  lea     rax, [rdx+rdx*2]
0x180014c31  lea     rsi, [r8+rax*4]
0x180014c35  jmp     short loc_180014CA0
0x180014c37  mov     eax, r10d
0x180014c3a  lea     rcx, [rax+rax*2]
0x180014c3e  lea     rdx, [rdx+rcx*4]
0x180014c42  lea     rax, [rsp+1090h+var_1040]
0x180014c47  cmp     rax, rdx
0x180014c4a  jz      short loc_180014C71
0x180014c4c  mov     r11d, [r8]
0x180014c4f  lea     rcx, [rsp+1090h+var_1040]
0x180014c54  cmp     [rcx], r11d
0x180014c57  jnz     short loc_180014C68
0x180014c59  movzx   eax, word ptr [r8+4]
0x180014c5e  cmp     [rcx+4], ax
0x180014c62  jz      loc_180014D0A
0x180014c68  add     rcx, 0Ch
0x180014c6c  cmp     rcx, rdx
0x180014c6f  jnz     short loc_180014C54
0x180014c71  mov     eax, r9d
0x180014c74  add     rax, 0Ch
0x180014c78  cmp     rax, 1000h
0x180014c7e  ja      short loc_180014C9C
0x180014c80  movsd   xmm0, qword ptr [r8]
0x180014c85  add     r9d, 0Ch
0x180014c89  movsd   qword ptr [rdx], xmm0
0x180014c8d  inc     r10d
0x180014c90  mov     eax, [r8+8]
0x180014c94  mov     [rdx+8], eax
0x180014c97  mov     [rsp+1090h+var_1050], r9d
0x180014c9c  add     r8, 0Ch
0x180014ca0  lea     rdx, [rsp+1090h+var_1040]
0x180014ca5  cmp     r8, rsi
0x180014ca8  jnz     short loc_180014C37
0x180014caa  mov     eax, [rsp+1090h+var_104C]
0x180014cae  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180014cb5  mov     [rsp+1090h+var_1060], 1
0x180014cbd  mov     r8d, r9d
0x180014cc0  mov     dword ptr [rsp+1090h+var_1068], eax
0x180014cc4  call    wil_details_NtUpdateWnfStateData
0x180014cc9  mov     esi, eax
0x180014ccb  cmp     esi, 0C0000001h
0x180014cd1  jnz     short loc_180014CE4
0x180014cd3  inc     r15d
0x180014cd6  cmp     r15d, 64h ; 'd'
0x180014cda  jge     short loc_180014CE4
0x180014cdc  test    edi, edi
0x180014cde  jz      loc_180014B2A
0x180014ce4  test    ebx, ebx
0x180014ce6  cmovz   ebx, esi
0x180014ce9  mov     eax, ebx
0x180014ceb  mov     rcx, [rbp+0F90h+var_40]
0x180014cf2  xor     rcx, rsp; StackCookie
0x180014cf5  call    __security_check_cookie
0x180014cfa  add     rsp, 1068h
0x180014d01  pop     r15
0x180014d03  pop     r14
0x180014d05  pop     rdi
0x180014d06  pop     rsi
0x180014d07  pop     rbx
0x180014d08  pop     rbp
0x180014d09  retn
0x180014d0a  mov     eax, [r8+8]
0x180014d0e  add     [rcx+8], eax
0x180014d11  mov     r9d, [rsp+1090h+var_1050]
0x180014d16  jmp     short loc_180014C9C
```
