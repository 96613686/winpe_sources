# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180031190`
- end: `0x180031232`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016ec0`
- `0x18002eff8`

## callees

- `0x180031190`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800311b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800311b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800311cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800311cb`

## string_xrefs

- `0x1800311a5`: `ntdll.dll`

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
0x180031190  push    rbp
0x180031192  mov     rbp, rsp
0x180031195  sub     rsp, 60h
0x180031199  lea     r8, [rbp+phModule]; phModule
0x18003119d  mov     [rbp+phModule], 0
0x1800311a5  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1800311ac  mov     ecx, 2; dwFlags
0x1800311b1  call    cs:__imp_GetModuleHandleExA
0x1800311b7  test    eax, eax
0x1800311b9  jz      short loc_18003122C
0x1800311bb  mov     rcx, [rbp+phModule]; hModule
0x1800311bf  test    rcx, rcx
0x1800311c2  jz      short loc_18003122C
0x1800311c4  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800311cb  call    cs:__imp_GetProcAddress
0x1800311d1  mov     rdx, rax
0x1800311d4  test    rax, rax
0x1800311d7  jz      short loc_18003122C
0x1800311d9  xor     eax, eax
0x1800311db  lea     rcx, [rbp+var_40]
0x1800311df  mov     [rbp+var_10], eax
0x1800311e2  xorps   xmm0, xmm0
0x1800311e5  movups  [rbp+var_20], xmm0
0x1800311e9  lea     rax, __ImageBase
0x1800311f0  movups  [rbp+var_40], xmm0
0x1800311f4  mov     qword ptr [rbp+var_40+8], rax
0x1800311f8  mov     rax, [rbp+8]
0x1800311fc  movups  [rbp+var_30], xmm0
0x180031200  mov     qword ptr [rbp+var_30], rax
0x180031204  or      eax, 0FFFFFFFFh
0x180031207  mov     dword ptr [rbp+var_20+8], eax
0x18003120a  mov     dword ptr [rbp+var_20+0Ch], eax
0x18003120d  mov     rax, rdx
0x180031210  mov     dword ptr [rbp+var_40], 0Bh
0x180031217  mov     byte ptr [rbp+var_10], 1
0x18003121b  mov     byte ptr [rbp+var_30+8], 0
0x18003121f  mov     qword ptr [rbp+var_20], 0
0x180031227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003122c  add     rsp, 60h
0x180031230  pop     rbp
0x180031231  retn
```
