# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18002de84`
- end: `0x18002df26`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fd00`
- `0x1800121c0`
- `0x180012e30`
- `0x180016b80`
- `0x180019dc8`
- `0x18001a280`

## callees

- `0x18002de84`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002debf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002debf`
- `KERNEL32!GetModuleHandleExA` at `0x18002dea5`
- `KERNEL32!GetModuleHandleExA` at `0x18002dea5`

## string_xrefs

- `0x18002de99`: `ntdll.dll`

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
0x18002de84  push    rbp
0x18002de86  mov     rbp, rsp
0x18002de89  sub     rsp, 60h
0x18002de8d  lea     r8, [rbp+phModule]; phModule
0x18002de91  mov     [rbp+phModule], 0
0x18002de99  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18002dea0  mov     ecx, 2; dwFlags
0x18002dea5  call    cs:__imp_GetModuleHandleExA
0x18002deab  test    eax, eax
0x18002dead  jz      short loc_18002DF20
0x18002deaf  mov     rcx, [rbp+phModule]; hModule
0x18002deb3  test    rcx, rcx
0x18002deb6  jz      short loc_18002DF20
0x18002deb8  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18002debf  call    cs:__imp_GetProcAddress
0x18002dec5  mov     rdx, rax
0x18002dec8  test    rax, rax
0x18002decb  jz      short loc_18002DF20
0x18002decd  xor     eax, eax
0x18002decf  lea     rcx, [rbp+var_40]
0x18002ded3  mov     [rbp+var_10], eax
0x18002ded6  xorps   xmm0, xmm0
0x18002ded9  movups  [rbp+var_20], xmm0
0x18002dedd  lea     rax, __ImageBase
0x18002dee4  movups  [rbp+var_40], xmm0
0x18002dee8  mov     qword ptr [rbp+var_40+8], rax
0x18002deec  mov     rax, [rbp+8]
0x18002def0  movups  [rbp+var_30], xmm0
0x18002def4  mov     qword ptr [rbp+var_30], rax
0x18002def8  or      eax, 0FFFFFFFFh
0x18002defb  mov     dword ptr [rbp+var_20+8], eax
0x18002defe  mov     dword ptr [rbp+var_20+0Ch], eax
0x18002df01  mov     rax, rdx
0x18002df04  mov     dword ptr [rbp+var_40], 0Bh
0x18002df0b  mov     byte ptr [rbp+var_10], 1
0x18002df0f  mov     byte ptr [rbp+var_30+8], 0
0x18002df13  mov     qword ptr [rbp+var_20], 0
0x18002df1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df20  add     rsp, 60h
0x18002df24  pop     rbp
0x18002df25  retn
```
