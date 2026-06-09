# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180012e40`
- end: `0x180012eef`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012618`

## callees

- `0x180012e40`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180012e61`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180012e61`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012e81`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012e81`

## string_xrefs

- `0x180012e55`: `ntdll.dll`

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
0x180012e40  push    rbp
0x180012e42  mov     rbp, rsp
0x180012e45  sub     rsp, 60h
0x180012e49  lea     r8, [rbp+phModule]; phModule
0x180012e4d  mov     [rbp+phModule], 0
0x180012e55  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180012e5c  mov     ecx, 2; dwFlags
0x180012e61  call    cs:__imp_GetModuleHandleExA
0x180012e68  nop     dword ptr [rax+rax+00h]
0x180012e6d  test    eax, eax
0x180012e6f  jz      short loc_180012EE8
0x180012e71  mov     rcx, [rbp+phModule]; hModule
0x180012e75  test    rcx, rcx
0x180012e78  jz      short loc_180012EE8
0x180012e7a  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180012e81  call    cs:__imp_GetProcAddress
0x180012e88  nop     dword ptr [rax+rax+00h]
0x180012e8d  mov     rdx, rax
0x180012e90  test    rax, rax
0x180012e93  jz      short loc_180012EE8
0x180012e95  xor     eax, eax
0x180012e97  lea     rcx, [rbp+var_40]
0x180012e9b  mov     [rbp+var_10], eax
0x180012e9e  xorps   xmm0, xmm0
0x180012ea1  movups  [rbp+var_20], xmm0
0x180012ea5  lea     rax, __ImageBase
0x180012eac  movups  [rbp+var_40], xmm0
0x180012eb0  mov     qword ptr [rbp+var_40+8], rax
0x180012eb4  mov     rax, [rbp+8]
0x180012eb8  movups  [rbp+var_30], xmm0
0x180012ebc  mov     qword ptr [rbp+var_30], rax
0x180012ec0  or      eax, 0FFFFFFFFh
0x180012ec3  mov     dword ptr [rbp+var_20+8], eax
0x180012ec6  mov     dword ptr [rbp+var_20+0Ch], eax
0x180012ec9  mov     rax, rdx
0x180012ecc  mov     dword ptr [rbp+var_40], 0Bh
0x180012ed3  mov     byte ptr [rbp+var_10], 1
0x180012ed7  mov     byte ptr [rbp+var_30+8], 0
0x180012edb  mov     qword ptr [rbp+var_20], 0
0x180012ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ee8  add     rsp, 60h
0x180012eec  pop     rbp
0x180012eed  retn
```
