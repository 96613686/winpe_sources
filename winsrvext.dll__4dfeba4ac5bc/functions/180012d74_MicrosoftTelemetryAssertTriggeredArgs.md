# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x180012d74`
- end: `0x180012e38`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dda0`

## callees

- `0x180012d74`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180012da1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180012da1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012dc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012dc1`

## string_xrefs

- `0x180012d9a`: `ntdll.dll`

## pseudocode

```c
int __fastcall MicrosoftTelemetryAssertTriggeredArgs(__int64 a1, __int64 a2, int a3)
{
  FARPROC ProcAddress; // rax
  _QWORD v6[5]; // [rsp+20h] [rbp-40h] BYREF
  int v7; // [rsp+48h] [rbp-18h]
  int v8; // [rsp+4Ch] [rbp-14h]
  int v9; // [rsp+50h] [rbp-10h]
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
        v9 = 1;
        v6[1] = &_ImageBase;
        v6[3] = 1;
        v6[2] = retaddr;
        v6[4] = "IXPTellMeIf";
        v6[0] = 11;
        v7 = 0x20000;
        v8 = a3;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v6);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x180012d74  mov     [rsp-8+arg_8], rbx
0x180012d79  mov     [rsp-8+phModule], rcx
0x180012d7e  push    rbp
0x180012d7f  mov     rbp, rsp
0x180012d82  sub     rsp, 60h
0x180012d86  mov     ebx, r8d
0x180012d89  mov     [rbp+phModule], 0
0x180012d91  lea     r8, [rbp+phModule]; phModule
0x180012d95  mov     ecx, 2; dwFlags
0x180012d9a  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180012da1  call    cs:__imp_GetModuleHandleExA
0x180012da8  nop     dword ptr [rax+rax+00h]
0x180012dad  test    eax, eax
0x180012daf  jz      short loc_180012E2C
0x180012db1  mov     rcx, [rbp+phModule]; hModule
0x180012db5  test    rcx, rcx
0x180012db8  jz      short loc_180012E2C
0x180012dba  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180012dc1  call    cs:__imp_GetProcAddress
0x180012dc8  nop     dword ptr [rax+rax+00h]
0x180012dcd  mov     rdx, rax
0x180012dd0  test    rax, rax
0x180012dd3  jz      short loc_180012E2C
0x180012dd5  xor     eax, eax
0x180012dd7  lea     rcx, [rbp+var_40]
0x180012ddb  mov     [rbp+var_10], eax
0x180012dde  xorps   xmm0, xmm0
0x180012de1  movups  [rbp+var_20], xmm0
0x180012de5  lea     rax, __ImageBase
0x180012dec  movups  [rbp+var_40], xmm0
0x180012df0  mov     qword ptr [rbp+var_40+8], rax
0x180012df4  mov     rax, [rbp+8]
0x180012df8  movups  [rbp+var_30], xmm0
0x180012dfc  mov     qword ptr [rbp+var_30], rax
0x180012e00  lea     rax, aIxptellmeif; "IXPTellMeIf"
0x180012e07  mov     qword ptr [rbp+var_20], rax
0x180012e0b  mov     rax, rdx
0x180012e0e  mov     dword ptr [rbp+var_40], 0Bh
0x180012e15  mov     byte ptr [rbp+var_10], 1
0x180012e19  mov     byte ptr [rbp+var_30+8], 1
0x180012e1d  mov     dword ptr [rbp+var_20+8], 20000h
0x180012e24  mov     dword ptr [rbp+var_20+0Ch], ebx
0x180012e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e2c  mov     rbx, [rsp+60h+arg_8]
0x180012e31  add     rsp, 60h
0x180012e35  pop     rbp
0x180012e36  retn
```
