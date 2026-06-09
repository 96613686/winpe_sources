# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140007510`
- end: `0x140007620`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `272`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140007510`
- `0x14000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400075c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400075c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400075a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400075a4`

## string_xrefs

- `0x14000759d`: `kernelbase.dll`

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
0x140007510  mov     [rsp-8+arg_8], rbx
0x140007515  mov     [rsp-8+arg_10], rdi
0x14000751a  push    rbp
0x14000751b  mov     rbp, rsp
0x14000751e  sub     rsp, 50h
0x140007522  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140007529  xor     eax, eax
0x14000752b  mov     [rbp+var_16], ax
0x14000752f  mov     rbx, rcx
0x140007532  mov     eax, [rcx+8]
0x140007535  mov     [rbp+var_30], eax
0x140007538  mov     rax, [rcx+18h]
0x14000753c  mov     [rbp+var_28], rax
0x140007540  mov     al, [rcx]
0x140007542  mov     [rbp+var_20], al
0x140007545  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x14000754c  mov     [rbp+var_1E], ax
0x140007550  movzx   eax, word ptr [rcx+40h]
0x140007554  mov     [rbp+var_18], ax
0x140007558  mov     rax, [rcx+38h]
0x14000755c  mov     [rbp+var_10], rax
0x140007560  mov     rax, [rcx+80h]
0x140007567  mov     [rbp+var_8], rax
0x14000756b  mov     [rbp+var_2C], 0
0x140007572  mov     [rbp+var_1F], 0
0x140007576  mov     [rbp+var_1C], 0
0x14000757d  mov     [rbp+var_14], 0
0x140007584  mov     [rbp+arg_0], 0
0x14000758c  test    rdi, rdi
0x14000758f  jnz     short loc_1400075D5
0x140007591  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140007598  test    rax, rax
0x14000759b  jnz     short loc_1400075B6
0x14000759d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400075a4  call    cs:__imp_GetModuleHandleW
0x1400075aa  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400075b1  test    rax, rax
0x1400075b4  jz      short loc_1400075C9
0x1400075b6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1400075bd  mov     rcx, rax; hModule
0x1400075c0  call    cs:__imp_GetProcAddress
0x1400075c6  mov     rdi, rax
0x1400075c9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1400075d0  test    rdi, rdi
0x1400075d3  jz      short loc_1400075E7
0x1400075d5  lea     r8, [rbp+arg_0]
0x1400075d9  xor     ecx, ecx
0x1400075db  lea     rdx, [rbp+var_30]
0x1400075df  mov     rax, rdi
0x1400075e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400075e7  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1400075eb  mov     eax, dword ptr [rbp+arg_0]
0x1400075ee  mov     [rbx+10h], eax
0x1400075f1  sub     ecx, 1
0x1400075f4  jz      short loc_14000760C
0x1400075f6  sub     ecx, 1
0x1400075f9  jz      short loc_140007606
0x1400075fb  cmp     ecx, 1
0x1400075fe  jnz     short loc_140007610
0x140007600  or      dword ptr [rbx+4], 4
0x140007604  jmp     short loc_140007610
0x140007606  or      dword ptr [rbx+4], 2
0x14000760a  jmp     short loc_140007610
0x14000760c  or      dword ptr [rbx+4], 1
0x140007610  mov     rbx, [rsp+50h+arg_8]
0x140007615  mov     rdi, [rsp+50h+arg_10]
0x14000761a  add     rsp, 50h
0x14000761e  pop     rbp
0x14000761f  retn
```
