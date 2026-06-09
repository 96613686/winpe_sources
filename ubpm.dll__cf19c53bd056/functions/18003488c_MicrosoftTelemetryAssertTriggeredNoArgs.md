# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18003488c`
- end: `0x18003492e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `17`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001764`
- `0x180007c50`
- `0x18000c3d4`
- `0x180013510`
- `0x1800136f4`
- `0x180013b60`
- `0x180014840`
- `0x180016688`
- `0x180027230`
- `0x18002aa0c`
- `0x18002ad7c`
- `0x18002e0c8`
- `0x18002ea04`
- `0x18002eb98`
- `0x1800307f0`
- `0x1800308ec`
- `0x1800367e0`

## callees

- `0x18003488c`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800348ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800348ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800348c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800348c7`

## string_xrefs

- `0x1800348a1`: `ntdll.dll`

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
0x18003488c  push    rbp
0x18003488e  mov     rbp, rsp
0x180034891  sub     rsp, 60h
0x180034895  lea     r8, [rbp+phModule]; phModule
0x180034899  mov     [rbp+phModule], 0
0x1800348a1  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1800348a8  mov     ecx, 2; dwFlags
0x1800348ad  call    cs:__imp_GetModuleHandleExA
0x1800348b3  test    eax, eax
0x1800348b5  jz      short loc_180034928
0x1800348b7  mov     rcx, [rbp+phModule]; hModule
0x1800348bb  test    rcx, rcx
0x1800348be  jz      short loc_180034928
0x1800348c0  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800348c7  call    cs:__imp_GetProcAddress
0x1800348cd  mov     rdx, rax
0x1800348d0  test    rax, rax
0x1800348d3  jz      short loc_180034928
0x1800348d5  xor     eax, eax
0x1800348d7  lea     rcx, [rbp+var_40]
0x1800348db  mov     [rbp+var_10], eax
0x1800348de  xorps   xmm0, xmm0
0x1800348e1  movups  [rbp+var_20], xmm0
0x1800348e5  lea     rax, __ImageBase
0x1800348ec  movups  [rbp+var_40], xmm0
0x1800348f0  mov     qword ptr [rbp+var_40+8], rax
0x1800348f4  mov     rax, [rbp+8]
0x1800348f8  movups  [rbp+var_30], xmm0
0x1800348fc  mov     qword ptr [rbp+var_30], rax
0x180034900  or      eax, 0FFFFFFFFh
0x180034903  mov     dword ptr [rbp+var_20+8], eax
0x180034906  mov     dword ptr [rbp+var_20+0Ch], eax
0x180034909  mov     rax, rdx
0x18003490c  mov     dword ptr [rbp+var_40], 0Bh
0x180034913  mov     byte ptr [rbp+var_10], 1
0x180034917  mov     byte ptr [rbp+var_30+8], 0
0x18003491b  mov     qword ptr [rbp+var_20], 0
0x180034923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034928  add     rsp, 60h
0x18003492c  pop     rbp
0x18003492d  retn
```
