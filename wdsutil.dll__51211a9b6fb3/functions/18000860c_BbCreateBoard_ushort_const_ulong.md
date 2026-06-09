# BbCreateBoard(ushort const *,ulong)

- ea: `0x18000860c`
- end: `0x180008646`
- name: `?BbCreateBoard@@YAPEAU_BLACKBOARD@@PEBGK@Z`
- size: `58`
- prototype: `struct _BLACKBOARD *__fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180002730`
- `0x180002898`
- `0x1800031a4`
- `0x180006570`

## callees

- `0x18000860c`

## import_xrefs

- `WDSCORE!WdsCreateBlackboard` at `0x18000862c`
- `WDSCORE!WdsCreateBlackboard` at `0x18000862c`

## pseudocode

```c
struct _BLACKBOARD *__fastcall BbCreateBoard(const unsigned __int16 *a1)
{
  return (struct _BLACKBOARD *)WdsCreateBlackboard(8, L"SetupInfo", 0);
}

```

## disassembly

```asm
0x18000860c  mov     [rsp+arg_0], rcx
0x180008611  sub     rsp, 38h
0x180008615  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000861e  xor     r8d, r8d
0x180008621  lea     rdx, aSetupinfo; "SetupInfo"
0x180008628  lea     ecx, [r8+8]
0x18000862c  call    cs:__imp_WdsCreateBlackboard
0x180008633  nop     dword ptr [rax+rax+00h]
0x180008638  nop
0x180008639  jmp     short loc_180008640
0x18000863b  mov     rax, [rsp+38h+arg_0]
0x180008640  add     rsp, 38h
0x180008644  retn
```
