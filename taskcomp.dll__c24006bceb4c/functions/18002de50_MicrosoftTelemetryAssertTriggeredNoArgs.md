# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18002de50`
- end: `0x18002def2`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018d00`

## callees

- `0x18002de50`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002de8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002de8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002de71`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002de71`

## string_xrefs

- `0x18002de65`: `ntdll.dll`

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
0x18002de50  push    rbp
0x18002de52  mov     rbp, rsp
0x18002de55  sub     rsp, 60h
0x18002de59  lea     r8, [rbp+phModule]; phModule
0x18002de5d  mov     [rbp+phModule], 0
0x18002de65  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18002de6c  mov     ecx, 2; dwFlags
0x18002de71  call    cs:__imp_GetModuleHandleExA
0x18002de77  test    eax, eax
0x18002de79  jz      short loc_18002DEEC
0x18002de7b  mov     rcx, [rbp+phModule]; hModule
0x18002de7f  test    rcx, rcx
0x18002de82  jz      short loc_18002DEEC
0x18002de84  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18002de8b  call    cs:__imp_GetProcAddress
0x18002de91  mov     rdx, rax
0x18002de94  test    rax, rax
0x18002de97  jz      short loc_18002DEEC
0x18002de99  xor     eax, eax
0x18002de9b  lea     rcx, [rbp+var_40]
0x18002de9f  mov     [rbp+var_10], eax
0x18002dea2  xorps   xmm0, xmm0
0x18002dea5  movups  [rbp+var_20], xmm0
0x18002dea9  lea     rax, __ImageBase
0x18002deb0  movups  [rbp+var_40], xmm0
0x18002deb4  mov     qword ptr [rbp+var_40+8], rax
0x18002deb8  mov     rax, [rbp+8]
0x18002debc  movups  [rbp+var_30], xmm0
0x18002dec0  mov     qword ptr [rbp+var_30], rax
0x18002dec4  or      eax, 0FFFFFFFFh
0x18002dec7  mov     dword ptr [rbp+var_20+8], eax
0x18002deca  mov     dword ptr [rbp+var_20+0Ch], eax
0x18002decd  mov     rax, rdx
0x18002ded0  mov     dword ptr [rbp+var_40], 0Bh
0x18002ded7  mov     byte ptr [rbp+var_10], 1
0x18002dedb  mov     byte ptr [rbp+var_30+8], 0
0x18002dedf  mov     qword ptr [rbp+var_20], 0
0x18002dee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002deec  add     rsp, 60h
0x18002def0  pop     rbp
0x18002def1  retn
```
