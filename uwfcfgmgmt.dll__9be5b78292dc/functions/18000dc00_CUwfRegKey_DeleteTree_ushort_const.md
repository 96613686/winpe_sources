# CUwfRegKey::DeleteTree(ushort const *)

- ea: `0x18000dc00`
- end: `0x18000dc38`
- name: `?DeleteTree@CUwfRegKey@@QEAAJPEBG@Z`
- size: `56`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007360`
- `0x180007390`

## callees

- `0x18000dc00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000dc17`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000dc17`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::DeleteTree(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  LSTATUS v3; // eax

  if ( a2 )
  {
    v2 = 0;
    v3 = RegDeleteTreeW(*this, a2);
    if ( v3 )
    {
      if ( v3 > 0 )
        return (unsigned __int16)v3 | 0x80070000;
      else
        return (unsigned int)v3;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v2;
}

```

## disassembly

```asm
0x18000dc00  push    rbx
0x18000dc02  sub     rsp, 20h
0x18000dc06  test    rdx, rdx
0x18000dc09  jnz     short loc_18000DC12
0x18000dc0b  mov     ebx, 80004003h
0x18000dc10  jmp     short loc_18000DC30
0x18000dc12  mov     rcx, [rcx]; hKey
0x18000dc15  xor     ebx, ebx
0x18000dc17  call    cs:__imp_RegDeleteTreeW
0x18000dc1d  test    eax, eax
0x18000dc1f  jz      short loc_18000DC30
0x18000dc21  jg      short loc_18000DC27
0x18000dc23  mov     ebx, eax
0x18000dc25  jmp     short loc_18000DC30
0x18000dc27  movzx   ebx, ax
0x18000dc2a  or      ebx, 80070000h
0x18000dc30  mov     eax, ebx
0x18000dc32  add     rsp, 20h
0x18000dc36  pop     rbx
0x18000dc37  retn
```
