# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1800038f0`
- end: `0x180003a18`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `296`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800038f0`
- `0x18000fc90`
- `0x1800159b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800039a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800039a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003989`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003989`

## string_xrefs

- `0x180003982`: `kernelbase.dll`

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
0x1800038f0  mov     [rsp-8+arg_8], rbx
0x1800038f5  mov     [rsp-8+arg_10], rsi
0x1800038fa  mov     [rsp-8+arg_18], rdi
0x1800038ff  push    rbp
0x180003900  mov     rbp, rsp
0x180003903  sub     rsp, 60h
0x180003907  mov     rax, cs:__security_cookie
0x18000390e  xor     rax, rsp
0x180003911  mov     [rbp+var_8], rax
0x180003915  mov     rbx, rcx
0x180003918  xor     esi, esi
0x18000391a  mov     [rbp+var_3C], esi
0x18000391d  mov     [rbp+var_2F], sil
0x180003921  mov     [rbp+var_2C], esi
0x180003924  mov     [rbp+var_26], si
0x180003928  mov     eax, [rcx+8]
0x18000392b  mov     [rbp+var_40], eax
0x18000392e  mov     rax, [rcx+18h]
0x180003932  mov     [rbp+var_38], rax
0x180003936  mov     al, [rcx]
0x180003938  mov     [rbp+var_30], al
0x18000393b  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180003942  mov     [rbp+var_2E], ax
0x180003946  movzx   eax, word ptr [rcx+40h]
0x18000394a  mov     [rbp+var_28], ax
0x18000394e  mov     [rbp+var_24], esi
0x180003951  mov     rax, [rcx+38h]
0x180003955  mov     [rbp+var_20], rax
0x180003959  mov     rax, [rcx+80h]
0x180003960  mov     [rbp+var_18], rax
0x180003964  mov     [rbp+var_10], rsi
0x180003968  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000396f  test    rdi, rdi
0x180003972  jnz     short loc_1800039BA
0x180003974  mov     edi, esi
0x180003976  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000397d  test    rax, rax
0x180003980  jnz     short loc_18000399B
0x180003982  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180003989  call    cs:__imp_GetModuleHandleW
0x18000398f  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180003996  test    rax, rax
0x180003999  jz      short loc_1800039AE
0x18000399b  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800039a2  mov     rcx, rax; hModule
0x1800039a5  call    cs:__imp_GetProcAddress
0x1800039ab  mov     rdi, rax
0x1800039ae  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800039b5  test    rdi, rdi
0x1800039b8  jz      short loc_1800039CD
0x1800039ba  lea     r8, [rbp+var_10]
0x1800039be  lea     rdx, [rbp+var_40]
0x1800039c2  xor     ecx, ecx
0x1800039c4  mov     rax, rdi
0x1800039c7  call    _guard_dispatch_icall
0x1800039cc  nop
0x1800039cd  mov     eax, dword ptr [rbp+var_10]
0x1800039d0  mov     [rbx+10h], eax
0x1800039d3  movzx   ecx, byte ptr [rbp+var_10+4]
0x1800039d7  sub     ecx, 1
0x1800039da  jz      short loc_1800039F2
0x1800039dc  sub     ecx, 1
0x1800039df  jz      short loc_1800039EC
0x1800039e1  cmp     ecx, 1
0x1800039e4  jnz     short loc_1800039F6
0x1800039e6  or      dword ptr [rbx+4], 4
0x1800039ea  jmp     short loc_1800039F6
0x1800039ec  or      dword ptr [rbx+4], 2
0x1800039f0  jmp     short loc_1800039F6
0x1800039f2  or      dword ptr [rbx+4], 1
0x1800039f6  mov     rcx, [rbp+var_8]
0x1800039fa  xor     rcx, rsp; StackCookie
0x1800039fd  call    __security_check_cookie
0x180003a02  lea     r11, [rsp+60h+var_s0]
0x180003a07  mov     rbx, [r11+18h]
0x180003a0b  mov     rsi, [r11+20h]
0x180003a0f  mov     rdi, [r11+28h]
0x180003a13  mov     rsp, r11
0x180003a16  pop     rbp
0x180003a17  retn
```
