# _dynamic_initializer_for__CEtwProviderT_void_::g_etwApi__

- ea: `0x180001030`
- end: `0x180001146`
- name: `_dynamic_initializer_for__CEtwProviderT_void_::g_etwApi__`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001030`
- `0x180001cb4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000104e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000104e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001077`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001096`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800010b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800010d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001077`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001096`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800010b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800010d4`

## string_xrefs

- `0x180001042`: `ntdll.dll`
- `0x1800010c6`: `EtwEventWrite`

## pseudocode

```c
int dynamic_initializer_for__CEtwProviderT_void_::g_etwApi__()
{
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+30h] [rbp+8h] BYREF

  phModule = 0;
  if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule) )
  {
    if ( phModule )
    {
      CEtwProviderT<void>::g_etwApi = (__int64)GetProcAddress(phModule, "EtwEventRegister");
      qword_180046F28 = (__int64)GetProcAddress(phModule, "EtwEventUnregister");
      qword_180046F30 = (__int64)GetProcAddress(phModule, "EtwEventEnabled");
      ProcAddress = GetProcAddress(phModule, "EtwEventWrite");
      qword_180046F38 = (__int64)ProcAddress;
      if ( !CEtwProviderT<void>::g_etwApi || !qword_180046F28 || !qword_180046F30 || !ProcAddress )
      {
        CEtwProviderT<void>::g_etwApi = 0;
        qword_180046F28 = 0;
        qword_180046F30 = 0;
        qword_180046F38 = 0;
      }
    }
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__CEtwProviderT_void_::g_etwApi__);
}

```

## disassembly

```asm
0x180001030  sub     rsp, 28h
0x180001034  lea     r8, [rsp+28h+phModule]; phModule
0x180001039  mov     [rsp+28h+phModule], 0
0x180001042  lea     rdx, ModuleName; "ntdll.dll"
0x180001049  mov     ecx, 1; dwFlags
0x18000104e  call    cs:__imp_GetModuleHandleExW
0x180001055  nop     dword ptr [rax+rax+00h]
0x18000105a  test    eax, eax
0x18000105c  jz      loc_180001136
0x180001062  mov     rcx, [rsp+28h+phModule]; hModule
0x180001067  test    rcx, rcx
0x18000106a  jz      loc_180001136
0x180001070  lea     rdx, ProcName; "EtwEventRegister"
0x180001077  call    cs:__imp_GetProcAddress
0x18000107e  nop     dword ptr [rax+rax+00h]
0x180001083  mov     rcx, [rsp+28h+phModule]; hModule
0x180001088  lea     rdx, aEtweventunregi; "EtwEventUnregister"
0x18000108f  mov     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, rax; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x180001096  call    cs:__imp_GetProcAddress
0x18000109d  nop     dword ptr [rax+rax+00h]
0x1800010a2  mov     rcx, [rsp+28h+phModule]; hModule
0x1800010a7  lea     rdx, aEtweventenable; "EtwEventEnabled"
0x1800010ae  mov     cs:qword_180046F28, rax
0x1800010b5  call    cs:__imp_GetProcAddress
0x1800010bc  nop     dword ptr [rax+rax+00h]
0x1800010c1  mov     rcx, [rsp+28h+phModule]; hModule
0x1800010c6  lea     rdx, aEtweventwrite; "EtwEventWrite"
0x1800010cd  mov     cs:qword_180046F30, rax
0x1800010d4  call    cs:__imp_GetProcAddress
0x1800010db  nop     dword ptr [rax+rax+00h]
0x1800010e0  cmp     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x1800010e8  mov     cs:qword_180046F38, rax
0x1800010ef  jz      short loc_18000110A
0x1800010f1  cmp     cs:qword_180046F28, 0
0x1800010f9  jz      short loc_18000110A
0x1800010fb  cmp     cs:qword_180046F30, 0
0x180001103  jz      short loc_18000110A
0x180001105  test    rax, rax
0x180001108  jnz     short loc_180001136
0x18000110a  mov     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x180001115  mov     cs:qword_180046F28, 0
0x180001120  mov     cs:qword_180046F30, 0
0x18000112b  mov     cs:qword_180046F38, 0
0x180001136  lea     rcx, _dynamic_atexit_destructor_for__CEtwProviderT_void___g_etwApi__
0x18000113d  add     rsp, 28h
0x180001141  jmp     atexit
```
