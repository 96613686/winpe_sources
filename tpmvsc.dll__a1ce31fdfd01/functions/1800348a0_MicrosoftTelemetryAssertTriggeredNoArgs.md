# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1800348a0`
- end: `0x180034942`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `145`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007a78`
- `0x180007bcc`
- `0x1800081c0`
- `0x180008324`
- `0x1800085b8`
- `0x180008c3c`
- `0x180008d28`
- `0x180009154`
- `0x1800093c8`
- `0x180009834`
- `0x180009d24`
- `0x180009ea4`
- `0x18000a028`
- `0x18000a110`
- `0x18000a1b8`
- `0x18000a46c`
- `0x18000a81c`
- `0x18000acb4`
- `0x18000b85c`
- `0x18000c404`
- `0x18000c61c`
- `0x18000f53c`
- `0x18000f6a0`
- `0x18000fafc`
- `0x18000fbe8`
- `0x18000fcb0`
- `0x18000fd68`
- `0x18000ff18`
- `0x18001001c`
- `0x180010298`
- `0x1800105b4`
- `0x1800108e8`
- `0x180010a08`
- `0x180010b0c`
- `0x180010cdc`
- `0x180010e90`
- `0x1800110c0`
- `0x18001130c`
- `0x180011468`
- `0x180011598`
- `0x1800116a0`
- `0x18001195c`
- `0x180011c40`
- `0x180011db4`
- `0x180011ee4`
- `0x180012074`
- `0x1800121dc`
- `0x1800123c4`
- `0x180012470`
- `0x180012580`

## callees

- `0x1800348a0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800348c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800348c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800348db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800348db`

## string_xrefs

- `0x1800348b5`: `ntdll.dll`

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
0x1800348a0  push    rbp
0x1800348a2  mov     rbp, rsp
0x1800348a5  sub     rsp, 60h
0x1800348a9  lea     r8, [rbp+phModule]; phModule
0x1800348ad  mov     [rbp+phModule], 0
0x1800348b5  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1800348bc  mov     ecx, 2; dwFlags
0x1800348c1  call    cs:__imp_GetModuleHandleExA
0x1800348c7  test    eax, eax
0x1800348c9  jz      short loc_18003493C
0x1800348cb  mov     rcx, [rbp+phModule]; hModule
0x1800348cf  test    rcx, rcx
0x1800348d2  jz      short loc_18003493C
0x1800348d4  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800348db  call    cs:__imp_GetProcAddress
0x1800348e1  mov     rdx, rax
0x1800348e4  test    rax, rax
0x1800348e7  jz      short loc_18003493C
0x1800348e9  xor     eax, eax
0x1800348eb  lea     rcx, [rbp+var_40]
0x1800348ef  mov     [rbp+var_10], eax
0x1800348f2  xorps   xmm0, xmm0
0x1800348f5  movups  [rbp+var_20], xmm0
0x1800348f9  lea     rax, __ImageBase
0x180034900  movups  [rbp+var_40], xmm0
0x180034904  mov     qword ptr [rbp+var_40+8], rax
0x180034908  mov     rax, [rbp+8]
0x18003490c  movups  [rbp+var_30], xmm0
0x180034910  mov     qword ptr [rbp+var_30], rax
0x180034914  or      eax, 0FFFFFFFFh
0x180034917  mov     dword ptr [rbp+var_20+8], eax
0x18003491a  mov     dword ptr [rbp+var_20+0Ch], eax
0x18003491d  mov     rax, rdx
0x180034920  mov     dword ptr [rbp+var_40], 0Bh
0x180034927  mov     byte ptr [rbp+var_10], 1
0x18003492b  mov     byte ptr [rbp+var_30+8], 0
0x18003492f  mov     qword ptr [rbp+var_20], 0
0x180034937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003493c  add     rsp, 60h
0x180034940  pop     rbp
0x180034941  retn
```
