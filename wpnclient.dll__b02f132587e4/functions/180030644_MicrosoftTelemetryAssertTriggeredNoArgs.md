# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180030644`
- end: `0x1800306e6`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e9e0`
- `0x18002ea70`
- `0x18002ffa0`
- `0x18002ffe0`
- `0x180030080`
- `0x1800303e0`
- `0x180030560`

## callees

- `0x180030644`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003067f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003067f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180030665`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180030665`

## string_xrefs

- `0x180030659`: `ntdll.dll`

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
0x180030644  push    rbp
0x180030646  mov     rbp, rsp
0x180030649  sub     rsp, 60h
0x18003064d  lea     r8, [rbp+phModule]; phModule
0x180030651  mov     [rbp+phModule], 0
0x180030659  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180030660  mov     ecx, 2; dwFlags
0x180030665  call    cs:__imp_GetModuleHandleExA
0x18003066b  test    eax, eax
0x18003066d  jz      short loc_1800306E0
0x18003066f  mov     rcx, [rbp+phModule]; hModule
0x180030673  test    rcx, rcx
0x180030676  jz      short loc_1800306E0
0x180030678  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18003067f  call    cs:__imp_GetProcAddress
0x180030685  mov     rdx, rax
0x180030688  test    rax, rax
0x18003068b  jz      short loc_1800306E0
0x18003068d  xor     eax, eax
0x18003068f  lea     rcx, [rbp+var_40]
0x180030693  mov     [rbp+var_10], eax
0x180030696  xorps   xmm0, xmm0
0x180030699  movups  [rbp+var_20], xmm0
0x18003069d  lea     rax, __ImageBase
0x1800306a4  movups  [rbp+var_40], xmm0
0x1800306a8  mov     qword ptr [rbp+var_40+8], rax
0x1800306ac  mov     rax, [rbp+8]
0x1800306b0  movups  [rbp+var_30], xmm0
0x1800306b4  mov     qword ptr [rbp+var_30], rax
0x1800306b8  or      eax, 0FFFFFFFFh
0x1800306bb  mov     dword ptr [rbp+var_20+8], eax
0x1800306be  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800306c1  mov     rax, rdx
0x1800306c4  mov     dword ptr [rbp+var_40], 0Bh
0x1800306cb  mov     byte ptr [rbp+var_10], 1
0x1800306cf  mov     byte ptr [rbp+var_30+8], 0
0x1800306d3  mov     qword ptr [rbp+var_20], 0
0x1800306db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306e0  add     rsp, 60h
0x1800306e4  pop     rbp
0x1800306e5  retn
```
