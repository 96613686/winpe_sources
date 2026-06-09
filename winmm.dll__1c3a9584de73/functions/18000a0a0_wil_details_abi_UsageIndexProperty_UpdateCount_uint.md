# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18000a0a0`
- end: `0x18000a0e9`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180005b0c`
- `0x1800068f4`
- `0x180019170`

## callees

- `0x180006864`
- `0x18000a0a0`

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
0x18000a0a0  sub     rsp, 28h
0x18000a0a4  lea     r8, [rcx+4]; Source
0x18000a0a8  cmp     [r8], edx
0x18000a0ab  jz      short loc_18000A0E4
0x18000a0ad  mov     al, [rcx+2]
0x18000a0b0  mov     [r8], edx
0x18000a0b3  cmp     al, 1
0x18000a0b5  jnz     short loc_18000A0CF
0x18000a0b7  mov     r9d, 2
0x18000a0bd  mov     [rsp+28h+arg_8], dx
0x18000a0c2  movzx   eax, dx
0x18000a0c5  lea     r8, [rsp+28h+arg_8]
0x18000a0ca  mov     edx, r9d
0x18000a0cd  jmp     short loc_18000A0DB
0x18000a0cf  cmp     al, 2
0x18000a0d1  jnz     short loc_18000A0E4
0x18000a0d3  mov     edx, 4; DestinationSize
0x18000a0d8  mov     r9d, edx; SourceSize
0x18000a0db  mov     rcx, [rcx+10h]; Destination
0x18000a0df  call    memcpy_s
0x18000a0e4  add     rsp, 28h
0x18000a0e8  retn
```
