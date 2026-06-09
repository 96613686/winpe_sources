# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180002d30`
- end: `0x180002e41`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002d30`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002de0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002de0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002dc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002dc4`

## string_xrefs

- `0x180002dbd`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v6; // [rsp+28h] [rbp-28h]
  char v7; // [rsp+30h] [rbp-20h]
  char v8; // [rsp+31h] [rbp-1Fh]
  __int16 v9; // [rsp+32h] [rbp-1Eh]
  int v10; // [rsp+34h] [rbp-1Ch]
  __int16 v11; // [rsp+38h] [rbp-18h]
  __int16 v12; // [rsp+3Ah] [rbp-16h]
  int v13; // [rsp+3Ch] [rbp-14h]
  __int64 v14; // [rsp+40h] [rbp-10h]
  __int64 v15; // [rsp+48h] [rbp-8h]
  __int64 v16; // [rsp+60h] [rbp+10h] BYREF

  v5[1] = 0;
  v8 = 0;
  v10 = 0;
  v12 = 0;
  v5[0] = *((_DWORD *)this + 2);
  v6 = *((_QWORD *)this + 3);
  v7 = *(_BYTE *)this;
  v9 = wil::g_moduleFailureReportFlags;
  v11 = *((_WORD *)this + 32);
  v13 = 0;
  v14 = *((_QWORD *)this + 7);
  v15 = *((_QWORD *)this + 16);
  v16 = 0;
  ProcAddress = (FARPROC)`wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers;
  if ( `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers )
    goto LABEL_6;
  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle
    || (ModuleHandleW = GetModuleHandleW(L"kernelbase.dll"),
        (`wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW) != 0) )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "WilFailureNotifyWatchers");
  }
  `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_6:
    ((void (__fastcall *)(_QWORD, _DWORD *, __int64 *))ProcAddress)(0, v5, &v16);
  *((_DWORD *)this + 4) = v16;
  switch ( BYTE4(v16) )
  {
    case 1u:
      *((_DWORD *)this + 1) |= 1u;
      break;
    case 2u:
      *((_DWORD *)this + 1) |= 2u;
      break;
    case 3u:
      *((_DWORD *)this + 1) |= 4u;
      break;
  }
}

```

## disassembly

```asm
0x180002d30  mov     [rsp-8+arg_8], rbx
0x180002d35  mov     [rsp-8+arg_10], rdi
0x180002d3a  push    rbp
0x180002d3b  mov     rbp, rsp
0x180002d3e  sub     rsp, 50h
0x180002d42  mov     rbx, rcx
0x180002d45  mov     [rbp+var_2C], 0
0x180002d4c  mov     [rbp+var_1F], 0
0x180002d50  mov     [rbp+var_1C], 0
0x180002d57  xor     eax, eax
0x180002d59  mov     [rbp+var_16], ax
0x180002d5d  mov     eax, [rcx+8]
0x180002d60  mov     [rbp+var_30], eax
0x180002d63  mov     rax, [rcx+18h]
0x180002d67  mov     [rbp+var_28], rax
0x180002d6b  mov     al, [rcx]
0x180002d6d  mov     [rbp+var_20], al
0x180002d70  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180002d77  mov     [rbp+var_1E], ax
0x180002d7b  movzx   eax, word ptr [rcx+40h]
0x180002d7f  mov     [rbp+var_18], ax
0x180002d83  mov     [rbp+var_14], 0
0x180002d8a  mov     rax, [rcx+38h]
0x180002d8e  mov     [rbp+var_10], rax
0x180002d92  mov     rax, [rcx+80h]
0x180002d99  mov     [rbp+var_8], rax
0x180002d9d  mov     [rbp+arg_0], 0
0x180002da5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180002dac  test    rdi, rdi
0x180002daf  jnz     short loc_180002DF5
0x180002db1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180002db8  test    rax, rax
0x180002dbb  jnz     short loc_180002DD6
0x180002dbd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180002dc4  call    cs:__imp_GetModuleHandleW
0x180002dca  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180002dd1  test    rax, rax
0x180002dd4  jz      short loc_180002DE9
0x180002dd6  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x180002ddd  mov     rcx, rax; hModule
0x180002de0  call    cs:__imp_GetProcAddress
0x180002de6  mov     rdi, rax
0x180002de9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180002df0  test    rdi, rdi
0x180002df3  jz      short loc_180002E08
0x180002df5  lea     r8, [rbp+arg_0]
0x180002df9  lea     rdx, [rbp+var_30]
0x180002dfd  xor     ecx, ecx
0x180002dff  mov     rax, rdi
0x180002e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e07  nop
0x180002e08  mov     eax, dword ptr [rbp+arg_0]
0x180002e0b  mov     [rbx+10h], eax
0x180002e0e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180002e12  sub     ecx, 1
0x180002e15  jz      short loc_180002E2D
0x180002e17  sub     ecx, 1
0x180002e1a  jz      short loc_180002E27
0x180002e1c  cmp     ecx, 1
0x180002e1f  jnz     short loc_180002E31
0x180002e21  or      dword ptr [rbx+4], 4
0x180002e25  jmp     short loc_180002E31
0x180002e27  or      dword ptr [rbx+4], 2
0x180002e2b  jmp     short loc_180002E31
0x180002e2d  or      dword ptr [rbx+4], 1
0x180002e31  mov     rbx, [rsp+50h+arg_8]
0x180002e36  mov     rdi, [rsp+50h+arg_10]
0x180002e3b  add     rsp, 50h
0x180002e3f  pop     rbp
0x180002e40  retn
```
