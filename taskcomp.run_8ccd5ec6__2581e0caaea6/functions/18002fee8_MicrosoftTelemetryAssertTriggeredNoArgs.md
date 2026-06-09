# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18002fee8`
- end: `0x18002ff97`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019f10`

## callees

- `0x18002fee8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ff29`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ff29`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002ff09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002ff09`

## string_xrefs

- `0x18002fefd`: `ntdll.dll`

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
0x18002fee8  push    rbp
0x18002feea  mov     rbp, rsp
0x18002feed  sub     rsp, 60h
0x18002fef1  lea     r8, [rbp+phModule]; phModule
0x18002fef5  mov     [rbp+phModule], 0
0x18002fefd  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18002ff04  mov     ecx, 2; dwFlags
0x18002ff09  call    cs:__imp_GetModuleHandleExA
0x18002ff10  nop     dword ptr [rax+rax+00h]
0x18002ff15  test    eax, eax
0x18002ff17  jz      short loc_18002FF90
0x18002ff19  mov     rcx, [rbp+phModule]; hModule
0x18002ff1d  test    rcx, rcx
0x18002ff20  jz      short loc_18002FF90
0x18002ff22  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18002ff29  call    cs:__imp_GetProcAddress
0x18002ff30  nop     dword ptr [rax+rax+00h]
0x18002ff35  mov     rdx, rax
0x18002ff38  test    rax, rax
0x18002ff3b  jz      short loc_18002FF90
0x18002ff3d  xor     eax, eax
0x18002ff3f  lea     rcx, [rbp+var_40]
0x18002ff43  mov     [rbp+var_10], eax
0x18002ff46  xorps   xmm0, xmm0
0x18002ff49  movups  [rbp+var_20], xmm0
0x18002ff4d  lea     rax, __ImageBase
0x18002ff54  movups  [rbp+var_40], xmm0
0x18002ff58  mov     qword ptr [rbp+var_40+8], rax
0x18002ff5c  mov     rax, [rbp+8]
0x18002ff60  movups  [rbp+var_30], xmm0
0x18002ff64  mov     qword ptr [rbp+var_30], rax
0x18002ff68  or      eax, 0FFFFFFFFh
0x18002ff6b  mov     dword ptr [rbp+var_20+8], eax
0x18002ff6e  mov     dword ptr [rbp+var_20+0Ch], eax
0x18002ff71  mov     rax, rdx
0x18002ff74  mov     dword ptr [rbp+var_40], 0Bh
0x18002ff7b  mov     byte ptr [rbp+var_10], 1
0x18002ff7f  mov     byte ptr [rbp+var_30+8], 0
0x18002ff83  mov     qword ptr [rbp+var_20], 0
0x18002ff8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff90  add     rsp, 60h
0x18002ff94  pop     rbp
0x18002ff95  retn
```
