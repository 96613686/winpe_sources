# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18000cb90`
- end: `0x18000cca9`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `281`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000cb90`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000cc3d`
- `KERNEL32!GetProcAddress` at `0x18000cc3d`
- `KERNEL32!GetModuleHandleW` at `0x18000cc1b`
- `KERNEL32!GetModuleHandleW` at `0x18000cc1b`

## string_xrefs

- `0x18000cc14`: `kernelbase.dll`

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
0x18000cb90  mov     [rsp-8+arg_8], rbx
0x18000cb95  mov     [rsp-8+arg_10], rsi
0x18000cb9a  mov     [rsp-8+arg_18], rdi
0x18000cb9f  push    rbp
0x18000cba0  mov     rbp, rsp
0x18000cba3  sub     rsp, 50h
0x18000cba7  mov     eax, [rcx+8]
0x18000cbaa  xor     esi, esi
0x18000cbac  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000cbb3  mov     rbx, rcx
0x18000cbb6  mov     [rbp+var_30], eax
0x18000cbb9  mov     rax, [rcx+18h]
0x18000cbbd  mov     [rbp+var_28], rax
0x18000cbc1  mov     al, [rcx]
0x18000cbc3  mov     [rbp+var_20], al
0x18000cbc6  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000cbcd  mov     [rbp+var_1E], ax
0x18000cbd1  movzx   eax, word ptr [rcx+40h]
0x18000cbd5  mov     [rbp+var_18], ax
0x18000cbd9  mov     rax, [rcx+38h]
0x18000cbdd  mov     [rbp+var_10], rax
0x18000cbe1  mov     rax, [rcx+80h]
0x18000cbe8  mov     [rbp+var_8], rax
0x18000cbec  mov     [rbp+var_2C], esi
0x18000cbef  mov     [rbp+var_1F], sil
0x18000cbf3  mov     [rbp+var_1C], esi
0x18000cbf6  mov     [rbp+var_16], si
0x18000cbfa  mov     [rbp+var_14], esi
0x18000cbfd  mov     [rbp+arg_0], rsi
0x18000cc01  test    rdi, rdi
0x18000cc04  jnz     short loc_18000CC58
0x18000cc06  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000cc0d  mov     edi, esi
0x18000cc0f  test    rax, rax
0x18000cc12  jnz     short loc_18000CC33
0x18000cc14  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000cc1b  call    cs:__imp_GetModuleHandleW
0x18000cc22  nop     dword ptr [rax+rax+00h]
0x18000cc27  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000cc2e  test    rax, rax
0x18000cc31  jz      short loc_18000CC4C
0x18000cc33  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000cc3a  mov     rcx, rax; hModule
0x18000cc3d  call    cs:__imp_GetProcAddress
0x18000cc44  nop     dword ptr [rax+rax+00h]
0x18000cc49  mov     rdi, rax
0x18000cc4c  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000cc53  test    rdi, rdi
0x18000cc56  jz      short loc_18000CC6A
0x18000cc58  lea     r8, [rbp+arg_0]
0x18000cc5c  xor     ecx, ecx
0x18000cc5e  lea     rdx, [rbp+var_30]
0x18000cc62  mov     rax, rdi
0x18000cc65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc6a  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000cc6e  mov     eax, dword ptr [rbp+arg_0]
0x18000cc71  mov     [rbx+10h], eax
0x18000cc74  sub     ecx, 1
0x18000cc77  jz      short loc_18000CC8F
0x18000cc79  sub     ecx, 1
0x18000cc7c  jz      short loc_18000CC89
0x18000cc7e  cmp     ecx, 1
0x18000cc81  jnz     short loc_18000CC93
0x18000cc83  or      dword ptr [rbx+4], 4
0x18000cc87  jmp     short loc_18000CC93
0x18000cc89  or      dword ptr [rbx+4], 2
0x18000cc8d  jmp     short loc_18000CC93
0x18000cc8f  or      dword ptr [rbx+4], 1
0x18000cc93  mov     rbx, [rsp+50h+arg_8]
0x18000cc98  mov     rsi, [rsp+50h+arg_10]
0x18000cc9d  mov     rdi, [rsp+50h+arg_18]
0x18000cca2  add     rsp, 50h
0x18000cca6  pop     rbp
0x18000cca7  retn
```
