# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18001045c`
- end: `0x1800104a5`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000ae64`
- `0x18000dcdc`
- `0x18000fdc0`

## callees

- `0x18001045c`
- `0x180010e4c`

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
0x18001045c  sub     rsp, 28h
0x180010460  lea     r8, [rcx+4]; Source
0x180010464  cmp     [r8], edx
0x180010467  jz      short loc_1800104A0
0x180010469  mov     al, [rcx+2]
0x18001046c  mov     [r8], edx
0x18001046f  cmp     al, 1
0x180010471  jnz     short loc_18001048B
0x180010473  mov     r9d, 2
0x180010479  mov     [rsp+28h+arg_8], dx
0x18001047e  movzx   eax, dx
0x180010481  lea     r8, [rsp+28h+arg_8]
0x180010486  mov     edx, r9d
0x180010489  jmp     short loc_180010497
0x18001048b  cmp     al, 2
0x18001048d  jnz     short loc_1800104A0
0x18001048f  mov     edx, 4; DestinationSize
0x180010494  mov     r9d, edx; SourceSize
0x180010497  mov     rcx, [rcx+10h]; Destination
0x18001049b  call    memcpy_s
0x1800104a0  add     rsp, 28h
0x1800104a4  retn
```
