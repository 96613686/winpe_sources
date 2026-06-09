# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180012ca0`
- end: `0x180012d4f`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800081b0`
- `0x180011ed0`
- `0x180012240`
- `0x1800122a0`
- `0x1800122f0`
- `0x180012350`
- `0x180012460`
- `0x1800124b0`
- `0x180012650`
- `0x180012794`
- `0x180012a5c`

## callees

- `0x180012ca0`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetModuleHandleExA` at `0x180012cc1`
- `KERNEL32!GetModuleHandleExA` at `0x180012cc1`
- `KERNEL32!GetProcAddress` at `0x180012ce1`
- `KERNEL32!GetProcAddress` at `0x180012ce1`

## string_xrefs

- `0x180012cb5`: `ntdll.dll`

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
0x180012ca0  push    rbp
0x180012ca2  mov     rbp, rsp
0x180012ca5  sub     rsp, 60h
0x180012ca9  lea     r8, [rbp+phModule]; phModule
0x180012cad  mov     [rbp+phModule], 0
0x180012cb5  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180012cbc  mov     ecx, 2; dwFlags
0x180012cc1  call    cs:__imp_GetModuleHandleExA
0x180012cc8  nop     dword ptr [rax+rax+00h]
0x180012ccd  test    eax, eax
0x180012ccf  jz      short loc_180012D48
0x180012cd1  mov     rcx, [rbp+phModule]; hModule
0x180012cd5  test    rcx, rcx
0x180012cd8  jz      short loc_180012D48
0x180012cda  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180012ce1  call    cs:__imp_GetProcAddress
0x180012ce8  nop     dword ptr [rax+rax+00h]
0x180012ced  mov     rdx, rax
0x180012cf0  test    rax, rax
0x180012cf3  jz      short loc_180012D48
0x180012cf5  xor     eax, eax
0x180012cf7  lea     rcx, [rbp+var_40]
0x180012cfb  mov     [rbp+var_10], eax
0x180012cfe  xorps   xmm0, xmm0
0x180012d01  movups  [rbp+var_20], xmm0
0x180012d05  lea     rax, cs:180000000h
0x180012d0c  movups  [rbp+var_40], xmm0
0x180012d10  mov     qword ptr [rbp+var_40+8], rax
0x180012d14  mov     rax, [rbp+8]
0x180012d18  movups  [rbp+var_30], xmm0
0x180012d1c  mov     qword ptr [rbp+var_30], rax
0x180012d20  or      eax, 0FFFFFFFFh
0x180012d23  mov     dword ptr [rbp+var_20+8], eax
0x180012d26  mov     dword ptr [rbp+var_20+0Ch], eax
0x180012d29  mov     rax, rdx
0x180012d2c  mov     dword ptr [rbp+var_40], 0Bh
0x180012d33  mov     byte ptr [rbp+var_10], 1
0x180012d37  mov     byte ptr [rbp+var_30+8], 0
0x180012d3b  mov     qword ptr [rbp+var_20], 0
0x180012d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d48  add     rsp, 60h
0x180012d4c  pop     rbp
0x180012d4d  retn
```
