# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140005040`
- end: `0x140005151`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005040`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400050d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400050d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400050f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400050f0`

## string_xrefs

- `0x1400050cd`: `kernelbase.dll`

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
0x140005040  mov     [rsp-8+arg_8], rbx
0x140005045  mov     [rsp-8+arg_10], rdi
0x14000504a  push    rbp
0x14000504b  mov     rbp, rsp
0x14000504e  sub     rsp, 50h
0x140005052  mov     rbx, rcx
0x140005055  mov     [rbp+var_2C], 0
0x14000505c  mov     [rbp+var_1F], 0
0x140005060  mov     [rbp+var_1C], 0
0x140005067  xor     eax, eax
0x140005069  mov     [rbp+var_16], ax
0x14000506d  mov     eax, [rcx+8]
0x140005070  mov     [rbp+var_30], eax
0x140005073  mov     rax, [rcx+18h]
0x140005077  mov     [rbp+var_28], rax
0x14000507b  mov     al, [rcx]
0x14000507d  mov     [rbp+var_20], al
0x140005080  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140005087  mov     [rbp+var_1E], ax
0x14000508b  movzx   eax, word ptr [rcx+40h]
0x14000508f  mov     [rbp+var_18], ax
0x140005093  mov     [rbp+var_14], 0
0x14000509a  mov     rax, [rcx+38h]
0x14000509e  mov     [rbp+var_10], rax
0x1400050a2  mov     rax, [rcx+80h]
0x1400050a9  mov     [rbp+var_8], rax
0x1400050ad  mov     [rbp+arg_0], 0
0x1400050b5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1400050bc  test    rdi, rdi
0x1400050bf  jnz     short loc_140005105
0x1400050c1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400050c8  test    rax, rax
0x1400050cb  jnz     short loc_1400050E6
0x1400050cd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400050d4  call    cs:__imp_GetModuleHandleW
0x1400050da  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400050e1  test    rax, rax
0x1400050e4  jz      short loc_1400050F9
0x1400050e6  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1400050ed  mov     rcx, rax; hModule
0x1400050f0  call    cs:__imp_GetProcAddress
0x1400050f6  mov     rdi, rax
0x1400050f9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140005100  test    rdi, rdi
0x140005103  jz      short loc_140005118
0x140005105  lea     r8, [rbp+arg_0]
0x140005109  lea     rdx, [rbp+var_30]
0x14000510d  xor     ecx, ecx
0x14000510f  mov     rax, rdi
0x140005112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005117  nop
0x140005118  mov     eax, dword ptr [rbp+arg_0]
0x14000511b  mov     [rbx+10h], eax
0x14000511e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x140005122  sub     ecx, 1
0x140005125  jz      short loc_14000513D
0x140005127  sub     ecx, 1
0x14000512a  jz      short loc_140005137
0x14000512c  cmp     ecx, 1
0x14000512f  jnz     short loc_140005141
0x140005131  or      dword ptr [rbx+4], 4
0x140005135  jmp     short loc_140005141
0x140005137  or      dword ptr [rbx+4], 2
0x14000513b  jmp     short loc_140005141
0x14000513d  or      dword ptr [rbx+4], 1
0x140005141  mov     rbx, [rsp+50h+arg_8]
0x140005146  mov     rdi, [rsp+50h+arg_10]
0x14000514b  add     rsp, 50h
0x14000514f  pop     rbp
0x140005150  retn
```
