# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x14004c318`
- end: `0x14004c3ba`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140038444`
- `0x1400384d8`

## callees

- `0x14004c318`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004c353`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004c353`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x14004c339`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x14004c339`

## string_xrefs

- `0x14004c32d`: `ntdll.dll`

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
0x14004c318  push    rbp
0x14004c31a  mov     rbp, rsp
0x14004c31d  sub     rsp, 60h
0x14004c321  lea     r8, [rbp+phModule]; phModule
0x14004c325  mov     [rbp+phModule], 0
0x14004c32d  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x14004c334  mov     ecx, 2; dwFlags
0x14004c339  call    cs:__imp_GetModuleHandleExA
0x14004c33f  test    eax, eax
0x14004c341  jz      short loc_14004C3B4
0x14004c343  mov     rcx, [rbp+phModule]; hModule
0x14004c347  test    rcx, rcx
0x14004c34a  jz      short loc_14004C3B4
0x14004c34c  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x14004c353  call    cs:__imp_GetProcAddress
0x14004c359  mov     rdx, rax
0x14004c35c  test    rax, rax
0x14004c35f  jz      short loc_14004C3B4
0x14004c361  xor     eax, eax
0x14004c363  lea     rcx, [rbp+var_40]
0x14004c367  mov     [rbp+var_10], eax
0x14004c36a  xorps   xmm0, xmm0
0x14004c36d  movups  [rbp+var_20], xmm0
0x14004c371  lea     rax, __ImageBase
0x14004c378  movups  [rbp+var_40], xmm0
0x14004c37c  mov     qword ptr [rbp+var_40+8], rax
0x14004c380  mov     rax, [rbp+8]
0x14004c384  movups  [rbp+var_30], xmm0
0x14004c388  mov     qword ptr [rbp+var_30], rax
0x14004c38c  or      eax, 0FFFFFFFFh
0x14004c38f  mov     dword ptr [rbp+var_20+8], eax
0x14004c392  mov     dword ptr [rbp+var_20+0Ch], eax
0x14004c395  mov     rax, rdx
0x14004c398  mov     dword ptr [rbp+var_40], 0Bh
0x14004c39f  mov     byte ptr [rbp+var_10], 1
0x14004c3a3  mov     byte ptr [rbp+var_30+8], 0
0x14004c3a7  mov     qword ptr [rbp+var_20], 0
0x14004c3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c3b4  add     rsp, 60h
0x14004c3b8  pop     rbp
0x14004c3b9  retn
```
