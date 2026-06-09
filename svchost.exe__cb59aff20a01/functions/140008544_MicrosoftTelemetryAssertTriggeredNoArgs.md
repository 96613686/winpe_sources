# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x140008544`
- end: `0x1400085e6`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006080`

## callees

- `0x140008544`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x140008565`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x140008565`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000857f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000857f`

## string_xrefs

- `0x140008559`: `ntdll.dll`

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
0x140008544  push    rbp
0x140008546  mov     rbp, rsp
0x140008549  sub     rsp, 60h
0x14000854d  lea     r8, [rbp+phModule]; phModule
0x140008551  mov     [rbp+phModule], 0
0x140008559  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x140008560  mov     ecx, 2; dwFlags
0x140008565  call    cs:__imp_GetModuleHandleExA
0x14000856b  test    eax, eax
0x14000856d  jz      short loc_1400085E0
0x14000856f  mov     rcx, [rbp+phModule]; hModule
0x140008573  test    rcx, rcx
0x140008576  jz      short loc_1400085E0
0x140008578  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x14000857f  call    cs:__imp_GetProcAddress
0x140008585  mov     rdx, rax
0x140008588  test    rax, rax
0x14000858b  jz      short loc_1400085E0
0x14000858d  xor     eax, eax
0x14000858f  lea     rcx, [rbp+var_40]
0x140008593  mov     [rbp+var_10], eax
0x140008596  xorps   xmm0, xmm0
0x140008599  movups  [rbp+var_20], xmm0
0x14000859d  lea     rax, __ImageBase
0x1400085a4  movups  [rbp+var_40], xmm0
0x1400085a8  mov     qword ptr [rbp+var_40+8], rax
0x1400085ac  mov     rax, [rbp+8]
0x1400085b0  movups  [rbp+var_30], xmm0
0x1400085b4  mov     qword ptr [rbp+var_30], rax
0x1400085b8  or      eax, 0FFFFFFFFh
0x1400085bb  mov     dword ptr [rbp+var_20+8], eax
0x1400085be  mov     dword ptr [rbp+var_20+0Ch], eax
0x1400085c1  mov     rax, rdx
0x1400085c4  mov     dword ptr [rbp+var_40], 0Bh
0x1400085cb  mov     byte ptr [rbp+var_10], 1
0x1400085cf  mov     byte ptr [rbp+var_30+8], 0
0x1400085d3  mov     qword ptr [rbp+var_20], 0
0x1400085db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085e0  add     rsp, 60h
0x1400085e4  pop     rbp
0x1400085e5  retn
```
