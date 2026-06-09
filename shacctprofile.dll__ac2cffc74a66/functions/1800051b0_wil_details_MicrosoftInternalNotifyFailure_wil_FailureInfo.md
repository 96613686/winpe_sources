# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1800051b0`
- end: `0x1800052c0`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `272`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800051b0`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005260`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005260`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005244`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005244`

## string_xrefs

- `0x18000523d`: `kernelbase.dll`

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
0x1800051b0  mov     [rsp-8+arg_8], rbx
0x1800051b5  mov     [rsp-8+arg_10], rdi
0x1800051ba  push    rbp
0x1800051bb  mov     rbp, rsp
0x1800051be  sub     rsp, 50h
0x1800051c2  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800051c9  xor     eax, eax
0x1800051cb  mov     [rbp+var_16], ax
0x1800051cf  mov     rbx, rcx
0x1800051d2  mov     eax, [rcx+8]
0x1800051d5  mov     [rbp+var_30], eax
0x1800051d8  mov     rax, [rcx+18h]
0x1800051dc  mov     [rbp+var_28], rax
0x1800051e0  mov     al, [rcx]
0x1800051e2  mov     [rbp+var_20], al
0x1800051e5  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1800051ec  mov     [rbp+var_1E], ax
0x1800051f0  movzx   eax, word ptr [rcx+40h]
0x1800051f4  mov     [rbp+var_18], ax
0x1800051f8  mov     rax, [rcx+38h]
0x1800051fc  mov     [rbp+var_10], rax
0x180005200  mov     rax, [rcx+80h]
0x180005207  mov     [rbp+var_8], rax
0x18000520b  mov     [rbp+var_2C], 0
0x180005212  mov     [rbp+var_1F], 0
0x180005216  mov     [rbp+var_1C], 0
0x18000521d  mov     [rbp+var_14], 0
0x180005224  mov     [rbp+arg_0], 0
0x18000522c  test    rdi, rdi
0x18000522f  jnz     short loc_180005275
0x180005231  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005238  test    rax, rax
0x18000523b  jnz     short loc_180005256
0x18000523d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005244  call    cs:__imp_GetModuleHandleW
0x18000524a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005251  test    rax, rax
0x180005254  jz      short loc_180005269
0x180005256  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18000525d  mov     rcx, rax; hModule
0x180005260  call    cs:__imp_GetProcAddress
0x180005266  mov     rdi, rax
0x180005269  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180005270  test    rdi, rdi
0x180005273  jz      short loc_180005287
0x180005275  lea     r8, [rbp+arg_0]
0x180005279  xor     ecx, ecx
0x18000527b  lea     rdx, [rbp+var_30]
0x18000527f  mov     rax, rdi
0x180005282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005287  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000528b  mov     eax, dword ptr [rbp+arg_0]
0x18000528e  mov     [rbx+10h], eax
0x180005291  sub     ecx, 1
0x180005294  jz      short loc_1800052AC
0x180005296  sub     ecx, 1
0x180005299  jz      short loc_1800052A6
0x18000529b  cmp     ecx, 1
0x18000529e  jnz     short loc_1800052B0
0x1800052a0  or      dword ptr [rbx+4], 4
0x1800052a4  jmp     short loc_1800052B0
0x1800052a6  or      dword ptr [rbx+4], 2
0x1800052aa  jmp     short loc_1800052B0
0x1800052ac  or      dword ptr [rbx+4], 1
0x1800052b0  mov     rbx, [rsp+50h+arg_8]
0x1800052b5  mov     rdi, [rsp+50h+arg_10]
0x1800052ba  add     rsp, 50h
0x1800052be  pop     rbp
0x1800052bf  retn
```
