# WdsModifySecurityPrivilege

- ea: `0x18001dc30`
- end: `0x18001dc6e`
- name: `WdsModifySecurityPrivilege`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019aec`
- `0x18001acf0`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18001dc49`
- `ntdll!RtlAdjustPrivilege` at `0x18001dc49`

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
0x18001dc30  push    rbx
0x18001dc32  sub     rsp, 20h
0x18001dc36  xor     ebx, ebx
0x18001dc38  lea     r9, [rsp+28h+OldValue]; OldValue
0x18001dc3d  mov     dl, cl; NewValue
0x18001dc3f  mov     [rsp+28h+OldValue], bl
0x18001dc43  xor     r8d, r8d; ForThread
0x18001dc46  lea     ecx, [rbx+8]; Privilege
0x18001dc49  call    cs:__imp_RtlAdjustPrivilege
0x18001dc50  nop     dword ptr [rax+rax+00h]
0x18001dc55  mov     ecx, eax
0x18001dc57  mov     edx, 0C0000000h
0x18001dc5c  bts     eax, 1Ch
0x18001dc60  and     ecx, edx
0x18001dc62  cmp     ecx, edx
0x18001dc64  cmovnz  eax, ebx
0x18001dc67  add     rsp, 20h
0x18001dc6b  pop     rbx
0x18001dc6c  retn
```
