# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180004ed0`
- end: `0x180004fe0`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `272`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004ed0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f80`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004f64`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004f64`

## string_xrefs

- `0x180004f5d`: `kernelbase.dll`

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
0x180004ed0  mov     [rsp-8+arg_8], rbx
0x180004ed5  mov     [rsp-8+arg_10], rdi
0x180004eda  push    rbp
0x180004edb  mov     rbp, rsp
0x180004ede  sub     rsp, 50h
0x180004ee2  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180004ee9  xor     eax, eax
0x180004eeb  mov     [rbp+var_16], ax
0x180004eef  mov     rbx, rcx
0x180004ef2  mov     eax, [rcx+8]
0x180004ef5  mov     [rbp+var_30], eax
0x180004ef8  mov     rax, [rcx+18h]
0x180004efc  mov     [rbp+var_28], rax
0x180004f00  mov     al, [rcx]
0x180004f02  mov     [rbp+var_20], al
0x180004f05  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180004f0c  mov     [rbp+var_1E], ax
0x180004f10  movzx   eax, word ptr [rcx+40h]
0x180004f14  mov     [rbp+var_18], ax
0x180004f18  mov     rax, [rcx+38h]
0x180004f1c  mov     [rbp+var_10], rax
0x180004f20  mov     rax, [rcx+80h]
0x180004f27  mov     [rbp+var_8], rax
0x180004f2b  mov     [rbp+var_2C], 0
0x180004f32  mov     [rbp+var_1F], 0
0x180004f36  mov     [rbp+var_1C], 0
0x180004f3d  mov     [rbp+var_14], 0
0x180004f44  mov     [rbp+arg_0], 0
0x180004f4c  test    rdi, rdi
0x180004f4f  jnz     short loc_180004F95
0x180004f51  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004f58  test    rax, rax
0x180004f5b  jnz     short loc_180004F76
0x180004f5d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180004f64  call    cs:__imp_GetModuleHandleW
0x180004f6a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004f71  test    rax, rax
0x180004f74  jz      short loc_180004F89
0x180004f76  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x180004f7d  mov     rcx, rax; hModule
0x180004f80  call    cs:__imp_GetProcAddress
0x180004f86  mov     rdi, rax
0x180004f89  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180004f90  test    rdi, rdi
0x180004f93  jz      short loc_180004FA7
0x180004f95  lea     r8, [rbp+arg_0]
0x180004f99  xor     ecx, ecx
0x180004f9b  lea     rdx, [rbp+var_30]
0x180004f9f  mov     rax, rdi
0x180004fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa7  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180004fab  mov     eax, dword ptr [rbp+arg_0]
0x180004fae  mov     [rbx+10h], eax
0x180004fb1  sub     ecx, 1
0x180004fb4  jz      short loc_180004FCC
0x180004fb6  sub     ecx, 1
0x180004fb9  jz      short loc_180004FC6
0x180004fbb  cmp     ecx, 1
0x180004fbe  jnz     short loc_180004FD0
0x180004fc0  or      dword ptr [rbx+4], 4
0x180004fc4  jmp     short loc_180004FD0
0x180004fc6  or      dword ptr [rbx+4], 2
0x180004fca  jmp     short loc_180004FD0
0x180004fcc  or      dword ptr [rbx+4], 1
0x180004fd0  mov     rbx, [rsp+50h+arg_8]
0x180004fd5  mov     rdi, [rsp+50h+arg_10]
0x180004fda  add     rsp, 50h
0x180004fde  pop     rbp
0x180004fdf  retn
```
