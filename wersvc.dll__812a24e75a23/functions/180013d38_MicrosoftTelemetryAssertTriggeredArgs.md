# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x180013d38`
- end: `0x180013dee`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `182`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800187f0`

## callees

- `0x180013d38`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013d7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013d7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180013d64`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180013d64`

## string_xrefs

- `0x180013d54`: `ntdll.dll`
- `0x180013db7`: `wersvc.dll`

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
        v5[4] = "wersvc.dll";
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
0x180013d38  mov     [rsp-8+arg_8], rbx
0x180013d3d  mov     [rsp-8+phModule], rcx
0x180013d42  push    rbp
0x180013d43  mov     rbp, rsp
0x180013d46  sub     rsp, 60h
0x180013d4a  mov     ebx, edx
0x180013d4c  mov     [rbp+phModule], 0
0x180013d54  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180013d5b  mov     ecx, 2; dwFlags
0x180013d60  lea     r8, [rbp+phModule]; phModule
0x180013d64  call    cs:__imp_GetModuleHandleExA
0x180013d6a  test    eax, eax
0x180013d6c  jz      short loc_180013DE3
0x180013d6e  mov     rcx, [rbp+phModule]; hModule
0x180013d72  test    rcx, rcx
0x180013d75  jz      short loc_180013DE3
0x180013d77  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180013d7e  call    cs:__imp_GetProcAddress
0x180013d84  mov     rdx, rax
0x180013d87  test    rax, rax
0x180013d8a  jz      short loc_180013DE3
0x180013d8c  xor     eax, eax
0x180013d8e  lea     rcx, [rbp+var_40]
0x180013d92  mov     [rbp+var_10], eax
0x180013d95  xorps   xmm0, xmm0
0x180013d98  movups  [rbp+var_20], xmm0
0x180013d9c  lea     rax, __ImageBase
0x180013da3  movups  [rbp+var_40], xmm0
0x180013da7  mov     qword ptr [rbp+var_40+8], rax
0x180013dab  mov     rax, [rbp+8]
0x180013daf  movups  [rbp+var_30], xmm0
0x180013db3  mov     qword ptr [rbp+var_30], rax
0x180013db7  lea     rax, aWersvcDll; "wersvc.dll"
0x180013dbe  mov     qword ptr [rbp+var_20], rax
0x180013dc2  mov     rax, rdx
0x180013dc5  mov     dword ptr [rbp+var_40], 0Bh
0x180013dcc  mov     byte ptr [rbp+var_10], 1
0x180013dd0  mov     byte ptr [rbp+var_30+8], 1
0x180013dd4  mov     dword ptr [rbp+var_20+8], ebx
0x180013dd7  mov     dword ptr [rbp+var_20+0Ch], 0
0x180013dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013de3  mov     rbx, [rsp+60h+arg_8]
0x180013de8  add     rsp, 60h
0x180013dec  pop     rbp
0x180013ded  retn
```
