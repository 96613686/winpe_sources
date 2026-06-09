# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180006a30`
- end: `0x180006b58`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `296`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006a30`
- `0x180010310`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006ac9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006ac9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006ae5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006ae5`

## string_xrefs

- `0x180006ac2`: `kernelbase.dll`

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
0x180006a30  mov     [rsp-8+arg_8], rbx
0x180006a35  mov     [rsp-8+arg_10], rsi
0x180006a3a  mov     [rsp-8+arg_18], rdi
0x180006a3f  push    rbp
0x180006a40  mov     rbp, rsp
0x180006a43  sub     rsp, 60h
0x180006a47  mov     rax, cs:__security_cookie
0x180006a4e  xor     rax, rsp
0x180006a51  mov     [rbp+var_8], rax
0x180006a55  mov     rbx, rcx
0x180006a58  xor     esi, esi
0x180006a5a  mov     [rbp+var_3C], esi
0x180006a5d  mov     [rbp+var_2F], sil
0x180006a61  mov     [rbp+var_2C], esi
0x180006a64  mov     [rbp+var_26], si
0x180006a68  mov     eax, [rcx+8]
0x180006a6b  mov     [rbp+var_40], eax
0x180006a6e  mov     rax, [rcx+18h]
0x180006a72  mov     [rbp+var_38], rax
0x180006a76  mov     al, [rcx]
0x180006a78  mov     [rbp+var_30], al
0x180006a7b  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180006a82  mov     [rbp+var_2E], ax
0x180006a86  movzx   eax, word ptr [rcx+40h]
0x180006a8a  mov     [rbp+var_28], ax
0x180006a8e  mov     [rbp+var_24], esi
0x180006a91  mov     rax, [rcx+38h]
0x180006a95  mov     [rbp+var_20], rax
0x180006a99  mov     rax, [rcx+80h]
0x180006aa0  mov     [rbp+var_18], rax
0x180006aa4  mov     [rbp+var_10], rsi
0x180006aa8  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180006aaf  test    rdi, rdi
0x180006ab2  jnz     short loc_180006AFA
0x180006ab4  mov     edi, esi
0x180006ab6  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006abd  test    rax, rax
0x180006ac0  jnz     short loc_180006ADB
0x180006ac2  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006ac9  call    cs:__imp_GetModuleHandleW
0x180006acf  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006ad6  test    rax, rax
0x180006ad9  jz      short loc_180006AEE
0x180006adb  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180006ae2  mov     rcx, rax; hModule
0x180006ae5  call    cs:__imp_GetProcAddress
0x180006aeb  mov     rdi, rax
0x180006aee  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180006af5  test    rdi, rdi
0x180006af8  jz      short loc_180006B0D
0x180006afa  lea     r8, [rbp+var_10]
0x180006afe  lea     rdx, [rbp+var_40]
0x180006b02  xor     ecx, ecx
0x180006b04  mov     rax, rdi
0x180006b07  call    _guard_dispatch_icall
0x180006b0c  nop
0x180006b0d  mov     eax, dword ptr [rbp+var_10]
0x180006b10  mov     [rbx+10h], eax
0x180006b13  movzx   ecx, byte ptr [rbp+var_10+4]
0x180006b17  sub     ecx, 1
0x180006b1a  jz      short loc_180006B32
0x180006b1c  sub     ecx, 1
0x180006b1f  jz      short loc_180006B2C
0x180006b21  cmp     ecx, 1
0x180006b24  jnz     short loc_180006B36
0x180006b26  or      dword ptr [rbx+4], 4
0x180006b2a  jmp     short loc_180006B36
0x180006b2c  or      dword ptr [rbx+4], 2
0x180006b30  jmp     short loc_180006B36
0x180006b32  or      dword ptr [rbx+4], 1
0x180006b36  mov     rcx, [rbp+var_8]
0x180006b3a  xor     rcx, rsp; StackCookie
0x180006b3d  call    __security_check_cookie
0x180006b42  lea     r11, [rsp+60h+var_s0]
0x180006b47  mov     rbx, [r11+18h]
0x180006b4b  mov     rsi, [r11+20h]
0x180006b4f  mov     rdi, [r11+28h]
0x180006b53  mov     rsp, r11
0x180006b56  pop     rbp
0x180006b57  retn
```
