# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18001a0e8`
- end: `0x18001a18a`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800194e0`

## callees

- `0x18001a0e8`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a123`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a123`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001a109`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001a109`

## string_xrefs

- `0x18001a0fd`: `ntdll.dll`

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
        v2[1] = &_ImageBase;
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
0x18001a0e8  push    rbp
0x18001a0ea  mov     rbp, rsp
0x18001a0ed  sub     rsp, 60h
0x18001a0f1  lea     r8, [rbp+phModule]; phModule
0x18001a0f5  mov     [rbp+phModule], 0
0x18001a0fd  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18001a104  mov     ecx, 2; dwFlags
0x18001a109  call    cs:__imp_GetModuleHandleExA
0x18001a10f  test    eax, eax
0x18001a111  jz      short loc_18001A184
0x18001a113  mov     rcx, [rbp+phModule]; hModule
0x18001a117  test    rcx, rcx
0x18001a11a  jz      short loc_18001A184
0x18001a11c  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18001a123  call    cs:__imp_GetProcAddress
0x18001a129  mov     rdx, rax
0x18001a12c  test    rax, rax
0x18001a12f  jz      short loc_18001A184
0x18001a131  xor     eax, eax
0x18001a133  lea     rcx, [rbp+var_40]
0x18001a137  mov     [rbp+var_10], eax
0x18001a13a  xorps   xmm0, xmm0
0x18001a13d  movups  [rbp+var_20], xmm0
0x18001a141  lea     rax, __ImageBase
0x18001a148  movups  [rbp+var_40], xmm0
0x18001a14c  mov     qword ptr [rbp+var_40+8], rax
0x18001a150  mov     rax, [rbp+8]
0x18001a154  movups  [rbp+var_30], xmm0
0x18001a158  mov     qword ptr [rbp+var_30], rax
0x18001a15c  or      eax, 0FFFFFFFFh
0x18001a15f  mov     dword ptr [rbp+var_20+8], eax
0x18001a162  mov     dword ptr [rbp+var_20+0Ch], eax
0x18001a165  mov     rax, rdx
0x18001a168  mov     dword ptr [rbp+var_40], 0Bh
0x18001a16f  mov     byte ptr [rbp+var_10], 1
0x18001a173  mov     byte ptr [rbp+var_30+8], 0
0x18001a177  mov     qword ptr [rbp+var_20], 0
0x18001a17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a184  add     rsp, 60h
0x18001a188  pop     rbp
0x18001a189  retn
```
