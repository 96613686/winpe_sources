# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180012028`
- end: `0x1800120ca`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005e04`

## callees

- `0x180012028`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180012049`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180012049`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012063`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012063`

## string_xrefs

- `0x18001203d`: `ntdll.dll`

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
0x180012028  push    rbp
0x18001202a  mov     rbp, rsp
0x18001202d  sub     rsp, 60h
0x180012031  lea     r8, [rbp+phModule]; phModule
0x180012035  mov     [rbp+phModule], 0
0x18001203d  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180012044  mov     ecx, 2; dwFlags
0x180012049  call    cs:__imp_GetModuleHandleExA
0x18001204f  test    eax, eax
0x180012051  jz      short loc_1800120C4
0x180012053  mov     rcx, [rbp+phModule]; hModule
0x180012057  test    rcx, rcx
0x18001205a  jz      short loc_1800120C4
0x18001205c  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180012063  call    cs:__imp_GetProcAddress
0x180012069  mov     rdx, rax
0x18001206c  test    rax, rax
0x18001206f  jz      short loc_1800120C4
0x180012071  xor     eax, eax
0x180012073  lea     rcx, [rbp+var_40]
0x180012077  mov     [rbp+var_10], eax
0x18001207a  xorps   xmm0, xmm0
0x18001207d  movups  [rbp+var_20], xmm0
0x180012081  lea     rax, cs:180000000h
0x180012088  movups  [rbp+var_40], xmm0
0x18001208c  mov     qword ptr [rbp+var_40+8], rax
0x180012090  mov     rax, [rbp+8]
0x180012094  movups  [rbp+var_30], xmm0
0x180012098  mov     qword ptr [rbp+var_30], rax
0x18001209c  or      eax, 0FFFFFFFFh
0x18001209f  mov     dword ptr [rbp+var_20+8], eax
0x1800120a2  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800120a5  mov     rax, rdx
0x1800120a8  mov     dword ptr [rbp+var_40], 0Bh
0x1800120af  mov     byte ptr [rbp+var_10], 1
0x1800120b3  mov     byte ptr [rbp+var_30+8], 0
0x1800120b7  mov     qword ptr [rbp+var_20], 0
0x1800120bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120c4  add     rsp, 60h
0x1800120c8  pop     rbp
0x1800120c9  retn
```
