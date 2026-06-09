# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18000d810`
- end: `0x18000d93c`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `300`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d810`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000d8ce`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000d8ce`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000d8b2`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000d8b2`

## string_xrefs

- `0x18000d8ab`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  _DWORD v8[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v9; // [rsp+28h] [rbp-38h]
  char v10; // [rsp+30h] [rbp-30h]
  char v11; // [rsp+31h] [rbp-2Fh]
  __int16 v12; // [rsp+32h] [rbp-2Eh]
  int v13; // [rsp+34h] [rbp-2Ch]
  __int16 v14; // [rsp+38h] [rbp-28h]
  __int16 v15; // [rsp+3Ah] [rbp-26h]
  int v16; // [rsp+3Ch] [rbp-24h]
  __int64 v17; // [rsp+40h] [rbp-20h]
  __int64 v18; // [rsp+48h] [rbp-18h]
  __int64 v19; // [rsp+50h] [rbp-10h] BYREF

  ProcAddress = (FARPROC)`wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers;
  v15 = 0;
  v8[0] = *((_DWORD *)this + 2);
  v9 = *((_QWORD *)this + 3);
  v10 = *(_BYTE *)this;
  v12 = wil::g_moduleFailureReportFlags;
  v14 = *((_WORD *)this + 32);
  v17 = *((_QWORD *)this + 7);
  v18 = *((_QWORD *)this + 16);
  v8[1] = 0;
  v11 = 0;
  v13 = 0;
  v16 = 0;
  v19 = 0;
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
    ((void (__fastcall *)(_QWORD, _DWORD *, __int64 *))ProcAddress)(0, v8, &v19);
  v5 = BYTE4(v19);
  *((_DWORD *)this + 4) = v19;
  v6 = v5 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
        *((_DWORD *)this + 1) |= 4u;
    }
    else
    {
      *((_DWORD *)this + 1) |= 2u;
    }
  }
  else
  {
    *((_DWORD *)this + 1) |= 1u;
  }
}

```

## disassembly

```asm
0x18000d810  mov     [rsp-8+arg_8], rbx
0x18000d815  mov     [rsp-8+arg_10], rdi
0x18000d81a  push    rbp
0x18000d81b  mov     rbp, rsp
0x18000d81e  sub     rsp, 60h
0x18000d822  mov     rax, cs:__security_cookie
0x18000d829  xor     rax, rsp
0x18000d82c  mov     [rbp+var_8], rax
0x18000d830  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000d837  xor     eax, eax
0x18000d839  mov     [rbp+var_26], ax
0x18000d83d  mov     rbx, rcx
0x18000d840  mov     eax, [rcx+8]
0x18000d843  mov     [rbp+var_40], eax
0x18000d846  mov     rax, [rcx+18h]
0x18000d84a  mov     [rbp+var_38], rax
0x18000d84e  mov     al, [rcx]
0x18000d850  mov     [rbp+var_30], al
0x18000d853  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000d85a  mov     [rbp+var_2E], ax
0x18000d85e  movzx   eax, word ptr [rcx+40h]
0x18000d862  mov     [rbp+var_28], ax
0x18000d866  mov     rax, [rcx+38h]
0x18000d86a  mov     [rbp+var_20], rax
0x18000d86e  mov     rax, [rcx+80h]
0x18000d875  mov     [rbp+var_18], rax
0x18000d879  mov     [rbp+var_3C], 0
0x18000d880  mov     [rbp+var_2F], 0
0x18000d884  mov     [rbp+var_2C], 0
0x18000d88b  mov     [rbp+var_24], 0
0x18000d892  mov     [rbp+var_10], 0
0x18000d89a  test    rdi, rdi
0x18000d89d  jnz     short loc_18000D8E3
0x18000d89f  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d8a6  test    rax, rax
0x18000d8a9  jnz     short loc_18000D8C4
0x18000d8ab  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000d8b2  call    cs:__imp_GetModuleHandleW
0x18000d8b8  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d8bf  test    rax, rax
0x18000d8c2  jz      short loc_18000D8D7
0x18000d8c4  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000d8cb  mov     rcx, rax; hModule
0x18000d8ce  call    cs:__imp_GetProcAddress
0x18000d8d4  mov     rdi, rax
0x18000d8d7  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000d8de  test    rdi, rdi
0x18000d8e1  jz      short loc_18000D8F5
0x18000d8e3  lea     r8, [rbp+var_10]
0x18000d8e7  xor     ecx, ecx
0x18000d8e9  lea     rdx, [rbp+var_40]
0x18000d8ed  mov     rax, rdi
0x18000d8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8f5  movzx   ecx, byte ptr [rbp+var_10+4]
0x18000d8f9  mov     eax, dword ptr [rbp+var_10]
0x18000d8fc  mov     [rbx+10h], eax
0x18000d8ff  sub     ecx, 1
0x18000d902  jz      short loc_18000D91A
0x18000d904  sub     ecx, 1
0x18000d907  jz      short loc_18000D914
0x18000d909  cmp     ecx, 1
0x18000d90c  jnz     short loc_18000D91E
0x18000d90e  or      dword ptr [rbx+4], 4
0x18000d912  jmp     short loc_18000D91E
0x18000d914  or      dword ptr [rbx+4], 2
0x18000d918  jmp     short loc_18000D91E
0x18000d91a  or      dword ptr [rbx+4], 1
0x18000d91e  mov     rcx, [rbp+var_8]
0x18000d922  xor     rcx, rsp; StackCookie
0x18000d925  call    __security_check_cookie
0x18000d92a  lea     r11, [rsp+60h+var_s0]
0x18000d92f  mov     rbx, [r11+18h]
0x18000d933  mov     rdi, [r11+20h]
0x18000d937  mov     rsp, r11
0x18000d93a  pop     rbp
0x18000d93b  retn
```
