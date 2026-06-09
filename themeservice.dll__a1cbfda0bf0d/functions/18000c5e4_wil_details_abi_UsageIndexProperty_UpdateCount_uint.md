# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18000c5e4`
- end: `0x18000c62e`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180007188`
- `0x18000b200`
- `0x18000c0b4`

## callees

- `0x18000c5e4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c623`
- `msvcrt!memcpy_s` at `0x18000c623`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexProperty::UpdateCount(wil::details_abi::UsageIndexProperty *this, int a2)
{
  __int16 *v2; // r8
  char v3; // al
  rsize_t v4; // r9
  rsize_t v5; // rdx
  __int16 v6; // [rsp+38h] [rbp+10h] BYREF

  v2 = (__int16 *)((char *)this + 4);
  if ( *((_DWORD *)this + 1) != a2 )
  {
    v3 = *((_BYTE *)this + 2);
    *(_DWORD *)v2 = a2;
    if ( v3 == 1 )
    {
      v4 = 2;
      v6 = a2;
      v2 = &v6;
      v5 = 2;
    }
    else
    {
      if ( v3 != 2 )
        return;
      v5 = 4;
      v4 = 4;
    }
    memcpy_s(*((void *const *)this + 2), v5, v2, v4);
  }
}

```

## disassembly

```asm
0x18000c5e4  sub     rsp, 28h
0x18000c5e8  lea     r8, [rcx+4]; Source
0x18000c5ec  cmp     [r8], edx
0x18000c5ef  jz      short loc_18000C629
0x18000c5f1  mov     al, [rcx+2]
0x18000c5f4  mov     [r8], edx
0x18000c5f7  cmp     al, 1
0x18000c5f9  jnz     short loc_18000C613
0x18000c5fb  mov     r9d, 2
0x18000c601  mov     [rsp+28h+arg_8], dx
0x18000c606  movzx   eax, dx
0x18000c609  lea     r8, [rsp+28h+arg_8]
0x18000c60e  mov     edx, r9d
0x18000c611  jmp     short loc_18000C61F
0x18000c613  cmp     al, 2
0x18000c615  jnz     short loc_18000C629
0x18000c617  mov     edx, 4; DestinationSize
0x18000c61c  mov     r9d, edx; SourceSize
0x18000c61f  mov     rcx, [rcx+10h]; Destination
0x18000c623  call    cs:__imp_memcpy_s
0x18000c629  add     rsp, 28h
0x18000c62d  retn
```
