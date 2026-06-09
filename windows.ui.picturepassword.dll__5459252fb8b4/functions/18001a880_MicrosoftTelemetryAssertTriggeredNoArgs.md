# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18001a880`
- end: `0x18001a922`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018f10`

## callees

- `0x18001a880`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a8bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a8bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001a8a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001a8a1`

## string_xrefs

- `0x18001a895`: `ntdll.dll`

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
0x18001a880  push    rbp
0x18001a882  mov     rbp, rsp
0x18001a885  sub     rsp, 60h
0x18001a889  lea     r8, [rbp+phModule]; phModule
0x18001a88d  mov     [rbp+phModule], 0
0x18001a895  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18001a89c  mov     ecx, 2; dwFlags
0x18001a8a1  call    cs:__imp_GetModuleHandleExA
0x18001a8a7  test    eax, eax
0x18001a8a9  jz      short loc_18001A91C
0x18001a8ab  mov     rcx, [rbp+phModule]; hModule
0x18001a8af  test    rcx, rcx
0x18001a8b2  jz      short loc_18001A91C
0x18001a8b4  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18001a8bb  call    cs:__imp_GetProcAddress
0x18001a8c1  mov     rdx, rax
0x18001a8c4  test    rax, rax
0x18001a8c7  jz      short loc_18001A91C
0x18001a8c9  xor     eax, eax
0x18001a8cb  lea     rcx, [rbp+var_40]
0x18001a8cf  mov     [rbp+var_10], eax
0x18001a8d2  xorps   xmm0, xmm0
0x18001a8d5  movups  [rbp+var_20], xmm0
0x18001a8d9  lea     rax, __ImageBase
0x18001a8e0  movups  [rbp+var_40], xmm0
0x18001a8e4  mov     qword ptr [rbp+var_40+8], rax
0x18001a8e8  mov     rax, [rbp+8]
0x18001a8ec  movups  [rbp+var_30], xmm0
0x18001a8f0  mov     qword ptr [rbp+var_30], rax
0x18001a8f4  or      eax, 0FFFFFFFFh
0x18001a8f7  mov     dword ptr [rbp+var_20+8], eax
0x18001a8fa  mov     dword ptr [rbp+var_20+0Ch], eax
0x18001a8fd  mov     rax, rdx
0x18001a900  mov     dword ptr [rbp+var_40], 0Bh
0x18001a907  mov     byte ptr [rbp+var_10], 1
0x18001a90b  mov     byte ptr [rbp+var_30+8], 0
0x18001a90f  mov     qword ptr [rbp+var_20], 0
0x18001a917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a91c  add     rsp, 60h
0x18001a920  pop     rbp
0x18001a921  retn
```
