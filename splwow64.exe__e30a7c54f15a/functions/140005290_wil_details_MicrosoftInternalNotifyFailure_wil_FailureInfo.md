# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140005290`
- end: `0x1400053a0`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `272`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005290`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140005340`
- `KERNEL32!GetProcAddress` at `0x140005340`
- `KERNEL32!GetModuleHandleW` at `0x140005324`
- `KERNEL32!GetModuleHandleW` at `0x140005324`

## string_xrefs

- `0x14000531d`: `kernelbase.dll`

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
0x140005290  mov     [rsp-8+arg_8], rbx
0x140005295  mov     [rsp-8+arg_10], rdi
0x14000529a  push    rbp
0x14000529b  mov     rbp, rsp
0x14000529e  sub     rsp, 50h
0x1400052a2  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1400052a9  xor     eax, eax
0x1400052ab  mov     [rbp+var_16], ax
0x1400052af  mov     rbx, rcx
0x1400052b2  mov     eax, [rcx+8]
0x1400052b5  mov     [rbp+var_30], eax
0x1400052b8  mov     rax, [rcx+18h]
0x1400052bc  mov     [rbp+var_28], rax
0x1400052c0  mov     al, [rcx]
0x1400052c2  mov     [rbp+var_20], al
0x1400052c5  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1400052cc  mov     [rbp+var_1E], ax
0x1400052d0  movzx   eax, word ptr [rcx+40h]
0x1400052d4  mov     [rbp+var_18], ax
0x1400052d8  mov     rax, [rcx+38h]
0x1400052dc  mov     [rbp+var_10], rax
0x1400052e0  mov     rax, [rcx+80h]
0x1400052e7  mov     [rbp+var_8], rax
0x1400052eb  mov     [rbp+var_2C], 0
0x1400052f2  mov     [rbp+var_1F], 0
0x1400052f6  mov     [rbp+var_1C], 0
0x1400052fd  mov     [rbp+var_14], 0
0x140005304  mov     [rbp+arg_0], 0
0x14000530c  test    rdi, rdi
0x14000530f  jnz     short loc_140005355
0x140005311  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAXEA; void * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140005318  test    rax, rax
0x14000531b  jnz     short loc_140005336
0x14000531d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140005324  call    cs:__imp_GetModuleHandleW
0x14000532a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAXEA, rax; void * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140005331  test    rax, rax
0x140005334  jz      short loc_140005349
0x140005336  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x14000533d  mov     rcx, rax; hModule
0x140005340  call    cs:__imp_GetProcAddress
0x140005346  mov     rdi, rax
0x140005349  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140005350  test    rdi, rdi
0x140005353  jz      short loc_140005367
0x140005355  lea     r8, [rbp+arg_0]
0x140005359  xor     ecx, ecx
0x14000535b  lea     rdx, [rbp+var_30]
0x14000535f  mov     rax, rdi
0x140005362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005367  movzx   ecx, byte ptr [rbp+arg_0+4]
0x14000536b  mov     eax, dword ptr [rbp+arg_0]
0x14000536e  mov     [rbx+10h], eax
0x140005371  sub     ecx, 1
0x140005374  jz      short loc_14000538C
0x140005376  sub     ecx, 1
0x140005379  jz      short loc_140005386
0x14000537b  cmp     ecx, 1
0x14000537e  jnz     short loc_140005390
0x140005380  or      dword ptr [rbx+4], 4
0x140005384  jmp     short loc_140005390
0x140005386  or      dword ptr [rbx+4], 2
0x14000538a  jmp     short loc_140005390
0x14000538c  or      dword ptr [rbx+4], 1
0x140005390  mov     rbx, [rsp+50h+arg_8]
0x140005395  mov     rdi, [rsp+50h+arg_10]
0x14000539a  add     rsp, 50h
0x14000539e  pop     rbp
0x14000539f  retn
```
