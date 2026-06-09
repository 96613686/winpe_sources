# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140004a10`
- end: `0x140004b38`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `296`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004a10`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004ac5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004ac5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004aa9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004aa9`

## string_xrefs

- `0x140004aa2`: `kernelbase.dll`

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
0x140004a10  mov     [rsp-8+arg_8], rbx
0x140004a15  mov     [rsp-8+arg_10], rsi
0x140004a1a  mov     [rsp-8+arg_18], rdi
0x140004a1f  push    rbp
0x140004a20  mov     rbp, rsp
0x140004a23  sub     rsp, 60h
0x140004a27  mov     rax, cs:__security_cookie
0x140004a2e  xor     rax, rsp
0x140004a31  mov     [rbp+var_8], rax
0x140004a35  mov     rbx, rcx
0x140004a38  xor     esi, esi
0x140004a3a  mov     [rbp+var_3C], esi
0x140004a3d  mov     [rbp+var_2F], sil
0x140004a41  mov     [rbp+var_2C], esi
0x140004a44  mov     [rbp+var_26], si
0x140004a48  mov     eax, [rcx+8]
0x140004a4b  mov     [rbp+var_40], eax
0x140004a4e  mov     rax, [rcx+18h]
0x140004a52  mov     [rbp+var_38], rax
0x140004a56  mov     al, [rcx]
0x140004a58  mov     [rbp+var_30], al
0x140004a5b  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140004a62  mov     [rbp+var_2E], ax
0x140004a66  movzx   eax, word ptr [rcx+40h]
0x140004a6a  mov     [rbp+var_28], ax
0x140004a6e  mov     [rbp+var_24], esi
0x140004a71  mov     rax, [rcx+38h]
0x140004a75  mov     [rbp+var_20], rax
0x140004a79  mov     rax, [rcx+80h]
0x140004a80  mov     [rbp+var_18], rax
0x140004a84  mov     [rbp+var_10], rsi
0x140004a88  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140004a8f  test    rdi, rdi
0x140004a92  jnz     short loc_140004ADA
0x140004a94  mov     edi, esi
0x140004a96  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140004a9d  test    rax, rax
0x140004aa0  jnz     short loc_140004ABB
0x140004aa2  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140004aa9  call    cs:__imp_GetModuleHandleW
0x140004aaf  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140004ab6  test    rax, rax
0x140004ab9  jz      short loc_140004ACE
0x140004abb  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x140004ac2  mov     rcx, rax; hModule
0x140004ac5  call    cs:__imp_GetProcAddress
0x140004acb  mov     rdi, rax
0x140004ace  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140004ad5  test    rdi, rdi
0x140004ad8  jz      short loc_140004AED
0x140004ada  lea     r8, [rbp+var_10]
0x140004ade  lea     rdx, [rbp+var_40]
0x140004ae2  xor     ecx, ecx
0x140004ae4  mov     rax, rdi
0x140004ae7  call    _guard_dispatch_icall
0x140004aec  nop
0x140004aed  mov     eax, dword ptr [rbp+var_10]
0x140004af0  mov     [rbx+10h], eax
0x140004af3  movzx   ecx, byte ptr [rbp+var_10+4]
0x140004af7  sub     ecx, 1
0x140004afa  jz      short loc_140004B12
0x140004afc  sub     ecx, 1
0x140004aff  jz      short loc_140004B0C
0x140004b01  cmp     ecx, 1
0x140004b04  jnz     short loc_140004B16
0x140004b06  or      dword ptr [rbx+4], 4
0x140004b0a  jmp     short loc_140004B16
0x140004b0c  or      dword ptr [rbx+4], 2
0x140004b10  jmp     short loc_140004B16
0x140004b12  or      dword ptr [rbx+4], 1
0x140004b16  mov     rcx, [rbp+var_8]
0x140004b1a  xor     rcx, rsp; StackCookie
0x140004b1d  call    __security_check_cookie
0x140004b22  lea     r11, [rsp+60h+var_s0]
0x140004b27  mov     rbx, [r11+18h]
0x140004b2b  mov     rsi, [r11+20h]
0x140004b2f  mov     rdi, [r11+28h]
0x140004b33  mov     rsp, r11
0x140004b36  pop     rbp
0x140004b37  retn
```
