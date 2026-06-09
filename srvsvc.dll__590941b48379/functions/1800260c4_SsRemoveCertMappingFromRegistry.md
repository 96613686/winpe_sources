# SsRemoveCertMappingFromRegistry

- ea: `0x1800260c4`
- end: `0x180026149`
- name: `SsRemoveCertMappingFromRegistry`
- size: `133`
- prototype: `__int64 __fastcall(PCWSTR ValueName)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180031c8c`
- `0x180032f00`
- `0x180033cb4`

## callees

- `0x1800260c4`
- `0x1800268d8`

## import_xrefs

- `ntdll!RtlDeleteRegistryValue` at `0x1800260e4`
- `ntdll!RtlDeleteRegistryValue` at `0x1800260e4`
- `ntdll!RtlNtStatusToDosError` at `0x18002612f`
- `ntdll!RtlNtStatusToDosError` at `0x18002612f`

## pseudocode

```c
__int64 __fastcall SsRemoveCertMappingFromRegistry(PCWSTR ValueName)
{
  unsigned int v2; // ebx
  int v3; // edi

  v2 = 0;
  v3 = RtlDeleteRegistryValue(0, &word_18005E1CC, ValueName);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        113,
        (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
        v3,
        (__int64)ValueName);
    }
    return RtlNtStatusToDosError(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x1800260c4  mov     [rsp+arg_0], rbx
0x1800260c9  mov     [rsp+arg_8], rsi
0x1800260ce  push    rdi
0x1800260cf  sub     rsp, 30h
0x1800260d3  mov     rsi, rcx
0x1800260d6  lea     rdx, word_18005E1CC; Path
0x1800260dd  mov     r8, rcx; ValueName
0x1800260e0  xor     ebx, ebx
0x1800260e2  xor     ecx, ecx; RelativeTo
0x1800260e4  call    cs:__imp_RtlDeleteRegistryValue
0x1800260ea  mov     edi, eax
0x1800260ec  test    eax, eax
0x1800260ee  jns     short loc_180026137
0x1800260f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800260f7  lea     rax, WPP_GLOBAL_Control
0x1800260fe  cmp     rcx, rax
0x180026101  jz      short loc_18002612D
0x180026103  test    dword ptr [rcx+1Ch], 100h
0x18002610a  jz      short loc_18002612D
0x18002610c  cmp     byte ptr [rcx+19h], 1
0x180026110  jb      short loc_18002612D
0x180026112  mov     rcx, [rcx+10h]
0x180026116  lea     edx, [rbx+71h]
0x180026119  mov     r9d, edi
0x18002611c  mov     [rsp+38h+var_18], rsi
0x180026121  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180026128  call    WPP_SF_dS
0x18002612d  mov     ecx, edi; Status
0x18002612f  call    cs:__imp_RtlNtStatusToDosError
0x180026135  mov     ebx, eax
0x180026137  mov     rsi, [rsp+38h+arg_8]
0x18002613c  mov     eax, ebx
0x18002613e  mov     rbx, [rsp+38h+arg_0]
0x180026143  add     rsp, 30h
0x180026147  pop     rdi
0x180026148  retn
```
