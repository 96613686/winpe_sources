# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18000d590`
- end: `0x18000d632`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c9d8`

## callees

- `0x18000d590`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d5cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d5cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000d5b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000d5b1`

## string_xrefs

- `0x18000d5a5`: `ntdll.dll`

## pseudocode

```c
int MicrosoftTelemetryAssertTriggeredNoArgs()
{
  FARPROC ProcAddress; // rax
  _QWORD v2[2]; // [rsp+20h] [rbp-40h] BYREF
  __int128 v3; // [rsp+30h] [rbp-30h]
  __int64 v4; // [rsp+40h] [rbp-20h]
  __int64 v5; // [rsp+48h] [rbp-18h]
  int v6; // [rsp+50h] [rbp-10h]
  unsigned __int64 retaddr; // [rsp+68h] [rbp+8h]
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
        v2[1] = 0x180000000uLL;
        v3 = retaddr;
        v5 = -1;
        v2[0] = 11;
        v4 = 0;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v2);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x18000d590  push    rbp
0x18000d592  mov     rbp, rsp
0x18000d595  sub     rsp, 60h
0x18000d599  lea     r8, [rbp+phModule]; phModule
0x18000d59d  mov     [rbp+phModule], 0
0x18000d5a5  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18000d5ac  mov     ecx, 2; dwFlags
0x18000d5b1  call    cs:__imp_GetModuleHandleExA
0x18000d5b7  test    eax, eax
0x18000d5b9  jz      short loc_18000D62C
0x18000d5bb  mov     rcx, [rbp+phModule]; hModule
0x18000d5bf  test    rcx, rcx
0x18000d5c2  jz      short loc_18000D62C
0x18000d5c4  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000d5cb  call    cs:__imp_GetProcAddress
0x18000d5d1  mov     rdx, rax
0x18000d5d4  test    rax, rax
0x18000d5d7  jz      short loc_18000D62C
0x18000d5d9  xor     eax, eax
0x18000d5db  lea     rcx, [rbp+var_40]
0x18000d5df  mov     [rbp+var_10], eax
0x18000d5e2  xorps   xmm0, xmm0
0x18000d5e5  movups  [rbp+var_20], xmm0
0x18000d5e9  lea     rax, cs:180000000h
0x18000d5f0  movups  [rbp+var_40], xmm0
0x18000d5f4  mov     qword ptr [rbp+var_40+8], rax
0x18000d5f8  mov     rax, [rbp+8]
0x18000d5fc  movups  [rbp+var_30], xmm0
0x18000d600  mov     qword ptr [rbp+var_30], rax
0x18000d604  or      eax, 0FFFFFFFFh
0x18000d607  mov     dword ptr [rbp+var_20+8], eax
0x18000d60a  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000d60d  mov     rax, rdx
0x18000d610  mov     dword ptr [rbp+var_40], 0Bh
0x18000d617  mov     byte ptr [rbp+var_10], 1
0x18000d61b  mov     byte ptr [rbp+var_30+8], 0
0x18000d61f  mov     qword ptr [rbp+var_20], 0
0x18000d627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d62c  add     rsp, 60h
0x18000d630  pop     rbp
0x18000d631  retn
```
