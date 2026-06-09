# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18000e270`
- end: `0x18000e381`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e270`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000e304`
- `KERNEL32!GetModuleHandleW` at `0x18000e304`
- `KERNEL32!GetProcAddress` at `0x18000e320`
- `KERNEL32!GetProcAddress` at `0x18000e320`

## string_xrefs

- `0x18000e2fd`: `kernelbase.dll`

## pseudocode

```c
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
0x18000e270  mov     [rsp-8+arg_8], rbx
0x18000e275  mov     [rsp-8+arg_10], rdi
0x18000e27a  push    rbp
0x18000e27b  mov     rbp, rsp
0x18000e27e  sub     rsp, 50h
0x18000e282  mov     rbx, rcx
0x18000e285  mov     [rbp+var_2C], 0
0x18000e28c  mov     [rbp+var_1F], 0
0x18000e290  mov     [rbp+var_1C], 0
0x18000e297  xor     eax, eax
0x18000e299  mov     [rbp+var_16], ax
0x18000e29d  mov     eax, [rcx+8]
0x18000e2a0  mov     [rbp+var_30], eax
0x18000e2a3  mov     rax, [rcx+18h]
0x18000e2a7  mov     [rbp+var_28], rax
0x18000e2ab  mov     al, [rcx]
0x18000e2ad  mov     [rbp+var_20], al
0x18000e2b0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000e2b7  mov     [rbp+var_1E], ax
0x18000e2bb  movzx   eax, word ptr [rcx+40h]
0x18000e2bf  mov     [rbp+var_18], ax
0x18000e2c3  mov     [rbp+var_14], 0
0x18000e2ca  mov     rax, [rcx+38h]
0x18000e2ce  mov     [rbp+var_10], rax
0x18000e2d2  mov     rax, [rcx+80h]
0x18000e2d9  mov     [rbp+var_8], rax
0x18000e2dd  mov     [rbp+arg_0], 0
0x18000e2e5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000e2ec  test    rdi, rdi
0x18000e2ef  jnz     short loc_18000E335
0x18000e2f1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e2f8  test    rax, rax
0x18000e2fb  jnz     short loc_18000E316
0x18000e2fd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000e304  call    cs:__imp_GetModuleHandleW
0x18000e30a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e311  test    rax, rax
0x18000e314  jz      short loc_18000E329
0x18000e316  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000e31d  mov     rcx, rax; hModule
0x18000e320  call    cs:__imp_GetProcAddress
0x18000e326  mov     rdi, rax
0x18000e329  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000e330  test    rdi, rdi
0x18000e333  jz      short loc_18000E348
0x18000e335  lea     r8, [rbp+arg_0]
0x18000e339  lea     rdx, [rbp+var_30]
0x18000e33d  xor     ecx, ecx
0x18000e33f  mov     rax, rdi
0x18000e342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e347  nop
0x18000e348  mov     eax, dword ptr [rbp+arg_0]
0x18000e34b  mov     [rbx+10h], eax
0x18000e34e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000e352  sub     ecx, 1
0x18000e355  jz      short loc_18000E36D
0x18000e357  sub     ecx, 1
0x18000e35a  jz      short loc_18000E367
0x18000e35c  cmp     ecx, 1
0x18000e35f  jnz     short loc_18000E371
0x18000e361  or      dword ptr [rbx+4], 4
0x18000e365  jmp     short loc_18000E371
0x18000e367  or      dword ptr [rbx+4], 2
0x18000e36b  jmp     short loc_18000E371
0x18000e36d  or      dword ptr [rbx+4], 1
0x18000e371  mov     rbx, [rsp+50h+arg_8]
0x18000e376  mov     rdi, [rsp+50h+arg_10]
0x18000e37b  add     rsp, 50h
0x18000e37f  pop     rbp
0x18000e380  retn
```
