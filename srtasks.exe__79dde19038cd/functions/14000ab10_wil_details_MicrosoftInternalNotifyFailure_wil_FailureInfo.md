# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x14000ab10`
- end: `0x14000ac20`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `272`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000ab10`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000aba4`
- `KERNEL32!GetModuleHandleW` at `0x14000aba4`
- `KERNEL32!GetProcAddress` at `0x14000abc0`
- `KERNEL32!GetProcAddress` at `0x14000abc0`

## string_xrefs

- `0x14000ab9d`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  _DWORD v8[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v9; // [rsp+28h] [rbp-28h]
  char v10; // [rsp+30h] [rbp-20h]
  char v11; // [rsp+31h] [rbp-1Fh]
  __int16 v12; // [rsp+32h] [rbp-1Eh]
  int v13; // [rsp+34h] [rbp-1Ch]
  __int16 v14; // [rsp+38h] [rbp-18h]
  __int16 v15; // [rsp+3Ah] [rbp-16h]
  int v16; // [rsp+3Ch] [rbp-14h]
  __int64 v17; // [rsp+40h] [rbp-10h]
  __int64 v18; // [rsp+48h] [rbp-8h]
  __int64 v19; // [rsp+60h] [rbp+10h] BYREF

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
0x14000ab10  mov     [rsp-8+arg_8], rbx
0x14000ab15  mov     [rsp-8+arg_10], rdi
0x14000ab1a  push    rbp
0x14000ab1b  mov     rbp, rsp
0x14000ab1e  sub     rsp, 50h
0x14000ab22  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x14000ab29  xor     eax, eax
0x14000ab2b  mov     [rbp+var_16], ax
0x14000ab2f  mov     rbx, rcx
0x14000ab32  mov     eax, [rcx+8]
0x14000ab35  mov     [rbp+var_30], eax
0x14000ab38  mov     rax, [rcx+18h]
0x14000ab3c  mov     [rbp+var_28], rax
0x14000ab40  mov     al, [rcx]
0x14000ab42  mov     [rbp+var_20], al
0x14000ab45  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x14000ab4c  mov     [rbp+var_1E], ax
0x14000ab50  movzx   eax, word ptr [rcx+40h]
0x14000ab54  mov     [rbp+var_18], ax
0x14000ab58  mov     rax, [rcx+38h]
0x14000ab5c  mov     [rbp+var_10], rax
0x14000ab60  mov     rax, [rcx+80h]
0x14000ab67  mov     [rbp+var_8], rax
0x14000ab6b  mov     [rbp+var_2C], 0
0x14000ab72  mov     [rbp+var_1F], 0
0x14000ab76  mov     [rbp+var_1C], 0
0x14000ab7d  mov     [rbp+var_14], 0
0x14000ab84  mov     [rbp+arg_0], 0
0x14000ab8c  test    rdi, rdi
0x14000ab8f  jnz     short loc_14000ABD5
0x14000ab91  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000ab98  test    rax, rax
0x14000ab9b  jnz     short loc_14000ABB6
0x14000ab9d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000aba4  call    cs:__imp_GetModuleHandleW
0x14000abaa  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000abb1  test    rax, rax
0x14000abb4  jz      short loc_14000ABC9
0x14000abb6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x14000abbd  mov     rcx, rax; hModule
0x14000abc0  call    cs:__imp_GetProcAddress
0x14000abc6  mov     rdi, rax
0x14000abc9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x14000abd0  test    rdi, rdi
0x14000abd3  jz      short loc_14000ABE7
0x14000abd5  lea     r8, [rbp+arg_0]
0x14000abd9  xor     ecx, ecx
0x14000abdb  lea     rdx, [rbp+var_30]
0x14000abdf  mov     rax, rdi
0x14000abe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abe7  movzx   ecx, byte ptr [rbp+arg_0+4]
0x14000abeb  mov     eax, dword ptr [rbp+arg_0]
0x14000abee  mov     [rbx+10h], eax
0x14000abf1  sub     ecx, 1
0x14000abf4  jz      short loc_14000AC0C
0x14000abf6  sub     ecx, 1
0x14000abf9  jz      short loc_14000AC06
0x14000abfb  cmp     ecx, 1
0x14000abfe  jnz     short loc_14000AC10
0x14000ac00  or      dword ptr [rbx+4], 4
0x14000ac04  jmp     short loc_14000AC10
0x14000ac06  or      dword ptr [rbx+4], 2
0x14000ac0a  jmp     short loc_14000AC10
0x14000ac0c  or      dword ptr [rbx+4], 1
0x14000ac10  mov     rbx, [rsp+50h+arg_8]
0x14000ac15  mov     rdi, [rsp+50h+arg_10]
0x14000ac1a  add     rsp, 50h
0x14000ac1e  pop     rbp
0x14000ac1f  retn
```
