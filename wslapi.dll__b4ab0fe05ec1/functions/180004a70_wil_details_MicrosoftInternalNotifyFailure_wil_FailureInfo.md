# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180004a70`
- end: `0x180004b9d`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `301`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180004a70`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004b12`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004b12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004b2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004b2e`

## string_xrefs

- `0x180004b0b`: `kernelbase.dll`

## pseudocode

```c
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
0x180004a70  mov     [rsp-8+arg_8], rbx
0x180004a75  mov     [rsp-8+arg_10], rdi
0x180004a7a  push    rbp
0x180004a7b  mov     rbp, rsp
0x180004a7e  sub     rsp, 60h
0x180004a82  mov     rax, cs:__security_cookie
0x180004a89  xor     rax, rsp
0x180004a8c  mov     [rbp+var_8], rax
0x180004a90  mov     rbx, rcx
0x180004a93  mov     [rbp+var_3C], 0
0x180004a9a  mov     [rbp+var_2F], 0
0x180004a9e  mov     [rbp+var_2C], 0
0x180004aa5  xor     eax, eax
0x180004aa7  mov     [rbp+var_26], ax
0x180004aab  mov     eax, [rcx+8]
0x180004aae  mov     [rbp+var_40], eax
0x180004ab1  mov     rax, [rcx+18h]
0x180004ab5  mov     [rbp+var_38], rax
0x180004ab9  mov     al, [rcx]
0x180004abb  mov     [rbp+var_30], al
0x180004abe  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180004ac5  mov     [rbp+var_2E], ax
0x180004ac9  movzx   eax, word ptr [rcx+40h]
0x180004acd  mov     [rbp+var_28], ax
0x180004ad1  mov     [rbp+var_24], 0
0x180004ad8  mov     rax, [rcx+38h]
0x180004adc  mov     [rbp+var_20], rax
0x180004ae0  mov     rax, [rcx+80h]
0x180004ae7  mov     [rbp+var_18], rax
0x180004aeb  mov     [rbp+var_10], 0
0x180004af3  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180004afa  test    rdi, rdi
0x180004afd  jnz     short loc_180004B43
0x180004aff  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004b06  test    rax, rax
0x180004b09  jnz     short loc_180004B24
0x180004b0b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180004b12  call    cs:__imp_GetModuleHandleW
0x180004b18  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004b1f  test    rax, rax
0x180004b22  jz      short loc_180004B37
0x180004b24  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180004b2b  mov     rcx, rax; hModule
0x180004b2e  call    cs:__imp_GetProcAddress
0x180004b34  mov     rdi, rax
0x180004b37  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180004b3e  test    rdi, rdi
0x180004b41  jz      short loc_180004B56
0x180004b43  lea     r8, [rbp+var_10]
0x180004b47  lea     rdx, [rbp+var_40]
0x180004b4b  xor     ecx, ecx
0x180004b4d  mov     rax, rdi
0x180004b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b55  nop
0x180004b56  mov     eax, dword ptr [rbp+var_10]
0x180004b59  mov     [rbx+10h], eax
0x180004b5c  movzx   ecx, byte ptr [rbp+var_10+4]
0x180004b60  sub     ecx, 1
0x180004b63  jz      short loc_180004B7B
0x180004b65  sub     ecx, 1
0x180004b68  jz      short loc_180004B75
0x180004b6a  cmp     ecx, 1
0x180004b6d  jnz     short loc_180004B7F
0x180004b6f  or      dword ptr [rbx+4], 4
0x180004b73  jmp     short loc_180004B7F
0x180004b75  or      dword ptr [rbx+4], 2
0x180004b79  jmp     short loc_180004B7F
0x180004b7b  or      dword ptr [rbx+4], 1
0x180004b7f  mov     rcx, [rbp+var_8]
0x180004b83  xor     rcx, rsp; StackCookie
0x180004b86  call    __security_check_cookie
0x180004b8b  lea     r11, [rsp+60h+var_s0]
0x180004b90  mov     rbx, [r11+18h]
0x180004b94  mov     rdi, [r11+20h]
0x180004b98  mov     rsp, r11
0x180004b9b  pop     rbp
0x180004b9c  retn
```
