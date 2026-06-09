# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x14004dc5c`
- end: `0x14004dd0b`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400399cc`
- `0x140039a6c`

## callees

- `0x14004dc5c`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004dc9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004dc9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x14004dc7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x14004dc7d`

## string_xrefs

- `0x14004dc71`: `ntdll.dll`

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
0x14004dc5c  push    rbp
0x14004dc5e  mov     rbp, rsp
0x14004dc61  sub     rsp, 60h
0x14004dc65  lea     r8, [rbp+phModule]; phModule
0x14004dc69  mov     [rbp+phModule], 0
0x14004dc71  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x14004dc78  mov     ecx, 2; dwFlags
0x14004dc7d  call    cs:__imp_GetModuleHandleExA
0x14004dc84  nop     dword ptr [rax+rax+00h]
0x14004dc89  test    eax, eax
0x14004dc8b  jz      short loc_14004DD04
0x14004dc8d  mov     rcx, [rbp+phModule]; hModule
0x14004dc91  test    rcx, rcx
0x14004dc94  jz      short loc_14004DD04
0x14004dc96  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x14004dc9d  call    cs:__imp_GetProcAddress
0x14004dca4  nop     dword ptr [rax+rax+00h]
0x14004dca9  mov     rdx, rax
0x14004dcac  test    rax, rax
0x14004dcaf  jz      short loc_14004DD04
0x14004dcb1  xor     eax, eax
0x14004dcb3  lea     rcx, [rbp+var_40]
0x14004dcb7  mov     [rbp+var_10], eax
0x14004dcba  xorps   xmm0, xmm0
0x14004dcbd  movups  [rbp+var_20], xmm0
0x14004dcc1  lea     rax, __ImageBase
0x14004dcc8  movups  [rbp+var_40], xmm0
0x14004dccc  mov     qword ptr [rbp+var_40+8], rax
0x14004dcd0  mov     rax, [rbp+8]
0x14004dcd4  movups  [rbp+var_30], xmm0
0x14004dcd8  mov     qword ptr [rbp+var_30], rax
0x14004dcdc  or      eax, 0FFFFFFFFh
0x14004dcdf  mov     dword ptr [rbp+var_20+8], eax
0x14004dce2  mov     dword ptr [rbp+var_20+0Ch], eax
0x14004dce5  mov     rax, rdx
0x14004dce8  mov     dword ptr [rbp+var_40], 0Bh
0x14004dcef  mov     byte ptr [rbp+var_10], 1
0x14004dcf3  mov     byte ptr [rbp+var_30+8], 0
0x14004dcf7  mov     qword ptr [rbp+var_20], 0
0x14004dcff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004dd04  add     rsp, 60h
0x14004dd08  pop     rbp
0x14004dd09  retn
```
