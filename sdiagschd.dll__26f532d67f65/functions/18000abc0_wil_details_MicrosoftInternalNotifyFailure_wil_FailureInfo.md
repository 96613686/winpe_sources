# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18000abc0`
- end: `0x18000acda`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `282`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000abc0`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000ac4b`
- `KERNEL32!GetModuleHandleW` at `0x18000ac4b`
- `KERNEL32!GetProcAddress` at `0x18000ac6d`
- `KERNEL32!GetProcAddress` at `0x18000ac6d`

## string_xrefs

- `0x18000ac44`: `kernelbase.dll`

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
  ProcAddress = 0;
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
0x18000abc0  mov     [rsp-8+arg_8], rbx
0x18000abc5  mov     [rsp-8+arg_10], rsi
0x18000abca  mov     [rsp-8+arg_18], rdi
0x18000abcf  push    rbp
0x18000abd0  mov     rbp, rsp
0x18000abd3  sub     rsp, 50h
0x18000abd7  mov     rbx, rcx
0x18000abda  xor     esi, esi
0x18000abdc  mov     [rbp+var_2C], esi
0x18000abdf  mov     [rbp+var_1F], sil
0x18000abe3  mov     [rbp+var_1C], esi
0x18000abe6  mov     [rbp+var_16], si
0x18000abea  mov     eax, [rcx+8]
0x18000abed  mov     [rbp+var_30], eax
0x18000abf0  mov     rax, [rcx+18h]
0x18000abf4  mov     [rbp+var_28], rax
0x18000abf8  mov     al, [rcx]
0x18000abfa  mov     [rbp+var_20], al
0x18000abfd  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000ac04  mov     [rbp+var_1E], ax
0x18000ac08  movzx   eax, word ptr [rcx+40h]
0x18000ac0c  mov     [rbp+var_18], ax
0x18000ac10  mov     [rbp+var_14], esi
0x18000ac13  mov     rax, [rcx+38h]
0x18000ac17  mov     [rbp+var_10], rax
0x18000ac1b  mov     rax, [rcx+80h]
0x18000ac22  mov     [rbp+var_8], rax
0x18000ac26  mov     [rbp+arg_0], rsi
0x18000ac2a  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000ac31  test    rdi, rdi
0x18000ac34  jnz     short loc_18000AC88
0x18000ac36  mov     edi, esi
0x18000ac38  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ac3f  test    rax, rax
0x18000ac42  jnz     short loc_18000AC63
0x18000ac44  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000ac4b  call    cs:__imp_GetModuleHandleW
0x18000ac52  nop     dword ptr [rax+rax+00h]
0x18000ac57  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ac5e  test    rax, rax
0x18000ac61  jz      short loc_18000AC7C
0x18000ac63  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18000ac6a  mov     rcx, rax; hModule
0x18000ac6d  call    cs:__imp_GetProcAddress
0x18000ac74  nop     dword ptr [rax+rax+00h]
0x18000ac79  mov     rdi, rax
0x18000ac7c  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000ac83  test    rdi, rdi
0x18000ac86  jz      short loc_18000AC9B
0x18000ac88  lea     r8, [rbp+arg_0]
0x18000ac8c  lea     rdx, [rbp+var_30]
0x18000ac90  xor     ecx, ecx
0x18000ac92  mov     rax, rdi
0x18000ac95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac9a  nop
0x18000ac9b  mov     eax, dword ptr [rbp+arg_0]
0x18000ac9e  mov     [rbx+10h], eax
0x18000aca1  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000aca5  sub     ecx, 1
0x18000aca8  jz      short loc_18000ACC0
0x18000acaa  sub     ecx, 1
0x18000acad  jz      short loc_18000ACBA
0x18000acaf  cmp     ecx, 1
0x18000acb2  jnz     short loc_18000ACC4
0x18000acb4  or      dword ptr [rbx+4], 4
0x18000acb8  jmp     short loc_18000ACC4
0x18000acba  or      dword ptr [rbx+4], 2
0x18000acbe  jmp     short loc_18000ACC4
0x18000acc0  or      dword ptr [rbx+4], 1
0x18000acc4  mov     rbx, [rsp+50h+arg_8]
0x18000acc9  mov     rsi, [rsp+50h+arg_10]
0x18000acce  mov     rdi, [rsp+50h+arg_18]
0x18000acd3  add     rsp, 50h
0x18000acd7  pop     rbp
0x18000acd8  retn
```
