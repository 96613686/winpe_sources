# ShouldRemoveDeletedThreadEntries(void)

- ea: `0x18001e66c`
- end: `0x18001e6bd`
- name: `?ShouldRemoveDeletedThreadEntries@@YAHXZ`
- size: `81`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001e2c0`

## callees

- `0x18001e66c`
- `0x18001e7b0`

## pseudocode

```c
_BOOL8 ShouldRemoveDeletedThreadEntries(void)
{
  unsigned __int64 v0; // rbx
  unsigned __int64 TickCount; // rax
  unsigned __int64 v3; // rcx

  v0 = LastPerThreadDataCleanup;
  TickCount = LdapGetTickCount();
  if ( !v0 )
    return 1;
  v3 = TickCount - v0;
  if ( v0 > TickCount )
    return v3 + 0xFFFFFFFF > 0x493E0;
  return v3 > 0x493E0;
}

```

## disassembly

```asm
0x18001e66c  push    rbx
0x18001e66e  sub     rsp, 20h
0x18001e672  mov     rbx, cs:?LastPerThreadDataCleanup@@3_KA; unsigned __int64 LastPerThreadDataCleanup
0x18001e679  call    LdapGetTickCount
0x18001e67e  test    rbx, rbx
0x18001e681  jnz     short loc_18001E68F
0x18001e683  mov     eax, 1
0x18001e688  add     rsp, 20h
0x18001e68c  pop     rbx
0x18001e68d  retn
0x18001e68f  mov     rcx, rax
0x18001e692  sub     rcx, rbx
0x18001e695  cmp     rbx, rax
0x18001e698  jbe     short loc_18001E6B0
0x18001e69a  mov     eax, 0FFFFFFFFh
0x18001e69f  add     rcx, rax
0x18001e6a2  xor     eax, eax
0x18001e6a4  cmp     rcx, 493E0h
0x18001e6ab  setnbe  al
0x18001e6ae  jmp     short loc_18001E688
0x18001e6b0  cmp     rcx, 493E0h
0x18001e6b7  ja      short loc_18001E683
0x18001e6b9  xor     eax, eax
0x18001e6bb  jmp     short loc_18001E688
```
