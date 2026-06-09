# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000bad8`
- end: `0x18000bd10`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180004d60`

## callees

- `0x180004120`
- `0x180004c80`
- `0x18000bad8`
- `0x18000bda8`
- `0x18002ef20`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb78`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb78`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bb61`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bb61`

## string_xrefs

- `0x18000bb5a`: `ntdll.dll`

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
0x18000bad8  push    rbp
0x18000bada  push    rbx
0x18000badb  push    rsi
0x18000badc  push    rdi
0x18000badd  push    r14
0x18000badf  push    r15
0x18000bae1  lea     rbp, [rsp-0F68h]
0x18000bae9  mov     eax, 1068h
0x18000baee  call    _alloca_probe
0x18000baf3  sub     rsp, rax
0x18000baf6  mov     rax, cs:__security_cookie
0x18000bafd  xor     rax, rsp
0x18000bb00  mov     [rbp+0F90h+var_40], rax
0x18000bb07  mov     rax, [rcx+8]
0x18000bb0b  xor     ebx, ebx
0x18000bb0d  sub     rax, [rcx]
0x18000bb10  xor     esi, esi
0x18000bb12  mov     r14, rcx
0x18000bb15  cmp     rax, 0Ch
0x18000bb19  jb      loc_18000BCDC
0x18000bb1f  xor     r15d, r15d
0x18000bb22  xor     edx, edx; Val
0x18000bb24  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000bb29  mov     r8d, 1000h; Size
0x18000bb2f  call    memset_0
0x18000bb34  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000bb3c  mov     [rsp+1090h+var_1050], 1000h
0x18000bb44  mov     [rsp+1090h+var_104C], 0
0x18000bb4c  jnz     short loc_18000BB96
0x18000bb4e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bb55  test    rax, rax
0x18000bb58  jnz     short loc_18000BB6E
0x18000bb5a  lea     rcx, ModuleName; "ntdll.dll"
0x18000bb61  call    cs:__imp_GetModuleHandleW
0x18000bb67  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bb6e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000bb75  mov     rcx, rax; hModule
0x18000bb78  call    cs:__imp_GetProcAddress
0x18000bb7e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000bb85  test    rax, rax
0x18000bb88  jnz     short loc_18000BB96
0x18000bb8a  mov     edi, 0C0000139h
0x18000bb8f  mov     ebx, edi
0x18000bb91  jmp     loc_18000BCC3
0x18000bb96  lea     rax, [rsp+1090h+var_1050]
0x18000bb9b  xor     r8d, r8d
0x18000bb9e  mov     [rsp+1090h+var_1068], rax
0x18000bba3  lea     r9, [rsp+1090h+var_104C]
0x18000bba8  lea     rax, [rsp+1090h+var_1040]
0x18000bbad  xor     edx, edx
0x18000bbaf  mov     [rsp+1090h+var_1070], rax
0x18000bbb4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000bbbb  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000bbc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbc7  mov     ebx, eax
0x18000bbc9  mov     edi, eax
0x18000bbcb  test    eax, eax
0x18000bbcd  jnz     loc_18000BCC3
0x18000bbd3  mov     r9d, [rsp+1090h+var_1050]
0x18000bbd8  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000bbe2  mov     rax, r11
0x18000bbe5  mul     r9
0x18000bbe8  shr     rdx, 3
0x18000bbec  lea     rcx, [rdx+rdx*2]
0x18000bbf0  shl     rcx, 2
0x18000bbf4  cmp     r9, rcx
0x18000bbf7  jz      short loc_18000BC01
0x18000bbf9  xor     r9d, r9d
0x18000bbfc  mov     [rsp+1090h+var_1050], r9d
0x18000bc01  mov     r8, [r14]
0x18000bc04  mov     rax, r11
0x18000bc07  mov     ecx, r9d
0x18000bc0a  mul     rcx
0x18000bc0d  mov     rcx, [r14+8]
0x18000bc11  mov     rax, r11
0x18000bc14  mov     r10, rdx
0x18000bc17  sub     rcx, r8
0x18000bc1a  mul     rcx
0x18000bc1d  shr     r10, 3
0x18000bc21  shr     rdx, 3
0x18000bc25  lea     rax, [rdx+rdx*2]
0x18000bc29  lea     rsi, [r8+rax*4]
0x18000bc2d  jmp     short loc_18000BC98
0x18000bc2f  mov     eax, r10d
0x18000bc32  lea     rcx, [rax+rax*2]
0x18000bc36  lea     rdx, [rdx+rcx*4]
0x18000bc3a  lea     rax, [rsp+1090h+var_1040]
0x18000bc3f  cmp     rax, rdx
0x18000bc42  jz      short loc_18000BC69
0x18000bc44  mov     r11d, [r8]
0x18000bc47  lea     rcx, [rsp+1090h+var_1040]
0x18000bc4c  cmp     [rcx], r11d
0x18000bc4f  jnz     short loc_18000BC60
0x18000bc51  movzx   eax, word ptr [r8+4]
0x18000bc56  cmp     [rcx+4], ax
0x18000bc5a  jz      loc_18000BD02
0x18000bc60  add     rcx, 0Ch
0x18000bc64  cmp     rcx, rdx
0x18000bc67  jnz     short loc_18000BC4C
0x18000bc69  mov     eax, r9d
0x18000bc6c  add     rax, 0Ch
0x18000bc70  cmp     rax, 1000h
0x18000bc76  ja      short loc_18000BC94
0x18000bc78  movsd   xmm0, qword ptr [r8]
0x18000bc7d  add     r9d, 0Ch
0x18000bc81  movsd   qword ptr [rdx], xmm0
0x18000bc85  inc     r10d
0x18000bc88  mov     eax, [r8+8]
0x18000bc8c  mov     [rdx+8], eax
0x18000bc8f  mov     [rsp+1090h+var_1050], r9d
0x18000bc94  add     r8, 0Ch
0x18000bc98  lea     rdx, [rsp+1090h+var_1040]
0x18000bc9d  cmp     r8, rsi
0x18000bca0  jnz     short loc_18000BC2F
0x18000bca2  mov     eax, [rsp+1090h+var_104C]
0x18000bca6  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000bcad  mov     [rsp+1090h+var_1060], 1
0x18000bcb5  mov     r8d, r9d
0x18000bcb8  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000bcbc  call    wil_details_NtUpdateWnfStateData
0x18000bcc1  mov     esi, eax
0x18000bcc3  cmp     esi, 0C0000001h
0x18000bcc9  jnz     short loc_18000BCDC
0x18000bccb  inc     r15d
0x18000bcce  cmp     r15d, 64h ; 'd'
0x18000bcd2  jge     short loc_18000BCDC
0x18000bcd4  test    edi, edi
0x18000bcd6  jz      loc_18000BB22
0x18000bcdc  test    ebx, ebx
0x18000bcde  cmovz   ebx, esi
0x18000bce1  mov     eax, ebx
0x18000bce3  mov     rcx, [rbp+0F90h+var_40]
0x18000bcea  xor     rcx, rsp; StackCookie
0x18000bced  call    __security_check_cookie
0x18000bcf2  add     rsp, 1068h
0x18000bcf9  pop     r15
0x18000bcfb  pop     r14
0x18000bcfd  pop     rdi
0x18000bcfe  pop     rsi
0x18000bcff  pop     rbx
0x18000bd00  pop     rbp
0x18000bd01  retn
0x18000bd02  mov     eax, [r8+8]
0x18000bd06  add     [rcx+8], eax
0x18000bd09  mov     r9d, [rsp+1090h+var_1050]
0x18000bd0e  jmp     short loc_18000BC94
```
