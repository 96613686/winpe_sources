# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18001c57c`
- end: `0x18001c62b`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005dcc`
- `0x180006408`

## callees

- `0x18001c57c`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c5bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c5bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001c59d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001c59d`

## string_xrefs

- `0x18001c591`: `ntdll.dll`

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
0x18001c57c  push    rbp
0x18001c57e  mov     rbp, rsp
0x18001c581  sub     rsp, 60h
0x18001c585  lea     r8, [rbp+phModule]; phModule
0x18001c589  mov     [rbp+phModule], 0
0x18001c591  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18001c598  mov     ecx, 2; dwFlags
0x18001c59d  call    cs:__imp_GetModuleHandleExA
0x18001c5a4  nop     dword ptr [rax+rax+00h]
0x18001c5a9  test    eax, eax
0x18001c5ab  jz      short loc_18001C624
0x18001c5ad  mov     rcx, [rbp+phModule]; hModule
0x18001c5b1  test    rcx, rcx
0x18001c5b4  jz      short loc_18001C624
0x18001c5b6  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18001c5bd  call    cs:__imp_GetProcAddress
0x18001c5c4  nop     dword ptr [rax+rax+00h]
0x18001c5c9  mov     rdx, rax
0x18001c5cc  test    rax, rax
0x18001c5cf  jz      short loc_18001C624
0x18001c5d1  xor     eax, eax
0x18001c5d3  lea     rcx, [rbp+var_40]
0x18001c5d7  mov     [rbp+var_10], eax
0x18001c5da  xorps   xmm0, xmm0
0x18001c5dd  movups  [rbp+var_20], xmm0
0x18001c5e1  lea     rax, __ImageBase
0x18001c5e8  movups  [rbp+var_40], xmm0
0x18001c5ec  mov     qword ptr [rbp+var_40+8], rax
0x18001c5f0  mov     rax, [rbp+8]
0x18001c5f4  movups  [rbp+var_30], xmm0
0x18001c5f8  mov     qword ptr [rbp+var_30], rax
0x18001c5fc  or      eax, 0FFFFFFFFh
0x18001c5ff  mov     dword ptr [rbp+var_20+8], eax
0x18001c602  mov     dword ptr [rbp+var_20+0Ch], eax
0x18001c605  mov     rax, rdx
0x18001c608  mov     dword ptr [rbp+var_40], 0Bh
0x18001c60f  mov     byte ptr [rbp+var_10], 1
0x18001c613  mov     byte ptr [rbp+var_30+8], 0
0x18001c617  mov     qword ptr [rbp+var_20], 0
0x18001c61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c624  add     rsp, 60h
0x18001c628  pop     rbp
0x18001c629  retn
```
