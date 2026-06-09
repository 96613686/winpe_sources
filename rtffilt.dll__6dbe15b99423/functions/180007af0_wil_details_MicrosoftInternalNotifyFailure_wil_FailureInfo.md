# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180007af0`
- end: `0x180007c01`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007af0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007b84`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007b84`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ba0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ba0`

## string_xrefs

- `0x180007b7d`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180007af0  mov     [rsp-8+arg_8], rbx
0x180007af5  mov     [rsp-8+arg_10], rdi
0x180007afa  push    rbp
0x180007afb  mov     rbp, rsp
0x180007afe  sub     rsp, 50h
0x180007b02  mov     rbx, rcx
0x180007b05  mov     [rbp+var_2C], 0
0x180007b0c  mov     [rbp+var_1F], 0
0x180007b10  mov     [rbp+var_1C], 0
0x180007b17  xor     eax, eax
0x180007b19  mov     [rbp+var_16], ax
0x180007b1d  mov     eax, [rcx+8]
0x180007b20  mov     [rbp+var_30], eax
0x180007b23  mov     rax, [rcx+18h]
0x180007b27  mov     [rbp+var_28], rax
0x180007b2b  mov     al, [rcx]
0x180007b2d  mov     [rbp+var_20], al
0x180007b30  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180007b37  mov     [rbp+var_1E], ax
0x180007b3b  movzx   eax, word ptr [rcx+40h]
0x180007b3f  mov     [rbp+var_18], ax
0x180007b43  mov     [rbp+var_14], 0
0x180007b4a  mov     rax, [rcx+38h]
0x180007b4e  mov     [rbp+var_10], rax
0x180007b52  mov     rax, [rcx+80h]
0x180007b59  mov     [rbp+var_8], rax
0x180007b5d  mov     [rbp+arg_0], 0
0x180007b65  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180007b6c  test    rdi, rdi
0x180007b6f  jnz     short loc_180007BB5
0x180007b71  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007b78  test    rax, rax
0x180007b7b  jnz     short loc_180007B96
0x180007b7d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007b84  call    cs:__imp_GetModuleHandleW
0x180007b8a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007b91  test    rax, rax
0x180007b94  jz      short loc_180007BA9
0x180007b96  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180007b9d  mov     rcx, rax; hModule
0x180007ba0  call    cs:__imp_GetProcAddress
0x180007ba6  mov     rdi, rax
0x180007ba9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180007bb0  test    rdi, rdi
0x180007bb3  jz      short loc_180007BC8
0x180007bb5  lea     r8, [rbp+arg_0]
0x180007bb9  lea     rdx, [rbp+var_30]
0x180007bbd  xor     ecx, ecx
0x180007bbf  mov     rax, rdi
0x180007bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bc7  nop
0x180007bc8  mov     eax, dword ptr [rbp+arg_0]
0x180007bcb  mov     [rbx+10h], eax
0x180007bce  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180007bd2  sub     ecx, 1
0x180007bd5  jz      short loc_180007BED
0x180007bd7  sub     ecx, 1
0x180007bda  jz      short loc_180007BE7
0x180007bdc  cmp     ecx, 1
0x180007bdf  jnz     short loc_180007BF1
0x180007be1  or      dword ptr [rbx+4], 4
0x180007be5  jmp     short loc_180007BF1
0x180007be7  or      dword ptr [rbx+4], 2
0x180007beb  jmp     short loc_180007BF1
0x180007bed  or      dword ptr [rbx+4], 1
0x180007bf1  mov     rbx, [rsp+50h+arg_8]
0x180007bf6  mov     rdi, [rsp+50h+arg_10]
0x180007bfb  add     rsp, 50h
0x180007bff  pop     rbp
0x180007c00  retn
```
