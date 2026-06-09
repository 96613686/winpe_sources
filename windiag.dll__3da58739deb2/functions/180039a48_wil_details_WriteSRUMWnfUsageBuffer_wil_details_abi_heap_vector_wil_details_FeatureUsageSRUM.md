# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180039a48`
- end: `0x180039c80`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180032f80`

## callees

- `0x180004510`
- `0x1800054e4`
- `0x180039a48`
- `0x180039f10`
- `0x180096b40`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039ae8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039ae8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039ad1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039ad1`

## string_xrefs

- `0x180039aca`: `ntdll.dll`

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
0x180039a48  push    rbp
0x180039a4a  push    rbx
0x180039a4b  push    rsi
0x180039a4c  push    rdi
0x180039a4d  push    r14
0x180039a4f  push    r15
0x180039a51  lea     rbp, [rsp-0F68h]
0x180039a59  mov     eax, 1068h
0x180039a5e  call    _alloca_probe
0x180039a63  sub     rsp, rax
0x180039a66  mov     rax, cs:__security_cookie
0x180039a6d  xor     rax, rsp
0x180039a70  mov     [rbp+0F90h+var_40], rax
0x180039a77  mov     rax, [rcx+8]
0x180039a7b  xor     ebx, ebx
0x180039a7d  sub     rax, [rcx]
0x180039a80  xor     esi, esi
0x180039a82  mov     r14, rcx
0x180039a85  cmp     rax, 0Ch
0x180039a89  jb      loc_180039C4C
0x180039a8f  xor     r15d, r15d
0x180039a92  xor     edx, edx; Val
0x180039a94  lea     rcx, [rsp+1090h+var_1040]; void *
0x180039a99  mov     r8d, 1000h; Size
0x180039a9f  call    memset_0
0x180039aa4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180039aac  mov     [rsp+1090h+var_1050], 1000h
0x180039ab4  mov     [rsp+1090h+var_104C], 0
0x180039abc  jnz     short loc_180039B06
0x180039abe  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180039ac5  test    rax, rax
0x180039ac8  jnz     short loc_180039ADE
0x180039aca  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180039ad1  call    cs:__imp_GetModuleHandleW
0x180039ad7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180039ade  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180039ae5  mov     rcx, rax; hModule
0x180039ae8  call    cs:__imp_GetProcAddress
0x180039aee  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180039af5  test    rax, rax
0x180039af8  jnz     short loc_180039B06
0x180039afa  mov     edi, 0C0000139h
0x180039aff  mov     ebx, edi
0x180039b01  jmp     loc_180039C33
0x180039b06  lea     rax, [rsp+1090h+var_1050]
0x180039b0b  xor     r8d, r8d
0x180039b0e  mov     [rsp+1090h+var_1068], rax
0x180039b13  lea     r9, [rsp+1090h+var_104C]
0x180039b18  lea     rax, [rsp+1090h+var_1040]
0x180039b1d  xor     edx, edx
0x180039b1f  mov     [rsp+1090h+var_1070], rax
0x180039b24  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180039b2b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180039b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b37  mov     ebx, eax
0x180039b39  mov     edi, eax
0x180039b3b  test    eax, eax
0x180039b3d  jnz     loc_180039C33
0x180039b43  mov     r9d, [rsp+1090h+var_1050]
0x180039b48  mov     r11, 0AAAAAAAAAAAAAAABh
0x180039b52  mov     rax, r11
0x180039b55  mul     r9
0x180039b58  shr     rdx, 3
0x180039b5c  lea     rcx, [rdx+rdx*2]
0x180039b60  shl     rcx, 2
0x180039b64  cmp     r9, rcx
0x180039b67  jz      short loc_180039B71
0x180039b69  xor     r9d, r9d
0x180039b6c  mov     [rsp+1090h+var_1050], r9d
0x180039b71  mov     r8, [r14]
0x180039b74  mov     rax, r11
0x180039b77  mov     ecx, r9d
0x180039b7a  mul     rcx
0x180039b7d  mov     rcx, [r14+8]
0x180039b81  mov     rax, r11
0x180039b84  mov     r10, rdx
0x180039b87  sub     rcx, r8
0x180039b8a  mul     rcx
0x180039b8d  shr     r10, 3
0x180039b91  shr     rdx, 3
0x180039b95  lea     rax, [rdx+rdx*2]
0x180039b99  lea     rsi, [r8+rax*4]
0x180039b9d  jmp     short loc_180039C08
0x180039b9f  mov     eax, r10d
0x180039ba2  lea     rcx, [rax+rax*2]
0x180039ba6  lea     rdx, [rdx+rcx*4]
0x180039baa  lea     rax, [rsp+1090h+var_1040]
0x180039baf  cmp     rax, rdx
0x180039bb2  jz      short loc_180039BD9
0x180039bb4  mov     r11d, [r8]
0x180039bb7  lea     rcx, [rsp+1090h+var_1040]
0x180039bbc  cmp     [rcx], r11d
0x180039bbf  jnz     short loc_180039BD0
0x180039bc1  movzx   eax, word ptr [r8+4]
0x180039bc6  cmp     [rcx+4], ax
0x180039bca  jz      loc_180039C72
0x180039bd0  add     rcx, 0Ch
0x180039bd4  cmp     rcx, rdx
0x180039bd7  jnz     short loc_180039BBC
0x180039bd9  mov     eax, r9d
0x180039bdc  add     rax, 0Ch
0x180039be0  cmp     rax, 1000h
0x180039be6  ja      short loc_180039C04
0x180039be8  movsd   xmm0, qword ptr [r8]
0x180039bed  add     r9d, 0Ch
0x180039bf1  movsd   qword ptr [rdx], xmm0
0x180039bf5  inc     r10d
0x180039bf8  mov     eax, [r8+8]
0x180039bfc  mov     [rdx+8], eax
0x180039bff  mov     [rsp+1090h+var_1050], r9d
0x180039c04  add     r8, 0Ch
0x180039c08  lea     rdx, [rsp+1090h+var_1040]
0x180039c0d  cmp     r8, rsi
0x180039c10  jnz     short loc_180039B9F
0x180039c12  mov     eax, [rsp+1090h+var_104C]
0x180039c16  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180039c1d  mov     [rsp+1090h+var_1060], 1
0x180039c25  mov     r8d, r9d
0x180039c28  mov     dword ptr [rsp+1090h+var_1068], eax
0x180039c2c  call    wil_details_NtUpdateWnfStateData
0x180039c31  mov     esi, eax
0x180039c33  cmp     esi, 0C0000001h
0x180039c39  jnz     short loc_180039C4C
0x180039c3b  inc     r15d
0x180039c3e  cmp     r15d, 64h ; 'd'
0x180039c42  jge     short loc_180039C4C
0x180039c44  test    edi, edi
0x180039c46  jz      loc_180039A92
0x180039c4c  test    ebx, ebx
0x180039c4e  cmovz   ebx, esi
0x180039c51  mov     eax, ebx
0x180039c53  mov     rcx, [rbp+0F90h+var_40]
0x180039c5a  xor     rcx, rsp; StackCookie
0x180039c5d  call    __security_check_cookie
0x180039c62  add     rsp, 1068h
0x180039c69  pop     r15
0x180039c6b  pop     r14
0x180039c6d  pop     rdi
0x180039c6e  pop     rsi
0x180039c6f  pop     rbx
0x180039c70  pop     rbp
0x180039c71  retn
0x180039c72  mov     eax, [r8+8]
0x180039c76  add     [rcx+8], eax
0x180039c79  mov     r9d, [rsp+1090h+var_1050]
0x180039c7e  jmp     short loc_180039C04
```
