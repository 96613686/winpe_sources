# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180034790`
- end: `0x1800349c8`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18002c860`

## callees

- `0x180034790`
- `0x180038678`
- `0x180056df2`
- `0x180056e30`
- `0x180056ef0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034830`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034830`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180034819`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180034819`

## string_xrefs

- `0x180034812`: `ntdll.dll`

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
0x180034790  push    rbp
0x180034792  push    rbx
0x180034793  push    rsi
0x180034794  push    rdi
0x180034795  push    r14
0x180034797  push    r15
0x180034799  lea     rbp, [rsp-0F68h]
0x1800347a1  mov     eax, 1068h
0x1800347a6  call    _alloca_probe
0x1800347ab  sub     rsp, rax
0x1800347ae  mov     rax, cs:__security_cookie
0x1800347b5  xor     rax, rsp
0x1800347b8  mov     [rbp+0F90h+var_40], rax
0x1800347bf  mov     rax, [rcx+8]
0x1800347c3  xor     ebx, ebx
0x1800347c5  sub     rax, [rcx]
0x1800347c8  xor     esi, esi
0x1800347ca  mov     r14, rcx
0x1800347cd  cmp     rax, 0Ch
0x1800347d1  jb      loc_180034994
0x1800347d7  xor     r15d, r15d
0x1800347da  xor     edx, edx; Val
0x1800347dc  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800347e1  mov     r8d, 1000h; Size
0x1800347e7  call    memset_0
0x1800347ec  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1800347f4  mov     [rsp+1090h+var_1050], 1000h
0x1800347fc  mov     [rsp+1090h+var_104C], 0
0x180034804  jnz     short loc_18003484E
0x180034806  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003480d  test    rax, rax
0x180034810  jnz     short loc_180034826
0x180034812  lea     rcx, ModuleName; "ntdll.dll"
0x180034819  call    cs:__imp_GetModuleHandleW
0x18003481f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180034826  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18003482d  mov     rcx, rax; hModule
0x180034830  call    cs:__imp_GetProcAddress
0x180034836  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18003483d  test    rax, rax
0x180034840  jnz     short loc_18003484E
0x180034842  mov     edi, 0C0000139h
0x180034847  mov     ebx, edi
0x180034849  jmp     loc_18003497B
0x18003484e  lea     rax, [rsp+1090h+var_1050]
0x180034853  xor     r8d, r8d
0x180034856  mov     [rsp+1090h+var_1068], rax
0x18003485b  lea     r9, [rsp+1090h+var_104C]
0x180034860  lea     rax, [rsp+1090h+var_1040]
0x180034865  xor     edx, edx
0x180034867  mov     [rsp+1090h+var_1070], rax
0x18003486c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180034873  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18003487a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003487f  mov     ebx, eax
0x180034881  mov     edi, eax
0x180034883  test    eax, eax
0x180034885  jnz     loc_18003497B
0x18003488b  mov     r9d, [rsp+1090h+var_1050]
0x180034890  mov     r11, 0AAAAAAAAAAAAAAABh
0x18003489a  mov     rax, r11
0x18003489d  mul     r9
0x1800348a0  shr     rdx, 3
0x1800348a4  lea     rcx, [rdx+rdx*2]
0x1800348a8  shl     rcx, 2
0x1800348ac  cmp     r9, rcx
0x1800348af  jz      short loc_1800348B9
0x1800348b1  xor     r9d, r9d
0x1800348b4  mov     [rsp+1090h+var_1050], r9d
0x1800348b9  mov     r8, [r14]
0x1800348bc  mov     rax, r11
0x1800348bf  mov     ecx, r9d
0x1800348c2  mul     rcx
0x1800348c5  mov     rcx, [r14+8]
0x1800348c9  mov     rax, r11
0x1800348cc  mov     r10, rdx
0x1800348cf  sub     rcx, r8
0x1800348d2  mul     rcx
0x1800348d5  shr     r10, 3
0x1800348d9  shr     rdx, 3
0x1800348dd  lea     rax, [rdx+rdx*2]
0x1800348e1  lea     rsi, [r8+rax*4]
0x1800348e5  jmp     short loc_180034950
0x1800348e7  mov     eax, r10d
0x1800348ea  lea     rcx, [rax+rax*2]
0x1800348ee  lea     rdx, [rdx+rcx*4]
0x1800348f2  lea     rax, [rsp+1090h+var_1040]
0x1800348f7  cmp     rax, rdx
0x1800348fa  jz      short loc_180034921
0x1800348fc  mov     r11d, [r8]
0x1800348ff  lea     rcx, [rsp+1090h+var_1040]
0x180034904  cmp     [rcx], r11d
0x180034907  jnz     short loc_180034918
0x180034909  movzx   eax, word ptr [r8+4]
0x18003490e  cmp     [rcx+4], ax
0x180034912  jz      loc_1800349BA
0x180034918  add     rcx, 0Ch
0x18003491c  cmp     rcx, rdx
0x18003491f  jnz     short loc_180034904
0x180034921  mov     eax, r9d
0x180034924  add     rax, 0Ch
0x180034928  cmp     rax, 1000h
0x18003492e  ja      short loc_18003494C
0x180034930  movsd   xmm0, qword ptr [r8]
0x180034935  add     r9d, 0Ch
0x180034939  movsd   qword ptr [rdx], xmm0
0x18003493d  inc     r10d
0x180034940  mov     eax, [r8+8]
0x180034944  mov     [rdx+8], eax
0x180034947  mov     [rsp+1090h+var_1050], r9d
0x18003494c  add     r8, 0Ch
0x180034950  lea     rdx, [rsp+1090h+var_1040]
0x180034955  cmp     r8, rsi
0x180034958  jnz     short loc_1800348E7
0x18003495a  mov     eax, [rsp+1090h+var_104C]
0x18003495e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180034965  mov     [rsp+1090h+var_1060], 1
0x18003496d  mov     r8d, r9d
0x180034970  mov     dword ptr [rsp+1090h+var_1068], eax
0x180034974  call    wil_details_NtUpdateWnfStateData
0x180034979  mov     esi, eax
0x18003497b  cmp     esi, 0C0000001h
0x180034981  jnz     short loc_180034994
0x180034983  inc     r15d
0x180034986  cmp     r15d, 64h ; 'd'
0x18003498a  jge     short loc_180034994
0x18003498c  test    edi, edi
0x18003498e  jz      loc_1800347DA
0x180034994  test    ebx, ebx
0x180034996  cmovz   ebx, esi
0x180034999  mov     eax, ebx
0x18003499b  mov     rcx, [rbp+0F90h+var_40]
0x1800349a2  xor     rcx, rsp; StackCookie
0x1800349a5  call    __security_check_cookie
0x1800349aa  add     rsp, 1068h
0x1800349b1  pop     r15
0x1800349b3  pop     r14
0x1800349b5  pop     rdi
0x1800349b6  pop     rsi
0x1800349b7  pop     rbx
0x1800349b8  pop     rbp
0x1800349b9  retn
0x1800349ba  mov     eax, [r8+8]
0x1800349be  add     [rcx+8], eax
0x1800349c1  mov     r9d, [rsp+1090h+var_1050]
0x1800349c6  jmp     short loc_18003494C
```
