# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1800251a0`
- end: `0x1800252b0`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `272`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800251a0`
- `0x18002b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180025250`
- `KERNEL32!GetProcAddress` at `0x180025250`
- `KERNEL32!GetModuleHandleW` at `0x180025234`
- `KERNEL32!GetModuleHandleW` at `0x180025234`

## string_xrefs

- `0x18002522d`: `kernelbase.dll`

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
0x1800251a0  mov     [rsp-8+arg_8], rbx
0x1800251a5  mov     [rsp-8+arg_10], rdi
0x1800251aa  push    rbp
0x1800251ab  mov     rbp, rsp
0x1800251ae  sub     rsp, 50h
0x1800251b2  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800251b9  xor     eax, eax
0x1800251bb  mov     [rbp+var_16], ax
0x1800251bf  mov     rbx, rcx
0x1800251c2  mov     eax, [rcx+8]
0x1800251c5  mov     [rbp+var_30], eax
0x1800251c8  mov     rax, [rcx+18h]
0x1800251cc  mov     [rbp+var_28], rax
0x1800251d0  mov     al, [rcx]
0x1800251d2  mov     [rbp+var_20], al
0x1800251d5  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1800251dc  mov     [rbp+var_1E], ax
0x1800251e0  movzx   eax, word ptr [rcx+40h]
0x1800251e4  mov     [rbp+var_18], ax
0x1800251e8  mov     rax, [rcx+38h]
0x1800251ec  mov     [rbp+var_10], rax
0x1800251f0  mov     rax, [rcx+80h]
0x1800251f7  mov     [rbp+var_8], rax
0x1800251fb  mov     [rbp+var_2C], 0
0x180025202  mov     [rbp+var_1F], 0
0x180025206  mov     [rbp+var_1C], 0
0x18002520d  mov     [rbp+var_14], 0
0x180025214  mov     [rbp+arg_0], 0
0x18002521c  test    rdi, rdi
0x18002521f  jnz     short loc_180025265
0x180025221  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180025228  test    rax, rax
0x18002522b  jnz     short loc_180025246
0x18002522d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180025234  call    cs:__imp_GetModuleHandleW
0x18002523a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180025241  test    rax, rax
0x180025244  jz      short loc_180025259
0x180025246  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18002524d  mov     rcx, rax; hModule
0x180025250  call    cs:__imp_GetProcAddress
0x180025256  mov     rdi, rax
0x180025259  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180025260  test    rdi, rdi
0x180025263  jz      short loc_180025277
0x180025265  lea     r8, [rbp+arg_0]
0x180025269  xor     ecx, ecx
0x18002526b  lea     rdx, [rbp+var_30]
0x18002526f  mov     rax, rdi
0x180025272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025277  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18002527b  mov     eax, dword ptr [rbp+arg_0]
0x18002527e  mov     [rbx+10h], eax
0x180025281  sub     ecx, 1
0x180025284  jz      short loc_18002529C
0x180025286  sub     ecx, 1
0x180025289  jz      short loc_180025296
0x18002528b  cmp     ecx, 1
0x18002528e  jnz     short loc_1800252A0
0x180025290  or      dword ptr [rbx+4], 4
0x180025294  jmp     short loc_1800252A0
0x180025296  or      dword ptr [rbx+4], 2
0x18002529a  jmp     short loc_1800252A0
0x18002529c  or      dword ptr [rbx+4], 1
0x1800252a0  mov     rbx, [rsp+50h+arg_8]
0x1800252a5  mov     rdi, [rsp+50h+arg_10]
0x1800252aa  add     rsp, 50h
0x1800252ae  pop     rbp
0x1800252af  retn
```
