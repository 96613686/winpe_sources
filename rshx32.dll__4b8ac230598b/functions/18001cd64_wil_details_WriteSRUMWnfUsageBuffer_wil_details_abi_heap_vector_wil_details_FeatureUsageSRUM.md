# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001cd64`
- end: `0x18001cf9c`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180019950`

## callees

- `0x18001cd64`
- `0x18001d190`
- `0x18001d33a`
- `0x18001d370`
- `0x18001d400`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ce04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ce04`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001cded`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001cded`

## string_xrefs

- `0x18001cde6`: `ntdll.dll`

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
0x18001cd64  push    rbp
0x18001cd66  push    rbx
0x18001cd67  push    rsi
0x18001cd68  push    rdi
0x18001cd69  push    r14
0x18001cd6b  push    r15
0x18001cd6d  lea     rbp, [rsp-0F68h]
0x18001cd75  mov     eax, 1068h
0x18001cd7a  call    _alloca_probe
0x18001cd7f  sub     rsp, rax
0x18001cd82  mov     rax, cs:__security_cookie
0x18001cd89  xor     rax, rsp
0x18001cd8c  mov     [rbp+0F90h+var_40], rax
0x18001cd93  mov     rax, [rcx+8]
0x18001cd97  xor     ebx, ebx
0x18001cd99  sub     rax, [rcx]
0x18001cd9c  xor     esi, esi
0x18001cd9e  mov     r14, rcx
0x18001cda1  cmp     rax, 0Ch
0x18001cda5  jb      loc_18001CF68
0x18001cdab  xor     r15d, r15d
0x18001cdae  xor     edx, edx; Val
0x18001cdb0  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001cdb5  mov     r8d, 1000h; Size
0x18001cdbb  call    memset_0
0x18001cdc0  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18001cdc8  mov     [rsp+1090h+var_1050], 1000h
0x18001cdd0  mov     [rsp+1090h+var_104C], 0
0x18001cdd8  jnz     short loc_18001CE22
0x18001cdda  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001cde1  test    rax, rax
0x18001cde4  jnz     short loc_18001CDFA
0x18001cde6  lea     rcx, ModuleName; "ntdll.dll"
0x18001cded  call    cs:__imp_GetModuleHandleW
0x18001cdf3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001cdfa  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18001ce01  mov     rcx, rax; hModule
0x18001ce04  call    cs:__imp_GetProcAddress
0x18001ce0a  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18001ce11  test    rax, rax
0x18001ce14  jnz     short loc_18001CE22
0x18001ce16  mov     edi, 0C0000139h
0x18001ce1b  mov     ebx, edi
0x18001ce1d  jmp     loc_18001CF4F
0x18001ce22  lea     rax, [rsp+1090h+var_1050]
0x18001ce27  xor     r8d, r8d
0x18001ce2a  mov     [rsp+1090h+var_1068], rax
0x18001ce2f  lea     r9, [rsp+1090h+var_104C]
0x18001ce34  lea     rax, [rsp+1090h+var_1040]
0x18001ce39  xor     edx, edx
0x18001ce3b  mov     [rsp+1090h+var_1070], rax
0x18001ce40  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001ce47  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18001ce4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce53  mov     ebx, eax
0x18001ce55  mov     edi, eax
0x18001ce57  test    eax, eax
0x18001ce59  jnz     loc_18001CF4F
0x18001ce5f  mov     r9d, [rsp+1090h+var_1050]
0x18001ce64  mov     r11, 0AAAAAAAAAAAAAAABh
0x18001ce6e  mov     rax, r11
0x18001ce71  mul     r9
0x18001ce74  shr     rdx, 3
0x18001ce78  lea     rcx, [rdx+rdx*2]
0x18001ce7c  shl     rcx, 2
0x18001ce80  cmp     r9, rcx
0x18001ce83  jz      short loc_18001CE8D
0x18001ce85  xor     r9d, r9d
0x18001ce88  mov     [rsp+1090h+var_1050], r9d
0x18001ce8d  mov     r8, [r14]
0x18001ce90  mov     rax, r11
0x18001ce93  mov     ecx, r9d
0x18001ce96  mul     rcx
0x18001ce99  mov     rcx, [r14+8]
0x18001ce9d  mov     rax, r11
0x18001cea0  mov     r10, rdx
0x18001cea3  sub     rcx, r8
0x18001cea6  mul     rcx
0x18001cea9  shr     r10, 3
0x18001cead  shr     rdx, 3
0x18001ceb1  lea     rax, [rdx+rdx*2]
0x18001ceb5  lea     rsi, [r8+rax*4]
0x18001ceb9  jmp     short loc_18001CF24
0x18001cebb  mov     eax, r10d
0x18001cebe  lea     rcx, [rax+rax*2]
0x18001cec2  lea     rdx, [rdx+rcx*4]
0x18001cec6  lea     rax, [rsp+1090h+var_1040]
0x18001cecb  cmp     rax, rdx
0x18001cece  jz      short loc_18001CEF5
0x18001ced0  mov     r11d, [r8]
0x18001ced3  lea     rcx, [rsp+1090h+var_1040]
0x18001ced8  cmp     [rcx], r11d
0x18001cedb  jnz     short loc_18001CEEC
0x18001cedd  movzx   eax, word ptr [r8+4]
0x18001cee2  cmp     [rcx+4], ax
0x18001cee6  jz      loc_18001CF8E
0x18001ceec  add     rcx, 0Ch
0x18001cef0  cmp     rcx, rdx
0x18001cef3  jnz     short loc_18001CED8
0x18001cef5  mov     eax, r9d
0x18001cef8  add     rax, 0Ch
0x18001cefc  cmp     rax, 1000h
0x18001cf02  ja      short loc_18001CF20
0x18001cf04  movsd   xmm0, qword ptr [r8]
0x18001cf09  add     r9d, 0Ch
0x18001cf0d  movsd   qword ptr [rdx], xmm0
0x18001cf11  inc     r10d
0x18001cf14  mov     eax, [r8+8]
0x18001cf18  mov     [rdx+8], eax
0x18001cf1b  mov     [rsp+1090h+var_1050], r9d
0x18001cf20  add     r8, 0Ch
0x18001cf24  lea     rdx, [rsp+1090h+var_1040]
0x18001cf29  cmp     r8, rsi
0x18001cf2c  jnz     short loc_18001CEBB
0x18001cf2e  mov     eax, [rsp+1090h+var_104C]
0x18001cf32  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001cf39  mov     [rsp+1090h+var_1060], 1
0x18001cf41  mov     r8d, r9d
0x18001cf44  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001cf48  call    wil_details_NtUpdateWnfStateData
0x18001cf4d  mov     esi, eax
0x18001cf4f  cmp     esi, 0C0000001h
0x18001cf55  jnz     short loc_18001CF68
0x18001cf57  inc     r15d
0x18001cf5a  cmp     r15d, 64h ; 'd'
0x18001cf5e  jge     short loc_18001CF68
0x18001cf60  test    edi, edi
0x18001cf62  jz      loc_18001CDAE
0x18001cf68  test    ebx, ebx
0x18001cf6a  cmovz   ebx, esi
0x18001cf6d  mov     eax, ebx
0x18001cf6f  mov     rcx, [rbp+0F90h+var_40]
0x18001cf76  xor     rcx, rsp; StackCookie
0x18001cf79  call    __security_check_cookie
0x18001cf7e  add     rsp, 1068h
0x18001cf85  pop     r15
0x18001cf87  pop     r14
0x18001cf89  pop     rdi
0x18001cf8a  pop     rsi
0x18001cf8b  pop     rbx
0x18001cf8c  pop     rbp
0x18001cf8d  retn
0x18001cf8e  mov     eax, [r8+8]
0x18001cf92  add     [rcx+8], eax
0x18001cf95  mov     r9d, [rsp+1090h+var_1050]
0x18001cf9a  jmp     short loc_18001CF20
```
