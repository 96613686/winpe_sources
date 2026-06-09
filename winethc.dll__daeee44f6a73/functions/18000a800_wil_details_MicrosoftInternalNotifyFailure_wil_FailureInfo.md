# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18000a800`
- end: `0x18000a91d`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `285`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a800`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000a8b6`
- `KERNEL32!GetProcAddress` at `0x18000a8b6`
- `KERNEL32!GetModuleHandleW` at `0x18000a894`
- `KERNEL32!GetModuleHandleW` at `0x18000a894`

## string_xrefs

- `0x18000a88d`: `kernelbase.dll`

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
0x18000a800  mov     [rsp-8+arg_8], rbx
0x18000a805  mov     [rsp-8+arg_10], rdi
0x18000a80a  push    rbp
0x18000a80b  mov     rbp, rsp
0x18000a80e  sub     rsp, 50h
0x18000a812  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000a819  xor     eax, eax
0x18000a81b  mov     [rbp+var_16], ax
0x18000a81f  mov     rbx, rcx
0x18000a822  mov     eax, [rcx+8]
0x18000a825  mov     [rbp+var_30], eax
0x18000a828  mov     rax, [rcx+18h]
0x18000a82c  mov     [rbp+var_28], rax
0x18000a830  mov     al, [rcx]
0x18000a832  mov     [rbp+var_20], al
0x18000a835  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000a83c  mov     [rbp+var_1E], ax
0x18000a840  movzx   eax, word ptr [rcx+40h]
0x18000a844  mov     [rbp+var_18], ax
0x18000a848  mov     rax, [rcx+38h]
0x18000a84c  mov     [rbp+var_10], rax
0x18000a850  mov     rax, [rcx+80h]
0x18000a857  mov     [rbp+var_8], rax
0x18000a85b  mov     [rbp+var_2C], 0
0x18000a862  mov     [rbp+var_1F], 0
0x18000a866  mov     [rbp+var_1C], 0
0x18000a86d  mov     [rbp+var_14], 0
0x18000a874  mov     [rbp+arg_0], 0
0x18000a87c  test    rdi, rdi
0x18000a87f  jnz     short loc_18000A8D1
0x18000a881  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a888  test    rax, rax
0x18000a88b  jnz     short loc_18000A8AC
0x18000a88d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a894  call    cs:__imp_GetModuleHandleW
0x18000a89b  nop     dword ptr [rax+rax+00h]
0x18000a8a0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a8a7  test    rax, rax
0x18000a8aa  jz      short loc_18000A8C5
0x18000a8ac  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000a8b3  mov     rcx, rax; hModule
0x18000a8b6  call    cs:__imp_GetProcAddress
0x18000a8bd  nop     dword ptr [rax+rax+00h]
0x18000a8c2  mov     rdi, rax
0x18000a8c5  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000a8cc  test    rdi, rdi
0x18000a8cf  jz      short loc_18000A8E3
0x18000a8d1  lea     r8, [rbp+arg_0]
0x18000a8d5  xor     ecx, ecx
0x18000a8d7  lea     rdx, [rbp+var_30]
0x18000a8db  mov     rax, rdi
0x18000a8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8e3  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000a8e7  mov     eax, dword ptr [rbp+arg_0]
0x18000a8ea  mov     [rbx+10h], eax
0x18000a8ed  sub     ecx, 1
0x18000a8f0  jz      short loc_18000A908
0x18000a8f2  sub     ecx, 1
0x18000a8f5  jz      short loc_18000A902
0x18000a8f7  cmp     ecx, 1
0x18000a8fa  jnz     short loc_18000A90C
0x18000a8fc  or      dword ptr [rbx+4], 4
0x18000a900  jmp     short loc_18000A90C
0x18000a902  or      dword ptr [rbx+4], 2
0x18000a906  jmp     short loc_18000A90C
0x18000a908  or      dword ptr [rbx+4], 1
0x18000a90c  mov     rbx, [rsp+50h+arg_8]
0x18000a911  mov     rdi, [rsp+50h+arg_10]
0x18000a916  add     rsp, 50h
0x18000a91a  pop     rbp
0x18000a91b  retn
```
