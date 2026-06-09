# SmpGetProcessId

- ea: `0x140001450`
- end: `0x140001495`
- name: `SmpGetProcessId`
- size: `69`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140001260`
- `0x140001630`
- `0x140001f60`
- `0x1400053e0`
- `0x140018154`

## callees

- `0x140001450`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x14000147a`
- `ntdll!NtQueryInformationProcess` at `0x14000147a`

## pseudocode

```c
__int64 __fastcall SmpGetProcessId(void *a1)
{
  _OWORD ProcessInformation[3]; // [rsp+30h] [rbp-38h] BYREF

  memset(ProcessInformation, 0, 44);
  if ( NtQueryInformationProcess(a1, ProcessBasicInformation, ProcessInformation, 0x30u, 0) >= 0 )
    return *(_QWORD *)&ProcessInformation[2];
  else
    return 0;
}

```

## disassembly

```asm
0x140001450  sub     rsp, 68h
0x140001454  xorps   xmm0, xmm0
0x140001457  lea     r8, [rsp+68h+ProcessInformation]; ProcessInformation
0x14000145c  xor     eax, eax
0x14000145e  mov     r9d, 30h ; '0'; ProcessInformationLength
0x140001464  movups  [rsp+68h+var_28], xmm0
0x140001469  xor     edx, edx; ProcessInformationClass
0x14000146b  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x140001470  movups  [rsp+68h+var_28+0Ch], xmm0
0x140001475  movups  [rsp+68h+ProcessInformation], xmm0
0x14000147a  call    cs:__imp_NtQueryInformationProcess
0x140001480  test    eax, eax
0x140001482  jns     short loc_14000148B
0x140001484  xor     eax, eax
0x140001486  add     rsp, 68h
0x14000148a  retn
0x14000148b  mov     rax, [rsp+68h+var_18]
0x140001490  add     rsp, 68h
0x140001494  retn
```
