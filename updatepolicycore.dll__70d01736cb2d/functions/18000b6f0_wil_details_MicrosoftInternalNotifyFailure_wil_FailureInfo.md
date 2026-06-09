# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18000b6f0`
- end: `0x18000b818`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `296`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b6f0`
- `0x18002ffd0`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b789`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b789`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b7a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b7a5`

## string_xrefs

- `0x18000b782`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
  ProcAddress = 0;
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
0x18000b6f0  mov     [rsp-8+arg_8], rbx
0x18000b6f5  mov     [rsp-8+arg_10], rsi
0x18000b6fa  mov     [rsp-8+arg_18], rdi
0x18000b6ff  push    rbp
0x18000b700  mov     rbp, rsp
0x18000b703  sub     rsp, 60h
0x18000b707  mov     rax, cs:__security_cookie
0x18000b70e  xor     rax, rsp
0x18000b711  mov     [rbp+var_8], rax
0x18000b715  mov     rbx, rcx
0x18000b718  xor     esi, esi
0x18000b71a  mov     [rbp+var_3C], esi
0x18000b71d  mov     [rbp+var_2F], sil
0x18000b721  mov     [rbp+var_2C], esi
0x18000b724  mov     [rbp+var_26], si
0x18000b728  mov     eax, [rcx+8]
0x18000b72b  mov     [rbp+var_40], eax
0x18000b72e  mov     rax, [rcx+18h]
0x18000b732  mov     [rbp+var_38], rax
0x18000b736  mov     al, [rcx]
0x18000b738  mov     [rbp+var_30], al
0x18000b73b  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000b742  mov     [rbp+var_2E], ax
0x18000b746  movzx   eax, word ptr [rcx+40h]
0x18000b74a  mov     [rbp+var_28], ax
0x18000b74e  mov     [rbp+var_24], esi
0x18000b751  mov     rax, [rcx+38h]
0x18000b755  mov     [rbp+var_20], rax
0x18000b759  mov     rax, [rcx+80h]
0x18000b760  mov     [rbp+var_18], rax
0x18000b764  mov     [rbp+var_10], rsi
0x18000b768  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000b76f  test    rdi, rdi
0x18000b772  jnz     short loc_18000B7BA
0x18000b774  mov     edi, esi
0x18000b776  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b77d  test    rax, rax
0x18000b780  jnz     short loc_18000B79B
0x18000b782  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000b789  call    cs:__imp_GetModuleHandleW
0x18000b78f  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b796  test    rax, rax
0x18000b799  jz      short loc_18000B7AE
0x18000b79b  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000b7a2  mov     rcx, rax; hModule
0x18000b7a5  call    cs:__imp_GetProcAddress
0x18000b7ab  mov     rdi, rax
0x18000b7ae  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000b7b5  test    rdi, rdi
0x18000b7b8  jz      short loc_18000B7CD
0x18000b7ba  lea     r8, [rbp+var_10]
0x18000b7be  lea     rdx, [rbp+var_40]
0x18000b7c2  xor     ecx, ecx
0x18000b7c4  mov     rax, rdi
0x18000b7c7  call    _guard_dispatch_icall
0x18000b7cc  nop
0x18000b7cd  mov     eax, dword ptr [rbp+var_10]
0x18000b7d0  mov     [rbx+10h], eax
0x18000b7d3  movzx   ecx, byte ptr [rbp+var_10+4]
0x18000b7d7  sub     ecx, 1
0x18000b7da  jz      short loc_18000B7F2
0x18000b7dc  sub     ecx, 1
0x18000b7df  jz      short loc_18000B7EC
0x18000b7e1  cmp     ecx, 1
0x18000b7e4  jnz     short loc_18000B7F6
0x18000b7e6  or      dword ptr [rbx+4], 4
0x18000b7ea  jmp     short loc_18000B7F6
0x18000b7ec  or      dword ptr [rbx+4], 2
0x18000b7f0  jmp     short loc_18000B7F6
0x18000b7f2  or      dword ptr [rbx+4], 1
0x18000b7f6  mov     rcx, [rbp+var_8]
0x18000b7fa  xor     rcx, rsp; StackCookie
0x18000b7fd  call    __security_check_cookie
0x18000b802  lea     r11, [rsp+60h+var_s0]
0x18000b807  mov     rbx, [r11+18h]
0x18000b80b  mov     rsi, [r11+20h]
0x18000b80f  mov     rdi, [r11+28h]
0x18000b813  mov     rsp, r11
0x18000b816  pop     rbp
0x18000b817  retn
```
