# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x140008b84`
- end: `0x140008c33`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006520`

## callees

- `0x140008b84`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x140008ba5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x140008ba5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008bc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008bc5`

## string_xrefs

- `0x140008b99`: `ntdll.dll`

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
0x140008b84  push    rbp
0x140008b86  mov     rbp, rsp
0x140008b89  sub     rsp, 60h
0x140008b8d  lea     r8, [rbp+phModule]; phModule
0x140008b91  mov     [rbp+phModule], 0
0x140008b99  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x140008ba0  mov     ecx, 2; dwFlags
0x140008ba5  call    cs:__imp_GetModuleHandleExA
0x140008bac  nop     dword ptr [rax+rax+00h]
0x140008bb1  test    eax, eax
0x140008bb3  jz      short loc_140008C2C
0x140008bb5  mov     rcx, [rbp+phModule]; hModule
0x140008bb9  test    rcx, rcx
0x140008bbc  jz      short loc_140008C2C
0x140008bbe  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x140008bc5  call    cs:__imp_GetProcAddress
0x140008bcc  nop     dword ptr [rax+rax+00h]
0x140008bd1  mov     rdx, rax
0x140008bd4  test    rax, rax
0x140008bd7  jz      short loc_140008C2C
0x140008bd9  xor     eax, eax
0x140008bdb  lea     rcx, [rbp+var_40]
0x140008bdf  mov     [rbp+var_10], eax
0x140008be2  xorps   xmm0, xmm0
0x140008be5  movups  [rbp+var_20], xmm0
0x140008be9  lea     rax, __ImageBase
0x140008bf0  movups  [rbp+var_40], xmm0
0x140008bf4  mov     qword ptr [rbp+var_40+8], rax
0x140008bf8  mov     rax, [rbp+8]
0x140008bfc  movups  [rbp+var_30], xmm0
0x140008c00  mov     qword ptr [rbp+var_30], rax
0x140008c04  or      eax, 0FFFFFFFFh
0x140008c07  mov     dword ptr [rbp+var_20+8], eax
0x140008c0a  mov     dword ptr [rbp+var_20+0Ch], eax
0x140008c0d  mov     rax, rdx
0x140008c10  mov     dword ptr [rbp+var_40], 0Bh
0x140008c17  mov     byte ptr [rbp+var_10], 1
0x140008c1b  mov     byte ptr [rbp+var_30+8], 0
0x140008c1f  mov     qword ptr [rbp+var_20], 0
0x140008c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c2c  add     rsp, 60h
0x140008c30  pop     rbp
0x140008c31  retn
```
