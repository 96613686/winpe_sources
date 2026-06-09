# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180013df4`
- end: `0x180013e96`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `50`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d640`
- `0x18000f9f0`
- `0x1800106f4`
- `0x180010f04`
- `0x1800137d0`
- `0x180013b60`
- `0x180014378`
- `0x180014934`
- `0x180014c54`
- `0x180014fa4`
- `0x180015d18`
- `0x180016ac0`
- `0x1800181f8`
- `0x180018700`
- `0x180018880`
- `0x180018910`
- `0x180018950`
- `0x180018a30`
- `0x180018a70`
- `0x180019ef4`
- `0x18001a6b0`
- `0x18001c604`
- `0x18001caf4`
- `0x18001d7c0`
- `0x18001d9e8`
- `0x18001fb94`
- `0x180022d54`
- `0x180023208`
- `0x1800244c0`
- `0x180024784`
- `0x1800248f4`
- `0x1800254e0`
- `0x180025b0c`
- `0x180025f00`
- `0x1800261f8`
- `0x1800264dc`
- `0x180026788`
- `0x180027460`
- `0x180029280`
- `0x180029310`
- `0x180029690`
- `0x180029740`
- `0x1800297d0`
- `0x180029800`
- `0x180029cac`
- `0x18002accc`
- `0x18002b168`
- `0x18002b424`
- `0x18002c9dc`
- `0x18002f4ac`

## callees

- `0x180013df4`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013e2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013e2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180013e15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180013e15`

## string_xrefs

- `0x180013e09`: `ntdll.dll`

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
0x180013df4  push    rbp
0x180013df6  mov     rbp, rsp
0x180013df9  sub     rsp, 60h
0x180013dfd  lea     r8, [rbp+phModule]; phModule
0x180013e01  mov     [rbp+phModule], 0
0x180013e09  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180013e10  mov     ecx, 2; dwFlags
0x180013e15  call    cs:__imp_GetModuleHandleExA
0x180013e1b  test    eax, eax
0x180013e1d  jz      short loc_180013E90
0x180013e1f  mov     rcx, [rbp+phModule]; hModule
0x180013e23  test    rcx, rcx
0x180013e26  jz      short loc_180013E90
0x180013e28  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180013e2f  call    cs:__imp_GetProcAddress
0x180013e35  mov     rdx, rax
0x180013e38  test    rax, rax
0x180013e3b  jz      short loc_180013E90
0x180013e3d  xor     eax, eax
0x180013e3f  lea     rcx, [rbp+var_40]
0x180013e43  mov     [rbp+var_10], eax
0x180013e46  xorps   xmm0, xmm0
0x180013e49  movups  [rbp+var_20], xmm0
0x180013e4d  lea     rax, __ImageBase
0x180013e54  movups  [rbp+var_40], xmm0
0x180013e58  mov     qword ptr [rbp+var_40+8], rax
0x180013e5c  mov     rax, [rbp+8]
0x180013e60  movups  [rbp+var_30], xmm0
0x180013e64  mov     qword ptr [rbp+var_30], rax
0x180013e68  or      eax, 0FFFFFFFFh
0x180013e6b  mov     dword ptr [rbp+var_20+8], eax
0x180013e6e  mov     dword ptr [rbp+var_20+0Ch], eax
0x180013e71  mov     rax, rdx
0x180013e74  mov     dword ptr [rbp+var_40], 0Bh
0x180013e7b  mov     byte ptr [rbp+var_10], 1
0x180013e7f  mov     byte ptr [rbp+var_30+8], 0
0x180013e83  mov     qword ptr [rbp+var_20], 0
0x180013e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e90  add     rsp, 60h
0x180013e94  pop     rbp
0x180013e95  retn
```
