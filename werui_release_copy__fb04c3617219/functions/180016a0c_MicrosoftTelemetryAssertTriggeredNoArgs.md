# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180016a0c`
- end: `0x180016aae`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003650`
- `0x180012d68`

## callees

- `0x180016a0c`
- `0x180018010`

## import_xrefs

- `KERNEL32!GetModuleHandleExA` at `0x180016a2d`
- `KERNEL32!GetModuleHandleExA` at `0x180016a2d`
- `KERNEL32!GetProcAddress` at `0x180016a47`
- `KERNEL32!GetProcAddress` at `0x180016a47`

## string_xrefs

- `0x180016a21`: `ntdll.dll`

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
0x180016a0c  push    rbp
0x180016a0e  mov     rbp, rsp
0x180016a11  sub     rsp, 60h
0x180016a15  lea     r8, [rbp+phModule]; phModule
0x180016a19  mov     [rbp+phModule], 0
0x180016a21  lea     rdx, aNtdllDll_1; "ntdll.dll"
0x180016a28  mov     ecx, 2; dwFlags
0x180016a2d  call    cs:__imp_GetModuleHandleExA
0x180016a33  test    eax, eax
0x180016a35  jz      short loc_180016AA8
0x180016a37  mov     rcx, [rbp+phModule]; hModule
0x180016a3b  test    rcx, rcx
0x180016a3e  jz      short loc_180016AA8
0x180016a40  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180016a47  call    cs:__imp_GetProcAddress
0x180016a4d  mov     rdx, rax
0x180016a50  test    rax, rax
0x180016a53  jz      short loc_180016AA8
0x180016a55  xor     eax, eax
0x180016a57  lea     rcx, [rbp+var_40]
0x180016a5b  mov     [rbp+var_10], eax
0x180016a5e  xorps   xmm0, xmm0
0x180016a61  movups  [rbp+var_20], xmm0
0x180016a65  lea     rax, __ImageBase
0x180016a6c  movups  [rbp+var_40], xmm0
0x180016a70  mov     qword ptr [rbp+var_40+8], rax
0x180016a74  mov     rax, [rbp+8]
0x180016a78  movups  [rbp+var_30], xmm0
0x180016a7c  mov     qword ptr [rbp+var_30], rax
0x180016a80  or      eax, 0FFFFFFFFh
0x180016a83  mov     dword ptr [rbp+var_20+8], eax
0x180016a86  mov     dword ptr [rbp+var_20+0Ch], eax
0x180016a89  mov     rax, rdx
0x180016a8c  mov     dword ptr [rbp+var_40], 0Bh
0x180016a93  mov     byte ptr [rbp+var_10], 1
0x180016a97  mov     byte ptr [rbp+var_30+8], 0
0x180016a9b  mov     qword ptr [rbp+var_20], 0
0x180016aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aa8  add     rsp, 60h
0x180016aac  pop     rbp
0x180016aad  retn
```
