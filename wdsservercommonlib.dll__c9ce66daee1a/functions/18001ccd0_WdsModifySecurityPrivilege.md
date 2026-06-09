# WdsModifySecurityPrivilege

- ea: `0x18001ccd0`
- end: `0x18001cd0e`
- name: `WdsModifySecurityPrivilege`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180018d00`
- `0x180019eb0`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18001cce9`
- `ntdll!RtlAdjustPrivilege` at `0x18001cce9`

## pseudocode

```c
int __fastcall WdsModifySecurityPrivilege(BOOLEAN a1)
{
  NTSTATUS v1; // ecx
  int result; // eax
  unsigned __int8 OldValue; // [rsp+38h] [rbp+10h] BYREF

  OldValue = 0;
  v1 = RtlAdjustPrivilege(8u, a1, 0, &OldValue);
  result = v1 | 0x10000000;
  if ( (v1 & 0xC0000000) != 0xC0000000 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18001ccd0  push    rbx
0x18001ccd2  sub     rsp, 20h
0x18001ccd6  xor     ebx, ebx
0x18001ccd8  lea     r9, [rsp+28h+OldValue]; OldValue
0x18001ccdd  mov     dl, cl; NewValue
0x18001ccdf  mov     [rsp+28h+OldValue], bl
0x18001cce3  xor     r8d, r8d; ForThread
0x18001cce6  lea     ecx, [rbx+8]; Privilege
0x18001cce9  call    cs:__imp_RtlAdjustPrivilege
0x18001ccf0  nop     dword ptr [rax+rax+00h]
0x18001ccf5  mov     ecx, eax
0x18001ccf7  mov     edx, 0C0000000h
0x18001ccfc  bts     eax, 1Ch
0x18001cd00  and     ecx, edx
0x18001cd02  cmp     ecx, edx
0x18001cd04  cmovnz  eax, ebx
0x18001cd07  add     rsp, 20h
0x18001cd0b  pop     rbx
0x18001cd0c  retn
```
