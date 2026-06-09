# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180038d98`
- end: `0x180038e3a`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013e6c`
- `0x1800154dc`

## callees

- `0x180038d98`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038dd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038dd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180038db9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180038db9`

## string_xrefs

- `0x180038dad`: `ntdll.dll`

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
0x180038d98  push    rbp
0x180038d9a  mov     rbp, rsp
0x180038d9d  sub     rsp, 60h
0x180038da1  lea     r8, [rbp+phModule]; phModule
0x180038da5  mov     [rbp+phModule], 0
0x180038dad  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180038db4  mov     ecx, 2; dwFlags
0x180038db9  call    cs:__imp_GetModuleHandleExA
0x180038dbf  test    eax, eax
0x180038dc1  jz      short loc_180038E34
0x180038dc3  mov     rcx, [rbp+phModule]; hModule
0x180038dc7  test    rcx, rcx
0x180038dca  jz      short loc_180038E34
0x180038dcc  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180038dd3  call    cs:__imp_GetProcAddress
0x180038dd9  mov     rdx, rax
0x180038ddc  test    rax, rax
0x180038ddf  jz      short loc_180038E34
0x180038de1  xor     eax, eax
0x180038de3  lea     rcx, [rbp+var_40]
0x180038de7  mov     [rbp+var_10], eax
0x180038dea  xorps   xmm0, xmm0
0x180038ded  movups  [rbp+var_20], xmm0
0x180038df1  lea     rax, __ImageBase
0x180038df8  movups  [rbp+var_40], xmm0
0x180038dfc  mov     qword ptr [rbp+var_40+8], rax
0x180038e00  mov     rax, [rbp+8]
0x180038e04  movups  [rbp+var_30], xmm0
0x180038e08  mov     qword ptr [rbp+var_30], rax
0x180038e0c  or      eax, 0FFFFFFFFh
0x180038e0f  mov     dword ptr [rbp+var_20+8], eax
0x180038e12  mov     dword ptr [rbp+var_20+0Ch], eax
0x180038e15  mov     rax, rdx
0x180038e18  mov     dword ptr [rbp+var_40], 0Bh
0x180038e1f  mov     byte ptr [rbp+var_10], 1
0x180038e23  mov     byte ptr [rbp+var_30+8], 0
0x180038e27  mov     qword ptr [rbp+var_20], 0
0x180038e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e34  add     rsp, 60h
0x180038e38  pop     rbp
0x180038e39  retn
```
