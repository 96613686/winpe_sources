# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x180032a14`
- end: `0x180032ad7`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013dd0`

## callees

- `0x180032a14`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032a60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032a60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180032a40`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180032a40`

## string_xrefs

- `0x180032a9f`: `winsta.dll`
- `0x180032a30`: `ntdll.dll`

## pseudocode

```c
int __fastcall MicrosoftTelemetryAssertTriggeredArgs(__int64 a1, unsigned int a2)
{
  FARPROC ProcAddress; // rax
  _QWORD v5[6]; // [rsp+20h] [rbp-40h] BYREF
  int v6; // [rsp+50h] [rbp-10h]
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+8h]
  HMODULE phModule; // [rsp+70h] [rbp+10h] BYREF

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExA(2u, "ntdll.dll", &phModule);
  if ( (_DWORD)ProcAddress )
  {
    if ( phModule )
    {
      ProcAddress = GetProcAddress(phModule, "MicrosoftTelemetryAssertTriggeredUM");
      if ( ProcAddress )
      {
        v6 = 1;
        v5[1] = &_ImageBase;
        v5[3] = 1;
        v5[2] = retaddr;
        v5[4] = "winsta.dll";
        v5[0] = 11;
        v5[5] = a2;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v5);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x180032a14  mov     [rsp-8+arg_8], rbx
0x180032a19  mov     [rsp-8+phModule], rcx
0x180032a1e  push    rbp
0x180032a1f  mov     rbp, rsp
0x180032a22  sub     rsp, 60h
0x180032a26  mov     ebx, edx
0x180032a28  mov     [rbp+phModule], 0
0x180032a30  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180032a37  mov     ecx, 2; dwFlags
0x180032a3c  lea     r8, [rbp+phModule]; phModule
0x180032a40  call    cs:__imp_GetModuleHandleExA
0x180032a47  nop     dword ptr [rax+rax+00h]
0x180032a4c  test    eax, eax
0x180032a4e  jz      short loc_180032ACB
0x180032a50  mov     rcx, [rbp+phModule]; hModule
0x180032a54  test    rcx, rcx
0x180032a57  jz      short loc_180032ACB
0x180032a59  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180032a60  call    cs:__imp_GetProcAddress
0x180032a67  nop     dword ptr [rax+rax+00h]
0x180032a6c  mov     rdx, rax
0x180032a6f  test    rax, rax
0x180032a72  jz      short loc_180032ACB
0x180032a74  xor     eax, eax
0x180032a76  lea     rcx, [rbp+var_40]
0x180032a7a  mov     [rbp+var_10], eax
0x180032a7d  xorps   xmm0, xmm0
0x180032a80  movups  [rbp+var_20], xmm0
0x180032a84  lea     rax, __ImageBase
0x180032a8b  movups  [rbp+var_40], xmm0
0x180032a8f  mov     qword ptr [rbp+var_40+8], rax
0x180032a93  mov     rax, [rbp+8]
0x180032a97  movups  [rbp+var_30], xmm0
0x180032a9b  mov     qword ptr [rbp+var_30], rax
0x180032a9f  lea     rax, aWinstaDll_0; "winsta.dll"
0x180032aa6  mov     qword ptr [rbp+var_20], rax
0x180032aaa  mov     rax, rdx
0x180032aad  mov     dword ptr [rbp+var_40], 0Bh
0x180032ab4  mov     byte ptr [rbp+var_10], 1
0x180032ab8  mov     byte ptr [rbp+var_30+8], 1
0x180032abc  mov     dword ptr [rbp+var_20+8], ebx
0x180032abf  mov     dword ptr [rbp+var_20+0Ch], 0
0x180032ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032acb  mov     rbx, [rsp+60h+arg_8]
0x180032ad0  add     rsp, 60h
0x180032ad4  pop     rbp
0x180032ad5  retn
```
