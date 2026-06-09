# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1800061b4`
- end: `0x180006256`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `int()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002234`
- `0x180005810`

## callees

- `0x1800061b4`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800061d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800061d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800061ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800061ef`

## string_xrefs

- `0x1800061c9`: `ntdll.dll`

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
0x1800061b4  push    rbp
0x1800061b6  mov     rbp, rsp
0x1800061b9  sub     rsp, 60h
0x1800061bd  lea     r8, [rbp+phModule]; phModule
0x1800061c1  mov     [rbp+phModule], 0
0x1800061c9  lea     rdx, ModuleName; "ntdll.dll"
0x1800061d0  mov     ecx, 2; dwFlags
0x1800061d5  call    cs:__imp_GetModuleHandleExA
0x1800061db  test    eax, eax
0x1800061dd  jz      short loc_180006250
0x1800061df  mov     rcx, [rbp+phModule]; hModule
0x1800061e3  test    rcx, rcx
0x1800061e6  jz      short loc_180006250
0x1800061e8  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x1800061ef  call    cs:__imp_GetProcAddress
0x1800061f5  mov     rdx, rax
0x1800061f8  test    rax, rax
0x1800061fb  jz      short loc_180006250
0x1800061fd  xor     eax, eax
0x1800061ff  lea     rcx, [rbp+var_40]
0x180006203  mov     [rbp+var_10], eax
0x180006206  xorps   xmm0, xmm0
0x180006209  movups  [rbp+var_20], xmm0
0x18000620d  lea     rax, cs:180000000h
0x180006214  movups  [rbp+var_40], xmm0
0x180006218  mov     qword ptr [rbp+var_40+8], rax
0x18000621c  mov     rax, [rbp+8]
0x180006220  movups  [rbp+var_30], xmm0
0x180006224  mov     qword ptr [rbp+var_30], rax
0x180006228  or      eax, 0FFFFFFFFh
0x18000622b  mov     dword ptr [rbp+var_20+8], eax
0x18000622e  mov     dword ptr [rbp+var_20+0Ch], eax
0x180006231  mov     rax, rdx
0x180006234  mov     dword ptr [rbp+var_40], 0Bh
0x18000623b  mov     byte ptr [rbp+var_10], 1
0x18000623f  mov     byte ptr [rbp+var_30+8], 0
0x180006243  mov     qword ptr [rbp+var_20], 0
0x18000624b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006250  add     rsp, 60h
0x180006254  pop     rbp
0x180006255  retn
```
