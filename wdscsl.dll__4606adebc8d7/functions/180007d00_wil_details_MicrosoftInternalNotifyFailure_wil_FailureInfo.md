# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180007d00`
- end: `0x180007e19`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `281`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007d00`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180007dad`
- `KERNEL32!GetProcAddress` at `0x180007dad`
- `KERNEL32!GetModuleHandleW` at `0x180007d8b`
- `KERNEL32!GetModuleHandleW` at `0x180007d8b`

## string_xrefs

- `0x180007d84`: `kernelbase.dll`

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
0x180007d00  mov     [rsp-8+arg_8], rbx
0x180007d05  mov     [rsp-8+arg_10], rsi
0x180007d0a  mov     [rsp-8+arg_18], rdi
0x180007d0f  push    rbp
0x180007d10  mov     rbp, rsp
0x180007d13  sub     rsp, 50h
0x180007d17  mov     eax, [rcx+8]
0x180007d1a  xor     esi, esi
0x180007d1c  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180007d23  mov     rbx, rcx
0x180007d26  mov     [rbp+var_30], eax
0x180007d29  mov     rax, [rcx+18h]
0x180007d2d  mov     [rbp+var_28], rax
0x180007d31  mov     al, [rcx]
0x180007d33  mov     [rbp+var_20], al
0x180007d36  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180007d3d  mov     [rbp+var_1E], ax
0x180007d41  movzx   eax, word ptr [rcx+40h]
0x180007d45  mov     [rbp+var_18], ax
0x180007d49  mov     rax, [rcx+38h]
0x180007d4d  mov     [rbp+var_10], rax
0x180007d51  mov     rax, [rcx+80h]
0x180007d58  mov     [rbp+var_8], rax
0x180007d5c  mov     [rbp+var_2C], esi
0x180007d5f  mov     [rbp+var_1F], sil
0x180007d63  mov     [rbp+var_1C], esi
0x180007d66  mov     [rbp+var_16], si
0x180007d6a  mov     [rbp+var_14], esi
0x180007d6d  mov     [rbp+arg_0], rsi
0x180007d71  test    rdi, rdi
0x180007d74  jnz     short loc_180007DC8
0x180007d76  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007d7d  mov     edi, esi
0x180007d7f  test    rax, rax
0x180007d82  jnz     short loc_180007DA3
0x180007d84  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007d8b  call    cs:__imp_GetModuleHandleW
0x180007d92  nop     dword ptr [rax+rax+00h]
0x180007d97  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007d9e  test    rax, rax
0x180007da1  jz      short loc_180007DBC
0x180007da3  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180007daa  mov     rcx, rax; hModule
0x180007dad  call    cs:__imp_GetProcAddress
0x180007db4  nop     dword ptr [rax+rax+00h]
0x180007db9  mov     rdi, rax
0x180007dbc  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180007dc3  test    rdi, rdi
0x180007dc6  jz      short loc_180007DDA
0x180007dc8  lea     r8, [rbp+arg_0]
0x180007dcc  xor     ecx, ecx
0x180007dce  lea     rdx, [rbp+var_30]
0x180007dd2  mov     rax, rdi
0x180007dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dda  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180007dde  mov     eax, dword ptr [rbp+arg_0]
0x180007de1  mov     [rbx+10h], eax
0x180007de4  sub     ecx, 1
0x180007de7  jz      short loc_180007DFF
0x180007de9  sub     ecx, 1
0x180007dec  jz      short loc_180007DF9
0x180007dee  cmp     ecx, 1
0x180007df1  jnz     short loc_180007E03
0x180007df3  or      dword ptr [rbx+4], 4
0x180007df7  jmp     short loc_180007E03
0x180007df9  or      dword ptr [rbx+4], 2
0x180007dfd  jmp     short loc_180007E03
0x180007dff  or      dword ptr [rbx+4], 1
0x180007e03  mov     rbx, [rsp+50h+arg_8]
0x180007e08  mov     rsi, [rsp+50h+arg_10]
0x180007e0d  mov     rdi, [rsp+50h+arg_18]
0x180007e12  add     rsp, 50h
0x180007e16  pop     rbp
0x180007e17  retn
```
