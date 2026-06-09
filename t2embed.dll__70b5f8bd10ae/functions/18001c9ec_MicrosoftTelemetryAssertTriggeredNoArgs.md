# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18001c9ec`
- end: `0x18001ca8e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `50`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001ce4`
- `0x180002bd0`
- `0x180004320`
- `0x180006548`
- `0x1800067cc`
- `0x180006b30`
- `0x180006c10`
- `0x180006d30`
- `0x180007210`
- `0x1800075a0`
- `0x180007bf0`
- `0x180007dc0`
- `0x180007fb0`
- `0x180008230`
- `0x180008540`
- `0x180008780`
- `0x1800088a0`
- `0x180009580`
- `0x180009770`
- `0x180009a50`
- `0x180009d40`
- `0x18000b0cc`
- `0x18000b1f0`
- `0x18000b4e0`
- `0x18000b728`
- `0x18000bc7c`
- `0x18000bde0`
- `0x18000d5a0`
- `0x18000d900`
- `0x18000db44`
- `0x18000de70`
- `0x18000e12c`
- `0x18000e2d4`
- `0x18000e640`
- `0x18000e840`
- `0x18000ea00`
- `0x18000eacc`
- `0x18000eb94`
- `0x18000ecc8`
- `0x18000ed70`
- `0x1800119f8`
- `0x180012a18`
- `0x1800156e8`
- `0x180017920`
- `0x180017cf0`
- `0x18001a414`
- `0x18001c5dc`
- `0x18001ce2c`
- `0x180029a94`
- `0x18002a344`

## callees

- `0x18001c9ec`
- `0x18002b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001ca27`
- `KERNEL32!GetProcAddress` at `0x18001ca27`
- `KERNEL32!GetModuleHandleExA` at `0x18001ca0d`
- `KERNEL32!GetModuleHandleExA` at `0x18001ca0d`

## string_xrefs

- `0x18001ca01`: `ntdll.dll`

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
0x18001c9ec  push    rbp
0x18001c9ee  mov     rbp, rsp
0x18001c9f1  sub     rsp, 60h
0x18001c9f5  lea     r8, [rbp+phModule]; phModule
0x18001c9f9  mov     [rbp+phModule], 0
0x18001ca01  lea     rdx, ModuleName; "ntdll.dll"
0x18001ca08  mov     ecx, 2; dwFlags
0x18001ca0d  call    cs:__imp_GetModuleHandleExA
0x18001ca13  test    eax, eax
0x18001ca15  jz      short loc_18001CA88
0x18001ca17  mov     rcx, [rbp+phModule]; hModule
0x18001ca1b  test    rcx, rcx
0x18001ca1e  jz      short loc_18001CA88
0x18001ca20  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18001ca27  call    cs:__imp_GetProcAddress
0x18001ca2d  mov     rdx, rax
0x18001ca30  test    rax, rax
0x18001ca33  jz      short loc_18001CA88
0x18001ca35  xor     eax, eax
0x18001ca37  lea     rcx, [rbp+var_40]
0x18001ca3b  mov     [rbp+var_10], eax
0x18001ca3e  xorps   xmm0, xmm0
0x18001ca41  movups  [rbp+var_20], xmm0
0x18001ca45  lea     rax, cs:180000000h
0x18001ca4c  movups  [rbp+var_40], xmm0
0x18001ca50  mov     qword ptr [rbp+var_40+8], rax
0x18001ca54  mov     rax, [rbp+8]
0x18001ca58  movups  [rbp+var_30], xmm0
0x18001ca5c  mov     qword ptr [rbp+var_30], rax
0x18001ca60  or      eax, 0FFFFFFFFh
0x18001ca63  mov     dword ptr [rbp+var_20+8], eax
0x18001ca66  mov     dword ptr [rbp+var_20+0Ch], eax
0x18001ca69  mov     rax, rdx
0x18001ca6c  mov     dword ptr [rbp+var_40], 0Bh
0x18001ca73  mov     byte ptr [rbp+var_10], 1
0x18001ca77  mov     byte ptr [rbp+var_30+8], 0
0x18001ca7b  mov     qword ptr [rbp+var_20], 0
0x18001ca83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca88  add     rsp, 60h
0x18001ca8c  pop     rbp
0x18001ca8d  retn
```
