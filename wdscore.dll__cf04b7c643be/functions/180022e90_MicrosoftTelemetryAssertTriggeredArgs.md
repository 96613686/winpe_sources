# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x180022e90`
- end: `0x180022f46`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d920`
- `0x18001dc70`

## callees

- `0x180022e90`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180022edc`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180022edc`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExA` at `0x180022ebc`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExA` at `0x180022ebc`

## string_xrefs

- `0x180022eb0`: `ntdll.dll`

## pseudocode

```c
int __fastcall MicrosoftTelemetryAssertTriggeredArgs(__int64 a1, int a2, int a3)
{
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v9[5]; // [rsp+28h] [rbp-40h] BYREF
  int v10; // [rsp+50h] [rbp-18h]
  int v11; // [rsp+54h] [rbp-14h]
  int v12; // [rsp+58h] [rbp-10h]
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+20h]

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExA(2u, "ntdll.dll", &phModule);
  if ( (_DWORD)ProcAddress )
  {
    if ( phModule )
    {
      ProcAddress = GetProcAddress(phModule, "MicrosoftTelemetryAssertTriggeredUM");
      if ( ProcAddress )
      {
        v12 = 1;
        v9[1] = 0x180000000uLL;
        v9[3] = 1;
        v9[2] = retaddr;
        v9[0] = 11;
        v9[4] = a1;
        v10 = a2;
        v11 = a3;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v9);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x180022e90  push    rbp
0x180022e92  push    rbx
0x180022e93  push    rsi
0x180022e94  push    rdi
0x180022e95  mov     rbp, rsp
0x180022e98  sub     rsp, 68h
0x180022e9c  mov     ebx, r8d
0x180022e9f  mov     [rbp+phModule], 0
0x180022ea7  mov     edi, edx
0x180022ea9  lea     r8, [rbp+phModule]; phModule
0x180022ead  mov     rsi, rcx
0x180022eb0  lea     rdx, ModuleName; "ntdll.dll"
0x180022eb7  mov     ecx, 2; dwFlags
0x180022ebc  call    cs:__imp_GetModuleHandleExA
0x180022ec3  nop     dword ptr [rax+rax+00h]
0x180022ec8  test    eax, eax
0x180022eca  jz      short loc_180022F3C
0x180022ecc  mov     rcx, [rbp+phModule]; hModule
0x180022ed0  test    rcx, rcx
0x180022ed3  jz      short loc_180022F3C
0x180022ed5  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x180022edc  call    cs:__imp_GetProcAddress
0x180022ee3  nop     dword ptr [rax+rax+00h]
0x180022ee8  mov     rdx, rax
0x180022eeb  test    rax, rax
0x180022eee  jz      short loc_180022F3C
0x180022ef0  xor     eax, eax
0x180022ef2  lea     rcx, [rbp+var_40]
0x180022ef6  mov     [rbp+var_10], eax
0x180022ef9  xorps   xmm0, xmm0
0x180022efc  movups  [rbp+var_20], xmm0
0x180022f00  lea     rax, cs:180000000h
0x180022f07  movups  [rbp+var_40], xmm0
0x180022f0b  mov     qword ptr [rbp+var_40+8], rax
0x180022f0f  mov     rax, [rbp+20h]
0x180022f13  movups  [rbp+var_30], xmm0
0x180022f17  mov     qword ptr [rbp+var_30], rax
0x180022f1b  mov     rax, rdx
0x180022f1e  mov     dword ptr [rbp+var_40], 0Bh
0x180022f25  mov     byte ptr [rbp+var_10], 1
0x180022f29  mov     byte ptr [rbp+var_30+8], 1
0x180022f2d  mov     qword ptr [rbp+var_20], rsi
0x180022f31  mov     dword ptr [rbp+var_20+8], edi
0x180022f34  mov     dword ptr [rbp+var_20+0Ch], ebx
0x180022f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f3c  add     rsp, 68h
0x180022f40  pop     rdi
0x180022f41  pop     rsi
0x180022f42  pop     rbx
0x180022f43  pop     rbp
0x180022f44  retn
```
