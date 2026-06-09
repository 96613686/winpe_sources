# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140006120`
- end: `0x140006231`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140006120`
- `0x14002f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400061d0`
- `KERNEL32!GetProcAddress` at `0x1400061d0`
- `KERNEL32!GetModuleHandleW` at `0x1400061b4`
- `KERNEL32!GetModuleHandleW` at `0x1400061b4`

## string_xrefs

- `0x1400061ad`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v6; // [rsp+28h] [rbp-28h]
  char v7; // [rsp+30h] [rbp-20h]
  char v8; // [rsp+31h] [rbp-1Fh]
  __int16 v9; // [rsp+32h] [rbp-1Eh]
  int v10; // [rsp+34h] [rbp-1Ch]
  __int16 v11; // [rsp+38h] [rbp-18h]
  __int16 v12; // [rsp+3Ah] [rbp-16h]
  int v13; // [rsp+3Ch] [rbp-14h]
  __int64 v14; // [rsp+40h] [rbp-10h]
  __int64 v15; // [rsp+48h] [rbp-8h]
  __int64 v16; // [rsp+60h] [rbp+10h] BYREF

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
0x140006120  mov     [rsp-8+arg_8], rbx
0x140006125  mov     [rsp-8+arg_10], rdi
0x14000612a  push    rbp
0x14000612b  mov     rbp, rsp
0x14000612e  sub     rsp, 50h
0x140006132  mov     rbx, rcx
0x140006135  mov     [rbp+var_2C], 0
0x14000613c  mov     [rbp+var_1F], 0
0x140006140  mov     [rbp+var_1C], 0
0x140006147  xor     eax, eax
0x140006149  mov     [rbp+var_16], ax
0x14000614d  mov     eax, [rcx+8]
0x140006150  mov     [rbp+var_30], eax
0x140006153  mov     rax, [rcx+18h]
0x140006157  mov     [rbp+var_28], rax
0x14000615b  mov     al, [rcx]
0x14000615d  mov     [rbp+var_20], al
0x140006160  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140006167  mov     [rbp+var_1E], ax
0x14000616b  movzx   eax, word ptr [rcx+40h]
0x14000616f  mov     [rbp+var_18], ax
0x140006173  mov     [rbp+var_14], 0
0x14000617a  mov     rax, [rcx+38h]
0x14000617e  mov     [rbp+var_10], rax
0x140006182  mov     rax, [rcx+80h]
0x140006189  mov     [rbp+var_8], rax
0x14000618d  mov     [rbp+arg_0], 0
0x140006195  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x14000619c  test    rdi, rdi
0x14000619f  jnz     short loc_1400061E5
0x1400061a1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400061a8  test    rax, rax
0x1400061ab  jnz     short loc_1400061C6
0x1400061ad  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400061b4  call    cs:__imp_GetModuleHandleW
0x1400061ba  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400061c1  test    rax, rax
0x1400061c4  jz      short loc_1400061D9
0x1400061c6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1400061cd  mov     rcx, rax; hModule
0x1400061d0  call    cs:__imp_GetProcAddress
0x1400061d6  mov     rdi, rax
0x1400061d9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1400061e0  test    rdi, rdi
0x1400061e3  jz      short loc_1400061F8
0x1400061e5  lea     r8, [rbp+arg_0]
0x1400061e9  lea     rdx, [rbp+var_30]
0x1400061ed  xor     ecx, ecx
0x1400061ef  mov     rax, rdi
0x1400061f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400061f7  nop
0x1400061f8  mov     eax, dword ptr [rbp+arg_0]
0x1400061fb  mov     [rbx+10h], eax
0x1400061fe  movzx   ecx, byte ptr [rbp+arg_0+4]
0x140006202  sub     ecx, 1
0x140006205  jz      short loc_14000621D
0x140006207  sub     ecx, 1
0x14000620a  jz      short loc_140006217
0x14000620c  cmp     ecx, 1
0x14000620f  jnz     short loc_140006221
0x140006211  or      dword ptr [rbx+4], 4
0x140006215  jmp     short loc_140006221
0x140006217  or      dword ptr [rbx+4], 2
0x14000621b  jmp     short loc_140006221
0x14000621d  or      dword ptr [rbx+4], 1
0x140006221  mov     rbx, [rsp+50h+arg_8]
0x140006226  mov     rdi, [rsp+50h+arg_10]
0x14000622b  add     rsp, 50h
0x14000622f  pop     rbp
0x140006230  retn
```
