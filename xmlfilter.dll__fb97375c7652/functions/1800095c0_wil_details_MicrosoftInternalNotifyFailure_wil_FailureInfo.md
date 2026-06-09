# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1800095c0`
- end: `0x1800096d1`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800095c0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009654`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009654`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009670`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009670`

## string_xrefs

- `0x18000964d`: `kernelbase.dll`

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
0x1800095c0  mov     [rsp-8+arg_8], rbx
0x1800095c5  mov     [rsp-8+arg_10], rdi
0x1800095ca  push    rbp
0x1800095cb  mov     rbp, rsp
0x1800095ce  sub     rsp, 50h
0x1800095d2  mov     rbx, rcx
0x1800095d5  mov     [rbp+var_2C], 0
0x1800095dc  mov     [rbp+var_1F], 0
0x1800095e0  mov     [rbp+var_1C], 0
0x1800095e7  xor     eax, eax
0x1800095e9  mov     [rbp+var_16], ax
0x1800095ed  mov     eax, [rcx+8]
0x1800095f0  mov     [rbp+var_30], eax
0x1800095f3  mov     rax, [rcx+18h]
0x1800095f7  mov     [rbp+var_28], rax
0x1800095fb  mov     al, [rcx]
0x1800095fd  mov     [rbp+var_20], al
0x180009600  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180009607  mov     [rbp+var_1E], ax
0x18000960b  movzx   eax, word ptr [rcx+40h]
0x18000960f  mov     [rbp+var_18], ax
0x180009613  mov     [rbp+var_14], 0
0x18000961a  mov     rax, [rcx+38h]
0x18000961e  mov     [rbp+var_10], rax
0x180009622  mov     rax, [rcx+80h]
0x180009629  mov     [rbp+var_8], rax
0x18000962d  mov     [rbp+arg_0], 0
0x180009635  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000963c  test    rdi, rdi
0x18000963f  jnz     short loc_180009685
0x180009641  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009648  test    rax, rax
0x18000964b  jnz     short loc_180009666
0x18000964d  lea     rcx, LibFileName; "kernelbase.dll"
0x180009654  call    cs:__imp_GetModuleHandleW
0x18000965a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009661  test    rax, rax
0x180009664  jz      short loc_180009679
0x180009666  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000966d  mov     rcx, rax; hModule
0x180009670  call    cs:__imp_GetProcAddress
0x180009676  mov     rdi, rax
0x180009679  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180009680  test    rdi, rdi
0x180009683  jz      short loc_180009698
0x180009685  lea     r8, [rbp+arg_0]
0x180009689  lea     rdx, [rbp+var_30]
0x18000968d  xor     ecx, ecx
0x18000968f  mov     rax, rdi
0x180009692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009697  nop
0x180009698  mov     eax, dword ptr [rbp+arg_0]
0x18000969b  mov     [rbx+10h], eax
0x18000969e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1800096a2  sub     ecx, 1
0x1800096a5  jz      short loc_1800096BD
0x1800096a7  sub     ecx, 1
0x1800096aa  jz      short loc_1800096B7
0x1800096ac  cmp     ecx, 1
0x1800096af  jnz     short loc_1800096C1
0x1800096b1  or      dword ptr [rbx+4], 4
0x1800096b5  jmp     short loc_1800096C1
0x1800096b7  or      dword ptr [rbx+4], 2
0x1800096bb  jmp     short loc_1800096C1
0x1800096bd  or      dword ptr [rbx+4], 1
0x1800096c1  mov     rbx, [rsp+50h+arg_8]
0x1800096c6  mov     rdi, [rsp+50h+arg_10]
0x1800096cb  add     rsp, 50h
0x1800096cf  pop     rbp
0x1800096d0  retn
```
