# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140005130`
- end: `0x14000524c`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `284`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005130`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400051e9`
- `KERNEL32!GetProcAddress` at `0x1400051e9`
- `KERNEL32!GetModuleHandleW` at `0x1400051cd`
- `KERNEL32!GetModuleHandleW` at `0x1400051cd`

## string_xrefs

- `0x1400051c6`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+28h] [rbp-38h] BYREF
  __int64 v6; // [rsp+30h] [rbp-30h]
  char v7; // [rsp+38h] [rbp-28h]
  char v8; // [rsp+39h] [rbp-27h]
  __int16 v9; // [rsp+3Ah] [rbp-26h]
  int v10; // [rsp+3Ch] [rbp-24h]
  __int16 v11; // [rsp+40h] [rbp-20h]
  __int16 v12; // [rsp+42h] [rbp-1Eh]
  int v13; // [rsp+44h] [rbp-1Ch]
  __int64 v14; // [rsp+48h] [rbp-18h]
  __int64 v15; // [rsp+50h] [rbp-10h]
  __int64 v16; // [rsp+70h] [rbp+10h] BYREF

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
0x140005130  mov     rax, rsp
0x140005133  push    rbp
0x140005134  mov     rbp, rsp
0x140005137  sub     rsp, 60h
0x14000513b  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x140005143  mov     [rax+10h], rbx
0x140005147  mov     [rax+18h], rdi
0x14000514b  mov     rbx, rcx
0x14000514e  mov     [rbp+var_34], 0
0x140005155  mov     [rbp+var_27], 0
0x140005159  mov     [rbp+var_24], 0
0x140005160  xor     eax, eax
0x140005162  mov     [rbp+var_1E], ax
0x140005166  mov     eax, [rcx+8]
0x140005169  mov     [rbp+var_38], eax
0x14000516c  mov     rax, [rcx+18h]
0x140005170  mov     [rbp+var_30], rax
0x140005174  mov     al, [rcx]
0x140005176  mov     [rbp+var_28], al
0x140005179  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140005180  mov     [rbp+var_26], ax
0x140005184  movzx   eax, word ptr [rcx+40h]
0x140005188  mov     [rbp+var_20], ax
0x14000518c  mov     [rbp+var_1C], 0
0x140005193  mov     rax, [rcx+38h]
0x140005197  mov     [rbp+var_18], rax
0x14000519b  mov     rax, [rcx+80h]
0x1400051a2  mov     [rbp+var_10], rax
0x1400051a6  mov     [rbp+arg_0], 0
0x1400051ae  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1400051b5  test    rdi, rdi
0x1400051b8  jnz     short loc_1400051FE
0x1400051ba  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400051c1  test    rax, rax
0x1400051c4  jnz     short loc_1400051DF
0x1400051c6  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400051cd  call    cs:__imp_GetModuleHandleW
0x1400051d3  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400051da  test    rax, rax
0x1400051dd  jz      short loc_1400051F2
0x1400051df  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1400051e6  mov     rcx, rax; hModule
0x1400051e9  call    cs:__imp_GetProcAddress
0x1400051ef  mov     rdi, rax
0x1400051f2  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1400051f9  test    rdi, rdi
0x1400051fc  jz      short loc_140005211
0x1400051fe  lea     r8, [rbp+arg_0]
0x140005202  lea     rdx, [rbp+var_38]
0x140005206  xor     ecx, ecx
0x140005208  mov     rax, rdi
0x14000520b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005210  nop
0x140005211  mov     eax, dword ptr [rbp+arg_0]
0x140005214  mov     [rbx+10h], eax
0x140005217  movzx   ecx, byte ptr [rbp+arg_0+4]
0x14000521b  sub     ecx, 1
0x14000521e  jz      short loc_140005236
0x140005220  sub     ecx, 1
0x140005223  jz      short loc_140005230
0x140005225  cmp     ecx, 1
0x140005228  jnz     short loc_14000523A
0x14000522a  or      dword ptr [rbx+4], 4
0x14000522e  jmp     short loc_14000523A
0x140005230  or      dword ptr [rbx+4], 2
0x140005234  jmp     short loc_14000523A
0x140005236  or      dword ptr [rbx+4], 1
0x14000523a  lea     r11, [rsp+60h+var_s0]
0x14000523f  mov     rbx, [r11+18h]
0x140005243  mov     rdi, [r11+20h]
0x140005247  mov     rsp, r11
0x14000524a  pop     rbp
0x14000524b  retn
```
