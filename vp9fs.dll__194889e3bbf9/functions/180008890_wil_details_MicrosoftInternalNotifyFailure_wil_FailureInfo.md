# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180008890`
- end: `0x1800089bd`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `301`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004120`
- `0x180008890`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000894e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000894e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008932`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008932`

## string_xrefs

- `0x18000892b`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v6; // [rsp+28h] [rbp-38h]
  char v7; // [rsp+30h] [rbp-30h]
  char v8; // [rsp+31h] [rbp-2Fh]
  __int16 v9; // [rsp+32h] [rbp-2Eh]
  int v10; // [rsp+34h] [rbp-2Ch]
  __int16 v11; // [rsp+38h] [rbp-28h]
  __int16 v12; // [rsp+3Ah] [rbp-26h]
  int v13; // [rsp+3Ch] [rbp-24h]
  __int64 v14; // [rsp+40h] [rbp-20h]
  __int64 v15; // [rsp+48h] [rbp-18h]
  __int64 v16; // [rsp+50h] [rbp-10h] BYREF

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
0x180008890  mov     [rsp-8+arg_8], rbx
0x180008895  mov     [rsp-8+arg_10], rdi
0x18000889a  push    rbp
0x18000889b  mov     rbp, rsp
0x18000889e  sub     rsp, 60h
0x1800088a2  mov     rax, cs:__security_cookie
0x1800088a9  xor     rax, rsp
0x1800088ac  mov     [rbp+var_8], rax
0x1800088b0  mov     rbx, rcx
0x1800088b3  mov     [rbp+var_3C], 0
0x1800088ba  mov     [rbp+var_2F], 0
0x1800088be  mov     [rbp+var_2C], 0
0x1800088c5  xor     eax, eax
0x1800088c7  mov     [rbp+var_26], ax
0x1800088cb  mov     eax, [rcx+8]
0x1800088ce  mov     [rbp+var_40], eax
0x1800088d1  mov     rax, [rcx+18h]
0x1800088d5  mov     [rbp+var_38], rax
0x1800088d9  mov     al, [rcx]
0x1800088db  mov     [rbp+var_30], al
0x1800088de  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1800088e5  mov     [rbp+var_2E], ax
0x1800088e9  movzx   eax, word ptr [rcx+40h]
0x1800088ed  mov     [rbp+var_28], ax
0x1800088f1  mov     [rbp+var_24], 0
0x1800088f8  mov     rax, [rcx+38h]
0x1800088fc  mov     [rbp+var_20], rax
0x180008900  mov     rax, [rcx+80h]
0x180008907  mov     [rbp+var_18], rax
0x18000890b  mov     [rbp+var_10], 0
0x180008913  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000891a  test    rdi, rdi
0x18000891d  jnz     short loc_180008963
0x18000891f  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008926  test    rax, rax
0x180008929  jnz     short loc_180008944
0x18000892b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008932  call    cs:__imp_GetModuleHandleW
0x180008938  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000893f  test    rax, rax
0x180008942  jz      short loc_180008957
0x180008944  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000894b  mov     rcx, rax; hModule
0x18000894e  call    cs:__imp_GetProcAddress
0x180008954  mov     rdi, rax
0x180008957  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000895e  test    rdi, rdi
0x180008961  jz      short loc_180008976
0x180008963  lea     r8, [rbp+var_10]
0x180008967  lea     rdx, [rbp+var_40]
0x18000896b  xor     ecx, ecx
0x18000896d  mov     rax, rdi
0x180008970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008975  nop
0x180008976  mov     eax, dword ptr [rbp+var_10]
0x180008979  mov     [rbx+10h], eax
0x18000897c  movzx   ecx, byte ptr [rbp+var_10+4]
0x180008980  sub     ecx, 1
0x180008983  jz      short loc_18000899B
0x180008985  sub     ecx, 1
0x180008988  jz      short loc_180008995
0x18000898a  cmp     ecx, 1
0x18000898d  jnz     short loc_18000899F
0x18000898f  or      dword ptr [rbx+4], 4
0x180008993  jmp     short loc_18000899F
0x180008995  or      dword ptr [rbx+4], 2
0x180008999  jmp     short loc_18000899F
0x18000899b  or      dword ptr [rbx+4], 1
0x18000899f  mov     rcx, [rbp+var_8]
0x1800089a3  xor     rcx, rsp; StackCookie
0x1800089a6  call    __security_check_cookie
0x1800089ab  lea     r11, [rsp+60h+var_s0]
0x1800089b0  mov     rbx, [r11+18h]
0x1800089b4  mov     rdi, [r11+20h]
0x1800089b8  mov     rsp, r11
0x1800089bb  pop     rbp
0x1800089bc  retn
```
