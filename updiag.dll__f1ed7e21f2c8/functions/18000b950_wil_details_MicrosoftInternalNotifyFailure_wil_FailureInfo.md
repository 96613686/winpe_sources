# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18000b950`
- end: `0x18000ba78`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `296`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b950`
- `0x18008fe00`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b9e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b9e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ba05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ba05`

## string_xrefs

- `0x18000b9e2`: `kernelbase.dll`

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
0x18000b950  mov     [rsp-8+arg_8], rbx
0x18000b955  mov     [rsp-8+arg_10], rsi
0x18000b95a  mov     [rsp-8+arg_18], rdi
0x18000b95f  push    rbp
0x18000b960  mov     rbp, rsp
0x18000b963  sub     rsp, 60h
0x18000b967  mov     rax, cs:__security_cookie
0x18000b96e  xor     rax, rsp
0x18000b971  mov     [rbp+var_8], rax
0x18000b975  mov     rbx, rcx
0x18000b978  xor     esi, esi
0x18000b97a  mov     [rbp+var_3C], esi
0x18000b97d  mov     [rbp+var_2F], sil
0x18000b981  mov     [rbp+var_2C], esi
0x18000b984  mov     [rbp+var_26], si
0x18000b988  mov     eax, [rcx+8]
0x18000b98b  mov     [rbp+var_40], eax
0x18000b98e  mov     rax, [rcx+18h]
0x18000b992  mov     [rbp+var_38], rax
0x18000b996  mov     al, [rcx]
0x18000b998  mov     [rbp+var_30], al
0x18000b99b  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000b9a2  mov     [rbp+var_2E], ax
0x18000b9a6  movzx   eax, word ptr [rcx+40h]
0x18000b9aa  mov     [rbp+var_28], ax
0x18000b9ae  mov     [rbp+var_24], esi
0x18000b9b1  mov     rax, [rcx+38h]
0x18000b9b5  mov     [rbp+var_20], rax
0x18000b9b9  mov     rax, [rcx+80h]
0x18000b9c0  mov     [rbp+var_18], rax
0x18000b9c4  mov     [rbp+var_10], rsi
0x18000b9c8  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000b9cf  test    rdi, rdi
0x18000b9d2  jnz     short loc_18000BA1A
0x18000b9d4  mov     edi, esi
0x18000b9d6  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b9dd  test    rax, rax
0x18000b9e0  jnz     short loc_18000B9FB
0x18000b9e2  lea     rcx, ModuleName; "kernelbase.dll"
0x18000b9e9  call    cs:__imp_GetModuleHandleW
0x18000b9ef  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b9f6  test    rax, rax
0x18000b9f9  jz      short loc_18000BA0E
0x18000b9fb  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000ba02  mov     rcx, rax; hModule
0x18000ba05  call    cs:__imp_GetProcAddress
0x18000ba0b  mov     rdi, rax
0x18000ba0e  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000ba15  test    rdi, rdi
0x18000ba18  jz      short loc_18000BA2D
0x18000ba1a  lea     r8, [rbp+var_10]
0x18000ba1e  lea     rdx, [rbp+var_40]
0x18000ba22  xor     ecx, ecx
0x18000ba24  mov     rax, rdi
0x18000ba27  call    _guard_dispatch_icall
0x18000ba2c  nop
0x18000ba2d  mov     eax, dword ptr [rbp+var_10]
0x18000ba30  mov     [rbx+10h], eax
0x18000ba33  movzx   ecx, byte ptr [rbp+var_10+4]
0x18000ba37  sub     ecx, 1
0x18000ba3a  jz      short loc_18000BA52
0x18000ba3c  sub     ecx, 1
0x18000ba3f  jz      short loc_18000BA4C
0x18000ba41  cmp     ecx, 1
0x18000ba44  jnz     short loc_18000BA56
0x18000ba46  or      dword ptr [rbx+4], 4
0x18000ba4a  jmp     short loc_18000BA56
0x18000ba4c  or      dword ptr [rbx+4], 2
0x18000ba50  jmp     short loc_18000BA56
0x18000ba52  or      dword ptr [rbx+4], 1
0x18000ba56  mov     rcx, [rbp+var_8]
0x18000ba5a  xor     rcx, rsp; StackCookie
0x18000ba5d  call    __security_check_cookie
0x18000ba62  lea     r11, [rsp+60h+var_s0]
0x18000ba67  mov     rbx, [r11+18h]
0x18000ba6b  mov     rsi, [r11+20h]
0x18000ba6f  mov     rdi, [r11+28h]
0x18000ba73  mov     rsp, r11
0x18000ba76  pop     rbp
0x18000ba77  retn
```
