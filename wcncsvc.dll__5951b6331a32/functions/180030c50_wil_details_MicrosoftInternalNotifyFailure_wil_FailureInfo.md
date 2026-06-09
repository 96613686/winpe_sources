# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180030c50`
- end: `0x180030d61`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180030c50`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030d00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030d00`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030ce4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030ce4`

## string_xrefs

- `0x180030cdd`: `kernelbase.dll`

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
0x180030c50  mov     [rsp-8+arg_8], rbx
0x180030c55  mov     [rsp-8+arg_10], rdi
0x180030c5a  push    rbp
0x180030c5b  mov     rbp, rsp
0x180030c5e  sub     rsp, 50h
0x180030c62  mov     rbx, rcx
0x180030c65  mov     [rbp+var_2C], 0
0x180030c6c  mov     [rbp+var_1F], 0
0x180030c70  mov     [rbp+var_1C], 0
0x180030c77  xor     eax, eax
0x180030c79  mov     [rbp+var_16], ax
0x180030c7d  mov     eax, [rcx+8]
0x180030c80  mov     [rbp+var_30], eax
0x180030c83  mov     rax, [rcx+18h]
0x180030c87  mov     [rbp+var_28], rax
0x180030c8b  mov     al, [rcx]
0x180030c8d  mov     [rbp+var_20], al
0x180030c90  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180030c97  mov     [rbp+var_1E], ax
0x180030c9b  movzx   eax, word ptr [rcx+40h]
0x180030c9f  mov     [rbp+var_18], ax
0x180030ca3  mov     [rbp+var_14], 0
0x180030caa  mov     rax, [rcx+38h]
0x180030cae  mov     [rbp+var_10], rax
0x180030cb2  mov     rax, [rcx+80h]
0x180030cb9  mov     [rbp+var_8], rax
0x180030cbd  mov     [rbp+arg_0], 0
0x180030cc5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180030ccc  test    rdi, rdi
0x180030ccf  jnz     short loc_180030D15
0x180030cd1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180030cd8  test    rax, rax
0x180030cdb  jnz     short loc_180030CF6
0x180030cdd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180030ce4  call    cs:__imp_GetModuleHandleW
0x180030cea  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180030cf1  test    rax, rax
0x180030cf4  jz      short loc_180030D09
0x180030cf6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180030cfd  mov     rcx, rax; hModule
0x180030d00  call    cs:__imp_GetProcAddress
0x180030d06  mov     rdi, rax
0x180030d09  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180030d10  test    rdi, rdi
0x180030d13  jz      short loc_180030D28
0x180030d15  lea     r8, [rbp+arg_0]
0x180030d19  lea     rdx, [rbp+var_30]
0x180030d1d  xor     ecx, ecx
0x180030d1f  mov     rax, rdi
0x180030d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d27  nop
0x180030d28  mov     eax, dword ptr [rbp+arg_0]
0x180030d2b  mov     [rbx+10h], eax
0x180030d2e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180030d32  sub     ecx, 1
0x180030d35  jz      short loc_180030D4D
0x180030d37  sub     ecx, 1
0x180030d3a  jz      short loc_180030D47
0x180030d3c  cmp     ecx, 1
0x180030d3f  jnz     short loc_180030D51
0x180030d41  or      dword ptr [rbx+4], 4
0x180030d45  jmp     short loc_180030D51
0x180030d47  or      dword ptr [rbx+4], 2
0x180030d4b  jmp     short loc_180030D51
0x180030d4d  or      dword ptr [rbx+4], 1
0x180030d51  mov     rbx, [rsp+50h+arg_8]
0x180030d56  mov     rdi, [rsp+50h+arg_10]
0x180030d5b  add     rsp, 50h
0x180030d5f  pop     rbp
0x180030d60  retn
```
