# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18000f3dc`
- end: `0x18000f47e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `int()`
- caller_count: `133`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011c4`
- `0x180001234`
- `0x1800012a0`
- `0x180001580`
- `0x1800018d0`
- `0x180001980`
- `0x180001ae0`
- `0x180001d24`
- `0x180001fc8`
- `0x18000219c`
- `0x180002420`
- `0x180002530`
- `0x1800027d4`
- `0x180002bc0`
- `0x180002d8c`
- `0x180003150`
- `0x180003370`
- `0x180003440`
- `0x1800034c0`
- `0x180003560`
- `0x1800035c0`
- `0x180003640`
- `0x1800036f0`
- `0x1800037b0`
- `0x180003dac`
- `0x180003e40`
- `0x18000410c`
- `0x180004380`
- `0x180004420`
- `0x180004830`
- `0x180004bd0`
- `0x180004e60`
- `0x1800051e0`
- `0x180005480`
- `0x1800059c0`
- `0x1800061d0`
- `0x18000681c`
- `0x180007440`
- `0x180007650`
- `0x180007790`
- `0x180007f70`
- `0x180008044`
- `0x180008640`
- `0x1800088b0`
- `0x180008c80`
- `0x180008e68`
- `0x1800092a4`
- `0x180009390`
- `0x18000950c`
- `0x180009684`

## callees

- `0x18000f3dc`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f417`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f417`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000f3fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000f3fd`

## string_xrefs

- `0x18000f3f1`: `ntdll.dll`

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
0x18000f3dc  push    rbp
0x18000f3de  mov     rbp, rsp
0x18000f3e1  sub     rsp, 60h
0x18000f3e5  lea     r8, [rbp+phModule]; phModule
0x18000f3e9  mov     [rbp+phModule], 0
0x18000f3f1  lea     rdx, ModuleName; "ntdll.dll"
0x18000f3f8  mov     ecx, 2; dwFlags
0x18000f3fd  call    cs:__imp_GetModuleHandleExA
0x18000f403  test    eax, eax
0x18000f405  jz      short loc_18000F478
0x18000f407  mov     rcx, [rbp+phModule]; hModule
0x18000f40b  test    rcx, rcx
0x18000f40e  jz      short loc_18000F478
0x18000f410  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18000f417  call    cs:__imp_GetProcAddress
0x18000f41d  mov     rdx, rax
0x18000f420  test    rax, rax
0x18000f423  jz      short loc_18000F478
0x18000f425  xor     eax, eax
0x18000f427  lea     rcx, [rbp+var_40]
0x18000f42b  mov     [rbp+var_10], eax
0x18000f42e  xorps   xmm0, xmm0
0x18000f431  movups  [rbp+var_20], xmm0
0x18000f435  lea     rax, __ImageBase
0x18000f43c  movups  [rbp+var_40], xmm0
0x18000f440  mov     qword ptr [rbp+var_40+8], rax
0x18000f444  mov     rax, [rbp+8]
0x18000f448  movups  [rbp+var_30], xmm0
0x18000f44c  mov     qword ptr [rbp+var_30], rax
0x18000f450  or      eax, 0FFFFFFFFh
0x18000f453  mov     dword ptr [rbp+var_20+8], eax
0x18000f456  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000f459  mov     rax, rdx
0x18000f45c  mov     dword ptr [rbp+var_40], 0Bh
0x18000f463  mov     byte ptr [rbp+var_10], 1
0x18000f467  mov     byte ptr [rbp+var_30+8], 0
0x18000f46b  mov     qword ptr [rbp+var_20], 0
0x18000f473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f478  add     rsp, 60h
0x18000f47c  pop     rbp
0x18000f47d  retn
```
