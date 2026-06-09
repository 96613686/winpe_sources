# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x18002fc44`
- end: `0x18002fcfa`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012f00`

## callees

- `0x18002fc44`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fc8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fc8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002fc70`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002fc70`

## string_xrefs

- `0x18002fcc3`: `winsta.dll`
- `0x18002fc60`: `ntdll.dll`

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
0x18002fc44  mov     [rsp-8+arg_8], rbx
0x18002fc49  mov     [rsp-8+phModule], rcx
0x18002fc4e  push    rbp
0x18002fc4f  mov     rbp, rsp
0x18002fc52  sub     rsp, 60h
0x18002fc56  mov     ebx, edx
0x18002fc58  mov     [rbp+phModule], 0
0x18002fc60  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18002fc67  mov     ecx, 2; dwFlags
0x18002fc6c  lea     r8, [rbp+phModule]; phModule
0x18002fc70  call    cs:__imp_GetModuleHandleExA
0x18002fc76  test    eax, eax
0x18002fc78  jz      short loc_18002FCEF
0x18002fc7a  mov     rcx, [rbp+phModule]; hModule
0x18002fc7e  test    rcx, rcx
0x18002fc81  jz      short loc_18002FCEF
0x18002fc83  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18002fc8a  call    cs:__imp_GetProcAddress
0x18002fc90  mov     rdx, rax
0x18002fc93  test    rax, rax
0x18002fc96  jz      short loc_18002FCEF
0x18002fc98  xor     eax, eax
0x18002fc9a  lea     rcx, [rbp+var_40]
0x18002fc9e  mov     [rbp+var_10], eax
0x18002fca1  xorps   xmm0, xmm0
0x18002fca4  movups  [rbp+var_20], xmm0
0x18002fca8  lea     rax, __ImageBase
0x18002fcaf  movups  [rbp+var_40], xmm0
0x18002fcb3  mov     qword ptr [rbp+var_40+8], rax
0x18002fcb7  mov     rax, [rbp+8]
0x18002fcbb  movups  [rbp+var_30], xmm0
0x18002fcbf  mov     qword ptr [rbp+var_30], rax
0x18002fcc3  lea     rax, aWinstaDll_0; "winsta.dll"
0x18002fcca  mov     qword ptr [rbp+var_20], rax
0x18002fcce  mov     rax, rdx
0x18002fcd1  mov     dword ptr [rbp+var_40], 0Bh
0x18002fcd8  mov     byte ptr [rbp+var_10], 1
0x18002fcdc  mov     byte ptr [rbp+var_30+8], 1
0x18002fce0  mov     dword ptr [rbp+var_20+8], ebx
0x18002fce3  mov     dword ptr [rbp+var_20+0Ch], 0
0x18002fcea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcef  mov     rbx, [rsp+60h+arg_8]
0x18002fcf4  add     rsp, 60h
0x18002fcf8  pop     rbp
0x18002fcf9  retn
```
