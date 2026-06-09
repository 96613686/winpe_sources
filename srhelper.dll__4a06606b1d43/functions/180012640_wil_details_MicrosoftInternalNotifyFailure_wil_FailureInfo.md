# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180012640`
- end: `0x180012750`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `272`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180012640`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800126f0`
- `KERNEL32!GetProcAddress` at `0x1800126f0`
- `KERNEL32!GetModuleHandleW` at `0x1800126d4`
- `KERNEL32!GetModuleHandleW` at `0x1800126d4`

## string_xrefs

- `0x1800126cd`: `kernelbase.dll`

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
0x180012640  mov     [rsp-8+arg_8], rbx
0x180012645  mov     [rsp-8+arg_10], rdi
0x18001264a  push    rbp
0x18001264b  mov     rbp, rsp
0x18001264e  sub     rsp, 50h
0x180012652  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180012659  xor     eax, eax
0x18001265b  mov     [rbp+var_16], ax
0x18001265f  mov     rbx, rcx
0x180012662  mov     eax, [rcx+8]
0x180012665  mov     [rbp+var_30], eax
0x180012668  mov     rax, [rcx+18h]
0x18001266c  mov     [rbp+var_28], rax
0x180012670  mov     al, [rcx]
0x180012672  mov     [rbp+var_20], al
0x180012675  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18001267c  mov     [rbp+var_1E], ax
0x180012680  movzx   eax, word ptr [rcx+40h]
0x180012684  mov     [rbp+var_18], ax
0x180012688  mov     rax, [rcx+38h]
0x18001268c  mov     [rbp+var_10], rax
0x180012690  mov     rax, [rcx+80h]
0x180012697  mov     [rbp+var_8], rax
0x18001269b  mov     [rbp+var_2C], 0
0x1800126a2  mov     [rbp+var_1F], 0
0x1800126a6  mov     [rbp+var_1C], 0
0x1800126ad  mov     [rbp+var_14], 0
0x1800126b4  mov     [rbp+arg_0], 0
0x1800126bc  test    rdi, rdi
0x1800126bf  jnz     short loc_180012705
0x1800126c1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800126c8  test    rax, rax
0x1800126cb  jnz     short loc_1800126E6
0x1800126cd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800126d4  call    cs:__imp_GetModuleHandleW
0x1800126da  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800126e1  test    rax, rax
0x1800126e4  jz      short loc_1800126F9
0x1800126e6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800126ed  mov     rcx, rax; hModule
0x1800126f0  call    cs:__imp_GetProcAddress
0x1800126f6  mov     rdi, rax
0x1800126f9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180012700  test    rdi, rdi
0x180012703  jz      short loc_180012717
0x180012705  lea     r8, [rbp+arg_0]
0x180012709  xor     ecx, ecx
0x18001270b  lea     rdx, [rbp+var_30]
0x18001270f  mov     rax, rdi
0x180012712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012717  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18001271b  mov     eax, dword ptr [rbp+arg_0]
0x18001271e  mov     [rbx+10h], eax
0x180012721  sub     ecx, 1
0x180012724  jz      short loc_18001273C
0x180012726  sub     ecx, 1
0x180012729  jz      short loc_180012736
0x18001272b  cmp     ecx, 1
0x18001272e  jnz     short loc_180012740
0x180012730  or      dword ptr [rbx+4], 4
0x180012734  jmp     short loc_180012740
0x180012736  or      dword ptr [rbx+4], 2
0x18001273a  jmp     short loc_180012740
0x18001273c  or      dword ptr [rbx+4], 1
0x180012740  mov     rbx, [rsp+50h+arg_8]
0x180012745  mov     rdi, [rsp+50h+arg_10]
0x18001274a  add     rsp, 50h
0x18001274e  pop     rbp
0x18001274f  retn
```
