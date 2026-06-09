# WdsModifyRestorePrivilege

- ea: `0x18001cc80`
- end: `0x18001ccbe`
- name: `WdsModifyRestorePrivilege`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180018d00`
- `0x180019eb0`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18001cc99`
- `ntdll!RtlAdjustPrivilege` at `0x18001cc99`

## pseudocode

```c
int __fastcall WdsModifyRestorePrivilege(BOOLEAN a1)
{
  NTSTATUS v1; // ecx
  int result; // eax
  unsigned __int8 OldValue; // [rsp+38h] [rbp+10h] BYREF

  OldValue = 0;
  v1 = RtlAdjustPrivilege(0x12u, a1, 0, &OldValue);
  result = v1 | 0x10000000;
  if ( (v1 & 0xC0000000) != 0xC0000000 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18001cc80  push    rbx
0x18001cc82  sub     rsp, 20h
0x18001cc86  xor     ebx, ebx
0x18001cc88  lea     r9, [rsp+28h+OldValue]; OldValue
0x18001cc8d  mov     dl, cl; NewValue
0x18001cc8f  mov     [rsp+28h+OldValue], bl
0x18001cc93  xor     r8d, r8d; ForThread
0x18001cc96  lea     ecx, [rbx+12h]; Privilege
0x18001cc99  call    cs:__imp_RtlAdjustPrivilege
0x18001cca0  nop     dword ptr [rax+rax+00h]
0x18001cca5  mov     ecx, eax
0x18001cca7  mov     edx, 0C0000000h
0x18001ccac  bts     eax, 1Ch
0x18001ccb0  and     ecx, edx
0x18001ccb2  cmp     ecx, edx
0x18001ccb4  cmovnz  eax, ebx
0x18001ccb7  add     rsp, 20h
0x18001ccbb  pop     rbx
0x18001ccbc  retn
```
