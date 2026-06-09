# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180004310`
- end: `0x180004438`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `296`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004310`
- `0x18000fce0`
- `0x180015a00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800043a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800043a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800043c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800043c5`

## string_xrefs

- `0x1800043a2`: `kernelbase.dll`

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
0x180004310  mov     [rsp-8+arg_8], rbx
0x180004315  mov     [rsp-8+arg_10], rsi
0x18000431a  mov     [rsp-8+arg_18], rdi
0x18000431f  push    rbp
0x180004320  mov     rbp, rsp
0x180004323  sub     rsp, 60h
0x180004327  mov     rax, cs:__security_cookie
0x18000432e  xor     rax, rsp
0x180004331  mov     [rbp+var_8], rax
0x180004335  mov     rbx, rcx
0x180004338  xor     esi, esi
0x18000433a  mov     [rbp+var_3C], esi
0x18000433d  mov     [rbp+var_2F], sil
0x180004341  mov     [rbp+var_2C], esi
0x180004344  mov     [rbp+var_26], si
0x180004348  mov     eax, [rcx+8]
0x18000434b  mov     [rbp+var_40], eax
0x18000434e  mov     rax, [rcx+18h]
0x180004352  mov     [rbp+var_38], rax
0x180004356  mov     al, [rcx]
0x180004358  mov     [rbp+var_30], al
0x18000435b  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180004362  mov     [rbp+var_2E], ax
0x180004366  movzx   eax, word ptr [rcx+40h]
0x18000436a  mov     [rbp+var_28], ax
0x18000436e  mov     [rbp+var_24], esi
0x180004371  mov     rax, [rcx+38h]
0x180004375  mov     [rbp+var_20], rax
0x180004379  mov     rax, [rcx+80h]
0x180004380  mov     [rbp+var_18], rax
0x180004384  mov     [rbp+var_10], rsi
0x180004388  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000438f  test    rdi, rdi
0x180004392  jnz     short loc_1800043DA
0x180004394  mov     edi, esi
0x180004396  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000439d  test    rax, rax
0x1800043a0  jnz     short loc_1800043BB
0x1800043a2  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800043a9  call    cs:__imp_GetModuleHandleW
0x1800043af  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800043b6  test    rax, rax
0x1800043b9  jz      short loc_1800043CE
0x1800043bb  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800043c2  mov     rcx, rax; hModule
0x1800043c5  call    cs:__imp_GetProcAddress
0x1800043cb  mov     rdi, rax
0x1800043ce  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800043d5  test    rdi, rdi
0x1800043d8  jz      short loc_1800043ED
0x1800043da  lea     r8, [rbp+var_10]
0x1800043de  lea     rdx, [rbp+var_40]
0x1800043e2  xor     ecx, ecx
0x1800043e4  mov     rax, rdi
0x1800043e7  call    _guard_dispatch_icall
0x1800043ec  nop
0x1800043ed  mov     eax, dword ptr [rbp+var_10]
0x1800043f0  mov     [rbx+10h], eax
0x1800043f3  movzx   ecx, byte ptr [rbp+var_10+4]
0x1800043f7  sub     ecx, 1
0x1800043fa  jz      short loc_180004412
0x1800043fc  sub     ecx, 1
0x1800043ff  jz      short loc_18000440C
0x180004401  cmp     ecx, 1
0x180004404  jnz     short loc_180004416
0x180004406  or      dword ptr [rbx+4], 4
0x18000440a  jmp     short loc_180004416
0x18000440c  or      dword ptr [rbx+4], 2
0x180004410  jmp     short loc_180004416
0x180004412  or      dword ptr [rbx+4], 1
0x180004416  mov     rcx, [rbp+var_8]
0x18000441a  xor     rcx, rsp; StackCookie
0x18000441d  call    __security_check_cookie
0x180004422  lea     r11, [rsp+60h+var_s0]
0x180004427  mov     rbx, [r11+18h]
0x18000442b  mov     rsi, [r11+20h]
0x18000442f  mov     rdi, [r11+28h]
0x180004433  mov     rsp, r11
0x180004436  pop     rbp
0x180004437  retn
```
