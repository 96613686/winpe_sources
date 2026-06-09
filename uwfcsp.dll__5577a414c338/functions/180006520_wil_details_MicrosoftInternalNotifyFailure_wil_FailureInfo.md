# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180006520`
- end: `0x180006630`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `272`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006520`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800065d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800065d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800065b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800065b4`

## string_xrefs

- `0x1800065ad`: `kernelbase.dll`

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
0x180006520  mov     [rsp-8+arg_8], rbx
0x180006525  mov     [rsp-8+arg_10], rdi
0x18000652a  push    rbp
0x18000652b  mov     rbp, rsp
0x18000652e  sub     rsp, 50h
0x180006532  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180006539  xor     eax, eax
0x18000653b  mov     [rbp+var_16], ax
0x18000653f  mov     rbx, rcx
0x180006542  mov     eax, [rcx+8]
0x180006545  mov     [rbp+var_30], eax
0x180006548  mov     rax, [rcx+18h]
0x18000654c  mov     [rbp+var_28], rax
0x180006550  mov     al, [rcx]
0x180006552  mov     [rbp+var_20], al
0x180006555  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000655c  mov     [rbp+var_1E], ax
0x180006560  movzx   eax, word ptr [rcx+40h]
0x180006564  mov     [rbp+var_18], ax
0x180006568  mov     rax, [rcx+38h]
0x18000656c  mov     [rbp+var_10], rax
0x180006570  mov     rax, [rcx+80h]
0x180006577  mov     [rbp+var_8], rax
0x18000657b  mov     [rbp+var_2C], 0
0x180006582  mov     [rbp+var_1F], 0
0x180006586  mov     [rbp+var_1C], 0
0x18000658d  mov     [rbp+var_14], 0
0x180006594  mov     [rbp+arg_0], 0
0x18000659c  test    rdi, rdi
0x18000659f  jnz     short loc_1800065E5
0x1800065a1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800065a8  test    rax, rax
0x1800065ab  jnz     short loc_1800065C6
0x1800065ad  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800065b4  call    cs:__imp_GetModuleHandleW
0x1800065ba  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800065c1  test    rax, rax
0x1800065c4  jz      short loc_1800065D9
0x1800065c6  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1800065cd  mov     rcx, rax; hModule
0x1800065d0  call    cs:__imp_GetProcAddress
0x1800065d6  mov     rdi, rax
0x1800065d9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800065e0  test    rdi, rdi
0x1800065e3  jz      short loc_1800065F7
0x1800065e5  lea     r8, [rbp+arg_0]
0x1800065e9  xor     ecx, ecx
0x1800065eb  lea     rdx, [rbp+var_30]
0x1800065ef  mov     rax, rdi
0x1800065f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065f7  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1800065fb  mov     eax, dword ptr [rbp+arg_0]
0x1800065fe  mov     [rbx+10h], eax
0x180006601  sub     ecx, 1
0x180006604  jz      short loc_18000661C
0x180006606  sub     ecx, 1
0x180006609  jz      short loc_180006616
0x18000660b  cmp     ecx, 1
0x18000660e  jnz     short loc_180006620
0x180006610  or      dword ptr [rbx+4], 4
0x180006614  jmp     short loc_180006620
0x180006616  or      dword ptr [rbx+4], 2
0x18000661a  jmp     short loc_180006620
0x18000661c  or      dword ptr [rbx+4], 1
0x180006620  mov     rbx, [rsp+50h+arg_8]
0x180006625  mov     rdi, [rsp+50h+arg_10]
0x18000662a  add     rsp, 50h
0x18000662e  pop     rbp
0x18000662f  retn
```
