# SIPolicyFree

- ea: `0x1800187d4`
- end: `0x1800187f7`
- name: `SIPolicyFree`
- size: `35`
- prototype: ``
- caller_count: `31`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800115e0`
- `0x180011750`
- `0x1800118c8`
- `0x180015624`
- `0x180018504`
- `0x180018a04`
- `0x180019300`
- `0x180019720`
- `0x180019a4c`
- `0x180019b64`
- `0x18001be2c`
- `0x18001c9ac`
- `0x18001ca7c`
- `0x18001cd1c`
- `0x18001ddb8`
- `0x18001dfa8`
- `0x18001e0b8`
- `0x18001e3a8`
- `0x18001e5cc`
- `0x18001f33c`
- `0x18001f800`
- `0x18001ff54`
- `0x18002019c`
- `0x180020bd4`
- `0x180020c38`
- `0x180021304`
- `0x18002151c`
- `0x180047a80`
- `0x180048c50`
- `0x18004ab74`
- `0x18004e5b8`

## callees

- `0x1800187d4`

## import_xrefs

- `securekernel!SkFreePool` at `0x1800187e5`
- `securekernel!SkFreePool` at `0x1800187e5`

## pseudocode

```c
__int64 __fastcall SIPolicyFree(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return SkFreePool(1, a1);
  return result;
}

```

## disassembly

```asm
0x1800187d4  sub     rsp, 28h
0x1800187d8  test    rcx, rcx
0x1800187db  jz      short loc_1800187F1
0x1800187dd  mov     rdx, rcx
0x1800187e0  mov     ecx, 1
0x1800187e5  call    cs:__imp_SkFreePool
0x1800187ec  nop     dword ptr [rax+rax+00h]
0x1800187f1  add     rsp, 28h
0x1800187f5  retn
```
