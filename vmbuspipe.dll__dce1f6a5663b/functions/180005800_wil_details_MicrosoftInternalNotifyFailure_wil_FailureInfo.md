# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180005800`
- end: `0x18000592d`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `301`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800024e0`
- `0x180005800`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800058be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800058be`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800058a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800058a2`

## string_xrefs

- `0x18000589b`: `kernelbase.dll`

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
0x180005800  mov     [rsp-8+arg_8], rbx
0x180005805  mov     [rsp-8+arg_10], rdi
0x18000580a  push    rbp
0x18000580b  mov     rbp, rsp
0x18000580e  sub     rsp, 60h
0x180005812  mov     rax, cs:__security_cookie
0x180005819  xor     rax, rsp
0x18000581c  mov     [rbp+var_8], rax
0x180005820  mov     rbx, rcx
0x180005823  mov     [rbp+var_3C], 0
0x18000582a  mov     [rbp+var_2F], 0
0x18000582e  mov     [rbp+var_2C], 0
0x180005835  xor     eax, eax
0x180005837  mov     [rbp+var_26], ax
0x18000583b  mov     eax, [rcx+8]
0x18000583e  mov     [rbp+var_40], eax
0x180005841  mov     rax, [rcx+18h]
0x180005845  mov     [rbp+var_38], rax
0x180005849  mov     al, [rcx]
0x18000584b  mov     [rbp+var_30], al
0x18000584e  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180005855  mov     [rbp+var_2E], ax
0x180005859  movzx   eax, word ptr [rcx+40h]
0x18000585d  mov     [rbp+var_28], ax
0x180005861  mov     [rbp+var_24], 0
0x180005868  mov     rax, [rcx+38h]
0x18000586c  mov     [rbp+var_20], rax
0x180005870  mov     rax, [rcx+80h]
0x180005877  mov     [rbp+var_18], rax
0x18000587b  mov     [rbp+var_10], 0
0x180005883  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000588a  test    rdi, rdi
0x18000588d  jnz     short loc_1800058D3
0x18000588f  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005896  test    rax, rax
0x180005899  jnz     short loc_1800058B4
0x18000589b  lea     rcx, ModuleName; "kernelbase.dll"
0x1800058a2  call    cs:__imp_GetModuleHandleW
0x1800058a8  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800058af  test    rax, rax
0x1800058b2  jz      short loc_1800058C7
0x1800058b4  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1800058bb  mov     rcx, rax; hModule
0x1800058be  call    cs:__imp_GetProcAddress
0x1800058c4  mov     rdi, rax
0x1800058c7  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800058ce  test    rdi, rdi
0x1800058d1  jz      short loc_1800058E6
0x1800058d3  lea     r8, [rbp+var_10]
0x1800058d7  lea     rdx, [rbp+var_40]
0x1800058db  xor     ecx, ecx
0x1800058dd  mov     rax, rdi
0x1800058e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058e5  nop
0x1800058e6  mov     eax, dword ptr [rbp+var_10]
0x1800058e9  mov     [rbx+10h], eax
0x1800058ec  movzx   ecx, byte ptr [rbp+var_10+4]
0x1800058f0  sub     ecx, 1
0x1800058f3  jz      short loc_18000590B
0x1800058f5  sub     ecx, 1
0x1800058f8  jz      short loc_180005905
0x1800058fa  cmp     ecx, 1
0x1800058fd  jnz     short loc_18000590F
0x1800058ff  or      dword ptr [rbx+4], 4
0x180005903  jmp     short loc_18000590F
0x180005905  or      dword ptr [rbx+4], 2
0x180005909  jmp     short loc_18000590F
0x18000590b  or      dword ptr [rbx+4], 1
0x18000590f  mov     rcx, [rbp+var_8]
0x180005913  xor     rcx, rsp; StackCookie
0x180005916  call    __security_check_cookie
0x18000591b  lea     r11, [rsp+60h+var_s0]
0x180005920  mov     rbx, [r11+18h]
0x180005924  mov     rdi, [r11+20h]
0x180005928  mov     rsp, r11
0x18000592b  pop     rbp
0x18000592c  retn
```
