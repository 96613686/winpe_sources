# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18000be20`
- end: `0x18000be6a`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180003df4`
- `0x1800080b0`
- `0x18000b650`

## callees

- `0x18000be20`
- `0x18001028c`

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
0x18000be20  sub     rsp, 28h
0x18000be24  lea     r8, [rcx+4]; Source
0x18000be28  cmp     [r8], edx
0x18000be2b  jz      short loc_18000BE64
0x18000be2d  mov     al, [rcx+2]
0x18000be30  mov     [r8], edx
0x18000be33  cmp     al, 1
0x18000be35  jnz     short loc_18000BE4F
0x18000be37  mov     r9d, 2
0x18000be3d  mov     [rsp+28h+arg_8], dx
0x18000be42  movzx   eax, dx
0x18000be45  lea     r8, [rsp+28h+arg_8]
0x18000be4a  mov     edx, r9d
0x18000be4d  jmp     short loc_18000BE5B
0x18000be4f  cmp     al, 2
0x18000be51  jnz     short loc_18000BE64
0x18000be53  mov     edx, 4; DestinationSize
0x18000be58  mov     r9d, edx; SourceSize
0x18000be5b  mov     rcx, [rcx+10h]; Destination
0x18000be5f  call    memcpy_s
0x18000be64  add     rsp, 28h
0x18000be68  retn
```
