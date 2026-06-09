# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18000a7b0`
- end: `0x18000a8c9`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `281`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a7b0`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000a83b`
- `KERNEL32!GetModuleHandleW` at `0x18000a83b`
- `KERNEL32!GetProcAddress` at `0x18000a85d`
- `KERNEL32!GetProcAddress` at `0x18000a85d`

## string_xrefs

- `0x18000a834`: `kernelbase.dll`

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
  v15 = 0;
  v16 = 0;
  v19 = 0;
  if ( `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers )
    goto LABEL_6;
  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  ProcAddress = 0;
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
0x18000a7b0  mov     [rsp-8+arg_8], rbx
0x18000a7b5  mov     [rsp-8+arg_10], rsi
0x18000a7ba  mov     [rsp-8+arg_18], rdi
0x18000a7bf  push    rbp
0x18000a7c0  mov     rbp, rsp
0x18000a7c3  sub     rsp, 50h
0x18000a7c7  mov     eax, [rcx+8]
0x18000a7ca  xor     esi, esi
0x18000a7cc  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000a7d3  mov     rbx, rcx
0x18000a7d6  mov     [rbp+var_30], eax
0x18000a7d9  mov     rax, [rcx+18h]
0x18000a7dd  mov     [rbp+var_28], rax
0x18000a7e1  mov     al, [rcx]
0x18000a7e3  mov     [rbp+var_20], al
0x18000a7e6  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000a7ed  mov     [rbp+var_1E], ax
0x18000a7f1  movzx   eax, word ptr [rcx+40h]
0x18000a7f5  mov     [rbp+var_18], ax
0x18000a7f9  mov     rax, [rcx+38h]
0x18000a7fd  mov     [rbp+var_10], rax
0x18000a801  mov     rax, [rcx+80h]
0x18000a808  mov     [rbp+var_8], rax
0x18000a80c  mov     [rbp+var_2C], esi
0x18000a80f  mov     [rbp+var_1F], sil
0x18000a813  mov     [rbp+var_1C], esi
0x18000a816  mov     [rbp+var_16], si
0x18000a81a  mov     [rbp+var_14], esi
0x18000a81d  mov     [rbp+arg_0], rsi
0x18000a821  test    rdi, rdi
0x18000a824  jnz     short loc_18000A878
0x18000a826  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a82d  mov     edi, esi
0x18000a82f  test    rax, rax
0x18000a832  jnz     short loc_18000A853
0x18000a834  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a83b  call    cs:__imp_GetModuleHandleW
0x18000a842  nop     dword ptr [rax+rax+00h]
0x18000a847  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a84e  test    rax, rax
0x18000a851  jz      short loc_18000A86C
0x18000a853  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18000a85a  mov     rcx, rax; hModule
0x18000a85d  call    cs:__imp_GetProcAddress
0x18000a864  nop     dword ptr [rax+rax+00h]
0x18000a869  mov     rdi, rax
0x18000a86c  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000a873  test    rdi, rdi
0x18000a876  jz      short loc_18000A88A
0x18000a878  lea     r8, [rbp+arg_0]
0x18000a87c  xor     ecx, ecx
0x18000a87e  lea     rdx, [rbp+var_30]
0x18000a882  mov     rax, rdi
0x18000a885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a88a  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000a88e  mov     eax, dword ptr [rbp+arg_0]
0x18000a891  mov     [rbx+10h], eax
0x18000a894  sub     ecx, 1
0x18000a897  jz      short loc_18000A8AF
0x18000a899  sub     ecx, 1
0x18000a89c  jz      short loc_18000A8A9
0x18000a89e  cmp     ecx, 1
0x18000a8a1  jnz     short loc_18000A8B3
0x18000a8a3  or      dword ptr [rbx+4], 4
0x18000a8a7  jmp     short loc_18000A8B3
0x18000a8a9  or      dword ptr [rbx+4], 2
0x18000a8ad  jmp     short loc_18000A8B3
0x18000a8af  or      dword ptr [rbx+4], 1
0x18000a8b3  mov     rbx, [rsp+50h+arg_8]
0x18000a8b8  mov     rsi, [rsp+50h+arg_10]
0x18000a8bd  mov     rdi, [rsp+50h+arg_18]
0x18000a8c2  add     rsp, 50h
0x18000a8c6  pop     rbp
0x18000a8c7  retn
```
